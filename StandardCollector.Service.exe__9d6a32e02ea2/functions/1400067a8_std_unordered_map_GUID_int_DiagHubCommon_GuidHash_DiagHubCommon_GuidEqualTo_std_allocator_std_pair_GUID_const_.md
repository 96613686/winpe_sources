# std::unordered_map<_GUID,int,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo,std::allocator<std::pair<_GUID const,int>>>::insert<std::pair<_GUID,int>,0>(std::pair<_GUID,int> &&)

- ea: `0x1400067a8`
- end: `0x14000697a`
- name: `??$insert@U?$pair@U_GUID@@H@std@@$0A@@?$unordered_map@U_GUID@@HUGuidHash@DiagHubCommon@@UGuidEqualTo@3@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@U_GUID@@H@1@@Z`
- size: `466`
- prototype: `__int64 __fastcall(float *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004d90`

## callees

- `0x1400067a8`
- `0x140006c80`
- `0x140007484`
- `0x140013834`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006854`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006854`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall std::unordered_map<_GUID,int,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo,std::allocator<std::pair<_GUID const,int>>>::insert<std::pair<_GUID,int>,0>(
        float *a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 v6; // rbp
  __int64 v7; // rdx
  char v8; // bl
  unsigned __int64 i; // rcx
  unsigned __int64 j; // rcx
  __int64 v11; // rbp
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  float v14; // xmm0_4
  __int64 v15; // rcx
  float v16; // xmm1_4
  __int64 v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 result; // rax
  __int128 v24; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v25; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v26; // [rsp+38h] [rbp-40h]

  v6 = 0xCBF29CE484222325uLL;
  v7 = 0xCBF29CE484222325uLL;
  v8 = 0;
  for ( i = 0; i < 8; ++i )
    v7 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ (unsigned __int64)v7);
  for ( j = 0; j < 8; ++j )
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + j + 8) ^ (unsigned __int64)v6);
  v11 = v7 ^ v6;
  std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
    a1,
    &v24,
    a3,
    v11);
  if ( !*((_QWORD *)&v24 + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v25 = a1 + 2;
    v26 = 0;
    v12 = operator new(0x28u);
    v26 = v12;
    *((_OWORD *)v12 + 1) = *(_OWORD *)a3;
    *((_DWORD *)v12 + 8) = a3[4];
    v13 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v13 < 0 )
      v14 = (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1))
          + (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1));
    else
      v14 = (float)(int)v13;
    v15 = *((_QWORD *)a1 + 7);
    if ( v15 < 0 )
    {
      v17 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v15 >> 1);
      v16 = (float)(int)v17 + (float)(int)v17;
    }
    else
    {
      v16 = (float)(int)v15;
    }
    if ( (float)(v14 / v16) > *a1 )
    {
      std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::_Rehash_for_1(a1);
      v24 = *(_OWORD *)std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
                         a1,
                         &v25,
                         v12 + 2,
                         v11);
    }
    v18 = v24;
    v19 = *(_QWORD **)(v24 + 8);
    ++*((_QWORD *)a1 + 2);
    *v12 = v18;
    v12[1] = v19;
    *v19 = v12;
    *(_QWORD *)(v18 + 8) = v12;
    v20 = 2 * (v11 & *((_QWORD *)a1 + 6));
    v21 = *((_QWORD *)a1 + 3);
    v22 = *(_QWORD *)(v21 + 16 * (v11 & *((_QWORD *)a1 + 6)));
    if ( v22 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v21 + 16 * (v11 & *((_QWORD *)a1 + 6))) = v12;
LABEL_22:
      *(_QWORD *)(v21 + 8 * v20 + 8) = v12;
      goto LABEL_23;
    }
    if ( v22 == v18 )
    {
      *(_QWORD *)(v21 + 16 * (v11 & *((_QWORD *)a1 + 6))) = v12;
    }
    else if ( *(_QWORD **)(v21 + 16 * (v11 & *((_QWORD *)a1 + 6)) + 8) == v19 )
    {
      goto LABEL_22;
    }
LABEL_23:
    *(_QWORD *)a2 = v12;
    v8 = 1;
    goto LABEL_24;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v24 + 1);
LABEL_24:
  result = a2;
  *(_BYTE *)(a2 + 8) = v8;
  return result;
}

```

## disassembly

```asm
0x1400067a8  mov     [rsp+arg_18], rbx
0x1400067ad  push    rbp
0x1400067ae  push    rsi
0x1400067af  push    rdi
0x1400067b0  push    r12
0x1400067b2  push    r13
0x1400067b4  push    r14
0x1400067b6  push    r15
0x1400067b8  sub     rsp, 40h
0x1400067bc  mov     r15, r8
0x1400067bf  mov     rsi, rdx
0x1400067c2  mov     rdi, rcx
0x1400067c5  mov     rbp, 0CBF29CE484222325h
0x1400067cf  mov     rdx, rbp
0x1400067d2  xor     ebx, ebx
0x1400067d4  mov     ecx, ebx
0x1400067d6  mov     r8, 100000001B3h
0x1400067e0  lea     r14d, [rbx+8]
0x1400067e4  movzx   eax, byte ptr [r15+rcx]
0x1400067e9  xor     rdx, rax
0x1400067ec  imul    rdx, r8
0x1400067f0  inc     rcx
0x1400067f3  cmp     rcx, r14
0x1400067f6  jb      short loc_1400067E4
0x1400067f8  mov     rcx, rbx
0x1400067fb  movzx   eax, byte ptr [r15+rcx+8]
0x140006801  xor     rbp, rax
0x140006804  imul    rbp, r8
0x140006808  inc     rcx
0x14000680b  cmp     rcx, r14
0x14000680e  jb      short loc_1400067FB
0x140006810  xor     rbp, rdx
0x140006813  mov     r9, rbp
0x140006816  mov     r8, r15
0x140006819  lea     rdx, [rsp+78h+var_58]
0x14000681e  mov     rcx, rdi
0x140006821  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x140006826  mov     rax, qword ptr [rsp+78h+var_58+8]
0x14000682b  test    rax, rax
0x14000682e  jz      short loc_140006838
0x140006830  mov     [rsi], rax
0x140006833  jmp     loc_14000695B
0x140006838  lea     r12, [rdi+8]
0x14000683c  mov     rax, 666666666666666h
0x140006846  cmp     [r12+8], rax
0x14000684b  jnz     short loc_14000685B
0x14000684d  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x140006854  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000685b  mov     [rsp+78h+var_48], r12
0x140006860  mov     [rsp+78h+var_40], rbx
0x140006865  mov     ecx, 28h ; '('; Size
0x14000686a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000686f  mov     rbx, rax
0x140006872  mov     [rsp+78h+var_40], rax
0x140006877  movups  xmm0, xmmword ptr [r15]
0x14000687b  movdqu  xmmword ptr [rax+10h], xmm0
0x140006880  mov     eax, [r15+10h]
0x140006884  mov     [rbx+20h], eax
0x140006887  mov     rcx, [rdi+10h]
0x14000688b  add     rcx, 1
0x14000688f  xorps   xmm0, xmm0
0x140006892  js      short loc_14000689B
0x140006894  cvtsi2ss xmm0, rcx
0x140006899  jmp     short loc_1400068B0
0x14000689b  mov     rax, rcx
0x14000689e  shr     rax, 1
0x1400068a1  and     ecx, 1
0x1400068a4  or      rax, rcx
0x1400068a7  cvtsi2ss xmm0, rax
0x1400068ac  addss   xmm0, xmm0
0x1400068b0  mov     rcx, [rdi+38h]
0x1400068b4  xorps   xmm1, xmm1
0x1400068b7  test    rcx, rcx
0x1400068ba  js      short loc_1400068C3
0x1400068bc  cvtsi2ss xmm1, rcx
0x1400068c1  jmp     short loc_1400068D8
0x1400068c3  mov     rax, rcx
0x1400068c6  shr     rax, 1
0x1400068c9  and     ecx, 1
0x1400068cc  or      rax, rcx
0x1400068cf  cvtsi2ss xmm1, rax
0x1400068d4  addss   xmm1, xmm1
0x1400068d8  divss   xmm0, xmm1
0x1400068dc  comiss  xmm0, dword ptr [rdi]
0x1400068df  jbe     short loc_140006906
0x1400068e1  mov     rcx, rdi
0x1400068e4  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::_Rehash_for_1(void)
0x1400068e9  mov     r9, rbp
0x1400068ec  lea     r8, [rbx+10h]
0x1400068f0  lea     rdx, [rsp+78h+var_48]
0x1400068f5  mov     rcx, rdi
0x1400068f8  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x1400068fd  movups  xmm0, xmmword ptr [rax]
0x140006900  movdqu  [rsp+78h+var_58], xmm0
0x140006906  mov     rdx, qword ptr [rsp+78h+var_58]
0x14000690b  mov     r8, [rdx+8]
0x14000690f  inc     qword ptr [rdi+10h]
0x140006913  mov     [rbx], rdx
0x140006916  mov     [rbx+8], r8
0x14000691a  mov     [r8], rbx
0x14000691d  mov     [rdx+8], rbx
0x140006921  mov     rax, [rdi+30h]
0x140006925  and     rax, rbp
0x140006928  add     rax, rax
0x14000692b  mov     rcx, [rdi+18h]
0x14000692f  mov     r9, [rcx+rax*8]
0x140006933  cmp     r9, [r12]
0x140006937  jnz     short loc_14000693F
0x140006939  mov     [rcx+rax*8], rbx
0x14000693d  jmp     short loc_140006951
0x14000693f  cmp     r9, rdx
0x140006942  jnz     short loc_14000694A
0x140006944  mov     [rcx+rax*8], rbx
0x140006948  jmp     short loc_140006956
0x14000694a  cmp     [rcx+rax*8+8], r8
0x14000694f  jnz     short loc_140006956
0x140006951  mov     [rcx+rax*8+8], rbx
0x140006956  mov     [rsi], rbx
0x140006959  mov     bl, 1
0x14000695b  mov     rax, rsi
0x14000695e  mov     [rax+r14], bl
0x140006962  mov     rbx, [rsp+78h+arg_18]
0x14000696a  add     rsp, 40h
0x14000696e  pop     r15
0x140006970  pop     r14
0x140006972  pop     r13
0x140006974  pop     r12
0x140006976  pop     rdi
0x140006977  pop     rsi
0x140006978  pop     rbp
0x140006979  retn
```
