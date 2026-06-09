# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::emplace_hint<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x180032dc8`
- end: `0x180032f30`
- name: `??$emplace_hint@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `360`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180032fa8`

## callees

- `0x18000aac4`
- `0x180032618`
- `0x180032cf8`
- `0x180032dc8`
- `0x1800335a0`
- `0x180033e04`
- `0x1800378cc`
- `0x180037ce4`
- `0x180038060`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180032e31`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180032e31`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace_hint<std::wstring>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v8; // r15
  _QWORD *v9; // rbp
  __int64 v10; // rcx
  __int64 v11; // rdx
  float v12; // xmm0_4
  __int64 v13; // rcx
  float v14; // xmm1_4
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v18; // [rsp+30h] [rbp-58h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-50h]
  _OWORD v20[4]; // [rsp+40h] [rbp-48h] BYREF

  v8 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a4);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_hint<std::wstring>(
    a1,
    v20,
    a3,
    a4,
    v8);
  if ( *((_QWORD *)&v20[0] + 1) )
  {
    *a2 = *((_QWORD *)&v20[0] + 1);
  }
  else
  {
    if ( *(_QWORD *)(a1 + 16) == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v18 = a1 + 8;
    v9 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    v19 = v9;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::wstring,void *>>>::construct<std::wstring,std::wstring>(
      v10,
      v9 + 2,
      a4);
    v11 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v11 < 0 )
      v12 = (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1))
          + (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1));
    else
      v12 = (float)(int)v11;
    v13 = *(_QWORD *)(a1 + 56);
    if ( v13 < 0 )
    {
      v15 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v13 >> 1);
      v14 = (float)(int)v15 + (float)(int)v15;
    }
    else
    {
      v14 = (float)(int)v13;
    }
    if ( (float)(v12 / v14) > *(float *)a1 )
    {
      v16 = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        a1,
        v16);
      v20[0] = *(_OWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_hint<std::wstring>(
                            a1,
                            v20,
                            a3,
                            (__int64)(v9 + 2),
                            v8);
    }
    v19 = 0;
    *a2 = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_new_node_before(
            a1,
            v8,
            *(_QWORD *)&v20[0],
            v9);
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(&v18);
  }
  return a2;
}

```

## disassembly

```asm
0x180032dc8  push    rbx
0x180032dca  push    rbp
0x180032dcb  push    rsi
0x180032dcc  push    rdi
0x180032dcd  push    r14
0x180032dcf  push    r15
0x180032dd1  sub     rsp, 58h
0x180032dd5  mov     r14, r9
0x180032dd8  mov     rbx, r8
0x180032ddb  mov     rsi, rdx
0x180032dde  mov     rdi, rcx
0x180032de1  mov     rcx, r9
0x180032de4  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180032de9  mov     r15, rax
0x180032dec  mov     [rsp+88h+var_68], rax
0x180032df1  mov     r9, r14
0x180032df4  mov     r8, rbx
0x180032df7  lea     rdx, [rsp+88h+var_48]
0x180032dfc  mov     rcx, rdi
0x180032dff  call    ??$_Find_hint@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@QEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_hint<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring const &,unsigned __int64)
0x180032e04  mov     rcx, qword ptr [rsp+88h+var_48+8]
0x180032e09  test    rcx, rcx
0x180032e0c  jz      short loc_180032E16
0x180032e0e  mov     [rsi], rcx
0x180032e11  jmp     loc_180032F20
0x180032e16  lea     rax, [rdi+8]
0x180032e1a  mov     rcx, 555555555555555h
0x180032e24  cmp     [rax+8], rcx
0x180032e28  jnz     short loc_180032E38
0x180032e2a  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180032e31  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180032e38  mov     [rsp+88h+var_58], rax
0x180032e3d  mov     [rsp+88h+var_50], 0
0x180032e46  mov     ecx, 30h ; '0'
0x180032e4b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180032e50  mov     rbp, rax
0x180032e53  mov     [rsp+88h+var_50], rax
0x180032e58  lea     rdx, [rax+10h]
0x180032e5c  mov     r8, r14
0x180032e5f  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::wstring,void *>>>::construct<std::wstring,std::wstring>(std::allocator<std::_List_node<std::wstring,void *>> &,std::wstring * const,std::wstring &&)
0x180032e64  nop
0x180032e65  mov     rdx, [rdi+10h]
0x180032e69  add     rdx, 1
0x180032e6d  xorps   xmm0, xmm0
0x180032e70  js      short loc_180032E79
0x180032e72  cvtsi2ss xmm0, rdx
0x180032e77  jmp     short loc_180032E91
0x180032e79  mov     rcx, rdx
0x180032e7c  shr     rcx, 1
0x180032e7f  mov     rax, rdx
0x180032e82  and     eax, 1
0x180032e85  or      rcx, rax
0x180032e88  cvtsi2ss xmm0, rcx
0x180032e8d  addss   xmm0, xmm0
0x180032e91  mov     rcx, [rdi+38h]
0x180032e95  xorps   xmm1, xmm1
0x180032e98  test    rcx, rcx
0x180032e9b  js      short loc_180032EA4
0x180032e9d  cvtsi2ss xmm1, rcx
0x180032ea2  jmp     short loc_180032EB9
0x180032ea4  mov     rax, rcx
0x180032ea7  shr     rax, 1
0x180032eaa  and     ecx, 1
0x180032ead  or      rax, rcx
0x180032eb0  cvtsi2ss xmm1, rax
0x180032eb5  addss   xmm1, xmm1
0x180032eb9  divss   xmm0, xmm1
0x180032ebd  comiss  xmm0, dword ptr [rdi]
0x180032ec0  jbe     short loc_180032EF7
0x180032ec2  mov     rcx, rdi
0x180032ec5  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180032eca  mov     rdx, rax
0x180032ecd  mov     rcx, rdi
0x180032ed0  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(unsigned __int64)
0x180032ed5  lea     r9, [rbp+10h]
0x180032ed9  mov     [rsp+88h+var_68], r15
0x180032ede  mov     r8, rbx
0x180032ee1  lea     rdx, [rsp+88h+var_48]
0x180032ee6  mov     rcx, rdi
0x180032ee9  call    ??$_Find_hint@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@QEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_hint<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring const &,unsigned __int64)
0x180032eee  movups  xmm0, xmmword ptr [rax]
0x180032ef1  movdqu  [rsp+88h+var_48], xmm0
0x180032ef7  mov     [rsp+88h+var_50], 0
0x180032f00  mov     r9, rbp
0x180032f03  mov     r8, qword ptr [rsp+88h+var_48]
0x180032f08  mov     rdx, r15
0x180032f0b  mov     rcx, rdi
0x180032f0e  call    ?_Insert_new_node_before@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::wstring,void *> * const,std::_List_node<std::wstring,void *> * const)
0x180032f13  mov     [rsi], rax
0x180032f16  lea     rcx, [rsp+88h+var_58]
0x180032f1b  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(void)
0x180032f20  mov     rax, rsi
0x180032f23  add     rsp, 58h
0x180032f27  pop     r15
0x180032f29  pop     r14
0x180032f2b  pop     rdi
0x180032f2c  pop     rsi
0x180032f2d  pop     rbp
0x180032f2e  pop     rbx
0x180032f2f  retn
```
