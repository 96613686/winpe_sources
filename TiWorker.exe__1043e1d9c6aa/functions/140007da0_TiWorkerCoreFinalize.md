# TiWorkerCoreFinalize

- ea: `0x140007da0`
- end: `0x140007eb2`
- name: `TiWorkerCoreFinalize`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006d68`

## callees

- `0x140007da0`
- `0x14000d81c`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140007e09`: `Trusted Installer core was not initialized.`

## pseudocode

```c
void TiWorkerCoreFinalize()
{
  if ( vhCoreModule )
  {
    if ( vpfnCbsCoreFinalize )
      vpfnCbsCoreFinalize();
    vhCoreModule = 0;
    vpfnCbsCoreInitialize = 0;
    vpfnCbsCoreStartupProcessing = 0;
    vpfnCbsCoreStartupProcessingEx = 0;
    vpfnCbsCoreEnsureNoStartupProcessing = 0;
    vpfnCbsCoreShutdownProcessing = 0;
    vpfnCbsCoreFinalize = 0;
    vpfnCbsCorePrepareShutdownProcessing = 0;
    vpfnCbsCoreFinalizeShutdownProcessing = 0;
  }
  else
  {
    if ( vpfnCbsCoreInitialize )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( vpfnCbsCoreStartupProcessing )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( vpfnCbsCoreStartupProcessingEx )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( vpfnCbsCoreEnsureNoStartupProcessing )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( vpfnCbsCoreShutdownProcessing )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( vpfnCbsCoreFinalize )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    vpfnCbsCoreInitialize = 0;
    vpfnCbsCoreStartupProcessing = 0;
    vpfnCbsCoreStartupProcessingEx = 0;
    vpfnCbsCoreEnsureNoStartupProcessing = 0;
    vpfnCbsCoreShutdownProcessing = 0;
    vpfnCbsCoreFinalize = 0;
    vpfnCbsCorePrepareShutdownProcessing = 0;
    vpfnCbsCoreFinalizeShutdownProcessing = 0;
    CBSWdsLog(0x4000000u, 0, 0, "Trusted Installer core was not initialized.");
  }
}

```

## disassembly

```asm
0x140007da0  push    rbx
0x140007da2  sub     rsp, 20h
0x140007da6  xor     ebx, ebx
0x140007da8  cmp     cs:?vhCoreModule@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * vhCoreModule
0x140007daf  jnz     loc_140007E5C
0x140007db5  cmp     cs:?vpfnCbsCoreInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ2222PEAPEAUIClassFactory@@@ZEA, rbx; long (*vpfnCbsCoreInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x140007dbc  jz      short loc_140007DC3
0x140007dbe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140007dc3  cmp     cs:?vpfnCbsCoreStartupProcessing@@3P6AJH@ZEA, rbx; long (*vpfnCbsCoreStartupProcessing)(int)
0x140007dca  jz      short loc_140007DD1
0x140007dcc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140007dd1  cmp     cs:?vpfnCbsCoreStartupProcessingEx@@3P6AJK@ZEA, rbx; long (*vpfnCbsCoreStartupProcessingEx)(ulong)
0x140007dd8  jz      short loc_140007DDF
0x140007dda  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140007ddf  cmp     cs:?vpfnCbsCoreEnsureNoStartupProcessing@@3P6AJH@ZEA, rbx; long (*vpfnCbsCoreEnsureNoStartupProcessing)(int)
0x140007de6  jz      short loc_140007DED
0x140007de8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140007ded  cmp     cs:?vpfnCbsCoreShutdownProcessing@@3P6AJPEAUITrustedInstallerService@@H@ZEA, rbx; long (*vpfnCbsCoreShutdownProcessing)(ITrustedInstallerService *,int)
0x140007df4  jz      short loc_140007DFB
0x140007df6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140007dfb  cmp     cs:?vpfnCbsCoreFinalize@@3P6AJXZEA, rbx; long (*vpfnCbsCoreFinalize)(void)
0x140007e02  jz      short loc_140007E09
0x140007e04  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140007e09  lea     r9, aTrustedInstall; "Trusted Installer core was not initiali"...
0x140007e10  mov     cs:?vpfnCbsCoreInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ2222PEAPEAUIClassFactory@@@ZEA, rbx; long (*vpfnCbsCoreInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x140007e17  xor     r8d, r8d
0x140007e1a  mov     cs:?vpfnCbsCoreStartupProcessing@@3P6AJH@ZEA, rbx; long (*vpfnCbsCoreStartupProcessing)(int)
0x140007e21  xor     edx, edx
0x140007e23  mov     cs:?vpfnCbsCoreStartupProcessingEx@@3P6AJK@ZEA, rbx; long (*vpfnCbsCoreStartupProcessingEx)(ulong)
0x140007e2a  mov     ecx, 4000000h
0x140007e2f  mov     cs:?vpfnCbsCoreEnsureNoStartupProcessing@@3P6AJH@ZEA, rbx; long (*vpfnCbsCoreEnsureNoStartupProcessing)(int)
0x140007e36  mov     cs:?vpfnCbsCoreShutdownProcessing@@3P6AJPEAUITrustedInstallerService@@H@ZEA, rbx; long (*vpfnCbsCoreShutdownProcessing)(ITrustedInstallerService *,int)
0x140007e3d  mov     cs:?vpfnCbsCoreFinalize@@3P6AJXZEA, rbx; long (*vpfnCbsCoreFinalize)(void)
0x140007e44  mov     cs:?vpfnCbsCorePrepareShutdownProcessing@@3P6AJPEAUITrustedInstallerService@@K@ZEA, rbx; long (*vpfnCbsCorePrepareShutdownProcessing)(ITrustedInstallerService *,ulong)
0x140007e4b  mov     cs:?vpfnCbsCoreFinalizeShutdownProcessing@@3P6AJXZEA, rbx; long (*vpfnCbsCoreFinalizeShutdownProcessing)(void)
0x140007e52  add     rsp, 20h
0x140007e56  pop     rbx
0x140007e57  jmp     ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007e5c  mov     rax, cs:?vpfnCbsCoreFinalize@@3P6AJXZEA; long (*vpfnCbsCoreFinalize)(void)
0x140007e63  test    rax, rax
0x140007e66  jz      short loc_140007E6D
0x140007e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e6d  mov     cs:?vhCoreModule@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * vhCoreModule
0x140007e74  mov     cs:?vpfnCbsCoreInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ2222PEAPEAUIClassFactory@@@ZEA, rbx; long (*vpfnCbsCoreInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x140007e7b  mov     cs:?vpfnCbsCoreStartupProcessing@@3P6AJH@ZEA, rbx; long (*vpfnCbsCoreStartupProcessing)(int)
0x140007e82  mov     cs:?vpfnCbsCoreStartupProcessingEx@@3P6AJK@ZEA, rbx; long (*vpfnCbsCoreStartupProcessingEx)(ulong)
0x140007e89  mov     cs:?vpfnCbsCoreEnsureNoStartupProcessing@@3P6AJH@ZEA, rbx; long (*vpfnCbsCoreEnsureNoStartupProcessing)(int)
0x140007e90  mov     cs:?vpfnCbsCoreShutdownProcessing@@3P6AJPEAUITrustedInstallerService@@H@ZEA, rbx; long (*vpfnCbsCoreShutdownProcessing)(ITrustedInstallerService *,int)
0x140007e97  mov     cs:?vpfnCbsCoreFinalize@@3P6AJXZEA, rbx; long (*vpfnCbsCoreFinalize)(void)
0x140007e9e  mov     cs:?vpfnCbsCorePrepareShutdownProcessing@@3P6AJPEAUITrustedInstallerService@@K@ZEA, rbx; long (*vpfnCbsCorePrepareShutdownProcessing)(ITrustedInstallerService *,ulong)
0x140007ea5  mov     cs:?vpfnCbsCoreFinalizeShutdownProcessing@@3P6AJXZEA, rbx; long (*vpfnCbsCoreFinalizeShutdownProcessing)(void)
0x140007eac  add     rsp, 20h
0x140007eb0  pop     rbx
0x140007eb1  retn
```
