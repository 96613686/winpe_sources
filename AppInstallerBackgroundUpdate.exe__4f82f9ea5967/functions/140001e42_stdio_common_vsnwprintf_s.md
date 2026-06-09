# __stdio_common_vsnwprintf_s

- ea: `0x140001e42`
- end: `0x140001e48`
- name: `__stdio_common_vsnwprintf_s`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, size_t MaxCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001f5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsnwprintf_s` at `0x140001e42`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vsnwprintf_s(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        size_t MaxCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return _o___stdio_common_vsnwprintf_s(Options, Buffer, BufferCount, MaxCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x140001e42  jmp     cs:__imp__o___stdio_common_vsnwprintf_s
```
