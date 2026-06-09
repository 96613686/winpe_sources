# type_info::operator==(type_info const &)

- ea: `0x18000e96c`
- end: `0x18000e988`
- name: `??8type_info@@QEBA_NAEBV0@@Z`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180011c60`
- `0x1800126d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000e978`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000e978`

## pseudocode

```c
bool __fastcall type_info::operator==(__int64 a1, __int64 a2)
{
  return (unsigned int)__std_type_info_compare(a1 + 8, a2 + 8) == 0;
}

```

## disassembly

```asm
0x18000e96c  sub     rsp, 28h
0x18000e970  add     rdx, 8
0x18000e974  add     rcx, 8
0x18000e978  call    cs:__imp___std_type_info_compare
0x18000e97e  test    eax, eax
0x18000e980  setz    al
0x18000e983  add     rsp, 28h
0x18000e987  retn
```
