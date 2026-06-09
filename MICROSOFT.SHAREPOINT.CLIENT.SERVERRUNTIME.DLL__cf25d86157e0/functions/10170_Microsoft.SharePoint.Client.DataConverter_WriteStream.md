# Microsoft.SharePoint.Client.DataConverter::WriteStream

- ea: `0x10170`
- end: `0x101a6`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteStream`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x101c0`

## callees

- `0x10170`
- `0x13410`
- `0x13850`
- `0x152b0`

## string_xrefs

- `0x10173`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10170  ldarg.0
0x10171  brtrue.s loc_1017E
0x10173  ldstr    aWriter// "writer"
0x10178  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1017d  throw
0x1017e  ldarg.2
0x1017f  brtrue.s loc_1018C
0x10181  ldstr    aProxycontext// "proxyContext"
0x10186  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1018b  throw
0x1018c  ldarg.1
0x1018d  brtrue.s loc_10196
0x1018f  ldarg.0
0x10190  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10195  ret
0x10196  ldarg.2
0x10197  ldarg.1
0x10198  callvirt instance string Microsoft.SharePoint.Client.ProxyContext::AddOutputAttachmentStream(class [mscorlib]System.IO.Stream stream)
0x1019d  stloc.0
0x1019e  ldarg.0
0x1019f  ldloc.0
0x101a0  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteAttachmentStreamLink(string streamId)
0x101a5  ret
```
