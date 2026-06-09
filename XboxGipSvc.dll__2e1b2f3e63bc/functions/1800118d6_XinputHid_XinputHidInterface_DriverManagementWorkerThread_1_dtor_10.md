# _XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor$10

- ea: `0x1800118d6`
- end: `0x1800118e2`
- name: `_XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor$10`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c96c`

## pseudocode

```c
void __fastcall XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((struct _RTL_CRITICAL_SECTION **)(a2 + 136));
}

```

## disassembly

```asm
0x1800118d6  lea     rcx, [rdx+88h]; this
0x1800118dd  jmp     ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
```
