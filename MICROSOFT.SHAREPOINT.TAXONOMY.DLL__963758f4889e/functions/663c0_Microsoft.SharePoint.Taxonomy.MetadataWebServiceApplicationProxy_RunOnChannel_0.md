# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::RunOnChannel_0

- ea: `0x663c0`
- end: `0x66484`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::RunOnChannel_0`
- size: `196`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x65810`
- `0x65850`
- `0x658a0`
- `0x658f0`
- `0x65920`
- `0x663a0`
- `0x666a0`
- `0x67380`
- `0x67410`
- `0x67910`
- `0x679b0`
- `0x679f0`
- `0x67fb0`

## callees

- `0x663c0`
- `0x760a0`
- `0x760c0`

## string_xrefs

- `0x663ed`: `Proxy Channel call for Enterprise Metadata Service for operation `
- `0x6641c`: `Metadata backend service request`

## pseudocode

```c

```

## disassembly

```asm
0x663c0  newobj   instance void <>c__DisplayClass4a::.ctor()
0x663c5  stloc.s  4
0x663c7  ldloc.s  4
0x663c9  ldarg.1
0x663ca  stfld    class CodeToRun <>c__DisplayClass4a::codeToRun
0x663cf  ldloc.s  4
0x663d1  ldarg.2
0x663d2  stfld    string <>c__DisplayClass4a::operationName
0x663d7  ldloc.s  4
0x663d9  ldarg.3
0x663da  stfld    float64 <>c__DisplayClass4a::operationTimeoutFactor
0x663df  ldloc.s  4
0x663e1  ldarg.0
0x663e2  stfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy <>c__DisplayClass4a::<>4__this
0x663e7  ldc.i4   0x2710
0x663ec  stloc.0
0x663ed  ldstr    aProxyChannelCa// "Proxy Channel call for Enterprise Metad"...
0x663f2  ldloc.s  4
0x663f4  ldfld    string <>c__DisplayClass4a::operationName
0x663f9  call     string [mscorlib]System.String::Concat(string, string)
0x663fe  ldloc.0
0x663ff  ldc.i4.0
0x66400  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x66405  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x6640a  stloc.1
0x6640b  ldnull
0x6640c  stloc.2
0x6640d  newobj   instance void <>c__DisplayClass4d::.ctor()
0x66412  stloc.3
0x66413  ldloc.3
0x66414  ldloc.s  4
0x66416  stfld    class <>c__DisplayClass4a <>c__DisplayClass4d::CS$<>8__locals4b
0x6641b  ldloc.3
0x6641c  ldstr    aMetadataBacken// "Metadata backend service request"
0x66421  ldc.i4   0x50D41B
0x66426  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x6642b  ldc.i4   0x50D41C
0x66430  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x66435  ldc.i4   0x50D41D
0x6643a  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x6643f  ldc.i4.0
0x66440  ldnull
0x66441  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor::.ctor(string, unsigned int32, unsigned int32, unsigned int32, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPLogType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x66446  stfld    class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor <>c__DisplayClass4d::reliabilityMonitor
0x6644b  ldloc.2
0x6644c  brtrue.s loc_6645B
0x6644e  ldloc.3
0x6644f  ldftn    instance void <>c__DisplayClass4d::<RunOnChannel>b__49()
0x66455  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Security.SecurityContext/CodeToRunElevated::.ctor(object, native int)
0x6645a  stloc.2
0x6645b  ldloc.2
0x6645c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Security.SecurityContext::RunAsProcess(class [Microsoft.Office.Server]Microsoft.Office.Server.Security.SecurityContext/CodeToRunElevated)
0x66461  leave.s  loc_66477
0x66463  ldloc.3
0x66464  ldfld    class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor <>c__DisplayClass4d::reliabilityMonitor
0x66469  brfalse.s loc_66476
0x6646b  ldloc.3
0x6646c  ldfld    class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor <>c__DisplayClass4d::reliabilityMonitor
0x66471  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66476  endfinally
0x66477  leave.s  loc_66483
0x66479  ldloc.1
0x6647a  brfalse.s loc_66482
0x6647c  ldloc.1
0x6647d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66482  endfinally
0x66483  ret
```
