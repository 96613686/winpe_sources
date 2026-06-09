# System.IO.Packaging.PackUriHelper::CreatePartUri

- ea: `0x4a5c0`
- end: `0x4a630`
- name: `System.IO.Packaging.PackUriHelper::CreatePartUri`
- size: `112`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x22760`
- `0x4a410`
- `0x4c170`
- `0x4cc00`
- `0x4ce70`

## callees

- `0x2c100`
- `0x4a5c0`
- `0x4acb0`
- `0x4ace0`
- `0x4ad10`
- `0x4ad50`
- `0x4adb0`
- `0x5a840`

## string_xrefs

- `0x4a5c9`: `partUri`
- `0x4a613`: `PartUriIsEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x4a5c0  ldarg.0
0x4a5c1  ldnull
0x4a5c2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a5c7  brfalse.s loc_4A5D4
0x4a5c9  ldstr    aParturi// "partUri"
0x4a5ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a5d3  throw
0x4a5d4  ldarg.0
0x4a5d5  call     void System.IO.Packaging.PackUriHelper::ThrowIfAbsoluteUri(class [System]System.Uri uri)
0x4a5da  ldarg.0
0x4a5db  ldc.i4   0x80000000
0x4a5e0  ldc.i4.3
0x4a5e1  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x4a5e6  stloc.0
0x4a5e7  ldloc.0
0x4a5e8  call     void System.IO.Packaging.PackUriHelper::ThrowIfPartNameStartsWithTwoSlashes(string partName)
0x4a5ed  ldloc.0
0x4a5ee  call     void System.IO.Packaging.PackUriHelper::ThrowIfFragmentPresent(string partName)
0x4a5f3  ldsfld   class [System]System.Uri System.IO.Packaging.PackUriHelper::_defaultUri
0x4a5f8  ldarg.0
0x4a5f9  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x4a5fe  stloc.1
0x4a5ff  ldloc.1
0x4a600  call     string System.IO.Packaging.PackUriHelper::GetStringForPartUriFromAnyUri(class [System]System.Uri partUri)
0x4a605  stloc.2
0x4a606  ldloc.2
0x4a607  ldsfld   string [mscorlib]System.String::Empty
0x4a60c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4a611  brfalse.s loc_4A623
0x4a613  ldstr    aParturiisempty// "PartUriIsEmpty"
0x4a618  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4a61d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4a622  throw
0x4a623  ldloc.2
0x4a624  call     void System.IO.Packaging.PackUriHelper::ThrowIfPartNameEndsWithSlash(string partName)
0x4a629  ldloc.2
0x4a62a  newobj   instance void ValidatedPartUri::.ctor(string partUriString)
0x4a62f  ret
```
