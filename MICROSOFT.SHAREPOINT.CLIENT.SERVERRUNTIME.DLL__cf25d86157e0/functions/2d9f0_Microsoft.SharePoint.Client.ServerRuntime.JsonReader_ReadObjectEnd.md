# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObjectEnd

- ea: `0x2d9f0`
- end: `0x2da27`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObjectEnd`
- size: `55`
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
- `0x2d9f0`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2da00`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d9f0  ldarg.0
0x2d9f1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d9f6  stloc.0
0x2d9f7  ldloc.0
0x2d9f8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d9fd  ldc.i4.1
0x2d9fe  beq.s    loc_2DA26
0x2da00  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2da05  ldc.i4.1
0x2da06  newarr   [mscorlib]System.Object
0x2da0b  stloc.1
0x2da0c  ldloc.1
0x2da0d  ldc.i4.0
0x2da0e  ldloc.0
0x2da0f  callvirt instance int32 Token::get_Position()
0x2da14  box      [mscorlib]System.Int32
0x2da19  stelem.ref
0x2da1a  ldloc.1
0x2da1b  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2da20  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2da25  throw
0x2da26  ret
```
