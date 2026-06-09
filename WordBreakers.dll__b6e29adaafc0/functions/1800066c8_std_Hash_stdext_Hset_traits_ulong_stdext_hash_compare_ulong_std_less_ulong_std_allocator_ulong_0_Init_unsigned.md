# std::_Hash<stdext::_Hset_traits<ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<ulong>,0>>::_Init(unsigned __int64)

- ea: `0x1800066c8`
- end: `0x18000674d`
- name: `?_Init@?$_Hash@V?$_Hset_traits@KV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@K@std@@$0A@@stdext@@@std@@IEAAX_K@Z`
- size: `133`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001ce0`

## callees

- `0x1800066c8`
- `0x180006754`
- `0x1800069ac`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<unsigned long>,0>>::_Init(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4)
{
  __int64 v4; // r8
  __int64 result; // rax
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = a2;
  v6 = a1;
  v4 = xmmword_180012C20;
  if ( (unsigned __int64)((qword_180012C30 - (__int64)xmmword_180012C20) >> 3) < 0x10 )
  {
    std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>>>>::_Reallocate(&xmmword_180012C20);
    v4 = xmmword_180012C20;
  }
  v7 = qword_180012C10;
  *((_QWORD *)&xmmword_180012C20 + 1) = v4;
  result = std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>>>>::_Insert_n(
             (unsigned int)&xmmword_180012C20,
             (unsigned int)&v6,
             v4,
             a4,
             (__int64)&v7);
  qword_180012C38 = 7;
  qword_180012C40 = 8;
  return result;
}

```

## disassembly

```asm
0x1800066c8  mov     [rsp+arg_8], rdx
0x1800066cd  mov     [rsp+arg_0], rcx
0x1800066d2  sub     rsp, 38h
0x1800066d6  mov     rax, cs:qword_180012C30
0x1800066dd  mov     r8, qword ptr cs:xmmword_180012C20
0x1800066e4  sub     rax, r8
0x1800066e7  sar     rax, 3
0x1800066eb  cmp     rax, 10h
0x1800066ef  jnb     short loc_180006704
0x1800066f1  lea     rcx, xmmword_180012C20
0x1800066f8  call    ?_Reallocate@?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>>>>::_Reallocate(unsigned __int64)
0x1800066fd  mov     r8, qword ptr cs:xmmword_180012C20
0x180006704  mov     rax, cs:qword_180012C10
0x18000670b  lea     rdx, [rsp+38h+arg_0]
0x180006710  mov     [rsp+38h+arg_8], rax
0x180006715  lea     rcx, xmmword_180012C20
0x18000671c  lea     rax, [rsp+38h+arg_8]
0x180006721  mov     qword ptr cs:xmmword_180012C20+8, r8
0x180006728  mov     [rsp+38h+var_18], rax
0x18000672d  call    ?_Insert_n@?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@@2@_KAEBV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@2@@Z; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>>>>,unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0> const &)
0x180006732  mov     cs:qword_180012C38, 7
0x18000673d  mov     cs:qword_180012C40, 8
0x180006748  add     rsp, 38h
0x18000674c  retn
```
