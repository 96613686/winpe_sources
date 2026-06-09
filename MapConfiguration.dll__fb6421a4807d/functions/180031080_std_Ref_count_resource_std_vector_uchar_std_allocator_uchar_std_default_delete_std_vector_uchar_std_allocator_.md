# std::_Ref_count_resource<std::vector<uchar,std::allocator<uchar>> *,std::default_delete<std::vector<uchar,std::allocator<uchar>>>>::_Get_deleter(type_info const &)

- ea: `0x180031080`
- end: `0x1800310ac`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAV?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180031080`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180031094`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180031094`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<std::vector<unsigned char> *,std::default_delete<std::vector<unsigned char>>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_180079C48) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x180031080  push    rbx
0x180031082  sub     rsp, 20h
0x180031086  mov     rbx, rcx
0x180031089  lea     rcx, [rdx+8]
0x18003108d  lea     rdx, qword_180079C48
0x180031094  call    cs:__imp___std_type_info_compare
0x18003109a  test    eax, eax
0x18003109c  jnz     short loc_1800310A4
0x18003109e  lea     rax, [rbx+10h]
0x1800310a2  jmp     short loc_1800310A6
0x1800310a4  xor     eax, eax
0x1800310a6  add     rsp, 20h
0x1800310aa  pop     rbx
0x1800310ab  retn
```
