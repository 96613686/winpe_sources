# _seh_filter_dll

- ea: `0x180006c2b`
- end: `0x180006c31`
- name: `_seh_filter_dll`
- size: `6`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000186c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_seh_filter_dll` at `0x180006c2b`

## pseudocode

```c
// attributes: thunk
int __cdecl seh_filter_dll(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  return _seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180006c2b  jmp     cs:__imp__seh_filter_dll
```
