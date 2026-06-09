# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadChar

- ea: `0x2d1f0`
- end: `0x2d233`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadChar`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d240`

## callees

- `0x16f10`
- `0x2d1f0`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x30570`

## string_xrefs

- `0x2d20d`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d1f0  ldarg.0
0x2d1f1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d1f6  stloc.0
0x2d1f7  ldloc.0
0x2d1f8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d1fd  ldc.i4.4
0x2d1fe  bne.un.s loc_2D20D
0x2d200  ldloc.0
0x2d201  callvirt instance string Token::get_StringValue()
0x2d206  ldc.i4.0
0x2d207  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2d20c  ret
0x2d20d  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d212  ldc.i4.1
0x2d213  newarr   [mscorlib]System.Object
0x2d218  stloc.1
0x2d219  ldloc.1
0x2d21a  ldc.i4.0
0x2d21b  ldloc.0
0x2d21c  callvirt instance int32 Token::get_Position()
0x2d221  box      [mscorlib]System.Int32
0x2d226  stelem.ref
0x2d227  ldloc.1
0x2d228  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d22d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d232  throw
```
