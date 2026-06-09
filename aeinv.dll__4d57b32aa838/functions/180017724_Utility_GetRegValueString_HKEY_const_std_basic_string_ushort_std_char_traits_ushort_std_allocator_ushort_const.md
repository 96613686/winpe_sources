# Utility::GetRegValueString(HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180017724`
- end: `0x180017962`
- name: `?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z`
- size: `574`
- prototype: `__int64 __fastcall(__int64, HKEY, const WCHAR *, const WCHAR *)`
- caller_count: `15`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180007824`
- `0x180017968`
- `0x180019edc`
- `0x18002bf3c`
- `0x18002bff4`
- `0x18002e8f8`
- `0x18003c10c`
- `0x18003d33c`
- `0x18004082c`
- `0x18004259c`
- `0x180050128`
- `0x180051d68`
- `0x18005241c`
- `0x1800fbe58`
- `0x180104040`

## callees

- `0x180017724`
- `0x180018a60`
- `0x180018ff4`
- `0x180040498`
- `0x180040500`
- `0x180059920`
- `0x180059cf0`
- `0x1801003f4`
- `0x180100418`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800177ab`
- `ADVAPI32!RegGetValueW` at `0x1800178ad`
- `ADVAPI32!RegGetValueW` at `0x1800177ab`
- `ADVAPI32!RegGetValueW` at `0x1800178ad`
- `KERNEL32!LocalAlloc` at `0x180017908`
- `KERNEL32!LocalAlloc` at `0x180017908`
- `KERNEL32!LocalFree` at `0x18001783d`
- `KERNEL32!LocalFree` at `0x18001783d`

## string_xrefs

- `0x18001793b`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`
- `0x180017950`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`

## pseudocode

```c

```
