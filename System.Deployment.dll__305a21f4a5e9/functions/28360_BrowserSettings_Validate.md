# BrowserSettings::Validate

- ea: `0x28360`
- end: `0x28400`
- name: `BrowserSettings::Validate`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0xae50`

## callees

- `0x147a0`
- `0x17cd0`
- `0x17d40`
- `0x23020`
- `0x26960`
- `0x28360`

## string_xrefs

- `0x28396`: `Ex_SignedManifestDisallow`
- `0x283b9`: `Ex_UnSignedManifestDisallow`

## pseudocode

```c

```

## disassembly

```asm
0x28360  ldstr    aBrowsersetting// "BrowserSettings.Validate("
0x28365  ldarg.1
0x28366  ldstr    aCalled// ") called."
0x2836b  call     string [mscorlib]System.String::Concat(string, string, string)
0x28370  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x28375  ldarg.1
0x28376  call     valuetype CertificateStatus System.Deployment.Application.Manifest.AssemblyManifest::AnalyzeManifestCertificate(string manifestPath)
0x2837b  stloc.0
0x2837c  ldloc.0
0x2837d  brfalse.s loc_28383
0x2837f  ldloc.0
0x28380  ldc.i4.1
0x28381  bne.un.s loc_283A6
0x28383  ldarg.0
0x28384  ldfld    valuetype ManagedFlags BrowserSettings::ManagedSignedFlag
0x28389  brfalse.s loc_283C9
0x2838b  ldarg.0
0x2838c  ldfld    valuetype ManagedFlags BrowserSettings::ManagedSignedFlag
0x28391  ldc.i4.1
0x28392  beq.s    loc_283C9
0x28394  ldc.i4.s 0xD
0x28396  ldstr    aExSignedmanife_0// "Ex_SignedManifestDisallow"
0x2839b  call     string System.Deployment.Application.Resources::GetString(string s)
0x283a0  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x283a5  throw
0x283a6  ldarg.0
0x283a7  ldfld    valuetype ManagedFlags BrowserSettings::ManagedUnSignedFlag
0x283ac  brfalse.s loc_283C9
0x283ae  ldarg.0
0x283af  ldfld    valuetype ManagedFlags BrowserSettings::ManagedUnSignedFlag
0x283b4  ldc.i4.1
0x283b5  beq.s    loc_283C9
0x283b7  ldc.i4.s 0xD
0x283b9  ldstr    aExUnsignedmani// "Ex_UnSignedManifestDisallow"
0x283be  call     string System.Deployment.Application.Resources::GetString(string s)
0x283c3  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x283c8  throw
0x283c9  ldstr    aBrowserSetting// "Browser settings allow activation. Mana"...
0x283ce  ldarg.0
0x283cf  ldflda   valuetype ManagedFlags BrowserSettings::ManagedSignedFlag
0x283d4  constrained. ManagedFlags
0x283da  callvirt instance string [mscorlib]System.Object::ToString()
0x283df  ldstr    aManagedunsigne// ",ManagedUnSignedFlag="
0x283e4  ldarg.0
0x283e5  ldflda   valuetype ManagedFlags BrowserSettings::ManagedUnSignedFlag
0x283ea  constrained. ManagedFlags
0x283f0  callvirt instance string [mscorlib]System.Object::ToString()
0x283f5  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x283fa  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x283ff  ret
```
