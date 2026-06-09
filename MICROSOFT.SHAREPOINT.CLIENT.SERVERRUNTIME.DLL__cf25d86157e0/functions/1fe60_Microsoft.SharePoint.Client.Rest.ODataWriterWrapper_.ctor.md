# Microsoft.SharePoint.Client.Rest.ODataWriterWrapper::.ctor

- ea: `0x1fe60`
- end: `0x1fe91`
- name: `Microsoft.SharePoint.Client.Rest.ODataWriterWrapper::.ctor`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1f3a0`

## callees

- `0x1fe40`
- `0x1fe60`

## string_xrefs

- `0x1fe69`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x1fe60  ldarg.0
0x1fe61  call     instance void Microsoft.SharePoint.Client.RESTfulODataWriter::.ctor()
0x1fe66  ldarg.1
0x1fe67  brtrue.s loc_1FE74
0x1fe69  ldstr    aWriter// "writer"
0x1fe6e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fe73  throw
0x1fe74  ldarg.2
0x1fe75  brtrue.s loc_1FE82
0x1fe77  ldstr    aProxycontext// "proxyContext"
0x1fe7c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fe81  throw
0x1fe82  ldarg.0
0x1fe83  ldarg.1
0x1fe84  stfld    class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter Microsoft.SharePoint.Client.Rest.ODataWriterWrapper::m_writer
0x1fe89  ldarg.0
0x1fe8a  ldarg.2
0x1fe8b  stfld    class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.Rest.ODataWriterWrapper::m_proxyContext
0x1fe90  ret
```
