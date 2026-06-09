# Microsoft.SharePoint.ServerStub.SPSiteServerStub::InvokeMethod_0

- ea: `0x834e0`
- end: `0x83c31`
- name: `Microsoft.SharePoint.ServerStub.SPSiteServerStub::InvokeMethod_0`
- size: `1873`
- prototype: ``
- caller_count: `0`
- callee_count: `40`
- tags: `installer_update, broker_com_uri`

## callees

- `0x82ee0`
- `0x82ef0`
- `0x82f00`
- `0x82f20`
- `0x82f30`
- `0x82f40`
- `0x82f50`
- `0x82f60`
- `0x82f80`
- `0x82fb0`
- `0x82fc0`
- `0x82fd0`
- `0x82ff0`
- `0x83010`
- `0x83040`
- `0x83080`
- `0x830b0`
- `0x830f0`
- `0x83110`
- `0x83120`
- `0x83140`
- `0x83190`
- `0x831f0`
- `0x83250`
- `0x83290`
- `0x832d0`
- `0x83310`
- `0x83330`
- `0x83350`
- `0x833b0`
- `0x833d0`
- `0x833f0`
- `0x83410`
- `0x83440`
- `0x83450`
- `0x83460`
- `0x83490`
- `0x834b0`
- `0x834d0`
- `0x834e0`

## string_xrefs

- `0x836dc`: `RestUpdate`
- `0x83b9f`: `RestUpdate`
- `0x8355b`: `RemoveHubSite`
- `0x83850`: `RemoveHubSite`
- `0x835be`: `UpdateClientObjectModelUseRemoteAPIsPermissionSetting`
- `0x8392a`: `UpdateClientObjectModelUseRemoteAPIsPermissionSetting`
- `0x835e5`: `CreatePreviewSPSite`
- `0x83981`: `CreatePreviewSPSite`
- `0x835ff`: `DeleteMigrationJob`
- `0x839b9`: `DeleteMigrationJob`
- `0x83626`: `CreateMigrationJob`
- `0x83a14`: `CreateMigrationJob`
- `0x83633`: `CreateMigrationJobEncrypted`
- `0x83a34`: `CreateMigrationJobEncrypted`
- `0x83640`: `CreateMigrationIngestionJob`
- `0x83a54`: `CreateMigrationIngestionJob`
- `0x8364d`: `MultiGeoCopyJob`
- `0x83a74`: `MultiGeoCopyJob`
- `0x8365a`: `CreateCopyJob`
- `0x83a90`: `CreateCopyJob`
- `0x83667`: `CreateCopyJobs`
- `0x83aab`: `CreateCopyJobs`
- `0x83674`: `GetCopyJobProgress`
- `0x83ac6`: `GetCopyJobProgress`
- `0x8369b`: `OpenWeb`
- `0x83b17`: `OpenWeb`
- `0x836a8`: `OpenWebUsingPath`
- `0x83b32`: `OpenWebUsingPath`
- `0x836b5`: `OpenWebById`
- `0x83b4d`: `OpenWebById`
- `0x836c2`: `GetWebPath`
- `0x83b68`: `GetWebPath`
- `0x836e9`: `GetWebTemplates`
- `0x83bbb`: `GetWebTemplates`
- `0x836f6`: `GetCustomListTemplates`
- `0x83bd6`: `GetCustomListTemplates`

## pseudocode

```c

```

## disassembly

```asm
0x834e0  ldarg.s  4
0x834e2  brtrue.s loc_834EF
0x834e4  ldstr    aProxycontext// "proxyContext"
0x834e9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x834ee  throw
0x834ef  ldarg.1
0x834f0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPSite
0x834f5  stloc.0
0x834f6  ldloc.0
0x834f7  brtrue.s loc_83504
0x834f9  ldstr    aTarget// "target"
0x834fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x83503  throw
0x83504  ldarg.0
0x83505  ldarg.2
0x83506  ldarg.s  4
0x83508  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8350d  starg.s  2
0x8350f  ldarg.2
0x83510  dup
0x83511  stloc.1
0x83512  brfalse  loc_83C23
0x83517  volatile.
0x83519  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015e2-1
0x8351e  brtrue   loc_83723
0x83523  ldc.i4.s 0x27
0x83525  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x8352a  dup
0x8352b  ldstr    aProvisionmigra// "ProvisionMigrationContainers"
0x83530  ldc.i4.0
0x83531  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83536  dup
0x83537  ldstr    aProvisionmigra_0// "ProvisionMigrationQueue"
0x8353c  ldc.i4.1
0x8353d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83542  dup
0x83543  ldstr    aJoinhubsite// "JoinHubSite"
0x83548  ldc.i4.2
0x83549  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8354e  dup
0x8354f  ldstr    aMakehubsite// "MakeHubSite"
0x83554  ldc.i4.3
0x83555  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8355a  dup
0x8355b  ldstr    aRemovehubsite// "RemoveHubSite"
0x83560  ldc.i4.4
0x83561  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83566  dup
0x83567  ldstr    aRegisterhubsit// "RegisterHubSite"
0x8356c  ldc.i4.5
0x8356d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83572  dup
0x83573  ldstr    aUnregisterhubs// "UnregisterHubSite"
0x83578  ldc.i4.6
0x83579  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8357e  dup
0x8357f  ldstr    aOnboardtenantf// "OnboardTenantForBringYourOwnKey"
0x83584  ldc.i4.7
0x83585  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8358a  dup
0x8358b  ldstr    aRolltenantbrin// "RollTenantBringYourOwnKey"
0x83590  ldc.i4.8
0x83591  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83596  dup
0x83597  ldstr    aGetbringyourow// "GetBringYourOwnKeyTenantStatus"
0x8359c  ldc.i4.s 9
0x8359e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x835a3  dup
0x835a4  ldstr    aGetbringyourow_0// "GetBringYourOwnKeySiteStatus"
0x835a9  ldc.i4.s 0xA
0x835ab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x835b0  dup
0x835b1  ldstr    aRecovertenantf// "RecoverTenantForBringYourOwnKey"
0x835b6  ldc.i4.s 0xB
0x835b8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x835bd  dup
0x835be  ldstr    aUpdateclientob// "UpdateClientObjectModelUseRemoteAPIsPer"...
0x835c3  ldc.i4.s 0xC
0x835c5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x835ca  dup
0x835cb  ldstr    aNeedsupgradeby// "NeedsUpgradeByType"
0x835d0  ldc.i4.s 0xD
0x835d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x835d7  dup
0x835d8  ldstr    aRunhealthcheck// "RunHealthCheck"
0x835dd  ldc.i4.s 0xE
0x835df  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x835e4  dup
0x835e5  ldstr    aCreatepreviews// "CreatePreviewSPSite"
0x835ea  ldc.i4.s 0xF
0x835ec  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x835f1  dup
0x835f2  ldstr    aRunupgradesite// "RunUpgradeSiteSession"
0x835f7  ldc.i4.s 0x10
0x835f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x835fe  dup
0x835ff  ldstr    aDeletemigratio// "DeleteMigrationJob"
0x83604  ldc.i4.s 0x11
0x83606  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8360b  dup
0x8360c  ldstr    aGetmigrationst// "GetMigrationStatus"
0x83611  ldc.i4.s 0x12
0x83613  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83618  dup
0x83619  ldstr    aGetmigrationjo// "GetMigrationJobStatus"
0x8361e  ldc.i4.s 0x13
0x83620  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83625  dup
0x83626  ldstr    aCreatemigratio// "CreateMigrationJob"
0x8362b  ldc.i4.s 0x14
0x8362d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83632  dup
0x83633  ldstr    aCreatemigratio_0// "CreateMigrationJobEncrypted"
0x83638  ldc.i4.s 0x15
0x8363a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8363f  dup
0x83640  ldstr    aCreatemigratio_1// "CreateMigrationIngestionJob"
0x83645  ldc.i4.s 0x16
0x83647  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8364c  dup
0x8364d  ldstr    aMultigeocopyjo// "MultiGeoCopyJob"
0x83652  ldc.i4.s 0x17
0x83654  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83659  dup
0x8365a  ldstr    aCreatecopyjob// "CreateCopyJob"
0x8365f  ldc.i4.s 0x18
0x83661  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83666  dup
0x83667  ldstr    aCreatecopyjobs// "CreateCopyJobs"
0x8366c  ldc.i4.s 0x19
0x8366e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83673  dup
0x83674  ldstr    aGetcopyjobprog// "GetCopyJobProgress"
0x83679  ldc.i4.s 0x1A
0x8367b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83680  dup
0x83681  ldstr    aGetchanges// "GetChanges"
0x83686  ldc.i4.s 0x1B
0x83688  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8368d  dup
0x8368e  ldstr    aGetrecyclebini// "GetRecycleBinItems"
0x83693  ldc.i4.s 0x1C
0x83695  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8369a  dup
0x8369b  ldstr    aOpenweb// "OpenWeb"
0x836a0  ldc.i4.s 0x1D
0x836a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x836a7  dup
0x836a8  ldstr    aOpenwebusingpa// "OpenWebUsingPath"
0x836ad  ldc.i4.s 0x1E
0x836af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x836b4  dup
0x836b5  ldstr    aOpenwebbyid// "OpenWebById"
0x836ba  ldc.i4.s 0x1F
0x836bc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x836c1  dup
0x836c2  ldstr    aGetwebpath// "GetWebPath"
0x836c7  ldc.i4.s 0x20
0x836c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x836ce  dup
0x836cf  ldstr    aExtendupgrader// "ExtendUpgradeReminderDate"
0x836d4  ldc.i4.s 0x21
0x836d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x836db  dup
0x836dc  ldstr    aRestupdate// "RestUpdate"
0x836e1  ldc.i4.s 0x22
0x836e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x836e8  dup
0x836e9  ldstr    aGetwebtemplate// "GetWebTemplates"
0x836ee  ldc.i4.s 0x23
0x836f0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x836f5  dup
0x836f6  ldstr    aGetcustomlistt// "GetCustomListTemplates"
0x836fb  ldc.i4.s 0x24
0x836fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83702  dup
0x83703  ldstr    aGetcatalog// "GetCatalog"
0x83708  ldc.i4.s 0x25
0x8370a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8370f  dup
0x83710  ldstr    aInvalidate// "Invalidate"
0x83715  ldc.i4.s 0x26
0x83717  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8371c  volatile.
0x8371e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015e2-1
0x83723  volatile.
0x83725  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015e2-1
0x8372a  ldloc.1
0x8372b  ldloca.s 2
0x8372d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x83732  brfalse  loc_83C23
0x83737  ldloc.2
0x83738  switch   loc_837DE, loc_837F9, loc_83814, loc_83830, loc_8384B, loc_83867, loc_83882, loc_8389E, loc_838B9, loc_838D4, loc_838EF, loc_8390A, loc_83925, loc_83941, loc_83961, loc_8397C, loc_83998, loc_839B4, loc_839D4, loc_839EF, loc_83A0F, loc_83A2F, loc_83A4F, loc_83A6F, loc_83A8B, loc_83AA6, loc_83AC1, loc_83ADC, loc_83AF7, loc_83B12, loc_83B2D, loc_83B48, loc_83B63, loc_83B7E, loc_83B9A, loc_83BB6, loc_83BD1, loc_83BEC, loc_83C07
0x837d9  br       loc_83C23
0x837de  ldarg.s  5
0x837e0  ldc.i4.0
0x837e1  stind.i1
0x837e2  ldarg.0
0x837e3  ldstr    aProvisionmigra// "ProvisionMigrationContainers"
0x837e8  ldarg.s  4
0x837ea  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x837ef  ldloc.0
0x837f0  ldarg.3
0x837f1  ldarg.s  4
0x837f3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPProvisionedMigrationContainersInfo Microsoft.SharePoint.ServerStub.SPSiteServerStub::ProvisionMigrationContainers_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x837f8  ret
0x837f9  ldarg.s  5
0x837fb  ldc.i4.0
0x837fc  stind.i1
0x837fd  ldarg.0
0x837fe  ldstr    aProvisionmigra_0// "ProvisionMigrationQueue"
0x83803  ldarg.s  4
0x83805  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8380a  ldloc.0
0x8380b  ldarg.3
0x8380c  ldarg.s  4
0x8380e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPProvisionedMigrationQueueInfo Microsoft.SharePoint.ServerStub.SPSiteServerStub::ProvisionMigrationQueue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x83813  ret
0x83814  ldarg.s  5
0x83816  ldc.i4.1
0x83817  stind.i1
0x83818  ldarg.0
0x83819  ldstr    aJoinhubsite// "JoinHubSite"
0x8381e  ldarg.s  4
0x83820  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83825  ldloc.0
0x83826  ldarg.3
0x83827  ldarg.s  4
0x83829  call     void Microsoft.SharePoint.ServerStub.SPSiteServerStub::JoinHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8382e  ldnull
0x8382f  ret
0x83830  ldarg.s  5
0x83832  ldc.i4.0
0x83833  stind.i1
0x83834  ldarg.0
0x83835  ldstr    aMakehubsite// "MakeHubSite"
0x8383a  ldarg.s  4
0x8383c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83841  ldloc.0
0x83842  ldarg.3
0x83843  ldarg.s  4
0x83845  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite Microsoft.SharePoint.ServerStub.SPSiteServerStub::MakeHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8384a  ret
0x8384b  ldarg.s  5
0x8384d  ldc.i4.1
0x8384e  stind.i1
0x8384f  ldarg.0
0x83850  ldstr    aRemovehubsite// "RemoveHubSite"
0x83855  ldarg.s  4
0x83857  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8385c  ldloc.0
0x8385d  ldarg.3
0x8385e  ldarg.s  4
0x83860  call     void Microsoft.SharePoint.ServerStub.SPSiteServerStub::RemoveHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x83865  ldnull
0x83866  ret
0x83867  ldarg.s  5
0x83869  ldc.i4.0
0x8386a  stind.i1
0x8386b  ldarg.0
0x8386c  ldstr    aRegisterhubsit// "RegisterHubSite"
0x83871  ldarg.s  4
0x83873  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83878  ldloc.0
0x83879  ldarg.3
0x8387a  ldarg.s  4
0x8387c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite Microsoft.SharePoint.ServerStub.SPSiteServerStub::RegisterHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x83881  ret
0x83882  ldarg.s  5
0x83884  ldc.i4.1
0x83885  stind.i1
0x83886  ldarg.0
0x83887  ldstr    aUnregisterhubs// "UnregisterHubSite"
0x8388c  ldarg.s  4
0x8388e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83893  ldloc.0
0x83894  ldarg.3
0x83895  ldarg.s  4
0x83897  call     void Microsoft.SharePoint.ServerStub.SPSiteServerStub::UnregisterHubSite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8389c  ldnull
0x8389d  ret
0x8389e  ldarg.s  5
0x838a0  ldc.i4.0
0x838a1  stind.i1
0x838a2  ldarg.0
0x838a3  ldstr    aOnboardtenantf// "OnboardTenantForBringYourOwnKey"
0x838a8  ldarg.s  4
0x838aa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x838af  ldloc.0
0x838b0  ldarg.3
0x838b1  ldarg.s  4
0x838b3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPCustomerKeyStatusInfo Microsoft.SharePoint.ServerStub.SPSiteServerStub::OnboardTenantForBringYourOwnKey_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x838b8  ret
0x838b9  ldarg.s  5
0x838bb  ldc.i4.0
0x838bc  stind.i1
0x838bd  ldarg.0
0x838be  ldstr    aRolltenantbrin// "RollTenantBringYourOwnKey"
0x838c3  ldarg.s  4
0x838c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
  ... truncated ...
```
