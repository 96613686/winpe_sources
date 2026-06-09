# Microsoft.VisualStudio.Setup.Validation.RegistryCheckWebView2::Evaluate

- ea: `0x20d10`
- end: `0x20e2c`
- name: `Microsoft.VisualStudio.Setup.Validation.RegistryCheckWebView2::Evaluate`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x199a0`
- `0x20af0`
- `0x20b10`
- `0x20b40`
- `0x20c40`
- `0x20cb0`
- `0x20cc0`
- `0x20cd0`
- `0x20d10`
- `0x21b80`
- `0x21c50`
- `0x21ce0`
- `0x21d00`

## string_xrefs

- `0x20db7`: `Precheck_GPOPolicyPreventsInstallOfWebView2`
- `0x20da3`: `Precheck: A GPO policy has prevented the installation of WebView2.`

## pseudocode

```c

```

## disassembly

```asm
0x20d10  ldarg.0
0x20d11  call     instance bool Microsoft.VisualStudio.Setup.Validation.RegistryCheck::get_IsPackageInstallable()
0x20d16  brfalse  loc_20E27
0x20d1b  ldarg.0
0x20d1c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.Validation.RegistryCheck::get_Registry()
0x20d21  ldc.i4.2
0x20d22  ldc.i4.0
0x20d23  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x20d28  stloc.0
0x20d29  ldloc.0
0x20d2a  call     string Microsoft.VisualStudio.Setup.Validation.RegistryCheckWebView2::get_EdgeUpdateRegistryKey()
0x20d2f  ldc.i4.1
0x20d30  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0x20d35  stloc.1
0x20d36  ldloc.1
0x20d37  brfalse  loc_20DE3
0x20d3c  ldc.i4.0
0x20d3d  stloc.2
0x20d3e  ldarg.0
0x20d3f  ldloc.1
0x20d40  call     string Microsoft.VisualStudio.Setup.Validation.RegistryCheckWebView2::get_InstallRegistryEntryName()
0x20d45  ldloca.s 3
0x20d47  call     instance bool Microsoft.VisualStudio.Setup.Validation.RegistryCheck::TryGetRegistryKeyValue(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey subKey, string registryEntryName, [out] valuetype [mscorlib]System.Nullable`1<int32>& registryValue)
0x20d4c  brfalse.s loc_20D6A
0x20d4e  ldloc.3
0x20d4f  stloc.s  4
0x20d51  ldc.i4.0
0x20d52  stloc.s  5
0x20d54  ldloca.s 4
0x20d56  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x20d5b  ldloc.s  5
0x20d5d  ceq
0x20d5f  ldloca.s 4
0x20d61  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x20d66  and
0x20d67  stloc.2
0x20d68  br.s     loc_20D94
0x20d6a  ldarg.0
0x20d6b  ldloc.1
0x20d6c  call     string Microsoft.VisualStudio.Setup.Validation.RegistryCheckWebView2::get_InstallDefaultRegistryEntryName()
0x20d71  ldloca.s 3
0x20d73  call     instance bool Microsoft.VisualStudio.Setup.Validation.RegistryCheck::TryGetRegistryKeyValue(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey subKey, string registryEntryName, [out] valuetype [mscorlib]System.Nullable`1<int32>& registryValue)
0x20d78  brfalse.s loc_20D94
0x20d7a  ldloc.3
0x20d7b  stloc.s  4
0x20d7d  ldc.i4.0
0x20d7e  stloc.s  5
0x20d80  ldloca.s 4
0x20d82  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x20d87  ldloc.s  5
0x20d89  ceq
0x20d8b  ldloca.s 4
0x20d8d  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x20d92  and
0x20d93  stloc.2
0x20d94  ldloc.2
0x20d95  brfalse.s loc_20DE3
0x20d97  ldarg.0
0x20d98  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.RegistryCheck::get_Logger()
0x20d9d  dup
0x20d9e  brtrue.s loc_20DA3
0x20da0  pop
0x20da1  br.s     loc_20DB2
0x20da3  ldstr    aPrecheckAGpoPo// "Precheck: A GPO policy has prevented th"...
0x20da8  call     T0x2B000003
0x20dad  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x20db2  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x20db7  ldstr    aPrecheckGpopol// "Precheck_GPOPolicyPreventsInstallOfWebV"...
0x20dbc  call     T0x2B000003
0x20dc1  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x20dc6  dup
0x20dc7  ldc.i4.1
0x20dc8  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_SupportsRetry(bool value)
0x20dcd  dup
0x20dce  ldc.i4.0
0x20dcf  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_IsWarning(bool value)
0x20dd4  dup
0x20dd5  ldc.i4   0x1F48
0x20dda  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_ErrorCode(int32 value)
0x20ddf  stloc.s  6
0x20de1  leave.s  loc_20E29
0x20de3  leave.s  loc_20DEF
0x20de5  ldloc.1
0x20de6  brfalse.s loc_20DEE
0x20de8  ldloc.1
0x20de9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20dee  endfinally
0x20def  leave.s  loc_20DFB
0x20df1  ldloc.0
0x20df2  brfalse.s loc_20DFA
0x20df4  ldloc.0
0x20df5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20dfa  endfinally
0x20dfb  leave.s  loc_20E27
0x20dfd  stloc.s  7
0x20dff  ldarg.0
0x20e00  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.RegistryCheck::get_Logger()
0x20e05  dup
0x20e06  brtrue.s loc_20E0B
0x20e08  pop
0x20e09  br.s     loc_20E25
0x20e0b  ldstr    aPrecheckFailur_3// "Precheck: Failure checking GPO policy f"...
0x20e10  ldc.i4.1
0x20e11  newarr   [mscorlib]System.Object
0x20e16  dup
0x20e17  ldc.i4.0
0x20e18  ldloc.s  7
0x20e1a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x20e1f  stelem.ref
0x20e20  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x20e25  leave.s  loc_20E27
0x20e27  ldnull
0x20e28  ret
0x20e29  ldloc.s  6
0x20e2b  ret
```
