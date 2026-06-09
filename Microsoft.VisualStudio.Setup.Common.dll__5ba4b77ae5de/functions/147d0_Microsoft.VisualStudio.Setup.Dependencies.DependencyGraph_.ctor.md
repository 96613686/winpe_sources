# Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::.ctor

- ea: `0x147d0`
- end: `0x14837`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::.ctor`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x15730`

## callees

- `0xc1a0`
- `0x147d0`
- `0x15540`
- `0x155e0`

## string_xrefs

- `0x147e5`: `services`

## pseudocode

```c

```

## disassembly

```asm
0x147d0  ldarg.0
0x147d1  call     instance void [mscorlib]System.Object::.ctor()
0x147d6  ldarg.1
0x147d7  ldstr    aRoot// "root"
0x147dc  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x147e1  ldarg.2
0x147e2  brfalse.s loc_147EF
0x147e4  ldarg.3
0x147e5  ldstr    aServices// "services"
0x147ea  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x147ef  ldarg.0
0x147f0  ldarg.3
0x147f1  stfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::services
0x147f6  ldarg.0
0x147f7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Exception>::.ctor()
0x147fc  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.Exception> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::nonFatalExceptions
0x14801  ldarg.0
0x14802  ldarg.1
0x14803  stfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::<Root>k__BackingField
0x14808  ldarg.0
0x14809  ldsfld   class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.ManifestIdentityComparer::StringComparer
0x1480e  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x14813  stfld    class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::catalogsToUninstall
0x14818  ldarg.2
0x14819  brtrue.s loc_14829
0x1481b  ldarg.0
0x1481c  ldarg.0
0x1481d  ldarg.1
0x1481e  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::SortByInstallOrder(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode root)
0x14823  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::<InstallOrder>k__BackingField
0x14828  ret
0x14829  ldarg.0
0x1482a  ldarg.0
0x1482b  ldarg.1
0x1482c  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::BuildUpdateOrder(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode root)
0x14831  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::<InstallOrder>k__BackingField
0x14836  ret
```
