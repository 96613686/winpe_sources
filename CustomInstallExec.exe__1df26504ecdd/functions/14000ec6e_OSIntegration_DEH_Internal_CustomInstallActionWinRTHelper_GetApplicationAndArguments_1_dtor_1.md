# _OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments_::_1_::dtor$1

- ea: `0x14000ec6e`
- end: `0x14000ec7a`
- name: `_OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000859c`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments_::_1_::dtor_1(
        __int64 a1,
        unsigned __int64 a2)
{
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)(a2 + 104), a2);
}

```

## disassembly

```asm
0x14000ec6e  lea     rcx, [rdx+68h]; this
0x14000ec75  jmp     ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
```
