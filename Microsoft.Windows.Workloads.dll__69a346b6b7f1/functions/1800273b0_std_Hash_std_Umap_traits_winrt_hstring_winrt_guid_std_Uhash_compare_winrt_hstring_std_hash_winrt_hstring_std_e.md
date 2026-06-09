# std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Try_emplace<winrt::hstring const &,>(winrt::hstring const &)

- ea: `0x1800273b0`
- end: `0x1800276de`
- name: `??$_Try_emplace@AEBUhstring@winrt@@$$V@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@Uguid@2@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@PEAX@std@@_N@1@AEBUhstring@winrt@@@Z`
- size: `814`
- prototype: `__int64 __fastcall(__int64, __int64, winrt::impl **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800257e0`

## callees

- `0x180015250`
- `0x1800157c0`
- `0x1800273b0`
- `0x180029f00`
- `0x1800323a4`
- `0x180035060`
- `0x18003beb0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Try_emplace<winrt::hstring const &,>(
        __int64 a1,
        __int64 a2,
        winrt::impl **a3)
{
  winrt::impl *v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rdx
  bool v9; // zf
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // rbx
  _QWORD *v14; // rdi
  _QWORD *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rcx
  const wchar_t *v18; // rdx
  winrt::impl *v19; // rax
  size_t v20; // r8
  const wchar_t *v21; // r9
  char *v23; // r14
  struct winrt::impl::hstring_header *v24; // rdx
  float v25; // xmm3_4
  unsigned __int64 v26; // rbx
  __int64 v27; // rcx
  float v28; // xmm0_4
  float v29; // xmm2_4
  __int64 v30; // rcx
  float v31; // xmm0_4
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rcx
  __int64 v35; // rcx
  _QWORD *v36; // rbx
  _QWORD *v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rcx
  const wchar_t *v40; // rdx
  __int64 v41; // rax
  size_t v42; // r8
  const wchar_t *v43; // r9
  _QWORD *v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rcx
  _QWORD *v48; // r8

  v6 = *a3;
  v7 = 0xCBF29CE484222325uLL;
  if ( *a3 )
  {
    v8 = *((unsigned int *)v6 + 1);
    v9 = 2 * v8 == 0;
    v10 = 2 * v8;
    v11 = 0;
    if ( !v9 )
    {
      do
        v7 = 0x100000001B3LL * (*(unsigned __int8 *)(*((_QWORD *)v6 + 2) + v11++) ^ (unsigned __int64)v7);
      while ( v11 < v10 );
    }
  }
  v12 = *(_QWORD *)(a1 + 24);
  v13 = *(_QWORD **)(v12 + 16 * (*(_QWORD *)(a1 + 48) & v7) + 8);
  v14 = *(_QWORD **)(a1 + 8);
  if ( v13 == v14 )
  {
LABEL_21:
    if ( *(_QWORD *)(a1 + 16) == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v23 = (char *)operator new(0x28u);
    *((_QWORD *)v23 + 2) = winrt::impl::duplicate_hstring(*a3, v24);
    *(_OWORD *)(v23 + 24) = 0;
    v25 = *(float *)a1;
    v26 = *(_QWORD *)(a1 + 56);
    v27 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v27 < 0 )
      v28 = (float)(v27 & 1 | (unsigned int)((unsigned __int64)v27 >> 1))
          + (float)(v27 & 1 | (unsigned int)((unsigned __int64)v27 >> 1));
    else
      v28 = (float)(int)v27;
    if ( (v26 & 0x8000000000000000uLL) != 0LL )
    {
      v30 = *(_QWORD *)(a1 + 56) & 1LL | (v26 >> 1);
      v29 = (float)(int)v30 + (float)(int)v30;
    }
    else
    {
      v29 = (float)(int)v26;
    }
    if ( (float)(v28 / v29) > v25 )
    {
      v31 = ceilf_0(v28 / v25);
      v32 = 0;
      if ( v31 >= 9.223372e18 )
      {
        v31 = v31 - 9.223372e18;
        if ( v31 < 9.223372e18 )
          v32 = 0x8000000000000000uLL;
      }
      v33 = v32 + (unsigned int)(int)v31;
      v34 = 8;
      if ( v33 > 8 )
        v34 = v33;
      if ( v26 < v34 )
      {
        if ( v26 >= 0x200 || (v26 *= 8LL, v26 < v34) )
          v26 = v34;
      }
      std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Forced_rehash(
        a1,
        v26);
      v35 = *(_QWORD *)(a1 + 24);
      v36 = *(_QWORD **)(v35 + 16 * (v7 & *(_QWORD *)(a1 + 48)) + 8);
      v14 = *(_QWORD **)(a1 + 8);
      if ( v36 != v14 )
      {
        v37 = *(_QWORD **)(v35 + 16 * (v7 & *(_QWORD *)(a1 + 48)));
        while ( 1 )
        {
          v38 = v36[2];
          if ( v38 )
          {
            v39 = *(unsigned int *)(v38 + 4);
            v40 = *(const wchar_t **)(v38 + 16);
          }
          else
          {
            v39 = 0;
            v40 = &Src;
          }
          v41 = *((_QWORD *)v23 + 2);
          if ( v41 )
          {
            v42 = *(unsigned int *)(v41 + 4);
            v43 = *(const wchar_t **)(v41 + 16);
          }
          else
          {
            v42 = 0;
            v43 = &Src;
          }
          if ( v42 == v39 && (!v42 || wmemcmp(v43, v40, v42) == 0) )
            break;
          if ( v36 == v37 )
          {
            v14 = v36;
            goto LABEL_56;
          }
          v36 = (_QWORD *)v36[1];
        }
        v14 = (_QWORD *)*v36;
      }
    }
LABEL_56:
    v45 = (_QWORD *)v14[1];
    ++*(_QWORD *)(a1 + 16);
    *(_QWORD *)v23 = v14;
    *((_QWORD *)v23 + 1) = v45;
    *v45 = v23;
    v14[1] = v23;
    v46 = 2 * (v7 & *(_QWORD *)(a1 + 48));
    v47 = *(_QWORD *)(a1 + 24);
    v48 = *(_QWORD **)(v47 + 16 * (v7 & *(_QWORD *)(a1 + 48)));
    if ( v48 == *(_QWORD **)(a1 + 8) )
    {
      *(_QWORD *)(v47 + 16 * (v7 & *(_QWORD *)(a1 + 48))) = v23;
LABEL_61:
      *(_QWORD *)(v47 + 8 * v46 + 8) = v23;
      goto LABEL_62;
    }
    if ( v48 == v14 )
    {
      *(_QWORD *)(v47 + 16 * (v7 & *(_QWORD *)(a1 + 48))) = v23;
    }
    else if ( *(_QWORD **)(v47 + 16 * (v7 & *(_QWORD *)(a1 + 48)) + 8) == v45 )
    {
      goto LABEL_61;
    }
LABEL_62:
    *(_QWORD *)a2 = v23;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  v15 = *(_QWORD **)(v12 + 16 * (*(_QWORD *)(a1 + 48) & v7));
  while ( 1 )
  {
    v16 = v13[2];
    if ( v16 )
    {
      v17 = *(unsigned int *)(v16 + 4);
      v18 = *(const wchar_t **)(v16 + 16);
    }
    else
    {
      v17 = 0;
      v18 = &Src;
    }
    v19 = *a3;
    if ( *a3 )
    {
      v20 = *((unsigned int *)v19 + 1);
      v21 = (const wchar_t *)*((_QWORD *)v19 + 2);
    }
    else
    {
      v20 = 0;
      v21 = &Src;
    }
    if ( v20 == v17 && (!v20 || wmemcmp(v21, v18, v20) == 0) )
      break;
    if ( v13 == v15 )
    {
      v14 = v13;
      goto LABEL_21;
    }
    v13 = (_QWORD *)v13[1];
  }
  *(_QWORD *)a2 = v13;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x1800273b0  mov     [rsp+arg_10], rbx
0x1800273b5  mov     [rsp+arg_18], rbp
0x1800273ba  push    rsi
0x1800273bb  push    rdi
0x1800273bc  push    r12
0x1800273be  push    r14
0x1800273c0  push    r15
0x1800273c2  sub     rsp, 30h
0x1800273c6  mov     r15, r8
0x1800273c9  mov     r12, rdx
0x1800273cc  mov     rbp, rcx
0x1800273cf  mov     rax, [r8]
0x1800273d2  mov     rsi, 0CBF29CE484222325h
0x1800273dc  test    rax, rax
0x1800273df  jz      short loc_180027414
0x1800273e1  mov     r8, [rax+10h]
0x1800273e5  mov     edx, [rax+4]
0x1800273e8  add     rdx, rdx
0x1800273eb  mov     ecx, 0
0x1800273f0  jz      short loc_180027414
0x1800273f2  mov     r9, 100000001B3h
0x1800273fc  nop     dword ptr [rax+00h]
0x180027400  movzx   eax, byte ptr [r8+rcx]
0x180027405  xor     rsi, rax
0x180027408  imul    rsi, r9
0x18002740c  inc     rcx
0x18002740f  cmp     rcx, rdx
0x180027412  jb      short loc_180027400
0x180027414  mov     rax, rsi
0x180027417  and     rax, [rbp+30h]
0x18002741b  add     rax, rax
0x18002741e  mov     rcx, [rbp+18h]
0x180027422  mov     rbx, [rcx+rax*8+8]
0x180027427  lea     r14, [rbp+8]
0x18002742b  mov     rdi, [r14]
0x18002742e  cmp     rbx, rdi
0x180027431  jz      short loc_1800274A6
0x180027433  mov     rdi, [rcx+rax*8]
0x180027437  mov     rax, [rbx+10h]
0x18002743b  test    rax, rax
0x18002743e  jz      short loc_180027449
0x180027440  mov     ecx, [rax+4]
0x180027443  mov     rdx, [rax+10h]
0x180027447  jmp     short loc_180027452
0x180027449  xor     ecx, ecx
0x18002744b  lea     rdx, Src; S2
0x180027452  mov     rax, [r15]
0x180027455  test    rax, rax
0x180027458  jz      short loc_180027464
0x18002745a  mov     r8d, [rax+4]
0x18002745e  mov     r9, [rax+10h]
0x180027462  jmp     short loc_18002746E
0x180027464  xor     r8d, r8d; N
0x180027467  lea     r9, Src
0x18002746e  cmp     r8, rcx
0x180027471  jz      short loc_18002747A
0x180027473  mov     ecx, 1
0x180027478  jmp     short loc_180027490
0x18002747a  test    r8, r8
0x18002747d  jnz     short loc_180027483
0x18002747f  xor     ecx, ecx
0x180027481  jmp     short loc_180027490
0x180027483  mov     rcx, r9; S1
0x180027486  call    wmemcmp
0x18002748b  test    eax, eax
0x18002748d  setnz   cl
0x180027490  test    cl, cl
0x180027492  jz      loc_1800276AD
0x180027498  cmp     rbx, rdi
0x18002749b  jz      short loc_1800274A3
0x18002749d  mov     rbx, [rbx+8]
0x1800274a1  jmp     short loc_180027437
0x1800274a3  mov     rdi, rbx
0x1800274a6  mov     rax, 666666666666666h
0x1800274b0  cmp     [rbp+10h], rax
0x1800274b4  jz      loc_1800276D1
0x1800274ba  mov     [rsp+58h+var_38], r14
0x1800274bf  mov     [rsp+58h+var_30], 0
0x1800274c8  mov     ecx, 28h ; '('; Size
0x1800274cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800274d2  mov     r14, rax
0x1800274d5  mov     [rsp+58h+var_30], rax
0x1800274da  mov     rcx, [r15]; this
0x1800274dd  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800274e2  mov     [r14+10h], rax
0x1800274e6  xorps   xmm0, xmm0
0x1800274e9  movups  xmmword ptr [r14+18h], xmm0
0x1800274ee  movss   xmm3, dword ptr [rbp+0]
0x1800274f3  mov     rbx, [rbp+38h]
0x1800274f7  mov     rcx, [rbp+10h]
0x1800274fb  add     rcx, 1
0x1800274ff  xorps   xmm0, xmm0
0x180027502  js      short loc_18002750B
0x180027504  cvtsi2ss xmm0, rcx
0x180027509  jmp     short loc_180027520
0x18002750b  mov     rax, rcx
0x18002750e  shr     rax, 1
0x180027511  and     ecx, 1
0x180027514  or      rax, rcx
0x180027517  cvtsi2ss xmm0, rax
0x18002751c  addss   xmm0, xmm0
0x180027520  xorps   xmm2, xmm2
0x180027523  test    rbx, rbx
0x180027526  js      short loc_18002752F
0x180027528  cvtsi2ss xmm2, rbx
0x18002752d  jmp     short loc_180027547
0x18002752f  mov     rcx, rbx
0x180027532  shr     rcx, 1
0x180027535  mov     rax, rbx
0x180027538  and     eax, 1
0x18002753b  or      rcx, rax
0x18002753e  cvtsi2ss xmm2, rcx
0x180027543  addss   xmm2, xmm2
0x180027547  movaps  xmm1, xmm0
0x18002754a  divss   xmm1, xmm2
0x18002754e  comiss  xmm1, xmm3
0x180027551  jbe     loc_180027656
0x180027557  divss   xmm0, xmm3; X
0x18002755b  call    ceilf_0
0x180027560  xor     ecx, ecx
0x180027562  movss   xmm1, cs:__real@5f000000
0x18002756a  comiss  xmm0, xmm1
0x18002756d  jb      short loc_180027585
0x18002756f  subss   xmm0, xmm1
0x180027573  comiss  xmm0, xmm1
0x180027576  jnb     short loc_180027585
0x180027578  mov     rax, 8000000000000000h
0x180027582  mov     rcx, rax
0x180027585  cvttss2si rax, xmm0
0x18002758a  add     rax, rcx
0x18002758d  mov     ecx, 8
0x180027592  cmp     rax, rcx
0x180027595  cmova   rcx, rax
0x180027599  cmp     rbx, rcx
0x18002759c  jnb     short loc_1800275BA
0x18002759e  cmp     rbx, 200h
0x1800275a5  jnb     short loc_1800275B7
0x1800275a7  lea     rax, ds:0[rbx*8]
0x1800275af  mov     rbx, rax
0x1800275b2  cmp     rax, rcx
0x1800275b5  jnb     short loc_1800275BA
0x1800275b7  mov     rbx, rcx
0x1800275ba  mov     rdx, rbx
0x1800275bd  mov     rcx, rbp
0x1800275c0  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@Uguid@2@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@5@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Forced_rehash(unsigned __int64)
0x1800275c5  mov     rax, [rbp+30h]
0x1800275c9  and     rax, rsi
0x1800275cc  add     rax, rax
0x1800275cf  mov     rcx, [rbp+18h]
0x1800275d3  mov     rbx, [rcx+rax*8+8]
0x1800275d8  mov     rdi, [rbp+8]
0x1800275dc  cmp     rbx, rdi
0x1800275df  jz      short loc_180027656
0x1800275e1  mov     rdi, [rcx+rax*8]
0x1800275e5  mov     rax, [rbx+10h]
0x1800275e9  test    rax, rax
0x1800275ec  jz      short loc_1800275F7
0x1800275ee  mov     ecx, [rax+4]
0x1800275f1  mov     rdx, [rax+10h]
0x1800275f5  jmp     short loc_180027600
0x1800275f7  xor     ecx, ecx
0x1800275f9  lea     rdx, Src; S2
0x180027600  mov     rax, [r14+10h]
0x180027604  test    rax, rax
0x180027607  jz      short loc_180027613
0x180027609  mov     r8d, [rax+4]
0x18002760d  mov     r9, [rax+10h]
0x180027611  jmp     short loc_18002761D
0x180027613  xor     r8d, r8d; N
0x180027616  lea     r9, Src
0x18002761d  cmp     r8, rcx
0x180027620  jz      short loc_180027629
0x180027622  mov     ecx, 1
0x180027627  jmp     short loc_18002763F
0x180027629  test    r8, r8
0x18002762c  jnz     short loc_180027632
0x18002762e  xor     ecx, ecx
0x180027630  jmp     short loc_18002763F
0x180027632  mov     rcx, r9; S1
0x180027635  call    wmemcmp
0x18002763a  test    eax, eax
0x18002763c  setnz   cl
0x18002763f  test    cl, cl
0x180027641  jz      short loc_180027653
0x180027643  cmp     rbx, rdi
0x180027646  jz      short loc_18002764E
0x180027648  mov     rbx, [rbx+8]
0x18002764c  jmp     short loc_1800275E5
0x18002764e  mov     rdi, rbx
0x180027651  jmp     short loc_180027656
0x180027653  mov     rdi, [rbx]
0x180027656  mov     rdx, [rdi+8]
0x18002765a  inc     qword ptr [rbp+10h]
0x18002765e  mov     [r14], rdi
0x180027661  mov     [r14+8], rdx
0x180027665  mov     [rdx], r14
0x180027668  mov     [rdi+8], r14
0x18002766c  mov     rax, [rbp+30h]
0x180027670  and     rax, rsi
0x180027673  add     rax, rax
0x180027676  mov     rcx, [rbp+18h]
0x18002767a  mov     r8, [rcx+rax*8]
0x18002767e  cmp     r8, [rbp+8]
0x180027682  jnz     short loc_18002768A
0x180027684  mov     [rcx+rax*8], r14
0x180027688  jmp     short loc_18002769C
0x18002768a  cmp     r8, rdi
0x18002768d  jnz     short loc_180027695
0x18002768f  mov     [rcx+rax*8], r14
0x180027693  jmp     short loc_1800276A1
0x180027695  cmp     [rcx+rax*8+8], rdx
0x18002769a  jnz     short loc_1800276A1
0x18002769c  mov     [rcx+rax*8+8], r14
0x1800276a1  mov     [r12], r14
0x1800276a5  mov     byte ptr [r12+8], 1
0x1800276ab  jmp     short loc_1800276B7
0x1800276ad  mov     [r12], rbx
0x1800276b1  mov     byte ptr [r12+8], 0
0x1800276b7  mov     rax, r12
0x1800276ba  mov     rbx, [rsp+58h+arg_10]
0x1800276bf  mov     rbp, [rsp+58h+arg_18]
0x1800276c4  add     rsp, 30h
0x1800276c8  pop     r15
0x1800276ca  pop     r14
0x1800276cc  pop     r12
0x1800276ce  pop     rdi
0x1800276cf  pop     rsi
0x1800276d0  retn
0x1800276d1  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x1800276d8  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
