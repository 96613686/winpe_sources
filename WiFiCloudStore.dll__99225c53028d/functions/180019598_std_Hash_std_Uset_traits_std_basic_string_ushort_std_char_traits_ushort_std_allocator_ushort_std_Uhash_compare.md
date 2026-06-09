# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180019598`
- end: `0x18001975c`
- name: `?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `452`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001956c`
- `0x1800211b0`

## callees

- `0x180019598`
- `0x180019764`
- `0x18001b9d0`
- `0x1800291fc`
- `0x18003bb10`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180019701`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180019701`

## pseudocode

```c
int __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // r12
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  __int64 v11; // rbp
  __int64 v12; // r14
  _QWORD *v13; // rsi
  const wchar_t *v14; // rdx
  size_t v15; // r8
  const wchar_t *v16; // rcx
  __int64 *v17; // r8
  _QWORD *v18; // rdx
  _QWORD *v19; // rcx
  _QWORD *v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // r8
  _QWORD *v24; // rdx
  _QWORD *v25; // rcx

  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    a1 + 3,
    2 * v7,
    v4);
  LODWORD(v8) = v7 - 1;
  a1[7] = v7;
  a1[6] = v7 - 1;
  v9 = *(_QWORD **)a1[1];
  v10 = v9;
  while ( v9 != v4 )
  {
    v10 = (_QWORD *)*v10;
    v8 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((unsigned __int8 *)v9 + 16);
    v11 = *v6;
    v12 = 2 * (a1[6] & v8);
    if ( *(_QWORD **)(*v6 + 16 * (a1[6] & v8)) == v4 )
    {
      *(_QWORD *)(v11 + 16 * (a1[6] & v8)) = v9;
      *(_QWORD *)(v11 + 8 * v12 + 8) = v9;
    }
    else
    {
      v13 = *(_QWORD **)(v11 + 16 * (a1[6] & v8) + 8);
      v14 = (const wchar_t *)(v13 + 2);
      v8 = v13[4];
      if ( v13[5] > 7u )
        v14 = *(const wchar_t **)v14;
      v15 = v9[4];
      if ( v9[5] <= 7u )
        v16 = (const wchar_t *)(v9 + 2);
      else
        v16 = (const wchar_t *)v9[2];
      if ( v15 != v8 || v15 && (LODWORD(v8) = wmemcmp(v16, v14, v15), (_DWORD)v8) )
      {
        do
        {
          v17 = v13 + 1;
          if ( *(_QWORD **)(v11 + 8 * v12) == v13 )
          {
            v18 = (_QWORD *)v9[1];
            *v18 = v10;
            v8 = v10[1];
            *(_QWORD *)v8 = v13;
            v19 = (_QWORD *)*v17;
            *v19 = v9;
            *v17 = v8;
            v10[1] = v18;
            v9[1] = v19;
            *(_QWORD *)(v11 + 8 * v12) = v9;
            goto LABEL_14;
          }
          v13 = (_QWORD *)*v17;
        }
        while ( std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                  (__int64)v16,
                  (__int64)(v9 + 2),
                  *v17 + 16) );
        v23 = (_QWORD *)*v13;
        v24 = (_QWORD *)v9[1];
        *v24 = v10;
        v25 = (_QWORD *)v10[1];
        *v25 = v23;
        v8 = v23[1];
        *(_QWORD *)v8 = v9;
        v23[1] = v25;
        v10[1] = v24;
        v9[1] = v8;
      }
      else
      {
        v20 = (_QWORD *)*v13;
        if ( (_QWORD *)*v13 != v9 )
        {
          v21 = (_QWORD *)v9[1];
          *v21 = v10;
          v22 = (_QWORD *)v10[1];
          *v22 = v20;
          v8 = v20[1];
          *(_QWORD *)v8 = v9;
          v20[1] = v22;
          v10[1] = v21;
          v9[1] = v8;
        }
        *(_QWORD *)(v11 + 8 * v12 + 8) = v9;
      }
LABEL_14:
      v6 = a1 + 3;
    }
    v9 = v10;
  }
  return v8;
}

```

## disassembly

```asm
0x180019598  push    rbx
0x18001959a  push    rbp
0x18001959b  push    rsi
0x18001959c  push    rdi
0x18001959d  push    r12
0x18001959f  push    r13
0x1800195a1  push    r14
0x1800195a3  push    r15
0x1800195a5  sub     rsp, 28h
0x1800195a9  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800195b3  mov     [rsp+68h+arg_8], 0
0x1800195bb  mov     r13, rcx
0x1800195be  mov     ebx, 1
0x1800195c3  bsr     rcx, rax
0x1800195c7  mov     eax, ebx
0x1800195c9  shl     rax, cl
0x1800195cc  cmp     rdx, rax
0x1800195cf  ja      loc_1800196FA
0x1800195d5  mov     r12, [r13+8]
0x1800195d9  lea     rax, [rdx-1]
0x1800195dd  or      rax, rbx
0x1800195e0  mov     [rsp+68h+arg_8], 0
0x1800195e8  bsr     rcx, rax
0x1800195ec  lea     rsi, [r13+18h]
0x1800195f0  mov     r8, r12
0x1800195f3  inc     ecx
0x1800195f5  shl     rbx, cl
0x1800195f8  mov     rcx, rsi
0x1800195fb  lea     rdx, [rbx+rbx]
0x1800195ff  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180019604  lea     rax, [rbx-1]
0x180019608  mov     [r13+38h], rbx
0x18001960c  mov     [r13+30h], rax
0x180019610  mov     rbx, [r13+8]
0x180019614  mov     rbx, [rbx]
0x180019617  mov     rdi, rbx
0x18001961a  cmp     rbx, r12
0x18001961d  jnz     short loc_180019630
0x18001961f  add     rsp, 28h
0x180019623  pop     r15
0x180019625  pop     r14
0x180019627  pop     r13
0x180019629  pop     r12
0x18001962b  pop     rdi
0x18001962c  pop     rsi
0x18001962d  pop     rbp
0x18001962e  pop     rbx
0x18001962f  retn
0x180019630  mov     rdi, [rdi]
0x180019633  lea     r15, [rbx+10h]
0x180019637  mov     rcx, r15; unsigned __int8 *
0x18001963a  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18001963f  mov     rbp, [rsi]
0x180019642  mov     r14, rax
0x180019645  and     r14, [r13+30h]
0x180019649  add     r14, r14
0x18001964c  cmp     [rbp+r14*8+0], r12
0x180019651  jnz     short loc_180019662
0x180019653  mov     [rbp+r14*8+0], rbx
0x180019658  mov     [rbp+r14*8+8], rbx
0x18001965d  mov     rbx, rdi
0x180019660  jmp     short loc_18001961A
0x180019662  mov     rsi, [rbp+r14*8+8]
0x180019667  lea     rdx, [rsi+10h]
0x18001966b  cmp     qword ptr [rdx+18h], 7
0x180019670  mov     rax, [rdx+10h]
0x180019674  jbe     short loc_180019679
0x180019676  mov     rdx, [rdx]; S2
0x180019679  cmp     qword ptr [r15+18h], 7
0x18001967e  mov     r8, [rbx+20h]; N
0x180019682  jbe     short loc_1800196C5
0x180019684  mov     rcx, [r15]; S1
0x180019687  cmp     r8, rax
0x18001968a  jz      short loc_180019708
0x18001968c  lea     r8, [rsi+8]
0x180019690  cmp     [rbp+r14*8+0], rsi
0x180019695  jnz     loc_18001971C
0x18001969b  mov     rdx, [rbx+8]
0x18001969f  mov     [rdx], rdi
0x1800196a2  mov     rax, [rdi+8]
0x1800196a6  mov     [rax], rsi
0x1800196a9  mov     rcx, [r8]
0x1800196ac  mov     [rcx], rbx
0x1800196af  mov     [r8], rax
0x1800196b2  mov     [rdi+8], rdx
0x1800196b6  mov     [rbx+8], rcx
0x1800196ba  mov     [rbp+r14*8+0], rbx
0x1800196bf  lea     rsi, [r13+18h]
0x1800196c3  jmp     short loc_18001965D
0x1800196c5  mov     rcx, r15
0x1800196c8  jmp     short loc_180019687
0x1800196ca  mov     r8, [rsi]
0x1800196cd  cmp     r8, rbx
0x1800196d0  jz      short loc_1800196F3
0x1800196d2  mov     rdx, [rbx+8]
0x1800196d6  mov     [rdx], rdi
0x1800196d9  mov     rcx, [rdi+8]
0x1800196dd  mov     [rcx], r8
0x1800196e0  mov     rax, [r8+8]
0x1800196e4  mov     [rax], rbx
0x1800196e7  mov     [r8+8], rcx
0x1800196eb  mov     [rdi+8], rdx
0x1800196ef  mov     [rbx+8], rax
0x1800196f3  mov     [rbp+r14*8+8], rbx
0x1800196f8  jmp     short loc_1800196BF
0x1800196fa  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180019701  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180019708  test    r8, r8
0x18001970b  jz      short loc_1800196CA
0x18001970d  call    wmemcmp
0x180019712  test    eax, eax
0x180019714  jnz     loc_18001968C
0x18001971a  jmp     short loc_1800196CA
0x18001971c  mov     rsi, [r8]
0x18001971f  mov     rdx, r15
0x180019722  lea     r8, [rsi+10h]
0x180019726  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18001972b  test    al, al
0x18001972d  jnz     loc_18001968C
0x180019733  mov     r8, [rsi]
0x180019736  mov     rdx, [rbx+8]
0x18001973a  mov     [rdx], rdi
0x18001973d  mov     rcx, [rdi+8]
0x180019741  mov     [rcx], r8
0x180019744  mov     rax, [r8+8]
0x180019748  mov     [rax], rbx
0x18001974b  mov     [r8+8], rcx
0x18001974f  mov     [rdi+8], rdx
0x180019753  mov     [rbx+8], rax
0x180019757  jmp     loc_1800196BF
```
