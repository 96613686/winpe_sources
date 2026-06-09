# _Thrd_id

- ea: `0x180017f3c`
- end: `0x180017f43`
- name: `_Thrd_id`
- size: `7`
- prototype: `_Thrd_id_t __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180017ff8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180017f3c`

## pseudocode

```c
// attributes: thunk
_Thrd_id_t __cdecl Thrd_id()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x180017f3c  jmp     cs:__imp_GetCurrentThreadId
```
