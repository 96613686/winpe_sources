# std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::emplace<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>(std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject> &&)

- ea: `0x18001740c`
- end: `0x180017598`
- name: `??$emplace@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@1@@Z`
- size: `396`
- prototype: `__int64 __fastcall(float *, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180019ee0`

## callees

- `0x180015c58`
- `0x1800168f4`
- `0x18001740c`
- `0x180017ed8`
- `0x18001b528`
- `0x18001baec`
- `0x18001be20`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017471`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017471`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::emplace<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>(
        float *a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 appended; // r14
  __int64 v7; // rdx
  float v8; // xmm0_4
  __int64 v9; // rcx
  float v10; // xmm1_4
  __int64 v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // rbx
  __int64 v14; // rdx
  _QWORD *v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r9
  _BYTE v20[8]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v21; // [rsp+28h] [rbp-40h]
  _OWORD v22[3]; // [rsp+30h] [rbp-38h] BYREF

  appended = std::_Fnv1a_append_bytes((unsigned __int64)a1, a3, 8u);
  std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(
    a1,
    v22,
    a3,
    appended);
  if ( !*((_QWORD *)&v22[0] + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0x492492492492492LL )
      std::_Xlength_error("unordered_map/set too long");
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>(
      v20,
      a1 + 2);
    v7 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v7 < 0 )
      v8 = (float)(v7 & 1 | (unsigned int)((unsigned __int64)v7 >> 1))
         + (float)(v7 & 1 | (unsigned int)((unsigned __int64)v7 >> 1));
    else
      v8 = (float)(int)v7;
    v9 = *((_QWORD *)a1 + 7);
    if ( v9 < 0 )
    {
      v11 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v9 >> 1);
      v10 = (float)(int)v11 + (float)(int)v11;
    }
    else
    {
      v10 = (float)(int)v9;
    }
    if ( (float)(v8 / v10) <= *a1 )
    {
      v13 = v21;
    }
    else
    {
      v12 = std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Forced_rehash(
        a1,
        v12);
      v13 = v21;
      v22[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(
                            a1,
                            v22,
                            v21 + 2,
                            appended);
    }
    v21 = 0;
    v14 = *(_QWORD *)&v22[0];
    v15 = *(_QWORD **)(*(_QWORD *)&v22[0] + 8LL);
    ++*((_QWORD *)a1 + 2);
    *v13 = v14;
    v13[1] = v15;
    *v15 = v13;
    *(_QWORD *)(v14 + 8) = v13;
    v16 = 2 * (appended & *((_QWORD *)a1 + 6));
    v17 = *((_QWORD *)a1 + 3);
    v18 = *(_QWORD *)(v17 + 16 * (appended & *((_QWORD *)a1 + 6)));
    if ( v18 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v17 + 16 * (appended & *((_QWORD *)a1 + 6))) = v13;
LABEL_19:
      *(_QWORD *)(v17 + 8 * v16 + 8) = v13;
      goto LABEL_20;
    }
    if ( v18 == v14 )
    {
      *(_QWORD *)(v17 + 16 * (appended & *((_QWORD *)a1 + 6))) = v13;
    }
    else if ( *(_QWORD **)(v17 + 16 * (appended & *((_QWORD *)a1 + 6)) + 8) == v15 )
    {
      goto LABEL_19;
    }
LABEL_20:
    *(_QWORD *)a2 = v13;
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>(v20);
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v22[0] + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18001740c  push    rbx
0x18001740e  push    rbp
0x18001740f  push    rsi
0x180017410  push    rdi
0x180017411  push    r14
0x180017413  sub     rsp, 40h
0x180017417  mov     rbx, r8
0x18001741a  mov     rdi, rdx
0x18001741d  mov     rsi, rcx
0x180017420  mov     r8d, 8; unsigned __int64
0x180017426  mov     rdx, rbx; unsigned __int8 *
0x180017429  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001742e  mov     r14, rax
0x180017431  mov     r9, rax
0x180017434  mov     r8, rbx
0x180017437  lea     rdx, [rsp+68h+var_38]
0x18001743c  mov     rcx, rsi
0x18001743f  call    ??$_Find_last@_K@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@AEB_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(unsigned __int64 const &,unsigned __int64)
0x180017444  mov     rdx, qword ptr [rsp+68h+var_38+8]
0x180017449  test    rdx, rdx
0x18001744c  jz      short loc_18001745A
0x18001744e  mov     [rdi], rdx
0x180017451  mov     byte ptr [rdi+8], 0
0x180017455  jmp     loc_18001758A
0x18001745a  mov     rax, 492492492492492h
0x180017464  cmp     [rsi+10h], rax
0x180017468  jnz     short loc_180017478
0x18001746a  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180017471  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017478  lea     rdx, [rsi+8]
0x18001747c  lea     rcx, [rsp+68h+var_48]
0x180017481  call    ??$?0U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@$$QEAU?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>(std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>> &,std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject> &&)
0x180017486  nop
0x180017487  mov     rdx, [rsi+10h]
0x18001748b  add     rdx, 1
0x18001748f  xorps   xmm0, xmm0
0x180017492  js      short loc_18001749B
0x180017494  cvtsi2ss xmm0, rdx
0x180017499  jmp     short loc_1800174B3
0x18001749b  mov     rcx, rdx
0x18001749e  shr     rcx, 1
0x1800174a1  mov     rax, rdx
0x1800174a4  and     eax, 1
0x1800174a7  or      rcx, rax
0x1800174aa  cvtsi2ss xmm0, rcx
0x1800174af  addss   xmm0, xmm0
0x1800174b3  mov     rcx, [rsi+38h]
0x1800174b7  xorps   xmm1, xmm1
0x1800174ba  test    rcx, rcx
0x1800174bd  js      short loc_1800174C6
0x1800174bf  cvtsi2ss xmm1, rcx
0x1800174c4  jmp     short loc_1800174DB
0x1800174c6  mov     rax, rcx
0x1800174c9  shr     rax, 1
0x1800174cc  and     ecx, 1
0x1800174cf  or      rax, rcx
0x1800174d2  cvtsi2ss xmm1, rax
0x1800174d7  addss   xmm1, xmm1
0x1800174db  divss   xmm0, xmm1
0x1800174df  comiss  xmm0, dword ptr [rsi]
0x1800174e2  jbe     short loc_18001751B
0x1800174e4  mov     rcx, rsi
0x1800174e7  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x1800174ec  mov     rdx, rax
0x1800174ef  mov     rcx, rsi
0x1800174f2  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Forced_rehash(unsigned __int64)
0x1800174f7  mov     rbx, [rsp+68h+var_40]
0x1800174fc  lea     r8, [rbx+10h]
0x180017500  mov     r9, r14
0x180017503  lea     rdx, [rsp+68h+var_38]
0x180017508  mov     rcx, rsi
0x18001750b  call    ??$_Find_last@_K@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@AEB_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(unsigned __int64 const &,unsigned __int64)
0x180017510  movups  xmm0, xmmword ptr [rax]
0x180017513  movdqu  [rsp+68h+var_38], xmm0
0x180017519  jmp     short loc_180017520
0x18001751b  mov     rbx, [rsp+68h+var_40]
0x180017520  mov     [rsp+68h+var_40], 0
0x180017529  mov     rdx, qword ptr [rsp+68h+var_38]
0x18001752e  mov     r8, [rdx+8]
0x180017532  inc     qword ptr [rsi+10h]
0x180017536  mov     [rbx], rdx
0x180017539  mov     [rbx+8], r8
0x18001753d  mov     [r8], rbx
0x180017540  mov     [rdx+8], rbx
0x180017544  mov     rax, [rsi+30h]
0x180017548  and     rax, r14
0x18001754b  add     rax, rax
0x18001754e  mov     rcx, [rsi+18h]
0x180017552  mov     r9, [rcx+rax*8]
0x180017556  cmp     r9, [rsi+8]
0x18001755a  jnz     short loc_180017562
0x18001755c  mov     [rcx+rax*8], rbx
0x180017560  jmp     short loc_180017574
0x180017562  cmp     r9, rdx
0x180017565  jnz     short loc_18001756D
0x180017567  mov     [rcx+rax*8], rbx
0x18001756b  jmp     short loc_180017579
0x18001756d  cmp     [rcx+rax*8+8], r8
0x180017572  jnz     short loc_180017579
0x180017574  mov     [rcx+rax*8+8], rbx
0x180017579  mov     [rdi], rbx
0x18001757c  mov     byte ptr [rdi+8], 1
0x180017580  lea     rcx, [rsp+68h+var_48]
0x180017585  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>(void)
0x18001758a  mov     rax, rdi
0x18001758d  add     rsp, 40h
0x180017591  pop     r14
0x180017593  pop     rdi
0x180017594  pop     rsi
0x180017595  pop     rbp
0x180017596  pop     rbx
0x180017597  retn
```
