# Microsoft.SharePoint.Upgrade.SPConstant::.cctor

- ea: `0xa47c70`
- end: `0xa47f53`
- name: `Microsoft.SharePoint.Upgrade.SPConstant::.cctor`
- size: `739`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xa47e4d`: `Template\sql\appmngext.sql`
- `0xa47e56`: `Template\sql\spsearch.sql`
- `0xa47e45`: `Template\sql\sitemapdb.sql`
- `0xa47d9b`: `SQL Data Services`
- `0xa47dd1`: `Software\Microsoft\Shared Tools\Web Server Extensions\12.0\Secure\ConfigDB`
- `0xa47e0d`: `Template\sql\storePre.sql`
- `0xa47e15`: `Template\sql\configdb.sql`
- `0xa47e1d`: `Template\sql\configup.sql`
- `0xa47e25`: `Template\sql\store.sql`
- `0xa47e2d`: `Template\sql\usagedb.sql`
- `0xa47e35`: `Template\sql\usgdbup.sql`
- `0xa47e3d`: `Template\sql\subscriptionsettings.sql`
- `0xa47e5f`: `Template\sql\store_gb18030_2022.sql`
- `0xa47eba`: `Microsoft.SharePoint.Dsp.XmlUrl`
- `0xa47ed3`: `Microsoft.SharePoint.Security`
- `0xa47efc`: `Microsoft.SharePoint.WorkflowActions, Version=12.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0xa47f3e`: `, Culture=neutral, PublicKeyToken=71e9bce111e9429c`

## pseudocode

```c

```

## disassembly

```asm
0xa47c70  ldc.i4.0
0xa47c71  newarr   [mscorlib]System.Object
0xa47c76  stsfld   object[] Microsoft.SharePoint.Upgrade.SPConstant::EmptyObjectArray
0xa47c7b  ldstr    a0000_0// "0.0.0.0"
0xa47c80  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47c85  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::NullVersion
0xa47c8a  ldstr    a12000// "12.0.0.0"
0xa47c8f  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47c94  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv3StartBuildVersion
0xa47c99  ldstr    a4000// "4.0.0.0"
0xa47c9e  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47ca3  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv4StartSchemaVersion
0xa47ca8  ldstr    a40250// "4.0.25.0"
0xa47cad  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47cb2  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv4RTMEndSchemaVersion
0xa47cb7  ldstr    a15000// "15.0.0.0"
0xa47cbc  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47cc1  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv5StartSchemaVersion
0xa47cc6  ldstr    a14045141000// "14.0.4514.1000"
0xa47ccb  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47cd0  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::SharePoint14Beta2BuildVersion
0xa47cd5  ldstr    a14047301000// "14.0.4730.1000"
0xa47cda  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47cdf  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::SharePoint14RCBuildVersion
0xa47ce4  ldstr    a12004518// "12.0.0.4518"
0xa47ce9  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47cee  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv3RTMBuildVersion
0xa47cf3  ldstr    a12006421// "12.0.0.6421"
0xa47cf8  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47cfd  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv3SP2BuildVersion
0xa47d02  ldstr    a12045181016// "12.0.4518.1016"
0xa47d07  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47d0c  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv3RTMDotBuildVersion
0xa47d11  ldstr    a15044201017// "15.0.4420.1017"
0xa47d16  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47d1b  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv15RTMBuildVersion
0xa47d20  ldstr    a15044811005// "15.0.4481.1005"
0xa47d25  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47d2a  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv15March2013PUBuildVersion
0xa47d2f  ldc.i4.s 0x10
0xa47d31  ldc.i4.0
0xa47d32  ldc.i4.0
0xa47d33  ldc.i4.0
0xa47d34  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0xa47d39  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSCurrentStartBuildVersion
0xa47d3e  ldsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv15RTMBuildVersion
0xa47d43  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::MinSupportedBuildVersion
0xa47d48  ldc.i4.s 0xF
0xa47d4a  ldc.i4.0
0xa47d4b  ldc.i4   0x8A
0xa47d50  ldc.i4.0
0xa47d51  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0xa47d56  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::MinSupportedBetaVersion
0xa47d5b  ldsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSv4StartSchemaVersion
0xa47d60  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::MinSupportedSchemaVersion
0xa47d65  ldstr    a15000// "15.0.0.0"
0xa47d6a  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xa47d6f  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::MinSupportedPersistedObjectSchemaVersion
0xa47d74  ldc.i4.s 0xD
0xa47d76  ldc.i4.0
0xa47d77  ldc.i4   0x641
0xa47d7c  ldc.i4.5
0xa47d7d  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0xa47d82  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::SqlMinProductVersion
0xa47d87  ldc.i4.s 0xB
0xa47d89  ldc.i4.0
0xa47d8a  ldc.i4   0x716
0xa47d8f  ldc.i4.s 0x1E
0xa47d91  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0xa47d96  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::SqlAzureMinProductVersion
0xa47d9b  ldstr    aSqlDataService// "SQL Data Services"
0xa47da0  stsfld   string Microsoft.SharePoint.Upgrade.SPConstant::SqlAzureProductName
0xa47da5  ldc.i4.s 0xC
0xa47da7  ldc.i4.0
0xa47da8  ldc.i4   0x7D0
0xa47dad  ldc.i4.8
0xa47dae  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0xa47db3  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::SqlAzureMIMinProductVersion
0xa47db8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa47dbd  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Upgrade.SPConstant::BuildVersionId
0xa47dc2  ldstr    a0x14b00c340x3f// "{0x14b00c34, 0x3f09, 0x441f, {0xaf, 0x5"...
0xa47dc7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa47dcc  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Upgrade.SPConstant::ClusterConfigGuid
0xa47dd1  ldstr    aSoftwareMicros_24// "Software\\Microsoft\\Shared Tools\\Web "...
0xa47dd6  stsfld   string Microsoft.SharePoint.Upgrade.SPConstant::PreviousConfigDatabaseRegKeyPath
0xa47ddb  ldstr    aUpgradestoptyp// "UpgradeStopTypeName"
0xa47de0  stsfld   string Microsoft.SharePoint.Upgrade.SPConstant::RegValueUpgradeStopTypeName
0xa47de5  ldstr    aUpgradestopsch// "UpgradeStopSchemaVersion"
0xa47dea  stsfld   string Microsoft.SharePoint.Upgrade.SPConstant::RegValueUpgradeStopSchemaVersion
0xa47def  ldstr    aUpgradedebugge// "UpgradeDebuggerConnect"
0xa47df4  stsfld   string Microsoft.SharePoint.Upgrade.SPConstant::RegValueUpgradeDebuggerConnect
0xa47df9  ldstr    aUpgradetimeout// "UpgradeTimeoutOverride"
0xa47dfe  stsfld   string Microsoft.SharePoint.Upgrade.SPConstant::RegValueUpgradeTimeoutOverride
0xa47e03  ldc.i4.s 0xB
0xa47e05  newarr   [mscorlib]System.String
0xa47e0a  stloc.0
0xa47e0b  ldloc.0
0xa47e0c  ldc.i4.0
0xa47e0d  ldstr    aTemplateSqlSto// "Template\\sql\\storePre.sql"
0xa47e12  stelem.ref
0xa47e13  ldloc.0
0xa47e14  ldc.i4.1
0xa47e15  ldstr    aTemplateSqlCon// "Template\\sql\\configdb.sql"
0xa47e1a  stelem.ref
0xa47e1b  ldloc.0
0xa47e1c  ldc.i4.2
0xa47e1d  ldstr    aTemplateSqlCon_0// "Template\\sql\\configup.sql"
0xa47e22  stelem.ref
0xa47e23  ldloc.0
0xa47e24  ldc.i4.3
0xa47e25  ldstr    aTemplateSqlSto_0// "Template\\sql\\store.sql"
0xa47e2a  stelem.ref
0xa47e2b  ldloc.0
0xa47e2c  ldc.i4.4
0xa47e2d  ldstr    aTemplateSqlUsa// "Template\\sql\\usagedb.sql"
0xa47e32  stelem.ref
0xa47e33  ldloc.0
0xa47e34  ldc.i4.5
0xa47e35  ldstr    aTemplateSqlUsg// "Template\\sql\\usgdbup.sql"
0xa47e3a  stelem.ref
0xa47e3b  ldloc.0
0xa47e3c  ldc.i4.6
0xa47e3d  ldstr    aTemplateSqlSub_0// "Template\\sql\\subscriptionsettings.sql"
0xa47e42  stelem.ref
0xa47e43  ldloc.0
0xa47e44  ldc.i4.7
0xa47e45  ldstr    aTemplateSqlSit// "Template\\sql\\sitemapdb.sql"
0xa47e4a  stelem.ref
0xa47e4b  ldloc.0
0xa47e4c  ldc.i4.8
0xa47e4d  ldstr    aTemplateSqlApp// "Template\\sql\\appmngext.sql"
0xa47e52  stelem.ref
0xa47e53  ldloc.0
0xa47e54  ldc.i4.s 9
0xa47e56  ldstr    aTemplateSqlSps// "Template\\sql\\spsearch.sql"
0xa47e5b  stelem.ref
0xa47e5c  ldloc.0
0xa47e5d  ldc.i4.s 0xA
0xa47e5f  ldstr    aTemplateSqlSto_1// "Template\\sql\\store_gb18030_2022.sql"
0xa47e64  stelem.ref
0xa47e65  ldloc.0
0xa47e66  stsfld   string[] Microsoft.SharePoint.Upgrade.SPConstant::SqlFileMapping
0xa47e6b  ldc.i4.1
0xa47e6c  newarr   [mscorlib]System.String
0xa47e71  stloc.1
0xa47e72  ldloc.1
0xa47e73  ldc.i4.0
0xa47e74  ldstr    a21140409700011// "{21140409-7000-11D3-8CFE-0150048383C9}"
0xa47e79  stelem.ref
0xa47e7a  ldloc.1
0xa47e7b  stsfld   string[] Microsoft.SharePoint.Upgrade.SPConstant::WSSProductCodes
0xa47e80  ldc.i4.s 0xA
0xa47e82  newarr   [mscorlib]System.String
0xa47e87  stloc.2
0xa47e88  ldloc.2
0xa47e89  ldc.i4.0
0xa47e8a  ldstr    aMicrosoftShare_56// "Microsoft.SharePoint.ApplicationPages"
0xa47e8f  stelem.ref
0xa47e90  ldloc.2
0xa47e91  ldc.i4.1
0xa47e92  ldstr    aMicrosoftShare_267// "Microsoft.SharePoint.ApplicationPages.A"...
0xa47e97  stelem.ref
0xa47e98  ldloc.2
0xa47e99  ldc.i4.2
0xa47e9a  ldstr    aMicrosoftShare_58// "Microsoft.SharePoint.Dsp"
0xa47e9f  stelem.ref
0xa47ea0  ldloc.2
0xa47ea1  ldc.i4.3
0xa47ea2  ldstr    aMicrosoftShare_268// "Microsoft.SharePoint.Dsp.OleDb"
0xa47ea7  stelem.ref
0xa47ea8  ldloc.2
0xa47ea9  ldc.i4.4
0xa47eaa  ldstr    aMicrosoftShare_269// "Microsoft.SharePoint.Dsp.SoapPT"
0xa47eaf  stelem.ref
0xa47eb0  ldloc.2
0xa47eb1  ldc.i4.5
0xa47eb2  ldstr    aMicrosoftShare_270// "Microsoft.SharePoint.Dsp.Sts"
0xa47eb7  stelem.ref
0xa47eb8  ldloc.2
0xa47eb9  ldc.i4.6
0xa47eba  ldstr    aMicrosoftShare_271// "Microsoft.SharePoint.Dsp.XmlUrl"
0xa47ebf  stelem.ref
0xa47ec0  ldloc.2
0xa47ec1  ldc.i4.7
0xa47ec2  ldstr    aMicrosoftShare_272// "Microsoft.SharePoint.intl"
0xa47ec7  stelem.ref
0xa47ec8  ldloc.2
0xa47ec9  ldc.i4.8
0xa47eca  ldstr    aMicrosoftShare_59// "Microsoft.SharePoint.Library"
0xa47ecf  stelem.ref
0xa47ed0  ldloc.2
0xa47ed1  ldc.i4.s 9
0xa47ed3  ldstr    aMicrosoftShare_273// "Microsoft.SharePoint.Security"
0xa47ed8  stelem.ref
0xa47ed9  ldloc.2
0xa47eda  stsfld   string[] Microsoft.SharePoint.Upgrade.SPConstant::WSSAssemblies
0xa47edf  ldc.i4.2
0xa47ee0  newarr   string[]
0xa47ee5  stloc.3
0xa47ee6  ldloc.3
0xa47ee7  ldc.i4.0
0xa47ee8  ldc.i4.2
0xa47ee9  newarr   [mscorlib]System.String
0xa47eee  stloc.s  4
0xa47ef0  ldloc.s  4
0xa47ef2  ldc.i4.0
0xa47ef3  ldstr    aMicrosoftShare_274// "Microsoft.SharePoint.WorkflowActions, V"...
0xa47ef8  stelem.ref
0xa47ef9  ldloc.s  4
0xa47efb  ldc.i4.1
0xa47efc  ldstr    aMicrosoftShare_275// "Microsoft.SharePoint.WorkflowActions, V"...
0xa47f01  stelem.ref
0xa47f02  ldloc.s  4
0xa47f04  stelem.ref
0xa47f05  ldloc.3
0xa47f06  ldc.i4.1
0xa47f07  ldc.i4.2
0xa47f08  newarr   [mscorlib]System.String
0xa47f0d  stloc.s  5
0xa47f0f  ldloc.s  5
0xa47f11  ldc.i4.0
0xa47f12  ldstr    aMicrosoftShare_276// "Microsoft.SharePoint.WorkflowActions, V"...
0xa47f17  ldsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSCurrentStartBuildVersion
0xa47f1c  callvirt instance string [mscorlib]System.Object::ToString()
0xa47f21  ldstr    aCultureNeutral// ", Culture=neutral"
0xa47f26  call     string [mscorlib]System.String::Concat(string, string, string)
0xa47f2b  stelem.ref
0xa47f2c  ldloc.s  5
0xa47f2e  ldc.i4.1
0xa47f2f  ldstr    aMicrosoftShare_276// "Microsoft.SharePoint.WorkflowActions, V"...
0xa47f34  ldsfld   class [mscorlib]System.Version Microsoft.SharePoint.Upgrade.SPConstant::WSSCurrentStartBuildVersion
0xa47f39  callvirt instance string [mscorlib]System.Object::ToString()
0xa47f3e  ldstr    aCultureNeutral_0// ", Culture=neutral, PublicKeyToken=71e9b"...
0xa47f43  call     string [mscorlib]System.String::Concat(string, string, string)
0xa47f48  stelem.ref
0xa47f49  ldloc.s  5
0xa47f4b  stelem.ref
0xa47f4c  ldloc.3
0xa47f4d  stsfld   string[][] Microsoft.SharePoint.Upgrade.SPConstant::QualifyAssemblies
0xa47f52  ret
```
