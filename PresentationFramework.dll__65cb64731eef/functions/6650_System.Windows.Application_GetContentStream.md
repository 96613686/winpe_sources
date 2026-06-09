# System.Windows.Application::GetContentStream

- ea: `0x6650`
- end: `0x66d5`
- name: `System.Windows.Application::GetContentStream`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x6650`
- `0x7960`
- `0x38c40`
- `0x38c70`
- `0x6bf30`

## string_xrefs

- `0x66a2`: `NonPackAppAbsoluteUriNotAllowed`
- `0x6659`: `uriContent`
- `0x6679`: `uriContent`

## pseudocode

```c

```

## disassembly

```asm
0x6650  ldarg.0
0x6651  ldnull
0x6652  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x6657  brfalse.s loc_6664
0x6659  ldstr    aUricontent// "uriContent"
0x665e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6663  throw
0x6664  ldarg.0
0x6665  callvirt instance string [System]System.Uri::get_OriginalString()
0x666a  brtrue.s loc_6692
0x666c  ldstr    aArgumentproper// "ArgumentPropertyMustNotBeNull"
0x6671  ldc.i4.2
0x6672  newarr   [mscorlib]System.Object
0x6677  dup
0x6678  ldc.i4.0
0x6679  ldstr    aUricontent// "uriContent"
0x667e  stelem.ref
0x667f  dup
0x6680  ldc.i4.1
0x6681  ldstr    aOriginalstring// "OriginalString"
0x6686  stelem.ref
0x6687  call     string System.Windows.SR::Get(string id, object[] args)
0x668c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6691  throw
0x6692  ldarg.0
0x6693  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x6698  brfalse.s loc_66B2
0x669a  ldarg.0
0x669b  call     bool [PresentationCore]System.Windows.Navigation.BaseUriHelper::IsPackApplicationUri(class [System]System.Uri)
0x66a0  brtrue.s loc_66B2
0x66a2  ldstr    aNonpackappabso// "NonPackAppAbsoluteUriNotAllowed"
0x66a7  call     string System.Windows.SR::Get(string id)
0x66ac  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x66b1  throw
0x66b2  ldarg.0
0x66b3  call     class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Application::GetResourceOrContentPart(class [System]System.Uri uri)
0x66b8  isinst   MS.Internal.AppModel.ContentFilePart
0x66bd  stloc.0
0x66be  ldloc.0
0x66bf  brfalse.s loc_66D3
0x66c1  ldloc.0
0x66c2  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream()
0x66c7  ldloc.0
0x66c8  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0x66cd  newobj   instance void System.Windows.Resources.StreamResourceInfo::.ctor(class [mscorlib]System.IO.Stream stream, string contentType)
0x66d2  ret
0x66d3  ldnull
0x66d4  ret
```
