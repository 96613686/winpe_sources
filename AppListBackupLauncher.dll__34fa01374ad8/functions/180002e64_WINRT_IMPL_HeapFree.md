# WINRT_IMPL_HeapFree

- ea: `0x180002e64`
- end: `0x180002e6a`
- name: `WINRT_IMPL_HeapFree`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005314`
- `0x18000ed6c`
- `0x180010858`
- `0x180010ad5`
- `0x180010e6d`
- `0x180010f66`
- `0x18001105f`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e64`

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
0x180002e64  jmp     cs:__imp_HeapFree
```
