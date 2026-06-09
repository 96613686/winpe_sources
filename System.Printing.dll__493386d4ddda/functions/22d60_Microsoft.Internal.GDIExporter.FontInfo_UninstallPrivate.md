# Microsoft.Internal.GDIExporter.FontInfo::UninstallPrivate

- ea: `0x22d60`
- end: `0x22da3`
- name: `Microsoft.Internal.GDIExporter.FontInfo::UninstallPrivate`
- size: `67`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1cf20`
- `0x22cb0`

## callees

- `0x22be0`
- `0x22d60`

## pseudocode

```c

```

## disassembly

```asm
0x22d60  ldarg.0
0x22d61  ldfld    class Microsoft.Internal.GDIExporter.FontInstallInfo Microsoft.Internal.GDIExporter.FontInfo::_privateInstall
0x22d66  brfalse.s loc_22DA2
0x22d68  ldarg.0
0x22d69  ldfld    object Microsoft.Internal.GDIExporter.FontInfo::_privateInstallHandle
0x22d6e  ldnull
0x22d6f  bne.un.s loc_22D74
0x22d71  ldc.i4.0
0x22d72  br.s     loc_22D75
0x22d74  ldc.i4.1
0x22d75  stloc.0
0x22d76  ldloc.0
0x22d77  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x22d7c  ldarg.0
0x22d7d  ldfld    class Microsoft.Internal.GDIExporter.FontInstallInfo Microsoft.Internal.GDIExporter.FontInfo::_privateInstall
0x22d82  ldarg.0
0x22d83  ldfld    object Microsoft.Internal.GDIExporter.FontInfo::_privateInstallHandle
0x22d88  call     instance void Microsoft.Internal.GDIExporter.FontInstallInfo::Uninstall(object installHandle)
0x22d8d  ldarg.0
0x22d8e  ldnull
0x22d8f  stfld    class Microsoft.Internal.GDIExporter.FontInstallInfo Microsoft.Internal.GDIExporter.FontInfo::_privateInstall
0x22d94  ldarg.0
0x22d95  ldnull
0x22d96  stfld    object Microsoft.Internal.GDIExporter.FontInfo::_privateInstallHandle
0x22d9b  ldarg.0
0x22d9c  ldnull
0x22d9d  stfld    string Microsoft.Internal.GDIExporter.FontInfo::_newFamilyName
0x22da2  ret
```
