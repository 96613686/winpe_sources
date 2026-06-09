# type_info::operator==(type_info const &)

- ea: `0x18001f2bc`
- end: `0x18001f2d8`
- name: `??8type_info@@QEBA_NAEBV0@@Z`
- size: `28`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180056a90`
- `0x1800575e4`
- `0x18006a07c`
- `0x18007f990`
- `0x1800c7910`
- `0x1800d1320`
- `0x1800d1360`
- `0x1800d13a0`
- `0x1800d13e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001f2c8`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001f2c8`

## pseudocode

```c
bool __fastcall type_info::operator==(__int64 a1, __int64 a2)
{
  return (unsigned int)__std_type_info_compare(a1 + 8, a2 + 8) == 0;
}

```

## disassembly

```asm
0x18001f2bc  sub     rsp, 28h
0x18001f2c0  add     rdx, 8
0x18001f2c4  add     rcx, 8
0x18001f2c8  call    cs:__imp___std_type_info_compare
0x18001f2ce  test    eax, eax
0x18001f2d0  setz    al
0x18001f2d3  add     rsp, 28h
0x18001f2d7  retn
```
