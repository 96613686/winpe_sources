# _MosStorageEnsureMapDataDirectoryAndKeepFileHandle_::_1_::dtor$1

- ea: `0x18000edfc`
- end: `0x18000ee08`
- name: `_MosStorageEnsureMapDataDirectoryAndKeepFileHandle_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006d5c`

## pseudocode

```c
void __fastcall MosStorageEnsureMapDataDirectoryAndKeepFileHandle_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CallingStateTracker::~CallingStateTracker((CallingStateTracker *)(a2 + 168));
}

```

## disassembly

```asm
0x18000edfc  lea     rcx, [rdx+0A8h]; this
0x18000ee03  jmp     ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
```
