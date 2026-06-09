# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTimeSpan

- ea: `0x2d590`
- end: `0x2d5d2`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTimeSpan`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d5e0`
- `0x2dfd0`

## callees

- `0x16f10`
- `0x2d590`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x30570`

## string_xrefs

- `0x2d5ac`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d590  ldarg.0
0x2d591  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d596  stloc.0
0x2d597  ldloc.0
0x2d598  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d59d  ldc.i4.4
0x2d59e  bne.un.s loc_2D5AC
0x2d5a0  ldloc.0
0x2d5a1  callvirt instance string Token::get_StringValue()
0x2d5a6  call     valuetype [mscorlib]System.TimeSpan [System.Xml]System.Xml.XmlConvert::ToTimeSpan(string)
0x2d5ab  ret
0x2d5ac  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d5b1  ldc.i4.1
0x2d5b2  newarr   [mscorlib]System.Object
0x2d5b7  stloc.1
0x2d5b8  ldloc.1
0x2d5b9  ldc.i4.0
0x2d5ba  ldloc.0
0x2d5bb  callvirt instance int32 Token::get_Position()
0x2d5c0  box      [mscorlib]System.Int32
0x2d5c5  stelem.ref
0x2d5c6  ldloc.1
0x2d5c7  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d5cc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d5d1  throw
```
