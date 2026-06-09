# System.Printing.PrintQueue::set_Comment

- ea: `0xea10`
- end: `0xea53`
- name: `System.Printing.PrintQueue::set_Comment`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0xa6f0`
- `0xea10`
- `0x110d0`
- `0x14560`
- `0x17110`

## string_xrefs

- `0xea42`: `Comment`

## pseudocode

```c

```

## disassembly

```asm
0xea10  ldarg.0
0xea11  call     instance void System.Printing.PrintQueue::VerifyAccess()
0xea16  ldarg.0
0xea17  ldfld    string System.Printing.PrintQueue::comment
0xea1c  ldarg.1
0xea1d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xea22  brtrue.s loc_EA35
0xea24  ldarg.1
0xea25  brfalse.s loc_EA52
0xea27  ldarg.1
0xea28  ldarg.0
0xea29  ldfld    string System.Printing.PrintQueue::comment
0xea2e  callvirt instance bool [mscorlib]System.String::Equals(string)
0xea33  brtrue.s loc_EA52
0xea35  ldarg.0
0xea36  ldarg.1
0xea37  stfld    string System.Printing.PrintQueue::comment
0xea3c  ldarg.0
0xea3d  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0xea42  ldstr    aComment// "Comment"
0xea47  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0xea4c  ldarg.1
0xea4d  callvirt instance void System.Printing.IndexedProperties.PrintProperty::set_Value(object objValue)
0xea52  ret
```
