# Microsoft.SharePoint.Administration.SPFeatureUseEntry::.cctor

- ea: `0x37e710`
- end: `0x37ebd1`
- name: `Microsoft.SharePoint.Administration.SPFeatureUseEntry::.cctor`
- size: `1217`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x37eab6`: `.Repair`
- `0x37e87b`: `.Copy`
- `0x37e8c7`: `.Move`
- `0x37e8d9`: `.Open`
- `0x37e906`: `.Remove`
- `0x37e90f`: `.Rename`
- `0x37e99f`: `.Read`
- `0x37e9ba`: `.Write`
- `0x37e9d5`: `.Compare`
- `0x37e9de`: `.Compress`
- `0x37ea02`: `.Dismount`
- `0x37ea53`: `.Mount`
- `0x37ea92`: `.Update`
- `0x37eaec`: `.Complete`
- `0x37eb19`: `.Install`
- `0x37eb73`: `.Uninstall`
- `0x37e752`: `Business Intelligence.Excel Services.`
- `0x37e75a`: `Business Solutions.Access Services.`
- `0x37e775`: `Business Solutions.PowerPoint Services.`
- `0x37e77e`: `Business Solutions.Project Services.`
- `0x37e787`: `Business Solutions.Visio Services.`
- `0x37e7d8`: `Content Management.Compliance.`
- `0x37e80e`: `Service.Authentication.`
- `0x37e817`: `Service.Authorization.`
- `0x37e820`: `Service.Availability.`
- `0x37e829`: `Service.Health.`
- `0x37e832`: `Service.Hosting.`
- `0x37e83b`: `Service.Monitoring.`
- `0x37e844`: `Service.Server.`
- `0x37e84d`: `Service.Upgrade.`

## pseudocode

```c

```

## disassembly

```asm
0x37e710  ldc.i4.s 0x24
0x37e712  newarr   [mscorlib]System.String
0x37e717  stloc.0
0x37e718  ldloc.0
0x37e719  ldc.i4.0
0x37e71a  ldstr    aAdministration_57// "Administration.Monitoring."
0x37e71f  stelem.ref
0x37e720  ldloc.0
0x37e721  ldc.i4.1
0x37e722  ldstr    aAdministration_58// "Administration.Server."
0x37e727  stelem.ref
0x37e728  ldloc.0
0x37e729  ldc.i4.2
0x37e72a  ldstr    aAdministration_59// "Administration.Tenant."
0x37e72f  stelem.ref
0x37e730  ldloc.0
0x37e731  ldc.i4.3
0x37e732  ldstr    aAdministration_60// "Administration.Upgrade."
0x37e737  stelem.ref
0x37e738  ldloc.0
0x37e739  ldc.i4.4
0x37e73a  ldstr    aAppsCatalog// "Apps.Catalog."
0x37e73f  stelem.ref
0x37e740  ldloc.0
0x37e741  ldc.i4.5
0x37e742  ldstr    aAppsCustom// "Apps.Custom."
0x37e747  stelem.ref
0x37e748  ldloc.0
0x37e749  ldc.i4.6
0x37e74a  ldstr    aAppsMarketplac// "Apps.Marketplace."
0x37e74f  stelem.ref
0x37e750  ldloc.0
0x37e751  ldc.i4.7
0x37e752  ldstr    aBusinessIntell// "Business Intelligence.Excel Services."
0x37e757  stelem.ref
0x37e758  ldloc.0
0x37e759  ldc.i4.8
0x37e75a  ldstr    aBusinessSoluti// "Business Solutions.Access Services."
0x37e75f  stelem.ref
0x37e760  ldloc.0
0x37e761  ldc.i4.s 9
0x37e763  ldstr    aBusinessSoluti_0// "Business Solutions.Business Connectivit"...
0x37e768  stelem.ref
0x37e769  ldloc.0
0x37e76a  ldc.i4.s 0xA
0x37e76c  ldstr    aBusinessSoluti_1// "Business Solutions.Form-based Applicati"...
0x37e771  stelem.ref
0x37e772  ldloc.0
0x37e773  ldc.i4.s 0xB
0x37e775  ldstr    aBusinessSoluti_2// "Business Solutions.PowerPoint Services."
0x37e77a  stelem.ref
0x37e77b  ldloc.0
0x37e77c  ldc.i4.s 0xC
0x37e77e  ldstr    aBusinessSoluti_3// "Business Solutions.Project Services."
0x37e783  stelem.ref
0x37e784  ldloc.0
0x37e785  ldc.i4.s 0xD
0x37e787  ldstr    aBusinessSoluti_4// "Business Solutions.Visio Services."
0x37e78c  stelem.ref
0x37e78d  ldloc.0
0x37e78e  ldc.i4.s 0xE
0x37e790  ldstr    aBusinessSoluti_5// "Business Solutions.Workflows."
0x37e795  stelem.ref
0x37e796  ldloc.0
0x37e797  ldc.i4.s 0xF
0x37e799  ldstr    aCollaborationP// "Collaboration.People."
0x37e79e  stelem.ref
0x37e79f  ldloc.0
0x37e7a0  ldc.i4.s 0x10
0x37e7a2  ldstr    aCollaborationS// "Collaboration.Sharing."
0x37e7a7  stelem.ref
0x37e7a8  ldloc.0
0x37e7a9  ldc.i4.s 0x11
0x37e7ab  ldstr    aCollaborationS_0// "Collaboration.Sites."
0x37e7b0  stelem.ref
0x37e7b1  ldloc.0
0x37e7b2  ldc.i4.s 0x12
0x37e7b4  ldstr    aCollaborationS_1// "Collaboration.Social."
0x37e7b9  stelem.ref
0x37e7ba  ldloc.0
0x37e7bb  ldc.i4.s 0x13
0x37e7bd  ldstr    aCollaborationW// "Collaboration.Work management."
0x37e7c2  stelem.ref
0x37e7c3  ldloc.0
0x37e7c4  ldc.i4.s 0x14
0x37e7c6  ldstr    aContentManagem_14// "Content Management.Analytics."
0x37e7cb  stelem.ref
0x37e7cc  ldloc.0
0x37e7cd  ldc.i4.s 0x15
0x37e7cf  ldstr    aContentManagem_15// "Content Management.Audit."
0x37e7d4  stelem.ref
0x37e7d5  ldloc.0
0x37e7d6  ldc.i4.s 0x16
0x37e7d8  ldstr    aContentManagem_16// "Content Management.Compliance."
0x37e7dd  stelem.ref
0x37e7de  ldloc.0
0x37e7df  ldc.i4.s 0x17
0x37e7e1  ldstr    aContentManagem_13// "Content Management.Content."
0x37e7e6  stelem.ref
0x37e7e7  ldloc.0
0x37e7e8  ldc.i4.s 0x18
0x37e7ea  ldstr    aContentManagem_17// "Content Management.EDiscovery."
0x37e7ef  stelem.ref
0x37e7f0  ldloc.0
0x37e7f1  ldc.i4.s 0x19
0x37e7f3  ldstr    aContentManagem_18// "Content Management.Record Management."
0x37e7f8  stelem.ref
0x37e7f9  ldloc.0
0x37e7fa  ldc.i4.s 0x1A
0x37e7fc  ldstr    aSearchEnterpri// "Search.Enterprise."
0x37e801  stelem.ref
0x37e802  ldloc.0
0x37e803  ldc.i4.s 0x1B
0x37e805  ldstr    aSearchStandard// "Search.Standard."
0x37e80a  stelem.ref
0x37e80b  ldloc.0
0x37e80c  ldc.i4.s 0x1C
0x37e80e  ldstr    aServiceAuthent// "Service.Authentication."
0x37e813  stelem.ref
0x37e814  ldloc.0
0x37e815  ldc.i4.s 0x1D
0x37e817  ldstr    aServiceAuthori// "Service.Authorization."
0x37e81c  stelem.ref
0x37e81d  ldloc.0
0x37e81e  ldc.i4.s 0x1E
0x37e820  ldstr    aServiceAvailab// "Service.Availability."
0x37e825  stelem.ref
0x37e826  ldloc.0
0x37e827  ldc.i4.s 0x1F
0x37e829  ldstr    aServiceHealth// "Service.Health."
0x37e82e  stelem.ref
0x37e82f  ldloc.0
0x37e830  ldc.i4.s 0x20
0x37e832  ldstr    aServiceHosting// "Service.Hosting."
0x37e837  stelem.ref
0x37e838  ldloc.0
0x37e839  ldc.i4.s 0x21
0x37e83b  ldstr    aServiceMonitor// "Service.Monitoring."
0x37e840  stelem.ref
0x37e841  ldloc.0
0x37e842  ldc.i4.s 0x22
0x37e844  ldstr    aServiceServer// "Service.Server."
0x37e849  stelem.ref
0x37e84a  ldloc.0
0x37e84b  ldc.i4.s 0x23
0x37e84d  ldstr    aServiceUpgrade// "Service.Upgrade."
0x37e852  stelem.ref
0x37e853  ldloc.0
0x37e854  stsfld   string[] Microsoft.SharePoint.Administration.SPFeatureUseEntry::approvedHighLevelFeatures
0x37e859  ldc.i4.s 0x62
0x37e85b  newarr   [mscorlib]System.String
0x37e860  stloc.1
0x37e861  ldloc.1
0x37e862  ldc.i4.0
0x37e863  ldstr    aAdd_1// ".Add"
0x37e868  stelem.ref
0x37e869  ldloc.1
0x37e86a  ldc.i4.1
0x37e86b  ldstr    aClear_0// ".Clear"
0x37e870  stelem.ref
0x37e871  ldloc.1
0x37e872  ldc.i4.2
0x37e873  ldstr    aClose_1// ".Close"
0x37e878  stelem.ref
0x37e879  ldloc.1
0x37e87a  ldc.i4.3
0x37e87b  ldstr    aCopy// ".Copy"
0x37e880  stelem.ref
0x37e881  ldloc.1
0x37e882  ldc.i4.4
0x37e883  ldstr    aEnter// ".Enter"
0x37e888  stelem.ref
0x37e889  ldloc.1
0x37e88a  ldc.i4.5
0x37e88b  ldstr    aExit// ".Exit"
0x37e890  stelem.ref
0x37e891  ldloc.1
0x37e892  ldc.i4.6
0x37e893  ldstr    aFind// ".Find"
0x37e898  stelem.ref
0x37e899  ldloc.1
0x37e89a  ldc.i4.7
0x37e89b  ldstr    aFormat// ".Format"
0x37e8a0  stelem.ref
0x37e8a1  ldloc.1
0x37e8a2  ldc.i4.8
0x37e8a3  ldstr    aGet_1// ".Get"
0x37e8a8  stelem.ref
0x37e8a9  ldloc.1
0x37e8aa  ldc.i4.s 9
0x37e8ac  ldstr    aHide// ".Hide"
0x37e8b1  stelem.ref
0x37e8b2  ldloc.1
0x37e8b3  ldc.i4.s 0xA
0x37e8b5  ldstr    aJoin// ".Join"
0x37e8ba  stelem.ref
0x37e8bb  ldloc.1
0x37e8bc  ldc.i4.s 0xB
0x37e8be  ldstr    aLock_0// ".Lock"
0x37e8c3  stelem.ref
0x37e8c4  ldloc.1
0x37e8c5  ldc.i4.s 0xC
0x37e8c7  ldstr    aMove// ".Move"
0x37e8cc  stelem.ref
0x37e8cd  ldloc.1
0x37e8ce  ldc.i4.s 0xD
0x37e8d0  ldstr    aNew_1// ".New"
0x37e8d5  stelem.ref
0x37e8d6  ldloc.1
0x37e8d7  ldc.i4.s 0xE
0x37e8d9  ldstr    aOpen// ".Open"
0x37e8de  stelem.ref
0x37e8df  ldloc.1
0x37e8e0  ldc.i4.s 0xF
0x37e8e2  ldstr    aOptimize// ".Optimize"
0x37e8e7  stelem.ref
0x37e8e8  ldloc.1
0x37e8e9  ldc.i4.s 0x10
0x37e8eb  ldstr    aPop// ".Pop"
0x37e8f0  stelem.ref
0x37e8f1  ldloc.1
0x37e8f2  ldc.i4.s 0x11
0x37e8f4  ldstr    aPush// ".Push"
0x37e8f9  stelem.ref
0x37e8fa  ldloc.1
0x37e8fb  ldc.i4.s 0x12
0x37e8fd  ldstr    aRedo// ".Redo"
0x37e902  stelem.ref
0x37e903  ldloc.1
0x37e904  ldc.i4.s 0x13
0x37e906  ldstr    aRemove_1// ".Remove"
0x37e90b  stelem.ref
0x37e90c  ldloc.1
0x37e90d  ldc.i4.s 0x14
0x37e90f  ldstr    aRename_0// ".Rename"
0x37e914  stelem.ref
0x37e915  ldloc.1
0x37e916  ldc.i4.s 0x15
0x37e918  ldstr    aReset// ".Reset"
0x37e91d  stelem.ref
0x37e91e  ldloc.1
0x37e91f  ldc.i4.s 0x16
0x37e921  ldstr    aResize// ".Resize"
0x37e926  stelem.ref
0x37e927  ldloc.1
0x37e928  ldc.i4.s 0x17
0x37e92a  ldstr    aSearch_1// ".Search"
0x37e92f  stelem.ref
0x37e930  ldloc.1
0x37e931  ldc.i4.s 0x18
0x37e933  ldstr    aSelect_4// ".Select"
0x37e938  stelem.ref
0x37e939  ldloc.1
0x37e93a  ldc.i4.s 0x19
0x37e93c  ldstr    aSet_0// ".Set"
0x37e941  stelem.ref
0x37e942  ldloc.1
0x37e943  ldc.i4.s 0x1A
0x37e945  ldstr    aShow// ".Show"
0x37e94a  stelem.ref
0x37e94b  ldloc.1
0x37e94c  ldc.i4.s 0x1B
0x37e94e  ldstr    aSkip// ".Skip"
0x37e953  stelem.ref
0x37e954  ldloc.1
0x37e955  ldc.i4.s 0x1C
0x37e957  ldstr    aSplit// ".Split"
0x37e95c  stelem.ref
0x37e95d  ldloc.1
0x37e95e  ldc.i4.s 0x1D
0x37e960  ldstr    aStep// ".Step"
0x37e965  stelem.ref
0x37e966  ldloc.1
0x37e967  ldc.i4.s 0x1E
0x37e969  ldstr    aSwitch// ".Switch"
0x37e96e  stelem.ref
0x37e96f  ldloc.1
0x37e970  ldc.i4.s 0x1F
0x37e972  ldstr    aUndo// ".Undo"
0x37e977  stelem.ref
0x37e978  ldloc.1
0x37e979  ldc.i4.s 0x20
0x37e97b  ldstr    aUnlock// ".Unlock"
0x37e980  stelem.ref
0x37e981  ldloc.1
0x37e982  ldc.i4.s 0x21
0x37e984  ldstr    aWatch// ".Watch"
0x37e989  stelem.ref
0x37e98a  ldloc.1
0x37e98b  ldc.i4.s 0x22
0x37e98d  ldstr    aConnect// ".Connect"
0x37e992  stelem.ref
0x37e993  ldloc.1
0x37e994  ldc.i4.s 0x23
0x37e996  ldstr    aDisconnect// ".Disconnect"
0x37e99b  stelem.ref
0x37e99c  ldloc.1
0x37e99d  ldc.i4.s 0x24
0x37e99f  ldstr    aRead_0// ".Read"
0x37e9a4  stelem.ref
  ... truncated ...
```
