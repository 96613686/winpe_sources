# std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::_Get_deleter(type_info const &)

- ea: `0x180016660`
- end: `0x18001668c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEBDVBufferDeleter@cloud_store@wil@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016660`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180016674`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180016674`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_1800462C0) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x180016660  push    rbx
0x180016662  sub     rsp, 20h
0x180016666  mov     rbx, rcx
0x180016669  lea     rcx, [rdx+8]
0x18001666d  lea     rdx, qword_1800462C0
0x180016674  call    cs:__imp___std_type_info_compare
0x18001667a  test    eax, eax
0x18001667c  jnz     short loc_180016684
0x18001667e  lea     rax, [rbx+10h]
0x180016682  jmp     short loc_180016686
0x180016684  xor     eax, eax
0x180016686  add     rsp, 20h
0x18001668a  pop     rbx
0x18001668b  retn
```
