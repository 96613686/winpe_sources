# std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::_Get_deleter(type_info const &)

- ea: `0x1800321f0`
- end: `0x18003221c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEBDVBufferDeleter@cloud_store@wil@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800321f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180032204`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180032204`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_180052240) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x1800321f0  push    rbx
0x1800321f2  sub     rsp, 20h
0x1800321f6  mov     rbx, rcx
0x1800321f9  lea     rcx, [rdx+8]
0x1800321fd  lea     rdx, qword_180052240
0x180032204  call    cs:__imp___std_type_info_compare
0x18003220a  test    eax, eax
0x18003220c  jnz     short loc_180032214
0x18003220e  lea     rax, [rbx+10h]
0x180032212  jmp     short loc_180032216
0x180032214  xor     eax, eax
0x180032216  add     rsp, 20h
0x18003221a  pop     rbx
0x18003221b  retn
```
