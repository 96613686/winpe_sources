# std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::emplace<std::pair<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>(std::pair<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess> &&)

- ea: `0x1400113e8`
- end: `0x1400115e8`
- name: `??$emplace@U?$pair@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@1@@Z`
- size: `512`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010a70`

## callees

- `0x1400113e8`
- `0x140011634`
- `0x140013834`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140011491`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140011491`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::emplace<std::pair<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbp
  unsigned __int64 i; // rcx
  __int64 v8; // rdx
  __int64 *v9; // rax
  __int64 *v10; // rsi
  _DWORD *v11; // rbx
  __int64 v12; // rcx
  float v13; // xmm0_4
  __int64 v14; // rcx
  float v15; // xmm1_4
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rax
  _QWORD *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 *v22; // r8

  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v6 = 0x100000001B3LL * (*(unsigned __int8 *)(a3 + i) ^ (unsigned __int64)v6);
  v8 = *(_QWORD *)(a1 + 24);
  v9 = *(__int64 **)(v8 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8);
  v10 = *(__int64 **)(a1 + 8);
  if ( v9 == v10 )
  {
LABEL_11:
    if ( *(_QWORD *)(a1 + 16) == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v11 = operator new(0x40u);
    v11[4] = *(_DWORD *)a3;
    v11[6] = *(_DWORD *)(a3 + 8);
    *((_QWORD *)v11 + 4) = *(_QWORD *)(a3 + 16);
    *((_BYTE *)v11 + 40) = *(_BYTE *)(a3 + 24);
    *((_QWORD *)v11 + 6) = *(_QWORD *)(a3 + 32);
    *((_QWORD *)v11 + 7) = *(_QWORD *)(a3 + 40);
    v12 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v12 < 0 )
      v13 = (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1))
          + (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1));
    else
      v13 = (float)(int)v12;
    v14 = *(_QWORD *)(a1 + 56);
    if ( v14 < 0 )
    {
      v16 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v14 >> 1);
      v15 = (float)(int)v16 + (float)(int)v16;
    }
    else
    {
      v15 = (float)(int)v14;
    }
    if ( (float)(v13 / v15) > *(float *)a1 )
    {
      std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::_Rehash_for_1(a1);
      v17 = *(_QWORD *)(a1 + 24);
      v18 = *(__int64 **)(v17 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8);
      v10 = *(__int64 **)(a1 + 8);
      if ( v18 != v10 )
      {
        while ( 1 )
        {
          if ( v11[4] == *((_DWORD *)v18 + 4) )
          {
            v10 = (__int64 *)*v18;
            goto LABEL_26;
          }
          if ( v18 == *(__int64 **)(v17 + 16 * (v6 & *(_QWORD *)(a1 + 48))) )
            break;
          v18 = (__int64 *)v18[1];
        }
        v10 = v18;
      }
    }
LABEL_26:
    v19 = (_QWORD *)v10[1];
    ++*(_QWORD *)(a1 + 16);
    *(_QWORD *)v11 = v10;
    *((_QWORD *)v11 + 1) = v19;
    *v19 = v11;
    v10[1] = (__int64)v11;
    v20 = 2 * (v6 & *(_QWORD *)(a1 + 48));
    v21 = *(_QWORD *)(a1 + 24);
    v22 = *(__int64 **)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48)));
    if ( v22 == *(__int64 **)(a1 + 8) )
    {
      *(_QWORD *)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v11;
LABEL_32:
      *(_QWORD *)(v21 + 8 * v20 + 8) = v11;
      goto LABEL_33;
    }
    if ( v22 == v10 )
    {
      *(_QWORD *)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v11;
    }
    else if ( *(_QWORD **)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8) == v19 )
    {
      goto LABEL_32;
    }
LABEL_33:
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  while ( *(_DWORD *)a3 != *((_DWORD *)v9 + 4) )
  {
    if ( v9 == *(__int64 **)(v8 + 16 * (v6 & *(_QWORD *)(a1 + 48))) )
    {
      v10 = v9;
      goto LABEL_11;
    }
    v9 = (__int64 *)v9[1];
  }
  v10 = (__int64 *)*v9;
  if ( !v9 )
    goto LABEL_11;
  *(_QWORD *)a2 = v9;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x1400113e8  mov     [rsp+arg_18], rbx
0x1400113ed  push    rbp
0x1400113ee  push    rsi
0x1400113ef  push    rdi
0x1400113f0  push    r14
0x1400113f2  push    r15
0x1400113f4  sub     rsp, 30h
0x1400113f8  mov     r15, r8
0x1400113fb  mov     r14, rdx
0x1400113fe  mov     rdi, rcx
0x140011401  mov     rbp, 0CBF29CE484222325h
0x14001140b  xor     ecx, ecx
0x14001140d  movzx   eax, byte ptr [r8+rcx]
0x140011412  xor     rbp, rax
0x140011415  mov     rdx, 100000001B3h
0x14001141f  imul    rbp, rdx
0x140011423  inc     rcx
0x140011426  cmp     rcx, 4
0x14001142a  jb      short loc_14001140D
0x14001142c  mov     rcx, [rdi+30h]
0x140011430  and     rcx, rbp
0x140011433  add     rcx, rcx
0x140011436  mov     rdx, [rdi+18h]
0x14001143a  mov     rax, [rdx+rcx*8+8]
0x14001143f  lea     r9, [rdi+8]
0x140011443  mov     rsi, [r9]
0x140011446  cmp     rax, rsi
0x140011449  jz      short loc_14001147A
0x14001144b  mov     r8, [rdx+rcx*8]
0x14001144f  mov     ecx, [r15]
0x140011452  jmp     short loc_14001145D
0x140011454  cmp     rax, r8
0x140011457  jz      short loc_140011477
0x140011459  mov     rax, [rax+8]
0x14001145d  cmp     ecx, [rax+10h]
0x140011460  jnz     short loc_140011454
0x140011462  mov     rsi, [rax]
0x140011465  test    rax, rax
0x140011468  jz      short loc_14001147A
0x14001146a  mov     [r14], rax
0x14001146d  mov     byte ptr [r14+8], 0
0x140011472  jmp     loc_1400115D4
0x140011477  mov     rsi, rax
0x14001147a  mov     rax, 3FFFFFFFFFFFFFFh
0x140011484  cmp     [rdi+10h], rax
0x140011488  jnz     short loc_140011498
0x14001148a  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x140011491  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140011498  mov     [rsp+58h+var_38], r9
0x14001149d  mov     [rsp+58h+var_30], 0
0x1400114a6  mov     ecx, 40h ; '@'; Size
0x1400114ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400114b0  mov     rbx, rax
0x1400114b3  mov     [rsp+58h+var_30], rax
0x1400114b8  mov     ecx, [r15]
0x1400114bb  mov     [rax+10h], ecx
0x1400114be  mov     ecx, [r15+8]
0x1400114c2  mov     [rax+18h], ecx
0x1400114c5  mov     rcx, [r15+10h]
0x1400114c9  mov     [rax+20h], rcx
0x1400114cd  mov     cl, [r15+18h]
0x1400114d1  mov     [rax+28h], cl
0x1400114d4  mov     rax, [r15+20h]
0x1400114d8  mov     [rbx+30h], rax
0x1400114dc  mov     rax, [r15+28h]
0x1400114e0  mov     [rbx+38h], rax
0x1400114e4  mov     rcx, [rdi+10h]
0x1400114e8  add     rcx, 1
0x1400114ec  xorps   xmm0, xmm0
0x1400114ef  js      short loc_1400114F8
0x1400114f1  cvtsi2ss xmm0, rcx
0x1400114f6  jmp     short loc_14001150D
0x1400114f8  mov     rax, rcx
0x1400114fb  shr     rax, 1
0x1400114fe  and     ecx, 1
0x140011501  or      rax, rcx
0x140011504  cvtsi2ss xmm0, rax
0x140011509  addss   xmm0, xmm0
0x14001150d  mov     rcx, [rdi+38h]
0x140011511  xorps   xmm1, xmm1
0x140011514  test    rcx, rcx
0x140011517  js      short loc_140011520
0x140011519  cvtsi2ss xmm1, rcx
0x14001151e  jmp     short loc_140011535
0x140011520  mov     rax, rcx
0x140011523  shr     rax, 1
0x140011526  and     ecx, 1
0x140011529  or      rax, rcx
0x14001152c  cvtsi2ss xmm1, rax
0x140011531  addss   xmm1, xmm1
0x140011535  divss   xmm0, xmm1
0x140011539  comiss  xmm0, dword ptr [rdi]
0x14001153c  jbe     short loc_14001157C
0x14001153e  mov     rcx, rdi
0x140011541  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::_Rehash_for_1(void)
0x140011546  mov     rcx, [rdi+30h]
0x14001154a  and     rcx, rbp
0x14001154d  add     rcx, rcx
0x140011550  mov     rdx, [rdi+18h]
0x140011554  mov     rax, [rdx+rcx*8+8]
0x140011559  mov     rsi, [rdi+8]
0x14001155d  cmp     rax, rsi
0x140011560  jz      short loc_14001157C
0x140011562  mov     r8, [rdx+rcx*8]
0x140011566  mov     ecx, [rbx+10h]
0x140011569  jmp     short loc_140011574
0x14001156b  cmp     rax, r8
0x14001156e  jz      short loc_1400115B0
0x140011570  mov     rax, [rax+8]
0x140011574  cmp     ecx, [rax+10h]
0x140011577  jnz     short loc_14001156B
0x140011579  mov     rsi, [rax]
0x14001157c  mov     rdx, [rsi+8]
0x140011580  inc     qword ptr [rdi+10h]
0x140011584  mov     [rbx], rsi
0x140011587  mov     [rbx+8], rdx
0x14001158b  mov     [rdx], rbx
0x14001158e  mov     [rsi+8], rbx
0x140011592  mov     rax, [rdi+30h]
0x140011596  and     rax, rbp
0x140011599  add     rax, rax
0x14001159c  mov     rcx, [rdi+18h]
0x1400115a0  mov     r8, [rcx+rax*8]
0x1400115a4  cmp     r8, [rdi+8]
0x1400115a8  jnz     short loc_1400115B5
0x1400115aa  mov     [rcx+rax*8], rbx
0x1400115ae  jmp     short loc_1400115C7
0x1400115b0  mov     rsi, rax
0x1400115b3  jmp     short loc_14001157C
0x1400115b5  cmp     r8, rsi
0x1400115b8  jnz     short loc_1400115C0
0x1400115ba  mov     [rcx+rax*8], rbx
0x1400115be  jmp     short loc_1400115CC
0x1400115c0  cmp     [rcx+rax*8+8], rdx
0x1400115c5  jnz     short loc_1400115CC
0x1400115c7  mov     [rcx+rax*8+8], rbx
0x1400115cc  mov     [r14], rbx
0x1400115cf  mov     byte ptr [r14+8], 1
0x1400115d4  mov     rax, r14
0x1400115d7  mov     rbx, [rsp+58h+arg_18]
0x1400115dc  add     rsp, 30h
0x1400115e0  pop     r15
0x1400115e2  pop     r14
0x1400115e4  pop     rdi
0x1400115e5  pop     rsi
0x1400115e6  pop     rbp
0x1400115e7  retn
```
