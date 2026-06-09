# DummyRemoveRTMemorySection(void *)

- ea: `0x18000de50`
- end: `0x18000de53`
- name: `?DummyRemoveRTMemorySection@@YAJPEAX@Z`
- size: `3`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e970`

## pseudocode

```c
__int64 __fastcall DummyRemoveRTMemorySection(void *a1)
{
  return 0;
}

```

## disassembly

```asm
0x18000de50  xor     eax, eax
0x18000de52  retn
```
