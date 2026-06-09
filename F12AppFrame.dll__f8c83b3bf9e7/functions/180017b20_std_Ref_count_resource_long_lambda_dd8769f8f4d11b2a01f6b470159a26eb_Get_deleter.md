# std::_Ref_count_resource_long____lambda_dd8769f8f4d11b2a01f6b470159a26eb___::_Get_deleter

- ea: `0x180017b20`
- end: `0x180017b4f`
- name: `std::_Ref_count_resource_long____lambda_dd8769f8f4d11b2a01f6b470159a26eb___::_Get_deleter`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180017b34`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180017b34`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource_long____lambda_dd8769f8f4d11b2a01f6b470159a26eb___::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_18004BB98);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x180017b20  push    rbx
0x180017b22  sub     rsp, 20h
0x180017b26  mov     rbx, rcx
0x180017b29  lea     rcx, [rdx+8]
0x180017b2d  lea     rdx, qword_18004BB98
0x180017b34  call    cs:__imp___std_type_info_compare
0x180017b3a  xor     ecx, ecx
0x180017b3c  lea     rdx, [rbx+10h]
0x180017b40  test    eax, eax
0x180017b42  cmovnz  rdx, rcx
0x180017b46  mov     rax, rdx
0x180017b49  add     rsp, 20h
0x180017b4d  pop     rbx
0x180017b4e  retn
```
