# Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetExtensionTypeFromString

- ea: `0x4d20`
- end: `0x4d84`
- name: `Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetExtensionTypeFromString`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x4cc0`

## callees

- `0xa0`
- `0x4d20`

## string_xrefs

- `0x4d69`: `Extension is not registered properly.  Extension of type {0} is not recognized`

## pseudocode

```c

```

## disassembly

```asm
0x4d20  ldc.i4.m1
0x4d21  stloc.0
0x4d22  ldsfld   valuetype StringToSnapInType[] Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::_snapInTypeToStringTable
0x4d27  stloc.2
0x4d28  ldc.i4.0
0x4d29  stloc.3
0x4d2a  br.s     loc_4D57
0x4d2c  ldloc.2
0x4d2d  ldloc.3
0x4d2e  ldelema  StringToSnapInType
0x4d33  ldobj    StringToSnapInType
0x4d38  stloc.1
0x4d39  ldloca.s 1
0x4d3b  ldfld    string StringToSnapInType::Description
0x4d40  ldarg.0
0x4d41  ldc.i4.3
0x4d42  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4d47  brtrue.s loc_4D53
0x4d49  ldloca.s 1
0x4d4b  ldfld    valuetype Microsoft.ManagementConsole.Internal.SnapInType StringToSnapInType::Type
0x4d50  stloc.0
0x4d51  br.s     loc_4D5D
0x4d53  ldloc.3
0x4d54  ldc.i4.1
0x4d55  add
0x4d56  stloc.3
0x4d57  ldloc.3
0x4d58  ldloc.2
0x4d59  ldlen
0x4d5a  conv.i4
0x4d5b  blt.s    loc_4D2C
0x4d5d  ldloc.0
0x4d5e  ldc.i4.m1
0x4d5f  bne.un.s loc_4D82
0x4d61  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x4d66  ldc.i4.2
0x4d67  ldc.i4.s 0xA
0x4d69  ldstr    aExtensionIsNot// "Extension is not registered properly.  "...
0x4d6e  ldc.i4.1
0x4d6f  newarr   [mscorlib]System.Object
0x4d74  stloc.s  4
0x4d76  ldloc.s  4
0x4d78  ldc.i4.0
0x4d79  ldarg.0
0x4d7a  stelem.ref
0x4d7b  ldloc.s  4
0x4d7d  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0x4d82  ldloc.0
0x4d83  ret
```
