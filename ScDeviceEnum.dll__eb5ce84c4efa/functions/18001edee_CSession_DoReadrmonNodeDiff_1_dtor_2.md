# _CSession::_DoReadrmonNodeDiff_::_1_::dtor$2

- ea: `0x18001edee`
- end: `0x18001edfa`
- name: `_CSession::_DoReadrmonNodeDiff_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800077a8`

## pseudocode

```c
void __fastcall CSession::_DoReadrmonNodeDiff_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((struct _RTL_CRITICAL_SECTION **)(a2 + 72));
}

```

## disassembly

```asm
0x18001edee  lea     rcx, [rdx+48h]; this
0x18001edf5  jmp     ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
```
