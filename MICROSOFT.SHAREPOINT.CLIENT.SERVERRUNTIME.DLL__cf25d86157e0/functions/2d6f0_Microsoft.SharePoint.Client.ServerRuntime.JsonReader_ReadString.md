# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadString

- ea: `0x2d6f0`
- end: `0x2d739`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadString`
- size: `73`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d740`
- `0x2e180`
- `0x2e470`
- `0x2e520`

## callees

- `0x16f10`
- `0x2d6f0`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x30570`

## string_xrefs

- `0x2d713`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d6f0  ldarg.0
0x2d6f1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d6f6  stloc.0
0x2d6f7  ldloc.0
0x2d6f8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d6fd  ldc.i4.4
0x2d6fe  bne.un.s loc_2D707
0x2d700  ldloc.0
0x2d701  callvirt instance string Token::get_StringValue()
0x2d706  ret
0x2d707  ldloc.0
0x2d708  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d70d  ldc.i4.s 0xB
0x2d70f  bne.un.s loc_2D713
0x2d711  ldnull
0x2d712  ret
0x2d713  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d718  ldc.i4.1
0x2d719  newarr   [mscorlib]System.Object
0x2d71e  stloc.1
0x2d71f  ldloc.1
0x2d720  ldc.i4.0
0x2d721  ldloc.0
0x2d722  callvirt instance int32 Token::get_Position()
0x2d727  box      [mscorlib]System.Int32
0x2d72c  stelem.ref
0x2d72d  ldloc.1
0x2d72e  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d733  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d738  throw
```
