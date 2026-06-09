# _o__seh_filter_dll_0

- ea: `0x180002618`
- end: `0x18000261e`
- name: `_o__seh_filter_dll_0`
- size: `6`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001d40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__seh_filter_dll` at `0x180002618`

## pseudocode

```c
// attributes: thunk
int __cdecl o__seh_filter_dll_0(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  return _seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180002618  jmp     cs:__imp__seh_filter_dll
```
