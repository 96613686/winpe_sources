# Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::RemoveComponentRegistration

- ea: `0x2f730`
- end: `0x2f79a`
- name: `Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::RemoveComponentRegistration`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2f310`

## callees

- `0x2f4a0`
- `0x2f730`
- `0x3f150`

## string_xrefs

- `0x2f73c`: `Removing component registration`
- `0x2f74c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Installer\UserData\S-1-5-18\Components`
- `0x2f782`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Installer\UserData\S-1-5-18\Components`

## pseudocode

```c

```

## disassembly

```asm
0x2f730  ldarg.0
0x2f731  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::logger
0x2f736  dup
0x2f737  brtrue.s loc_2F73C
0x2f739  pop
0x2f73a  br.s     loc_2F74B
0x2f73c  ldstr    aRemovingCompon// "Removing component registration"
0x2f741  call     T0x2B000003
0x2f746  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2f74b  ldarg.1
0x2f74c  ldstr    aSoftwareMicros_6// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x2f751  ldc.i4.1
0x2f752  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey::OpenSubKeyTransacted(string path, [opt] bool writable)
0x2f757  isinst   Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey
0x2f75c  stloc.0
0x2f75d  ldloc.0
0x2f75e  brfalse.s loc_2F769
0x2f760  ldloc.0
0x2f761  ldarg.2
0x2f762  call     void Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::RemoveChildKeys(class Microsoft.VisualStudio.Setup.Services.ITransactedRegistryKey root, string packedProductCode)
0x2f767  leave.s  loc_2F799
0x2f769  ldarg.0
0x2f76a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.MsiZapResolver::logger
0x2f76f  dup
0x2f770  brtrue.s loc_2F775
0x2f772  pop
0x2f773  leave.s  loc_2F799
0x2f775  ldstr    aKeyNotFound0// "Key not found: {0}"
0x2f77a  ldc.i4.1
0x2f77b  newarr   [mscorlib]System.Object
0x2f780  dup
0x2f781  ldc.i4.0
0x2f782  ldstr    aSoftwareMicros_6// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x2f787  stelem.ref
0x2f788  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2f78d  leave.s  loc_2F799
0x2f78f  ldloc.0
0x2f790  brfalse.s loc_2F798
0x2f792  ldloc.0
0x2f793  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f798  endfinally
0x2f799  ret
```
