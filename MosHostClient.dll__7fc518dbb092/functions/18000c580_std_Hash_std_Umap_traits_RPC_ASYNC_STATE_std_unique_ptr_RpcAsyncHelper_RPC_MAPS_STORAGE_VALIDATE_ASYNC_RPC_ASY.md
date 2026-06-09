# std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Try_emplace<_RPC_ASYNC_STATE * const &,>(_RPC_ASYNC_STATE * const &)

- ea: `0x18000c580`
- end: `0x18000c769`
- name: `??$_Try_emplace@AEBQEAU_RPC_ASYNC_STATE@@$$V@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_RPC_ASYNC_STATE@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cd98`
- `0x18000e2c0`
- `0x18000e5f8`
- `0x18000e908`
- `0x18000f6f4`

## callees

- `0x18000294c`
- `0x18000c580`
- `0x18000dd80`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c61f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c61f`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Try_emplace<_RPC_ASYNC_STATE * const &,>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rbp
  unsigned __int64 i; // rcx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  _QWORD *v10; // r12
  _QWORD *v11; // rsi
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  float v14; // xmm0_4
  __int64 v15; // rcx
  float v16; // xmm1_4
  __int64 v17; // rax
  __int64 v18; // r8
  _QWORD *v19; // rcx
  _QWORD *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // r8

  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ (unsigned __int64)v6);
  v8 = *(_QWORD *)(a1 + 24);
  v9 = *(_QWORD **)(v8 + 16 * (*(_QWORD *)(a1 + 48) & v6) + 8);
  v10 = (_QWORD *)(a1 + 8);
  v11 = *(_QWORD **)(a1 + 8);
  if ( v9 == v11 )
  {
LABEL_8:
    if ( *(_QWORD *)(a1 + 16) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v12 = operator new(0x20u);
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
      std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Rehash_for_1(a1);
      v18 = *(_QWORD *)(a1 + 24);
      v19 = *(_QWORD **)(v18 + 16 * (*(_QWORD *)(a1 + 48) & v6) + 8);
      v11 = (_QWORD *)*v10;
      if ( v19 != (_QWORD *)*v10 )
      {
        while ( v12[2] != v19[2] )
        {
          if ( v19 == *(_QWORD **)(v18 + 16 * (*(_QWORD *)(a1 + 48) & v6)) )
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
    v20 = (_QWORD *)v11[1];
    ++*(_QWORD *)(a1 + 16);
    *v12 = v11;
    v12[1] = v20;
    *v20 = v12;
    v11[1] = v12;
    v21 = *(_QWORD *)(a1 + 24);
    v22 = 2 * (v6 & *(_QWORD *)(a1 + 48));
    v23 = *(_QWORD **)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48)));
    if ( v23 == (_QWORD *)*v10 )
    {
      *(_QWORD *)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v12;
LABEL_28:
      *(_QWORD *)(v21 + 8 * v22 + 8) = v12;
      goto LABEL_29;
    }
    if ( v23 == v11 )
    {
      *(_QWORD *)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v12;
    }
    else if ( *(_QWORD **)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8) == v20 )
    {
      goto LABEL_28;
    }
LABEL_29:
    *(_QWORD *)a2 = v12;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  while ( *a3 != v9[2] )
  {
    if ( v9 == *(_QWORD **)(v8 + 16 * (*(_QWORD *)(a1 + 48) & v6)) )
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
0x18000c580  push    rbx
0x18000c582  push    rbp
0x18000c583  push    rsi
0x18000c584  push    rdi
0x18000c585  push    r12
0x18000c587  push    r14
0x18000c589  push    r15
0x18000c58b  sub     rsp, 30h
0x18000c58f  mov     r15, r8
0x18000c592  mov     r14, rdx
0x18000c595  mov     rdi, rcx
0x18000c598  mov     rbp, 0CBF29CE484222325h
0x18000c5a2  xor     ecx, ecx
0x18000c5a4  movzx   eax, byte ptr [r8+rcx]
0x18000c5a9  xor     rbp, rax
0x18000c5ac  mov     rdx, 100000001B3h
0x18000c5b6  imul    rbp, rdx
0x18000c5ba  inc     rcx
0x18000c5bd  cmp     rcx, 8
0x18000c5c1  jb      short loc_18000C5A4
0x18000c5c3  mov     rdx, rbp
0x18000c5c6  and     rdx, [rdi+30h]
0x18000c5ca  mov     r8, [rdi+18h]
0x18000c5ce  mov     rax, rdx
0x18000c5d1  add     rax, rax
0x18000c5d4  mov     rcx, [r8+rax*8+8]
0x18000c5d9  lea     r12, [rdi+8]
0x18000c5dd  mov     rsi, [r12]
0x18000c5e1  cmp     rcx, rsi
0x18000c5e4  jz      short loc_18000C608
0x18000c5e6  add     rdx, rdx
0x18000c5e9  mov     rax, [r8+rdx*8]
0x18000c5ed  mov     rdx, [r15]
0x18000c5f0  cmp     rdx, [rcx+10h]
0x18000c5f4  jz      loc_18000C74F
0x18000c5fa  cmp     rcx, rax
0x18000c5fd  jz      short loc_18000C605
0x18000c5ff  mov     rcx, [rcx+8]
0x18000c603  jmp     short loc_18000C5F0
0x18000c605  mov     rsi, rcx
0x18000c608  mov     rax, 7FFFFFFFFFFFFFFh
0x18000c612  cmp     [rdi+10h], rax
0x18000c616  jnz     short loc_18000C626
0x18000c618  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000c61f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000c626  mov     [rsp+68h+var_48], r12
0x18000c62b  mov     [rsp+68h+var_40], 0
0x18000c634  mov     ecx, 20h ; ' '; Size
0x18000c639  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c63e  mov     rbx, rax
0x18000c641  mov     [rsp+68h+var_40], rax
0x18000c646  mov     rcx, [r15]
0x18000c649  mov     [rax+10h], rcx
0x18000c64d  mov     qword ptr [rax+18h], 0
0x18000c655  mov     rcx, [rdi+10h]
0x18000c659  add     rcx, 1
0x18000c65d  xorps   xmm0, xmm0
0x18000c660  js      short loc_18000C669
0x18000c662  cvtsi2ss xmm0, rcx
0x18000c667  jmp     short loc_18000C67E
0x18000c669  mov     rax, rcx
0x18000c66c  shr     rax, 1
0x18000c66f  and     ecx, 1
0x18000c672  or      rax, rcx
0x18000c675  cvtsi2ss xmm0, rax
0x18000c67a  addss   xmm0, xmm0
0x18000c67e  mov     rcx, [rdi+38h]
0x18000c682  xorps   xmm1, xmm1
0x18000c685  test    rcx, rcx
0x18000c688  js      short loc_18000C691
0x18000c68a  cvtsi2ss xmm1, rcx
0x18000c68f  jmp     short loc_18000C6A6
0x18000c691  mov     rax, rcx
0x18000c694  shr     rax, 1
0x18000c697  and     ecx, 1
0x18000c69a  or      rax, rcx
0x18000c69d  cvtsi2ss xmm1, rax
0x18000c6a2  addss   xmm1, xmm1
0x18000c6a6  divss   xmm0, xmm1
0x18000c6aa  comiss  xmm0, dword ptr [rdi]
0x18000c6ad  jbe     short loc_18000C6FA
0x18000c6af  mov     rcx, rdi
0x18000c6b2  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Rehash_for_1(void)
0x18000c6b7  mov     rdx, rbp
0x18000c6ba  and     rdx, [rdi+30h]
0x18000c6be  mov     r8, [rdi+18h]
0x18000c6c2  mov     rax, rdx
0x18000c6c5  add     rax, rax
0x18000c6c8  mov     rcx, [r8+rax*8+8]
0x18000c6cd  mov     rsi, [r12]
0x18000c6d1  cmp     rcx, rsi
0x18000c6d4  jz      short loc_18000C6FA
0x18000c6d6  add     rdx, rdx
0x18000c6d9  mov     rax, [r8+rdx*8]
0x18000c6dd  mov     rdx, [rbx+10h]
0x18000c6e1  cmp     rdx, [rcx+10h]
0x18000c6e5  jz      short loc_18000C6F7
0x18000c6e7  cmp     rcx, rax
0x18000c6ea  jz      short loc_18000C6F2
0x18000c6ec  mov     rcx, [rcx+8]
0x18000c6f0  jmp     short loc_18000C6E1
0x18000c6f2  mov     rsi, rcx
0x18000c6f5  jmp     short loc_18000C6FA
0x18000c6f7  mov     rsi, [rcx]
0x18000c6fa  mov     rdx, [rsi+8]
0x18000c6fe  inc     qword ptr [rdi+10h]
0x18000c702  mov     [rbx], rsi
0x18000c705  mov     [rbx+8], rdx
0x18000c709  mov     [rdx], rbx
0x18000c70c  mov     [rsi+8], rbx
0x18000c710  mov     rcx, [rdi+18h]
0x18000c714  mov     rax, [rdi+30h]
0x18000c718  and     rax, rbp
0x18000c71b  add     rax, rax
0x18000c71e  mov     r8, [rcx+rax*8]
0x18000c722  cmp     r8, [r12]
0x18000c726  jnz     short loc_18000C72E
0x18000c728  mov     [rcx+rax*8], rbx
0x18000c72c  jmp     short loc_18000C740
0x18000c72e  cmp     r8, rsi
0x18000c731  jnz     short loc_18000C739
0x18000c733  mov     [rcx+rax*8], rbx
0x18000c737  jmp     short loc_18000C745
0x18000c739  cmp     [rcx+rax*8+8], rdx
0x18000c73e  jnz     short loc_18000C745
0x18000c740  mov     [rcx+rax*8+8], rbx
0x18000c745  mov     [r14], rbx
0x18000c748  mov     byte ptr [r14+8], 1
0x18000c74d  jmp     short loc_18000C757
0x18000c74f  mov     [r14], rcx
0x18000c752  mov     byte ptr [r14+8], 0
0x18000c757  mov     rax, r14
0x18000c75a  add     rsp, 30h
0x18000c75e  pop     r15
0x18000c760  pop     r14
0x18000c762  pop     r12
0x18000c764  pop     rdi
0x18000c765  pop     rsi
0x18000c766  pop     rbp
0x18000c767  pop     rbx
0x18000c768  retn
```
