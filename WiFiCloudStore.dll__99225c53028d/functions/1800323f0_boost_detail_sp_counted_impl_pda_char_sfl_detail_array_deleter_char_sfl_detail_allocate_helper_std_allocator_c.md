# boost::detail::sp_counted_impl_pda<char *,sfl::detail::array_deleter<char>,sfl::detail::allocate_helper<std::allocator<char>,char,char>>::get_deleter(type_info const &)

- ea: `0x1800323f0`
- end: `0x18003241f`
- name: `?get_deleter@?$sp_counted_impl_pda@PEADV?$array_deleter@D@detail@sfl@@V?$allocate_helper@V?$allocator@D@std@@DD@23@@detail@boost@@UEAAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180032404`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180032404`

## pseudocode

```c
__int64 __fastcall boost::detail::sp_counted_impl_pda<char *,sfl::detail::array_deleter<char>,sfl::detail::allocate_helper<std::allocator<char>,char,char>>::get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_180052178);
  v4 = a1 + 24;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x1800323f0  push    rbx
0x1800323f2  sub     rsp, 20h
0x1800323f6  mov     rbx, rcx
0x1800323f9  lea     rcx, [rdx+8]
0x1800323fd  lea     rdx, qword_180052178
0x180032404  call    cs:__imp___std_type_info_compare
0x18003240a  xor     ecx, ecx
0x18003240c  lea     rdx, [rbx+18h]
0x180032410  test    eax, eax
0x180032412  cmovnz  rdx, rcx
0x180032416  mov     rax, rdx
0x180032419  add     rsp, 20h
0x18003241d  pop     rbx
0x18003241e  retn
```
