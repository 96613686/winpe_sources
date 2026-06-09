# SPWebSystemProperties::.cctor

- ea: `0x85a220`
- end: `0x85b09b`
- name: `SPWebSystemProperties::.cctor`
- size: `3707`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x859880`
- `0x85bb70`

## string_xrefs

- `0x85b03a`: `WebTemplate`
- `0x85b05d`: `WebTemplateId`
- `0x85a432`: `Configuration`
- `0x85a49b`: `Created`
- `0x85a248`: `AllowAnonymousAccess`
- `0x85aa13`: `ListTemplates`
- `0x85accf`: `ReusableAcl`
- `0x85a4e1`: `CurrentChangeToken`
- `0x85a56d`: `DataRetrievalServicesSettings`
- `0x85a5d6`: `DocTemplates`
- `0x85a6cb`: `ExternalSecurityProviderSetting`
- `0x85a829`: `HasExternalSecurityProvider`
- `0x85aeff`: `TypeCache`

## pseudocode

```c

```

## disassembly

```asm
0x85a220  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a225  ldstr    aAlerts// "Alerts"
0x85a22a  call     string [mscorlib]System.String::Concat(string, string)
0x85a22f  ldtoken  Microsoft.SharePoint.SPAlertCollection
0x85a234  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a239  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a23e  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Alerts
0x85a243  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a248  ldstr    aAllowanonymous_0// "AllowAnonymousAccess"
0x85a24d  call     string [mscorlib]System.String::Concat(string, string)
0x85a252  ldtoken  [mscorlib]System.Boolean
0x85a257  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a25c  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a261  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AllowAnonymousAccess
0x85a266  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a26b  ldstr    aAllowglobalcat// "AllowGlobalCatalog"
0x85a270  call     string [mscorlib]System.String::Concat(string, string)
0x85a275  ldtoken  [mscorlib]System.Boolean
0x85a27a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a27f  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a284  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AllowGlobalCatalog
0x85a289  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a28e  ldstr    aAllowp2p// "AllowP2P"
0x85a293  call     string [mscorlib]System.String::Concat(string, string)
0x85a298  ldtoken  [mscorlib]System.Boolean
0x85a29d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a2a2  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a2a7  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AllowP2P
0x85a2ac  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a2b1  ldstr    aAllproperties// "AllProperties"
0x85a2b6  call     string [mscorlib]System.String::Concat(string, string)
0x85a2bb  ldtoken  [mscorlib]System.Collections.Hashtable
0x85a2c0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a2c5  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a2ca  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AllProperties
0x85a2cf  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a2d4  ldstr    aAllusers_0// "AllUsers"
0x85a2d9  call     string [mscorlib]System.String::Concat(string, string)
0x85a2de  ldtoken  Microsoft.SharePoint.SPUserCollection
0x85a2e3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a2e8  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a2ed  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AllUsers
0x85a2f2  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a2f7  ldstr    aAlternatecssur_0// "AlternateCssUrl"
0x85a2fc  call     string [mscorlib]System.String::Concat(string, string)
0x85a301  ldtoken  [mscorlib]System.String
0x85a306  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a30b  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a310  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AlternateCssUrl
0x85a315  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a31a  ldstr    aAlternateheade_2// "AlternateHeader"
0x85a31f  call     string [mscorlib]System.String::Concat(string, string)
0x85a324  ldtoken  [mscorlib]System.String
0x85a329  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a32e  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a333  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AlternateHeader
0x85a338  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a33d  ldstr    aAnonymouspermm_2// "AnonymousPermMask64"
0x85a342  call     string [mscorlib]System.String::Concat(string, string)
0x85a347  ldtoken  Microsoft.SharePoint.SPBasePermissions
0x85a34c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a351  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a356  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AnonymousPermMask64
0x85a35b  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a360  ldstr    aAnonymousstate// "AnonymousState"
0x85a365  call     string [mscorlib]System.String::Concat(string, string)
0x85a36a  ldtoken  WebAnonymousState
0x85a36f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a374  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a379  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AnonymousState
0x85a37e  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a383  ldstr    aAudit// "Audit"
0x85a388  call     string [mscorlib]System.String::Concat(string, string)
0x85a38d  ldtoken  Microsoft.SharePoint.SPAudit
0x85a392  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a397  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a39c  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Audit
0x85a3a1  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a3a6  ldstr    aAuthentication_1// "AuthenticationMode"
0x85a3ab  call     string [mscorlib]System.String::Concat(string, string)
0x85a3b0  ldtoken  [System.Web]System.Web.Configuration.AuthenticationMode
0x85a3b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a3ba  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a3bf  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AuthenticationMode
0x85a3c4  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a3c9  ldstr    aAuthor_0// "Author"
0x85a3ce  call     string [mscorlib]System.String::Concat(string, string)
0x85a3d3  ldtoken  Microsoft.SharePoint.SPUser
0x85a3d8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a3dd  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a3e2  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Author
0x85a3e7  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a3ec  ldstr    aAvailableconte// "AvailableContentTypes"
0x85a3f1  call     string [mscorlib]System.String::Concat(string, string)
0x85a3f6  ldtoken  Microsoft.SharePoint.SPContentTypeCollection
0x85a3fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a400  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a405  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AvailableContentTypes
0x85a40a  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a40f  ldstr    aAvailablefield_0// "AvailableFields"
0x85a414  call     string [mscorlib]System.String::Concat(string, string)
0x85a419  ldtoken  Microsoft.SharePoint.SPFieldCollection
0x85a41e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a423  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a428  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::AvailableFields
0x85a42d  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a432  ldstr    aConfiguration_1// "Configuration"
0x85a437  call     string [mscorlib]System.String::Concat(string, string)
0x85a43c  ldtoken  [mscorlib]System.Int16
0x85a441  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a446  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a44b  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Configuration
0x85a450  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a455  ldstr    aContenttypes_0// "ContentTypes"
0x85a45a  call     string [mscorlib]System.String::Concat(string, string)
0x85a45f  ldtoken  Microsoft.SharePoint.SPContentTypeCollection
0x85a464  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a469  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a46e  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::ContentTypes
0x85a473  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a478  ldstr    aContext_3// "Context"
0x85a47d  call     string [mscorlib]System.String::Concat(string, string)
0x85a482  ldtoken  Microsoft.SharePoint.SPContext
0x85a487  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a48c  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a491  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Context
0x85a496  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a49b  ldstr    aCreated_0// "Created"
0x85a4a0  call     string [mscorlib]System.String::Concat(string, string)
0x85a4a5  ldtoken  [mscorlib]System.DateTime
0x85a4aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a4af  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a4b4  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Created
0x85a4b9  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a4be  ldstr    aCurrencylocale_2// "CurrencyLocaleID"
0x85a4c3  call     string [mscorlib]System.String::Concat(string, string)
0x85a4c8  ldtoken  [mscorlib]System.Int32
0x85a4cd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a4d2  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a4d7  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::CurrencyLocaleID
0x85a4dc  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a4e1  ldstr    aCurrentchanget// "CurrentChangeToken"
0x85a4e6  call     string [mscorlib]System.String::Concat(string, string)
0x85a4eb  ldtoken  Microsoft.SharePoint.SPChangeToken
0x85a4f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a4f5  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a4fa  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::CurrentChangeToken
0x85a4ff  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a504  ldstr    aCurrentuser// "CurrentUser"
0x85a509  call     string [mscorlib]System.String::Concat(string, string)
0x85a50e  ldtoken  Microsoft.SharePoint.SPUser
0x85a513  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a518  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a51d  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::CurrentUser
0x85a522  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a527  ldstr    aCustomizationm// "CustomizationMode"
0x85a52c  call     string [mscorlib]System.String::Concat(string, string)
0x85a531  ldtoken  [mscorlib]System.Boolean
0x85a536  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a53b  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a540  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::CustomizationMode
0x85a545  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a54a  ldstr    aCustomjsurl_0// "CustomJSUrl"
0x85a54f  call     string [mscorlib]System.String::Concat(string, string)
0x85a554  ldtoken  [mscorlib]System.String
0x85a559  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a55e  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a563  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::CustomJSUrl
0x85a568  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a56d  ldstr    aDataretrievals// "DataRetrievalServicesSettings"
0x85a572  call     string [mscorlib]System.String::Concat(string, string)
0x85a577  ldtoken  Microsoft.SharePoint.SPDataRetrievalServicesSettings
0x85a57c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a581  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a586  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::DataRetrievalServicesSettings
0x85a58b  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a590  ldstr    aDefaulturl// "DefaultUrl"
0x85a595  call     string [mscorlib]System.String::Concat(string, string)
0x85a59a  ldtoken  [mscorlib]System.String
0x85a59f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a5a4  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a5a9  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::DefaultUrl
0x85a5ae  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a5b3  ldstr    aDescription// "Description"
0x85a5b8  call     string [mscorlib]System.String::Concat(string, string)
0x85a5bd  ldtoken  [mscorlib]System.String
0x85a5c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a5c7  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a5cc  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Description
0x85a5d1  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a5d6  ldstr    aDoctemplates// "DocTemplates"
0x85a5db  call     string [mscorlib]System.String::Concat(string, string)
0x85a5e0  ldtoken  Microsoft.SharePoint.SPDocTemplateCollection
0x85a5e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a5ea  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a5ef  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::DocTemplates
0x85a5f4  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a5f9  ldstr    aEffectivebasep_1// "EffectiveBasePermissions"
0x85a5fe  call     string [mscorlib]System.String::Concat(string, string)
0x85a603  ldtoken  Microsoft.SharePoint.SPBasePermissions
0x85a608  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a60d  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a612  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::EffectiveBasePermissions
0x85a617  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a61c  ldstr    aEffectiveprese// "EffectivePresenceEnabled"
0x85a621  call     string [mscorlib]System.String::Concat(string, string)
0x85a626  ldtoken  [mscorlib]System.Boolean
0x85a62b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a630  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a635  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::EffectivePresenceEnabled
0x85a63a  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a63f  ldstr    aEventhandlerse_0// "EventHandlersEnabled"
0x85a644  call     string [mscorlib]System.String::Concat(string, string)
0x85a649  ldtoken  [mscorlib]System.Boolean
0x85a64e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a653  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a658  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::EventHandlersEnabled
0x85a65d  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a662  ldstr    aEventreceivers// "EventReceivers"
0x85a667  call     string [mscorlib]System.String::Concat(string, string)
0x85a66c  ldtoken  Microsoft.SharePoint.SPEventReceiverDefinitionCollection
0x85a671  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a676  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a67b  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::EventReceivers
0x85a680  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a685  ldstr    aExecuteurl// "ExecuteUrl"
0x85a68a  call     string [mscorlib]System.String::Concat(string, string)
0x85a68f  ldtoken  [mscorlib]System.String
0x85a694  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a699  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a69e  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::ExecuteUrl
0x85a6a3  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a6a8  ldstr    aExists_1// "Exists"
0x85a6ad  call     string [mscorlib]System.String::Concat(string, string)
0x85a6b2  ldtoken  [mscorlib]System.Boolean
0x85a6b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a6bc  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a6c1  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Exists
0x85a6c6  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a6cb  ldstr    aExternalsecuri_1// "ExternalSecurityProviderSetting"
0x85a6d0  call     string [mscorlib]System.String::Concat(string, string)
0x85a6d5  ldtoken  [mscorlib]System.String
0x85a6da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a6df  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a6e4  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::ExternalSecurityProviderSetting
0x85a6e9  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a6ee  ldstr    aFeatures// "Features"
0x85a6f3  call     string [mscorlib]System.String::Concat(string, string)
0x85a6f8  ldtoken  Microsoft.SharePoint.SPFeatureCollection
0x85a6fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a702  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a707  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Features
0x85a70c  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a711  ldstr    aFields_0// "Fields"
0x85a716  call     string [mscorlib]System.String::Concat(string, string)
0x85a71b  ldtoken  Microsoft.SharePoint.SPFieldCollection
0x85a720  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a725  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a72a  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Fields
0x85a72f  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a734  ldstr    aFieldtypedefin// "FieldTypeDefinitionCollection"
0x85a739  call     string [mscorlib]System.String::Concat(string, string)
0x85a73e  ldtoken  Microsoft.SharePoint.SPFieldTypeDefinitionCollection
0x85a743  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a748  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a74d  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::FieldTypeDefinitionCollection
0x85a752  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a757  ldstr    aFiles// "Files"
0x85a75c  call     string [mscorlib]System.String::Concat(string, string)
0x85a761  ldtoken  Microsoft.SharePoint.SPFileCollection
0x85a766  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a76b  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a770  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::Files
0x85a775  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a77a  ldstr    aFirstuniqueanc// "FirstUniqueAncestor"
0x85a77f  call     string [mscorlib]System.String::Concat(string, string)
0x85a784  ldtoken  Microsoft.SharePoint.ISecurableObject
0x85a789  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a78e  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a793  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::FirstUniqueAncestor
0x85a798  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a79d  ldstr    aFirstuniqueanc_0// "FirstUniqueAncestorWeb"
0x85a7a2  call     string [mscorlib]System.String::Concat(string, string)
0x85a7a7  ldtoken  Microsoft.SharePoint.SPWeb
0x85a7ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a7b1  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a7b6  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::FirstUniqueAncestorWeb
0x85a7bb  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a7c0  ldstr    aFirstuniquerol// "FirstUniqueRoleDefinitionWeb"
0x85a7c5  call     string [mscorlib]System.String::Concat(string, string)
0x85a7ca  ldtoken  Microsoft.SharePoint.SPWeb
0x85a7cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a7d4  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
0x85a7d9  stsfld   class Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor SPWebSystemProperties::FirstUniqueRoleDefinitionWeb
0x85a7de  ldsfld   string Microsoft.SharePoint.WebControls.SPDataSource::SystemPropertyPrefix
0x85a7e3  ldstr    aFolders// "Folders"
0x85a7e8  call     string [mscorlib]System.String::Concat(string, string)
0x85a7ed  ldtoken  Microsoft.SharePoint.SPFolderCollection
0x85a7f2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a7f7  newobj   instance void Microsoft.SharePoint.WebControls.SPDataSourceViewPropertyDescriptor::.ctor(string columnName, class [mscorlib]System.Type propertyType)
  ... truncated ...
```
