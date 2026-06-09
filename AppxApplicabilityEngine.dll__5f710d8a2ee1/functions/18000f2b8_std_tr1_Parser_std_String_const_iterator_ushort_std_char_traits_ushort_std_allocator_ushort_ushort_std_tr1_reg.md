# std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Compile(void)

- ea: `0x18000f2b8`
- end: `0x18000f33c`
- name: `?_Compile@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAPEAV_Root_node@23@XZ`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000f11c`

## callees

- `0x18000b8d8`
- `0x18000f2b8`
- `0x18000f378`
- `0x18000f418`
- `0x180012444`
- `0x180018ea4`

## pseudocode

```c
__int64 __fastcall std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Compile(
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
    v4 = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Begin_capture_group(
           v3,
           0);
    std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Disjunction(a1);
    if ( *(_QWORD *)a1 != *(_QWORD *)(a1 + 16) )
      std::tr1::_Xbad(14);
    std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_End_group(
      v2,
      v4);
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
0x18000f2b8  mov     rax, rsp
0x18000f2bb  mov     [rax+8], rcx
0x18000f2bf  push    rdi
0x18000f2c0  sub     rsp, 30h
0x18000f2c4  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18000f2cc  mov     [rax+10h], rbx
0x18000f2d0  mov     [rax+18h], rsi
0x18000f2d4  mov     rbx, rcx
0x18000f2d7  lea     rdi, [rcx+28h]
0x18000f2db  xor     edx, edx
0x18000f2dd  mov     rcx, rdi
0x18000f2e0  call    ?_Begin_capture_group@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAPEAV_Node_base@23@I@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Begin_capture_group(uint)
0x18000f2e5  mov     rsi, rax
0x18000f2e8  mov     rcx, rbx
0x18000f2eb  call    ?_Disjunction@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAXXZ; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Disjunction(void)
0x18000f2f0  mov     rcx, [rbx+10h]
0x18000f2f4  cmp     [rbx], rcx
0x18000f2f7  jz      short loc_18000F303
0x18000f2f9  mov     ecx, 0Eh
0x18000f2fe  call    ?_Xbad@tr1@std@@YAXW4error_type@regex_constants@12@@Z; std::tr1::_Xbad(std::tr1::regex_constants::error_type)
0x18000f303  mov     rdx, rsi
0x18000f306  mov     rcx, rdi
0x18000f309  call    ?_End_group@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAXPEAV_Node_base@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_End_group(std::tr1::_Node_base *)
0x18000f30e  mov     edx, 15h
0x18000f313  mov     rcx, rdi
0x18000f316  call    ?_New_node@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAPEAV_Node_base@23@W4_Node_type@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_New_node(std::tr1::_Node_type)
0x18000f31b  mov     rax, [rdi]
0x18000f31e  mov     ecx, [rbx+58h]
0x18000f321  mov     [rax+20h], ecx
0x18000f324  mov     ecx, [rbx+18h]
0x18000f327  inc     ecx
0x18000f329  mov     [rax+24h], ecx
0x18000f32c  mov     rbx, [rsp+38h+arg_8]
0x18000f331  mov     rsi, [rsp+38h+arg_10]
0x18000f336  add     rsp, 30h
0x18000f33a  pop     rdi
0x18000f33b  retn
```
