# Microsoft.VisualStudio.Setup.OpcVerifier::CopyCertsToLayoutFolder

- ea: `0x3940`
- end: `0x39f7`
- name: `Microsoft.VisualStudio.Setup.OpcVerifier::CopyCertsToLayoutFolder`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x36d0`

## callees

- `0x3940`
- `0x3a00`

## string_xrefs

- `0x3963`: `Creating directory for vs_installer certificates failed: '`
- `0x397d`: `Creating directory for vs_installer certificates failed: '`
- `0x39c5`: `Exception creating vs_installer Signing certificate file: `
- `0x39da`: `Exception creating vs_installer Signing certificate file: `

## pseudocode

```c

```

## disassembly

```asm
0x3940  ldarg.1
0x3941  ldsfld   string Microsoft.VisualStudio.Setup.OpcVerifier::LayoutCertSubPath
0x3946  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x394b  stloc.0
0x394c  ldloc.0
0x394d  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x3952  pop
0x3953  leave.s  loc_3993
0x3955  stloc.3
0x3956  ldarg.0
0x3957  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.OpcVerifier::logger
0x395c  dup
0x395d  brtrue.s loc_3962
0x395f  pop
0x3960  br.s     loc_397D
0x3962  ldloc.3
0x3963  ldstr    aCreatingDirect// "Creating directory for vs_installer cer"...
0x3968  ldloc.0
0x3969  ldstr    asc_7FEB6// "'"
0x396e  call     string [mscorlib]System.String::Concat(string, string, string)
0x3973  call     T0x2B000003
0x3978  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x397d  ldstr    aCreatingDirect// "Creating directory for vs_installer cer"...
0x3982  ldloc.0
0x3983  ldstr    asc_7FEB6// "'"
0x3988  call     string [mscorlib]System.String::Concat(string, string, string)
0x398d  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x3992  throw
0x3993  ldarg.0
0x3994  ldarg.2
0x3995  call     instance unsigned int8[] Microsoft.VisualStudio.Setup.OpcVerifier::GetRootCertificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 certificate)
0x399a  stloc.1
0x399b  ldnull
0x399c  stloc.2
0x399d  ldloc.1
0x399e  brfalse.s loc_39EB
0x39a0  ldloc.0
0x39a1  ldsfld   string Microsoft.VisualStudio.Setup.OpcVerifier::OpcSignRootFileName
0x39a6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x39ab  stloc.2
0x39ac  ldloc.2
0x39ad  ldloc.1
0x39ae  call     void [mscorlib]System.IO.File::WriteAllBytes(string, unsigned int8[])
0x39b3  leave.s  loc_39F6
0x39b5  stloc.s  4
0x39b7  ldarg.0
0x39b8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.OpcVerifier::logger
0x39bd  dup
0x39be  brtrue.s loc_39C3
0x39c0  pop
0x39c1  br.s     loc_39DA
0x39c3  ldloc.s  4
0x39c5  ldstr    aExceptionCreat// "Exception creating vs_installer Signing"...
0x39ca  ldloc.2
0x39cb  call     string [mscorlib]System.String::Concat(string, string)
0x39d0  call     T0x2B000003
0x39d5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x39da  ldstr    aExceptionCreat// "Exception creating vs_installer Signing"...
0x39df  ldloc.2
0x39e0  call     string [mscorlib]System.String::Concat(string, string)
0x39e5  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x39ea  throw
0x39eb  ldstr    aSigningCertifi// "Signing certificate collection missing"
0x39f0  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x39f5  throw
0x39f6  ret
```
