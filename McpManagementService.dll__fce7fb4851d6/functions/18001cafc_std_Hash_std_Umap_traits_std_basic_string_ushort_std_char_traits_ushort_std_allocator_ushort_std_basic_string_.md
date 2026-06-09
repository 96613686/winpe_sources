# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18001cafc`
- end: `0x18001cc9f`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011814`

## callees

- `0x18000f9c4`
- `0x180012ae0`
- `0x180012cd4`
- `0x18001c5f0`
- `0x18001cafc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001cb3c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001cb3c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r15
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
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Assign_grow(
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
  return std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x18001cafc  push    rbx
0x18001cafe  push    rbp
0x18001caff  push    rsi
0x18001cb00  push    rdi
0x18001cb01  push    r12
0x18001cb03  push    r13
0x18001cb05  push    r14
0x18001cb07  push    r15
0x18001cb09  sub     rsp, 28h
0x18001cb0d  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001cb17  mov     dword ptr [rsp+68h+arg_8], 0
0x18001cb1f  mov     r13, rcx
0x18001cb22  mov     ebx, 1
0x18001cb27  bsr     rcx, rax
0x18001cb2b  mov     eax, ebx
0x18001cb2d  shl     rax, cl
0x18001cb30  cmp     rdx, rax
0x18001cb33  jbe     short loc_18001CB43
0x18001cb35  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18001cb3c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001cb43  mov     rbp, [r13+8]
0x18001cb47  lea     rax, [rdx-1]
0x18001cb4b  or      rax, rbx
0x18001cb4e  mov     dword ptr [rsp+68h+arg_8], 0
0x18001cb56  bsr     rcx, rax
0x18001cb5a  lea     rsi, [r13+18h]
0x18001cb5e  mov     r8, rbp
0x18001cb61  inc     ecx
0x18001cb63  shl     rbx, cl
0x18001cb66  mov     rcx, rsi
0x18001cb69  lea     rdx, [rbx+rbx]
0x18001cb6d  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>)
0x18001cb72  lea     rax, [rbx-1]
0x18001cb76  mov     [r13+38h], rbx
0x18001cb7a  mov     [r13+30h], rax
0x18001cb7e  mov     rbx, [r13+8]
0x18001cb82  mov     rbx, [rbx]
0x18001cb85  mov     rdi, rbx
0x18001cb88  cmp     rbx, rbp
0x18001cb8b  jz      loc_18001CC7B
0x18001cb91  mov     rdi, [rdi]
0x18001cb94  lea     r12, [rbx+10h]
0x18001cb98  mov     rcx, r12
0x18001cb9b  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18001cba0  mov     r15, [rsi]
0x18001cba3  mov     r14, rax
0x18001cba6  and     r14, [r13+30h]
0x18001cbaa  add     r14, r14
0x18001cbad  cmp     [r15+r14*8], rbp
0x18001cbb1  jnz     short loc_18001CBC1
0x18001cbb3  mov     [r15+r14*8], rbx
0x18001cbb7  mov     [r15+r14*8+8], rbx
0x18001cbbc  jmp     loc_18001CC73
0x18001cbc1  mov     rsi, [r15+r14*8+8]
0x18001cbc6  mov     rdx, r12
0x18001cbc9  lea     r8, [rsi+10h]
0x18001cbcd  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18001cbd2  test    al, al
0x18001cbd4  jnz     short loc_18001CC06
0x18001cbd6  mov     r8, [rsi]
0x18001cbd9  cmp     r8, rbx
0x18001cbdc  jz      short loc_18001CBFF
0x18001cbde  mov     rdx, [rbx+8]
0x18001cbe2  mov     [rdx], rdi
0x18001cbe5  mov     rcx, [rdi+8]
0x18001cbe9  mov     [rcx], r8
0x18001cbec  mov     rax, [r8+8]
0x18001cbf0  mov     [rax], rbx
0x18001cbf3  mov     [r8+8], rcx
0x18001cbf7  mov     [rdi+8], rdx
0x18001cbfb  mov     [rbx+8], rax
0x18001cbff  mov     [r15+r14*8+8], rbx
0x18001cc04  jmp     short loc_18001CC6F
0x18001cc06  mov     rax, rsi
0x18001cc09  lea     r8, [rsi+8]
0x18001cc0d  cmp     [r15+r14*8], rax
0x18001cc11  jz      short loc_18001CC4C
0x18001cc13  mov     rsi, [r8]
0x18001cc16  mov     rdx, r12
0x18001cc19  lea     r8, [rsi+10h]
0x18001cc1d  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18001cc22  test    al, al
0x18001cc24  jnz     short loc_18001CC06
0x18001cc26  mov     r8, [rsi]
0x18001cc29  mov     rdx, [rbx+8]
0x18001cc2d  mov     [rdx], rdi
0x18001cc30  mov     rcx, [rdi+8]
0x18001cc34  mov     [rcx], r8
0x18001cc37  mov     rax, [r8+8]
0x18001cc3b  mov     [rax], rbx
0x18001cc3e  mov     [r8+8], rcx
0x18001cc42  mov     [rdi+8], rdx
0x18001cc46  mov     [rbx+8], rax
0x18001cc4a  jmp     short loc_18001CC6F
0x18001cc4c  mov     rdx, [rbx+8]
0x18001cc50  mov     [rdx], rdi
0x18001cc53  mov     rax, [rdi+8]
0x18001cc57  mov     [rax], rsi
0x18001cc5a  mov     rcx, [r8]
0x18001cc5d  mov     [rcx], rbx
0x18001cc60  mov     [r8], rax
0x18001cc63  mov     [rdi+8], rdx
0x18001cc67  mov     [rbx+8], rcx
0x18001cc6b  mov     [r15+r14*8], rbx
0x18001cc6f  lea     rsi, [r13+18h]
0x18001cc73  mov     rbx, rdi
0x18001cc76  jmp     loc_18001CB88
0x18001cc7b  lea     rcx, [rsp+68h+arg_8]
0x18001cc80  mov     [rsp+68h+arg_8], 0
0x18001cc89  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18001cc8e  add     rsp, 28h
0x18001cc92  pop     r15
0x18001cc94  pop     r14
0x18001cc96  pop     r13
0x18001cc98  pop     r12
0x18001cc9a  pop     rdi
0x18001cc9b  pop     rsi
0x18001cc9c  pop     rbp
0x18001cc9d  pop     rbx
0x18001cc9e  retn
```
