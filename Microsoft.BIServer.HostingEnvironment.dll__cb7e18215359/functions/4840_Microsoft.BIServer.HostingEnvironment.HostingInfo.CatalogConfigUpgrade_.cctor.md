# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::.cctor

- ea: `0x4840`
- end: `0x4877`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::.cctor`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x4840  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4845  dup
0x4846  ldstr    aCustomheadersH_0// "<CustomHeaders> <Header> <Name>X-Frame-"...
0x484b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4850  dup
0x4851  ldstr    aCustomheadersH_1// "<CustomHeaders> <Header> <Name>X-Frame-"...
0x4856  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x485b  dup
0x485c  ldstr    aCustomheadersH_2// "<CustomHeaders> <Header> <Name>X-Frame-"...
0x4861  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4866  dup
0x4867  ldstr    aCustomheadersH_3// "<CustomHeaders> <Header> <Name>X-Frame-"...
0x486c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4871  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::OriginalCustomHeaders
0x4876  ret
```
