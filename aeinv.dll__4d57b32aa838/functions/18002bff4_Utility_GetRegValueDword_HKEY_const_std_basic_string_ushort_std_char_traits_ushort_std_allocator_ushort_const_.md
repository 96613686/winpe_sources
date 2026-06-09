# Utility::GetRegValueDword(HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18002bff4`
- end: `0x18002c138`
- name: `?GetRegValueDword@Utility@@SAKQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z`
- size: `324`
- prototype: `__int64 __fastcall(HKEY, _QWORD *, _QWORD *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007824`
- `0x18002bf3c`
- `0x18005241c`

## callees

- `0x180017724`
- `0x180018a60`
- `0x18002bff4`
- `0x1800404c4`
- `0x180059920`
- `0x180100418`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002c0ea`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002c0ea`
- `ADVAPI32!RegGetValueW` at `0x18002c06c`
- `ADVAPI32!RegGetValueW` at `0x18002c06c`

## string_xrefs

- `0x18002c126`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`

## pseudocode

```c

```
