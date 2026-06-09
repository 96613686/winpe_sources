# System.Printing.PrintCommitAttributesException::GetObjectData

- ea: `0x1b970`
- end: `0x1b9af`
- name: `System.Printing.PrintCommitAttributesException::GetObjectData`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1b540`
- `0x1b970`

## string_xrefs

- `0x1b974`: `CommittedAttributes`

## pseudocode

```c

```

## disassembly

```asm
0x1b970  ldarg.1
0x1b971  brfalse.s loc_1B9A6
0x1b973  ldarg.1
0x1b974  ldstr    aCommittedattri// "CommittedAttributes"
0x1b979  ldarg.0
0x1b97a  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::committedAttributes
0x1b97f  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, object)
0x1b984  ldarg.1
0x1b985  ldstr    aFailedattribut// "FailedAttributes"
0x1b98a  ldarg.0
0x1b98b  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::failedAttributes
0x1b990  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, object)
0x1b995  ldarg.1
0x1b996  ldstr    aObjectname// "ObjectName"
0x1b99b  ldarg.0
0x1b99c  ldfld    string System.Printing.PrintCommitAttributesException::printObjectName
0x1b9a1  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, object)
0x1b9a6  ldarg.0
0x1b9a7  ldarg.1
0x1b9a8  ldarg.2
0x1b9a9  call     instance void System.Printing.PrintSystemException::GetObjectData(class [mscorlib]System.Runtime.Serialization.SerializationInfo info, valuetype [mscorlib]System.Runtime.Serialization.StreamingContext context)
0x1b9ae  ret
```
