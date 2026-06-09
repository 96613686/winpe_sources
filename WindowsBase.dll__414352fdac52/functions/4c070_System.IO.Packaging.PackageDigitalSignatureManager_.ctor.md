# System.IO.Packaging.PackageDigitalSignatureManager::.ctor

- ea: `0x4c070`
- end: `0x4c0f8`
- name: `System.IO.Packaging.PackageDigitalSignatureManager::.ctor`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x23e40`
- `0x25900`
- `0x4c050`
- `0x4c070`

## string_xrefs

- `0x4c0d3`: `http://www.w3.org/TR/2001/REC-xml-c14n-20010315`
- `0x4c0ed`: `http://www.w3.org/TR/2001/REC-xml-c14n-20010315`

## pseudocode

```c

```

## disassembly

```asm
0x4c070  ldarg.0
0x4c071  ldsfld   class [System]System.Uri System.IO.Packaging.PackageDigitalSignatureManager::_defaultOriginPartName
0x4c076  stfld    class [System]System.Uri System.IO.Packaging.PackageDigitalSignatureManager::_originPartName
0x4c07b  ldarg.0
0x4c07c  call     string System.IO.Packaging.PackageDigitalSignatureManager::get_DefaultHashAlgorithm()
0x4c081  stfld    string System.IO.Packaging.PackageDigitalSignatureManager::_hashAlgorithmString
0x4c086  ldarg.0
0x4c087  call     string MS.Internal.IO.Packaging.XmlSignatureProperties::get_DefaultDateTimeFormat()
0x4c08c  stfld    string System.IO.Packaging.PackageDigitalSignatureManager::_signatureTimeFormat
0x4c091  ldarg.0
0x4c092  call     instance void [mscorlib]System.Object::.ctor()
0x4c097  ldarg.1
0x4c098  brtrue.s loc_4C0A5
0x4c09a  ldstr    aPackage// "package"
0x4c09f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4c0a4  throw
0x4c0a5  ldarg.0
0x4c0a6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4c0ab  stfld    native int System.IO.Packaging.PackageDigitalSignatureManager::_parentWindow
0x4c0b0  ldarg.0
0x4c0b1  ldarg.1
0x4c0b2  stfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c0b7  ldarg.0
0x4c0b8  ldc.i4.4
0x4c0b9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(int32)
0x4c0be  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.IO.Packaging.PackageDigitalSignatureManager::_transformDictionary
0x4c0c3  ldarg.0
0x4c0c4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.IO.Packaging.PackageDigitalSignatureManager::_transformDictionary
0x4c0c9  ldsfld   class MS.Internal.ContentType MS.Internal.IO.Packaging.PackagingUtilities::RelationshipPartContentType
0x4c0ce  callvirt instance string [mscorlib]System.Object::ToString()
0x4c0d3  ldstr    aHttpWwwW3OrgTr// "http://www.w3.org/TR/2001/REC-xml-c14n-"...
0x4c0d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x4c0dd  ldarg.0
0x4c0de  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.IO.Packaging.PackageDigitalSignatureManager::_transformDictionary
0x4c0e3  call     class MS.Internal.ContentType MS.Internal.IO.Packaging.XmlDigitalSignatureProcessor::get_ContentType()
0x4c0e8  callvirt instance string [mscorlib]System.Object::ToString()
0x4c0ed  ldstr    aHttpWwwW3OrgTr// "http://www.w3.org/TR/2001/REC-xml-c14n-"...
0x4c0f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x4c0f7  ret
```
