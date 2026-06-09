# MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::WriteAttempt

- ea: `0x2ad80`
- end: `0x2ae3c`
- name: `MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::WriteAttempt`
- size: `188`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2a880`
- `0x2a8d0`
- `0x2a910`
- `0x2ab40`
- `0x2ab80`
- `0x2ac00`

## callees

- `0x2aaf0`
- `0x2ad80`
- `0x2aee0`
- `0x2af70`
- `0x2b160`
- `0x2b170`
- `0x2b2b0`
- `0x2b4e0`
- `0x2c130`
- `0x44e60`

## string_xrefs

- `0x2adc8`: `UpdaterVersionError`

## pseudocode

```c

```

## disassembly

```asm
0x2ad80  ldarg.0
0x2ad81  call     instance void MS.Internal.IO.Packaging.CompoundFile.VersionedStream::CheckDisposed()
0x2ad86  ldarg.0
0x2ad87  ldfld    bool MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_writeOccurred
0x2ad8c  brtrue   loc_2AE3B
0x2ad91  ldarg.0
0x2ad92  call     instance void MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::EnsureParsed()
0x2ad97  ldarg.0
0x2ad98  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2ad9d  brtrue.s loc_2ADB0
0x2ad9f  ldarg.0
0x2ada0  ldarg.0
0x2ada1  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_codeVersion
0x2ada6  call     instance void MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::PersistVersion(class MS.Internal.IO.Packaging.CompoundFile.FormatVersion version)
0x2adab  br       loc_2AE34
0x2adb0  ldarg.0
0x2adb1  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2adb6  ldarg.0
0x2adb7  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_codeVersion
0x2adbc  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.VersionPair MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_UpdaterVersion()
0x2adc1  callvirt instance bool MS.Internal.IO.Packaging.CompoundFile.FormatVersion::IsUpdatableBy(class MS.Internal.IO.Packaging.CompoundFile.VersionPair version)
0x2adc6  brtrue.s loc_2ADF5
0x2adc8  ldstr    aUpdaterversion// "UpdaterVersionError"
0x2adcd  ldc.i4.2
0x2adce  newarr   [mscorlib]System.Object
0x2add3  dup
0x2add4  ldc.i4.0
0x2add5  ldarg.0
0x2add6  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2addb  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.VersionPair MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_UpdaterVersion()
0x2ade0  stelem.ref
0x2ade1  dup
0x2ade2  ldc.i4.1
0x2ade3  ldarg.0
0x2ade4  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_codeVersion
0x2ade9  stelem.ref
0x2adea  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x2adef  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x2adf4  throw
0x2adf5  ldarg.0
0x2adf6  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_codeVersion
0x2adfb  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.VersionPair MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_UpdaterVersion()
0x2ae00  ldarg.0
0x2ae01  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2ae06  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.VersionPair MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_UpdaterVersion()
0x2ae0b  call     bool MS.Internal.IO.Packaging.CompoundFile.VersionPair::op_Inequality(class MS.Internal.IO.Packaging.CompoundFile.VersionPair v1, class MS.Internal.IO.Packaging.CompoundFile.VersionPair v2)
0x2ae10  brfalse.s loc_2AE34
0x2ae12  ldarg.0
0x2ae13  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2ae18  ldarg.0
0x2ae19  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_codeVersion
0x2ae1e  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.VersionPair MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_UpdaterVersion()
0x2ae23  callvirt instance void MS.Internal.IO.Packaging.CompoundFile.FormatVersion::set_UpdaterVersion(class MS.Internal.IO.Packaging.CompoundFile.VersionPair value)
0x2ae28  ldarg.0
0x2ae29  ldarg.0
0x2ae2a  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2ae2f  call     instance void MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::PersistVersion(class MS.Internal.IO.Packaging.CompoundFile.FormatVersion version)
0x2ae34  ldarg.0
0x2ae35  ldc.i4.1
0x2ae36  stfld    bool MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_writeOccurred
0x2ae3b  ret
```
