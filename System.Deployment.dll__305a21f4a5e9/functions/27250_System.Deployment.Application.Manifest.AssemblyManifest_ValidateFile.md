# System.Deployment.Application.Manifest.AssemblyManifest::ValidateFile

- ea: `0x27250`
- end: `0x27337`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::ValidateFile`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x26250`

## callees

- `0x147a0`
- `0x219c0`
- `0x23020`
- `0x24780`
- `0x247a0`
- `0x247b0`
- `0x247c0`
- `0x247e0`
- `0x27250`
- `0x27340`

## string_xrefs

- `0x2729c`: `Ex_FilePathNotRelative`

## pseudocode

```c

```

## disassembly

```asm
0x27250  ldarg.0
0x27251  callvirt instance class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.File::get_HashCollection()
0x27256  call     bool System.Deployment.Application.Manifest.AssemblyManifest::IsInvalidHash(class System.Deployment.Application.HashCollection hashCollection)
0x2725b  brfalse.s loc_27288
0x2725d  ldc.i4.s 0x11
0x2725f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x27264  ldstr    aExInvalidfileh// "Ex_InvalidFileHash"
0x27269  call     string System.Deployment.Application.Resources::GetString(string s)
0x2726e  ldc.i4.1
0x2726f  newarr   [mscorlib]System.Object
0x27274  dup
0x27275  ldc.i4.0
0x27276  ldarg.0
0x27277  callvirt instance string System.Deployment.Application.Manifest.File::get_Name()
0x2727c  stelem.ref
0x2727d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27282  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x27287  throw
0x27288  ldarg.0
0x27289  callvirt instance string System.Deployment.Application.Manifest.File::get_Name()
0x2728e  call     bool System.Deployment.Application.UriHelper::IsValidRelativeFilePath(string path)
0x27293  brtrue.s loc_272C0
0x27295  ldc.i4.s 0x11
0x27297  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2729c  ldstr    aExFilepathnotr// "Ex_FilePathNotRelative"
0x272a1  call     string System.Deployment.Application.Resources::GetString(string s)
0x272a6  ldc.i4.1
0x272a7  newarr   [mscorlib]System.Object
0x272ac  dup
0x272ad  ldc.i4.0
0x272ae  ldarg.0
0x272af  callvirt instance string System.Deployment.Application.Manifest.File::get_Name()
0x272b4  stelem.ref
0x272b5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x272ba  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x272bf  throw
0x272c0  ldarg.0
0x272c1  callvirt instance bool System.Deployment.Application.Manifest.File::get_IsOptional()
0x272c6  brfalse.s loc_272FB
0x272c8  ldarg.0
0x272c9  callvirt instance string System.Deployment.Application.Manifest.File::get_Group()
0x272ce  brtrue.s loc_272FB
0x272d0  ldc.i4.s 0x11
0x272d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x272d7  ldstr    aExFileoptional// "Ex_FileOptionalButNoGroup"
0x272dc  call     string System.Deployment.Application.Resources::GetString(string s)
0x272e1  ldc.i4.1
0x272e2  newarr   [mscorlib]System.Object
0x272e7  dup
0x272e8  ldc.i4.0
0x272e9  ldarg.0
0x272ea  callvirt instance string System.Deployment.Application.Manifest.File::get_Name()
0x272ef  stelem.ref
0x272f0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x272f5  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x272fa  throw
0x272fb  ldarg.0
0x272fc  callvirt instance bool System.Deployment.Application.Manifest.File::get_IsOptional()
0x27301  brfalse.s loc_27336
0x27303  ldarg.0
0x27304  callvirt instance bool System.Deployment.Application.Manifest.File::get_IsData()
0x27309  brfalse.s loc_27336
0x2730b  ldc.i4.s 0x11
0x2730d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x27312  ldstr    aExFileoptional_0// "Ex_FileOptionalAndData"
0x27317  call     string System.Deployment.Application.Resources::GetString(string s)
0x2731c  ldc.i4.1
0x2731d  newarr   [mscorlib]System.Object
0x27322  dup
0x27323  ldc.i4.0
0x27324  ldarg.0
0x27325  callvirt instance string System.Deployment.Application.Manifest.File::get_Name()
0x2732a  stelem.ref
0x2732b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27330  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x27335  throw
0x27336  ret
```
