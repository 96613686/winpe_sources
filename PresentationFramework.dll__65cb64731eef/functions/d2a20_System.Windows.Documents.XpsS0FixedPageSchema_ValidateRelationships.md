# System.Windows.Documents.XpsS0FixedPageSchema::ValidateRelationships

- ea: `0xd2a20`
- end: `0xd2db7`
- name: `System.Windows.Documents.XpsS0FixedPageSchema::ValidateRelationships`
- size: `919`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x38c40`
- `0xd2a20`

## string_xrefs

- `0xd2a2f`: `http://schemas.microsoft.com/xps/2005/06/printticket`
- `0xd2acb`: `http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail`
- `0xd2cf8`: `http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail`
- `0xd2b9b`: `http://schemas.microsoft.com/xps/2005/06/restricted-font`
- `0xd2c51`: `http://schemas.microsoft.com/xps/2005/06/discard-control`

## pseudocode

```c

```

## disassembly

```asm
0xd2a20  ldarga.s 1
0xd2a22  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [WindowsBase]System.IO.Packaging.Package>::get_Value()
0xd2a27  ldarg.3
0xd2a28  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0xd2a2d  stloc.0
0xd2a2e  ldloc.0
0xd2a2f  ldstr    aHttpSchemasMic_6// "http://schemas.microsoft.com/xps/2005/0"...
0xd2a34  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.PackagePart::GetRelationshipsByType(string)
0xd2a39  stloc.1
0xd2a3a  ldc.i4.0
0xd2a3b  stloc.2
0xd2a3c  ldloc.1
0xd2a3d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0xd2a42  stloc.3
0xd2a43  br.s     loc_D2AB6
0xd2a45  ldloc.3
0xd2a46  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0xd2a4b  stloc.s  4
0xd2a4d  ldloc.2
0xd2a4e  ldc.i4.1
0xd2a4f  add
0xd2a50  stloc.2
0xd2a51  ldloc.2
0xd2a52  ldc.i4.1
0xd2a53  ble.s    loc_D2A65
0xd2a55  ldstr    aXpsvalidatingl_0// "XpsValidatingLoaderMoreThanOnePrintTick"...
0xd2a5a  call     string System.Windows.SR::Get(string id)
0xd2a5f  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(string)
0xd2a64  throw
0xd2a65  ldarg.3
0xd2a66  ldloc.s  4
0xd2a68  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0xd2a6d  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0xd2a72  stloc.s  5
0xd2a74  ldarg.2
0xd2a75  ldloc.s  5
0xd2a77  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::Create(class [System]System.Uri, class [System]System.Uri)
0xd2a7c  stloc.s  6
0xd2a7e  ldarga.s 1
0xd2a80  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [WindowsBase]System.IO.Packaging.Package>::get_Value()
0xd2a85  ldloc.s  5
0xd2a87  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0xd2a8c  stloc.s  7
0xd2a8e  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_printTicketContentType
0xd2a93  ldloc.s  7
0xd2a95  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0xd2a9a  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2a9f  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2aa4  brtrue.s loc_D2AB6
0xd2aa6  ldstr    aXpsvalidatingl_1// "XpsValidatingLoaderPrintTicketHasIncorr"...
0xd2aab  call     string System.Windows.SR::Get(string id)
0xd2ab0  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(string)
0xd2ab5  throw
0xd2ab6  ldloc.3
0xd2ab7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd2abc  brtrue.s loc_D2A45
0xd2abe  leave.s  loc_D2ACA
0xd2ac0  ldloc.3
0xd2ac1  brfalse.s loc_D2AC9
0xd2ac3  ldloc.3
0xd2ac4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2ac9  endfinally
0xd2aca  ldloc.0
0xd2acb  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/packa"...
0xd2ad0  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.PackagePart::GetRelationshipsByType(string)
0xd2ad5  stloc.1
0xd2ad6  ldc.i4.0
0xd2ad7  stloc.2
0xd2ad8  ldloc.1
0xd2ad9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0xd2ade  stloc.s  8
0xd2ae0  br       loc_D2B6F
0xd2ae5  ldloc.s  8
0xd2ae7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0xd2aec  stloc.s  9
0xd2aee  ldloc.2
0xd2aef  ldc.i4.1
0xd2af0  add
0xd2af1  stloc.2
0xd2af2  ldloc.2
0xd2af3  ldc.i4.1
0xd2af4  ble.s    loc_D2B06
0xd2af6  ldstr    aXpsvalidatingl_2// "XpsValidatingLoaderMoreThanOneThumbnail"...
0xd2afb  call     string System.Windows.SR::Get(string id)
0xd2b00  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(string)
0xd2b05  throw
0xd2b06  ldarg.3
0xd2b07  ldloc.s  9
0xd2b09  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0xd2b0e  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0xd2b13  stloc.s  0xA
0xd2b15  ldarg.2
0xd2b16  ldloc.s  0xA
0xd2b18  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::Create(class [System]System.Uri, class [System]System.Uri)
0xd2b1d  stloc.s  0xB
0xd2b1f  ldarga.s 1
0xd2b21  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [WindowsBase]System.IO.Packaging.Package>::get_Value()
0xd2b26  ldloc.s  0xA
0xd2b28  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0xd2b2d  stloc.s  0xC
0xd2b2f  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_jpgContentType
0xd2b34  ldloc.s  0xC
0xd2b36  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0xd2b3b  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2b40  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2b45  brtrue.s loc_D2B6F
0xd2b47  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_pngContentType
0xd2b4c  ldloc.s  0xC
0xd2b4e  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0xd2b53  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2b58  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2b5d  brtrue.s loc_D2B6F
0xd2b5f  ldstr    aXpsvalidatingl_3// "XpsValidatingLoaderThumbnailHasIncorrec"...
0xd2b64  call     string System.Windows.SR::Get(string id)
0xd2b69  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(string)
0xd2b6e  throw
0xd2b6f  ldloc.s  8
0xd2b71  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd2b76  brtrue   loc_D2AE5
0xd2b7b  leave.s  loc_D2B89
0xd2b7d  ldloc.s  8
0xd2b7f  brfalse.s loc_D2B88
0xd2b81  ldloc.s  8
0xd2b83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2b88  endfinally
0xd2b89  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_fixedDocumentContentType
0xd2b8e  ldarg.s  4
0xd2b90  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2b95  brfalse  loc_D2C39
0xd2b9a  ldloc.0
0xd2b9b  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/xps/2005/0"...
0xd2ba0  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.PackagePart::GetRelationshipsByType(string)
0xd2ba5  stloc.1
0xd2ba6  ldloc.1
0xd2ba7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0xd2bac  stloc.s  0xD
0xd2bae  br.s     loc_D2C22
0xd2bb0  ldloc.s  0xD
0xd2bb2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0xd2bb7  stloc.s  0xE
0xd2bb9  ldarg.3
0xd2bba  ldloc.s  0xE
0xd2bbc  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0xd2bc1  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0xd2bc6  stloc.s  0xF
0xd2bc8  ldarg.2
0xd2bc9  ldloc.s  0xF
0xd2bcb  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::Create(class [System]System.Uri, class [System]System.Uri)
0xd2bd0  stloc.s  0x10
0xd2bd2  ldarga.s 1
0xd2bd4  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [WindowsBase]System.IO.Packaging.Package>::get_Value()
0xd2bd9  ldloc.s  0xF
0xd2bdb  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0xd2be0  stloc.s  0x11
0xd2be2  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_fontContentType
0xd2be7  ldloc.s  0x11
0xd2be9  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0xd2bee  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2bf3  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2bf8  brtrue.s loc_D2C22
0xd2bfa  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_obfuscatedContentType
0xd2bff  ldloc.s  0x11
0xd2c01  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0xd2c06  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2c0b  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2c10  brtrue.s loc_D2C22
0xd2c12  ldstr    aXpsvalidatingl_4// "XpsValidatingLoaderRestrictedFontHasInc"...
0xd2c17  call     string System.Windows.SR::Get(string id)
0xd2c1c  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(string)
0xd2c21  throw
0xd2c22  ldloc.s  0xD
0xd2c24  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd2c29  brtrue.s loc_D2BB0
0xd2c2b  leave.s  loc_D2C39
0xd2c2d  ldloc.s  0xD
0xd2c2f  brfalse.s loc_D2C38
0xd2c31  ldloc.s  0xD
0xd2c33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2c38  endfinally
0xd2c39  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_fixedDocumentSequenceContentType
0xd2c3e  ldarg.s  4
0xd2c40  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2c45  brfalse  loc_D2DB6
0xd2c4a  ldarga.s 1
0xd2c4c  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [WindowsBase]System.IO.Packaging.Package>::get_Value()
0xd2c51  ldstr    aHttpSchemasMic_8// "http://schemas.microsoft.com/xps/2005/0"...
0xd2c56  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.Package::GetRelationshipsByType(string)
0xd2c5b  stloc.1
0xd2c5c  ldc.i4.0
0xd2c5d  stloc.2
0xd2c5e  ldloc.1
0xd2c5f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0xd2c64  stloc.s  0x12
0xd2c66  br.s     loc_D2CDA
0xd2c68  ldloc.s  0x12
0xd2c6a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0xd2c6f  stloc.s  0x13
0xd2c71  ldloc.2
0xd2c72  ldc.i4.1
0xd2c73  add
0xd2c74  stloc.2
0xd2c75  ldloc.2
0xd2c76  ldc.i4.1
0xd2c77  ble.s    loc_D2C89
0xd2c79  ldstr    aXpsvalidatingl_5// "XpsValidatingLoaderMoreThanOneDiscardCo"...
0xd2c7e  call     string System.Windows.SR::Get(string id)
0xd2c83  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(string)
0xd2c88  throw
0xd2c89  ldarg.3
0xd2c8a  ldloc.s  0x13
0xd2c8c  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0xd2c91  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0xd2c96  stloc.s  0x14
0xd2c98  ldarg.2
0xd2c99  ldloc.s  0x14
0xd2c9b  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::Create(class [System]System.Uri, class [System]System.Uri)
0xd2ca0  stloc.s  0x15
0xd2ca2  ldarga.s 1
0xd2ca4  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [WindowsBase]System.IO.Packaging.Package>::get_Value()
0xd2ca9  ldloc.s  0x14
0xd2cab  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0xd2cb0  stloc.s  0x16
0xd2cb2  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_discardControlContentType
0xd2cb7  ldloc.s  0x16
0xd2cb9  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0xd2cbe  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2cc3  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2cc8  brtrue.s loc_D2CDA
0xd2cca  ldstr    aXpsvalidatingl_6// "XpsValidatingLoaderDiscardControlHasInc"...
0xd2ccf  call     string System.Windows.SR::Get(string id)
0xd2cd4  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(string)
0xd2cd9  throw
0xd2cda  ldloc.s  0x12
0xd2cdc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd2ce1  brtrue.s loc_D2C68
0xd2ce3  leave.s  loc_D2CF1
0xd2ce5  ldloc.s  0x12
0xd2ce7  brfalse.s loc_D2CF0
0xd2ce9  ldloc.s  0x12
0xd2ceb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2cf0  endfinally
0xd2cf1  ldarga.s 1
0xd2cf3  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [WindowsBase]System.IO.Packaging.Package>::get_Value()
0xd2cf8  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/packa"...
0xd2cfd  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.Package::GetRelationshipsByType(string)
0xd2d02  stloc.1
0xd2d03  ldc.i4.0
0xd2d04  stloc.2
0xd2d05  ldloc.1
0xd2d06  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0xd2d0b  stloc.s  0x17
0xd2d0d  br       loc_D2D9C
0xd2d12  ldloc.s  0x17
0xd2d14  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0xd2d19  stloc.s  0x18
0xd2d1b  ldloc.2
0xd2d1c  ldc.i4.1
0xd2d1d  add
0xd2d1e  stloc.2
0xd2d1f  ldloc.2
0xd2d20  ldc.i4.1
0xd2d21  ble.s    loc_D2D33
0xd2d23  ldstr    aXpsvalidatingl_7// "XpsValidatingLoaderMoreThanOneThumbnail"...
0xd2d28  call     string System.Windows.SR::Get(string id)
0xd2d2d  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(string)
0xd2d32  throw
0xd2d33  ldarg.3
0xd2d34  ldloc.s  0x18
0xd2d36  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0xd2d3b  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0xd2d40  stloc.s  0x19
0xd2d42  ldarg.2
0xd2d43  ldloc.s  0x19
0xd2d45  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::Create(class [System]System.Uri, class [System]System.Uri)
0xd2d4a  stloc.s  0x1A
0xd2d4c  ldarga.s 1
0xd2d4e  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [WindowsBase]System.IO.Packaging.Package>::get_Value()
0xd2d53  ldloc.s  0x19
0xd2d55  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0xd2d5a  stloc.s  0x1B
0xd2d5c  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_jpgContentType
0xd2d61  ldloc.s  0x1B
0xd2d63  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0xd2d68  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2d6d  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2d72  brtrue.s loc_D2D9C
0xd2d74  ldsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_pngContentType
0xd2d79  ldloc.s  0x1B
0xd2d7b  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0xd2d80  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2d85  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0xd2d8a  brtrue.s loc_D2D9C
0xd2d8c  ldstr    aXpsvalidatingl_3// "XpsValidatingLoaderThumbnailHasIncorrec"...
0xd2d91  call     string System.Windows.SR::Get(string id)
0xd2d96  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(string)
0xd2d9b  throw
0xd2d9c  ldloc.s  0x17
0xd2d9e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd2da3  brtrue   loc_D2D12
0xd2da8  leave.s  loc_D2DB6
  ... truncated ...
```
