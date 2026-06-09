# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadBoolean

- ea: `0x2d150`
- end: `0x2d18d`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadBoolean`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d190`
- `0x2da30`

## callees

- `0x16f10`
- `0x2d150`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x306a0`

## string_xrefs

- `0x2d167`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d150  ldarg.0
0x2d151  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d156  stloc.0
0x2d157  ldloc.0
0x2d158  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d15d  ldc.i4.8
0x2d15e  bne.un.s loc_2D167
0x2d160  ldloc.0
0x2d161  callvirt instance bool Token::get_BoolValue()
0x2d166  ret
0x2d167  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d16c  ldc.i4.1
0x2d16d  newarr   [mscorlib]System.Object
0x2d172  stloc.1
0x2d173  ldloc.1
0x2d174  ldc.i4.0
0x2d175  ldloc.0
0x2d176  callvirt instance int32 Token::get_Position()
0x2d17b  box      [mscorlib]System.Int32
0x2d180  stelem.ref
0x2d181  ldloc.1
0x2d182  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d187  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d18c  throw
```
