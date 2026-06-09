# HeapCompact_0

- ea: `0x180078d60`
- end: `0x180078d66`
- name: `HeapCompact_0`
- size: `6`
- prototype: `SIZE_T __stdcall(HANDLE hHeap, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCompact` at `0x180078d60`

## pseudocode

```c
// attributes: thunk
SIZE_T __stdcall HeapCompact_0(HANDLE hHeap, DWORD dwFlags)
{
  return HeapCompact(hHeap, dwFlags);
}

```

## disassembly

```asm
0x180078d60  jmp     cs:__imp_HeapCompact
```
