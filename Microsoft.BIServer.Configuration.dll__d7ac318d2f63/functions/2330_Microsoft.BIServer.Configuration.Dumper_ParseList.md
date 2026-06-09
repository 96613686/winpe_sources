# Microsoft.BIServer.Configuration.Dumper::ParseList

- ea: `0x2330`
- end: `0x237a`
- name: `Microsoft.BIServer.Configuration.Dumper::ParseList`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1e00`

## callees

- `0x2330`

## pseudocode

```c

```

## disassembly

```asm
0x2330  ldarg.0
0x2331  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2336  brtrue.s loc_236F
0x2338  ldarg.0
0x2339  ldc.i4.1
0x233a  newarr   [mscorlib]System.Char
0x233f  dup
0x2340  ldc.i4.0
0x2341  ldc.i4.s 0x2C
0x2343  stelem.i2
0x2344  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2349  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__27_0
0x234e  dup
0x234f  brtrue.s loc_2368
0x2351  pop
0x2352  ldsfld   class <>c <>c::<>9
0x2357  ldftn    instance string <>c::<ParseList>b__27_0(string p)
0x235d  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x2362  dup
0x2363  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__27_0
0x2368  call     T0x2B000025
0x236d  br.s     loc_2374
0x236f  call     T0x2B000026
0x2374  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x2379  ret
```
