# _MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$1

- ea: `0x18000eeb0`
- end: `0x18000eebc`
- name: `_MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006d5c`

## pseudocode

```c
void __fastcall MosQueryPackagesFromPathInternal_Unified_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CallingStateTracker::~CallingStateTracker((CallingStateTracker *)(a2 + 100));
}

```

## disassembly

```asm
0x18000eeb0  lea     rcx, [rdx+64h]; this
0x18000eeb7  jmp     ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
```
