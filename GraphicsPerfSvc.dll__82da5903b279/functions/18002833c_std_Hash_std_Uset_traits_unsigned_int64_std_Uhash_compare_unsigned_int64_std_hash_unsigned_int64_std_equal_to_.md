# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::emplace<unsigned __int64 &>(unsigned __int64 &)

- ea: `0x18002833c`
- end: `0x1800284e8`
- name: `??$emplace@AEA_K@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@std@@_N@1@AEA_K@Z`
- size: `428`
- prototype: `__int64 __fastcall(float *, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180029254`

## callees

- `0x18000c1b8`
- `0x1800168f4`
- `0x180016b40`
- `0x18001b528`
- `0x18001baec`
- `0x18002833c`
- `0x180028e14`
- `0x18002d974`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800283a9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800283a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::emplace<unsigned __int64 &>(
        float *a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 appended; // r15
  size_t size_of; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rdx
  float v10; // xmm0_4
  __int64 v11; // rcx
  float v12; // xmm1_4
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  _QWORD *v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  _QWORD *v21; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v22; // [rsp+28h] [rbp-50h]
  _OWORD v23[4]; // [rsp+30h] [rbp-48h] BYREF

  appended = std::_Fnv1a_append_bytes((unsigned __int64)a1, a3, 8u);
  std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(
    a1,
    v23,
    a3,
    appended);
  if ( !*((_QWORD *)&v23[0] + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v21 = a1 + 2;
    size_of = std::_Get_size_of_n<24>(1);
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v22 = v8;
    v8[2] = *(_QWORD *)a3;
    v9 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v9 < 0 )
      v10 = (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1))
          + (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1));
    else
      v10 = (float)(int)v9;
    v11 = *((_QWORD *)a1 + 7);
    if ( v11 < 0 )
    {
      v13 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v11 >> 1);
      v12 = (float)(int)v13 + (float)(int)v13;
    }
    else
    {
      v12 = (float)(int)v11;
    }
    if ( (float)(v10 / v12) > *a1 )
    {
      v14 = std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Forced_rehash(
        a1,
        v14);
      v23[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(
                            a1,
                            v23,
                            v8 + 2,
                            appended);
    }
    v22 = 0;
    v15 = *(_QWORD *)&v23[0];
    v16 = *(_QWORD **)(*(_QWORD *)&v23[0] + 8LL);
    ++*((_QWORD *)a1 + 2);
    *v8 = v15;
    v8[1] = v16;
    *v16 = v8;
    *(_QWORD *)(v15 + 8) = v8;
    v17 = 2 * (appended & *((_QWORD *)a1 + 6));
    v18 = *((_QWORD *)a1 + 3);
    v19 = *(_QWORD *)(v18 + 16 * (appended & *((_QWORD *)a1 + 6)));
    if ( v19 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v18 + 16 * (appended & *((_QWORD *)a1 + 6))) = v8;
LABEL_18:
      *(_QWORD *)(v18 + 8 * v17 + 8) = v8;
      goto LABEL_19;
    }
    if ( v19 == v15 )
    {
      *(_QWORD *)(v18 + 16 * (appended & *((_QWORD *)a1 + 6))) = v8;
    }
    else if ( *(_QWORD **)(v18 + 16 * (appended & *((_QWORD *)a1 + 6)) + 8) == v16 )
    {
      goto LABEL_18;
    }
LABEL_19:
    *(_QWORD *)a2 = v8;
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>(&v21);
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v23[0] + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18002833c  push    rbx
0x18002833e  push    rbp
0x18002833f  push    rsi
0x180028340  push    rdi
0x180028341  push    r12
0x180028343  push    r14
0x180028345  push    r15
0x180028347  sub     rsp, 40h
0x18002834b  mov     r14, r8
0x18002834e  mov     rdi, rdx
0x180028351  mov     rsi, rcx
0x180028354  mov     r8d, 8; unsigned __int64
0x18002835a  mov     rdx, r14; unsigned __int8 *
0x18002835d  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180028362  mov     r15, rax
0x180028365  mov     r9, rax
0x180028368  mov     r8, r14
0x18002836b  lea     rdx, [rsp+78h+var_48]
0x180028370  mov     rcx, rsi
0x180028373  call    ??$_Find_last@_K@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@AEB_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(unsigned __int64 const &,unsigned __int64)
0x180028378  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18002837d  test    rdx, rdx
0x180028380  jz      short loc_18002838E
0x180028382  mov     [rdi], rdx
0x180028385  mov     byte ptr [rdi+8], 0
0x180028389  jmp     loc_1800284D6
0x18002838e  lea     rbp, [rsi+8]
0x180028392  mov     rax, 0AAAAAAAAAAAAAAAh
0x18002839c  cmp     [rbp+8], rax
0x1800283a0  jnz     short loc_1800283B0
0x1800283a2  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x1800283a9  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800283b0  mov     [rsp+78h+var_58], rbp
0x1800283b5  mov     [rsp+78h+var_50], 0
0x1800283be  mov     ecx, 1
0x1800283c3  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x1800283c8  mov     rcx, rax
0x1800283cb  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800283d0  mov     rbx, rax
0x1800283d3  mov     [rsp+78h+var_50], rax
0x1800283d8  mov     rcx, [r14]
0x1800283db  mov     [rax+10h], rcx
0x1800283df  mov     rdx, [rsi+10h]
0x1800283e3  add     rdx, 1
0x1800283e7  xorps   xmm0, xmm0
0x1800283ea  js      short loc_1800283F3
0x1800283ec  cvtsi2ss xmm0, rdx
0x1800283f1  jmp     short loc_18002840B
0x1800283f3  mov     rcx, rdx
0x1800283f6  shr     rcx, 1
0x1800283f9  mov     rax, rdx
0x1800283fc  and     eax, 1
0x1800283ff  or      rcx, rax
0x180028402  cvtsi2ss xmm0, rcx
0x180028407  addss   xmm0, xmm0
0x18002840b  mov     rcx, [rsi+38h]
0x18002840f  xorps   xmm1, xmm1
0x180028412  test    rcx, rcx
0x180028415  js      short loc_18002841E
0x180028417  cvtsi2ss xmm1, rcx
0x18002841c  jmp     short loc_180028433
0x18002841e  mov     rax, rcx
0x180028421  shr     rax, 1
0x180028424  and     ecx, 1
0x180028427  or      rax, rcx
0x18002842a  cvtsi2ss xmm1, rax
0x18002842f  addss   xmm1, xmm1
0x180028433  divss   xmm0, xmm1
0x180028437  comiss  xmm0, dword ptr [rsi]
0x18002843a  jbe     short loc_18002846C
0x18002843c  mov     rcx, rsi
0x18002843f  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180028444  mov     rdx, rax
0x180028447  mov     rcx, rsi
0x18002844a  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Forced_rehash(unsigned __int64)
0x18002844f  mov     r9, r15
0x180028452  lea     r8, [rbx+10h]
0x180028456  lea     rdx, [rsp+78h+var_48]
0x18002845b  mov     rcx, rsi
0x18002845e  call    ??$_Find_last@_K@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@AEB_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(unsigned __int64 const &,unsigned __int64)
0x180028463  movups  xmm0, xmmword ptr [rax]
0x180028466  movdqu  [rsp+78h+var_48], xmm0
0x18002846c  mov     [rsp+78h+var_50], 0
0x180028475  mov     rdx, qword ptr [rsp+78h+var_48]
0x18002847a  mov     r8, [rdx+8]
0x18002847e  inc     qword ptr [rsi+10h]
0x180028482  mov     [rbx], rdx
0x180028485  mov     [rbx+8], r8
0x180028489  mov     [r8], rbx
0x18002848c  mov     [rdx+8], rbx
0x180028490  mov     rax, [rsi+30h]
0x180028494  and     rax, r15
0x180028497  add     rax, rax
0x18002849a  mov     rcx, [rsi+18h]
0x18002849e  mov     r9, [rcx+rax*8]
0x1800284a2  cmp     r9, [rbp+0]
0x1800284a6  jnz     short loc_1800284AE
0x1800284a8  mov     [rcx+rax*8], rbx
0x1800284ac  jmp     short loc_1800284C0
0x1800284ae  cmp     r9, rdx
0x1800284b1  jnz     short loc_1800284B9
0x1800284b3  mov     [rcx+rax*8], rbx
0x1800284b7  jmp     short loc_1800284C5
0x1800284b9  cmp     [rcx+rax*8+8], r8
0x1800284be  jnz     short loc_1800284C5
0x1800284c0  mov     [rcx+rax*8+8], rbx
0x1800284c5  mov     [rdi], rbx
0x1800284c8  mov     byte ptr [rdi+8], 1
0x1800284cc  lea     rcx, [rsp+78h+var_58]
0x1800284d1  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@_KPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>(void)
0x1800284d6  mov     rax, rdi
0x1800284d9  add     rsp, 40h
0x1800284dd  pop     r15
0x1800284df  pop     r14
0x1800284e1  pop     r12
0x1800284e3  pop     rdi
0x1800284e4  pop     rsi
0x1800284e5  pop     rbp
0x1800284e6  pop     rbx
0x1800284e7  retn
```
