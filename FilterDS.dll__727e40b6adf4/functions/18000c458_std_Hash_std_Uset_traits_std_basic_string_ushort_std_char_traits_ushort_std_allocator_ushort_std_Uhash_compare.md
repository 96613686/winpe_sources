# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Check_size(void)

- ea: `0x18000c458`
- end: `0x18000c52c`
- name: `?_Check_size@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ`
- size: `212`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007e50`

## callees

- `0x180007e50`
- `0x18000c458`
- `0x18000c794`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_size(
        __int64 a1)
{
  __int64 v1; // r8
  __int64 v3; // rdx
  float v4; // xmm0_4
  __int64 v5; // rax
  float v6; // xmm1_4
  __int64 *v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rbx
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 48);
  if ( v1 < 0 )
  {
    v5 = *(_QWORD *)(a1 + 8) & 1LL | (*(_QWORD *)(a1 + 8) >> 1);
    v4 = (float)(int)v5 + (float)(int)v5;
  }
  else
  {
    v4 = (float)(int)v1;
  }
  if ( v3 < 0 )
    v6 = (float)(int)(*(_DWORD *)(a1 + 48) & 1 | ((unsigned __int64)v3 >> 1))
       + (float)(int)(*(_DWORD *)(a1 + 48) & 1 | ((unsigned __int64)v3 >> 1));
  else
    v6 = (float)(int)v3;
  if ( (float)(v4 / v6) > *(float *)(a1 + 56) )
  {
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(a1);
    v7 = *(__int64 **)a1;
    if ( (__int64 *)*v7 != v7 )
    {
      v8 = v7[1];
      do
      {
        v9 = **(_QWORD **)a1;
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert<std::wstring const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
          a1,
          (__int64)v10,
          (_QWORD *)(v9 + 16),
          (_QWORD **)v9);
      }
      while ( v9 != v8 );
    }
  }
}

```

## disassembly

```asm
0x18000c458  mov     [rsp+arg_0], rbx
0x18000c45d  mov     [rsp+arg_8], rsi
0x18000c462  push    rdi
0x18000c463  sub     rsp, 30h
0x18000c467  mov     r8, [rcx+8]
0x18000c46b  mov     rdi, rcx
0x18000c46e  mov     rdx, [rcx+30h]
0x18000c472  xorps   xmm0, xmm0
0x18000c475  test    r8, r8
0x18000c478  js      short loc_18000C481
0x18000c47a  cvtsi2ss xmm0, r8
0x18000c47f  jmp     short loc_18000C497
0x18000c481  mov     rax, r8
0x18000c484  and     r8d, 1
0x18000c488  shr     rax, 1
0x18000c48b  or      rax, r8
0x18000c48e  cvtsi2ss xmm0, rax
0x18000c493  addss   xmm0, xmm0
0x18000c497  xorps   xmm1, xmm1
0x18000c49a  test    rdx, rdx
0x18000c49d  js      short loc_18000C4A6
0x18000c49f  cvtsi2ss xmm1, rdx
0x18000c4a4  jmp     short loc_18000C4BE
0x18000c4a6  mov     rax, rdx
0x18000c4a9  mov     rcx, rdx
0x18000c4ac  shr     rcx, 1
0x18000c4af  and     eax, 1
0x18000c4b2  or      rcx, rax
0x18000c4b5  cvtsi2ss xmm1, rcx
0x18000c4ba  addss   xmm1, xmm1
0x18000c4be  divss   xmm0, xmm1
0x18000c4c2  comiss  xmm0, dword ptr [rdi+38h]
0x18000c4c6  jbe     short loc_18000C51C
0x18000c4c8  cmp     rdx, 200h
0x18000c4cf  jnb     short loc_18000C4D7
0x18000c4d1  shl     rdx, 3
0x18000c4d5  jmp     short loc_18000C4E9
0x18000c4d7  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000c4e1  cmp     rdx, rax
0x18000c4e4  jnb     short loc_18000C4E9
0x18000c4e6  add     rdx, rdx
0x18000c4e9  mov     rcx, rdi
0x18000c4ec  call    ?_Init@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(unsigned __int64)
0x18000c4f1  mov     rax, [rdi]
0x18000c4f4  cmp     [rax], rax
0x18000c4f7  jz      short loc_18000C51C
0x18000c4f9  mov     rsi, [rax+8]
0x18000c4fd  mov     rbx, [rdi]
0x18000c500  lea     rdx, [rsp+38h+var_18]
0x18000c505  mov     rcx, rdi
0x18000c508  mov     rbx, [rbx]
0x18000c50b  mov     r9, rbx
0x18000c50e  lea     r8, [rbx+10h]
0x18000c512  call    ??$_Insert@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert<std::wstring const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(std::wstring const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18000c517  cmp     rbx, rsi
0x18000c51a  jnz     short loc_18000C4FD
0x18000c51c  mov     rbx, [rsp+38h+arg_0]
0x18000c521  mov     rsi, [rsp+38h+arg_8]
0x18000c526  add     rsp, 30h
0x18000c52a  pop     rdi
0x18000c52b  retn
```
