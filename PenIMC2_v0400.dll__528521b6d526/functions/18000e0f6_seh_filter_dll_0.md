# _seh_filter_dll_0

- ea: `0x18000e0f6`
- end: `0x18000e0fc`
- name: `_seh_filter_dll_0`
- size: `6`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000d180`

## import_xrefs

- `ucrtbase_clr0400!_seh_filter_dll` at `0x18000e0f6`

## pseudocode

```c
// attributes: thunk
int __cdecl seh_filter_dll_0(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  return _seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000e0f6  jmp     cs:__imp__seh_filter_dll
```
