# boost::detail::sp_counted_impl_pda<char *,sfl::detail::array_deleter<char>,sfl::detail::allocate_helper<std::allocator<char>,char,char>>::get_deleter(type_info const &)

- ea: `0x180016f70`
- end: `0x180016f9f`
- name: `?get_deleter@?$sp_counted_impl_pda@PEADV?$array_deleter@D@detail@sfl@@V?$allocate_helper@V?$allocator@D@std@@DD@23@@detail@boost@@UEAAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180016f84`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180016f84`

## pseudocode

```c
__int64 __fastcall boost::detail::sp_counted_impl_pda<char *,sfl::detail::array_deleter<char>,sfl::detail::allocate_helper<std::allocator<char>,char,char>>::get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_1800461F8);
  v4 = a1 + 24;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x180016f70  push    rbx
0x180016f72  sub     rsp, 20h
0x180016f76  mov     rbx, rcx
0x180016f79  lea     rcx, [rdx+8]
0x180016f7d  lea     rdx, qword_1800461F8
0x180016f84  call    cs:__imp___std_type_info_compare
0x180016f8a  xor     ecx, ecx
0x180016f8c  lea     rdx, [rbx+18h]
0x180016f90  test    eax, eax
0x180016f92  cmovnz  rdx, rcx
0x180016f96  mov     rax, rdx
0x180016f99  add     rsp, 20h
0x180016f9d  pop     rbx
0x180016f9e  retn
```
