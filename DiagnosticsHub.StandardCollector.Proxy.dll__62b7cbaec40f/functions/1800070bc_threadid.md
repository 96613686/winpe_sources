# __threadid

- ea: `0x1800070bc`
- end: `0x1800070c3`
- name: `__threadid`
- size: `7`
- prototype: `unsigned int __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800070bc`

## pseudocode

```c
// attributes: thunk
unsigned int __cdecl _threadid()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x1800070bc  jmp     cs:__imp_GetCurrentThreadId
```
