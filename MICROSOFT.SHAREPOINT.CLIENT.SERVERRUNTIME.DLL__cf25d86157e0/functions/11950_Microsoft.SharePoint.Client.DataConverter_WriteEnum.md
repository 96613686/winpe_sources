# Microsoft.SharePoint.Client.DataConverter::WriteEnum

- ea: `0x11950`
- end: `0x11988`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteEnum`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x11950`
- `0x13470`
- `0x13560`

## string_xrefs

- `0x11953`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11950  ldarg.0
0x11951  brtrue.s loc_1195E
0x11953  ldstr    aWriter// "writer"
0x11958  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1195d  throw
0x1195e  ldtoken  mvar<u1>
0x11963  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11968  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x1196d  brtrue.s loc_11976
0x1196f  ldarg.0
0x11970  ldc.i4.0
0x11971  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0x11976  ldarg.0
0x11977  ldarg.1
0x11978  box      mvar<u1>
0x1197d  castclass [mscorlib]System.Enum
0x11982  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(class [mscorlib]System.Enum value)
0x11987  ret
```
