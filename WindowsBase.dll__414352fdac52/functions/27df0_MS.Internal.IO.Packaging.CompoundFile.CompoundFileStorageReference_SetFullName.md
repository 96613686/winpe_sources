# MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference::SetFullName

- ea: `0x27df0`
- end: `0x27e57`
- name: `MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference::SetFullName`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x27d40`

## callees

- `0x27df0`
- `0x286a0`
- `0x2c100`

## string_xrefs

- `0x27e41`: `CompoundFilePathNullEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x27df0  ldarg.1
0x27df1  brfalse.s loc_27DFB
0x27df3  ldarg.1
0x27df4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x27df9  brtrue.s loc_27E07
0x27dfb  ldarg.0
0x27dfc  ldsfld   string [mscorlib]System.String::Empty
0x27e01  stfld    string MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference::_fullName
0x27e06  ret
0x27e07  ldarg.1
0x27e08  ldsfld   string MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::PathSeparatorAsString
0x27e0d  ldc.i4.4
0x27e0e  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x27e13  brfalse.s loc_27E2A
0x27e15  ldstr    aDelimiterleadi// "DelimiterLeading"
0x27e1a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x27e1f  ldstr    aFullname// "fullName"
0x27e24  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x27e29  throw
0x27e2a  ldarg.0
0x27e2b  ldarg.1
0x27e2c  stfld    string MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference::_fullName
0x27e31  ldarg.0
0x27e32  ldfld    string MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference::_fullName
0x27e37  call     string[] MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::ConvertBackSlashPathToStringArrayPath(string backSlashPath)
0x27e3c  stloc.0
0x27e3d  ldloc.0
0x27e3e  ldlen
0x27e3f  brtrue.s loc_27E56
0x27e41  ldstr    aCompoundfilepa// "CompoundFilePathNullEmpty"
0x27e46  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x27e4b  ldstr    aFullname// "fullName"
0x27e50  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x27e55  throw
0x27e56  ret
```
