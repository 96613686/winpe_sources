# __scrt_set_unhandled_exception_filter

- ea: `0x140001170`
- end: `0x14000117e`
- name: `__scrt_set_unhandled_exception_filter`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001a90`

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001177`

## pseudocode

```c
LPTOP_LEVEL_EXCEPTION_FILTER _scrt_set_unhandled_exception_filter()
{
  return SetUnhandledExceptionFilter((LPTOP_LEVEL_EXCEPTION_FILTER)_scrt_unhandled_exception_filter);
}

```

## disassembly

```asm
0x140001170  lea     rcx, __scrt_unhandled_exception_filter
0x140001177  jmp     cs:__imp_SetUnhandledExceptionFilter
```
