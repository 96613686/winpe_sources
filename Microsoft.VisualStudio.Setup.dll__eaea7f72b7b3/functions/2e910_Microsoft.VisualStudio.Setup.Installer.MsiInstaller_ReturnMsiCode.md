# Microsoft.VisualStudio.Setup.Installer.MsiInstaller::ReturnMsiCode

- ea: `0x2e910`
- end: `0x2ea1c`
- name: `Microsoft.VisualStudio.Setup.Installer.MsiInstaller::ReturnMsiCode`
- size: `268`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2e4f0`
- `0x6cc50`
- `0x6ccb0`
- `0x6cd70`
- `0x6cdd0`
- `0x6ce30`

## callees

- `0x2b940`
- `0x2bf60`
- `0x2bfa0`
- `0x2e910`

## string_xrefs

- `0x2e972`: `Switching MSI error code '{0}' to success`
- `0x2e9bf`: `MSIFile_Args2`
- `0x2e9f2`: `MSIProductCode_Args2`

## pseudocode

```c

```

## disassembly

```asm
0x2e910  ldarg.3
0x2e911  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductCode()
0x2e916  stloc.1
0x2e917  ldarg.0
0x2e918  ldarg.3
0x2e919  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultCollection Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetCustomReturnCodes(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package)
0x2e91e  stloc.2
0x2e91f  ldarg.1
0x2e920  ldc.i4   0x643
0x2e925  bne.un.s loc_2E95E
0x2e927  ldarg.0
0x2e928  ldloc.2
0x2e929  ldarg.1
0x2e92a  ldarg.s  4
0x2e92c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetMessageFromSystemIfNotMapped(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultCollection returnCodes, int32 code, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action)
0x2e931  stloc.0
0x2e932  ldarg.0
0x2e933  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::err
0x2e938  brfalse.s loc_2E9B6
0x2e93a  ldloc.0
0x2e93b  ldarg.0
0x2e93c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::err
0x2e941  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x2e946  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_MessageId(int32)
0x2e94b  ldloc.0
0x2e94c  ldarg.0
0x2e94d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::err
0x2e952  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x2e957  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Message(string)
0x2e95c  br.s     loc_2E9B6
0x2e95e  ldarg.1
0x2e95f  ldc.i4   0x645
0x2e964  bne.un.s loc_2E999
0x2e966  ldarg.0
0x2e967  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2e96c  dup
0x2e96d  brtrue.s loc_2E972
0x2e96f  pop
0x2e970  br.s     loc_2E98C
0x2e972  ldstr    aSwitchingMsiEr// "Switching MSI error code '{0}' to succe"...
0x2e977  ldarg.1
0x2e978  box      [mscorlib]System.Int32
0x2e97d  call     string [mscorlib]System.String::Format(string, object)
0x2e982  call     T0x2B000003
0x2e987  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2e98c  ldarg.0
0x2e98d  ldloc.2
0x2e98e  ldc.i4.0
0x2e98f  ldarg.s  4
0x2e991  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetMessageFromSystemIfNotMapped(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultCollection returnCodes, int32 code, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action)
0x2e996  stloc.0
0x2e997  br.s     loc_2E9B6
0x2e999  ldloc.2
0x2e99a  ldarg.1
0x2e99b  ldarg.s  4
0x2e99d  ldc.i4.1
0x2e99e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultCollection::Get(int32, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction, bool)
0x2e9a3  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Type()
0x2e9a8  ldc.i4.5
0x2e9a9  pop
0x2e9aa  pop
0x2e9ab  ldarg.0
0x2e9ac  ldloc.2
0x2e9ad  ldarg.1
0x2e9ae  ldarg.s  4
0x2e9b0  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetMessageFromSystemIfNotMapped(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultCollection returnCodes, int32 code, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action)
0x2e9b5  stloc.0
0x2e9b6  ldarg.2
0x2e9b7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e9bc  brtrue.s loc_2E9E9
0x2e9be  ldloc.0
0x2e9bf  ldstr    aMsifileArgs2// "MSIFile_Args2"
0x2e9c4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_OperationContextResourceId(string)
0x2e9c9  ldloc.0
0x2e9ca  ldc.i4.2
0x2e9cb  newarr   [mscorlib]System.Object
0x2e9d0  dup
0x2e9d1  ldc.i4.0
0x2e9d2  ldarg.2
0x2e9d3  stelem.ref
0x2e9d4  dup
0x2e9d5  ldc.i4.1
0x2e9d6  ldarg.s  5
0x2e9d8  dup
0x2e9d9  brtrue.s loc_2E9E1
0x2e9db  pop
0x2e9dc  ldsfld   string [mscorlib]System.String::Empty
0x2e9e1  stelem.ref
0x2e9e2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_OperationContextArgs(object[])
0x2e9e7  br.s     loc_2EA1A
0x2e9e9  ldloc.1
0x2e9ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e9ef  brtrue.s loc_2EA1A
0x2e9f1  ldloc.0
0x2e9f2  ldstr    aMsiproductcode// "MSIProductCode_Args2"
0x2e9f7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_OperationContextResourceId(string)
0x2e9fc  ldloc.0
0x2e9fd  ldc.i4.2
0x2e9fe  newarr   [mscorlib]System.Object
0x2ea03  dup
0x2ea04  ldc.i4.0
0x2ea05  ldloc.1
0x2ea06  stelem.ref
0x2ea07  dup
0x2ea08  ldc.i4.1
0x2ea09  ldarg.s  5
0x2ea0b  dup
0x2ea0c  brtrue.s loc_2EA14
0x2ea0e  pop
0x2ea0f  ldsfld   string [mscorlib]System.String::Empty
0x2ea14  stelem.ref
0x2ea15  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_OperationContextArgs(object[])
0x2ea1a  ldloc.0
0x2ea1b  ret
```
