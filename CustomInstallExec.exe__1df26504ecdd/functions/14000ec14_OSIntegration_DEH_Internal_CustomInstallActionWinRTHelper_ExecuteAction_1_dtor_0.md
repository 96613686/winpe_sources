# _OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction_::_1_::dtor$0

- ea: `0x14000ec14`
- end: `0x14000ec20`
- name: `_OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140008560`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  CASTraceProvider::ExecuteCustomAction::~ExecuteCustomAction((CASTraceProvider::ExecuteCustomAction *)(a2 + 288));
}

```

## disassembly

```asm
0x14000ec14  lea     rcx, [rdx+120h]; this
0x14000ec1b  jmp     ??1ExecuteCustomAction@CASTraceProvider@@QEAA@XZ; CASTraceProvider::ExecuteCustomAction::~ExecuteCustomAction(void)
```
