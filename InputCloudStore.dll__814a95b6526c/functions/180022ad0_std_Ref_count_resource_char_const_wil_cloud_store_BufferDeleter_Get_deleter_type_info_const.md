# std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::_Get_deleter(type_info const &)

- ea: `0x180022ad0`
- end: `0x180022afc`
- name: `?_Get_deleter@?$_Ref_count_resource@PEBDVBufferDeleter@cloud_store@wil@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022ad0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180022ae4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180022ae4`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_180040288) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x180022ad0  push    rbx
0x180022ad2  sub     rsp, 20h
0x180022ad6  mov     rbx, rcx
0x180022ad9  lea     rcx, [rdx+8]
0x180022add  lea     rdx, qword_180040288
0x180022ae4  call    cs:__imp___std_type_info_compare
0x180022aea  test    eax, eax
0x180022aec  jnz     short loc_180022AF4
0x180022aee  lea     rax, [rbx+10h]
0x180022af2  jmp     short loc_180022AF6
0x180022af4  xor     eax, eax
0x180022af6  add     rsp, 20h
0x180022afa  pop     rbx
0x180022afb  retn
```
