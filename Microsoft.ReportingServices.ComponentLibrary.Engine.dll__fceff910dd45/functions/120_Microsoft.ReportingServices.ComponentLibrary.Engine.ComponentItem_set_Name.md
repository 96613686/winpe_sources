# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::set_Name

- ea: `0x120`
- end: `0x151`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::set_Name`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x80`

## callees

- `0x120`
- `0xcb0`

## pseudocode

```c

```

## disassembly

```asm
0x120  ldarg.1
0x121  brtrue.s loc_129
0x123  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor()
0x128  throw
0x129  ldarg.1
0x12a  callvirt instance string [mscorlib]System.String::Trim()
0x12f  starg.s  1
0x131  ldarg.1
0x132  ldsfld   string [mscorlib]System.String::Empty
0x137  callvirt instance bool [mscorlib]System.String::Equals(string)
0x13c  brfalse.s loc_149
0x13e  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_EmptyName()
0x143  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x148  throw
0x149  ldarg.0
0x14a  ldarg.1
0x14b  stfld    string Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::m_name
0x150  ret
```
