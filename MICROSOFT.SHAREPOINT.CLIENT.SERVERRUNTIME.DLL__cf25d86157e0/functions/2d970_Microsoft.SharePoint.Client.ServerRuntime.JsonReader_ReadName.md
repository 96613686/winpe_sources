# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadName

- ea: `0x2d970`
- end: `0x2d9ae`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadName`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e470`
- `0x2e520`

## callees

- `0x16f10`
- `0x2d970`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x30570`

## string_xrefs

- `0x2d988`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d970  ldarg.0
0x2d971  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d976  stloc.0
0x2d977  ldloc.0
0x2d978  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d97d  ldc.i4.s 0xC
0x2d97f  bne.un.s loc_2D988
0x2d981  ldloc.0
0x2d982  callvirt instance string Token::get_StringValue()
0x2d987  ret
0x2d988  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d98d  ldc.i4.1
0x2d98e  newarr   [mscorlib]System.Object
0x2d993  stloc.1
0x2d994  ldloc.1
0x2d995  ldc.i4.0
0x2d996  ldloc.0
0x2d997  callvirt instance int32 Token::get_Position()
0x2d99c  box      [mscorlib]System.Int32
0x2d9a1  stelem.ref
0x2d9a2  ldloc.1
0x2d9a3  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d9a8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d9ad  throw
```
