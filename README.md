# DevOps-Project-MultiTier-Bank-Application-with-OpenLDAP-Authentication-Aws

For configuration of Open LDAP followed the steps as mentioned in the screenshot attahed below.

![image](https://github.com/user-attachments/assets/9f4cdfac-4f35-466e-8bed-2dce5a17cf2c)

Edit the password for general setting as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/bd7e3029-88a0-43a1-8847-c813d876e95d)
![image](https://github.com/user-attachments/assets/7f7c663b-60cb-4ecc-948a-bee85434a591)

Edited the server profile as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/30103dfc-fb2b-4910-b868-d38e11a9c72e)
![image](https://github.com/user-attachments/assets/7e2a37b0-5448-4adf-b82d-b7756acb7418)
![image](https://github.com/user-attachments/assets/b4fb6cfa-1034-47ab-86d8-9ad36eb8eefd)
![image](https://github.com/user-attachments/assets/83aa6047-e7e7-4aad-97e5-9ef6c6524294)
![image](https://github.com/user-attachments/assets/e657b626-485d-4188-9a16-cf87dc697023)

The default password for general setting and server profile is **lam** but I changed it as shown in the screenshot attached above and using the changed password I was able to login.

![image](https://github.com/user-attachments/assets/3242ca94-1464-4c94-8b3b-080441af4815)

After the changes as mentioned above tree view is as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/545dd316-322a-4a60-a89a-ce64be457a12)

Now Login with the Open LDAP Manager password as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/abb4d59b-bde7-42d1-9bbc-7519fa09686d)

I had create a Group with the name of sysadmin and User with the name of dexter as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/8016e788-4a09-45f2-943e-187611626b1d)
![image](https://github.com/user-attachments/assets/b6df4214-0a3a-4e6b-98e2-5ddaa3c796c4)

I will Login into Jenkins, SonarQube and Nexus using the user dexter and provided administrator privilege to the user dexter.

**Authentication in Jenkins using Open LDAP**

![image](https://github.com/user-attachments/assets/f41c3ed7-1499-4582-852a-213a0958e34b)
![image](https://github.com/user-attachments/assets/9c5c1873-9000-4042-b47f-4add34943d32)

**Authentication in SonarQube using Open LDAP**
```
vim /opt/sonarqube/conf/sonar.properties             


sonar.security.realm=LDAP
ldap.url=ldap://IP_Address_of_OpenLDAP_Server:389                                           
ldap.bindDn=cn=ldapadm,dc=singhritesh85,dc=com
ldap.bindPassword=Admin123
ldap.user.baseDn=ou=People,dc=singhritesh85,dc=com
ldap.user.request=(&(objectClass=inetOrgPerson)(uid={login}))
ldap.user.realNameAttribute=cn
ldap.user.emailAttribute=mail
ldap.group.baseDn=ou=Group,dc=singhritesh85,dc=com
ldap.group.request=(&(objectClass=groupOfUniqueNames)(uniqueMember={dn}))
sonar.log.level=DEBUG



Now Restart the Sonarqube.
```
Now you will be able to login with Open LDAP user dexter as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/34576962-84e1-4df2-95f1-05453abf6a10)

Here you need to provide privilege to the dexter user in SonarQube which you could do as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/144880f9-3101-4c52-8cff-e3f973388f33)

Configure OpenLDAP for Authentication Sonatype Nexus as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/e3ae82b1-4f70-49c3-b9bf-6de998931861)
![image](https://github.com/user-attachments/assets/973f2041-2b36-4149-a8cc-c3f83ff1747e)
![image](https://github.com/user-attachments/assets/1bc25af7-a5c9-47ba-8eb2-b0f6905b8249)
![image](https://github.com/user-attachments/assets/9d8e912f-887f-4726-a509-50f969464474)
![image](https://github.com/user-attachments/assets/3cc37fd7-0f87-461d-93d0-f16668e4823b)
![image](https://github.com/user-attachments/assets/99015568-3ea0-4536-a53c-6fd697344aa2)
![image](https://github.com/user-attachments/assets/05369024-9568-4d28-b0b1-da2755f1d7f5)
![image](https://github.com/user-attachments/assets/a6862157-6f6f-4577-b6db-8c16e8b1ab10)

Now to provide Administrator privilege to OpenLDAP user dexter follow the below steps.

![image](https://github.com/user-attachments/assets/22307996-3e97-4a2f-8b19-ee19b05f9cad)
![image](https://github.com/user-attachments/assets/bac67c91-7cb2-4616-b5ac-756dc863acc8)
