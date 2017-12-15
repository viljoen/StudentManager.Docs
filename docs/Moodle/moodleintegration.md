## **Moodle and Student Manager Integration**

## In Moodle
/admin/search.php?query=webservicesoverview

1. Enable web services - Yes
2. Enable protocols - REST protocols
3. Create a specific user
4. Check user capability 

        a. Users > Permissions > Define Roles > Add a new role
        b. Use Role or archetype: Manager
        c. Continue
        dd.
        d. Short name: studentmanagerwebaccess
        e. Custom full name: Student Manager Web Access
        f. Allow Role assignments - Select all
        g. Capability

            i. webservice/rest:use
            ii. moodle/course:create
            iii.moodle/course:visibility
            iv. moodle/course:delete
            v.  moodle/category:viewhiddencategories
            vi. moodle/course:managegroups
            vii. moodle/role:assign
            viii.moodle/user:create
            ix.  moodle/user:delete
            x.   enrol/manual:enrol

        h. Create this Role:
           
        i. Users > Permissions > Assign system roles
           - Select role you created earlier
           - Select the user you created earlier
           - Add

5. Select a Service

        a. External Service
        b. Add
        c. Name: Student Manager
        d. Short name: studentmanager
        e. Enabled: Yes
        f. Authorised User only: Yes
        g. More Options – Required Capabilities: webservice/rest:use: Use REST protocol
        h. Add Service

6. Add Functions - Functions

- enrol_manual_enrol_users
- core_group_add_group_members
- core_user_create_users
- core_course_create_courses
- core_group_create_groups
- core_course_get_categories
- core_role_assign_roles
- core_role_unassign_roles
- core_user_delete_users
- core_course_delete_courses
- core_group_delete_groups

7. Select a Specific User > Authorised Users

    a. Select the user you created earlier
    
    b. Add

8. Create a token for a user

    a. Select the user you created earlier

    b. Service: Student Manager

    c. Save changes

    d. Save token

## In Student Manager

Go to: 

- Settings – Moodle Integration
- Moodle URL: The base Url of your Moodle installation
- Moodle Token: The token you saved in step 8d
- /admin/roles/manage.php

If you select the role, in the address bar you’ll see roleid= 
The number after roleid is the number you want to put for each option below

- Moodle Student Role Id: The Id of the role for students
- Moodle Lecturer Role Id: The Id of the role for lecturers
- Moodle Assessor Role Id: The Id of the role for assessors

## **Moodle Student Manager Authentication Plugin**

This plugin allows Moodle users to log in with their Student Manager details. You can do this by:

1. Downloading the following folder and zip the student manager folder - https://github.com/AgileSystemsTechnology/StudentManager.Moodle
2. Site administration – Plugins – Install plugins
3. Add new file – select zip
4. Continue
5. Upgrade Moodle database
7. Site administration - Plugins – Manage Authentication
8. Enable Student Manager
9. Move Student Manager to the top of the list


















