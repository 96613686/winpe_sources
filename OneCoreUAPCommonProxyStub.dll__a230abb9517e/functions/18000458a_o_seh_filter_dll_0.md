# _o__seh_filter_dll_0

- ea: `0x18000458a`
- end: `0x180004590`
- name: `_o__seh_filter_dll_0`
- size: `6`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003e84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__seh_filter_dll` at `0x18000458a`

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
0x18000458a  jmp     cs:__imp__seh_filter_dll
```
