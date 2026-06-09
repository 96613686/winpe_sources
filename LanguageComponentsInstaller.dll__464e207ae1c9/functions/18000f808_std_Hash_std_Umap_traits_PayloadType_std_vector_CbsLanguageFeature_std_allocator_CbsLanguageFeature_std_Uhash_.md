# std::_Hash<std::_Umap_traits<PayloadType,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>,std::_Uhash_compare<PayloadType,std::hash<PayloadType>,std::equal_to<PayloadType>>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>>>,0>>::_Try_emplace<PayloadType,>(PayloadType &&)

- ea: `0x18000f808`
- end: `0x18000f9fd`
- name: `??$_Try_emplace@W4PayloadType@@$$V@?$_Hash@V?$_Umap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@V?$_Uhash_compare@W4PayloadType@@U?$hash@W4PayloadType@@@std@@U?$equal_to@W4PayloadType@@@3@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAW4PayloadType@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010094`

## callees

- `0x180003544`
- `0x18000f808`
- `0x1800211f0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f8a6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f8a6`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<enum PayloadType,std::hash<enum PayloadType>,std::equal_to<enum PayloadType>>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Try_emplace<enum PayloadType,>(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 v6; // rbp
  unsigned __int64 i; // rcx
  __int64 v8; // r8
  __int64 *v9; // rcx
  __int64 **v10; // r12
  __int64 *v11; // rsi
  _DWORD *v12; // rbx
  __int64 v13; // rcx
  float v14; // xmm0_4
  __int64 v15; // rcx
  float v16; // xmm1_4
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 *v19; // rcx
  _QWORD *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 *v23; // r8

  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ (unsigned __int64)v6);
  v8 = *(_QWORD *)(a1 + 24);
  v9 = *(__int64 **)(v8 + 16 * (*(_QWORD *)(a1 + 48) & v6) + 8);
  v10 = (__int64 **)(a1 + 8);
  v11 = *(__int64 **)(a1 + 8);
  if ( v9 == v11 )
  {
LABEL_8:
    if ( *(_QWORD *)(a1 + 16) == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v12 = operator new(0x30u);
    v12[4] = *a3;
    *((_QWORD *)v12 + 3) = 0;
    *((_QWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 5) = 0;
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
      std::_Hash<std::_Umap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<enum PayloadType,std::hash<enum PayloadType>,std::equal_to<enum PayloadType>>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Rehash_for_1(a1);
      v18 = *(_QWORD *)(a1 + 24);
      v19 = *(__int64 **)(v18 + 16 * (*(_QWORD *)(a1 + 48) & v6) + 8);
      v11 = *v10;
      if ( v19 != *v10 )
      {
        while ( v12[4] != *((_DWORD *)v19 + 4) )
        {
          if ( v19 == *(__int64 **)(v18 + 16 * (*(_QWORD *)(a1 + 48) & v6)) )
          {
            v11 = v19;
            goto LABEL_23;
          }
          v19 = (__int64 *)v19[1];
        }
        v11 = (__int64 *)*v19;
      }
    }
LABEL_23:
    v20 = (_QWORD *)v11[1];
    ++*(_QWORD *)(a1 + 16);
    *(_QWORD *)v12 = v11;
    *((_QWORD *)v12 + 1) = v20;
    *v20 = v12;
    v11[1] = (__int64)v12;
    v21 = *(_QWORD *)(a1 + 24);
    v22 = 2 * (v6 & *(_QWORD *)(a1 + 48));
    v23 = *(__int64 **)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48)));
    if ( v23 == *v10 )
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
  while ( *a3 != *((_DWORD *)v9 + 4) )
  {
    if ( v9 == *(__int64 **)(v8 + 16 * (*(_QWORD *)(a1 + 48) & v6)) )
    {
      v11 = v9;
      goto LABEL_8;
    }
    v9 = (__int64 *)v9[1];
  }
  *(_QWORD *)a2 = v9;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18000f808  push    rbx
0x18000f80a  push    rbp
0x18000f80b  push    rsi
0x18000f80c  push    rdi
0x18000f80d  push    r12
0x18000f80f  push    r14
0x18000f811  push    r15
0x18000f813  sub     rsp, 30h
0x18000f817  mov     r15, r8
0x18000f81a  mov     r14, rdx
0x18000f81d  mov     rdi, rcx
0x18000f820  mov     rbp, 0CBF29CE484222325h
0x18000f82a  xor     ecx, ecx
0x18000f82c  movzx   eax, byte ptr [r8+rcx]
0x18000f831  xor     rbp, rax
0x18000f834  mov     rdx, 100000001B3h
0x18000f83e  imul    rbp, rdx
0x18000f842  inc     rcx
0x18000f845  cmp     rcx, 4
0x18000f849  jb      short loc_18000F82C
0x18000f84b  mov     rdx, rbp
0x18000f84e  and     rdx, [rdi+30h]
0x18000f852  mov     r8, [rdi+18h]
0x18000f856  mov     rax, rdx
0x18000f859  add     rax, rax
0x18000f85c  mov     rcx, [r8+rax*8+8]
0x18000f861  lea     r12, [rdi+8]
0x18000f865  mov     rsi, [r12]
0x18000f869  cmp     rcx, rsi
0x18000f86c  jz      short loc_18000F88F
0x18000f86e  add     rdx, rdx
0x18000f871  mov     rax, [r8+rdx*8]
0x18000f875  mov     edx, [r15]
0x18000f878  cmp     edx, [rcx+10h]
0x18000f87b  jz      loc_18000F9E3
0x18000f881  cmp     rcx, rax
0x18000f884  jz      short loc_18000F88C
0x18000f886  mov     rcx, [rcx+8]
0x18000f88a  jmp     short loc_18000F878
0x18000f88c  mov     rsi, rcx
0x18000f88f  mov     rax, 555555555555555h
0x18000f899  cmp     [rdi+10h], rax
0x18000f89d  jnz     short loc_18000F8AD
0x18000f89f  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000f8a6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f8ad  mov     [rsp+68h+var_48], r12
0x18000f8b2  mov     [rsp+68h+var_40], 0
0x18000f8bb  mov     ecx, 30h ; '0'; Size
0x18000f8c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f8c5  mov     rbx, rax
0x18000f8c8  mov     [rsp+68h+var_40], rax
0x18000f8cd  mov     eax, [r15]
0x18000f8d0  mov     [rbx+10h], eax
0x18000f8d3  mov     qword ptr [rbx+18h], 0
0x18000f8db  mov     qword ptr [rbx+20h], 0
0x18000f8e3  mov     qword ptr [rbx+28h], 0
0x18000f8eb  mov     rcx, [rdi+10h]
0x18000f8ef  add     rcx, 1
0x18000f8f3  xorps   xmm0, xmm0
0x18000f8f6  js      short loc_18000F8FF
0x18000f8f8  cvtsi2ss xmm0, rcx
0x18000f8fd  jmp     short loc_18000F914
0x18000f8ff  mov     rax, rcx
0x18000f902  shr     rax, 1
0x18000f905  and     ecx, 1
0x18000f908  or      rax, rcx
0x18000f90b  cvtsi2ss xmm0, rax
0x18000f910  addss   xmm0, xmm0
0x18000f914  mov     rcx, [rdi+38h]
0x18000f918  xorps   xmm1, xmm1
0x18000f91b  test    rcx, rcx
0x18000f91e  js      short loc_18000F927
0x18000f920  cvtsi2ss xmm1, rcx
0x18000f925  jmp     short loc_18000F93C
0x18000f927  mov     rax, rcx
0x18000f92a  shr     rax, 1
0x18000f92d  and     ecx, 1
0x18000f930  or      rax, rcx
0x18000f933  cvtsi2ss xmm1, rax
0x18000f938  addss   xmm1, xmm1
0x18000f93c  divss   xmm0, xmm1
0x18000f940  comiss  xmm0, dword ptr [rdi]
0x18000f943  jbe     short loc_18000F98E
0x18000f945  mov     rcx, rdi
0x18000f948  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@V?$_Uhash_compare@W4PayloadType@@U?$hash@W4PayloadType@@@std@@U?$equal_to@W4PayloadType@@@3@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<PayloadType,std::hash<PayloadType>,std::equal_to<PayloadType>>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Rehash_for_1(void)
0x18000f94d  mov     rdx, rbp
0x18000f950  and     rdx, [rdi+30h]
0x18000f954  mov     r8, [rdi+18h]
0x18000f958  mov     rax, rdx
0x18000f95b  add     rax, rax
0x18000f95e  mov     rcx, [r8+rax*8+8]
0x18000f963  mov     rsi, [r12]
0x18000f967  cmp     rcx, rsi
0x18000f96a  jz      short loc_18000F98E
0x18000f96c  add     rdx, rdx
0x18000f96f  mov     rax, [r8+rdx*8]
0x18000f973  mov     edx, [rbx+10h]
0x18000f976  cmp     edx, [rcx+10h]
0x18000f979  jz      short loc_18000F98B
0x18000f97b  cmp     rcx, rax
0x18000f97e  jz      short loc_18000F986
0x18000f980  mov     rcx, [rcx+8]
0x18000f984  jmp     short loc_18000F976
0x18000f986  mov     rsi, rcx
0x18000f989  jmp     short loc_18000F98E
0x18000f98b  mov     rsi, [rcx]
0x18000f98e  mov     rdx, [rsi+8]
0x18000f992  inc     qword ptr [rdi+10h]
0x18000f996  mov     [rbx], rsi
0x18000f999  mov     [rbx+8], rdx
0x18000f99d  mov     [rdx], rbx
0x18000f9a0  mov     [rsi+8], rbx
0x18000f9a4  mov     rcx, [rdi+18h]
0x18000f9a8  mov     rax, [rdi+30h]
0x18000f9ac  and     rax, rbp
0x18000f9af  add     rax, rax
0x18000f9b2  mov     r8, [rcx+rax*8]
0x18000f9b6  cmp     r8, [r12]
0x18000f9ba  jnz     short loc_18000F9C2
0x18000f9bc  mov     [rcx+rax*8], rbx
0x18000f9c0  jmp     short loc_18000F9D4
0x18000f9c2  cmp     r8, rsi
0x18000f9c5  jnz     short loc_18000F9CD
0x18000f9c7  mov     [rcx+rax*8], rbx
0x18000f9cb  jmp     short loc_18000F9D9
0x18000f9cd  cmp     [rcx+rax*8+8], rdx
0x18000f9d2  jnz     short loc_18000F9D9
0x18000f9d4  mov     [rcx+rax*8+8], rbx
0x18000f9d9  mov     [r14], rbx
0x18000f9dc  mov     byte ptr [r14+8], 1
0x18000f9e1  jmp     short loc_18000F9EB
0x18000f9e3  mov     [r14], rcx
0x18000f9e6  mov     byte ptr [r14+8], 0
0x18000f9eb  mov     rax, r14
0x18000f9ee  add     rsp, 30h
0x18000f9f2  pop     r15
0x18000f9f4  pop     r14
0x18000f9f6  pop     r12
0x18000f9f8  pop     rdi
0x18000f9f9  pop     rsi
0x18000f9fa  pop     rbp
0x18000f9fb  pop     rbx
0x18000f9fc  retn
```
