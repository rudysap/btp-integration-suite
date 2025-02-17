<!-- loiof6eb4332cd5144ef91f4a84cc614ba1c -->

# Enable API Management Capability

You can provision the API Management capability from the **Integration Suite** launchpad.



<a name="loiof6eb4332cd5144ef91f4a84cc614ba1c__prereq_hgt_tfb_stb"/>

## Prerequisites

-   You already have a subaccount and have enable the Cloud Foundry environment in this subaccount. For more information, see [Create a Subaccount](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/05280a123d3044ae97457a25b3013918.html?q=entitlements).

-   An *Integration Suite* entitlement has been created for your subaccount. For more information, see [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/5ba357b4fa1e4de4b9fcc4ae771609da.html?q=entitlements).




<a name="loiof6eb4332cd5144ef91f4a84cc614ba1c__context_kqs_twb_stb"/>

## Context

To set up the API Management capability from Integration Suite, you should first have an Integration Suite subscription.

> ### Note:  
> Ensure that you don’t have an instance of a starter plan created in the same subaccount where you plan to create an Integration Suite subscription. Also, note that API Management capabilities from Integration Suite and API Management subscriptions using the stand-alone tile can’t coexist in the same subaccount.

> ### Note:  
> For visual intructions on how to set up and configure API Management capability from Integration Suite, refer the tutorial [Set Up API Management from Integration Suite | Tutorials for SAP Developers](https://developers.sap.com/tutorials/api-mgmt-isuite-initial-setup.html).



<a name="loiof6eb4332cd5144ef91f4a84cc614ba1c__steps_bnm_ft1_stb"/>

## Procedure

1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

2.  In the navigation area of the subaccount, choose *Services* \> *Service Marketplace* and search for *Integration Suite* and choose *Create*.

3.  On the *New Instances and Subscriptions* dialog, choose Integration Suite as the *Service*, select the *Plan*, and choose *Create*.

    Wait for the subscription to complete successfully.

4.  Choose *View Subscription* on the *Creation in Progress* dialog.

    Check the status of the submission in the *Subscriptions* section on the *Instances and Subscriptions* page. If the subscription is successful, you’ll notice the status of the *Integration Suite* is shown as *Subscribed*.

5.  To access the Integration Suite, assign the *Integration\_Provisioner* role to yourself.

    > ### Note:  
    > If you choose *Go to Application* without assigning the *Integration\_Provisioner* role, an application authentication error appears. If the error persists after assigning the role, clear your web browser cache, and log out of the application and log on again.

    To assign the role:

    1.  On the navigation pane, under *Security*, choose *Users*.

    2.  Select your Username and under *Role Collections* section, choose *Assign Role Collection*.

    3.  In the resulting dialog box, select the *Integration\_Provisioner* role and choose *Assign Role Collection*.


    For detailed instructions, see [Working with Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/393ea0b222754311884123ce564779bd.html?q=SAP%20ID%20Service).

6.  Once the role is assigned, choose *Instances and Subscriptions* on the left navigation pane and under *Subscriptions* look for ***Integration Suite***, and choose **Go To Application**.

    You’re navigated to the *Integration Suite* home page.

7.  On the Integration Suite home page, under *Capabilities*, choose *Add Capabilities*.

8.  To design, develop, publish, and oversee APIs in a secure and scalable environment, select *Manage APIs* on the *Activate Capabilities* dialog, and choose *Next*.

9.  To discover, consume and monitor APIs from a centralized API catalogue, choose *Enable API Business Hub Enterprise*.

    Once you enable API business hub enterprise, you will get an option to enable *Graph*.

10. If you want to expose all your business data in the form of a single semantically connected data graph, select the checkbox for *Graph*, and choose **Next**.

11. Choose *Activate* on the *Activate Capabilities* dialog.

    > ### Note:  
    > If you face any issues during activation or the activation fails, then refer SAP Note [2904202](https://me.sap.com/notes/2904202) and proceed accordingly.

12. On the resulting screen, choose *OK* once the status changes from *In Progress* to *Active*.

13. Log out of *Integration Suite*.

14. At this point, navigate back to the SAP BTP Cockpit and assign the following roles:

    -   *APIManagement.Selfservice.Administrator*: This role is required for the onboarding of API Portal and to get access to its Settings page.

    -   *AuthGroup.SelfService.Admin*: You'll need this role during the onboarding of API business hub enterprise and to get access to it.


    To assign these roles:

    1.  Choose *Security* \> *Users* from the left navigation pane.

    2.  Select your username and under *Role Collections* section, choose *Assign Role Collection*.

    3.  In the resulting dialog box, select the *APIManagement.Selfservice.Administrator* and *AuthGroup.SelfService.Admin* roles and choose *Assign Role Collection*.


15. Once the roles are assigned, log on to the *Integration Suite*.

    > ### Note:  
    > If you are using a trial account, the account will be provisioned automatically. As a result, the option to access *APIs* will not appear under *Settings* in the side-navigation menu once the account is onboarded. During the provisioning process, the system will select the default virtual host for you. You will receive a notification indicating that the account is being provisioned. Once the process is complete, you will be automatically logged out of the Integration Suite. To continue, simply log in again. At this point, you will be able to create APIs, build API proxies as a service provider, and utilize other convenient services provided by the platform.
    > 
    > Steps 16 and 17 are not applicable for the trial users.

16. On the *Integration Suite* home page, choose *Settings* \> *APIs* from the left navigation pane.

17. On the *Configure the API Management Service* screen, configure the following and choose *Set Up*:

    -   Select the *Account type*:

        -   Select the *Non Production* account type for non-business critical activities, such as integrating test systems, testing new scenarios, performance testing, and sandbox activities.
        -   Select the *Production* account type for business critical usages, such as integrating production systems, and productive APIs.

    -   In the *Virtual Host* section, enter the *Host Alias*.

    -   Provide an email ID in the *Notification Contact* field to receive updates.


    In the *Set-up Confirmation* window, review the provided details and choose *Confirm* to start the onboarding process.

    You’re redirected to a progress window, which states *API Management Service Setup In Progress*.

    The *Configuration* process is triggered, where the necessary resources are provisioned for you. It’s followed by *Testing the Setup* process, where a simple API Proxy is deployed and invoked to check that everything is set up properly.

    When the processes complete, the indicators turn green to indicate that the processes are successful. A *Release Notification* mail is sent out to the email IDs provided in the *Configure the API Management Service* screen. This email contains details of the newly set up API Management service on your account.

    > ### Note:  
    > If the API Management Service Setup encounters an error or fails, the onboarding process will automatically retry the setup up to five times. If the same error or failure continues to occur, please report the issue by creating an incident in the [SAP Support Portal](https://support.sap.com/en/index.html). Please use the component OPU-API-OD-OPS for reporting.

    The API Management capability is now configured.

18. You must log out of *Integration Suite* and log in again.

    You can now create APIs, build API proxies as a service provider, or use APIs and other convenient services.




<a name="loiof6eb4332cd5144ef91f4a84cc614ba1c__postreq_y2t_fb3_4zb"/>

## Next Steps

After enabling the API Management capability, you need to first set up the service. For more information, see  <?sap-ot O2O class="- topic/xref " href="f34e86cafb274d4bbef725a610ed225d.xml" text="" desc="" xtrc="xref:6" xtrf="file:/home/builder/src/dita-all/djr1548327031813/loiocf0e5a9be9804817aa649f51a84b9f39_en-US/src/content/localization/en-us/f6eb4332cd5144ef91f4a84cc614ba1c.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

**Related Information**  


[Setting Up API Portal Application Using API Management Standalone Tile](setting-up-api-portal-application-using-api-management-standalone-tile-9d8c7ae.md "You can provision the API portal using the API Management, API Portal standalone tile from the SAP BTP cockpit.")

[Assign User Roles in API Management](https://help.sap.com/viewer/de4066bb3f9240e3bfbcd5614e18c2f9/Cloud/en-US/911ca5a620e94ab581fa159d76b3b108.html "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.") :arrow_upper_right:

[Create an API Provider](../create-an-api-provider-6b263e2.md "Define the details of the host you want an application to reach by creating an API provider.")

[Different Methods of Creating an API Proxy](../different-methods-of-creating-an-api-proxy-4ac0431.md "An API proxy is the data object that contains all the functionality to be executed when an external user wants to access the backend service.")

[Requesting a Custom Domain for a Virtual Host](requesting-a-custom-domain-for-a-virtual-host-6b9e5a3.md "A virtual host lets you host multiple domain names on API Management capability within Integration Suite.")

[Request for a Two-Way SSL Certificate](request-for-a-two-way-ssl-certificate-9faf7ce.md "Request a two-way SSL certificate for the default domain of the virtual host of your API Management service.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "You can deactivate your API Management capability from Integration Suite to disable your account from the API Management service.")

