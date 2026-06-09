# System.Net.Http.Formatting.BufferedMediaTypeFormatter::ReadFromStreamAsync_0

- ea: `0x6ba0`
- end: `0x6be2`
- name: `System.Net.Http.Formatting.BufferedMediaTypeFormatter::ReadFromStreamAsync_0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x6ba0`
- `0x6bf0`
- `0xb3c0`

## string_xrefs

- `0x6bb7`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x6ba0  ldarg.1
0x6ba1  ldnull
0x6ba2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6ba7  brfalse.s loc_6BB4
0x6ba9  ldstr    aType// "type"
0x6bae  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x6bb3  throw
0x6bb4  ldarg.2
0x6bb5  brtrue.s loc_6BC2
0x6bb7  ldstr    aReadstream// "readStream"
0x6bbc  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x6bc1  throw
0x6bc2  nop
0x6bc3  ldarg.0
0x6bc4  ldarg.1
0x6bc5  ldarg.2
0x6bc6  ldarg.3
0x6bc7  ldarg.s  4
0x6bc9  ldarg.s  5
0x6bcb  call     instance object System.Net.Http.Formatting.BufferedMediaTypeFormatter::ReadFromStreamSync(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [System.Net.Http]System.Net.Http.HttpContent content, class System.Net.Http.Formatting.IFormatterLogger formatterLogger, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x6bd0  call     T0x2B000041
0x6bd5  stloc.0
0x6bd6  leave.s  loc_6BE0
0x6bd8  call     T0x2B000042
0x6bdd  stloc.0
0x6bde  leave.s  loc_6BE0
0x6be0  ldloc.0
0x6be1  ret
```
