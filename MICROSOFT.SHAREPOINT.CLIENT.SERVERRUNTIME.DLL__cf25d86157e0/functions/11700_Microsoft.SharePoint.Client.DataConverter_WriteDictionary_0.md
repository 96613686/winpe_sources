# Microsoft.SharePoint.Client.DataConverter::WriteDictionary_0

- ea: `0x11700`
- end: `0x1175e`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDictionary_0`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x11ef0`

## callees

- `0x11700`
- `0x11ee0`
- `0x13030`
- `0x13220`
- `0x132d0`
- `0x13410`

## string_xrefs

- `0x11703`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11700  ldarg.0
0x11701  brtrue.s loc_1170E
0x11703  ldstr    aWriter// "writer"
0x11708  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1170d  throw
0x1170e  ldarg.1
0x1170f  brtrue.s loc_11718
0x11711  ldarg.0
0x11712  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x11717  ret
0x11718  ldarg.0
0x11719  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartObjectScope()
0x1171e  ldarg.1
0x1171f  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0x11724  stloc.0
0x11725  br.s     loc_1174F
0x11727  ldloc.0
0x11728  callvirt instance object [mscorlib]System.Collections.IDictionaryEnumerator::get_Key()
0x1172d  isinst   [mscorlib]System.String
0x11732  stloc.1
0x11733  ldloc.1
0x11734  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11739  brtrue.s loc_1174F
0x1173b  ldarg.0
0x1173c  ldloc.1
0x1173d  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x11742  ldarg.0
0x11743  ldloc.0
0x11744  callvirt instance object [mscorlib]System.Collections.IDictionaryEnumerator::get_Value()
0x11749  ldarg.2
0x1174a  call     void Microsoft.SharePoint.Client.DataConverter::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1174f  ldloc.0
0x11750  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11755  brtrue.s loc_11727
0x11757  ldarg.0
0x11758  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1175d  ret
```
