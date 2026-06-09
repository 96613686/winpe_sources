# System.Windows.Application::GetRemoteStream

- ea: `0x66e0`
- end: `0x67c7`
- name: `System.Windows.Application::GetRemoteStream`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x66e0`
- `0x79c0`
- `0x38c40`
- `0x38c70`
- `0x6bf30`
- `0x24e920`

## string_xrefs

- `0x66eb`: `uriRemote`
- `0x670b`: `uriRemote`
- `0x6739`: `NonPackSooAbsoluteUriNotAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x66e0  ldnull
0x66e1  stloc.0
0x66e2  ldarg.0
0x66e3  ldnull
0x66e4  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x66e9  brfalse.s loc_66F6
0x66eb  ldstr    aUriremote// "uriRemote"
0x66f0  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x66f5  throw
0x66f6  ldarg.0
0x66f7  callvirt instance string [System]System.Uri::get_OriginalString()
0x66fc  brtrue.s loc_6724
0x66fe  ldstr    aArgumentproper// "ArgumentPropertyMustNotBeNull"
0x6703  ldc.i4.2
0x6704  newarr   [mscorlib]System.Object
0x6709  dup
0x670a  ldc.i4.0
0x670b  ldstr    aUriremote// "uriRemote"
0x6710  stelem.ref
0x6711  dup
0x6712  ldc.i4.1
0x6713  ldstr    aOriginalstring// "OriginalString"
0x6718  stelem.ref
0x6719  call     string System.Windows.SR::Get(string id, object[] args)
0x671e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6723  throw
0x6724  ldarg.0
0x6725  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x672a  brfalse.s loc_6749
0x672c  call     class [System]System.Uri [PresentationCore]System.Windows.Navigation.BaseUriHelper::get_SiteOfOriginBaseUri()
0x6731  ldarg.0
0x6732  callvirt instance bool [System]System.Uri::IsBaseOf(class [System]System.Uri)
0x6737  brtrue.s loc_6749
0x6739  ldstr    aNonpacksooabso// "NonPackSooAbsoluteUriNotAllowed"
0x673e  call     string System.Windows.SR::Get(string id)
0x6743  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6748  throw
0x6749  call     class [System]System.Uri [PresentationCore]System.Windows.Navigation.BaseUriHelper::get_SiteOfOriginBaseUri()
0x674e  ldarg.0
0x674f  call     class [System]System.Uri MS.Internal.Utility.BindUriHelper::GetResolvedUri(class [System]System.Uri baseUri, class [System]System.Uri orgUri)
0x6754  stloc.1
0x6755  ldloc.1
0x6756  ldloca.s 2
0x6758  ldloca.s 3
0x675a  call     void [WindowsBase]System.IO.Packaging.PackUriHelper::ValidateAndGetPackUriComponents(class [System]System.Uri, class [System]System.Uri&, class [System]System.Uri&)
0x675f  ldloc.2
0x6760  call     class [WindowsBase]System.IO.Packaging.Package System.Windows.Application::GetResourcePackage(class [System]System.Uri packageUri)
0x6765  castclass [PresentationCore]MS.Internal.AppModel.SiteOfOriginContainer
0x676a  stloc.s  4
0x676c  ldloc.s  4
0x676e  stloc.s  6
0x6770  ldc.i4.0
0x6771  stloc.s  7
0x6773  ldloc.s  6
0x6775  ldloca.s 7
0x6777  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x677c  ldloc.s  4
0x677e  ldloc.3
0x677f  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0x6784  isinst   [PresentationCore]MS.Internal.AppModel.SiteOfOriginPart
0x6789  stloc.0
0x678a  leave.s  loc_6798
0x678c  ldloc.s  7
0x678e  brfalse.s loc_6797
0x6790  ldloc.s  6
0x6792  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x6797  endfinally
0x6798  ldnull
0x6799  stloc.s  5
0x679b  ldloc.0
0x679c  brfalse.s loc_67B3
0x679e  ldloc.0
0x679f  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream()
0x67a4  stloc.s  5
0x67a6  ldloc.s  5
0x67a8  brtrue.s loc_67AC
0x67aa  ldnull
0x67ab  stloc.0
0x67ac  leave.s  loc_67B3
0x67ae  pop
0x67af  ldnull
0x67b0  stloc.0
0x67b1  leave.s  loc_67B3
0x67b3  ldloc.s  5
0x67b5  brfalse.s loc_67C5
0x67b7  ldloc.s  5
0x67b9  ldloc.0
0x67ba  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0x67bf  newobj   instance void System.Windows.Resources.StreamResourceInfo::.ctor(class [mscorlib]System.IO.Stream stream, string contentType)
0x67c4  ret
0x67c5  ldnull
0x67c6  ret
```
