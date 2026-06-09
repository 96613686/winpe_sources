# System.Windows.Navigation.BaseUriHelper::.cctor

- ea: `0x2f7f0`
- end: `0x2f866`
- name: `System.Windows.Navigation.BaseUriHelper::.cctor`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x2f8a0`
- `0x1314f0`
- `0x133d90`

## string_xrefs

- `0x2f818`: `BaseUri`

## pseudocode

```c

```

## disassembly

```asm
0x2f7f0  ldstr    aSiteoforigin// "SiteOfOrigin://"
0x2f7f5  newobj   instance void [System]System.Uri::.ctor(string)
0x2f7fa  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::Create(class [System]System.Uri)
0x2f7ff  stsfld   class [System]System.Uri System.Windows.Navigation.BaseUriHelper::_siteOfOriginBaseUri
0x2f804  ldstr    aApplication// "application://"
0x2f809  newobj   instance void [System]System.Uri::.ctor(string)
0x2f80e  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::Create(class [System]System.Uri)
0x2f813  stsfld   class [System]System.Uri System.Windows.Navigation.BaseUriHelper::_packAppBaseUri
0x2f818  ldstr    aBaseuri// "BaseUri"
0x2f81d  ldtoken  [System]System.Uri
0x2f822  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f827  ldtoken  System.Windows.Navigation.BaseUriHelper
0x2f82c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f831  ldnull
0x2f832  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object)
0x2f837  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x2f83c  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Navigation.BaseUriHelper::BaseUriProperty
0x2f841  ldsfld   class [System]System.Uri System.Windows.Navigation.BaseUriHelper::_packAppBaseUri
0x2f846  newobj   instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class [System]System.Uri>::.ctor(var<u1>)
0x2f84b  stsfld   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class [System]System.Uri> System.Windows.Navigation.BaseUriHelper::_baseUri
0x2f850  call     class [System]System.Uri System.Windows.Navigation.BaseUriHelper::get_SiteOfOriginBaseUri()
0x2f855  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::GetPackageUri(class [System]System.Uri)
0x2f85a  newobj   instance void MS.Internal.AppModel.SiteOfOriginContainer::.ctor()
0x2f85f  ldc.i4.1
0x2f860  call     void MS.Internal.IO.Packaging.PreloadedPackages::AddPackage(class [System]System.Uri uri, class [WindowsBase]System.IO.Packaging.Package package, bool threadSafe)
0x2f865  ret
```
