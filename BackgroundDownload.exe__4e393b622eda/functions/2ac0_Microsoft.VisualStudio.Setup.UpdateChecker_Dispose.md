# Microsoft.VisualStudio.Setup.UpdateChecker::Dispose

- ea: `0x2ac0`
- end: `0x2adc`
- name: `Microsoft.VisualStudio.Setup.UpdateChecker::Dispose`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x19d0`
- `0x1a50`
- `0x2ac0`

## pseudocode

```c

```

## disassembly

```asm
0x2ac0  ldarg.0
0x2ac1  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_IsDisposed()
0x2ac6  brtrue.s loc_2ADB
0x2ac8  ldarg.0
0x2ac9  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ISingletonService Microsoft.VisualStudio.Setup.UpdateChecker::singletonService
0x2ace  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ISingletonService::ReleaseSingletonLock()
0x2ad3  pop
0x2ad4  ldarg.0
0x2ad5  ldarg.1
0x2ad6  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::Dispose(bool disposing)
0x2adb  ret
```
