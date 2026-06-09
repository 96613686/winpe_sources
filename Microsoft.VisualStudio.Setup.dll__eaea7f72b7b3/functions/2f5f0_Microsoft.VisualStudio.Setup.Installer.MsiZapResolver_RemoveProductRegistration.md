# Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::RemoveProductRegistration

- ea: `0x2f5f0`
- end: `0x2f665`
- name: `Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::RemoveProductRegistration`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2f310`

## callees

- `0x2f420`
- `0x2f5f0`
- `0x3e960`
- `0x3f140`

## string_xrefs

- `0x2f60c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Installer\UserData\S-1-5-18\Products\`
- `0x2f61e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\`
- `0x2f653`: `SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\`

## pseudocode

```c

```

## disassembly

```asm
0x2f5f0  ldarg.0
0x2f5f1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::logger
0x2f5f6  dup
0x2f5f7  brtrue.s loc_2F5FC
0x2f5f9  pop
0x2f5fa  br.s     loc_2F60B
0x2f5fc  ldstr    aRemovingProduc// "Removing product registration"
0x2f601  call     T0x2B000003
0x2f606  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2f60b  ldarg.1
0x2f60c  ldstr    aSoftwareMicros_3// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x2f611  ldarg.2
0x2f612  call     string [mscorlib]System.String::Concat(string, string)
0x2f617  ldc.i4.0
0x2f618  callvirt instance void Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey::DeleteSubKeyTreeTransacted(string path, [opt] bool throwOnMissingSubKey)
0x2f61d  ldarg.1
0x2f61e  ldstr    aSoftwareMicros_4// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x2f623  ldarg.3
0x2f624  call     string [mscorlib]System.String::Concat(string, string)
0x2f629  ldc.i4.0
0x2f62a  callvirt instance void Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey::DeleteSubKeyTreeTransacted(string path, [opt] bool throwOnMissingSubKey)
0x2f62f  ldarg.0
0x2f630  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::get_Services()
0x2f635  dup
0x2f636  brtrue.s loc_2F63C
0x2f638  pop
0x2f639  ldnull
0x2f63a  br.s     loc_2F642
0x2f63c  ldc.i4.0
0x2f63d  call     T0x2B000053
0x2f642  dup
0x2f643  brtrue.s loc_2F64B
0x2f645  pop
0x2f646  ldsfld   class Microsoft.VisualStudio.Setup.Services.IOperatingSystem Microsoft.VisualStudio.Setup.Services.OperatingSystem::Default
0x2f64b  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IOperatingSystem::get_Is64Bit()
0x2f650  brfalse.s loc_2F664
0x2f652  ldarg.1
0x2f653  ldstr    aSoftwareWow643_1// "SOFTWARE\\WOW6432Node\\Microsoft\\Windo"...
0x2f658  ldarg.3
0x2f659  call     string [mscorlib]System.String::Concat(string, string)
0x2f65e  ldc.i4.0
0x2f65f  callvirt instance void Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey::DeleteSubKeyTreeTransacted(string path, [opt] bool throwOnMissingSubKey)
0x2f664  ret
```
