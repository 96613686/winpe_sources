# Microsoft.SharePoint.Client.DataConverter::WriteAsJson

- ea: `0x11e60`
- end: `0x11e7c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteAsJson`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11e60`
- `0x11ee0`

## string_xrefs

- `0x11e63`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11e60  ldarg.0
0x11e61  brtrue.s loc_11E6E
0x11e63  ldstr    aWriter// "writer"
0x11e68  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11e6d  throw
0x11e6e  ldarg.0
0x11e6f  ldarg.1
0x11e70  box      mvar<u1>
0x11e75  ldarg.2
0x11e76  call     void Microsoft.SharePoint.Client.DataConverter::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11e7b  ret
```
