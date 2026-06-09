# System.Printing.PrintServer::set_DefaultPortThreadPriority

- ea: `0x12300`
- end: `0x12332`
- name: `System.Printing.PrintServer::set_DefaultPortThreadPriority`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0xa6f0`
- `0x12300`
- `0x13460`
- `0x14560`
- `0x17110`

## string_xrefs

- `0x1231c`: `DefaultPortThreadPriority`

## pseudocode

```c

```

## disassembly

```asm
0x12300  ldarg.0
0x12301  call     instance void System.Printing.PrintServer::VerifyAccess()
0x12306  ldarg.0
0x12307  ldfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.PrintServer::defaultPortThreadPriority
0x1230c  ldarg.1
0x1230d  beq.s    loc_12331
0x1230f  ldarg.0
0x12310  ldarg.1
0x12311  stfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.PrintServer::defaultPortThreadPriority
0x12316  ldarg.0
0x12317  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0x1231c  ldstr    aDefaultportthr// "DefaultPortThreadPriority"
0x12321  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x12326  ldarg.1
0x12327  box      [mscorlib]System.Threading.ThreadPriority
0x1232c  callvirt instance void System.Printing.IndexedProperties.PrintProperty::set_Value(object objValue)
0x12331  ret
```
