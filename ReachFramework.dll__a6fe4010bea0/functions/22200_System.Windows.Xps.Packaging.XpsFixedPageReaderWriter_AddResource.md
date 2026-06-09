# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddResource

- ea: `0x22200`
- end: `0x22326`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddResource`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x20080`
- `0x20210`
- `0x22200`
- `0x22d40`
- `0x22dc0`
- `0x22e80`
- `0x22f00`
- `0x22f80`
- `0x249a0`
- `0x24be0`
- `0x25950`
- `0x25a70`
- `0x25aa0`
- `0x26400`

## string_xrefs

- `0x22208`: `FixedPageReader`

## pseudocode

```c

```

## disassembly

```asm
0x22200  ldarg.0
0x22201  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x22206  brtrue.s loc_22213
0x22208  ldstr    aFixedpagereade// "FixedPageReader"
0x2220d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x22212  throw
0x22213  ldnull
0x22214  stloc.0
0x22215  ldarg.2
0x22216  ldnull
0x22217  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x2221c  brfalse.s loc_22237
0x2221e  ldarg.0
0x2221f  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22224  ldarg.2
0x22225  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GetPart(class [System]System.Uri uri)
0x2222a  stloc.0
0x2222b  ldloc.0
0x2222c  brtrue.s loc_22237
0x2222e  ldarg.0
0x2222f  ldarg.1
0x22230  ldarg.2
0x22231  call     instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::GeneratePartForResourceType(class [mscorlib]System.Type resourceType, class [System]System.Uri resourceUri)
0x22236  stloc.0
0x22237  ldarg.1
0x22238  ldtoken  System.Windows.Xps.Packaging.XpsImage
0x2223d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22242  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x22247  brfalse.s loc_22256
0x22249  ldarg.0
0x2224a  ldloc.0
0x2224b  call     instance class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddImage(class [WindowsBase]System.IO.Packaging.PackagePart packagePart)
0x22250  stloc.1
0x22251  br       loc_22324
0x22256  ldarg.1
0x22257  ldtoken  System.Windows.Xps.Packaging.XpsFont
0x2225c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22261  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x22266  brfalse.s loc_22275
0x22268  ldarg.0
0x22269  ldloc.0
0x2226a  call     instance class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddFont(class [WindowsBase]System.IO.Packaging.PackagePart packagePart)
0x2226f  stloc.1
0x22270  br       loc_22324
0x22275  ldarg.1
0x22276  ldtoken  System.Windows.Xps.Packaging.XpsColorContext
0x2227b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22280  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x22285  brfalse.s loc_22294
0x22287  ldarg.0
0x22288  ldloc.0
0x22289  call     instance class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddColorContext(class [WindowsBase]System.IO.Packaging.PackagePart packagePart)
0x2228e  stloc.1
0x2228f  br       loc_22324
0x22294  ldarg.1
0x22295  ldtoken  System.Windows.Xps.Packaging.XpsResourceDictionary
0x2229a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2229f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x222a4  brfalse.s loc_222B0
0x222a6  ldarg.0
0x222a7  ldloc.0
0x222a8  call     instance class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddResourceDictionary(class [WindowsBase]System.IO.Packaging.PackagePart packagePart)
0x222ad  stloc.1
0x222ae  br.s     loc_22324
0x222b0  ldloc.0
0x222b1  brtrue.s loc_222CD
0x222b3  ldarg.2
0x222b4  ldnull
0x222b5  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x222ba  brfalse.s loc_222CD
0x222bc  ldarg.0
0x222bd  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x222c2  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceContentType()
0x222c7  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart(class [WindowsBase]MS.Internal.ContentType contentType)
0x222cc  stloc.0
0x222cd  ldarg.0
0x222ce  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x222d3  ldarg.0
0x222d4  ldloc.0
0x222d5  newobj   instance void System.Windows.Xps.Packaging.XpsResource::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x222da  stloc.1
0x222db  ldarg.0
0x222dc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsResource> System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_resourceCache
0x222e1  ldloc.1
0x222e2  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x222e7  ldloc.1
0x222e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsResource>::set_Item(var<u1>, !!T0)
0x222ed  ldarg.0
0x222ee  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x222f3  ldloc.0
0x222f4  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x222f9  call     string System.Windows.Xps.Packaging.XpsManager::MakeRelativePath(class [System]System.Uri baseUri, class [System]System.Uri fileUri)
0x222fe  stloc.2
0x222ff  ldarg.0
0x22300  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Xps.Packaging.INode> System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_currentChildren
0x22305  ldloc.1
0x22306  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Xps.Packaging.INode>::Add(var<u1>)
0x2230b  ldarg.0
0x2230c  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x22311  ldloc.2
0x22312  ldc.i4.2
0x22313  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x22318  ldc.i4.0
0x22319  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceRelationshipName()
0x2231e  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string)
0x22323  pop
0x22324  ldloc.1
0x22325  ret
```
