# std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Try_emplace<_RPC_ASYNC_STATE * const &,>(_RPC_ASYNC_STATE * const &)

- ea: `0x18000819c`
- end: `0x18000838c`
- name: `??$_Try_emplace@AEBQEAU_RPC_ASYNC_STATE@@$$V@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_RPC_ASYNC_STATE@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009798`
- `0x18000c270`

## callees

- `0x18000294c`
- `0x18000819c`
- `0x1800090c0`
- `0x18000bec8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008235`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008235`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Try_emplace<_RPC_ASYNC_STATE * const &,>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rbp
  unsigned __int64 i; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rax
  _QWORD *v10; // r12
  _QWORD *v11; // rsi
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  float v14; // xmm0_4
  __int64 v15; // rcx
  float v16; // xmm1_4
  __int64 v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // r8
  __int64 v25; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v26; // [rsp+28h] [rbp-40h]

  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ (unsigned __int64)v6);
  v8 = *(_QWORD *)(a1 + 24);
  v9 = *(_QWORD **)(v8 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8);
  v10 = (_QWORD *)(a1 + 8);
  v11 = *(_QWORD **)(a1 + 8);
  if ( v9 == v11 )
  {
LABEL_8:
    if ( *(_QWORD *)(a1 + 16) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v25 = a1 + 8;
    v12 = operator new(0x20u);
    v26 = v12;
    v12[2] = *a3;
    v12[3] = 0;
    v13 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v13 < 0 )
      v14 = (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1))
          + (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1));
    else
      v14 = (float)(int)v13;
    v15 = *(_QWORD *)(a1 + 56);
    if ( v15 < 0 )
    {
      v17 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v15 >> 1);
      v16 = (float)(int)v17 + (float)(int)v17;
    }
    else
    {
      v16 = (float)(int)v15;
    }
    if ( (float)(v14 / v16) > *(float *)a1 )
    {
      std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Rehash_for_1(a1);
      v18 = *(_QWORD *)(a1 + 24);
      v19 = *(_QWORD **)(v18 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8);
      v11 = (_QWORD *)*v10;
      if ( v19 != (_QWORD *)*v10 )
      {
        while ( v12[2] != v19[2] )
        {
          if ( v19 == *(_QWORD **)(v18 + 16 * (v6 & *(_QWORD *)(a1 + 48))) )
          {
            v11 = v19;
            goto LABEL_23;
          }
          v19 = (_QWORD *)v19[1];
        }
        v11 = (_QWORD *)*v19;
      }
    }
LABEL_23:
    v26 = 0;
    v20 = (_QWORD *)v11[1];
    ++*(_QWORD *)(a1 + 16);
    *v12 = v11;
    v12[1] = v20;
    *v20 = v12;
    v11[1] = v12;
    v21 = 2 * (v6 & *(_QWORD *)(a1 + 48));
    v22 = *(_QWORD *)(a1 + 24);
    v23 = *(_QWORD **)(v22 + 16 * (v6 & *(_QWORD *)(a1 + 48)));
    if ( v23 == (_QWORD *)*v10 )
    {
      *(_QWORD *)(v22 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v12;
LABEL_28:
      *(_QWORD *)(v22 + 8 * v21 + 8) = v12;
      goto LABEL_29;
    }
    if ( v23 == v11 )
    {
      *(_QWORD *)(v22 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v12;
    }
    else if ( *(_QWORD **)(v22 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8) == v20 )
    {
      goto LABEL_28;
    }
LABEL_29:
    *(_QWORD *)a2 = v12;
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(&v25);
    return a2;
  }
  while ( *a3 != v9[2] )
  {
    if ( v9 == *(_QWORD **)(v8 + 16 * (v6 & *(_QWORD *)(a1 + 48))) )
    {
      v11 = v9;
      goto LABEL_8;
    }
    v9 = (_QWORD *)v9[1];
  }
  *(_QWORD *)a2 = v9;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18000819c  push    rbx
0x18000819e  push    rbp
0x18000819f  push    rsi
0x1800081a0  push    rdi
0x1800081a1  push    r12
0x1800081a3  push    r14
0x1800081a5  push    r15
0x1800081a7  sub     rsp, 30h
0x1800081ab  mov     r15, r8
0x1800081ae  mov     r14, rdx
0x1800081b1  mov     rdi, rcx
0x1800081b4  mov     rbp, 0CBF29CE484222325h
0x1800081be  xor     ecx, ecx
0x1800081c0  movzx   eax, byte ptr [r8+rcx]
0x1800081c5  xor     rbp, rax
0x1800081c8  mov     rdx, 100000001B3h
0x1800081d2  imul    rbp, rdx
0x1800081d6  inc     rcx
0x1800081d9  cmp     rcx, 8
0x1800081dd  jb      short loc_1800081C0
0x1800081df  mov     rcx, [rdi+30h]
0x1800081e3  and     rcx, rbp
0x1800081e6  add     rcx, rcx
0x1800081e9  mov     rdx, [rdi+18h]
0x1800081ed  mov     rax, [rdx+rcx*8+8]
0x1800081f2  lea     r12, [rdi+8]
0x1800081f6  mov     rsi, [r12]
0x1800081fa  cmp     rax, rsi
0x1800081fd  jz      short loc_18000821E
0x1800081ff  mov     r8, [rdx+rcx*8]
0x180008203  mov     rcx, [r15]
0x180008206  cmp     rcx, [rax+10h]
0x18000820a  jz      loc_180008372
0x180008210  cmp     rax, r8
0x180008213  jz      short loc_18000821B
0x180008215  mov     rax, [rax+8]
0x180008219  jmp     short loc_180008206
0x18000821b  mov     rsi, rax
0x18000821e  mov     rax, 7FFFFFFFFFFFFFFh
0x180008228  cmp     [rdi+10h], rax
0x18000822c  jnz     short loc_18000823C
0x18000822e  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180008235  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000823c  mov     [rsp+68h+var_48], r12
0x180008241  mov     [rsp+68h+var_40], 0
0x18000824a  mov     ecx, 20h ; ' '; Size
0x18000824f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008254  mov     rbx, rax
0x180008257  mov     [rsp+68h+var_40], rax
0x18000825c  mov     rcx, [r15]
0x18000825f  mov     [rax+10h], rcx
0x180008263  mov     qword ptr [rax+18h], 0
0x18000826b  mov     rcx, [rdi+10h]
0x18000826f  add     rcx, 1
0x180008273  xorps   xmm0, xmm0
0x180008276  js      short loc_18000827F
0x180008278  cvtsi2ss xmm0, rcx
0x18000827d  jmp     short loc_180008294
0x18000827f  mov     rax, rcx
0x180008282  shr     rax, 1
0x180008285  and     ecx, 1
0x180008288  or      rax, rcx
0x18000828b  cvtsi2ss xmm0, rax
0x180008290  addss   xmm0, xmm0
0x180008294  mov     rcx, [rdi+38h]
0x180008298  xorps   xmm1, xmm1
0x18000829b  test    rcx, rcx
0x18000829e  js      short loc_1800082A7
0x1800082a0  cvtsi2ss xmm1, rcx
0x1800082a5  jmp     short loc_1800082BC
0x1800082a7  mov     rax, rcx
0x1800082aa  shr     rax, 1
0x1800082ad  and     ecx, 1
0x1800082b0  or      rax, rcx
0x1800082b3  cvtsi2ss xmm1, rax
0x1800082b8  addss   xmm1, xmm1
0x1800082bc  divss   xmm0, xmm1
0x1800082c0  comiss  xmm0, dword ptr [rdi]
0x1800082c3  jbe     short loc_18000830A
0x1800082c5  mov     rcx, rdi
0x1800082c8  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Rehash_for_1(void)
0x1800082cd  mov     rcx, [rdi+30h]
0x1800082d1  and     rcx, rbp
0x1800082d4  add     rcx, rcx
0x1800082d7  mov     rdx, [rdi+18h]
0x1800082db  mov     rax, [rdx+rcx*8+8]
0x1800082e0  mov     rsi, [r12]
0x1800082e4  cmp     rax, rsi
0x1800082e7  jz      short loc_18000830A
0x1800082e9  mov     r8, [rdx+rcx*8]
0x1800082ed  mov     rcx, [rbx+10h]
0x1800082f1  cmp     rcx, [rax+10h]
0x1800082f5  jz      short loc_180008307
0x1800082f7  cmp     rax, r8
0x1800082fa  jz      short loc_180008302
0x1800082fc  mov     rax, [rax+8]
0x180008300  jmp     short loc_1800082F1
0x180008302  mov     rsi, rax
0x180008305  jmp     short loc_18000830A
0x180008307  mov     rsi, [rax]
0x18000830a  mov     [rsp+68h+var_40], 0
0x180008313  mov     rdx, [rsi+8]
0x180008317  inc     qword ptr [rdi+10h]
0x18000831b  mov     [rbx], rsi
0x18000831e  mov     [rbx+8], rdx
0x180008322  mov     [rdx], rbx
0x180008325  mov     [rsi+8], rbx
0x180008329  mov     rax, [rdi+30h]
0x18000832d  and     rax, rbp
0x180008330  add     rax, rax
0x180008333  mov     rcx, [rdi+18h]
0x180008337  mov     r8, [rcx+rax*8]
0x18000833b  cmp     r8, [r12]
0x18000833f  jnz     short loc_180008347
0x180008341  mov     [rcx+rax*8], rbx
0x180008345  jmp     short loc_180008359
0x180008347  cmp     r8, rsi
0x18000834a  jnz     short loc_180008352
0x18000834c  mov     [rcx+rax*8], rbx
0x180008350  jmp     short loc_18000835E
0x180008352  cmp     [rcx+rax*8+8], rdx
0x180008357  jnz     short loc_18000835E
0x180008359  mov     [rcx+rax*8+8], rbx
0x18000835e  mov     [r14], rbx
0x180008361  mov     byte ptr [r14+8], 1
0x180008366  lea     rcx, [rsp+68h+var_48]
0x18000836b  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(void)
0x180008370  jmp     short loc_18000837A
0x180008372  mov     [r14], rax
0x180008375  mov     byte ptr [r14+8], 0
0x18000837a  mov     rax, r14
0x18000837d  add     rsp, 30h
0x180008381  pop     r15
0x180008383  pop     r14
0x180008385  pop     r12
0x180008387  pop     rdi
0x180008388  pop     rsi
0x180008389  pop     rbp
0x18000838a  pop     rbx
0x18000838b  retn
```
