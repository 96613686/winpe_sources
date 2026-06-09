# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStreamAsync

- ea: `0x55d0`
- end: `0x5610`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStreamAsync`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x5960`

## callees

- `0x55d0`
- `0x5610`
- `0xb3c0`

## string_xrefs

- `0x55e7`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x55d0  ldarg.1
0x55d1  ldnull
0x55d2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x55d7  brfalse.s loc_55E4
0x55d9  ldstr    aType// "type"
0x55de  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x55e3  throw
0x55e4  ldarg.2
0x55e5  brtrue.s loc_55F2
0x55e7  ldstr    aReadstream// "readStream"
0x55ec  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x55f1  throw
0x55f2  nop
0x55f3  ldarg.0
0x55f4  ldarg.1
0x55f5  ldarg.2
0x55f6  ldarg.3
0x55f7  ldarg.s  4
0x55f9  call     instance object System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStream(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [System.Net.Http]System.Net.Http.HttpContent content, class System.Net.Http.Formatting.IFormatterLogger formatterLogger)
0x55fe  call     T0x2B000041
0x5603  stloc.0
0x5604  leave.s  loc_560E
0x5606  call     T0x2B000042
0x560b  stloc.0
0x560c  leave.s  loc_560E
0x560e  ldloc.0
0x560f  ret
```
