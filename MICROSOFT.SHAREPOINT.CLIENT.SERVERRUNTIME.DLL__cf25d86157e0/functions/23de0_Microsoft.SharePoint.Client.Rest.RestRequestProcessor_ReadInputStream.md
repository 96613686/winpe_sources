# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ReadInputStream

- ea: `0x23de0`
- end: `0x23e12`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ReadInputStream`
- size: `50`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x22a00`
- `0x22c70`
- `0x258f0`
- `0x25bb0`
- `0x25e80`

## callees

- `0x98e0`
- `0xe000`
- `0x23de0`

## string_xrefs

- `0x23df4`: `The input stream has already been read`

## pseudocode

```c

```

## disassembly

```asm
0x23de0  ldarg.0
0x23de1  ldfld    bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_inputStreamAlreadyRead
0x23de6  brfalse.s loc_23E04
0x23de8  ldarg.0
0x23de9  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x23dee  ldc.i4   0x1C50D7
0x23df3  ldc.i4.1
0x23df4  ldstr    aTheInputStream// "The input stream has already been read"
0x23df9  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x23dfe  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x23e03  throw
0x23e04  ldarg.0
0x23e05  ldc.i4.1
0x23e06  stfld    bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_inputStreamAlreadyRead
0x23e0b  ldarg.0
0x23e0c  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_inputStream
0x23e11  ret
```
