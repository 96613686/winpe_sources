# Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::TraceMetadata

- ea: `0x143dc0`
- end: `0x143f47`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::TraceMetadata`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x143ca0`

## callees

- `0x128440`
- `0x128520`
- `0x128540`
- `0x128560`
- `0x128580`
- `0x128590`
- `0x1285a0`
- `0x1285b0`
- `0x1285c0`
- `0x143d80`
- `0x143dc0`
- `0x144140`
- `0x200300`
- `0x200320`

## string_xrefs

- `0x143dd4`: `{0}ReportSnapshot: Time={1}, Language={2}, User={3}, Path={4}`

## pseudocode

```c

```

## disassembly

```asm
0x143dc0  ldarg.0
0x143dc1  brtrue.s loc_143DC4
0x143dc3  ret
0x143dc4  ldarg.0
0x143dc5  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143dca  brfalse  loc_143EA4
0x143dcf  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x143dd4  ldstr    a0Reportsnapsho// "{0}ReportSnapshot: Time={1}, Language={"...
0x143dd9  ldc.i4.5
0x143dda  newarr   [mscorlib]System.Object
0x143ddf  dup
0x143de0  ldc.i4.0
0x143de1  ldarg.1
0x143de2  call     string Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::GetEmptyString(int32 level)
0x143de7  stelem.ref
0x143de8  dup
0x143de9  ldc.i4.1
0x143dea  ldarg.0
0x143deb  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143df0  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::get_ExecutionTime()
0x143df5  box      [mscorlib]System.DateTime
0x143dfa  stelem.ref
0x143dfb  dup
0x143dfc  ldc.i4.2
0x143dfd  ldarg.0
0x143dfe  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143e03  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::get_Language()
0x143e08  stelem.ref
0x143e09  dup
0x143e0a  ldc.i4.3
0x143e0b  ldarg.0
0x143e0c  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143e11  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::get_RequestUserName()
0x143e16  stelem.ref
0x143e17  dup
0x143e18  ldc.i4.4
0x143e19  ldarg.0
0x143e1a  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143e1f  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::get_ReportServerUrl()
0x143e24  ldarg.0
0x143e25  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143e2a  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::get_ReportFolder()
0x143e2f  call     string [mscorlib]System.String::Concat(string, string)
0x143e34  stelem.ref
0x143e35  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x143e3a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x143e3f  ldstr    a0SnapshotFlags// "{0}Snapshot flags: Bookmarks={1}, Docum"...
0x143e44  ldc.i4.5
0x143e45  newarr   [mscorlib]System.Object
0x143e4a  dup
0x143e4b  ldc.i4.0
0x143e4c  ldarg.1
0x143e4d  call     string Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::GetEmptyString(int32 level)
0x143e52  stelem.ref
0x143e53  dup
0x143e54  ldc.i4.1
0x143e55  ldarg.0
0x143e56  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143e5b  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::get_HasBookmarks()
0x143e60  box      [mscorlib]System.Boolean
0x143e65  stelem.ref
0x143e66  dup
0x143e67  ldc.i4.2
0x143e68  ldarg.0
0x143e69  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143e6e  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::get_HasDocumentMap()
0x143e73  box      [mscorlib]System.Boolean
0x143e78  stelem.ref
0x143e79  dup
0x143e7a  ldc.i4.3
0x143e7b  ldarg.0
0x143e7c  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143e81  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::get_HasShowHide()
0x143e86  box      [mscorlib]System.Boolean
0x143e8b  stelem.ref
0x143e8c  dup
0x143e8d  ldc.i4.4
0x143e8e  ldarg.0
0x143e8f  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x143e94  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::get_HasUserSortFilter()
0x143e99  box      [mscorlib]System.Boolean
0x143e9e  stelem.ref
0x143e9f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x143ea4  ldarg.0
0x143ea5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance> Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_DataChunkMap()
0x143eaa  brfalse  loc_143F46
0x143eaf  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x143eb4  ldstr    a0DataChunkMap// "{0}Data chunk map: "
0x143eb9  ldc.i4.1
0x143eba  newarr   [mscorlib]System.Object
0x143ebf  dup
0x143ec0  ldc.i4.0
0x143ec1  ldarg.1
0x143ec2  call     string Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::GetEmptyString(int32 level)
0x143ec7  stelem.ref
0x143ec8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x143ecd  ldarg.0
0x143ece  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance> Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_DataChunkMap()
0x143ed3  stloc.0
0x143ed4  ldc.i4.0
0x143ed5  stloc.1
0x143ed6  ldloc.0
0x143ed7  ldloca.s 1
0x143ed9  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x143ede  ldarg.0
0x143edf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance> Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_DataChunkMap()
0x143ee4  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance>::GetEnumerator()
0x143ee9  box      valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance>
0x143eee  stloc.2
0x143eef  br.s     loc_143F32
0x143ef1  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x143ef6  ldstr    a0DataChunk1// "{0}Data chunk={1}"
0x143efb  ldc.i4.2
0x143efc  newarr   [mscorlib]System.Object
0x143f01  dup
0x143f02  ldc.i4.0
0x143f03  ldarg.1
0x143f04  ldc.i4.1
0x143f05  add
0x143f06  call     string Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::GetEmptyString(int32 level)
0x143f0b  stelem.ref
0x143f0c  dup
0x143f0d  ldc.i4.1
0x143f0e  ldloc.2
0x143f0f  callvirt instance object [mscorlib]System.Collections.IDictionaryEnumerator::get_Key()
0x143f14  castclass [mscorlib]System.String
0x143f19  stelem.ref
0x143f1a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x143f1f  ldloc.2
0x143f20  callvirt instance object [mscorlib]System.Collections.IDictionaryEnumerator::get_Value()
0x143f25  isinst   Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance
0x143f2a  ldarg.1
0x143f2b  ldc.i4.2
0x143f2c  add
0x143f2d  call     void Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::TraceDataSetInstance(class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance instance, int32 level)
0x143f32  ldloc.2
0x143f33  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x143f38  brtrue.s loc_143EF1
0x143f3a  leave.s  loc_143F46
0x143f3c  ldloc.1
0x143f3d  brfalse.s loc_143F45
0x143f3f  ldloc.0
0x143f40  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x143f45  endfinally
0x143f46  ret
```
