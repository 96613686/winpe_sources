# _CTaskCounter::Increment_::_1_::dtor$1

- ea: `0x18001e8f2`
- end: `0x18001e8fe`
- name: `_CTaskCounter::Increment_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800077a8`

## pseudocode

```c
void __fastcall CTaskCounter::Increment_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((struct _RTL_CRITICAL_SECTION **)(a2 + 56));
}

```

## disassembly

```asm
0x18001e8f2  lea     rcx, [rdx+38h]; this
0x18001e8f9  jmp     ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
```
