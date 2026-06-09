# System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::ReadFromStreamAsync

- ea: `0x75e0`
- end: `0x761d`
- name: `System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::ReadFromStreamAsync`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x75e0`
- `0x7620`
- `0xb3c0`

## string_xrefs

- `0x75f7`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x75e0  ldarg.1
0x75e1  ldnull
0x75e2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x75e7  brfalse.s loc_75F4
0x75e9  ldstr    aType// "type"
0x75ee  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x75f3  throw
0x75f4  ldarg.2
0x75f5  brtrue.s loc_7602
0x75f7  ldstr    aReadstream// "readStream"
0x75fc  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7601  throw
0x7602  nop
0x7603  ldarg.0
0x7604  ldarg.1
0x7605  ldarg.2
0x7606  call     instance object System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::ReadFromStream(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream)
0x760b  call     T0x2B000041
0x7610  stloc.0
0x7611  leave.s  loc_761B
0x7613  call     T0x2B000042
0x7618  stloc.0
0x7619  leave.s  loc_761B
0x761b  ldloc.0
0x761c  ret
```
