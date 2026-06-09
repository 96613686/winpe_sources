# std::_Ref_count_resource_HKEY______lambda_47ef7a1cbce50a45ab0606f962b6bd7d___::_Get_deleter

- ea: `0x180027740`
- end: `0x18002776f`
- name: `std::_Ref_count_resource_HKEY______lambda_47ef7a1cbce50a45ab0606f962b6bd7d___::_Get_deleter`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180027754`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180027754`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource_HKEY______lambda_47ef7a1cbce50a45ab0606f962b6bd7d___::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_180044C38);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x180027740  push    rbx
0x180027742  sub     rsp, 20h
0x180027746  mov     rbx, rcx
0x180027749  lea     rcx, [rdx+8]
0x18002774d  lea     rdx, qword_180044C38
0x180027754  call    cs:__imp___std_type_info_compare
0x18002775a  xor     ecx, ecx
0x18002775c  lea     rdx, [rbx+10h]
0x180027760  test    eax, eax
0x180027762  cmovnz  rdx, rcx
0x180027766  mov     rax, rdx
0x180027769  add     rsp, 20h
0x18002776d  pop     rbx
0x18002776e  retn
```
