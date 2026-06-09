# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObjectStart

- ea: `0x2d930`
- end: `0x2d966`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObjectStart`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e370`
- `0x2e470`
- `0x2e520`
- `0x2e5e0`

## callees

- `0x16f10`
- `0x2d930`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2d93f`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d930  ldarg.0
0x2d931  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d936  stloc.0
0x2d937  ldloc.0
0x2d938  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d93d  brfalse.s loc_2D965
0x2d93f  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d944  ldc.i4.1
0x2d945  newarr   [mscorlib]System.Object
0x2d94a  stloc.1
0x2d94b  ldloc.1
0x2d94c  ldc.i4.0
0x2d94d  ldloc.0
0x2d94e  callvirt instance int32 Token::get_Position()
0x2d953  box      [mscorlib]System.Int32
0x2d958  stelem.ref
0x2d959  ldloc.1
0x2d95a  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d95f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d964  throw
0x2d965  ret
```
