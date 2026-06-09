# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps

- ea: `0x1000`
- end: `0x103e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps`
- size: `62`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1060`
- `0x1090`
- `0x10d0`
- `0x1100`
- `0x1130`
- `0x1250`
- `0x15c0`
- `0x16f0`
- `0x18d0`

## callees

- `0x1000`

## pseudocode

```c

```

## disassembly

```asm
0x1000  ldarg.0
0x1001  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_definitionPathSteps
0x1006  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x100b  stloc.0
0x100c  br.s     loc_1021
0x100e  ldloca.s 0
0x1010  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x1015  ldarg.1
0x1016  call     bool [mscorlib]System.String::op_Equality(string, string)
0x101b  brfalse.s loc_1021
0x101d  ldc.i4.1
0x101e  stloc.1
0x101f  leave.s  loc_103C
0x1021  ldloca.s 0
0x1023  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x1028  brtrue.s loc_100E
0x102a  leave.s  loc_103A
0x102c  ldloca.s 0
0x102e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x1034  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1039  endfinally
0x103a  ldc.i4.0
0x103b  ret
0x103c  ldloc.1
0x103d  ret
```
