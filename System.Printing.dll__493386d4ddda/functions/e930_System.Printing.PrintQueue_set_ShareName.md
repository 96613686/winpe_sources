# System.Printing.PrintQueue::set_ShareName

- ea: `0xe930`
- end: `0xe9e4`
- name: `System.Printing.PrintQueue::set_ShareName`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0xa6f0`
- `0xe930`
- `0xf850`
- `0x110d0`
- `0x14560`
- `0x145c0`
- `0x145f0`
- `0x17110`

## string_xrefs

- `0xe968`: `ShareName`
- `0xe97e`: `ShareName`

## pseudocode

```c

```

## disassembly

```asm
0xe930  ldarg.0
0xe931  call     instance void System.Printing.PrintQueue::VerifyAccess()
0xe936  ldarg.0
0xe937  ldfld    string System.Printing.PrintQueue::shareName
0xe93c  ldarg.1
0xe93d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xe942  brtrue.s loc_E95B
0xe944  ldarg.1
0xe945  brfalse  loc_E9E3
0xe94a  ldarg.1
0xe94b  ldarg.0
0xe94c  ldfld    string System.Printing.PrintQueue::shareName
0xe951  callvirt instance bool [mscorlib]System.String::Equals(string)
0xe956  brtrue   loc_E9E3
0xe95b  ldarg.0
0xe95c  ldarg.1
0xe95d  stfld    string System.Printing.PrintQueue::shareName
0xe962  ldarg.0
0xe963  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0xe968  ldstr    aSharename// "ShareName"
0xe96d  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0xe972  ldarg.1
0xe973  callvirt instance void System.Printing.IndexedProperties.PrintProperty::set_Value(object objValue)
0xe978  ldarg.0
0xe979  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0xe97e  ldstr    aSharename// "ShareName"
0xe983  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0xe988  call     instance bool System.Printing.IndexedProperties.PrintProperty::get_IsInternallyInitialized()
0xe98d  brtrue.s loc_E9E3
0xe98f  ldarg.0
0xe990  ldfld    valuetype System.Printing.PrintQueueAttributes System.Printing.PrintQueue::queueAttributes
0xe995  stloc.0
0xe996  ldarg.0
0xe997  ldfld    string System.Printing.PrintQueue::shareName
0xe99c  ldnull
0xe99d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xe9a2  brfalse.s loc_E9AA
0xe9a4  ldloc.0
0xe9a5  ldc.i4.8
0xe9a6  or
0xe9a7  stloc.0
0xe9a8  br.s     loc_E9AF
0xe9aa  ldloc.0
0xe9ab  ldc.i4.s 0xF7
0xe9ad  and
0xe9ae  stloc.0
0xe9af  ldstr    aAttributes// "Attributes"
0xe9b4  stloc.1
0xe9b5  ldarg.0
0xe9b6  ldloc.1
0xe9b7  callvirt instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintQueue::get_InternalPropertiesCollection(string attributeName)
0xe9bc  ldloc.1
0xe9bd  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0xe9c2  ldloc.0
0xe9c3  box      [mscorlib]System.Int32
0xe9c8  callvirt instance void System.Printing.IndexedProperties.PrintProperty::set_Value(object objValue)
0xe9cd  ldarg.0
0xe9ce  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0xe9d3  ldstr    aQueueattribute// "QueueAttributes"
0xe9d8  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0xe9dd  ldc.i4.1
0xe9de  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsDirty([hasfieldmarshal] bool setDirty)
0xe9e3  ret
```
