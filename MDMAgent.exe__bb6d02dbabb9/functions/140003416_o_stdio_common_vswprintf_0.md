# _o___stdio_common_vswprintf_0

- ea: `0x140003416`
- end: `0x14000341c`
- name: `_o___stdio_common_vswprintf_0`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003554`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x140003416`

## pseudocode

```c
// attributes: thunk
int __cdecl o___stdio_common_vswprintf_0(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return __stdio_common_vswprintf(Options, Buffer, BufferCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x140003416  jmp     cs:__imp___stdio_common_vswprintf
```
