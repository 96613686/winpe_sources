# System.Windows.Application::GetResourceStream

- ea: `0x65c0`
- end: `0x6645`
- name: `System.Windows.Application::GetResourceStream`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x65c0`
- `0x7960`
- `0x38c40`
- `0x38c70`
- `0x6bf30`

## string_xrefs

- `0x65c9`: `uriResource`
- `0x65e9`: `uriResource`
- `0x6612`: `NonPackAppAbsoluteUriNotAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x65c0  ldarg.0
0x65c1  ldnull
0x65c2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x65c7  brfalse.s loc_65D4
0x65c9  ldstr    aUriresource// "uriResource"
0x65ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x65d3  throw
0x65d4  ldarg.0
0x65d5  callvirt instance string [System]System.Uri::get_OriginalString()
0x65da  brtrue.s loc_6602
0x65dc  ldstr    aArgumentproper// "ArgumentPropertyMustNotBeNull"
0x65e1  ldc.i4.2
0x65e2  newarr   [mscorlib]System.Object
0x65e7  dup
0x65e8  ldc.i4.0
0x65e9  ldstr    aUriresource// "uriResource"
0x65ee  stelem.ref
0x65ef  dup
0x65f0  ldc.i4.1
0x65f1  ldstr    aOriginalstring// "OriginalString"
0x65f6  stelem.ref
0x65f7  call     string System.Windows.SR::Get(string id, object[] args)
0x65fc  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6601  throw
0x6602  ldarg.0
0x6603  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x6608  brfalse.s loc_6622
0x660a  ldarg.0
0x660b  call     bool [PresentationCore]System.Windows.Navigation.BaseUriHelper::IsPackApplicationUri(class [System]System.Uri)
0x6610  brtrue.s loc_6622
0x6612  ldstr    aNonpackappabso// "NonPackAppAbsoluteUriNotAllowed"
0x6617  call     string System.Windows.SR::Get(string id)
0x661c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6621  throw
0x6622  ldarg.0
0x6623  call     class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Application::GetResourceOrContentPart(class [System]System.Uri uri)
0x6628  isinst   MS.Internal.AppModel.ResourcePart
0x662d  stloc.0
0x662e  ldloc.0
0x662f  brfalse.s loc_6643
0x6631  ldloc.0
0x6632  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream()
0x6637  ldloc.0
0x6638  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0x663d  newobj   instance void System.Windows.Resources.StreamResourceInfo::.ctor(class [mscorlib]System.IO.Stream stream, string contentType)
0x6642  ret
0x6643  ldnull
0x6644  ret
```
