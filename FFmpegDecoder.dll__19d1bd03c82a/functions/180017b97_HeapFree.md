# HeapFree

- ea: `0x180017b97`
- end: `0x180017b9d`
- name: `HeapFree`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a04c`
- `0x18000a28c`
- `0x18000f3c0`
- `0x18001e287`
- `0x18001e376`
- `0x18001e465`
- `0x18001e9ef`
- `0x18001ede4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017b97`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall HeapFree(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)
{
  return __imp_HeapFree(hHeap, dwFlags, lpMem);
}

```

## disassembly

```asm
0x180017b97  jmp     cs:__imp_HeapFree
```
