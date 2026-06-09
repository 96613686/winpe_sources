# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt32

- ea: `0x2d2f0`
- end: `0x2d32e`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt32`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d330`
- `0x2dbe0`

## callees

- `0x16f10`
- `0x2d2f0`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`

## string_xrefs

- `0x2d308`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d2f0  ldarg.0
0x2d2f1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d2f6  stloc.0
0x2d2f7  ldloc.0
0x2d2f8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d2fd  ldc.i4.5
0x2d2fe  bne.un.s loc_2D308
0x2d300  ldloc.0
0x2d301  callvirt instance int64 Token::get_LongValue()
0x2d306  conv.i4
0x2d307  ret
0x2d308  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d30d  ldc.i4.1
0x2d30e  newarr   [mscorlib]System.Object
0x2d313  stloc.1
0x2d314  ldloc.1
0x2d315  ldc.i4.0
0x2d316  ldloc.0
0x2d317  callvirt instance int32 Token::get_Position()
0x2d31c  box      [mscorlib]System.Int32
0x2d321  stelem.ref
0x2d322  ldloc.1
0x2d323  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d328  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d32d  throw
```
