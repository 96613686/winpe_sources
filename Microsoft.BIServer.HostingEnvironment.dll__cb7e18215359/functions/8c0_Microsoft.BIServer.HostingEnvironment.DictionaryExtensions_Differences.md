# Microsoft.BIServer.HostingEnvironment.DictionaryExtensions::Differences

- ea: `0x8c0`
- end: `0x926`
- name: `Microsoft.BIServer.HostingEnvironment.DictionaryExtensions::Differences`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8c0`

## pseudocode

```c

```

## disassembly

```asm
0x8c0  ldarg.0
0x8c1  ldarg.1
0x8c2  call     T0x2B000004
0x8c7  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>, var<u1>> class <>c__0`2<mvar<u1>, !!T0>::<>9__0_0
0x8cc  dup
0x8cd  brtrue.s loc_8E6
0x8cf  pop
0x8d0  ldsfld   class <>c__0`2<var<u1>, !!T0> class <>c__0`2<mvar<u1>, !!T0>::<>9
0x8d5  ldftn    instance var<u1> class <>c__0`2<mvar<u1>, !!T0>::<Differences>b__0_0(!!T0)
0x8db  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<mvar<u1>, !!T0>, mvar<u1>>::.ctor(object, native int)
0x8e0  dup
0x8e1  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>, var<u1>> class <>c__0`2<mvar<u1>, !!T0>::<>9__0_0
0x8e6  call     T0x2B000005
0x8eb  ldarg.1
0x8ec  ldarg.0
0x8ed  call     T0x2B000004
0x8f2  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>, var<u1>> class <>c__0`2<mvar<u1>, !!T0>::<>9__0_1
0x8f7  dup
0x8f8  brtrue.s loc_911
0x8fa  pop
0x8fb  ldsfld   class <>c__0`2<var<u1>, !!T0> class <>c__0`2<mvar<u1>, !!T0>::<>9
0x900  ldftn    instance var<u1> class <>c__0`2<mvar<u1>, !!T0>::<Differences>b__0_1(!!T0)
0x906  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<mvar<u1>, !!T0>, mvar<u1>>::.ctor(object, native int)
0x90b  dup
0x90c  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>, var<u1>> class <>c__0`2<mvar<u1>, !!T0>::<>9__0_1
0x911  call     T0x2B000005
0x916  call     T0x2B000006
0x91b  call     T0x2B000007
0x920  call     T0x2B000008
0x925  ret
```
