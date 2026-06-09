# __stdio_common_vsscanf

- ea: `0x1800168de`
- end: `0x1800168e4`
- name: `__stdio_common_vsscanf`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, const char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180016b18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsscanf` at `0x1800168de`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vsscanf(
        unsigned __int64 Options,
        const char *Buffer,
        size_t BufferCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return _o___stdio_common_vsscanf(Options, Buffer, BufferCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x1800168de  jmp     cs:__imp__o___stdio_common_vsscanf
```
