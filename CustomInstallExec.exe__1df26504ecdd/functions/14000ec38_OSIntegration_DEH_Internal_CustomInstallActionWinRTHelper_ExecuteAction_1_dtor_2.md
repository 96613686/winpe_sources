# _OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction_::_1_::dtor$2

- ea: `0x14000ec38`
- end: `0x14000ec44`
- name: `_OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000859c`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction_::_1_::dtor_2(
        __int64 a1,
        unsigned __int64 a2)
{
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)(a2 + 112), a2);
}

```

## disassembly

```asm
0x14000ec38  lea     rcx, [rdx+70h]; this
0x14000ec3f  jmp     ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
```
