# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180009b90`
- end: `0x180009d37`
- name: `?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008428`

## callees

- `0x180007afc`
- `0x180008888`
- `0x18000939c`
- `0x180009960`
- `0x180009b90`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009bd0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009bd0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // r12
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbp
  __int64 v13; // r14
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  _QWORD *v16; // r8
  _QWORD *v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  _QWORD **v20; // r8
  _QWORD *v21; // r8
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rdx
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  __int64 v29; // [rsp+78h] [rbp+10h] BYREF

  LODWORD(v29) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  LODWORD(v29) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    a1 + 3,
    2 * v7,
    v4);
  a1[7] = v7;
  a1[6] = v7 - 1;
  v8 = *(_QWORD **)a1[1];
  v9 = v8;
  while ( v8 != v4 )
  {
    v9 = (_QWORD *)*v9;
    v10 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((unsigned __int8 *)v8 + 16);
    v12 = *v6;
    v13 = 2 * (a1[6] & v10);
    if ( *(_QWORD **)(*v6 + 16 * (a1[6] & v10)) == v4 )
    {
      *(_QWORD *)(v12 + 16 * (a1[6] & v10)) = v8;
      *(_QWORD *)(v12 + 8 * v13 + 8) = v8;
    }
    else
    {
      v14 = *(_QWORD **)(v12 + 16 * (a1[6] & v10) + 8);
      if ( (unsigned __int8)std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                              v11,
                              v8 + 2,
                              v14 + 2) )
      {
        while ( 1 )
        {
          v20 = (_QWORD **)(v14 + 1);
          if ( *(_QWORD **)(v12 + 8 * v13) == v14 )
            break;
          v14 = *v20;
          if ( !(unsigned __int8)std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                                   v15,
                                   v8 + 2,
                                   *v20 + 2) )
          {
            v21 = (_QWORD *)*v14;
            v22 = (_QWORD *)v8[1];
            *v22 = v9;
            v23 = (_QWORD *)v9[1];
            *v23 = v21;
            v24 = (_QWORD *)v21[1];
            *v24 = v8;
            v21[1] = v23;
            v9[1] = v22;
            v8[1] = v24;
            goto LABEL_15;
          }
        }
        v25 = (_QWORD *)v8[1];
        *v25 = v9;
        v26 = (_QWORD *)v9[1];
        *v26 = v14;
        v27 = *v20;
        *v27 = v8;
        *v20 = v26;
        v9[1] = v25;
        v8[1] = v27;
        *(_QWORD *)(v12 + 8 * v13) = v8;
      }
      else
      {
        v16 = (_QWORD *)*v14;
        if ( (_QWORD *)*v14 != v8 )
        {
          v17 = (_QWORD *)v8[1];
          *v17 = v9;
          v18 = (_QWORD *)v9[1];
          *v18 = v16;
          v19 = (_QWORD *)v16[1];
          *v19 = v8;
          v16[1] = v18;
          v9[1] = v17;
          v8[1] = v19;
        }
        *(_QWORD *)(v12 + 8 * v13 + 8) = v8;
      }
LABEL_15:
      v6 = a1 + 3;
    }
    v8 = v9;
  }
  v29 = 0;
  return std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x180009b90  push    rbx
0x180009b92  push    rbp
0x180009b93  push    rsi
0x180009b94  push    rdi
0x180009b95  push    r12
0x180009b97  push    r13
0x180009b99  push    r14
0x180009b9b  push    r15
0x180009b9d  sub     rsp, 28h
0x180009ba1  mov     rax, 0FFFFFFFFFFFFFFFh
0x180009bab  mov     dword ptr [rsp+68h+arg_8], 0
0x180009bb3  mov     r13, rcx
0x180009bb6  mov     ebx, 1
0x180009bbb  bsr     rcx, rax
0x180009bbf  mov     eax, ebx
0x180009bc1  shl     rax, cl
0x180009bc4  cmp     rdx, rax
0x180009bc7  jbe     short loc_180009BD7
0x180009bc9  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180009bd0  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180009bd7  mov     r12, [r13+8]
0x180009bdb  lea     rax, [rdx-1]
0x180009bdf  or      rax, rbx
0x180009be2  mov     dword ptr [rsp+68h+arg_8], 0
0x180009bea  bsr     rcx, rax
0x180009bee  lea     rsi, [r13+18h]
0x180009bf2  mov     r8, r12
0x180009bf5  inc     ecx
0x180009bf7  shl     rbx, cl
0x180009bfa  mov     rcx, rsi
0x180009bfd  lea     rdx, [rbx+rbx]
0x180009c01  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180009c06  lea     rax, [rbx-1]
0x180009c0a  mov     [r13+38h], rbx
0x180009c0e  mov     [r13+30h], rax
0x180009c12  mov     rbx, [r13+8]
0x180009c16  mov     rbx, [rbx]
0x180009c19  mov     rdi, rbx
0x180009c1c  cmp     rbx, r12
0x180009c1f  jz      loc_180009D13
0x180009c25  mov     rdi, [rdi]
0x180009c28  lea     r15, [rbx+10h]
0x180009c2c  mov     rcx, r15; unsigned __int8 *
0x180009c2f  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180009c34  mov     rbp, [rsi]
0x180009c37  mov     r14, rax
0x180009c3a  and     r14, [r13+30h]
0x180009c3e  add     r14, r14
0x180009c41  cmp     [rbp+r14*8+0], r12
0x180009c46  jnz     short loc_180009C57
0x180009c48  mov     [rbp+r14*8+0], rbx
0x180009c4d  mov     [rbp+r14*8+8], rbx
0x180009c52  jmp     loc_180009D0B
0x180009c57  mov     rsi, [rbp+r14*8+8]
0x180009c5c  mov     rdx, r15
0x180009c5f  lea     r8, [rsi+10h]
0x180009c63  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180009c68  test    al, al
0x180009c6a  jnz     short loc_180009C9C
0x180009c6c  mov     r8, [rsi]
0x180009c6f  cmp     r8, rbx
0x180009c72  jz      short loc_180009C95
0x180009c74  mov     rdx, [rbx+8]
0x180009c78  mov     [rdx], rdi
0x180009c7b  mov     rcx, [rdi+8]
0x180009c7f  mov     [rcx], r8
0x180009c82  mov     rax, [r8+8]
0x180009c86  mov     [rax], rbx
0x180009c89  mov     [r8+8], rcx
0x180009c8d  mov     [rdi+8], rdx
0x180009c91  mov     [rbx+8], rax
0x180009c95  mov     [rbp+r14*8+8], rbx
0x180009c9a  jmp     short loc_180009D07
0x180009c9c  mov     rax, rsi
0x180009c9f  lea     r8, [rsi+8]
0x180009ca3  cmp     [rbp+r14*8+0], rax
0x180009ca8  jz      short loc_180009CE3
0x180009caa  mov     rsi, [r8]
0x180009cad  mov     rdx, r15
0x180009cb0  lea     r8, [rsi+10h]
0x180009cb4  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180009cb9  test    al, al
0x180009cbb  jnz     short loc_180009C9C
0x180009cbd  mov     r8, [rsi]
0x180009cc0  mov     rdx, [rbx+8]
0x180009cc4  mov     [rdx], rdi
0x180009cc7  mov     rcx, [rdi+8]
0x180009ccb  mov     [rcx], r8
0x180009cce  mov     rax, [r8+8]
0x180009cd2  mov     [rax], rbx
0x180009cd5  mov     [r8+8], rcx
0x180009cd9  mov     [rdi+8], rdx
0x180009cdd  mov     [rbx+8], rax
0x180009ce1  jmp     short loc_180009D07
0x180009ce3  mov     rdx, [rbx+8]
0x180009ce7  mov     [rdx], rdi
0x180009cea  mov     rax, [rdi+8]
0x180009cee  mov     [rax], rsi
0x180009cf1  mov     rcx, [r8]
0x180009cf4  mov     [rcx], rbx
0x180009cf7  mov     [r8], rax
0x180009cfa  mov     [rdi+8], rdx
0x180009cfe  mov     [rbx+8], rcx
0x180009d02  mov     [rbp+r14*8+0], rbx
0x180009d07  lea     rsi, [r13+18h]
0x180009d0b  mov     rbx, rdi
0x180009d0e  jmp     loc_180009C1C
0x180009d13  lea     rcx, [rsp+68h+arg_8]
0x180009d18  mov     [rsp+68h+arg_8], 0
0x180009d21  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(void)
0x180009d26  add     rsp, 28h
0x180009d2a  pop     r15
0x180009d2c  pop     r14
0x180009d2e  pop     r13
0x180009d30  pop     r12
0x180009d32  pop     rdi
0x180009d33  pop     rsi
0x180009d34  pop     rbp
0x180009d35  pop     rbx
0x180009d36  retn
```
