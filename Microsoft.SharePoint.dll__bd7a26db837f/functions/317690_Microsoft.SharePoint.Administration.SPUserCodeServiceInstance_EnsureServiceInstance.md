# Microsoft.SharePoint.Administration.SPUserCodeServiceInstance::EnsureServiceInstance

- ea: `0x317690`
- end: `0x31799e`
- name: `Microsoft.SharePoint.Administration.SPUserCodeServiceInstance::EnsureServiceInstance`
- size: `782`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x29e300`
- `0xa7acc0`

## callees

- `0x1c8480`
- `0x1c8640`
- `0x1c89b0`
- `0x1c8a20`
- `0x2232c0`
- `0x223630`
- `0x2236e0`
- `0x223920`
- `0x223950`
- `0x2eba00`
- `0x316800`
- `0x317670`
- `0x317690`
- `0x317a30`
- `0x7ebbc0`
- `0x888c60`
- `0x93dab0`
- `0x93dae0`
- `0x957530`

## string_xrefs

- `0x3176b8`: `Creating UserCodeServiceInstance.`
- `0x3176df`: `SPUserCodeService object in NULL, throwing.`
- `0x3176e9`: `Can't create user code service instance because there's no user code service in the farm.`
- `0x317700`: `Created UserCodeServiceInstance.`
- `0x317716`: `Ensuring SPUserCodeServiceInstance.`
- `0x317739`: `Ensured SPUserCodeServiceInstance.`
- `0x31774f`: `Provisioning SPUserCodeServiceInstance.`
- `0x31776c`: `Provisioned SPUserCodeServiceInstance.`
- `0x317782`: `Enabling FailureActions for UserCodeService Errors`
- `0x3177a8`: `Enabled FailureActions for UserCodeService Errors.`
- `0x3177db`: `Enabling UserCodeServiceInstance.`
- `0x3177fc`: `Enabled UserCodeServiceInstance.`
- `0x317812`: `Starting UserCodeServiceInstance.`
- `0x31782e`: `Started UserCodeServiceInstance.`
- `0x317844`: `Marking UserCodeServiceInstance as Online.`
- `0x317861`: `Marked UserCodeServiceInstance as Online.`
- `0x31787d`: `UserCodeServiceInstance failed to start with following exception: {0}.`
- `0x3178a4`: `Marking UserCodeServiceInstance as Offline.`
- `0x3178c1`: `Marked UserCodeServiceInstance as Offline.`
- `0x3178dc`: `Enabling firewall rule for UserCodeServiceInstance`
- `0x3178f8`: `Enabled firewall rule for UserCodeServiceInstance`
- `0x31790e`: `Disabling UserCodeServiceInstance.`
- `0x31792e`: `Disabled UserCodeServiceInstance.`
- `0x317944`: `Marking UserCodeServiceInstance as Disabled.`
- `0x317961`: `Marked UserCodeServiceInstance as Disabled.`
- `0x317977`: `Updating UserCodeServiceInstance.`
- `0x317993`: `Updated UserCodeServiceInstance.`

## pseudocode

```c

```

## disassembly

```asm
0x317690  ldc.i4   0x66653434
0x317695  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31769a  ldarg.0
0x31769b  ldstr    aFarm// "farm"
0x3176a0  call     void Microsoft.SharePoint.Utilities.Verify::ArgumentNotNullTag(unsigned int32 tag, class Microsoft.SharePoint.Diagnostics.ULSCat category, object parameterValue, string parameterName)
0x3176a5  ldarg.0
0x3176a6  call     class Microsoft.SharePoint.Administration.SPUserCodeService Microsoft.SharePoint.Administration.SPUserCodeService::GetService(class Microsoft.SharePoint.Administration.SPFarm farm)
0x3176ab  stloc.0
0x3176ac  ldc.i4   0x61787232
0x3176b1  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3176b6  ldc.i4.s 0x32
0x3176b8  ldstr    aCreatingUserco// "Creating UserCodeServiceInstance."
0x3176bd  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3176c2  ldarg.1
0x3176c3  ldloc.0
0x3176c4  newobj   instance void Microsoft.SharePoint.Administration.SPUserCodeServiceInstance::.ctor(class Microsoft.SharePoint.Administration.SPServer server, class Microsoft.SharePoint.Administration.SPUserCodeService service)
0x3176c9  stloc.1
0x3176ca  ldnull
0x3176cb  ldloc.1
0x3176cc  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x3176d1  brfalse.s loc_3176F4
0x3176d3  ldc.i4   0x61787233
0x3176d8  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3176dd  ldc.i4.s 0x32
0x3176df  ldstr    aSpusercodeserv// "SPUserCodeService object in NULL, throw"...
0x3176e4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3176e9  ldstr    aCanTCreateUser// "Can't create user code service instance"...
0x3176ee  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3176f3  throw
0x3176f4  ldc.i4   0x61787234
0x3176f9  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3176fe  ldc.i4.s 0x32
0x317700  ldstr    aCreatedUsercod// "Created UserCodeServiceInstance."
0x317705  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x31770a  ldc.i4   0x61787235
0x31770f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x317714  ldc.i4.s 0x32
0x317716  ldstr    aEnsuringSpuser_0// "Ensuring SPUserCodeServiceInstance."
0x31771b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317720  ldarg.1
0x317721  callvirt instance class Microsoft.SharePoint.Administration.SPServiceInstanceCollection Microsoft.SharePoint.Administration.SPServer::get_ServiceInstances()
0x317726  ldloc.1
0x317727  callvirt instance var<u1> class Microsoft.SharePoint.Administration.SPPersistedChildCollection`1<class Microsoft.SharePoint.Administration.SPServiceInstance>::Ensure(!!T0)
0x31772c  pop
0x31772d  ldc.i4   0x61787236
0x317732  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x317737  ldc.i4.s 0x32
0x317739  ldstr    aEnsuredSpuserc_1// "Ensured SPUserCodeServiceInstance."
0x31773e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317743  ldc.i4   0x61787237
0x317748  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31774d  ldc.i4.s 0x32
0x31774f  ldstr    aProvisioningSp_0// "Provisioning SPUserCodeServiceInstance."
0x317754  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317759  ldloc.1
0x31775a  ldc.i4.0
0x31775b  callvirt instance void Microsoft.SharePoint.Administration.SPWindowsServiceInstance::Provision(bool start)
0x317760  ldc.i4   0x61787238
0x317765  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31776a  ldc.i4.s 0x32
0x31776c  ldstr    aProvisionedSpu// "Provisioned SPUserCodeServiceInstance."
0x317771  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317776  ldc.i4   0x67347A62
0x31777b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x317780  ldc.i4.s 0x32
0x317782  ldstr    aEnablingFailur// "Enabling FailureActions for UserCodeSer"...
0x317787  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x31778c  ldloc.1
0x31778d  callvirt instance class Microsoft.SharePoint.Administration.SPService Microsoft.SharePoint.Administration.SPServiceInstance::get_Service()
0x317792  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x317797  call     void Microsoft.SharePoint.Win32.SPAdvApi32::EnableFailureActionsForServiceErrors(string serviceName)
0x31779c  ldc.i4   0x67347A63
0x3177a1  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3177a6  ldc.i4.s 0x32
0x3177a8  ldstr    aEnabledFailure// "Enabled FailureActions for UserCodeServ"...
0x3177ad  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3177b2  ldarg.2
0x3177b3  ldc.i4.3
0x3177b4  bne.un   loc_3178D0
0x3177b9  ldc.i4   0x78A0D6
0x3177be  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3177c3  ldc.i4.s 0xA
0x3177c5  ldstr    aUnexpectedUsag// "Unexpected usage of SPServerRole.Single"...
0x3177ca  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3177cf  ldc.i4   0x61787239
0x3177d4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3177d9  ldc.i4.s 0x32
0x3177db  ldstr    aEnablingUserco// "Enabling UserCodeServiceInstance."
0x3177e0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3177e5  ldsfld   string Microsoft.SharePoint.Administration.SPConstants::UserCodeServiceName
0x3177ea  ldc.i4.1
0x3177eb  call     void Microsoft.SharePoint.Administration.SPWindowsServiceInstance::Enable(string serviceName, bool autoStart)
0x3177f0  ldc.i4   0x61787330
0x3177f5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3177fa  ldc.i4.s 0x32
0x3177fc  ldstr    aEnabledUsercod// "Enabled UserCodeServiceInstance."
0x317801  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317806  ldc.i4   0x61787331
0x31780b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x317810  ldc.i4.s 0x32
0x317812  ldstr    aStartingUserco// "Starting UserCodeServiceInstance."
0x317817  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x31781c  ldloc.1
0x31781d  callvirt instance void Microsoft.SharePoint.Administration.SPWindowsServiceInstance::Start()
0x317822  ldc.i4   0x61787332
0x317827  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31782c  ldc.i4.s 0x32
0x31782e  ldstr    aStartedUsercod// "Started UserCodeServiceInstance."
0x317833  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317838  ldc.i4   0x61787333
0x31783d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x317842  ldc.i4.s 0x32
0x317844  ldstr    aMarkingUsercod// "Marking UserCodeServiceInstance as Onli"...
0x317849  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x31784e  ldloc.1
0x31784f  ldc.i4.0
0x317850  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::set_Status(valuetype Microsoft.SharePoint.Administration.SPObjectStatus value)
0x317855  ldc.i4   0x61787334
0x31785a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31785f  ldc.i4.s 0x32
0x317861  ldstr    aMarkedUsercode// "Marked UserCodeServiceInstance as Onlin"...
0x317866  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x31786b  leave    loc_31796B
0x317870  stloc.2
0x317871  ldc.i4   0x67337571
0x317876  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31787b  ldc.i4.s 0xF
0x31787d  ldstr    aUsercodeservic_2// "UserCodeServiceInstance failed to start"...
0x317882  ldc.i4.1
0x317883  newarr   [mscorlib]System.Object
0x317888  stloc.3
0x317889  ldloc.3
0x31788a  ldc.i4.0
0x31788b  ldloc.2
0x31788c  callvirt instance string [mscorlib]System.Object::ToString()
0x317891  stelem.ref
0x317892  ldloc.3
0x317893  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x317898  ldc.i4   0x67337572
0x31789d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3178a2  ldc.i4.s 0x32
0x3178a4  ldstr    aMarkingUsercod_0// "Marking UserCodeServiceInstance as Offl"...
0x3178a9  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3178ae  ldloc.1
0x3178af  ldc.i4.2
0x3178b0  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::set_Status(valuetype Microsoft.SharePoint.Administration.SPObjectStatus value)
0x3178b5  ldc.i4   0x67337573
0x3178ba  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3178bf  ldc.i4.s 0x32
0x3178c1  ldstr    aMarkedUsercode_0// "Marked UserCodeServiceInstance as Offli"...
0x3178c6  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3178cb  leave    loc_31796B
0x3178d0  ldc.i4   0x66676434
0x3178d5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3178da  ldc.i4.s 0x32
0x3178dc  ldstr    aEnablingFirewa// "Enabling firewall rule for UserCodeServ"...
0x3178e1  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3178e6  ldloc.1
0x3178e7  callvirt instance void Microsoft.SharePoint.Administration.SPUserCodeServiceInstance::OpenFirewallPort()
0x3178ec  ldc.i4   0x66676435
0x3178f1  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3178f6  ldc.i4.s 0x32
0x3178f8  ldstr    aEnabledFirewal// "Enabled firewall rule for UserCodeServi"...
0x3178fd  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317902  ldc.i4   0x61787335
0x317907  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31790c  ldc.i4.s 0x32
0x31790e  ldstr    aDisablingUserc// "Disabling UserCodeServiceInstance."
0x317913  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317918  ldsfld   string Microsoft.SharePoint.Administration.SPConstants::UserCodeServiceName
0x31791d  call     void Microsoft.SharePoint.Administration.SPWindowsServiceInstance::Disable(string serviceName)
0x317922  ldc.i4   0x61787336
0x317927  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31792c  ldc.i4.s 0x32
0x31792e  ldstr    aDisabledUserco// "Disabled UserCodeServiceInstance."
0x317933  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317938  ldc.i4   0x61787337
0x31793d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x317942  ldc.i4.s 0x32
0x317944  ldstr    aMarkingUsercod_1// "Marking UserCodeServiceInstance as Disa"...
0x317949  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x31794e  ldloc.1
0x31794f  ldc.i4.1
0x317950  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::set_Status(valuetype Microsoft.SharePoint.Administration.SPObjectStatus value)
0x317955  ldc.i4   0x61787338
0x31795a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31795f  ldc.i4.s 0x32
0x317961  ldstr    aMarkedUsercode_1// "Marked UserCodeServiceInstance as Disab"...
0x317966  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x31796b  ldc.i4   0x61787339
0x317970  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x317975  ldc.i4.s 0x32
0x317977  ldstr    aUpdatingUserco_0// "Updating UserCodeServiceInstance."
0x31797c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x317981  ldloc.1
0x317982  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x317987  ldc.i4   0x61787430
0x31798c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x317991  ldc.i4.s 0x32
0x317993  ldstr    aUpdatedUsercod_0// "Updated UserCodeServiceInstance."
0x317998  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x31799d  ret
```
