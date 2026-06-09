# Microsoft.BIServer.Configuration.UrlApplications::Add_0

- ea: `0x3790`
- end: `0x37c8`
- name: `Microsoft.BIServer.Configuration.UrlApplications::Add_0`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3750`

## callees

- `0x3790`
- `0x7440`

## pseudocode

```c

```

## disassembly

```asm
0x3790  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x3795  stloc.0
0x3796  ldloc.0
0x3797  ldarg.1
0x3798  stfld    class Microsoft.BIServer.Configuration.Application <>c__DisplayClass5_0::app
0x379d  ldarg.0
0x379e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.UrlApplications::_urlApplications
0x37a3  ldloc.0
0x37a4  ldftn    instance bool <>c__DisplayClass5_0::<Add>b__0(class Microsoft.BIServer.Configuration.Application appInList)
0x37aa  newobj   instance void class [mscorlib]System.Predicate`1<class Microsoft.BIServer.Configuration.Application>::.ctor(object, native int)
0x37af  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application>::Exists(class [mscorlib]System.Predicate`1<var<u1>>)
0x37b4  brtrue.s loc_37C7
0x37b6  ldarg.0
0x37b7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.UrlApplications::_urlApplications
0x37bc  ldloc.0
0x37bd  ldfld    class Microsoft.BIServer.Configuration.Application <>c__DisplayClass5_0::app
0x37c2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application>::Add(var<u1>)
0x37c7  ret
```
