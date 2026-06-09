# System.Printing.PrintServer::set_PortThreadPriority

- ea: `0x12280`
- end: `0x122b2`
- name: `System.Printing.PrintServer::set_PortThreadPriority`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0xa6f0`
- `0x12280`
- `0x13460`
- `0x14560`
- `0x17110`

## string_xrefs

- `0x1229c`: `PortThreadPriority`

## pseudocode

```c

```

## disassembly

```asm
0x12280  ldarg.0
0x12281  call     instance void System.Printing.PrintServer::VerifyAccess()
0x12286  ldarg.0
0x12287  ldfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.PrintServer::portThreadPriority
0x1228c  ldarg.1
0x1228d  beq.s    loc_122B1
0x1228f  ldarg.0
0x12290  ldarg.1
0x12291  stfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.PrintServer::portThreadPriority
0x12296  ldarg.0
0x12297  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0x1229c  ldstr    aPortthreadprio// "PortThreadPriority"
0x122a1  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x122a6  ldarg.1
0x122a7  box      [mscorlib]System.Threading.ThreadPriority
0x122ac  callvirt instance void System.Printing.IndexedProperties.PrintProperty::set_Value(object objValue)
0x122b1  ret
```
