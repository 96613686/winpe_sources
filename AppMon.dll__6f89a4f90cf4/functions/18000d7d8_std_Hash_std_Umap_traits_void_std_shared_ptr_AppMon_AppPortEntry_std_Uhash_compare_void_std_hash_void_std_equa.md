# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18000d7d8`
- end: `0x18000d965`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ac1c`

## callees

- `0x180009960`
- `0x18000b3f4`
- `0x18000cb08`
- `0x18000d7d8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d812`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d812`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Forced_rehash(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // rdi
  unsigned __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rsi
  unsigned __int8 *v7; // r11
  unsigned __int8 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r10
  unsigned __int8 **v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  __int64 **v19; // r10
  __int64 v20; // r8
  unsigned __int8 **v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  unsigned __int8 **v24; // rdx
  __int64 **v25; // rcx
  __int64 *v26; // rax
  __int64 v28; // [rsp+50h] [rbp+8h] BYREF

  HIDWORD(v28) = HIDWORD(a1);
  LODWORD(v28) = 0;
  _BitScanReverse64(&v2, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v2 )
    std::_Xlength_error("invalid hash bucket count");
  v3 = qword_180016578;
  LODWORD(v28) = 0;
  _BitScanReverse64(&v4, (a2 - 1) | 1);
  v5 = 1LL << ((unsigned __int8)v4 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    &qword_180016588,
    2 * v5,
    qword_180016578);
  v6 = v5 - 1;
  qword_1800165A8 = v5;
  qword_1800165A0 = v5 - 1;
  v7 = *(unsigned __int8 **)qword_180016578;
  v8 = *(unsigned __int8 **)qword_180016578;
  while ( v7 != (unsigned __int8 *)v3 )
  {
    v8 = *(unsigned __int8 **)v8;
    v9 = std::_Conditionally_enabled_hash<void *,1>::operator()(v7 + 16);
    v11 = qword_180016588;
    v12 = 2 * (v6 & v9);
    if ( *(_QWORD *)(qword_180016588 + 16 * (v6 & v9)) == v3 )
    {
      *(_QWORD *)(qword_180016588 + 16 * (v6 & v9)) = v10;
LABEL_7:
      *(_QWORD *)(v11 + 8 * v12 + 8) = v10;
      goto LABEL_15;
    }
    v13 = *(__int64 **)(qword_180016588 + 16 * (v6 & v9) + 8);
    v14 = *(_QWORD *)(v10 + 16);
    if ( v14 == v13[2] )
    {
      v15 = *v13;
      if ( *v13 != v10 )
      {
        v16 = *(unsigned __int8 ***)(v10 + 8);
        *v16 = v8;
        v17 = (_QWORD *)*((_QWORD *)v8 + 1);
        *v17 = v15;
        v18 = *(_QWORD **)(v15 + 8);
        *v18 = v10;
        *(_QWORD *)(v15 + 8) = v17;
        *((_QWORD *)v8 + 1) = v16;
        *(_QWORD *)(v10 + 8) = v18;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v19 = (__int64 **)(v13 + 1);
      if ( *(__int64 **)(qword_180016588 + 8 * v12) == v13 )
        break;
      v13 = *v19;
      if ( v14 == (*v19)[2] )
      {
        v20 = *v13;
        v21 = *(unsigned __int8 ***)(v10 + 8);
        *v21 = v8;
        v22 = (_QWORD *)*((_QWORD *)v8 + 1);
        *v22 = v20;
        v23 = *(_QWORD **)(v20 + 8);
        *v23 = v10;
        *(_QWORD *)(v20 + 8) = v22;
        *((_QWORD *)v8 + 1) = v21;
        *(_QWORD *)(v10 + 8) = v23;
        goto LABEL_15;
      }
    }
    v24 = *(unsigned __int8 ***)(v10 + 8);
    *v24 = v8;
    v25 = (__int64 **)*((_QWORD *)v8 + 1);
    *v25 = v13;
    v26 = *v19;
    *v26 = v10;
    *v19 = (__int64 *)v25;
    *((_QWORD *)v8 + 1) = v24;
    *(_QWORD *)(v10 + 8) = v26;
    *(_QWORD *)(v11 + 8 * v12) = v10;
LABEL_15:
    v6 = qword_1800165A0;
    v7 = v8;
  }
  v28 = 0;
  return std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Clear_guard::~_Clear_guard(&v28);
}

```

## disassembly

```asm
0x18000d7d8  mov     [rsp+arg_0], rcx
0x18000d7dd  push    rbx
0x18000d7de  push    rsi
0x18000d7df  push    rdi
0x18000d7e0  push    r14
0x18000d7e2  sub     rsp, 28h
0x18000d7e6  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000d7f0  mov     dword ptr [rsp+48h+arg_0], 0
0x18000d7f8  bsr     rcx, rax
0x18000d7fc  mov     ebx, 1
0x18000d801  mov     eax, ebx
0x18000d803  shl     rax, cl
0x18000d806  cmp     rdx, rax
0x18000d809  jbe     short loc_18000D819
0x18000d80b  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18000d812  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000d819  mov     rdi, cs:qword_180016578
0x18000d820  lea     rax, [rdx-1]
0x18000d824  or      rax, rbx
0x18000d827  mov     dword ptr [rsp+48h+arg_0], 0
0x18000d82f  bsr     rcx, rax
0x18000d833  mov     r8, rdi
0x18000d836  inc     ecx
0x18000d838  shl     rbx, cl
0x18000d83b  lea     rcx, qword_180016588
0x18000d842  lea     rdx, [rbx+rbx]
0x18000d846  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18000d84b  mov     r11, cs:qword_180016578
0x18000d852  lea     rsi, [rbx-1]
0x18000d856  mov     cs:qword_1800165A8, rbx
0x18000d85d  mov     cs:qword_1800165A0, rsi
0x18000d864  mov     r11, [r11]
0x18000d867  mov     rbx, r11
0x18000d86a  cmp     r11, rdi
0x18000d86d  jz      loc_18000D948
0x18000d873  mov     rbx, [rbx]
0x18000d876  lea     rcx, [r11+10h]; unsigned __int8 *
0x18000d87a  call    ??R?$_Conditionally_enabled_hash@PEAX$00@std@@SA_KAEBQEAX@Z; std::_Conditionally_enabled_hash<void *,1>::operator()(void * const &)
0x18000d87f  mov     r9, cs:qword_180016588
0x18000d886  mov     r8, rax
0x18000d889  and     r8, rsi
0x18000d88c  add     r8, r8
0x18000d88f  cmp     [r9+r8*8], rdi
0x18000d893  jnz     short loc_18000D8A3
0x18000d895  mov     [r9+r8*8], r11
0x18000d899  mov     [r9+r8*8+8], r11
0x18000d89e  jmp     loc_18000D939
0x18000d8a3  mov     rax, [r9+r8*8+8]
0x18000d8a8  mov     rcx, [r11+10h]
0x18000d8ac  cmp     rcx, [rax+10h]
0x18000d8b0  jnz     short loc_18000D8DD
0x18000d8b2  mov     r10, [rax]
0x18000d8b5  cmp     r10, r11
0x18000d8b8  jz      short loc_18000D899
0x18000d8ba  mov     rdx, [r11+8]
0x18000d8be  mov     [rdx], rbx
0x18000d8c1  mov     rcx, [rbx+8]
0x18000d8c5  mov     [rcx], r10
0x18000d8c8  mov     rax, [r10+8]
0x18000d8cc  mov     [rax], r11
0x18000d8cf  mov     [r10+8], rcx
0x18000d8d3  mov     [rbx+8], rdx
0x18000d8d7  mov     [r11+8], rax
0x18000d8db  jmp     short loc_18000D899
0x18000d8dd  lea     r10, [rax+8]
0x18000d8e1  cmp     [r9+r8*8], rax
0x18000d8e5  jz      short loc_18000D916
0x18000d8e7  mov     rax, [r10]
0x18000d8ea  cmp     rcx, [rax+10h]
0x18000d8ee  jnz     short loc_18000D8DD
0x18000d8f0  mov     r8, [rax]
0x18000d8f3  mov     rdx, [r11+8]
0x18000d8f7  mov     [rdx], rbx
0x18000d8fa  mov     rcx, [rbx+8]
0x18000d8fe  mov     [rcx], r8
0x18000d901  mov     rax, [r8+8]
0x18000d905  mov     [rax], r11
0x18000d908  mov     [r8+8], rcx
0x18000d90c  mov     [rbx+8], rdx
0x18000d910  mov     [r11+8], rax
0x18000d914  jmp     short loc_18000D939
0x18000d916  mov     rdx, [r11+8]
0x18000d91a  mov     [rdx], rbx
0x18000d91d  mov     rcx, [rbx+8]
0x18000d921  mov     [rcx], rax
0x18000d924  mov     rax, [r10]
0x18000d927  mov     [rax], r11
0x18000d92a  mov     [r10], rcx
0x18000d92d  mov     [rbx+8], rdx
0x18000d931  mov     [r11+8], rax
0x18000d935  mov     [r9+r8*8], r11
0x18000d939  mov     rsi, cs:qword_1800165A0
0x18000d940  mov     r11, rbx
0x18000d943  jmp     loc_18000D86A
0x18000d948  lea     rcx, [rsp+48h+arg_0]
0x18000d94d  mov     [rsp+48h+arg_0], 0
0x18000d956  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000d95b  add     rsp, 28h
0x18000d95f  pop     r14
0x18000d961  pop     rdi
0x18000d962  pop     rsi
0x18000d963  pop     rbx
0x18000d964  retn
```
