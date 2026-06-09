# Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::FuncToUri

- ea: `0x1dd20`
- end: `0x1dd5c`
- name: `Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::FuncToUri`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12440`
- `0x16f10`
- `0x1dd20`

## string_xrefs

- `0x1dd32`: `CannotDeserializeData`

## pseudocode

```c

```

## disassembly

```asm
0x1dd20  ldarg.0
0x1dd21  isinst   [mscorlib]System.String
0x1dd26  stloc.0
0x1dd27  ldloc.0
0x1dd28  brfalse.s loc_1DD32
0x1dd2a  ldloc.0
0x1dd2b  ldc.i4.0
0x1dd2c  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x1dd31  ret
0x1dd32  ldstr    aCannotdeserial// "CannotDeserializeData"
0x1dd37  ldc.i4.1
0x1dd38  newarr   [mscorlib]System.Object
0x1dd3d  stloc.1
0x1dd3e  ldloc.1
0x1dd3f  ldc.i4.0
0x1dd40  ldtoken  [System]System.Uri
0x1dd45  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1dd4a  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1dd4f  stelem.ref
0x1dd50  ldloc.1
0x1dd51  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x1dd56  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x1dd5b  throw
```
