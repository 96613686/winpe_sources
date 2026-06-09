# WINRT_IMPL_HeapFree

- ea: `0x180002d20`
- end: `0x180002d26`
- name: `WINRT_IMPL_HeapFree`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180006a74`
- `0x18000c8a4`
- `0x18000e257`
- `0x18000e4d4`
- `0x18000e927`
- `0x18000ea20`
- `0x18000eb19`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d20`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall WINRT_IMPL_HeapFree(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)
{
  return HeapFree(hHeap, dwFlags, lpMem);
}

```

## disassembly

```asm
0x180002d20  jmp     cs:__imp_HeapFree
```
