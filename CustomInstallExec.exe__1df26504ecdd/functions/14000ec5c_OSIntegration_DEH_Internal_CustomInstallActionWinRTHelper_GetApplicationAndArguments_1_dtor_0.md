# _OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments_::_1_::dtor$0

- ea: `0x14000ec5c`
- end: `0x14000ec68`
- name: `_OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000859c`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments_::_1_::dtor_0(
        __int64 a1,
        unsigned __int64 a2)
{
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)(a2 + 80), a2);
}

```

## disassembly

```asm
0x14000ec5c  lea     rcx, [rdx+50h]; this
0x14000ec63  jmp     ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
```
