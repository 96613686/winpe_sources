# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18000d96c`
- end: `0x18000db0f`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ad94`
- `0x18000bafc`

## callees

- `0x180007afc`
- `0x18000939c`
- `0x180009960`
- `0x18000b474`
- `0x18000d96c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d9ac`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d9ac`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Forced_rehash(
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
  return std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x18000d96c  push    rbx
0x18000d96e  push    rbp
0x18000d96f  push    rsi
0x18000d970  push    rdi
0x18000d971  push    r12
0x18000d973  push    r13
0x18000d975  push    r14
0x18000d977  push    r15
0x18000d979  sub     rsp, 28h
0x18000d97d  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000d987  mov     dword ptr [rsp+68h+arg_8], 0
0x18000d98f  mov     r13, rcx
0x18000d992  mov     ebx, 1
0x18000d997  bsr     rcx, rax
0x18000d99b  mov     eax, ebx
0x18000d99d  shl     rax, cl
0x18000d9a0  cmp     rdx, rax
0x18000d9a3  jbe     short loc_18000D9B3
0x18000d9a5  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18000d9ac  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000d9b3  mov     rbp, [r13+8]
0x18000d9b7  lea     rax, [rdx-1]
0x18000d9bb  or      rax, rbx
0x18000d9be  mov     dword ptr [rsp+68h+arg_8], 0
0x18000d9c6  bsr     rcx, rax
0x18000d9ca  lea     rsi, [r13+18h]
0x18000d9ce  mov     r8, rbp
0x18000d9d1  inc     ecx
0x18000d9d3  shl     rbx, cl
0x18000d9d6  mov     rcx, rsi
0x18000d9d9  lea     rdx, [rbx+rbx]
0x18000d9dd  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18000d9e2  lea     rax, [rbx-1]
0x18000d9e6  mov     [r13+38h], rbx
0x18000d9ea  mov     [r13+30h], rax
0x18000d9ee  mov     rbx, [r13+8]
0x18000d9f2  mov     rbx, [rbx]
0x18000d9f5  mov     rdi, rbx
0x18000d9f8  cmp     rbx, rbp
0x18000d9fb  jz      loc_18000DAEB
0x18000da01  mov     rdi, [rdi]
0x18000da04  lea     r12, [rbx+10h]
0x18000da08  mov     rcx, r12; unsigned __int8 *
0x18000da0b  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000da10  mov     r15, [rsi]
0x18000da13  mov     r14, rax
0x18000da16  and     r14, [r13+30h]
0x18000da1a  add     r14, r14
0x18000da1d  cmp     [r15+r14*8], rbp
0x18000da21  jnz     short loc_18000DA31
0x18000da23  mov     [r15+r14*8], rbx
0x18000da27  mov     [r15+r14*8+8], rbx
0x18000da2c  jmp     loc_18000DAE3
0x18000da31  mov     rsi, [r15+r14*8+8]
0x18000da36  mov     rdx, r12
0x18000da39  lea     r8, [rsi+10h]
0x18000da3d  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18000da42  test    al, al
0x18000da44  jnz     short loc_18000DA76
0x18000da46  mov     r8, [rsi]
0x18000da49  cmp     r8, rbx
0x18000da4c  jz      short loc_18000DA6F
0x18000da4e  mov     rdx, [rbx+8]
0x18000da52  mov     [rdx], rdi
0x18000da55  mov     rcx, [rdi+8]
0x18000da59  mov     [rcx], r8
0x18000da5c  mov     rax, [r8+8]
0x18000da60  mov     [rax], rbx
0x18000da63  mov     [r8+8], rcx
0x18000da67  mov     [rdi+8], rdx
0x18000da6b  mov     [rbx+8], rax
0x18000da6f  mov     [r15+r14*8+8], rbx
0x18000da74  jmp     short loc_18000DADF
0x18000da76  mov     rax, rsi
0x18000da79  lea     r8, [rsi+8]
0x18000da7d  cmp     [r15+r14*8], rax
0x18000da81  jz      short loc_18000DABC
0x18000da83  mov     rsi, [r8]
0x18000da86  mov     rdx, r12
0x18000da89  lea     r8, [rsi+10h]
0x18000da8d  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18000da92  test    al, al
0x18000da94  jnz     short loc_18000DA76
0x18000da96  mov     r8, [rsi]
0x18000da99  mov     rdx, [rbx+8]
0x18000da9d  mov     [rdx], rdi
0x18000daa0  mov     rcx, [rdi+8]
0x18000daa4  mov     [rcx], r8
0x18000daa7  mov     rax, [r8+8]
0x18000daab  mov     [rax], rbx
0x18000daae  mov     [r8+8], rcx
0x18000dab2  mov     [rdi+8], rdx
0x18000dab6  mov     [rbx+8], rax
0x18000daba  jmp     short loc_18000DADF
0x18000dabc  mov     rdx, [rbx+8]
0x18000dac0  mov     [rdx], rdi
0x18000dac3  mov     rax, [rdi+8]
0x18000dac7  mov     [rax], rsi
0x18000daca  mov     rcx, [r8]
0x18000dacd  mov     [rcx], rbx
0x18000dad0  mov     [r8], rax
0x18000dad3  mov     [rdi+8], rdx
0x18000dad7  mov     [rbx+8], rcx
0x18000dadb  mov     [r15+r14*8], rbx
0x18000dadf  lea     rsi, [r13+18h]
0x18000dae3  mov     rbx, rdi
0x18000dae6  jmp     loc_18000D9F8
0x18000daeb  lea     rcx, [rsp+68h+arg_8]
0x18000daf0  mov     [rsp+68h+arg_8], 0
0x18000daf9  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000dafe  add     rsp, 28h
0x18000db02  pop     r15
0x18000db04  pop     r14
0x18000db06  pop     r13
0x18000db08  pop     r12
0x18000db0a  pop     rdi
0x18000db0b  pop     rsi
0x18000db0c  pop     rbp
0x18000db0d  pop     rbx
0x18000db0e  retn
```
