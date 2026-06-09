# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDouble

- ea: `0x2d4c0`
- end: `0x2d520`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDouble`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d520`
- `0x2deb0`

## callees

- `0x16f10`
- `0x2d4c0`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`
- `0x30620`
- `0x30660`

## string_xrefs

- `0x2d4fa`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d4c0  ldarg.0
0x2d4c1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d4c6  stloc.0
0x2d4c7  ldloc.0
0x2d4c8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d4cd  ldc.i4.5
0x2d4ce  bne.un.s loc_2D4D8
0x2d4d0  ldloc.0
0x2d4d1  callvirt instance int64 Token::get_LongValue()
0x2d4d6  conv.r8
0x2d4d7  ret
0x2d4d8  ldloc.0
0x2d4d9  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d4de  ldc.i4.6
0x2d4df  bne.un.s loc_2D4EA
0x2d4e1  ldloc.0
0x2d4e2  callvirt instance unsigned int64 Token::get_ULongValue()
0x2d4e7  conv.r.un
0x2d4e8  conv.r8
0x2d4e9  ret
0x2d4ea  ldloc.0
0x2d4eb  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d4f0  ldc.i4.7
0x2d4f1  bne.un.s loc_2D4FA
0x2d4f3  ldloc.0
0x2d4f4  callvirt instance float64 Token::get_DoubleValue()
0x2d4f9  ret
0x2d4fa  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d4ff  ldc.i4.1
0x2d500  newarr   [mscorlib]System.Object
0x2d505  stloc.1
0x2d506  ldloc.1
0x2d507  ldc.i4.0
0x2d508  ldloc.0
0x2d509  callvirt instance int32 Token::get_Position()
0x2d50e  box      [mscorlib]System.Int32
0x2d513  stelem.ref
0x2d514  ldloc.1
0x2d515  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d51a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d51f  throw
```
