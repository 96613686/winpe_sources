# __threadid

- ea: `0x18000695c`
- end: `0x180006963`
- name: `__threadid`
- size: `7`
- prototype: `unsigned int __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000695c`

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
0x18000695c  jmp     cs:__imp_GetCurrentThreadId
```
