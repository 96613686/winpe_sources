# System.Web.Configuration.RemoteWebConfigurationHostServer::WriteData

- ea: `0x154ce0`
- end: `0x154ea7`
- name: `System.Web.Configuration.RemoteWebConfigurationHostServer::WriteData`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x30220`
- `0x34f20`
- `0x34fa0`
- `0x154ce0`
- `0x155140`
- `0x155190`
- `0x1551c0`

## string_xrefs

- `0x154ce6`: `.config`
- `0x154cf3`: `Can_not_access_files_other_than_config`
- `0x154d39`: `File_changed_since_read`
- `0x154d6e`: `File_is_read_only`
- `0x154da9`: `Unable_to_create_temp_file`

## pseudocode

```c

```

## disassembly

```asm
0x154ce0  ldarg.1
0x154ce1  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x154ce6  ldstr    aConfig_1// ".config"
0x154ceb  ldc.i4.4
0x154cec  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x154cf1  brtrue.s loc_154D03
0x154cf3  ldstr    aCanNotAccessFi// "Can_not_access_files_other_than_config"
0x154cf8  call     string System.Web.SR::GetString(string name)
0x154cfd  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x154d02  throw
0x154d03  ldarg.1
0x154d04  call     bool [mscorlib]System.IO.File::Exists(string)
0x154d09  stloc.0
0x154d0a  ldnull
0x154d0b  stloc.1
0x154d0c  ldc.i4   0x80
0x154d11  stloc.2
0x154d12  ldnull
0x154d13  stloc.3
0x154d14  ldnull
0x154d15  stloc.s  4
0x154d17  ldnull
0x154d18  stloc.s  5
0x154d1a  ldc.i4.0
0x154d1b  conv.i8
0x154d1c  stloc.s  6
0x154d1e  ldc.i4.0
0x154d1f  conv.i8
0x154d20  stloc.s  7
0x154d22  ldloc.0
0x154d23  brfalse.s loc_154D53
0x154d25  ldarg.1
0x154d26  call     valuetype [mscorlib]System.DateTime [mscorlib]System.IO.File::GetLastWriteTimeUtc(string)
0x154d2b  stloc.s  8
0x154d2d  ldloca.s 8
0x154d2f  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x154d34  ldarg.s  4
0x154d36  ldind.i8
0x154d37  ble.s    loc_154D53
0x154d39  ldstr    aFileChangedSin// "File_changed_since_read"
0x154d3e  ldc.i4.1
0x154d3f  newarr   [mscorlib]System.Object
0x154d44  dup
0x154d45  ldc.i4.0
0x154d46  ldarg.1
0x154d47  stelem.ref
0x154d48  call     string System.Web.SR::GetString(string name, object[] args)
0x154d4d  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x154d52  throw
0x154d53  ldloc.0
0x154d54  brfalse.s loc_154D88
0x154d56  ldarg.1
0x154d57  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x154d5c  stloc.1
0x154d5d  ldloc.1
0x154d5e  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x154d63  stloc.2
0x154d64  leave.s  loc_154D69
0x154d66  pop
0x154d67  leave.s  loc_154D69
0x154d69  ldloc.2
0x154d6a  ldc.i4.3
0x154d6b  and
0x154d6c  brfalse.s loc_154D88
0x154d6e  ldstr    aFileIsReadOnly// "File_is_read_only"
0x154d73  ldc.i4.1
0x154d74  newarr   [mscorlib]System.Object
0x154d79  dup
0x154d7a  ldc.i4.0
0x154d7b  ldarg.1
0x154d7c  stelem.ref
0x154d7d  call     string System.Web.SR::GetString(string name, object[] args)
0x154d82  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x154d87  throw
0x154d88  ldarg.1
0x154d89  ldstr    asc_1B2EDA// "."
0x154d8e  call     string System.Web.Configuration.RemoteWebConfigurationHostServer::GetRandomFileExt()
0x154d93  ldstr    aTmp// ".tmp"
0x154d98  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x154d9d  stloc.3
0x154d9e  ldc.i4.0
0x154d9f  stloc.s  9
0x154da1  br.s     loc_154DD5
0x154da3  ldloc.s  9
0x154da5  ldc.i4.s 0x64
0x154da7  ble.s    loc_154DB9
0x154da9  ldstr    aUnableToCreate// "Unable_to_create_temp_file"
0x154dae  call     string System.Web.SR::GetString(string name)
0x154db3  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x154db8  throw
0x154db9  ldarg.1
0x154dba  ldstr    asc_1B2EDA// "."
0x154dbf  call     string System.Web.Configuration.RemoteWebConfigurationHostServer::GetRandomFileExt()
0x154dc4  ldstr    aTmp// ".tmp"
0x154dc9  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x154dce  stloc.3
0x154dcf  ldloc.s  9
0x154dd1  ldc.i4.1
0x154dd2  add
0x154dd3  stloc.s  9
0x154dd5  ldloc.3
0x154dd6  call     bool [mscorlib]System.IO.File::Exists(string)
0x154ddb  brtrue.s loc_154DA3
0x154ddd  nop
0x154dde  ldloc.3
0x154ddf  ldc.i4.1
0x154de0  ldc.i4.2
0x154de1  ldc.i4.3
0x154de2  ldarg.3
0x154de3  ldlen
0x154de4  conv.i4
0x154de5  ldc.i4   0x80000000
0x154dea  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare, int32, valuetype [mscorlib]System.IO.FileOptions)
0x154def  stloc.s  5
0x154df1  ldloc.s  5
0x154df3  ldarg.3
0x154df4  ldc.i4.0
0x154df5  ldarg.3
0x154df6  ldlen
0x154df7  conv.i4
0x154df8  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x154dfd  leave.s  loc_154E13
0x154dff  stloc.s  0xA
0x154e01  ldloc.s  0xA
0x154e03  stloc.s  4
0x154e05  leave.s  loc_154E13
0x154e07  ldloc.s  5
0x154e09  brfalse.s loc_154E12
0x154e0b  ldloc.s  5
0x154e0d  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x154e12  endfinally
0x154e13  ldloc.s  4
0x154e15  brfalse.s loc_154E25
0x154e17  ldloc.3
0x154e18  call     void [mscorlib]System.IO.File::Delete(string)
0x154e1d  leave.s  loc_154E22
0x154e1f  pop
0x154e20  leave.s  loc_154E22
0x154e22  ldloc.s  4
0x154e24  throw
0x154e25  ldloc.0
0x154e26  brfalse.s loc_154E35
0x154e28  ldarg.0
0x154e29  ldarg.1
0x154e2a  ldloc.3
0x154e2b  call     instance void System.Web.Configuration.RemoteWebConfigurationHostServer::DuplicateFileAttributes(string oldFileName, string newFileName)
0x154e30  leave.s  loc_154E45
0x154e32  pop
0x154e33  leave.s  loc_154E45
0x154e35  ldarg.2
0x154e36  brfalse.s loc_154E45
0x154e38  ldarg.0
0x154e39  ldarg.1
0x154e3a  ldarg.2
0x154e3b  call     instance void System.Web.Configuration.RemoteWebConfigurationHostServer::DuplicateTemplateAttributes(string oldFileName, string newFileName)
0x154e40  leave.s  loc_154E45
0x154e42  pop
0x154e43  leave.s  loc_154E45
0x154e45  ldloc.3
0x154e46  ldarg.1
0x154e47  ldc.i4.s 0xB
0x154e49  call     bool System.Web.UnsafeNativeMethods::MoveFileEx(string oldFilename, string newFilename, unsigned int32 flags)
0x154e4e  brtrue.s loc_154E65
0x154e50  ldloc.3
0x154e51  call     void [mscorlib]System.IO.File::Delete(string)
0x154e56  leave.s  loc_154E5B
0x154e58  pop
0x154e59  leave.s  loc_154E5B
0x154e5b  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForLastWin32Error()
0x154e60  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x154e65  ldloc.0
0x154e66  brfalse.s loc_154E76
0x154e68  ldarg.1
0x154e69  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x154e6e  stloc.1
0x154e6f  ldloc.1
0x154e70  ldloc.2
0x154e71  callvirt instance void [mscorlib]System.IO.FileSystemInfo::set_Attributes(valuetype [mscorlib]System.IO.FileAttributes)
0x154e76  ldarg.1
0x154e77  call     valuetype [mscorlib]System.DateTime [mscorlib]System.IO.File::GetLastWriteTimeUtc(string)
0x154e7c  stloc.s  8
0x154e7e  ldloca.s 8
0x154e80  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x154e85  stloc.s  6
0x154e87  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x154e8c  stloc.s  8
0x154e8e  ldloca.s 8
0x154e90  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x154e95  stloc.s  7
0x154e97  ldarg.s  4
0x154e99  ldloc.s  7
0x154e9b  ldloc.s  6
0x154e9d  bgt.s    loc_154EA3
0x154e9f  ldloc.s  6
0x154ea1  br.s     loc_154EA5
0x154ea3  ldloc.s  7
0x154ea5  stind.i8
0x154ea6  ret
```
