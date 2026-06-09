# _CSessionManager::RemoveAll_::_1_::dtor$0

- ea: `0x18001ecde`
- end: `0x18001ecea`
- name: `_CSessionManager::RemoveAll_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800077a8`

## pseudocode

```c
void __fastcall CSessionManager::RemoveAll_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((struct _RTL_CRITICAL_SECTION **)(a2 + 48));
}

```

## disassembly

```asm
0x18001ecde  lea     rcx, [rdx+30h]; this
0x18001ece5  jmp     ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
```
