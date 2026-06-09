# System.IO.Packaging.PackUriHelper::GetExceptionIfPartUriInvalid

- ea: `0x4abe0`
- end: `0x4acb0`
- name: `System.IO.Packaging.PackUriHelper::GetExceptionIfPartUriInvalid`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x4a9e0`
- `0x4aa10`

## callees

- `0x2c100`
- `0x4abe0`
- `0x4acc0`
- `0x4acf0`
- `0x4ad20`
- `0x4ad60`
- `0x4adb0`

## string_xrefs

- `0x4abf0`: `partUri`
- `0x4ac1d`: `PartUriIsEmpty`
- `0x4ac38`: `PartUriShouldStartWithForwardSlash`
- `0x4ac9b`: `InvalidPartUri`

## pseudocode

```c

```

## disassembly

```asm
0x4abe0  ldarg.1
0x4abe1  ldsfld   string [mscorlib]System.String::Empty
0x4abe6  stind.ref
0x4abe7  ldarg.0
0x4abe8  ldnull
0x4abe9  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4abee  brfalse.s loc_4ABFB
0x4abf0  ldstr    aParturi// "partUri"
0x4abf5  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4abfa  ret
0x4abfb  ldnull
0x4abfc  stloc.0
0x4abfd  ldarg.0
0x4abfe  call     class [mscorlib]System.ArgumentException System.IO.Packaging.PackUriHelper::GetExceptionIfAbsoluteUri(class [System]System.Uri uri)
0x4ac03  stloc.0
0x4ac04  ldloc.0
0x4ac05  brfalse.s loc_4AC09
0x4ac07  ldloc.0
0x4ac08  ret
0x4ac09  ldarg.0
0x4ac0a  call     string System.IO.Packaging.PackUriHelper::GetStringForPartUriFromAnyUri(class [System]System.Uri partUri)
0x4ac0f  stloc.1
0x4ac10  ldloc.1
0x4ac11  ldsfld   string [mscorlib]System.String::Empty
0x4ac16  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ac1b  brfalse.s loc_4AC2D
0x4ac1d  ldstr    aParturiisempty// "PartUriIsEmpty"
0x4ac22  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4ac27  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ac2c  ret
0x4ac2d  ldloc.1
0x4ac2e  ldc.i4.0
0x4ac2f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4ac34  ldc.i4.s 0x2F
0x4ac36  beq.s    loc_4AC48
0x4ac38  ldstr    aParturishoulds// "PartUriShouldStartWithForwardSlash"
0x4ac3d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4ac42  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ac47  ret
0x4ac48  ldloc.1
0x4ac49  call     class [mscorlib]System.ArgumentException System.IO.Packaging.PackUriHelper::GetExceptionIfPartNameStartsWithTwoSlashes(string partName)
0x4ac4e  stloc.0
0x4ac4f  ldloc.0
0x4ac50  brfalse.s loc_4AC54
0x4ac52  ldloc.0
0x4ac53  ret
0x4ac54  ldloc.1
0x4ac55  call     class [mscorlib]System.ArgumentException System.IO.Packaging.PackUriHelper::GetExceptionIfPartNameEndsWithSlash(string partName)
0x4ac5a  stloc.0
0x4ac5b  ldloc.0
0x4ac5c  brfalse.s loc_4AC60
0x4ac5e  ldloc.0
0x4ac5f  ret
0x4ac60  ldloc.1
0x4ac61  call     class [mscorlib]System.ArgumentException System.IO.Packaging.PackUriHelper::GetExceptionIfFragmentPresent(string partName)
0x4ac66  stloc.0
0x4ac67  ldloc.0
0x4ac68  brfalse.s loc_4AC6C
0x4ac6a  ldloc.0
0x4ac6b  ret
0x4ac6c  ldsfld   class [System]System.Uri System.IO.Packaging.PackUriHelper::_defaultUri
0x4ac71  ldloc.1
0x4ac72  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x4ac77  ldc.i4   0x40000010
0x4ac7c  ldc.i4.1
0x4ac7d  call     instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x4ac82  stloc.2
0x4ac83  ldarg.0
0x4ac84  callvirt instance string [System]System.Uri::get_OriginalString()
0x4ac89  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4ac8e  ldloc.2
0x4ac8f  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4ac94  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x4ac99  brfalse.s loc_4ACAB
0x4ac9b  ldstr    aInvalidparturi// "InvalidPartUri"
0x4aca0  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4aca5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4acaa  ret
0x4acab  ldarg.1
0x4acac  ldloc.1
0x4acad  stind.ref
0x4acae  ldnull
0x4acaf  ret
```
