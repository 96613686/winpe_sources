# std::_Ref_count_resource_bool____lambda_37637c8b52e7f5910352e2380eaa98ac___::_Get_deleter

- ea: `0x18002b700`
- end: `0x18002b72f`
- name: `std::_Ref_count_resource_bool____lambda_37637c8b52e7f5910352e2380eaa98ac___::_Get_deleter`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b714`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b714`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource_bool____lambda_37637c8b52e7f5910352e2380eaa98ac___::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_18004BF48);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18002b700  push    rbx
0x18002b702  sub     rsp, 20h
0x18002b706  mov     rbx, rcx
0x18002b709  lea     rcx, [rdx+8]
0x18002b70d  lea     rdx, qword_18004BF48
0x18002b714  call    cs:__imp___std_type_info_compare
0x18002b71a  xor     ecx, ecx
0x18002b71c  lea     rdx, [rbx+10h]
0x18002b720  test    eax, eax
0x18002b722  cmovnz  rdx, rcx
0x18002b726  mov     rax, rdx
0x18002b729  add     rsp, 20h
0x18002b72d  pop     rbx
0x18002b72e  retn
```
