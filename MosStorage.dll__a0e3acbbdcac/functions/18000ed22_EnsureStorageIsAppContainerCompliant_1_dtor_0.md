# _EnsureStorageIsAppContainerCompliant_::_1_::dtor$0

- ea: `0x18000ed22`
- end: `0x18000ed2e`
- name: `_EnsureStorageIsAppContainerCompliant_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006d5c`

## pseudocode

```c
void __fastcall EnsureStorageIsAppContainerCompliant_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CallingStateTracker::~CallingStateTracker((CallingStateTracker *)(a2 + 56));
}

```

## disassembly

```asm
0x18000ed22  lea     rcx, [rdx+38h]; this
0x18000ed29  jmp     ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
```
