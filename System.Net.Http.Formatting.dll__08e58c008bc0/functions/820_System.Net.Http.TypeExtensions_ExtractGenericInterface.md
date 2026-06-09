# System.Net.Http.TypeExtensions::ExtractGenericInterface

- ea: `0x820`
- end: `0x850`
- name: `System.Net.Http.TypeExtensions::ExtractGenericInterface`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x7fa0`

## callees

- `0x820`
- `0xbf20`

## pseudocode

```c

```

## disassembly

```asm
0x820  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x825  dup
0x826  ldarg.1
0x827  stfld    class [mscorlib]System.Type <>c__DisplayClass0_0::interfaceType
0x82c  ldftn    instance bool <>c__DisplayClass0_0::<ExtractGenericInterface>b__0(class [mscorlib]System.Type t)
0x832  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Type, bool>::.ctor(object, native int)
0x837  stloc.0
0x838  ldloc.0
0x839  ldarg.0
0x83a  callvirt instance var<u1> class [mscorlib]System.Func`2<class [mscorlib]System.Type, bool>::Invoke(void)
0x83f  brtrue.s loc_84E
0x841  ldarg.0
0x842  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Type::GetInterfaces()
0x847  ldloc.0
0x848  call     T0x2B000005
0x84d  ret
0x84e  ldarg.0
0x84f  ret
```
