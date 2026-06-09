# __scrt_set_unhandled_exception_filter

- ea: `0x1400017f0`
- end: `0x1400017fe`
- name: `__scrt_set_unhandled_exception_filter`
- size: `14`
- prototype: `LPTOP_LEVEL_EXCEPTION_FILTER()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400017f7`

## pseudocode

```c
LPTOP_LEVEL_EXCEPTION_FILTER _scrt_set_unhandled_exception_filter()
{
  return SetUnhandledExceptionFilter((LPTOP_LEVEL_EXCEPTION_FILTER)_scrt_unhandled_exception_filter);
}

```

## disassembly

```asm
0x1400017f0  lea     rcx, __scrt_unhandled_exception_filter
0x1400017f7  jmp     cs:__imp_SetUnhandledExceptionFilter
```
