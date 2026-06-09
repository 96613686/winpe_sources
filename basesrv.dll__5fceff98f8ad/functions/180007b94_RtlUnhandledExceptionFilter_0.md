# RtlUnhandledExceptionFilter_0

- ea: `0x180007b94`
- end: `0x180007b9a`
- name: `RtlUnhandledExceptionFilter_0`
- size: `6`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180007858`
- `0x180007880`

## import_xrefs

- `ntdll!RtlUnhandledExceptionFilter` at `0x180007b94`

## pseudocode

```c
// attributes: thunk
LONG __stdcall RtlUnhandledExceptionFilter_0(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  return RtlUnhandledExceptionFilter(ExceptionInfo);
}

```

## disassembly

```asm
0x180007b94  jmp     cs:__imp_RtlUnhandledExceptionFilter
```
