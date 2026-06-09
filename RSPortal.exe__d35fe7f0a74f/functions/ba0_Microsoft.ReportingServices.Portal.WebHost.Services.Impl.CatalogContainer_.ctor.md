# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::.ctor

- ea: `0xba0`
- end: `0xbde`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::.ctor`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xba0`

## pseudocode

```c

```

## disassembly

```asm
0xba0  ldarg.0
0xba1  ldnull
0xba2  ldftn    bool [mscorlib]System.IO.Directory::Exists(string)
0xba8  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xbad  stfld    class [mscorlib]System.Func`2<string, bool> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::DirectoryExists
0xbb2  ldarg.0
0xbb3  ldsfld   class [mscorlib]System.Func`2<string, class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog> <>c::<>9__9_0
0xbb8  dup
0xbb9  brtrue.s loc_BD2
0xbbb  pop
0xbbc  ldsfld   class <>c <>c::<>9
0xbc1  ldftn    instance class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog <>c::<.ctor>b__9_0(string s)
0xbc7  newobj   instance void class [mscorlib]System.Func`2<string, class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog>::.ctor(object, native int)
0xbcc  dup
0xbcd  stsfld   class [mscorlib]System.Func`2<string, class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog> <>c::<>9__9_0
0xbd2  stfld    class [mscorlib]System.Func`2<string, class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::NewDirectoryCatalog
0xbd7  ldarg.0
0xbd8  call     instance void [mscorlib]System.Object::.ctor()
0xbdd  ret
```
