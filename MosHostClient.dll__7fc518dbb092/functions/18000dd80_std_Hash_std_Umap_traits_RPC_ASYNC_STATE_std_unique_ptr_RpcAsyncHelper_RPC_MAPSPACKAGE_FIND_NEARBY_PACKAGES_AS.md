# std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Rehash_for_1(void)

- ea: `0x18000dd80`
- end: `0x18000dfa5`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ`
- size: `549`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c580`

## callees

- `0x180002f94`
- `0x18000bbc4`
- `0x18000cc3c`
- `0x18000dd80`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000de40`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000de40`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Rehash_for_1(
        __int64 a1)
{
  __int64 v1; // rdx
  bool v3; // sf
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  float v6; // xmm0_4
  float v7; // xmm0_4
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  __int64 v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // r8
  unsigned __int64 i; // r9
  __int64 v20; // rdx
  __int64 v21; // r11
  __int64 v22; // r10
  _QWORD *v23; // rdx
  __int64 v24; // r8
  _QWORD *v25; // rdi
  _QWORD *v26; // r9
  _QWORD *v27; // r8
  _QWORD *v28; // rdx
  _QWORD *v29; // rdi
  _QWORD *v30; // r10
  _QWORD *v31; // r9
  _QWORD *v32; // r8
  _QWORD *v33; // rdx
  _QWORD *v34; // r9
  _QWORD *v35; // r8
  _QWORD *v36; // rdx
  unsigned __int64 *v37; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v3 = v1 + 1 < 0;
  v4 = v1 + 1;
  v5 = *(_QWORD *)(a1 + 56);
  if ( v3 )
    v6 = (float)(int)(v4 & 1 | (v4 >> 1)) + (float)(int)(v4 & 1 | (v4 >> 1));
  else
    v6 = (float)(int)v4;
  v7 = o_ceilf_0(v6 / *(float *)a1);
  v8 = 0;
  if ( v7 >= 9.223372e18 )
  {
    v7 = v7 - 9.223372e18;
    if ( v7 < 9.223372e18 )
      v8 = 0x8000000000000000uLL;
  }
  v9 = v8 + (unsigned int)(int)v7;
  v10 = 8;
  if ( v9 > 8 )
    v10 = v9;
  if ( v5 < v10 )
  {
    if ( v5 >= 0x200 || (v5 *= 8LL, v5 < v10) )
      v5 = v10;
  }
  LODWORD(v37) = 0;
  _BitScanReverse64(&v11, 0xFFFFFFFFFFFFFFFuLL);
  if ( v5 > 1LL << v11 )
    std::_Xlength_error("invalid hash bucket count");
  v12 = v5 - 1;
  LODWORD(v37) = 0;
  v13 = *(_QWORD *)(a1 + 8);
  _BitScanReverse64(&v14, v12 | 1);
  v15 = 1LL << ((unsigned __int8)v14 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::_Assign_grow(
    a1 + 24,
    2 * v15,
    v13);
  *(_QWORD *)(a1 + 56) = v15;
  *(_QWORD *)(a1 + 48) = v15 - 1;
  v16 = **(_QWORD ***)(a1 + 8);
  v17 = v16;
  while ( v16 != (_QWORD *)v13 )
  {
    v17 = (_QWORD *)*v17;
    v18 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 8; ++i )
    {
      v20 = *((unsigned __int8 *)v16 + i + 16);
      v18 = 0x100000001B3LL * (v20 ^ v18);
    }
    v21 = *(_QWORD *)(a1 + 24);
    v22 = 2 * (v18 & *(_QWORD *)(a1 + 48));
    if ( *(_QWORD *)(v21 + 16 * (v18 & *(_QWORD *)(a1 + 48))) == v13 )
    {
      *(_QWORD *)(v21 + 16 * (v18 & *(_QWORD *)(a1 + 48))) = v16;
LABEL_21:
      *(_QWORD *)(v21 + 8 * v22 + 8) = v16;
      goto LABEL_29;
    }
    v23 = *(_QWORD **)(v21 + 16 * (v18 & *(_QWORD *)(a1 + 48)) + 8);
    v24 = v16[2];
    if ( v24 == v23[2] )
    {
      v25 = (_QWORD *)*v23;
      if ( (_QWORD *)*v23 != v16 )
      {
        v26 = (_QWORD *)v16[1];
        *v26 = v17;
        v27 = (_QWORD *)v17[1];
        *v27 = v25;
        v28 = (_QWORD *)v25[1];
        *v28 = v16;
        v25[1] = v27;
        v17[1] = v26;
        v16[1] = v28;
      }
      goto LABEL_21;
    }
    while ( 1 )
    {
      v29 = v23 + 1;
      if ( *(_QWORD **)(v21 + 8 * v22) == v23 )
        break;
      v23 = (_QWORD *)*v29;
      if ( v24 == *(_QWORD *)(*v29 + 16LL) )
      {
        v30 = (_QWORD *)*v23;
        v31 = (_QWORD *)v16[1];
        *v31 = v17;
        v32 = (_QWORD *)v17[1];
        *v32 = v30;
        v33 = (_QWORD *)v30[1];
        *v33 = v16;
        v30[1] = v32;
        v17[1] = v31;
        v16[1] = v33;
        goto LABEL_29;
      }
    }
    v34 = (_QWORD *)v16[1];
    *v34 = v17;
    v35 = (_QWORD *)v17[1];
    *v35 = v23;
    v36 = (_QWORD *)*v29;
    *v36 = v16;
    *v29 = v35;
    v17[1] = v34;
    v16[1] = v36;
    *(_QWORD *)(v21 + 8 * v22) = v16;
LABEL_29:
    v16 = v17;
  }
  v37 = 0;
  std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Clear_guard::~_Clear_guard(&v37);
}

```

## disassembly

```asm
0x18000dd80  push    rbx
0x18000dd82  push    rsi
0x18000dd83  push    rdi
0x18000dd84  push    r14
0x18000dd86  sub     rsp, 28h
0x18000dd8a  mov     rdx, [rcx+10h]
0x18000dd8e  mov     rsi, rcx
0x18000dd91  add     rdx, 1
0x18000dd95  mov     rbx, [rcx+38h]
0x18000dd99  xorps   xmm0, xmm0
0x18000dd9c  js      short loc_18000DDA5
0x18000dd9e  cvtsi2ss xmm0, rdx
0x18000dda3  jmp     short loc_18000DDBA
0x18000dda5  mov     rax, rdx
0x18000dda8  and     edx, 1
0x18000ddab  shr     rax, 1
0x18000ddae  or      rax, rdx
0x18000ddb1  cvtsi2ss xmm0, rax
0x18000ddb6  addss   xmm0, xmm0
0x18000ddba  divss   xmm0, dword ptr [rcx]; X
0x18000ddbe  call    _o_ceilf_0
0x18000ddc3  movss   xmm1, cs:__real@5f000000
0x18000ddcb  xor     ecx, ecx
0x18000ddcd  comiss  xmm0, xmm1
0x18000ddd0  jb      short loc_18000DDE8
0x18000ddd2  subss   xmm0, xmm1
0x18000ddd6  comiss  xmm0, xmm1
0x18000ddd9  jnb     short loc_18000DDE8
0x18000dddb  mov     rax, 8000000000000000h
0x18000dde5  mov     rcx, rax
0x18000dde8  cvttss2si rax, xmm0
0x18000dded  add     rax, rcx
0x18000ddf0  mov     ecx, 8
0x18000ddf5  cmp     rax, rcx
0x18000ddf8  cmova   rcx, rax
0x18000ddfc  cmp     rbx, rcx
0x18000ddff  jnb     short loc_18000DE16
0x18000de01  cmp     rbx, 200h
0x18000de08  jnb     short loc_18000DE13
0x18000de0a  shl     rbx, 3
0x18000de0e  cmp     rbx, rcx
0x18000de11  jnb     short loc_18000DE16
0x18000de13  mov     rbx, rcx
0x18000de16  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000de20  mov     dword ptr [rsp+48h+arg_0], 0
0x18000de28  bsr     rcx, rax
0x18000de2c  mov     eax, 1
0x18000de31  shl     rax, cl
0x18000de34  cmp     rbx, rax
0x18000de37  jbe     short loc_18000DE47
0x18000de39  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18000de40  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000de47  lea     rax, [rbx-1]
0x18000de4b  mov     dword ptr [rsp+48h+arg_0], 0
0x18000de53  mov     rbx, [rsi+8]
0x18000de57  or      rax, 1
0x18000de5b  bsr     rcx, rax
0x18000de5f  mov     edi, 1
0x18000de64  mov     r8, rbx
0x18000de67  inc     ecx
0x18000de69  shl     rdi, cl
0x18000de6c  lea     rcx, [rsi+18h]
0x18000de70  lea     rdx, [rdi+rdi]
0x18000de74  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>)
0x18000de79  lea     rax, [rdi-1]
0x18000de7d  mov     [rsi+38h], rdi
0x18000de81  mov     [rsi+30h], rax
0x18000de85  mov     rax, [rsi+8]
0x18000de89  mov     rax, [rax]
0x18000de8c  mov     rcx, rax
0x18000de8f  cmp     rax, rbx
0x18000de92  jz      loc_18000DF88
0x18000de98  mov     rcx, [rcx]
0x18000de9b  mov     r8, 0CBF29CE484222325h
0x18000dea5  xor     r9d, r9d
0x18000dea8  movzx   edx, byte ptr [rax+r9+10h]
0x18000deae  mov     r10, 100000001B3h
0x18000deb8  xor     r8, rdx
0x18000debb  inc     r9
0x18000debe  imul    r8, r10
0x18000dec2  cmp     r9, 8
0x18000dec6  jb      short loc_18000DEA8
0x18000dec8  mov     r10, [rsi+30h]
0x18000decc  mov     r11, [rsi+18h]
0x18000ded0  and     r10, r8
0x18000ded3  add     r10, r10
0x18000ded6  cmp     [r11+r10*8], rbx
0x18000deda  jnz     short loc_18000DEEA
0x18000dedc  mov     [r11+r10*8], rax
0x18000dee0  mov     [r11+r10*8+8], rax
0x18000dee5  jmp     loc_18000DF80
0x18000deea  mov     rdx, [r11+r10*8+8]
0x18000deef  mov     r8, [rax+10h]
0x18000def3  cmp     r8, [rdx+10h]
0x18000def7  jnz     short loc_18000DF24
0x18000def9  mov     rdi, [rdx]
0x18000defc  cmp     rdi, rax
0x18000deff  jz      short loc_18000DEE0
0x18000df01  mov     r9, [rax+8]
0x18000df05  mov     [r9], rcx
0x18000df08  mov     r8, [rcx+8]
0x18000df0c  mov     [r8], rdi
0x18000df0f  mov     rdx, [rdi+8]
0x18000df13  mov     [rdx], rax
0x18000df16  mov     [rdi+8], r8
0x18000df1a  mov     [rcx+8], r9
0x18000df1e  mov     [rax+8], rdx
0x18000df22  jmp     short loc_18000DEE0
0x18000df24  lea     rdi, [rdx+8]
0x18000df28  cmp     [r11+r10*8], rdx
0x18000df2c  jz      short loc_18000DF5D
0x18000df2e  mov     rdx, [rdi]
0x18000df31  cmp     r8, [rdx+10h]
0x18000df35  jnz     short loc_18000DF24
0x18000df37  mov     r10, [rdx]
0x18000df3a  mov     r9, [rax+8]
0x18000df3e  mov     [r9], rcx
0x18000df41  mov     r8, [rcx+8]
0x18000df45  mov     [r8], r10
0x18000df48  mov     rdx, [r10+8]
0x18000df4c  mov     [rdx], rax
0x18000df4f  mov     [r10+8], r8
0x18000df53  mov     [rcx+8], r9
0x18000df57  mov     [rax+8], rdx
0x18000df5b  jmp     short loc_18000DF80
0x18000df5d  mov     r9, [rax+8]
0x18000df61  mov     [r9], rcx
0x18000df64  mov     r8, [rcx+8]
0x18000df68  mov     [r8], rdx
0x18000df6b  mov     rdx, [rdi]
0x18000df6e  mov     [rdx], rax
0x18000df71  mov     [rdi], r8
0x18000df74  mov     [rcx+8], r9
0x18000df78  mov     [rax+8], rdx
0x18000df7c  mov     [r11+r10*8], rax
0x18000df80  mov     rax, rcx
0x18000df83  jmp     loc_18000DE8F
0x18000df88  lea     rcx, [rsp+48h+arg_0]
0x18000df8d  mov     [rsp+48h+arg_0], 0
0x18000df96  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000df9b  add     rsp, 28h
0x18000df9f  pop     r14
0x18000dfa1  pop     rdi
0x18000dfa2  pop     rsi
0x18000dfa3  pop     rbx
0x18000dfa4  retn
```
