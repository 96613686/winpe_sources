# System.Windows.Media.CacheMode::Parse

- ea: `0x74140`
- end: `0x74169`
- name: `System.Windows.Media.CacheMode::Parse`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x83200`
- `0xf1420`

## callees

- `0x71560`
- `0x74140`
- `0x146e40`

## string_xrefs

- `0x74157`: `Parsers_IllegalToken`
- `0x74143`: `BitmapCache`

## pseudocode

```c

```

## disassembly

```asm
0x74140  ldnull
0x74141  stloc.0
0x74142  ldarg.0
0x74143  ldstr    aBitmapcache// "BitmapCache"
0x74148  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7414d  brfalse.s loc_74157
0x7414f  newobj   instance void System.Windows.Media.BitmapCache::.ctor()
0x74154  stloc.0
0x74155  br.s     loc_74167
0x74157  ldstr    aParsersIllegal// "Parsers_IllegalToken"
0x7415c  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x74161  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x74166  throw
0x74167  ldloc.0
0x74168  ret
```
