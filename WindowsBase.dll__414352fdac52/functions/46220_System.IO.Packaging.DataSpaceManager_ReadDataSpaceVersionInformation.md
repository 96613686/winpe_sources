# System.IO.Packaging.DataSpaceManager::ReadDataSpaceVersionInformation

- ea: `0x46220`
- end: `0x462c0`
- name: `System.IO.Packaging.DataSpaceManager::ReadDataSpaceVersionInformation`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x457e0`

## callees

- `0x28500`
- `0x2b140`
- `0x2b190`
- `0x2b1a0`
- `0x2c130`
- `0x44e60`
- `0x46220`
- `0x468f0`
- `0x46930`
- `0x47a00`

## string_xrefs

- `0x46277`: `InvalidTransformFeatureName`

## pseudocode

```c

```

## disassembly

```asm
0x46220  ldarg.0
0x46221  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion System.IO.Packaging.DataSpaceManager::_fileFormatVersion
0x46226  brtrue   loc_462BF
0x4622b  ldarg.1
0x4622c  ldstr    aVersion_0// "Version"
0x46231  callvirt instance bool System.IO.Packaging.StorageInfo::StreamExists(string name)
0x46236  brfalse  loc_462BF
0x4623b  ldarg.1
0x4623c  ldstr    aVersion_0// "Version"
0x46241  callvirt instance class System.IO.Packaging.StreamInfo System.IO.Packaging.StorageInfo::GetStreamInfo(string name)
0x46246  stloc.0
0x46247  ldloc.0
0x46248  ldc.i4.3
0x46249  callvirt instance class [mscorlib]System.IO.Stream System.IO.Packaging.StreamInfo::GetStream(valuetype [mscorlib]System.IO.FileMode mode)
0x4624e  stloc.1
0x4624f  ldarg.0
0x46250  ldloc.1
0x46251  call     class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.FormatVersion::LoadFromStream(class [mscorlib]System.IO.Stream stream)
0x46256  stfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion System.IO.Packaging.DataSpaceManager::_fileFormatVersion
0x4625b  call     class MS.Internal.IO.Packaging.CaseInsensitiveOrdinalStringComparer MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::get_StringCaseInsensitiveComparer()
0x46260  ldarg.0
0x46261  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion System.IO.Packaging.DataSpaceManager::_fileFormatVersion
0x46266  callvirt instance string MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_FeatureIdentifier()
0x4626b  ldsfld   string System.IO.Packaging.DataSpaceManager::DataSpaceVersionIdentifier
0x46270  callvirt instance bool [mscorlib]System.Collections.IEqualityComparer::Equals(object, object)
0x46275  brtrue.s loc_462A3
0x46277  ldstr    aInvalidtransfo// "InvalidTransformFeatureName"
0x4627c  ldc.i4.2
0x4627d  newarr   [mscorlib]System.Object
0x46282  dup
0x46283  ldc.i4.0
0x46284  ldarg.0
0x46285  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion System.IO.Packaging.DataSpaceManager::_fileFormatVersion
0x4628a  callvirt instance string MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_FeatureIdentifier()
0x4628f  stelem.ref
0x46290  dup
0x46291  ldc.i4.1
0x46292  ldsfld   string System.IO.Packaging.DataSpaceManager::DataSpaceVersionIdentifier
0x46297  stelem.ref
0x46298  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x4629d  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x462a2  throw
0x462a3  ldarg.0
0x462a4  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion System.IO.Packaging.DataSpaceManager::_fileFormatVersion
0x462a9  ldsfld   class MS.Internal.IO.Packaging.CompoundFile.VersionPair System.IO.Packaging.DataSpaceManager::DataSpaceCurrentWriterVersion
0x462ae  callvirt instance void MS.Internal.IO.Packaging.CompoundFile.FormatVersion::set_WriterVersion(class MS.Internal.IO.Packaging.CompoundFile.VersionPair value)
0x462b3  leave.s  loc_462BF
0x462b5  ldloc.1
0x462b6  brfalse.s loc_462BE
0x462b8  ldloc.1
0x462b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x462be  endfinally
0x462bf  ret
```
