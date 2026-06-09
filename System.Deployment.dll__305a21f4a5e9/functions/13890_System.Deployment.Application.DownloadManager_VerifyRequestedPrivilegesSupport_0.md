# System.Deployment.Application.DownloadManager::VerifyRequestedPrivilegesSupport_0

- ea: `0x13890`
- end: `0x13948`
- name: `System.Deployment.Application.DownloadManager::VerifyRequestedPrivilegesSupport_0`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x13510`
- `0x13820`

## callees

- `0x13890`
- `0x147a0`
- `0x17cd0`
- `0x17d40`
- `0x1c730`
- `0x23020`

## string_xrefs

- `0x13890`: `VerifyRequestedPrivilegesSupport(`
- `0x1390a`: `requireAdministrator`
- `0x1392c`: `Ex_ManifestExecutionLevelNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x13890  ldstr    aVerifyrequeste// "VerifyRequestedPrivilegesSupport("
0x13895  ldarg.0
0x13896  ldstr    aCalled// ") called."
0x1389b  call     string [mscorlib]System.String::Concat(string, string, string)
0x138a0  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x138a5  call     bool System.Deployment.Application.PlatformSpecific::get_OnVistaOrAbove()
0x138aa  brfalse  loc_13947
0x138af  ldc.i4.0
0x138b0  stloc.0
0x138b1  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x138b6  ldstr    aSoftwareMicros_0// "Software\\Microsoft\\Windows\\CurrentVe"...
0x138bb  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x138c0  stloc.1
0x138c1  ldloc.1
0x138c2  brfalse.s loc_13906
0x138c4  ldloc.1
0x138c5  ldstr    aEnablelua// "EnableLUA"
0x138ca  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x138cf  brfalse.s loc_13906
0x138d1  ldstr    aLuaPolicyKey// "LUA policy key = "
0x138d6  ldloc.1
0x138d7  callvirt instance string [mscorlib]Microsoft.Win32.RegistryKey::get_Name()
0x138dc  call     string [mscorlib]System.String::Concat(string, string)
0x138e1  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x138e6  ldloc.1
0x138e7  ldstr    aEnablelua// "EnableLUA"
0x138ec  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x138f1  unbox.any [mscorlib]System.Int32
0x138f6  stloc.2
0x138f7  ldloc.2
0x138f8  brfalse.s loc_13906
0x138fa  ldc.i4.1
0x138fb  stloc.0
0x138fc  ldstr    aLuaIsEnabled// "LUA is enabled."
0x13901  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13906  ldloc.0
0x13907  brfalse.s loc_13947
0x13909  ldarg.0
0x1390a  ldstr    aRequireadminis// "requireAdministrator"
0x1390f  ldc.i4.5
0x13910  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x13915  brfalse.s loc_13925
0x13917  ldarg.0
0x13918  ldstr    aHighestavailab// "highestAvailable"
0x1391d  ldc.i4.5
0x1391e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x13923  brtrue.s loc_13947
0x13925  ldc.i4.s 0x12
0x13927  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1392c  ldstr    aExManifestexec// "Ex_ManifestExecutionLevelNotSupported"
0x13931  call     string System.Deployment.Application.Resources::GetString(string s)
0x13936  ldc.i4.0
0x13937  newarr   [mscorlib]System.Object
0x1393c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13941  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x13946  throw
0x13947  ret
```
