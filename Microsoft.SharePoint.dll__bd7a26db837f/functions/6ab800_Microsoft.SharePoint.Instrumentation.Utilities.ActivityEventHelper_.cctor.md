# Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::.cctor

- ea: `0x6ab800`
- end: `0x6abb70`
- name: `Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::.cctor`
- size: `880`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x6ab800`

## string_xrefs

- `0x6ab884`: `FileAccessed`
- `0x6ab854`: `AccessRequestApproved`
- `0x6ab859`: `AccessRequestChanged`
- `0x6ab869`: `AccessRequestChanged`
- `0x6ab879`: `AccessRequestChanged`
- `0x6ab864`: `AccessRequestCreated`
- `0x6ab874`: `AccessRequestRejected`
- `0x6ab889`: `FileAccessedOrDownloaded`
- `0x6ab899`: `FileAccessedOrDownloaded`
- `0x6ab8e9`: `FileCreatedOrModified`
- `0x6ab8f9`: `FileCreatedOrModified`
- `0x6ab909`: `FileCreatedOrModified`
- `0x6ab919`: `FileCreatedOrModified`
- `0x6ab904`: `FolderCreated`
- `0x6ab924`: `FileDeleted`
- `0x6ab929`: `FileDeletedOrRestored`
- `0x6ab939`: `FileDeletedOrRestored`
- `0x6ab949`: `FileDeletedOrRestored`
- `0x6ab959`: `FileDeletedOrRestored`
- `0x6ab944`: `FolderDeleted`
- `0x6ab964`: `FileMoved`
- `0x6ab969`: `FileMoved`
- `0x6ab979`: `FileMoved`
- `0x6ab974`: `FolderMoved`
- `0x6ab994`: `FileRenamed`
- `0x6ab999`: `FileRenamed`
- `0x6ab9a9`: `FileRenamed`
- `0x6ab9a4`: `FolderRenamed`
- `0x6ab9e4`: `RemovedFromGroup`
- `0x6aba04`: `GroupRemoved`
- `0x6aba14`: `GroupUpdated`
- `0x6aba44`: `SharingInvitationCreated`
- `0x6aba74`: `RemovedFromSiteCollection`
- `0x6aba84`: `SiteCollectionCreated`
- `0x6abaa4`: `SiteCollectionAdminRemoved`

## pseudocode

```c

```

## disassembly

```asm
0x6ab800  ldstr    aDDD// "([^\\d]*\\d)\\.\\d.*"
0x6ab805  ldc.i4.8
0x6ab806  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x6ab80b  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::VersionRegex
0x6ab810  ldstr    asc_108A384// "[.| |-]"
0x6ab815  ldc.i4.8
0x6ab816  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x6ab81b  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::SeparatorRegex
0x6ab820  ldstr    a38087b0b4ecd48// "38087b0b-4ecd-4871-a63a-cb6942ebe2dd"
0x6ab825  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6ab82a  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::SiphonEventGenerationKillSwitch
0x6ab82f  ldstr    a42656923084041// "42656923-0840-41BA-9029-199B20287C95"
0x6ab834  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6ab839  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::SiphonItemActivityKillSwitch
0x6ab83e  ldstr    a2070b5b4501c42// "2070B5B4-501C-42D6-B503-55FB6384FA79"
0x6ab843  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6ab848  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::SiphonEventPropertiesFilter
0x6ab84d  newobj   instance void [System]System.Collections.Specialized.StringDictionary::.ctor()
0x6ab852  stloc.0
0x6ab853  ldloc.0
0x6ab854  ldstr    aAccessrequesta// "AccessRequestApproved"
0x6ab859  ldstr    aAccessrequestc// "AccessRequestChanged"
0x6ab85e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab863  ldloc.0
0x6ab864  ldstr    aAccessrequestc_0// "AccessRequestCreated"
0x6ab869  ldstr    aAccessrequestc// "AccessRequestChanged"
0x6ab86e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab873  ldloc.0
0x6ab874  ldstr    aAccessrequestr// "AccessRequestRejected"
0x6ab879  ldstr    aAccessrequestc// "AccessRequestChanged"
0x6ab87e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab883  ldloc.0
0x6ab884  ldstr    aFileaccessed// "FileAccessed"
0x6ab889  ldstr    aFileaccessedor// "FileAccessedOrDownloaded"
0x6ab88e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab893  ldloc.0
0x6ab894  ldstr    aFiledownloaded// "FileDownloaded"
0x6ab899  ldstr    aFileaccessedor// "FileAccessedOrDownloaded"
0x6ab89e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab8a3  ldloc.0
0x6ab8a4  ldstr    aFilecheckedin// "FileCheckedIn"
0x6ab8a9  ldstr    aFilecheckedino// "FileCheckedInOrOut"
0x6ab8ae  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab8b3  ldloc.0
0x6ab8b4  ldstr    aFilecheckedout// "FileCheckedOut"
0x6ab8b9  ldstr    aFilecheckedino// "FileCheckedInOrOut"
0x6ab8be  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab8c3  ldloc.0
0x6ab8c4  ldstr    aFilecheckoutdi// "FileCheckOutDiscarded"
0x6ab8c9  ldstr    aFilecheckedino// "FileCheckedInOrOut"
0x6ab8ce  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab8d3  ldloc.0
0x6ab8d4  ldstr    aFilecopied// "FileCopied"
0x6ab8d9  ldstr    aFilecopied// "FileCopied"
0x6ab8de  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab8e3  ldloc.0
0x6ab8e4  ldstr    aFilemodified// "FileModified"
0x6ab8e9  ldstr    aFilecreatedorm// "FileCreatedOrModified"
0x6ab8ee  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab8f3  ldloc.0
0x6ab8f4  ldstr    aFileuploaded// "FileUploaded"
0x6ab8f9  ldstr    aFilecreatedorm// "FileCreatedOrModified"
0x6ab8fe  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab903  ldloc.0
0x6ab904  ldstr    aFoldercreated// "FolderCreated"
0x6ab909  ldstr    aFilecreatedorm// "FileCreatedOrModified"
0x6ab90e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab913  ldloc.0
0x6ab914  ldstr    aFoldermodified// "FolderModified"
0x6ab919  ldstr    aFilecreatedorm// "FileCreatedOrModified"
0x6ab91e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab923  ldloc.0
0x6ab924  ldstr    aFiledeleted// "FileDeleted"
0x6ab929  ldstr    aFiledeletedorr// "FileDeletedOrRestored"
0x6ab92e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab933  ldloc.0
0x6ab934  ldstr    aFilerestored// "FileRestored"
0x6ab939  ldstr    aFiledeletedorr// "FileDeletedOrRestored"
0x6ab93e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab943  ldloc.0
0x6ab944  ldstr    aFolderdeleted// "FolderDeleted"
0x6ab949  ldstr    aFiledeletedorr// "FileDeletedOrRestored"
0x6ab94e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab953  ldloc.0
0x6ab954  ldstr    aFolderrestored// "FolderRestored"
0x6ab959  ldstr    aFiledeletedorr// "FileDeletedOrRestored"
0x6ab95e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab963  ldloc.0
0x6ab964  ldstr    aFilemoved// "FileMoved"
0x6ab969  ldstr    aFilemoved// "FileMoved"
0x6ab96e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab973  ldloc.0
0x6ab974  ldstr    aFoldermoved// "FolderMoved"
0x6ab979  ldstr    aFilemoved// "FileMoved"
0x6ab97e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab983  ldloc.0
0x6ab984  ldstr    aFilepreviewed// "FilePreviewed"
0x6ab989  ldstr    aFilepreviewed// "FilePreviewed"
0x6ab98e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab993  ldloc.0
0x6ab994  ldstr    aFilerenamed// "FileRenamed"
0x6ab999  ldstr    aFilerenamed// "FileRenamed"
0x6ab99e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab9a3  ldloc.0
0x6ab9a4  ldstr    aFolderrenamed// "FolderRenamed"
0x6ab9a9  ldstr    aFilerenamed// "FileRenamed"
0x6ab9ae  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab9b3  ldloc.0
0x6ab9b4  ldstr    aFilesyncdownlo// "FileSyncDownloaded"
0x6ab9b9  ldstr    aFilesyncdownlo// "FileSyncDownloaded"
0x6ab9be  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab9c3  ldloc.0
0x6ab9c4  ldstr    aFilesyncupload// "FileSyncUploaded"
0x6ab9c9  ldstr    aFilesyncupload// "FileSyncUploaded"
0x6ab9ce  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab9d3  ldloc.0
0x6ab9d4  ldstr    aAddedtogroup// "AddedToGroup"
0x6ab9d9  ldstr    aGroupmodified// "GroupModified"
0x6ab9de  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab9e3  ldloc.0
0x6ab9e4  ldstr    aRemovedfromgro// "RemovedFromGroup"
0x6ab9e9  ldstr    aGroupmodified// "GroupModified"
0x6ab9ee  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6ab9f3  ldloc.0
0x6ab9f4  ldstr    aGroupadded// "GroupAdded"
0x6ab9f9  ldstr    aGroupmodified// "GroupModified"
0x6ab9fe  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba03  ldloc.0
0x6aba04  ldstr    aGroupremoved// "GroupRemoved"
0x6aba09  ldstr    aGroupmodified// "GroupModified"
0x6aba0e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba13  ldloc.0
0x6aba14  ldstr    aGroupupdated// "GroupUpdated"
0x6aba19  ldstr    aGroupmodified// "GroupModified"
0x6aba1e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba23  ldloc.0
0x6aba24  ldstr    aPageviewed// "PageViewed"
0x6aba29  ldstr    aPageviewed// "PageViewed"
0x6aba2e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba33  ldloc.0
0x6aba34  ldstr    aSharinginvitat// "SharingInvitationAccepted"
0x6aba39  ldstr    aSharinginvitat_0// "SharingInvitationChanged"
0x6aba3e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba43  ldloc.0
0x6aba44  ldstr    aSharinginvitat_1// "SharingInvitationCreated"
0x6aba49  ldstr    aSharinginvitat_0// "SharingInvitationChanged"
0x6aba4e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba53  ldloc.0
0x6aba54  ldstr    aSharingrevoked// "SharingRevoked"
0x6aba59  ldstr    aSharingsetorre// "SharingSetOrRevoked"
0x6aba5e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba63  ldloc.0
0x6aba64  ldstr    aSharingset// "SharingSet"
0x6aba69  ldstr    aSharingsetorre// "SharingSetOrRevoked"
0x6aba6e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba73  ldloc.0
0x6aba74  ldstr    aRemovedfromsit// "RemovedFromSiteCollection"
0x6aba79  ldstr    aSitecollection_14// "SiteCollectionModified"
0x6aba7e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba83  ldloc.0
0x6aba84  ldstr    aSitecollection_15// "SiteCollectionCreated"
0x6aba89  ldstr    aSitecollection_14// "SiteCollectionModified"
0x6aba8e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6aba93  ldloc.0
0x6aba94  ldstr    aSitecollection_16// "SiteCollectionAdminAdded"
0x6aba99  ldstr    aSitecollection_14// "SiteCollectionModified"
0x6aba9e  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6abaa3  ldloc.0
0x6abaa4  ldstr    aSitecollection_17// "SiteCollectionAdminRemoved"
0x6abaa9  ldstr    aSitecollection_14// "SiteCollectionModified"
0x6abaae  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6abab3  ldloc.0
0x6abab4  ldstr    aVideorequested// "VideoRequested"
0x6abab9  ldstr    aVideorequested// "VideoRequested"
0x6ababe  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x6abac3  ldloc.0
0x6abac4  stsfld   class [System]System.Collections.Specialized.StringDictionary Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::TopicDictionary
0x6abac9  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x6abace  stloc.1
0x6abacf  ldloc.1
0x6abad0  ldstr    aActivity_0// "Activity"
0x6abad5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6abada  pop
0x6abadb  ldloc.1
0x6abadc  ldstr    aActivityid// "ActivityId"
0x6abae1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6abae6  pop
0x6abae7  ldloc.1
0x6abae8  ldstr    aIsactivitycoal// "IsActivityCoalesced"
0x6abaed  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6abaf2  pop
0x6abaf3  ldloc.1
0x6abaf4  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::ExcludeFromEventProperties
0x6abaf9  ldtoken  [Cil.Core]Cil.Events.Internal.Activity.NormalizedUserAgent
0x6abafe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6abb03  call     class [mscorlib]System.Array [mscorlib]System.Enum::GetValues(class [mscorlib]System.Type)
0x6abb08  call     T0x2B0005EA
0x6abb0d  ldsfld   class [mscorlib]System.Func`2<valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedUserAgent, string> Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::CS$<>9__CachedAnonymousMethodDelegate4
0x6abb12  brtrue.s loc_6ABB25
0x6abb14  ldnull
0x6abb15  ldftn    string Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::<.cctor>b__2(valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedUserAgent t)
0x6abb1b  newobj   instance void class [mscorlib]System.Func`2<valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedUserAgent, string>::.ctor(object, native int)
0x6abb20  stsfld   class [mscorlib]System.Func`2<valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedUserAgent, string> Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::CS$<>9__CachedAnonymousMethodDelegate4
0x6abb25  ldsfld   class [mscorlib]System.Func`2<valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedUserAgent, string> Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::CS$<>9__CachedAnonymousMethodDelegate4
0x6abb2a  call     T0x2B0005EB
0x6abb2f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedUserAgent> Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::DictionaryForNormalizedUserAgent
0x6abb34  ldtoken  [Cil.Core]Cil.Events.Internal.Activity.NormalizedFileExtension
0x6abb39  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6abb3e  call     class [mscorlib]System.Array [mscorlib]System.Enum::GetValues(class [mscorlib]System.Type)
0x6abb43  call     T0x2B0005EC
0x6abb48  ldsfld   class [mscorlib]System.Func`2<valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedFileExtension, string> Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::CS$<>9__CachedAnonymousMethodDelegate5
0x6abb4d  brtrue.s loc_6ABB60
0x6abb4f  ldnull
0x6abb50  ldftn    string Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::<.cctor>b__3(valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedFileExtension t)
0x6abb56  newobj   instance void class [mscorlib]System.Func`2<valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedFileExtension, string>::.ctor(object, native int)
0x6abb5b  stsfld   class [mscorlib]System.Func`2<valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedFileExtension, string> Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::CS$<>9__CachedAnonymousMethodDelegate5
0x6abb60  ldsfld   class [mscorlib]System.Func`2<valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedFileExtension, string> Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::CS$<>9__CachedAnonymousMethodDelegate5
0x6abb65  call     T0x2B0005ED
0x6abb6a  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Cil.Core]Cil.Events.Internal.Activity.NormalizedFileExtension> Microsoft.SharePoint.Instrumentation.Utilities.ActivityEventHelper::DictionaryForNormalizedFileExtension
0x6abb6f  ret
```
