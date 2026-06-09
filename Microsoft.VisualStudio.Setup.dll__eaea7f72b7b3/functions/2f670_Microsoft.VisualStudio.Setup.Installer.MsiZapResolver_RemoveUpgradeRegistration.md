# Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::RemoveUpgradeRegistration

- ea: `0x2f670`
- end: `0x2f728`
- name: `Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::RemoveUpgradeRegistration`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2f310`

## callees

- `0x2f4a0`
- `0x2f670`
- `0x3f150`

## string_xrefs

- `0x2f68c`: `SOFTWARE\Classes\Installer\UpgradeCodes`
- `0x2f6c2`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Installer\UpgradeCodes`
- `0x2f6da`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Installer\UpgradeCodes`
- `0x2f710`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Installer\UpgradeCodes`

## pseudocode

```c

```

## disassembly

```asm
0x2f670  ldarg.0
0x2f671  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::logger
0x2f676  dup
0x2f677  brtrue.s loc_2F67C
0x2f679  pop
0x2f67a  br.s     loc_2F68B
0x2f67c  ldstr    aRemovingUpgrad// "Removing upgrade registration"
0x2f681  call     T0x2B000003
0x2f686  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2f68b  ldarg.1
0x2f68c  ldstr    aSoftwareClasse_2// "SOFTWARE\\Classes\\Installer\\UpgradeCo"...
0x2f691  ldc.i4.1
0x2f692  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey::OpenSubKeyTransacted(string path, [opt] bool writable)
0x2f697  isinst   Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey
0x2f69c  stloc.0
0x2f69d  ldloc.0
0x2f69e  brfalse.s loc_2F6A9
0x2f6a0  ldloc.0
0x2f6a1  ldarg.2
0x2f6a2  call     void Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::RemoveChildKeys(class Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey root, string packedProductCode)
0x2f6a7  leave.s  loc_2F6D9
0x2f6a9  ldarg.0
0x2f6aa  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::logger
0x2f6af  dup
0x2f6b0  brtrue.s loc_2F6B5
0x2f6b2  pop
0x2f6b3  leave.s  loc_2F6D9
0x2f6b5  ldstr    aKeyNotFound0// "Key not found: {0}"
0x2f6ba  ldc.i4.1
0x2f6bb  newarr   [mscorlib]System.Object
0x2f6c0  dup
0x2f6c1  ldc.i4.0
0x2f6c2  ldstr    aSoftwareMicros_5// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x2f6c7  stelem.ref
0x2f6c8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2f6cd  leave.s  loc_2F6D9
0x2f6cf  ldloc.0
0x2f6d0  brfalse.s loc_2F6D8
0x2f6d2  ldloc.0
0x2f6d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f6d8  endfinally
0x2f6d9  ldarg.1
0x2f6da  ldstr    aSoftwareMicros_5// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x2f6df  ldc.i4.1
0x2f6e0  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey::OpenSubKeyTransacted(string path, [opt] bool writable)
0x2f6e5  isinst   Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey
0x2f6ea  stloc.1
0x2f6eb  ldloc.1
0x2f6ec  brfalse.s loc_2F6F7
0x2f6ee  ldloc.1
0x2f6ef  ldarg.2
0x2f6f0  call     void Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::RemoveChildKeys(class Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey root, string packedProductCode)
0x2f6f5  leave.s  loc_2F727
0x2f6f7  ldarg.0
0x2f6f8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::logger
0x2f6fd  dup
0x2f6fe  brtrue.s loc_2F703
0x2f700  pop
0x2f701  leave.s  loc_2F727
0x2f703  ldstr    aKeyNotFound0// "Key not found: {0}"
0x2f708  ldc.i4.1
0x2f709  newarr   [mscorlib]System.Object
0x2f70e  dup
0x2f70f  ldc.i4.0
0x2f710  ldstr    aSoftwareMicros_5// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x2f715  stelem.ref
0x2f716  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2f71b  leave.s  loc_2F727
0x2f71d  ldloc.1
0x2f71e  brfalse.s loc_2F726
0x2f720  ldloc.1
0x2f721  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f726  endfinally
0x2f727  ret
```
