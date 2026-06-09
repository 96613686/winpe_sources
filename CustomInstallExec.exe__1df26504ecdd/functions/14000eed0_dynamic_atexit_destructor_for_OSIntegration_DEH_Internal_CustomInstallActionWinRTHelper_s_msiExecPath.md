# _dynamic_atexit_destructor_for__OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath__

- ea: `0x14000eed0`
- end: `0x14000eedc`
- name: `_dynamic_atexit_destructor_for__OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath__`
- size: `12`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000859c`

## pseudocode

```c
void __fastcall dynamic_atexit_destructor_for__OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath__(
        __int64 a1,
        unsigned __int64 a2)
{
  Common::StringBuffer::~StringBuffer(
    (Common::StringBuffer *)&OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath,
    a2);
}

```

## disassembly

```asm
0x14000eed0  lea     rcx, ?s_msiExecPath@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@1VStringBuffer@Common@@A; this
0x14000eed7  jmp     ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
```
