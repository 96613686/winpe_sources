# Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::.ctor

- ea: `0x1d7d0`
- end: `0x1d801`
- name: `Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::.ctor`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x229a0`

## callees

- `0x1d7b0`
- `0x1d7d0`

## string_xrefs

- `0x1d7d9`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x1d7d0  ldarg.0
0x1d7d1  call     instance void Microsoft.SharePoint.Client.RESTfulODataMessageWriter::.ctor()
0x1d7d6  ldarg.1
0x1d7d7  brtrue.s loc_1D7E4
0x1d7d9  ldstr    aWriter// "writer"
0x1d7de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d7e3  throw
0x1d7e4  ldarg.2
0x1d7e5  brtrue.s loc_1D7F2
0x1d7e7  ldstr    aProxycontext// "proxyContext"
0x1d7ec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d7f1  throw
0x1d7f2  ldarg.0
0x1d7f3  ldarg.1
0x1d7f4  stfld    class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::m_writer
0x1d7f9  ldarg.0
0x1d7fa  ldarg.2
0x1d7fb  stfld    class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::m_proxyContext
0x1d800  ret
```
