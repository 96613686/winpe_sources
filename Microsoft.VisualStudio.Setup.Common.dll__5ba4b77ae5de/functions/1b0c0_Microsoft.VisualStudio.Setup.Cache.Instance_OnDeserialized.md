# Microsoft.VisualStudio.Setup.Cache.Instance::OnDeserialized

- ea: `0x1b0c0`
- end: `0x1b10a`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::OnDeserialized`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1a950`
- `0x1a960`
- `0x1a980`
- `0x1ae10`
- `0x1b0c0`
- `0x1bca0`

## pseudocode

```c

```

## disassembly

```asm
0x1b0c0  ldarg.0
0x1b0c1  call     instance class Microsoft.VisualStudio.Setup.Cache.ProductReference Microsoft.VisualStudio.Setup.Cache.Instance::get_Product()
0x1b0c6  brtrue.s loc_1B103
0x1b0c8  ldarg.0
0x1b0c9  call     instance class Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.Instance::get_Packages()
0x1b0ce  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.PackageReference, bool> <>c::<>9__237_0
0x1b0d3  dup
0x1b0d4  brtrue.s loc_1B0ED
0x1b0d6  pop
0x1b0d7  ldsfld   class <>c <>c::<>9
0x1b0dc  ldftn    instance bool <>c::<OnDeserialized>b__237_0(class Microsoft.VisualStudio.Setup.Cache.PackageReference package)
0x1b0e2  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.PackageReference, bool>::.ctor(object, native int)
0x1b0e7  dup
0x1b0e8  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.PackageReference, bool> <>c::<>9__237_0
0x1b0ed  call     T0x2B0000D0
0x1b0f2  stloc.0
0x1b0f3  ldloc.0
0x1b0f4  brfalse.s loc_1B103
0x1b0f6  ldarg.0
0x1b0f7  ldloc.0
0x1b0f8  ldc.i4.1
0x1b0f9  call     class Microsoft.VisualStudio.Setup.Cache.ProductReference Microsoft.VisualStudio.Setup.Cache.ProductReference::FromIdentity(class Microsoft.VisualStudio.Setup.IPackageIdentity identity, [opt] bool installed)
0x1b0fe  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_Product(class Microsoft.VisualStudio.Setup.Cache.ProductReference value)
0x1b103  ldarg.0
0x1b104  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::ResetChanged()
0x1b109  ret
```
