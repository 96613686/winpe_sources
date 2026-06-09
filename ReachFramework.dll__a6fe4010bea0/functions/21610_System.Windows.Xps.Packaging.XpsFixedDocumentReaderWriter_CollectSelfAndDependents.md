# System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::CollectSelfAndDependents

- ea: `0x21610`
- end: `0x21698`
- name: `System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::CollectSelfAndDependents`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x20e30`

## callees

- `0x201e0`
- `0x20230`
- `0x20240`
- `0x21610`
- `0x21730`
- `0x24c80`
- `0x25a70`
- `0x25aa0`

## pseudocode

```c

```

## disassembly

```asm
0x21610  ldarg.1
0x21611  ldarg.0
0x21612  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x21617  ldarg.0
0x21618  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2161d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [System]System.Uri>::set_Item(var<u1>, !!T0)
0x21622  ldarg.0
0x21623  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x21628  ldarg.0
0x21629  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2162e  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GetSignatureDefinitionPart(class [System]System.Uri documentUri)
0x21633  stloc.0
0x21634  ldarg.2
0x21635  ldarg.0
0x21636  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2163b  ldc.i4.1
0x2163c  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SignatureDefinitionRelationshipName()
0x21641  newobj   instance void [WindowsBase]System.IO.Packaging.PackageRelationshipSelector::.ctor(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.PackageRelationshipSelectorType, string)
0x21646  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [WindowsBase]System.IO.Packaging.PackageRelationshipSelector>::Add(var<u1>)
0x2164b  ldloc.0
0x2164c  brfalse.s loc_21660
0x2164e  ldarg.1
0x2164f  ldloc.0
0x21650  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x21655  ldloc.0
0x21656  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x2165b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [System]System.Uri>::set_Item(var<u1>, !!T0)
0x21660  ldarg.2
0x21661  ldarg.0
0x21662  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x21667  ldc.i4.1
0x21668  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_RestrictedFontRelationshipType()
0x2166d  newobj   instance void [WindowsBase]System.IO.Packaging.PackageRelationshipSelector::.ctor(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.PackageRelationshipSelectorType, string)
0x21672  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [WindowsBase]System.IO.Packaging.PackageRelationshipSelector>::Add(var<u1>)
0x21677  ldarg.2
0x21678  ldarg.0
0x21679  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2167e  ldc.i4.1
0x2167f  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_StructureRelationshipName()
0x21684  newobj   instance void [WindowsBase]System.IO.Packaging.PackageRelationshipSelector::.ctor(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.PackageRelationshipSelectorType, string)
0x21689  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [WindowsBase]System.IO.Packaging.PackageRelationshipSelector>::Add(var<u1>)
0x2168e  ldarg.0
0x2168f  ldarg.1
0x21690  ldarg.2
0x21691  ldarg.3
0x21692  call     instance void System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::CollectDependents(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [System]System.Uri> dependents, class [mscorlib]System.Collections.Generic.List`1<class [WindowsBase]System.IO.Packaging.PackageRelationshipSelector> selectorList, valuetype System.Windows.Xps.Packaging.XpsDigSigPartAlteringRestrictions restrictions)
0x21697  ret
```
