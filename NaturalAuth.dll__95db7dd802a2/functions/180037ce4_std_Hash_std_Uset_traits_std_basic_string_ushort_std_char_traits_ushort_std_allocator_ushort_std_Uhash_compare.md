# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180037ce4`
- end: `0x180037e8b`
- name: `?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `423`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180032dc8`

## callees

- `0x180031ef4`
- `0x1800338c4`
- `0x180033e04`
- `0x18003774c`
- `0x180037ce4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180037d24`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180037d24`

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
    v10 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(v8 + 2);
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
      if ( std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
             v11,
             (__int64)(v8 + 2),
             (__int64)(v14 + 2)) )
      {
        while ( 1 )
        {
          v20 = (_QWORD **)(v14 + 1);
          if ( *(_QWORD **)(v12 + 8 * v13) == v14 )
            break;
          v14 = *v20;
          if ( !std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                  v15,
                  (__int64)(v8 + 2),
                  (__int64)(*v20 + 2)) )
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
0x180037ce4  push    rbx
0x180037ce6  push    rbp
0x180037ce7  push    rsi
0x180037ce8  push    rdi
0x180037ce9  push    r12
0x180037ceb  push    r13
0x180037ced  push    r14
0x180037cef  push    r15
0x180037cf1  sub     rsp, 28h
0x180037cf5  mov     rax, 0FFFFFFFFFFFFFFFh
0x180037cff  mov     dword ptr [rsp+68h+arg_8], 0
0x180037d07  mov     r13, rcx
0x180037d0a  mov     ebx, 1
0x180037d0f  bsr     rcx, rax
0x180037d13  mov     eax, ebx
0x180037d15  shl     rax, cl
0x180037d18  cmp     rdx, rax
0x180037d1b  jbe     short loc_180037D2B
0x180037d1d  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180037d24  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180037d2b  mov     r12, [r13+8]
0x180037d2f  lea     rax, [rdx-1]
0x180037d33  or      rax, rbx
0x180037d36  mov     dword ptr [rsp+68h+arg_8], 0
0x180037d3e  bsr     rcx, rax
0x180037d42  lea     rsi, [r13+18h]
0x180037d46  mov     r8, r12
0x180037d49  inc     ecx
0x180037d4b  shl     rbx, cl
0x180037d4e  mov     rcx, rsi
0x180037d51  lea     rdx, [rbx+rbx]
0x180037d55  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180037d5a  lea     rax, [rbx-1]
0x180037d5e  mov     [r13+38h], rbx
0x180037d62  mov     [r13+30h], rax
0x180037d66  mov     rbx, [r13+8]
0x180037d6a  mov     rbx, [rbx]
0x180037d6d  mov     rdi, rbx
0x180037d70  cmp     rbx, r12
0x180037d73  jz      loc_180037E67
0x180037d79  mov     rdi, [rdi]
0x180037d7c  lea     r15, [rbx+10h]
0x180037d80  mov     rcx, r15
0x180037d83  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180037d88  mov     rbp, [rsi]
0x180037d8b  mov     r14, rax
0x180037d8e  and     r14, [r13+30h]
0x180037d92  add     r14, r14
0x180037d95  cmp     [rbp+r14*8+0], r12
0x180037d9a  jnz     short loc_180037DAB
0x180037d9c  mov     [rbp+r14*8+0], rbx
0x180037da1  mov     [rbp+r14*8+8], rbx
0x180037da6  jmp     loc_180037E5F
0x180037dab  mov     rsi, [rbp+r14*8+8]
0x180037db0  mov     rdx, r15
0x180037db3  lea     r8, [rsi+10h]
0x180037db7  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180037dbc  test    al, al
0x180037dbe  jnz     short loc_180037DF0
0x180037dc0  mov     r8, [rsi]
0x180037dc3  cmp     r8, rbx
0x180037dc6  jz      short loc_180037DE9
0x180037dc8  mov     rdx, [rbx+8]
0x180037dcc  mov     [rdx], rdi
0x180037dcf  mov     rcx, [rdi+8]
0x180037dd3  mov     [rcx], r8
0x180037dd6  mov     rax, [r8+8]
0x180037dda  mov     [rax], rbx
0x180037ddd  mov     [r8+8], rcx
0x180037de1  mov     [rdi+8], rdx
0x180037de5  mov     [rbx+8], rax
0x180037de9  mov     [rbp+r14*8+8], rbx
0x180037dee  jmp     short loc_180037E5B
0x180037df0  mov     rax, rsi
0x180037df3  lea     r8, [rsi+8]
0x180037df7  cmp     [rbp+r14*8+0], rax
0x180037dfc  jz      short loc_180037E37
0x180037dfe  mov     rsi, [r8]
0x180037e01  mov     rdx, r15
0x180037e04  lea     r8, [rsi+10h]
0x180037e08  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180037e0d  test    al, al
0x180037e0f  jnz     short loc_180037DF0
0x180037e11  mov     r8, [rsi]
0x180037e14  mov     rdx, [rbx+8]
0x180037e18  mov     [rdx], rdi
0x180037e1b  mov     rcx, [rdi+8]
0x180037e1f  mov     [rcx], r8
0x180037e22  mov     rax, [r8+8]
0x180037e26  mov     [rax], rbx
0x180037e29  mov     [r8+8], rcx
0x180037e2d  mov     [rdi+8], rdx
0x180037e31  mov     [rbx+8], rax
0x180037e35  jmp     short loc_180037E5B
0x180037e37  mov     rdx, [rbx+8]
0x180037e3b  mov     [rdx], rdi
0x180037e3e  mov     rax, [rdi+8]
0x180037e42  mov     [rax], rsi
0x180037e45  mov     rcx, [r8]
0x180037e48  mov     [rcx], rbx
0x180037e4b  mov     [r8], rax
0x180037e4e  mov     [rdi+8], rdx
0x180037e52  mov     [rbx+8], rcx
0x180037e56  mov     [rbp+r14*8+0], rbx
0x180037e5b  lea     rsi, [r13+18h]
0x180037e5f  mov     rbx, rdi
0x180037e62  jmp     loc_180037D70
0x180037e67  lea     rcx, [rsp+68h+arg_8]
0x180037e6c  mov     [rsp+68h+arg_8], 0
0x180037e75  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(void)
0x180037e7a  add     rsp, 28h
0x180037e7e  pop     r15
0x180037e80  pop     r14
0x180037e82  pop     r13
0x180037e84  pop     r12
0x180037e86  pop     rdi
0x180037e87  pop     rsi
0x180037e88  pop     rbp
0x180037e89  pop     rbx
0x180037e8a  retn
```
