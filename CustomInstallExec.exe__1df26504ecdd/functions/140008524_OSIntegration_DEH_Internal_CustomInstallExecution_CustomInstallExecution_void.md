# OSIntegration::DEH::Internal::CustomInstallExecution::~CustomInstallExecution(void)

- ea: `0x140008524`
- end: `0x140008558`
- name: `??1CustomInstallExecution@Internal@DEH@OSIntegration@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::CustomInstallExecution *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a8a8`
- `0x14000edb2`

## callees

- `0x1400024e8`
- `0x1400082ec`
- `0x14000859c`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::~CustomInstallExecution(
        OSIntegration::DEH::Internal::CustomInstallExecution *this)
{
  unsigned __int64 v2; // rdx

  TraceLoggingUnregister_EventUnregister(&qword_140016038);
  Common::Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>::~Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>(
    (__int64)this + 48,
    v2);
  Common::StringBuffer::~StringBuffer((OSIntegration::DEH::Internal::CustomInstallExecution *)((char *)this + 24));
  Common::StringBuffer::~StringBuffer(this);
}

```

## disassembly

```asm
0x140008524  push    rbx
0x140008526  sub     rsp, 20h
0x14000852a  mov     rbx, rcx
0x14000852d  lea     rcx, qword_140016038
0x140008534  call    TraceLoggingUnregister_EventUnregister
0x140008539  lea     rcx, [rbx+30h]
0x14000853d  call    ??1?$Array@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@V1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@VNoKey@Common@@@6@@Common@@QEAA@XZ; Common::Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>::~Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>(void)
0x140008542  lea     rcx, [rbx+18h]; this
0x140008546  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x14000854b  mov     rcx, rbx; this
0x14000854e  add     rsp, 20h
0x140008552  pop     rbx
0x140008553  jmp     ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
```
