# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001b858`
- end: `0x18001b999`
- name: `??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `321`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001b838`

## callees

- `0x180005b70`
- `0x18000a188`
- `0x18000a1a8`
- `0x18001956c`
- `0x18001b634`
- `0x18001b858`
- `0x18001b9a0`
- `0x18001b9d0`
- `0x18003bb10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        _QWORD *a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rbp
  _QWORD *v10; // rbx
  _QWORD *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v16; // rbp
  _QWORD v17[9]; // [rsp+20h] [rbp-48h] BYREF

  v6 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a3);
  v7 = a1[3];
  v8 = *(_QWORD *)(v7 + 16 * (a1[6] & v6) + 8);
  v9 = a1[1];
  if ( v8 == v9 )
  {
LABEL_2:
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_max_size(a1);
    v17[0] = a1 + 1;
    v10 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    v17[1] = v10;
    std::wstring::wstring(v10 + 2, a3);
    if ( (unsigned __int8)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Rehash_for_1(a1);
      v9 = *std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
              a1,
              v17,
              v10 + 2,
              v6);
    }
    v11 = *(_QWORD **)(v9 + 8);
    ++a1[2];
    *v10 = v9;
    v10[1] = v11;
    *v11 = v10;
    *(_QWORD *)(v9 + 8) = v10;
    v12 = 2 * (v6 & a1[6]);
    v13 = a1[3];
    v14 = *(_QWORD *)(v13 + 16 * (v6 & a1[6]));
    if ( v14 == a1[1] )
    {
      *(_QWORD *)(v13 + 16 * (v6 & a1[6])) = v10;
    }
    else
    {
      if ( v14 == v9 )
      {
        *(_QWORD *)(v13 + 16 * (v6 & a1[6])) = v10;
        goto LABEL_7;
      }
      if ( *(_QWORD **)(v13 + 16 * (v6 & a1[6]) + 8) != v11 )
        goto LABEL_7;
    }
    *(_QWORD *)(v13 + 8 * v12 + 8) = v10;
LABEL_7:
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  v16 = *(_QWORD *)(v7 + 16 * (a1[6] & v6));
  while ( std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
            v7,
            (__int64)a3,
            v8 + 16) )
  {
    if ( v8 == v16 )
    {
      v9 = v8;
      goto LABEL_2;
    }
    v8 = *(_QWORD *)(v8 + 8);
  }
  *(_QWORD *)a2 = v8;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18001b858  push    rbx
0x18001b85a  push    rbp
0x18001b85b  push    rsi
0x18001b85c  push    rdi
0x18001b85d  push    r12
0x18001b85f  push    r14
0x18001b861  push    r15
0x18001b863  sub     rsp, 30h
0x18001b867  mov     r14, r8
0x18001b86a  mov     rdi, rdx
0x18001b86d  mov     rsi, rcx
0x18001b870  mov     rcx, r8; unsigned __int8 *
0x18001b873  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18001b878  mov     r15, rax
0x18001b87b  and     rax, [rsi+30h]
0x18001b87f  add     rax, rax
0x18001b882  mov     rcx, [rsi+18h]
0x18001b886  mov     rbx, [rcx+rax*8+8]
0x18001b88b  lea     r12, [rsi+8]
0x18001b88f  mov     rbp, [r12]
0x18001b893  cmp     rbx, rbp
0x18001b896  jnz     loc_18001B93C
0x18001b89c  mov     rcx, rsi
0x18001b89f  call    ?_Check_max_size@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBAXXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_max_size(void)
0x18001b8a4  mov     [rsp+68h+var_48], r12
0x18001b8a9  mov     [rsp+68h+var_40], 0
0x18001b8b2  mov     ecx, 30h ; '0'
0x18001b8b7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001b8bc  mov     rbx, rax
0x18001b8bf  mov     [rsp+68h+var_40], rax
0x18001b8c4  lea     rcx, [rax+10h]
0x18001b8c8  mov     rdx, r14
0x18001b8cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b8d0  nop
0x18001b8d1  mov     rcx, rsi
0x18001b8d4  call    ?_Check_rehash_required_1@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_NXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_rehash_required_1(void)
0x18001b8d9  test    al, al
0x18001b8db  jnz     loc_18001B963
0x18001b8e1  mov     rdx, [rbp+8]
0x18001b8e5  inc     qword ptr [rsi+10h]
0x18001b8e9  mov     [rbx], rbp
0x18001b8ec  mov     [rbx+8], rdx
0x18001b8f0  mov     [rdx], rbx
0x18001b8f3  mov     [rbp+8], rbx
0x18001b8f7  mov     rax, [rsi+30h]
0x18001b8fb  and     rax, r15
0x18001b8fe  add     rax, rax
0x18001b901  mov     rcx, [rsi+18h]
0x18001b905  mov     r8, [rcx+rax*8]
0x18001b909  cmp     r8, [r12]
0x18001b90d  jnz     short loc_18001B931
0x18001b90f  mov     [rcx+rax*8], rbx
0x18001b913  mov     [rcx+rax*8+8], rbx
0x18001b918  mov     [rdi], rbx
0x18001b91b  mov     byte ptr [rdi+8], 1
0x18001b91f  mov     rax, rdi
0x18001b922  add     rsp, 30h
0x18001b926  pop     r15
0x18001b928  pop     r14
0x18001b92a  pop     r12
0x18001b92c  pop     rdi
0x18001b92d  pop     rsi
0x18001b92e  pop     rbp
0x18001b92f  pop     rbx
0x18001b930  retn
0x18001b931  cmp     r8, rbp
0x18001b934  jnz     short loc_18001B987
0x18001b936  mov     [rcx+rax*8], rbx
0x18001b93a  jmp     short loc_18001B918
0x18001b93c  mov     rbp, [rcx+rax*8]
0x18001b940  lea     r8, [rbx+10h]
0x18001b944  mov     rdx, r14
0x18001b947  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18001b94c  test    al, al
0x18001b94e  jz      short loc_18001B990
0x18001b950  cmp     rbx, rbp
0x18001b953  jnz     short loc_18001B95D
0x18001b955  mov     rbp, rbx
0x18001b958  jmp     loc_18001B89C
0x18001b95d  mov     rbx, [rbx+8]
0x18001b961  jmp     short loc_18001B940
0x18001b963  mov     rcx, rsi
0x18001b966  call    ?_Rehash_for_1@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Rehash_for_1(void)
0x18001b96b  lea     r8, [rbx+10h]
0x18001b96f  mov     r9, r15
0x18001b972  lea     rdx, [rsp+68h+var_48]
0x18001b977  mov     rcx, rsi
0x18001b97a  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18001b97f  mov     rbp, [rax]
0x18001b982  jmp     loc_18001B8E1
0x18001b987  cmp     [rcx+rax*8+8], rdx
0x18001b98c  jnz     short loc_18001B918
0x18001b98e  jmp     short loc_18001B913
0x18001b990  mov     [rdi], rbx
0x18001b993  mov     byte ptr [rdi+8], 0
0x18001b997  jmp     short loc_18001B91F
```
