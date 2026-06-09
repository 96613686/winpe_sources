# std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Compile(void)

- ea: `0x18001970c`
- end: `0x180019790`
- name: `?_Compile@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@QEAAPEAV_Root_node@23@XZ`
- size: `132`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000f068`

## callees

- `0x18000bb30`
- `0x18000f418`
- `0x180012444`
- `0x180018ea4`
- `0x18001970c`
- `0x180019970`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Compile(
        __int64 a1)
{
  __int64 *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rsi
  struct std::tr1::_Node_base *v5; // r8
  __int64 result; // rax

  v2 = (__int64 *)(a1 + 40);
  v3 = a1 + 40;
  try
  {
    v4 = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Begin_capture_group(v3);
    std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Disjunction(a1);
    if ( *(_QWORD *)a1 != *(_QWORD *)(a1 + 16) )
      std::tr1::_Xbad(14);
    std::tr1::_Builder<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_End_group(v2, v4);
    std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_New_node(
      v2,
      21);
    result = *v2;
    *(_DWORD *)(result + 32) = *(_DWORD *)(a1 + 88);
    *(_DWORD *)(result + 36) = *(_DWORD *)(a1 + 24) + 1;
  }
  catch ( ... )
  {
    std::tr1::_Destroy_node(*(std::tr1 **)(a1 + 40), 0, v5);
    *(_QWORD *)(a1 + 40) = 0;
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001970c  mov     rax, rsp
0x18001970f  mov     [rax+8], rcx
0x180019713  push    rdi
0x180019714  sub     rsp, 30h
0x180019718  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180019720  mov     [rax+10h], rbx
0x180019724  mov     [rax+18h], rsi
0x180019728  mov     rbx, rcx
0x18001972b  lea     rdi, [rcx+28h]
0x18001972f  xor     edx, edx
0x180019731  mov     rcx, rdi
0x180019734  call    ?_Begin_capture_group@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAPEAV_Node_base@23@I@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Begin_capture_group(uint)
0x180019739  mov     rsi, rax
0x18001973c  mov     rcx, rbx
0x18001973f  call    ?_Disjunction@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAXXZ; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Disjunction(void)
0x180019744  mov     rcx, [rbx+10h]
0x180019748  cmp     [rbx], rcx
0x18001974b  jz      short loc_180019757
0x18001974d  mov     ecx, 0Eh
0x180019752  call    ?_Xbad@tr1@std@@YAXW4error_type@regex_constants@12@@Z; std::tr1::_Xbad(std::tr1::regex_constants::error_type)
0x180019757  mov     rdx, rsi
0x18001975a  mov     rcx, rdi
0x18001975d  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@QEAAXPEAV_Node_base@23@@Z; std::tr1::_Builder<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_End_group(std::tr1::_Node_base *)
0x180019762  mov     edx, 15h
0x180019767  mov     rcx, rdi
0x18001976a  call    ?_New_node@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAPEAV_Node_base@23@W4_Node_type@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_New_node(std::tr1::_Node_type)
0x18001976f  mov     rax, [rdi]
0x180019772  mov     ecx, [rbx+58h]
0x180019775  mov     [rax+20h], ecx
0x180019778  mov     ecx, [rbx+18h]
0x18001977b  inc     ecx
0x18001977d  mov     [rax+24h], ecx
0x180019780  mov     rbx, [rsp+38h+arg_8]
0x180019785  mov     rsi, [rsp+38h+arg_10]
0x18001978a  add     rsp, 30h
0x18001978e  pop     rdi
0x18001978f  retn
```
