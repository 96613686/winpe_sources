# MS.Internal.IO.Packaging.CompoundFile.CompoundFileStreamReference::SetFullName

- ea: `0x27cc0`
- end: `0x27d16`
- name: `MS.Internal.IO.Packaging.CompoundFile.CompoundFileStreamReference::SetFullName`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x27bb0`

## callees

- `0x27cc0`
- `0x286a0`
- `0x28800`
- `0x2c100`

## string_xrefs

- `0x27d00`: `CompoundFilePathNullEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x27cc0  ldarg.1
0x27cc1  ldstr    aFullname// "fullName"
0x27cc6  call     void MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::CheckStringAgainstNullAndEmpty(string testString, string testStringIdentifier)
0x27ccb  ldarg.1
0x27ccc  ldsfld   string MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::PathSeparatorAsString
0x27cd1  ldc.i4.4
0x27cd2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x27cd7  brfalse.s loc_27CEE
0x27cd9  ldstr    aDelimiterleadi// "DelimiterLeading"
0x27cde  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x27ce3  ldstr    aFullname// "fullName"
0x27ce8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x27ced  throw
0x27cee  ldarg.0
0x27cef  ldarg.1
0x27cf0  stfld    string MS.Internal.IO.Packaging.CompoundFile.CompoundFileStreamReference::_fullName
0x27cf5  ldarg.1
0x27cf6  call     string[] MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::ConvertBackSlashPathToStringArrayPath(string backSlashPath)
0x27cfb  stloc.0
0x27cfc  ldloc.0
0x27cfd  ldlen
0x27cfe  brtrue.s loc_27D15
0x27d00  ldstr    aCompoundfilepa// "CompoundFilePathNullEmpty"
0x27d05  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x27d0a  ldstr    aFullname// "fullName"
0x27d0f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x27d14  throw
0x27d15  ret
```
