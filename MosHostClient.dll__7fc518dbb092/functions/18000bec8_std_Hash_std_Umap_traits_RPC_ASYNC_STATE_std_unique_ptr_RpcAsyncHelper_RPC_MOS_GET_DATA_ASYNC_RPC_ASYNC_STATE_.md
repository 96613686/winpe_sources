# std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Rehash_for_1(void)

- ea: `0x18000bec8`
- end: `0x18000c0d7`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ`
- size: `527`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000819c`

## callees

- `0x180002f94`
- `0x18000bbc4`
- `0x18000bec8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bf88`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bf88`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Rehash_for_1(
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
  _QWORD *result; // rax
  _QWORD *v17; // rcx
  __int64 v18; // r10
  unsigned __int64 i; // r8
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
  _BitScanReverse64(&v11, 0xFFFFFFFFFFFFFFFuLL);
  if ( v5 > 1LL << v11 )
    std::_Xlength_error("invalid hash bucket count");
  v12 = v5 - 1;
  v13 = *(_QWORD *)(a1 + 8);
  _BitScanReverse64(&v14, v12 | 1);
  v15 = 1LL << ((unsigned __int8)v14 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::_Assign_grow(
    a1 + 24,
    2 * v15,
    v13);
  *(_QWORD *)(a1 + 56) = v15;
  *(_QWORD *)(a1 + 48) = v15 - 1;
  result = **(_QWORD ***)(a1 + 8);
  v17 = result;
  while ( result != (_QWORD *)v13 )
  {
    v17 = (_QWORD *)*v17;
    v18 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 8; ++i )
    {
      v20 = *((unsigned __int8 *)result + i + 16);
      v18 = 0x100000001B3LL * (v20 ^ v18);
    }
    v21 = *(_QWORD *)(a1 + 24);
    v22 = 2 * (*(_QWORD *)(a1 + 48) & v18);
    if ( *(_QWORD *)(v21 + 8 * v22) == v13 )
    {
      *(_QWORD *)(v21 + 8 * v22) = result;
LABEL_21:
      *(_QWORD *)(v21 + 8 * v22 + 8) = result;
      goto LABEL_29;
    }
    v23 = *(_QWORD **)(v21 + 8 * v22 + 8);
    v24 = result[2];
    if ( v24 == v23[2] )
    {
      v25 = (_QWORD *)*v23;
      if ( (_QWORD *)*v23 != result )
      {
        v26 = (_QWORD *)result[1];
        *v26 = v17;
        v27 = (_QWORD *)v17[1];
        *v27 = v25;
        v28 = (_QWORD *)v25[1];
        *v28 = result;
        v25[1] = v27;
        v17[1] = v26;
        result[1] = v28;
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
        v31 = (_QWORD *)result[1];
        *v31 = v17;
        v32 = (_QWORD *)v17[1];
        *v32 = v30;
        v33 = (_QWORD *)v30[1];
        *v33 = result;
        v30[1] = v32;
        v17[1] = v31;
        result[1] = v33;
        goto LABEL_29;
      }
    }
    v34 = (_QWORD *)result[1];
    *v34 = v17;
    v35 = (_QWORD *)v17[1];
    *v35 = v23;
    v36 = (_QWORD *)*v29;
    *v36 = result;
    *v29 = v35;
    v17[1] = v34;
    result[1] = v36;
    *(_QWORD *)(v21 + 8 * v22) = result;
LABEL_29:
    result = v17;
  }
  return result;
}

```

## disassembly

```asm
0x18000bec8  push    rbx
0x18000beca  push    rsi
0x18000becb  push    rdi
0x18000becc  push    r14
0x18000bece  sub     rsp, 28h
0x18000bed2  mov     rdx, [rcx+10h]
0x18000bed6  mov     rsi, rcx
0x18000bed9  add     rdx, 1
0x18000bedd  mov     rbx, [rcx+38h]
0x18000bee1  xorps   xmm0, xmm0
0x18000bee4  js      short loc_18000BEED
0x18000bee6  cvtsi2ss xmm0, rdx
0x18000beeb  jmp     short loc_18000BF02
0x18000beed  mov     rax, rdx
0x18000bef0  and     edx, 1
0x18000bef3  shr     rax, 1
0x18000bef6  or      rax, rdx
0x18000bef9  cvtsi2ss xmm0, rax
0x18000befe  addss   xmm0, xmm0
0x18000bf02  divss   xmm0, dword ptr [rcx]; X
0x18000bf06  call    _o_ceilf_0
0x18000bf0b  movss   xmm1, cs:__real@5f000000
0x18000bf13  xor     ecx, ecx
0x18000bf15  comiss  xmm0, xmm1
0x18000bf18  jb      short loc_18000BF30
0x18000bf1a  subss   xmm0, xmm1
0x18000bf1e  comiss  xmm0, xmm1
0x18000bf21  jnb     short loc_18000BF30
0x18000bf23  mov     rax, 8000000000000000h
0x18000bf2d  mov     rcx, rax
0x18000bf30  cvttss2si rax, xmm0
0x18000bf35  add     rax, rcx
0x18000bf38  mov     ecx, 8
0x18000bf3d  cmp     rax, rcx
0x18000bf40  cmova   rcx, rax
0x18000bf44  cmp     rbx, rcx
0x18000bf47  jnb     short loc_18000BF5E
0x18000bf49  cmp     rbx, 200h
0x18000bf50  jnb     short loc_18000BF5B
0x18000bf52  shl     rbx, 3
0x18000bf56  cmp     rbx, rcx
0x18000bf59  jnb     short loc_18000BF5E
0x18000bf5b  mov     rbx, rcx
0x18000bf5e  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000bf68  mov     [rsp+48h+arg_0], 0
0x18000bf70  bsr     rcx, rax
0x18000bf74  mov     eax, 1
0x18000bf79  shl     rax, cl
0x18000bf7c  cmp     rbx, rax
0x18000bf7f  jbe     short loc_18000BF8F
0x18000bf81  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18000bf88  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000bf8f  lea     rax, [rbx-1]
0x18000bf93  mov     [rsp+48h+arg_0], 0
0x18000bf9b  mov     rbx, [rsi+8]
0x18000bf9f  or      rax, 1
0x18000bfa3  bsr     rcx, rax
0x18000bfa7  mov     edi, 1
0x18000bfac  mov     r8, rbx
0x18000bfaf  inc     ecx
0x18000bfb1  shl     rdi, cl
0x18000bfb4  lea     rcx, [rsi+18h]
0x18000bfb8  lea     rdx, [rdi+rdi]
0x18000bfbc  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>)
0x18000bfc1  lea     rax, [rdi-1]
0x18000bfc5  mov     [rsi+38h], rdi
0x18000bfc9  mov     [rsi+30h], rax
0x18000bfcd  mov     rax, [rsi+8]
0x18000bfd1  mov     rax, [rax]
0x18000bfd4  mov     rcx, rax
0x18000bfd7  cmp     rax, rbx
0x18000bfda  jz      loc_18000C0CD
0x18000bfe0  mov     rcx, [rcx]
0x18000bfe3  mov     r10, 0CBF29CE484222325h
0x18000bfed  xor     r8d, r8d
0x18000bff0  movzx   edx, byte ptr [rax+r8+10h]
0x18000bff6  mov     r9, 100000001B3h
0x18000c000  xor     r10, rdx
0x18000c003  inc     r8
0x18000c006  imul    r10, r9
0x18000c00a  cmp     r8, 8
0x18000c00e  jb      short loc_18000BFF0
0x18000c010  and     r10, [rsi+30h]
0x18000c014  mov     r11, [rsi+18h]
0x18000c018  add     r10, r10
0x18000c01b  cmp     [r11+r10*8], rbx
0x18000c01f  jnz     short loc_18000C02F
0x18000c021  mov     [r11+r10*8], rax
0x18000c025  mov     [r11+r10*8+8], rax
0x18000c02a  jmp     loc_18000C0C5
0x18000c02f  mov     rdx, [r11+r10*8+8]
0x18000c034  mov     r8, [rax+10h]
0x18000c038  cmp     r8, [rdx+10h]
0x18000c03c  jnz     short loc_18000C069
0x18000c03e  mov     rdi, [rdx]
0x18000c041  cmp     rdi, rax
0x18000c044  jz      short loc_18000C025
0x18000c046  mov     r9, [rax+8]
0x18000c04a  mov     [r9], rcx
0x18000c04d  mov     r8, [rcx+8]
0x18000c051  mov     [r8], rdi
0x18000c054  mov     rdx, [rdi+8]
0x18000c058  mov     [rdx], rax
0x18000c05b  mov     [rdi+8], r8
0x18000c05f  mov     [rcx+8], r9
0x18000c063  mov     [rax+8], rdx
0x18000c067  jmp     short loc_18000C025
0x18000c069  lea     rdi, [rdx+8]
0x18000c06d  cmp     [r11+r10*8], rdx
0x18000c071  jz      short loc_18000C0A2
0x18000c073  mov     rdx, [rdi]
0x18000c076  cmp     r8, [rdx+10h]
0x18000c07a  jnz     short loc_18000C069
0x18000c07c  mov     r10, [rdx]
0x18000c07f  mov     r9, [rax+8]
0x18000c083  mov     [r9], rcx
0x18000c086  mov     r8, [rcx+8]
0x18000c08a  mov     [r8], r10
0x18000c08d  mov     rdx, [r10+8]
0x18000c091  mov     [rdx], rax
0x18000c094  mov     [r10+8], r8
0x18000c098  mov     [rcx+8], r9
0x18000c09c  mov     [rax+8], rdx
0x18000c0a0  jmp     short loc_18000C0C5
0x18000c0a2  mov     r9, [rax+8]
0x18000c0a6  mov     [r9], rcx
0x18000c0a9  mov     r8, [rcx+8]
0x18000c0ad  mov     [r8], rdx
0x18000c0b0  mov     rdx, [rdi]
0x18000c0b3  mov     [rdx], rax
0x18000c0b6  mov     [rdi], r8
0x18000c0b9  mov     [rcx+8], r9
0x18000c0bd  mov     [rax+8], rdx
0x18000c0c1  mov     [r11+r10*8], rax
0x18000c0c5  mov     rax, rcx
0x18000c0c8  jmp     loc_18000BFD7
0x18000c0cd  add     rsp, 28h
0x18000c0d1  pop     r14
0x18000c0d3  pop     rdi
0x18000c0d4  pop     rsi
0x18000c0d5  pop     rbx
0x18000c0d6  retn
```
