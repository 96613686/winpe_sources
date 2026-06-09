# <CrtImplementationDetails>.ModuleUninitializer::.ctor

- ea: `0x2050`
- end: `0x207a`
- name: `<CrtImplementationDetails>.ModuleUninitializer::.ctor`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x2030`

## pseudocode

```c

```

## disassembly

```asm
0x2050  ldarg.0
0x2051  call     instance void [mscorlib]System.Collections.Stack::.ctor()
0x2056  ldarg.0
0x2057  ldftn    instance void <CrtImplementationDetails>.ModuleUninitializer::SingletonDomainUnload(object source, class [mscorlib]System.EventArgs arguments)
0x205d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2062  stloc.0
0x2063  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x2068  ldloc.0
0x2069  callvirt instance void [mscorlib]System.AppDomain::add_DomainUnload(class [mscorlib]System.EventHandler)
0x206e  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x2073  ldloc.0
0x2074  callvirt instance void [mscorlib]System.AppDomain::add_ProcessExit(class [mscorlib]System.EventHandler)
0x2079  ret
```
