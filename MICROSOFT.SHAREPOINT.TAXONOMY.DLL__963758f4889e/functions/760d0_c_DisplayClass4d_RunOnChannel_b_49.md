# <>c__DisplayClass4d::<RunOnChannel>b__49

- ea: `0x760d0`
- end: `0x762fe`
- name: `<>c__DisplayClass4d::<RunOnChannel>b__49`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x66120`
- `0x661d0`
- `0x66490`
- `0x66a10`
- `0x760d0`

## string_xrefs

- `0x7617e`: `Opened metadata service channel at '{0}'.`
- `0x761d5`: `Success at first attempt.`
- `0x761ed`: `Succeeded after {0} attempts`
- `0x76273`: `Giving up because there were too many retries; attemptCount={0}, totalMs={1} error={2}`
- `0x762b7`: `Retried reusing a cached channel 10 times for operation: `

## pseudocode

```c

```

## disassembly

```asm
0x760d0  ldnull
0x760d1  stloc.0
0x760d2  ldc.i4.0
0x760d3  stloc.1
0x760d4  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x760d9  stloc.2
0x760da  ldloc.2
0x760db  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x760e0  ldloc.1
0x760e1  ldc.i4.1
0x760e2  add.ovf
0x760e3  stloc.1
0x760e4  ldarg.0
0x760e5  ldfld    class <>c__DisplayClass4a <>c__DisplayClass4d::CS$<>8__locals4b
0x760ea  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy <>c__DisplayClass4a::<>4__this
0x760ef  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancer Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::loadBalancer
0x760f4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancerContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancer::BeginOperation()
0x760f9  stloc.0
0x760fa  ldc.i4.0
0x760fb  stloc.3
0x760fc  ldarg.0
0x760fd  ldfld    class <>c__DisplayClass4a <>c__DisplayClass4d::CS$<>8__locals4b
0x76102  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy <>c__DisplayClass4a::<>4__this
0x76107  ldloc.0
0x76108  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancerContext::get_EndpointAddress()
0x7610d  ldloca.s 3
0x7610f  call     instance class Microsoft.SharePoint.Taxonomy.IMetadataWebServiceApplication Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetChannel(class [System]System.Uri address, [out] bool& cachedChannel)
0x76114  castclass [System.ServiceModel]System.ServiceModel.Channels.IChannel
0x76119  stloc.s  4
0x7611b  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::defaultOperationTimeout
0x76120  stloc.s  5
0x76122  ldloc.s  4
0x76124  brfalse.s loc_76172
0x76126  ldarg.0
0x76127  ldfld    class <>c__DisplayClass4a <>c__DisplayClass4d::CS$<>8__locals4b
0x7612c  ldfld    float64 <>c__DisplayClass4a::operationTimeoutFactor
0x76131  ldc.r8   1.0
0x7613a  beq.s    loc_76164
0x7613c  ldloca.s 5
0x7613e  ldsflda  valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::defaultOperationTimeout
0x76143  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x76148  conv.r8
0x76149  ldarg.0
0x7614a  ldfld    class <>c__DisplayClass4a <>c__DisplayClass4d::CS$<>8__locals4b
0x7614f  ldfld    float64 <>c__DisplayClass4a::operationTimeoutFactor
0x76154  mul
0x76155  call     float64 [mscorlib]System.Math::Ceiling(float64)
0x7615a  call     int64 [mscorlib]System.Convert::ToInt64(float64)
0x7615f  call     instance void [mscorlib]System.TimeSpan::.ctor(int64)
0x76164  ldloc.s  4
0x76166  castclass [System.ServiceModel]System.ServiceModel.IContextChannel
0x7616b  ldloc.s  5
0x7616d  callvirt instance void [System.ServiceModel]System.ServiceModel.IContextChannel::set_OperationTimeout(valuetype [mscorlib]System.TimeSpan)
0x76172  ldc.i4   0x62386F35
0x76177  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x7617c  ldc.i4.s 0x64
0x7617e  ldstr    aOpenedMetadata// "Opened metadata service channel at '{0}"...
0x76183  ldc.i4.1
0x76184  newarr   [mscorlib]System.Object
0x76189  stloc.s  0xA
0x7618b  ldloc.s  0xA
0x7618d  ldc.i4.0
0x7618e  ldloc.0
0x7618f  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancerContext::get_EndpointAddress()
0x76194  stelem.ref
0x76195  ldloc.s  0xA
0x76197  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x7619c  ldc.i4.0
0x7619d  stloc.s  6
0x7619f  ldarg.0
0x761a0  ldfld    class <>c__DisplayClass4a <>c__DisplayClass4d::CS$<>8__locals4b
0x761a5  ldfld    class CodeToRun <>c__DisplayClass4a::codeToRun
0x761aa  ldloc.s  4
0x761ac  castclass Microsoft.SharePoint.Taxonomy.IMetadataWebServiceApplication
0x761b1  callvirt instance void CodeToRun::Invoke(class Microsoft.SharePoint.Taxonomy.IMetadataWebServiceApplication application)
0x761b6  ldc.i4.1
0x761b7  stloc.s  6
0x761b9  ldarg.0
0x761ba  ldfld    class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor <>c__DisplayClass4d::reliabilityMonitor
0x761bf  ldnull
0x761c0  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::Success(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x761c5  ldloc.1
0x761c6  ldc.i4.1
0x761c7  bne.un.s loc_761E1
0x761c9  ldc.i4   0x58434D
0x761ce  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x761d3  ldc.i4.s 0x32
0x761d5  ldstr    aSuccessAtFirst// "Success at first attempt."
0x761da  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x761df  br.s     loc_7620B
0x761e1  ldc.i4   0x58434E
0x761e6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x761eb  ldc.i4.s 0x32
0x761ed  ldstr    aSucceededAfter// "Succeeded after {0} attempts"
0x761f2  ldc.i4.1
0x761f3  newarr   [mscorlib]System.Object
0x761f8  stloc.s  0xB
0x761fa  ldloc.s  0xB
0x761fc  ldc.i4.0
0x761fd  ldloc.1
0x761fe  box      [mscorlib]System.Int32
0x76203  stelem.ref
0x76204  ldloc.s  0xB
0x76206  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x7620b  ldarg.0
0x7620c  ldfld    class <>c__DisplayClass4a <>c__DisplayClass4d::CS$<>8__locals4b
0x76211  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy <>c__DisplayClass4a::<>4__this
0x76216  ldloc.s  4
0x76218  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::PutChannel(class [System.ServiceModel]System.ServiceModel.Channels.IChannel channel)
0x7621d  ldnull
0x7621e  stloc.s  4
0x76220  leave    loc_762FD
0x76225  stloc.s  7
0x76227  ldloc.0
0x76228  brfalse.s loc_76234
0x7622a  ldloc.3
0x7622b  brtrue.s loc_76234
0x7622d  ldloc.0
0x7622e  ldc.i4.1
0x7622f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancerContext::set_Status(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancerStatus)
0x76234  ldloc.3
0x76235  brfalse.s loc_7623E
0x76237  ldloc.s  6
0x76239  ldc.i4.0
0x7623a  ceq
0x7623c  br.s     loc_7623F
0x7623e  ldc.i4.0
0x7623f  stloc.s  8
0x76241  ldloc.s  7
0x76243  ldarg.0
0x76244  ldfld    class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor <>c__DisplayClass4d::reliabilityMonitor
0x76249  ldloc.s  8
0x7624b  call     void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::HandleExceptionForRunOnChannel(class [mscorlib]System.Exception e, class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor reliabilityMonitor, bool retryAllowed)
0x76250  ldloc.2
0x76251  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x76256  stloc.s  9
0x76258  ldloc.1
0x76259  ldc.i4.s 0xA
0x7625b  bge.s    loc_76267
0x7625d  ldloc.s  9
0x7625f  ldc.i4   0x3A98
0x76264  conv.i8
0x76265  ble.s    loc_762D4
0x76267  ldc.i4   0x5D4706
0x7626c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x76271  ldc.i4.s 0x32
0x76273  ldstr    aGivingUpBecaus// "Giving up because there were too many r"...
0x76278  ldc.i4.3
0x76279  newarr   [mscorlib]System.Object
0x7627e  stloc.s  0xC
0x76280  ldloc.s  0xC
0x76282  ldc.i4.0
0x76283  ldloc.1
0x76284  box      [mscorlib]System.Int32
0x76289  stelem.ref
0x7628a  ldloc.s  0xC
0x7628c  ldc.i4.1
0x7628d  ldloc.s  9
0x7628f  box      [mscorlib]System.Int64
0x76294  stelem.ref
0x76295  ldloc.s  0xC
0x76297  ldc.i4.2
0x76298  ldloc.s  7
0x7629a  callvirt instance string [mscorlib]System.Object::ToString()
0x7629f  stelem.ref
0x762a0  ldloc.s  0xC
0x762a2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x762a7  ldarg.0
0x762a8  ldfld    class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor <>c__DisplayClass4d::reliabilityMonitor
0x762ad  ldc.i4   0x5C3152
0x762b2  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x762b7  ldstr    aRetriedReusing// "Retried reusing a cached channel 10 tim"...
0x762bc  ldarg.0
0x762bd  ldfld    class <>c__DisplayClass4a <>c__DisplayClass4d::CS$<>8__locals4b
0x762c2  ldfld    string <>c__DisplayClass4a::operationName
0x762c7  call     string [mscorlib]System.String::Concat(string, string)
0x762cc  ldnull
0x762cd  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x762d2  rethrow
0x762d4  leave.s  loc_762D6
0x762d6  leave.s  loc_762EE
0x762d8  ldloc.s  4
0x762da  brfalse.s loc_762ED
0x762dc  ldloc.s  4
0x762de  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.ICommunicationObject::get_State()
0x762e3  ldc.i4.4
0x762e4  beq.s    loc_762ED
0x762e6  ldloc.s  4
0x762e8  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Abort()
0x762ed  endfinally
0x762ee  leave    loc_760E0
0x762f3  ldloc.0
0x762f4  brfalse.s loc_762FC
0x762f6  ldloc.0
0x762f7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancerContext::EndOperation()
0x762fc  endfinally
0x762fd  ret
```
