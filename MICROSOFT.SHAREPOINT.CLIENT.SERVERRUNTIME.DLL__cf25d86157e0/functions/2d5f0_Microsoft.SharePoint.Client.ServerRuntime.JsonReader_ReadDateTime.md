# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDateTime

- ea: `0x2d5f0`
- end: `0x2d62e`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDateTime`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d630`
- `0x2e060`

## callees

- `0x16f10`
- `0x2d5f0`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x306e0`

## string_xrefs

- `0x2d608`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d5f0  ldarg.0
0x2d5f1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d5f6  stloc.0
0x2d5f7  ldloc.0
0x2d5f8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d5fd  ldc.i4.s 9
0x2d5ff  bne.un.s loc_2D608
0x2d601  ldloc.0
0x2d602  callvirt instance valuetype [mscorlib]System.DateTime Token::get_DateTimeValue()
0x2d607  ret
0x2d608  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d60d  ldc.i4.1
0x2d60e  newarr   [mscorlib]System.Object
0x2d613  stloc.1
0x2d614  ldloc.1
0x2d615  ldc.i4.0
0x2d616  ldloc.0
0x2d617  callvirt instance int32 Token::get_Position()
0x2d61c  box      [mscorlib]System.Int32
0x2d621  stelem.ref
0x2d622  ldloc.1
0x2d623  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d628  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d62d  throw
```
