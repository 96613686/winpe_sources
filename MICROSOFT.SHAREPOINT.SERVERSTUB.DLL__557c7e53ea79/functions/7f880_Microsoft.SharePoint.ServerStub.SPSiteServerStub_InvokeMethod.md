# Microsoft.SharePoint.ServerStub.SPSiteServerStub::InvokeMethod

- ea: `0x7f880`
- end: `0x7ffd1`
- name: `Microsoft.SharePoint.ServerStub.SPSiteServerStub::InvokeMethod`
- size: `1873`
- prototype: ``
- caller_count: `0`
- callee_count: `40`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7f280`
- `0x7f290`
- `0x7f2a0`
- `0x7f2c0`
- `0x7f2d0`
- `0x7f2e0`
- `0x7f2f0`
- `0x7f300`
- `0x7f320`
- `0x7f350`
- `0x7f360`
- `0x7f370`
- `0x7f390`
- `0x7f3b0`
- `0x7f3e0`
- `0x7f420`
- `0x7f450`
- `0x7f490`
- `0x7f4b0`
- `0x7f4c0`
- `0x7f4e0`
- `0x7f530`
- `0x7f590`
- `0x7f5f0`
- `0x7f630`
- `0x7f670`
- `0x7f6b0`
- `0x7f6d0`
- `0x7f6f0`
- `0x7f750`
- `0x7f770`
- `0x7f790`
- `0x7f7b0`
- `0x7f7e0`
- `0x7f7f0`
- `0x7f800`
- `0x7f830`
- `0x7f850`
- `0x7f870`
- `0x7f880`

## string_xrefs

- `0x7fa7c`: `RestUpdate`
- `0x7ff3f`: `RestUpdate`
- `0x7f8fb`: `RemoveHubSite`
- `0x7fbf0`: `RemoveHubSite`
- `0x7f95e`: `UpdateClientObjectModelUseRemoteAPIsPermissionSetting`
- `0x7fcca`: `UpdateClientObjectModelUseRemoteAPIsPermissionSetting`
- `0x7f985`: `CreatePreviewSPSite`
- `0x7fd21`: `CreatePreviewSPSite`
- `0x7f99f`: `DeleteMigrationJob`
- `0x7fd59`: `DeleteMigrationJob`
- `0x7f9c6`: `CreateMigrationJob`
- `0x7fdb4`: `CreateMigrationJob`
- `0x7f9d3`: `CreateMigrationJobEncrypted`
- `0x7fdd4`: `CreateMigrationJobEncrypted`
- `0x7f9e0`: `CreateMigrationIngestionJob`
- `0x7fdf4`: `CreateMigrationIngestionJob`
- `0x7f9ed`: `MultiGeoCopyJob`
- `0x7fe14`: `MultiGeoCopyJob`
- `0x7f9fa`: `CreateCopyJob`
- `0x7fe30`: `CreateCopyJob`
- `0x7fa07`: `CreateCopyJobs`
- `0x7fe4b`: `CreateCopyJobs`
- `0x7fa14`: `GetCopyJobProgress`
- `0x7fe66`: `GetCopyJobProgress`
- `0x7fa3b`: `OpenWeb`
- `0x7feb7`: `OpenWeb`
- `0x7fa48`: `OpenWebUsingPath`
- `0x7fed2`: `OpenWebUsingPath`
- `0x7fa55`: `OpenWebById`
- `0x7feed`: `OpenWebById`
- `0x7fa62`: `GetWebPath`
- `0x7ff08`: `GetWebPath`
- `0x7fa89`: `GetWebTemplates`
- `0x7ff5b`: `GetWebTemplates`
- `0x7fa96`: `GetCustomListTemplates`
- `0x7ff76`: `GetCustomListTemplates`

## pseudocode

```c

```

## disassembly

```asm
0x7f880  ldarg.s  4
0x7f882  brtrue.s loc_7F88F
0x7f884  ldstr    aProxycontext// "proxyContext"
0x7f889  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7f88e  throw
0x7f88f  ldarg.1
0x7f890  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPSite
0x7f895  stloc.0
0x7f896  ldloc.0
0x7f897  brtrue.s loc_7F8A4
0x7f899  ldstr    aTarget// "target"
0x7f89e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7f8a3  throw
0x7f8a4  ldarg.0
0x7f8a5  ldarg.2
0x7f8a6  ldarg.s  4
0x7f8a8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7f8ad  starg.s  2
0x7f8af  ldarg.2
0x7f8b0  dup
0x7f8b1  stloc.1
0x7f8b2  brfalse  loc_7FFC3
0x7f8b7  volatile.
0x7f8b9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015ae-1
0x7f8be  brtrue   loc_7FAC3
0x7f8c3  ldc.i4.s 0x27
0x7f8c5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x7f8ca  dup
0x7f8cb  ldstr    aProvisionmigra// "ProvisionMigrationContainers"
0x7f8d0  ldc.i4.0
0x7f8d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f8d6  dup
0x7f8d7  ldstr    aProvisionmigra_0// "ProvisionMigrationQueue"
0x7f8dc  ldc.i4.1
0x7f8dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f8e2  dup
0x7f8e3  ldstr    aJoinhubsite// "JoinHubSite"
0x7f8e8  ldc.i4.2
0x7f8e9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f8ee  dup
0x7f8ef  ldstr    aMakehubsite// "MakeHubSite"
0x7f8f4  ldc.i4.3
0x7f8f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f8fa  dup
0x7f8fb  ldstr    aRemovehubsite// "RemoveHubSite"
0x7f900  ldc.i4.4
0x7f901  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f906  dup
0x7f907  ldstr    aRegisterhubsit// "RegisterHubSite"
0x7f90c  ldc.i4.5
0x7f90d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f912  dup
0x7f913  ldstr    aUnregisterhubs// "UnregisterHubSite"
0x7f918  ldc.i4.6
0x7f919  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f91e  dup
0x7f91f  ldstr    aOnboardtenantf// "OnboardTenantForBringYourOwnKey"
0x7f924  ldc.i4.7
0x7f925  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f92a  dup
0x7f92b  ldstr    aRolltenantbrin// "RollTenantBringYourOwnKey"
0x7f930  ldc.i4.8
0x7f931  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f936  dup
0x7f937  ldstr    aGetbringyourow// "GetBringYourOwnKeyTenantStatus"
0x7f93c  ldc.i4.s 9
0x7f93e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f943  dup
0x7f944  ldstr    aGetbringyourow_0// "GetBringYourOwnKeySiteStatus"
0x7f949  ldc.i4.s 0xA
0x7f94b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f950  dup
0x7f951  ldstr    aRecovertenantf// "RecoverTenantForBringYourOwnKey"
0x7f956  ldc.i4.s 0xB
0x7f958  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f95d  dup
0x7f95e  ldstr    aUpdateclientob// "UpdateClientObjectModelUseRemoteAPIsPer"...
0x7f963  ldc.i4.s 0xC
0x7f965  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f96a  dup
0x7f96b  ldstr    aNeedsupgradeby// "NeedsUpgradeByType"
0x7f970  ldc.i4.s 0xD
0x7f972  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f977  dup
0x7f978  ldstr    aRunhealthcheck// "RunHealthCheck"
0x7f97d  ldc.i4.s 0xE
0x7f97f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f984  dup
0x7f985  ldstr    aCreatepreviews// "CreatePreviewSPSite"
0x7f98a  ldc.i4.s 0xF
0x7f98c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f991  dup
0x7f992  ldstr    aRunupgradesite// "RunUpgradeSiteSession"
0x7f997  ldc.i4.s 0x10
0x7f999  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f99e  dup
0x7f99f  ldstr    aDeletemigratio// "DeleteMigrationJob"
0x7f9a4  ldc.i4.s 0x11
0x7f9a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f9ab  dup
0x7f9ac  ldstr    aGetmigrationst// "GetMigrationStatus"
0x7f9b1  ldc.i4.s 0x12
0x7f9b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f9b8  dup
0x7f9b9  ldstr    aGetmigrationjo// "GetMigrationJobStatus"
0x7f9be  ldc.i4.s 0x13
0x7f9c0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f9c5  dup
0x7f9c6  ldstr    aCreatemigratio// "CreateMigrationJob"
0x7f9cb  ldc.i4.s 0x14
0x7f9cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f9d2  dup
0x7f9d3  ldstr    aCreatemigratio_0// "CreateMigrationJobEncrypted"
0x7f9d8  ldc.i4.s 0x15
0x7f9da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f9df  dup
0x7f9e0  ldstr    aCreatemigratio_1// "CreateMigrationIngestionJob"
0x7f9e5  ldc.i4.s 0x16
0x7f9e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f9ec  dup
0x7f9ed  ldstr    aMultigeocopyjo// "MultiGeoCopyJob"
0x7f9f2  ldc.i4.s 0x17
0x7f9f4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7f9f9  dup
0x7f9fa  ldstr    aCreatecopyjob// "CreateCopyJob"
0x7f9ff  ldc.i4.s 0x18
0x7fa01  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa06  dup
0x7fa07  ldstr    aCreatecopyjobs// "CreateCopyJobs"
0x7fa0c  ldc.i4.s 0x19
0x7fa0e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa13  dup
0x7fa14  ldstr    aGetcopyjobprog// "GetCopyJobProgress"
0x7fa19  ldc.i4.s 0x1A
0x7fa1b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa20  dup
0x7fa21  ldstr    aGetchanges// "GetChanges"
0x7fa26  ldc.i4.s 0x1B
0x7fa28  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa2d  dup
0x7fa2e  ldstr    aGetrecyclebini// "GetRecycleBinItems"
0x7fa33  ldc.i4.s 0x1C
0x7fa35  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa3a  dup
0x7fa3b  ldstr    aOpenweb// "OpenWeb"
0x7fa40  ldc.i4.s 0x1D
0x7fa42  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa47  dup
0x7fa48  ldstr    aOpenwebusingpa// "OpenWebUsingPath"
0x7fa4d  ldc.i4.s 0x1E
0x7fa4f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa54  dup
0x7fa55  ldstr    aOpenwebbyid// "OpenWebById"
0x7fa5a  ldc.i4.s 0x1F
0x7fa5c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa61  dup
0x7fa62  ldstr    aGetwebpath// "GetWebPath"
0x7fa67  ldc.i4.s 0x20
0x7fa69  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa6e  dup
0x7fa6f  ldstr    aExtendupgrader// "ExtendUpgradeReminderDate"
0x7fa74  ldc.i4.s 0x21
0x7fa76  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa7b  dup
0x7fa7c  ldstr    aRestupdate// "RestUpdate"
0x7fa81  ldc.i4.s 0x22
0x7fa83  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa88  dup
0x7fa89  ldstr    aGetwebtemplate// "GetWebTemplates"
0x7fa8e  ldc.i4.s 0x23
0x7fa90  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fa95  dup
0x7fa96  ldstr    aGetcustomlistt// "GetCustomListTemplates"
0x7fa9b  ldc.i4.s 0x24
0x7fa9d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7faa2  dup
0x7faa3  ldstr    aGetcatalog// "GetCatalog"
0x7faa8  ldc.i4.s 0x25
0x7faaa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7faaf  dup
0x7fab0  ldstr    aInvalidate// "Invalidate"
0x7fab5  ldc.i4.s 0x26
0x7fab7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7fabc  volatile.
0x7fabe  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015ae-1
0x7fac3  volatile.
0x7fac5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015ae-1
0x7faca  ldloc.1
0x7facb  ldloca.s 2
0x7facd  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x7fad2  brfalse  loc_7FFC3
0x7fad7  ldloc.2
0x7fad8  switch   loc_7FB7E, loc_7FB99, loc_7FBB4, loc_7FBD0, loc_7FBEB, loc_7FC07, loc_7FC22, loc_7FC3E, loc_7FC59, loc_7FC74, loc_7FC8F, loc_7FCAA, loc_7FCC5, loc_7FCE1, loc_7FD01, loc_7FD1C, loc_7FD38, loc_7FD54, loc_7FD74, loc_7FD8F, loc_7FDAF, loc_7FDCF, loc_7FDEF, loc_7FE0F, loc_7FE2B, loc_7FE46, loc_7FE61, loc_7FE7C, loc_7FE97, loc_7FEB2, loc_7FECD, loc_7FEE8, loc_7FF03, loc_7FF1E, loc_7FF3A, loc_7FF56, loc_7FF71, loc_7FF8C, loc_7FFA7
0x7fb79  br       loc_7FFC3
0x7fb7e  ldarg.s  5
0x7fb80  ldc.i4.0
0x7fb81  stind.i1
0x7fb82  ldarg.0
0x7fb83  ldstr    aProvisionmigra// "ProvisionMigrationContainers"
0x7fb88  ldarg.s  4
0x7fb8a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fb8f  ldloc.0
0x7fb90  ldarg.3
0x7fb91  ldarg.s  4
0x7fb93  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPProvisionedMigrationContainersInfo Microsoft.SharePoint.ServerStub.SPSiteServerStub::ProvisionMigrationContainers_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7fb98  ret
0x7fb99  ldarg.s  5
0x7fb9b  ldc.i4.0
0x7fb9c  stind.i1
0x7fb9d  ldarg.0
0x7fb9e  ldstr    aProvisionmigra_0// "ProvisionMigrationQueue"
0x7fba3  ldarg.s  4
0x7fba5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fbaa  ldloc.0
0x7fbab  ldarg.3
0x7fbac  ldarg.s  4
0x7fbae  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPProvisionedMigrationQueueInfo Microsoft.SharePoint.ServerStub.SPSiteServerStub::ProvisionMigrationQueue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7fbb3  ret
0x7fbb4  ldarg.s  5
0x7fbb6  ldc.i4.1
0x7fbb7  stind.i1
0x7fbb8  ldarg.0
0x7fbb9  ldstr    aJoinhubsite// "JoinHubSite"
0x7fbbe  ldarg.s  4
0x7fbc0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fbc5  ldloc.0
0x7fbc6  ldarg.3
0x7fbc7  ldarg.s  4
0x7fbc9  call     void Microsoft.SharePoint.ServerStub.SPSiteServerStub::JoinHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7fbce  ldnull
0x7fbcf  ret
0x7fbd0  ldarg.s  5
0x7fbd2  ldc.i4.0
0x7fbd3  stind.i1
0x7fbd4  ldarg.0
0x7fbd5  ldstr    aMakehubsite// "MakeHubSite"
0x7fbda  ldarg.s  4
0x7fbdc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fbe1  ldloc.0
0x7fbe2  ldarg.3
0x7fbe3  ldarg.s  4
0x7fbe5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite Microsoft.SharePoint.ServerStub.SPSiteServerStub::MakeHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7fbea  ret
0x7fbeb  ldarg.s  5
0x7fbed  ldc.i4.1
0x7fbee  stind.i1
0x7fbef  ldarg.0
0x7fbf0  ldstr    aRemovehubsite// "RemoveHubSite"
0x7fbf5  ldarg.s  4
0x7fbf7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fbfc  ldloc.0
0x7fbfd  ldarg.3
0x7fbfe  ldarg.s  4
0x7fc00  call     void Microsoft.SharePoint.ServerStub.SPSiteServerStub::RemoveHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7fc05  ldnull
0x7fc06  ret
0x7fc07  ldarg.s  5
0x7fc09  ldc.i4.0
0x7fc0a  stind.i1
0x7fc0b  ldarg.0
0x7fc0c  ldstr    aRegisterhubsit// "RegisterHubSite"
0x7fc11  ldarg.s  4
0x7fc13  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fc18  ldloc.0
0x7fc19  ldarg.3
0x7fc1a  ldarg.s  4
0x7fc1c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite Microsoft.SharePoint.ServerStub.SPSiteServerStub::RegisterHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7fc21  ret
0x7fc22  ldarg.s  5
0x7fc24  ldc.i4.1
0x7fc25  stind.i1
0x7fc26  ldarg.0
0x7fc27  ldstr    aUnregisterhubs// "UnregisterHubSite"
0x7fc2c  ldarg.s  4
0x7fc2e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fc33  ldloc.0
0x7fc34  ldarg.3
0x7fc35  ldarg.s  4
0x7fc37  call     void Microsoft.SharePoint.ServerStub.SPSiteServerStub::UnregisterHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7fc3c  ldnull
0x7fc3d  ret
0x7fc3e  ldarg.s  5
0x7fc40  ldc.i4.0
0x7fc41  stind.i1
0x7fc42  ldarg.0
0x7fc43  ldstr    aOnboardtenantf// "OnboardTenantForBringYourOwnKey"
0x7fc48  ldarg.s  4
0x7fc4a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fc4f  ldloc.0
0x7fc50  ldarg.3
0x7fc51  ldarg.s  4
0x7fc53  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPCustomerKeyStatusInfo Microsoft.SharePoint.ServerStub.SPSiteServerStub::OnboardTenantForBringYourOwnKey_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7fc58  ret
0x7fc59  ldarg.s  5
0x7fc5b  ldc.i4.0
0x7fc5c  stind.i1
0x7fc5d  ldarg.0
0x7fc5e  ldstr    aRolltenantbrin// "RollTenantBringYourOwnKey"
0x7fc63  ldarg.s  4
0x7fc65  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
  ... truncated ...
```
