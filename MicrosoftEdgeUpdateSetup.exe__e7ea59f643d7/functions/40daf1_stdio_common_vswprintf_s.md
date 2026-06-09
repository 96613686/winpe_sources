# ___stdio_common_vswprintf_s

- ea: `0x40daf1`
- end: `0x40db15`
- name: `___stdio_common_vswprintf_s`
- size: `36`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x401583`
- `0x403fc4`

## callees

- `0x40c668`

## pseudocode

```c
int __cdecl __stdio_common_vswprintf_s(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return common_vsprintf_s<wchar_t>(Options, SHIDWORD(Options), Buffer, BufferCount, (int)Format, Locale, (int)ArgList);
}

```

## disassembly

```asm
0x40daf1  mov     edi, edi
0x40daf3  push    ebp
0x40daf4  mov     ebp, esp
0x40daf6  push    [ebp+ArgList]; int
0x40daf9  push    [ebp+Locale]; struct __crt_locale_pointers *
0x40dafc  push    [ebp+Format]; int
0x40daff  push    [ebp+BufferCount]; int
0x40db02  push    [ebp+Buffer]; int
0x40db05  push    dword ptr [ebp+Options+4]; int
0x40db08  push    dword ptr [ebp+Options]; int
0x40db0b  call    ??$common_vsprintf_s@_W@@YAH_KQA_WIQB_WQAU__crt_locale_pointers@@QAD@Z
0x40db10  add     esp, 1Ch
0x40db13  pop     ebp
0x40db14  retn
```
