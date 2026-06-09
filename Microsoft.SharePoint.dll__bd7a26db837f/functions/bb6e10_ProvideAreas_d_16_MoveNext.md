# <ProvideAreas>d__16::MoveNext

- ea: `0xbb6e10`
- end: `0xbb954d`
- name: `<ProvideAreas>d__16::MoveNext`
- size: `10045`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x2904e0`
- `0x290610`
- `0xbb6e10`

## string_xrefs

- `0xbb74bf`: `Client File Access`
- `0xbb6e3e`: `Business Connectivity Services`
- `0xbb6ea0`: `Services Infrastructure`
- `0xbb6fa5`: `Configuration`
- `0xbb75a3`: `Configuration`
- `0xbb7063`: `Office Service Finder`
- `0xbb7089`: `Services Infrastructure Assert`
- `0xbb70af`: `Services Infrastructure Br Err`
- `0xbb70d5`: `Services Infrastructure Health`
- `0xbb70fb`: `Services Infrastructure Logging`
- `0xbb73db`: `Azure Access Control`
- `0xbb7427`: `BEC Web Service`
- `0xbb7531`: `Compliance Settings`
- `0xbb7557`: `Config Cache`
- `0xbb757d`: `Config DB`
- `0xbb7687`: `Database Extensions`
- `0xbb76d3`: `DistributedCache`
- `0xbb76f9`: `Doc Conversion Communication`
- `0xbb7745`: `Document Move`
- `0xbb77dd`: `Expression Service`
- `0xbb7a17`: `Marketplace Web Service`
- `0xbb7a3d`: `Micro Services`
- `0xbb7ad5`: `Mount Point`
- `0xbb7b6d`: `Object Cache`
- `0xbb7d35`: `Sandboxed Code Service`
- `0xbb7d81`: `Security`
- `0xbb7da7`: `Security Token`
- `0xbb7dcd`: `Security Token Handler`
- `0xbb7df3`: `Security Token Service`
- `0xbb7e19`: `Security Token Service Caller`
- `0xbb7e8b`: `Service Connections`
- `0xbb7eb1`: `SharePoint Federated Directory API`
- `0xbb7efd`: `Site Cache`
- `0xbb7fbb`: `SkySync REST Service`
- `0xbb8079`: `Static Configuration`
- `0xbb809f`: `Template Cache`
- `0xbb815d`: `Token Binding`
- `0xbb81a9`: `Tracing Controller Service`
- `0xbb821b`: `Unified Logging Service`
- `0xbb834b`: `Workflow Services`
- `0xbb8491`: `CB Common`
- `0xbb85e7`: `Crawler:Azure Plugin`
- `0xbb860d`: `Crawler:Common`
- `0xbb8633`: `Crawler:Content Plugin`
- `0xbb867f`: `Crawler:Gatherer Plugin`
- `0xbb86a5`: `Crawler:Gatherer Service`
- `0xbb87af`: `FDComponentSelection`
- `0xbb8821`: `FDProtocolHandlerInternal`
- `0xbb8847`: `FDProtocolHandlerOutput`
- `0xbb8893`: `FeatureExtractorPlugin`
- `0xbb8a81`: `IDXPIPlugin`
- `0xbb8b3f`: `PerfCounter Common`
- `0xbb8c23`: `QueryCache`
- `0xbb8c49`: `QueryComponentSelection`
- `0xbb8d53`: `ScopesCompilation`
- `0xbb8d79`: `ScopesPlugin`
- `0xbb8dc5`: `Search Featurization`
- `0xbb8deb`: `Search foundation common task`
- `0xbb8e11`: `Search service events`
- `0xbb91a1`: `Tripoli PComp`
- `0xbb94e5`: `TripoliBufferCache`
- `0xbb950b`: `Used Component`

## pseudocode

```c

```

## disassembly

```asm
0xbb6e10  ldarg.0
0xbb6e11  ldfld    int32 <ProvideAreas>d__16::<>1__state
0xbb6e16  stloc.0
0xbb6e17  ldloc.0
0xbb6e18  switch   loc_BB6E36, loc_BB6E98, loc_BB715A, loc_BB8384, loc_BB9544
0xbb6e31  br       loc_BB954B
0xbb6e36  ldarg.0
0xbb6e37  ldc.i4.m1
0xbb6e38  stfld    int32 <ProvideAreas>d__16::<>1__state
0xbb6e3d  ldarg.0
0xbb6e3e  ldstr    aBusinessConnec// "Business Connectivity Services"
0xbb6e43  ldc.i4   0x252B0000
0xbb6e48  ldc.i4   0x252B0000
0xbb6e4d  ldc.i4.0
0xbb6e4e  ldarg.0
0xbb6e4f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::.ctor()
0xbb6e54  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal12
0xbb6e59  ldarg.0
0xbb6e5a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal12
0xbb6e5f  ldstr    aBusinessData// "Business Data"
0xbb6e64  ldnull
0xbb6e65  ldc.i4.s 0x32
0xbb6e67  ldc.i4.s 0x50
0xbb6e69  ldc.i4   0x252B8014
0xbb6e6e  ldc.i4   0x252B014
0xbb6e73  ldc.i4.0
0xbb6e74  ldc.i4.0
0xbb6e75  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb6e7a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb6e7f  ldarg.0
0xbb6e80  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal12
0xbb6e85  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsArea::.ctor(string name, unsigned int32 messageId, unsigned int32 areaId, bool hidden, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> categories)
0xbb6e8a  stfld    class Microsoft.SharePoint.Administration.SPDiagnosticsArea <ProvideAreas>d__16::<>2__current
0xbb6e8f  ldarg.0
0xbb6e90  ldc.i4.1
0xbb6e91  stfld    int32 <ProvideAreas>d__16::<>1__state
0xbb6e96  ldc.i4.1
0xbb6e97  ret
0xbb6e98  ldarg.0
0xbb6e99  ldc.i4.m1
0xbb6e9a  stfld    int32 <ProvideAreas>d__16::<>1__state
0xbb6e9f  ldarg.0
0xbb6ea0  ldstr    aServicesInfras// "Services Infrastructure"
0xbb6ea5  ldc.i4   0x4F330000
0xbb6eaa  ldc.i4   0x4F330000
0xbb6eaf  ldc.i4.0
0xbb6eb0  ldarg.0
0xbb6eb1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::.ctor()
0xbb6eb6  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6ebb  ldarg.0
0xbb6ebc  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6ec1  ldstr    aBrowserUlsLogs// "Browser Uls Logs"
0xbb6ec6  ldnull
0xbb6ec7  ldc.i4.s 0x32
0xbb6ec9  ldc.i4.s 0x50
0xbb6ecb  ldc.i4   0x4F338001
0xbb6ed0  ldc.i4   0x4F33001
0xbb6ed5  ldc.i4.0
0xbb6ed6  ldc.i4.0
0xbb6ed7  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb6edc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb6ee1  ldarg.0
0xbb6ee2  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6ee7  ldstr    aBulsBeacon// "bUls Beacon"
0xbb6eec  ldnull
0xbb6eed  ldc.i4.s 0x32
0xbb6eef  ldc.i4.s 0x50
0xbb6ef1  ldc.i4   0x4F338002
0xbb6ef6  ldc.i4   0x4F33002
0xbb6efb  ldc.i4.0
0xbb6efc  ldc.i4.0
0xbb6efd  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb6f02  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb6f07  ldarg.0
0xbb6f08  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6f0d  ldstr    aBulsCachingHos// "bUls Caching Host"
0xbb6f12  ldnull
0xbb6f13  ldc.i4.s 0x32
0xbb6f15  ldc.i4.s 0x50
0xbb6f17  ldc.i4   0x4F338004
0xbb6f1c  ldc.i4   0x4F33004
0xbb6f21  ldc.i4.0
0xbb6f22  ldc.i4.0
0xbb6f23  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb6f28  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb6f2d  ldarg.0
0xbb6f2e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6f33  ldstr    aBulsClientCore// "bUls Client Core"
0xbb6f38  ldnull
0xbb6f39  ldc.i4.s 0x32
0xbb6f3b  ldc.i4.s 0x50
0xbb6f3d  ldc.i4   0x4F338005
0xbb6f42  ldc.i4   0x4F33005
0xbb6f47  ldc.i4.0
0xbb6f48  ldc.i4.0
0xbb6f49  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb6f4e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb6f53  ldarg.0
0xbb6f54  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6f59  ldstr    aBulsUploadList// "bUls Upload Listener"
0xbb6f5e  ldnull
0xbb6f5f  ldc.i4.s 0x32
0xbb6f61  ldc.i4.s 0x50
0xbb6f63  ldc.i4   0x4F338006
0xbb6f68  ldc.i4   0x4F33006
0xbb6f6d  ldc.i4.0
0xbb6f6e  ldc.i4.0
0xbb6f6f  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb6f74  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb6f79  ldarg.0
0xbb6f7a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6f7f  ldstr    aBulsUploader// "bUls Uploader"
0xbb6f84  ldnull
0xbb6f85  ldc.i4.s 0x32
0xbb6f87  ldc.i4.s 0x50
0xbb6f89  ldc.i4   0x4F338003
0xbb6f8e  ldc.i4   0x4F33003
0xbb6f93  ldc.i4.0
0xbb6f94  ldc.i4.0
0xbb6f95  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb6f9a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb6f9f  ldarg.0
0xbb6fa0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6fa5  ldstr    aConfiguration_1// "Configuration"
0xbb6faa  ldnull
0xbb6fab  ldc.i4.s 0x32
0xbb6fad  ldc.i4.s 0x50
0xbb6faf  ldc.i4   0x4F33800B
0xbb6fb4  ldc.i4   0x4F3300B
0xbb6fb9  ldc.i4.0
0xbb6fba  ldc.i4.0
0xbb6fbb  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb6fc0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb6fc5  ldarg.0
0xbb6fc6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6fcb  ldstr    aGlobalization// "Globalization"
0xbb6fd0  ldnull
0xbb6fd1  ldc.i4.s 0x32
0xbb6fd3  ldc.i4.s 0x50
0xbb6fd5  ldc.i4   0x4F33800F
0xbb6fda  ldc.i4   0x4F3300F
0xbb6fdf  ldc.i4.0
0xbb6fe0  ldc.i4.0
0xbb6fe1  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb6fe6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb6feb  ldarg.0
0xbb6fec  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb6ff1  ldstr    aIdentity// "Identity"
0xbb6ff6  ldnull
0xbb6ff7  ldc.i4.s 0x32
0xbb6ff9  ldc.i4.s 0x50
0xbb6ffb  ldc.i4   0x4F338011
0xbb7000  ldc.i4   0x4F33011
0xbb7005  ldc.i4.0
0xbb7006  ldc.i4.0
0xbb7007  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb700c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb7011  ldarg.0
0xbb7012  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb7017  ldstr    aOfficeLogSanit// "Office Log Sanitizer"
0xbb701c  ldnull
0xbb701d  ldc.i4.s 0x32
0xbb701f  ldc.i4.s 0x50
0xbb7021  ldc.i4   0x4F338008
0xbb7026  ldc.i4   0x4F33008
0xbb702b  ldc.i4.0
0xbb702c  ldc.i4.0
0xbb702d  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb7032  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb7037  ldarg.0
0xbb7038  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb703d  ldstr    aOfficePerforma// "Office Performance Tracing"
0xbb7042  ldnull
0xbb7043  ldc.i4.s 0x32
0xbb7045  ldc.i4.s 0x50
0xbb7047  ldc.i4   0x4F33800E
0xbb704c  ldc.i4   0x4F3300E
0xbb7051  ldc.i4.0
0xbb7052  ldc.i4.0
0xbb7053  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb7058  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb705d  ldarg.0
0xbb705e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb7063  ldstr    aOfficeServiceF// "Office Service Finder"
0xbb7068  ldnull
0xbb7069  ldc.i4.s 0x32
0xbb706b  ldc.i4.s 0x50
0xbb706d  ldc.i4   0x4F33800C
0xbb7072  ldc.i4   0x4F3300C
0xbb7077  ldc.i4.0
0xbb7078  ldc.i4.0
0xbb7079  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb707e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb7083  ldarg.0
0xbb7084  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb7089  ldstr    aServicesInfras_0// "Services Infrastructure Assert"
0xbb708e  ldnull
0xbb708f  ldc.i4.s 0x32
0xbb7091  ldc.i4.s 0x50
0xbb7093  ldc.i4   0x4F33800A
0xbb7098  ldc.i4   0x4F3300A
0xbb709d  ldc.i4.0
0xbb709e  ldc.i4.0
0xbb709f  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb70a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb70a9  ldarg.0
0xbb70aa  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb70af  ldstr    aServicesInfras_1// "Services Infrastructure Br Err"
0xbb70b4  ldnull
0xbb70b5  ldc.i4.s 0x32
0xbb70b7  ldc.i4.s 0x50
0xbb70b9  ldc.i4   0x4F338009
0xbb70be  ldc.i4   0x4F33009
0xbb70c3  ldc.i4.0
0xbb70c4  ldc.i4.0
0xbb70c5  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb70ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb70cf  ldarg.0
0xbb70d0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb70d5  ldstr    aServicesInfras_2// "Services Infrastructure Health"
0xbb70da  ldnull
0xbb70db  ldc.i4.s 0x32
0xbb70dd  ldc.i4.s 0x50
0xbb70df  ldc.i4   0x4F33800D
0xbb70e4  ldc.i4   0x4F3300D
0xbb70e9  ldc.i4.0
0xbb70ea  ldc.i4.0
0xbb70eb  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb70f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb70f5  ldarg.0
0xbb70f6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb70fb  ldstr    aServicesInfras_3// "Services Infrastructure Logging"
0xbb7100  ldnull
0xbb7101  ldc.i4.s 0x32
0xbb7103  ldc.i4.s 0x50
0xbb7105  ldc.i4   0x4F338007
0xbb710a  ldc.i4   0x4F33007
0xbb710f  ldc.i4.0
0xbb7110  ldc.i4.0
0xbb7111  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb7116  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb711b  ldarg.0
0xbb711c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb7121  ldstr    aUnrepresentedP// "Unrepresented Portable Log Cats"
0xbb7126  ldnull
0xbb7127  ldc.i4.s 0x32
0xbb7129  ldc.i4.s 0x50
0xbb712b  ldc.i4   0x4F338010
0xbb7130  ldc.i4   0x4F33010
0xbb7135  ldc.i4.0
0xbb7136  ldc.i4.0
0xbb7137  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb713c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb7141  ldarg.0
0xbb7142  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal13
0xbb7147  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsArea::.ctor(string name, unsigned int32 messageId, unsigned int32 areaId, bool hidden, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> categories)
0xbb714c  stfld    class Microsoft.SharePoint.Administration.SPDiagnosticsArea <ProvideAreas>d__16::<>2__current
0xbb7151  ldarg.0
0xbb7152  ldc.i4.2
0xbb7153  stfld    int32 <ProvideAreas>d__16::<>1__state
0xbb7158  ldc.i4.1
0xbb7159  ret
0xbb715a  ldarg.0
0xbb715b  ldc.i4.m1
0xbb715c  stfld    int32 <ProvideAreas>d__16::<>1__state
0xbb7161  ldarg.0
0xbb7162  ldstr    aSharepointFoun// "SharePoint Foundation"
0xbb7167  ldc.i4   0x6FB70000
0xbb716c  ldc.i4   0x6FB70000
0xbb7171  ldc.i4.0
0xbb7172  ldarg.0
0xbb7173  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::.ctor()
0xbb7178  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal14
0xbb717d  ldarg.0
0xbb717e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal14
0xbb7183  ldstr    aUnknown_0// "Unknown"
0xbb7188  ldnull
0xbb7189  ldc.i4.s 0x32
0xbb718b  ldc.i4.s 0x28
0xbb718d  ldc.i4.0
0xbb718e  ldc.i4.m1
0xbb718f  ldc.i4.1
0xbb7190  ldc.i4.1
0xbb7191  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb7196  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb719b  ldarg.0
0xbb719c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal14
0xbb71a1  ldstr    aAbs// "Abs"
0xbb71a6  ldnull
0xbb71a7  ldc.i4.s 0x32
0xbb71a9  ldc.i4.s 0x50
0xbb71ab  ldc.i4   0x6FB78061
0xbb71b0  ldc.i4   0x6FB7061
0xbb71b5  ldc.i4.0
0xbb71b6  ldc.i4.0
0xbb71b7  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsCategory::.ctor(string name, string localizedName, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceDefault, valuetype Microsoft.SharePoint.Administration.EventSeverity eventDefault, unsigned int32 messageId, unsigned int32 categoryId, bool hidden, bool shadow)
0xbb71bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory>::Add(var<u1>)
0xbb71c1  ldarg.0
0xbb71c2  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPDiagnosticsCategory> <ProvideAreas>d__16::<>g__initLocal14
0xbb71c7  ldstr    aAlerts// "Alerts"
  ... truncated ...
```
