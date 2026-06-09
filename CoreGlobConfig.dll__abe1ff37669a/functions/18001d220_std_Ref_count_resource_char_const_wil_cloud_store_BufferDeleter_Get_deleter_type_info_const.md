# std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::_Get_deleter(type_info const &)

- ea: `0x18001d220`
- end: `0x18001d24c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEBDVBufferDeleter@cloud_store@wil@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d220`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001d234`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001d234`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_1800324E8) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x18001d220  push    rbx
0x18001d222  sub     rsp, 20h
0x18001d226  mov     rbx, rcx
0x18001d229  lea     rcx, [rdx+8]
0x18001d22d  lea     rdx, qword_1800324E8
0x18001d234  call    cs:__imp___std_type_info_compare
0x18001d23a  test    eax, eax
0x18001d23c  jnz     short loc_18001D244
0x18001d23e  lea     rax, [rbx+10h]
0x18001d242  jmp     short loc_18001D246
0x18001d244  xor     eax, eax
0x18001d246  add     rsp, 20h
0x18001d24a  pop     rbx
0x18001d24b  retn
```
