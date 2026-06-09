# _ServiceBase::_ServiceCtrlHandler_::_1_::dtor$0

- ea: `0x18001116d`
- end: `0x180011179`
- name: `_ServiceBase::_ServiceCtrlHandler_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000decc`

## pseudocode

```c
void __fastcall ServiceBase::_ServiceCtrlHandler_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)(a2 + 104));
}

```

## disassembly

```asm
0x18001116d  lea     rcx, [rdx+68h]; this
0x180011174  jmp     ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
```
