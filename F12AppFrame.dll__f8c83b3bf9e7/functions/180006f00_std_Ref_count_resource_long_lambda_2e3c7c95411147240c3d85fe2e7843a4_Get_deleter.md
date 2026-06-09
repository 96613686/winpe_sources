# std::_Ref_count_resource_long____lambda_2e3c7c95411147240c3d85fe2e7843a4___::_Get_deleter

- ea: `0x180006f00`
- end: `0x180006f2f`
- name: `std::_Ref_count_resource_long____lambda_2e3c7c95411147240c3d85fe2e7843a4___::_Get_deleter`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180006f14`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180006f14`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource_long____lambda_2e3c7c95411147240c3d85fe2e7843a4___::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_18004BB18);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x180006f00  push    rbx
0x180006f02  sub     rsp, 20h
0x180006f06  mov     rbx, rcx
0x180006f09  lea     rcx, [rdx+8]
0x180006f0d  lea     rdx, qword_18004BB18
0x180006f14  call    cs:__imp___std_type_info_compare
0x180006f1a  xor     ecx, ecx
0x180006f1c  lea     rdx, [rbx+10h]
0x180006f20  test    eax, eax
0x180006f22  cmovnz  rdx, rcx
0x180006f26  mov     rax, rdx
0x180006f29  add     rsp, 20h
0x180006f2d  pop     rbx
0x180006f2e  retn
```
