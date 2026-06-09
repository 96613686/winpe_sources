# operator delete(void *)

- ea: `0x18000dc30`
- end: `0x18000dc37`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800016f4`
- `0x180002100`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc30`

## pseudocode

```c
// attributes: thunk
HLOCAL __stdcall operator delete(HLOCAL hMem)
{
  return LocalFree(hMem);
}

```

## disassembly

```asm
0x18000dc30  jmp     cs:__imp_LocalFree
```
