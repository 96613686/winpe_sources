# std::_Ref_count_resource<Pal::NetworkRequestImpl *,std::default_delete<Pal::NetworkRequestImpl>>::_Get_deleter(type_info const &)

- ea: `0x18002e720`
- end: `0x18002e74c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAVNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002e720`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002e734`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002e734`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<Pal::NetworkRequestImpl *,std::default_delete<Pal::NetworkRequestImpl>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_180079BF8) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x18002e720  push    rbx
0x18002e722  sub     rsp, 20h
0x18002e726  mov     rbx, rcx
0x18002e729  lea     rcx, [rdx+8]
0x18002e72d  lea     rdx, qword_180079BF8
0x18002e734  call    cs:__imp___std_type_info_compare
0x18002e73a  test    eax, eax
0x18002e73c  jnz     short loc_18002E744
0x18002e73e  lea     rax, [rbx+10h]
0x18002e742  jmp     short loc_18002E746
0x18002e744  xor     eax, eax
0x18002e746  add     rsp, 20h
0x18002e74a  pop     rbx
0x18002e74b  retn
```
