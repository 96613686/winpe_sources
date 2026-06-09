# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180018bd0`
- end: `0x180018f36`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEAAX_K@Z`
- size: `870`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800191c0`

## callees

- `0x18000b810`
- `0x18000bf70`
- `0x1800159f0`
- `0x180016d80`
- `0x180016e5c`
- `0x180016e9c`
- `0x180016f48`
- `0x180016f60`
- `0x180016f80`
- `0x180016fa4`
- `0x180016fc8`
- `0x180018750`
- `0x1800188e0`
- `0x180018b00`
- `0x180018bd0`
- `0x1800193ac`
- `0x180019420`
- `0x1800197b0`
- `0x180019b00`
- `0x180019f20`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018c38`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018c38`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v10; // [rsp+20h] [rbp-88h] BYREF
  __int64 v11; // [rsp+28h] [rbp-80h] BYREF
  __int64 v12; // [rsp+30h] [rbp-78h] BYREF
  _QWORD *v13; // [rsp+38h] [rbp-70h]
  unsigned int v14; // [rsp+40h] [rbp-68h]
  __int64 v15; // [rsp+48h] [rbp-60h] BYREF
  __int64 *v16; // [rsp+50h] [rbp-58h]
  __int64 v17; // [rsp+58h] [rbp-50h]
  __int64 v18; // [rsp+60h] [rbp-48h]
  _QWORD v19[5]; // [rsp+68h] [rbp-40h] BYREF
  _QWORD *v20; // [rsp+90h] [rbp-18h]
  _QWORD *v21; // [rsp+98h] [rbp-10h]
  unsigned __int64 v24; // [rsp+B8h] [rbp+10h]

  v2 = std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::max_size(a1 + 3);
  v14 = std::_Floor_of_log_2(v2 >> 1);
  v19[1] = 1;
  v19[2] = 1LL << v14;
  if ( a2 > 1LL << v14 )
    std::_Xlength_error("invalid hash bucket count");
  v19[3] = 1;
  v24 = 1LL << std::_Ceiling_of_log_2(a2);
  std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_end(
    a1,
    &v15);
  v19[4] = a1 + 3;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v24,
    v15);
  a1[6] = v24 - 1;
  a1[7] = v24;
  Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>(
    v19,
    a1);
  std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_begin(
    a1,
    &v10);
  v12 = v10;
  while ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator!=(
                             &v10,
                             &v15) )
  {
    std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator++(&v12);
    v3 = std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator*(&v10);
    v17 = Microsoft::WRL::Details::Forward<std::nullptr_t>(v3);
    v18 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(
            a1,
            v17);
    v13 = (_QWORD *)(a1[3] + 16 * v18);
    v16 = (__int64 *)(a1[3] + 16 * v18 + 8);
    if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator==(
                            v13,
                            &v15) )
    {
      *v13 = v10;
      *v16 = v10;
    }
    else
    {
      v11 = *v16;
      v20 = a1;
      v4 = std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator*(&v11);
      v5 = Microsoft::WRL::Details::Forward<std::nullptr_t>(v4);
      if ( (unsigned __int8)std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int,int>(
                              v20,
                              v17,
                              v5) )
      {
        do
        {
          if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator==(
                                  v13,
                                  &v11) )
          {
            std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>::_Unchecked_splice(
              v11,
              v10,
              v12);
            *v13 = v10;
            goto LABEL_4;
          }
          v21 = a1;
          v6 = std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator--(&v11);
          v7 = std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator*(v6);
          v8 = Microsoft::WRL::Details::Forward<std::nullptr_t>(v7);
        }
        while ( (unsigned __int8)std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int,int>(
                                   v21,
                                   v17,
                                   v8) );
        std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator++(&v11);
        std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>::_Unchecked_splice(
          v11,
          v10,
          v12);
      }
      else
      {
        std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator++(&v11);
        if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator!=(
                                &v11,
                                &v10) )
          std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>::_Unchecked_splice(
            v11,
            v10,
            v12);
        *v16 = v10;
      }
    }
LABEL_4:
    v10 = v12;
  }
  v19[0] = 0;
  return std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Clear_guard::~_Clear_guard(v19);
}

```

## disassembly

```asm
0x180018bd0  mov     [rsp+arg_8], rdx
0x180018bd5  mov     [rsp+arg_0], rcx
0x180018bda  sub     rsp, 0A8h
0x180018be1  mov     rax, [rsp+0A8h+arg_0]
0x180018be9  add     rax, 18h
0x180018bed  mov     rcx, rax
0x180018bf0  call    ?max_size@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@@std@@@std@@QEBA_KXZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::max_size(void)
0x180018bf5  shr     rax, 1
0x180018bf8  mov     rcx, rax; unsigned __int64
0x180018bfb  call    ?_Floor_of_log_2@std@@YAK_K@Z; std::_Floor_of_log_2(unsigned __int64)
0x180018c00  mov     [rsp+0A8h+var_68], eax
0x180018c04  mov     eax, [rsp+0A8h+var_68]
0x180018c08  mov     ecx, 1
0x180018c0d  mov     [rsp+0A8h+var_38], rcx
0x180018c12  movzx   ecx, al
0x180018c15  mov     rax, [rsp+0A8h+var_38]
0x180018c1a  shl     rax, cl
0x180018c1d  mov     [rsp+0A8h+var_30], rax
0x180018c22  mov     rax, [rsp+0A8h+var_30]
0x180018c27  cmp     [rsp+0A8h+arg_8], rax
0x180018c2f  jbe     short loc_180018C3F
0x180018c31  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180018c38  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018c3f  mov     rcx, [rsp+0A8h+arg_8]; unsigned __int64
0x180018c47  call    ?_Ceiling_of_log_2@std@@YAK_K@Z; std::_Ceiling_of_log_2(unsigned __int64)
0x180018c4c  mov     ecx, 1
0x180018c51  mov     [rsp+0A8h+var_28], rcx
0x180018c59  movzx   ecx, al
0x180018c5c  mov     rax, [rsp+0A8h+var_28]
0x180018c64  shl     rax, cl
0x180018c67  mov     [rsp+0A8h+arg_8], rax
0x180018c6f  lea     rdx, [rsp+0A8h+var_60]
0x180018c74  mov     rcx, [rsp+0A8h+arg_0]
0x180018c7c  call    ?_Unchecked_end@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_end(void)
0x180018c81  mov     rax, [rsp+0A8h+arg_0]
0x180018c89  add     rax, 18h
0x180018c8d  mov     [rsp+0A8h+var_20], rax
0x180018c95  mov     rax, [rsp+0A8h+arg_8]
0x180018c9d  shl     rax, 1
0x180018ca0  mov     r8, [rsp+0A8h+var_60]
0x180018ca5  mov     rdx, rax
0x180018ca8  mov     rcx, [rsp+0A8h+var_20]
0x180018cb0  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>)
0x180018cb5  mov     rax, [rsp+0A8h+arg_8]
0x180018cbd  dec     rax
0x180018cc0  mov     rcx, [rsp+0A8h+arg_0]
0x180018cc8  mov     [rcx+30h], rax
0x180018ccc  mov     rax, [rsp+0A8h+arg_0]
0x180018cd4  mov     rcx, [rsp+0A8h+arg_8]
0x180018cdc  mov     [rax+38h], rcx
0x180018ce0  mov     rdx, [rsp+0A8h+arg_0]
0x180018ce8  lea     rcx, [rsp+0A8h+var_40]
0x180018ced  call    ??0?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@PEAV?$ComPtr@UIInspectable@@@23@@Z; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>(Microsoft::WRL::ComPtr<IInspectable> *)
0x180018cf2  lea     rdx, [rsp+0A8h+var_88]
0x180018cf7  mov     rcx, [rsp+0A8h+arg_0]
0x180018cff  call    ?_Unchecked_begin@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_begin(void)
0x180018d04  nop
0x180018d05  mov     rax, [rsp+0A8h+var_88]
0x180018d0a  mov     [rsp+0A8h+var_78], rax
0x180018d0f  jmp     short loc_180018D1B
0x180018d11  mov     rax, [rsp+0A8h+var_78]
0x180018d16  mov     [rsp+0A8h+var_88], rax
0x180018d1b  lea     rdx, [rsp+0A8h+var_60]
0x180018d20  lea     rcx, [rsp+0A8h+var_88]
0x180018d25  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> const &)
0x180018d2a  movzx   eax, al
0x180018d2d  test    eax, eax
0x180018d2f  jz      loc_180018F1A
0x180018d35  lea     rcx, [rsp+0A8h+var_78]
0x180018d3a  call    ??E?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator++(void)
0x180018d3f  lea     rcx, [rsp+0A8h+var_88]
0x180018d44  call    ??D?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@QEBAAEAU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@1@XZ; std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator*(void)
0x180018d49  mov     rcx, rax
0x180018d4c  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180018d51  mov     [rsp+0A8h+var_50], rax
0x180018d56  mov     rdx, [rsp+0A8h+var_50]
0x180018d5b  mov     rcx, [rsp+0A8h+arg_0]
0x180018d63  call    ?bucket@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KAEBH@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(int const &)
0x180018d68  mov     [rsp+0A8h+var_48], rax
0x180018d6d  mov     rax, [rsp+0A8h+var_48]
0x180018d72  shl     rax, 1
0x180018d75  mov     rcx, [rsp+0A8h+arg_0]
0x180018d7d  mov     rcx, [rcx+18h]
0x180018d81  lea     rax, [rcx+rax*8]
0x180018d85  mov     [rsp+0A8h+var_70], rax
0x180018d8a  mov     rax, [rsp+0A8h+var_48]
0x180018d8f  shl     rax, 1
0x180018d92  mov     rcx, [rsp+0A8h+arg_0]
0x180018d9a  mov     rcx, [rcx+18h]
0x180018d9e  lea     rax, [rcx+rax*8+8]
0x180018da3  mov     [rsp+0A8h+var_58], rax
0x180018da8  lea     rdx, [rsp+0A8h+var_60]
0x180018dad  mov     rcx, [rsp+0A8h+var_70]
0x180018db2  call    ??8?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator==(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> const &)
0x180018db7  movzx   eax, al
0x180018dba  test    eax, eax
0x180018dbc  jz      short loc_180018DDD
0x180018dbe  mov     rax, [rsp+0A8h+var_70]
0x180018dc3  mov     rcx, [rsp+0A8h+var_88]
0x180018dc8  mov     [rax], rcx
0x180018dcb  mov     rax, [rsp+0A8h+var_58]
0x180018dd0  mov     rcx, [rsp+0A8h+var_88]
0x180018dd5  mov     [rax], rcx
0x180018dd8  jmp     loc_180018D11
0x180018ddd  mov     rax, [rsp+0A8h+var_58]
0x180018de2  mov     rax, [rax]
0x180018de5  mov     [rsp+0A8h+var_80], rax
0x180018dea  mov     rax, [rsp+0A8h+arg_0]
0x180018df2  mov     [rsp+0A8h+var_18], rax
0x180018dfa  lea     rcx, [rsp+0A8h+var_80]
0x180018dff  call    ??D?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEBAAEBU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@1@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator*(void)
0x180018e04  mov     rcx, rax
0x180018e07  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180018e0c  mov     r8, rax
0x180018e0f  mov     rdx, [rsp+0A8h+var_50]
0x180018e14  mov     rcx, [rsp+0A8h+var_18]
0x180018e1c  call    ??$?RHH@?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@QEBA_NAEBH0@Z; std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int,int>(int const &,int const &)
0x180018e21  movzx   eax, al
0x180018e24  test    eax, eax
0x180018e26  jnz     short loc_180018E70
0x180018e28  lea     rcx, [rsp+0A8h+var_80]
0x180018e2d  call    ??E?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator++(void)
0x180018e32  nop
0x180018e33  lea     rdx, [rsp+0A8h+var_88]
0x180018e38  lea     rcx, [rsp+0A8h+var_80]
0x180018e3d  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> const &)
0x180018e42  movzx   eax, al
0x180018e45  test    eax, eax
0x180018e47  jz      short loc_180018E5E
0x180018e49  mov     r8, [rsp+0A8h+var_78]
0x180018e4e  mov     rdx, [rsp+0A8h+var_88]
0x180018e53  mov     rcx, [rsp+0A8h+var_80]
0x180018e58  call    ?_Unchecked_splice@?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@SAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@QEAU32@00@Z; std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>::_Unchecked_splice(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const)
0x180018e5d  nop
0x180018e5e  mov     rax, [rsp+0A8h+var_58]
0x180018e63  mov     rcx, [rsp+0A8h+var_88]
0x180018e68  mov     [rax], rcx
0x180018e6b  jmp     loc_180018D11
0x180018e70  lea     rdx, [rsp+0A8h+var_80]
0x180018e75  mov     rcx, [rsp+0A8h+var_70]
0x180018e7a  call    ??8?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator==(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> const &)
0x180018e7f  movzx   eax, al
0x180018e82  test    eax, eax
0x180018e84  jz      short loc_180018EA9
0x180018e86  mov     r8, [rsp+0A8h+var_78]
0x180018e8b  mov     rdx, [rsp+0A8h+var_88]
0x180018e90  mov     rcx, [rsp+0A8h+var_80]
0x180018e95  call    ?_Unchecked_splice@?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@SAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@QEAU32@00@Z; std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>::_Unchecked_splice(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const)
0x180018e9a  mov     rax, [rsp+0A8h+var_70]
0x180018e9f  mov     rcx, [rsp+0A8h+var_88]
0x180018ea4  mov     [rax], rcx
0x180018ea7  jmp     short loc_180018F15
0x180018ea9  mov     rax, [rsp+0A8h+arg_0]
0x180018eb1  mov     [rsp+0A8h+var_10], rax
0x180018eb9  lea     rcx, [rsp+0A8h+var_80]
0x180018ebe  call    ??F?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator--(void)
0x180018ec3  mov     rcx, rax
0x180018ec6  call    ??D?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEBAAEBU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@1@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator*(void)
0x180018ecb  mov     rcx, rax
0x180018ece  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180018ed3  mov     r8, rax
0x180018ed6  mov     rdx, [rsp+0A8h+var_50]
0x180018edb  mov     rcx, [rsp+0A8h+var_10]
0x180018ee3  call    ??$?RHH@?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@QEBA_NAEBH0@Z; std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int,int>(int const &,int const &)
0x180018ee8  movzx   eax, al
0x180018eeb  test    eax, eax
0x180018eed  jnz     short loc_180018F10
0x180018eef  lea     rcx, [rsp+0A8h+var_80]
0x180018ef4  call    ??E?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,std::_Iterator_base0>::operator++(void)
0x180018ef9  mov     r8, [rsp+0A8h+var_78]
0x180018efe  mov     rdx, [rsp+0A8h+var_88]
0x180018f03  mov     rcx, [rsp+0A8h+var_80]
0x180018f08  call    ?_Unchecked_splice@?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@SAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@QEAU32@00@Z; std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>::_Unchecked_splice(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const)
0x180018f0d  nop
0x180018f0e  jmp     short loc_180018F15
0x180018f10  jmp     loc_180018E70
0x180018f15  jmp     loc_180018D11
0x180018f1a  mov     [rsp+0A8h+var_40], 0
0x180018f23  lea     rcx, [rsp+0A8h+var_40]
0x180018f28  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180018f2d  nop
0x180018f2e  add     rsp, 0A8h
0x180018f35  retn
```
