# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadEnumArray

- ea: `0x2e210`
- end: `0x2e281`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadEnumArray`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16f10`
- `0x2d8f0`
- `0x2e210`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2e232`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2e210  ldarg.0
0x2e211  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e216  stloc.0
0x2e217  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<mvar<u1>>::.ctor()
0x2e21c  stloc.1
0x2e21d  ldloc.0
0x2e21e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e223  ldc.i4.s 0xB
0x2e225  bne.un.s loc_2E229
0x2e227  ldnull
0x2e228  ret
0x2e229  ldloc.0
0x2e22a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e22f  ldc.i4.2
0x2e230  beq.s    loc_2E264
0x2e232  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2e237  ldc.i4.1
0x2e238  newarr   [mscorlib]System.Object
0x2e23d  stloc.2
0x2e23e  ldloc.2
0x2e23f  ldc.i4.0
0x2e240  ldloc.0
0x2e241  callvirt instance int32 Token::get_Position()
0x2e246  box      [mscorlib]System.Int32
0x2e24b  stelem.ref
0x2e24c  ldloc.2
0x2e24d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2e252  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e257  throw
0x2e258  ldloc.1
0x2e259  ldarg.0
0x2e25a  call     T0x2B000043
0x2e25f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<mvar<u1>>::Add(var<u1>)
0x2e264  ldarg.0
0x2e265  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2e26a  dup
0x2e26b  stloc.0
0x2e26c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e271  ldc.i4.3
0x2e272  bne.un.s loc_2E258
0x2e274  ldarg.0
0x2e275  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2e27a  ldloc.1
0x2e27b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<mvar<u1>>::ToArray()
0x2e280  ret
```
