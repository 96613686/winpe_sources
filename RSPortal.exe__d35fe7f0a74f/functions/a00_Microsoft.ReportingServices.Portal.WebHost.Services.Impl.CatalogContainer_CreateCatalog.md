# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::CreateCatalog

- ea: `0xa00`
- end: `0xa8b`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::CreateCatalog`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x9d0`

## callees

- `0xa00`
- `0xa90`
- `0xac0`

## string_xrefs

- `0xa06`: `AssemblyExtensionPaths`
- `0xa3f`: `Microsoft.BIServer.Owin.Common.dll`

## pseudocode

```c

```

## disassembly

```asm
0xa00  ldarg.0
0xa01  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0xa06  ldstr    aAssemblyextens// "AssemblyExtensionPaths"
0xa0b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa10  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::GetAssemblyExtensionPaths(string assemblyExtensionPaths)
0xa15  stloc.0
0xa16  ldc.i4.1
0xa17  newarr   [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog
0xa1c  dup
0xa1d  ldc.i4.0
0xa1e  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0xa23  newobj   instance void [System.ComponentModel.Composition]System.ComponentModel.Composition.Hosting.AssemblyCatalog::.ctor(class [mscorlib]System.Reflection.Assembly)
0xa28  stelem.ref
0xa29  newobj   instance void [System.ComponentModel.Composition]System.ComponentModel.Composition.Hosting.AggregateCatalog::.ctor(class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog[])
0xa2e  stloc.1
0xa2f  ldloc.1
0xa30  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog> [System.ComponentModel.Composition]System.ComponentModel.Composition.Hosting.AggregateCatalog::get_Catalogs()
0xa35  ldstr    asc_5380// "."
0xa3a  call     string Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::GetStandardizedPathName(string path)
0xa3f  ldstr    aMicrosoftBiser// "Microsoft.BIServer.Owin.Common.dll"
0xa44  newobj   instance void [System.ComponentModel.Composition]System.ComponentModel.Composition.Hosting.DirectoryCatalog::.ctor(string, string)
0xa49  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog>::Add(var<u1>)
0xa4e  ldloc.0
0xa4f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0xa54  stloc.2
0xa55  br.s     loc_A75
0xa57  ldloc.2
0xa58  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0xa5d  stloc.3
0xa5e  ldloc.1
0xa5f  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog> [System.ComponentModel.Composition]System.ComponentModel.Composition.Hosting.AggregateCatalog::get_Catalogs()
0xa64  ldarg.0
0xa65  ldfld    class [mscorlib]System.Func`2<string, class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::NewDirectoryCatalog
0xa6a  ldloc.3
0xa6b  callvirt instance var<u1> class [mscorlib]System.Func`2<string, class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog>::Invoke(void)
0xa70  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog>::Add(var<u1>)
0xa75  ldloc.2
0xa76  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa7b  brtrue.s loc_A57
0xa7d  leave.s  loc_A89
0xa7f  ldloc.2
0xa80  brfalse.s loc_A88
0xa82  ldloc.2
0xa83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa88  endfinally
0xa89  ldloc.1
0xa8a  ret
```
