# __threadhandle

- ea: `0x180006954`
- end: `0x18000695b`
- name: `__threadhandle`
- size: `7`
- prototype: `uintptr_t __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180006954`

## pseudocode

```c
// attributes: thunk
uintptr_t __cdecl _threadhandle()
{
  return (uintptr_t)GetCurrentThread();
}

```

## disassembly

```asm
0x180006954  jmp     cs:__imp_GetCurrentThread
```
