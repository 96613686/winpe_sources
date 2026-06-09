# _seh_filter_dll

- ea: `0x18007ba29`
- end: `0x18007ba2f`
- name: `_seh_filter_dll`
- size: `6`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18007ac44`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_seh_filter_dll` at `0x18007ba29`

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
0x18007ba29  jmp     cs:__imp__seh_filter_dll
```
