# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadKeyValue

- ea: `0x2e630`
- end: `0x2e67d`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadKeyValue`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e370`
- `0x2e5e0`

## callees

- `0x16f10`
- `0x2e630`
- `0x2e8d0`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x30570`

## string_xrefs

- `0x2e641`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2e630  ldarg.0
0x2e631  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e636  stloc.0
0x2e637  ldloc.0
0x2e638  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e63d  ldc.i4.s 0xC
0x2e63f  beq.s    loc_2E667
0x2e641  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2e646  ldc.i4.1
0x2e647  newarr   [mscorlib]System.Object
0x2e64c  stloc.3
0x2e64d  ldloc.3
0x2e64e  ldc.i4.0
0x2e64f  ldloc.0
0x2e650  callvirt instance int32 Token::get_Position()
0x2e655  box      [mscorlib]System.Int32
0x2e65a  stelem.ref
0x2e65b  ldloc.3
0x2e65c  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2e661  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e666  throw
0x2e667  ldloc.0
0x2e668  callvirt instance string Token::get_StringValue()
0x2e66d  stloc.1
0x2e66e  ldarg.0
0x2e66f  call     instance object Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObject()
0x2e674  stloc.2
0x2e675  ldloc.1
0x2e676  ldloc.2
0x2e677  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::.ctor(var<u1>, !!T0)
0x2e67c  ret
```
