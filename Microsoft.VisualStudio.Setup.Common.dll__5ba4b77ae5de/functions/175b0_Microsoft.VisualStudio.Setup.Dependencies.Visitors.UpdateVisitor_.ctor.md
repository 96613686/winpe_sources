# Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::.ctor

- ea: `0x175b0`
- end: `0x175e6`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::.ctor`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15540`

## callees

- `0xc1a0`
- `0x16ac0`
- `0x16b60`

## string_xrefs

- `0x175cb`: `Cache`

## pseudocode

```c

```

## disassembly

```asm
0x175b0  ldarg.0
0x175b1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::.ctor()
0x175b6  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::uninstalls
0x175bb  ldarg.0
0x175bc  ldarg.1
0x175bd  ldarg.3
0x175be  ldarg.s  4
0x175c0  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::.ctor(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode rootNode, [opt] class [mscorlib]System.IServiceProvider services, [opt] class [System]System.Collections.Generic.ISet`1<string> catalogsToUninstall)
0x175c5  ldarg.0
0x175c6  call     instance class Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_Cache()
0x175cb  ldstr    aCache_0// "Cache"
0x175d0  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x175d5  ldarg.0
0x175d6  ldarg.2
0x175d7  stfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::defaultVersion
0x175dc  ldarg.0
0x175dd  ldarg.s  5
0x175df  ldind.ref
0x175e0  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.Exception> Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::nonFatalExceptions
0x175e5  ret
```
