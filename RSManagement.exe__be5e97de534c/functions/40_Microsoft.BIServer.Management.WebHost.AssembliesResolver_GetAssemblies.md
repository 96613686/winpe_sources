# Microsoft.BIServer.Management.WebHost.AssembliesResolver::GetAssemblies

- ea: `0x40`
- end: `0x60`
- name: `Microsoft.BIServer.Management.WebHost.AssembliesResolver::GetAssemblies`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x4d`: `Microsoft.BIServer.Management.WebApi.dll`

## pseudocode

```c

```

## disassembly

```asm
0x40  ldarg.0
0x41  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Reflection.Assembly> [System.Web.Http]System.Web.Http.Dispatcher.DefaultAssembliesResolver::GetAssemblies()
0x46  dup
0x47  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Reflection.Assembly>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x4c  stloc.0
0x4d  ldstr    aMicrosoftBiser// "Microsoft.BIServer.Management.WebApi.dl"...
0x52  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadFrom(string)
0x57  stloc.1
0x58  ldloc.1
0x59  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Reflection.Assembly>::Add(var<u1>)
0x5e  ldloc.0
0x5f  ret
```
