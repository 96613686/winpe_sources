# System.Printing.PrintServer::set_DefaultSpoolDirectory

- ea: `0x121f0`
- end: `0x12233`
- name: `System.Printing.PrintServer::set_DefaultSpoolDirectory`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0xa6f0`
- `0x121f0`
- `0x13460`
- `0x14560`
- `0x17110`

## string_xrefs

- `0x12222`: `DefaultSpoolDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x121f0  ldarg.0
0x121f1  call     instance void System.Printing.PrintServer::VerifyAccess()
0x121f6  ldarg.0
0x121f7  ldfld    string System.Printing.PrintServer::defaultSpoolDirectory
0x121fc  ldarg.1
0x121fd  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x12202  brtrue.s loc_12215
0x12204  ldarg.1
0x12205  brfalse.s loc_12232
0x12207  ldarg.1
0x12208  ldarg.0
0x12209  ldfld    string System.Printing.PrintServer::defaultSpoolDirectory
0x1220e  callvirt instance bool [mscorlib]System.String::Equals(string)
0x12213  brtrue.s loc_12232
0x12215  ldarg.0
0x12216  ldarg.1
0x12217  stfld    string System.Printing.PrintServer::defaultSpoolDirectory
0x1221c  ldarg.0
0x1221d  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0x12222  ldstr    aDefaultspooldi// "DefaultSpoolDirectory"
0x12227  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x1222c  ldarg.1
0x1222d  callvirt instance void System.Printing.IndexedProperties.PrintProperty::set_Value(object objValue)
0x12232  ret
```
