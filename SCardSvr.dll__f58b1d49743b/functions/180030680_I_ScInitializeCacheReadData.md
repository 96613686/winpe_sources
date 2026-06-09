# I_ScInitializeCacheReadData

- ea: `0x180030680`
- end: `0x180030c04`
- name: `I_ScInitializeCacheReadData`
- size: `1412`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180030d4c`

## callees

- `0x1800027f4`
- `0x180005700`
- `0x180015074`
- `0x180018514`
- `0x180023276`
- `0x180028b78`
- `0x18002ab90`
- `0x180030680`
- `0x1800314b0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall I_ScInitializeCacheReadData(__int64 a1, _DWORD *a2, unsigned int a3)
{
  __int64 v3; // r14
  unsigned int v6; // ebx
  PVOID v7; // rcx
  __int64 v8; // r10
  _DWORD *v10; // r15
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r12
  unsigned int v14; // eax
  unsigned int v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdi
  void *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  int v22; // ecx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // r14d
  _WORD *v27; // rbx
  __int64 v28; // rcx
  void *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // r14
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // r8
  unsigned int i; // ebx
  __int64 v39; // rcx
  char *v40; // r13
  void *v41; // rcx
  __int64 v42; // r8
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  _QWORD *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // [rsp+30h] [rbp-30h] BYREF
  __int64 v50; // [rsp+38h] [rbp-28h]
  int v51; // [rsp+40h] [rbp-20h] BYREF
  __int64 v52; // [rsp+48h] [rbp-18h]
  int v53; // [rsp+50h] [rbp-10h]
  __int64 v54; // [rsp+58h] [rbp-8h]
  unsigned int v55; // [rsp+A8h] [rbp+48h]
  unsigned int v56; // [rsp+B0h] [rbp+50h] BYREF

  v3 = a3;
  LODWORD(v50) = 0;
  v49 = 0;
  v56 = 0;
  v6 = 0;
  WppTraceIndent(a1, 0);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  if ( (_DWORD)v3 && a2 && *a2 == 1161906223 )
  {
    v8 = (unsigned int)a2[2];
    v55 = a2[2];
    v7 = (PVOID)(v8 + 16);
    if ( v8 + 16 != v3 )
    {
      v6 = -2146435041;
      goto LABEL_10;
    }
    v10 = a2 + 4;
    if ( (a2[1] & 1) != 0 )
    {
      v6 = UncompressData((unsigned int)v8, a2 + 4, &v56, 0);
      if ( v6 )
        goto LABEL_10;
      v11 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 48))(v56);
      v13 = v11;
      if ( !v11 )
      {
        WppTraceIndent(v12, v6 + 2);
        v6 = 8;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
            WPP_pszIndent);
        }
        goto LABEL_10;
      }
      v14 = UncompressData((unsigned int)a2[2], a2 + 4, &v56, v11);
      v6 = v14;
      if ( v14 )
      {
        if ( v14 == 1359 )
          v6 = -2146893819;
LABEL_78:
        (*(void (__fastcall **)(__int64))(a1 + 56))(v13);
        goto LABEL_10;
      }
      LODWORD(v8) = v56;
      v10 = (_DWORD *)v13;
      v55 = v56;
    }
    else
    {
      v13 = 0;
    }
    v15 = 0;
    while ( 1 )
    {
      if ( v15 >= (unsigned int)v8 )
        goto LABEL_77;
      v16 = (*(__int64 (__fastcall **)(__int64))(a1 + 48))(80);
      v18 = v16;
      if ( !v16 )
        break;
      *(_DWORD *)(v16 + 8) = *(_DWORD *)((char *)v10 + v15);
      v19 = (void *)(*(__int64 (**)(void))(a1 + 48))();
      *(_QWORD *)v18 = v19;
      if ( !v19 )
      {
        WppTraceIndent(v20, 2);
        v6 = 8;
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v48 = 13;
LABEL_67:
          WPP_SF_s(v47[2], v48, &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
        }
LABEL_72:
        I_ServerCacheFreeItem(a1, v18);
        goto LABEL_77;
      }
      memcpy_0(v19, (char *)v10 + v15 + 4, *(unsigned int *)(v18 + 8));
      v21 = v15 + 4 + ((*(_DWORD *)(v18 + 8) + 7) & 0xFFFFFFF8);
      v22 = *(_DWORD *)((char *)v10 + v21);
      v23 = (unsigned int)(v21 + 4);
      *(_DWORD *)(v18 + 12) = v22;
      v24 = *(_QWORD *)((char *)v10 + v23);
      v25 = (unsigned int)(v23 + 8);
      *(_QWORD *)(v18 + 16) = v24;
      v26 = v25 + 16;
      v27 = (_WORD *)((char *)v10 + (unsigned int)(v25 + 16));
      v28 = -1;
      *(_OWORD *)(v18 + 24) = *(_OWORD *)((char *)v10 + v25);
      do
        ++v28;
      while ( v27[v28] );
      v29 = (void *)(*(__int64 (__fastcall **)(__int64))(a1 + 48))(2 * v28 + 2);
      *(_QWORD *)(v18 + 40) = v29;
      if ( !v29 )
      {
        WppTraceIndent(v30, 2);
        v6 = 8;
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v48 = 14;
          goto LABEL_67;
        }
        goto LABEL_72;
      }
      v31 = -1;
      do
        ++v31;
      while ( v27[v31] );
      memcpy_0(v29, v27, 2 * v31 + 2);
      v32 = -1;
      do
        ++v32;
      while ( *(_WORD *)(*(_QWORD *)(v18 + 40) + 2 * v32) );
      v33 = (unsigned int)(v26 + 2 * v32 + 2);
      v34 = *(unsigned int *)((char *)v10 + v33);
      *(_DWORD *)(v18 + 72) = v34;
      v35 = (*(__int64 (__fastcall **)(__int64))(a1 + 48))(8 * v34);
      *(_QWORD *)(v18 + 64) = v35;
      if ( !v35 )
      {
        WppTraceIndent(v36, 2);
        v6 = 8;
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v48 = 15;
          goto LABEL_67;
        }
        goto LABEL_72;
      }
      v15 = v33 + 4;
      for ( i = 0; i < *(_DWORD *)(v18 + 72); ++i )
      {
        v39 = -1;
        v40 = (char *)v10 + v15;
        do
          ++v39;
        while ( *(_WORD *)&v40[2 * v39] );
        *(_QWORD *)(*(_QWORD *)(v18 + 64) + 8LL * i) = (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 48))(
                                                         2 * v39 + 2,
                                                         -1);
        v41 = *(void **)(*(_QWORD *)(v18 + 64) + 8LL * i);
        if ( !v41 )
        {
          WppTraceIndent(0, 2);
          v6 = 8;
          v47 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v48 = 16;
            goto LABEL_67;
          }
          goto LABEL_72;
        }
        v42 = -1;
        do
          ++v42;
        while ( *(_WORD *)&v40[2 * v42] );
        memcpy_0(v41, (char *)v10 + v15, 2 * v42 + 2);
        v43 = -1;
        do
          ++v43;
        while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v18 + 64) + 8LL * i) + 2 * v43) );
        v15 += 2 * v43 + 2;
      }
      v44 = *(_QWORD *)(v18 + 40);
      v52 = v18 + 24;
      v45 = -1;
      v50 = v18;
      LODWORD(v49) = 80;
      v51 = 16;
      do
        ++v45;
      while ( *(_WORD *)(v44 + 2 * v45) );
      v54 = v44;
      v46 = *(_QWORD *)(a1 + 40);
      v53 = 2 * v45;
      v6 = CacheAddItem(v46, &v51, v37, &v49);
      if ( v6 )
        goto LABEL_72;
      ++*(_DWORD *)(a1 + 84);
      *(_DWORD *)(a1 + 80) += *(_DWORD *)(v18 + 8);
      if ( !*(_QWORD *)(a1 + 64) )
        *(_QWORD *)(a1 + 64) = v18;
      I_ServerCacheSetMRU(a1, v18);
      LODWORD(v8) = v55;
    }
    WppTraceIndent(v17, 2);
    v6 = 8;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
    }
LABEL_77:
    if ( v13 )
      goto LABEL_78;
  }
LABEL_10:
  WppTraceIndent((__int64)v7, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)&WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180030680  mov     [rsp-38h+arg_0], rbx
0x180030685  push    rbp
0x180030686  push    rsi
0x180030687  push    rdi
0x180030688  push    r12
0x18003068a  push    r13
0x18003068c  push    r14
0x18003068e  push    r15
0x180030690  mov     rbp, rsp
0x180030693  sub     rsp, 60h
0x180030697  xor     eax, eax
0x180030699  mov     r14d, r8d
0x18003069c  xor     r13d, r13d
0x18003069f  mov     qword ptr [rbp+var_2C], rax
0x1800306a3  mov     rdi, rdx
0x1800306a6  mov     [rbp-30h], rax
0x1800306aa  xor     edx, edx
0x1800306ac  mov     [rbp+arg_10], r13d
0x1800306b0  mov     rsi, rcx
0x1800306b3  mov     ebx, r13d
0x1800306b6  call    WppTraceIndent
0x1800306bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306c2  lea     rax, WPP_GLOBAL_Control
0x1800306c9  cmp     rcx, rax
0x1800306cc  jz      short loc_1800306F5
0x1800306ce  test    byte ptr [rcx+1Ch], 2
0x1800306d2  jz      short loc_1800306F5
0x1800306d4  cmp     byte ptr [rcx+19h], 5
0x1800306d8  jb      short loc_1800306F5
0x1800306da  mov     r9, cs:WPP_pszIndent
0x1800306e1  lea     edx, [r13+0Ah]
0x1800306e5  mov     rcx, [rcx+10h]
0x1800306e9  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800306f0  call    WPP_SF_s
0x1800306f5  test    r14d, r14d
0x1800306f8  jz      short loc_18003071D
0x1800306fa  test    rdi, rdi
0x1800306fd  jz      short loc_18003071D
0x1800306ff  cmp     dword ptr [rdi], 4541482Fh
0x180030705  jnz     short loc_18003071D
0x180030707  mov     r10d, [rdi+8]
0x18003070b  mov     [rbp+arg_8], r10
0x18003070f  lea     rcx, [r10+10h]
0x180030713  cmp     rcx, r14
0x180030716  jz      short loc_180030780
0x180030718  mov     ebx, 8010001Fh
0x18003071d  lea     r14, WPP_GLOBAL_Control
0x180030724  mov     edx, 1
0x180030729  call    WppTraceIndent
0x18003072e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030735  cmp     rcx, r14
0x180030738  jz      short loc_180030766
0x18003073a  test    byte ptr [rcx+1Ch], 2
0x18003073e  jz      short loc_180030766
0x180030740  cmp     byte ptr [rcx+19h], 5
0x180030744  jb      short loc_180030766
0x180030746  mov     r9, cs:WPP_pszIndent
0x18003074d  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180030754  mov     rcx, [rcx+10h]
0x180030758  mov     edx, 11h
0x18003075d  mov     [rsp+60h+var_40], ebx
0x180030761  call    WPP_SF_sD
0x180030766  mov     eax, ebx
0x180030768  mov     rbx, [rsp+60h+arg_0]
0x180030770  add     rsp, 60h
0x180030774  pop     r15
0x180030776  pop     r14
0x180030778  pop     r13
0x18003077a  pop     r12
0x18003077c  pop     rdi
0x18003077d  pop     rsi
0x18003077e  pop     rbp
0x18003077f  retn
0x180030780  mov     eax, [rdi+4]
0x180030783  lea     r15, [rdi+10h]
0x180030787  test    al, 1
0x180030789  jz      loc_180030857
0x18003078f  xor     r9d, r9d
0x180030792  lea     r8, [rbp+arg_10]
0x180030796  mov     rdx, r15
0x180030799  mov     ecx, r10d
0x18003079c  call    UncompressData
0x1800307a1  mov     ebx, eax
0x1800307a3  test    eax, eax
0x1800307a5  jnz     loc_18003071D
0x1800307ab  mov     ecx, [rbp+arg_10]
0x1800307ae  mov     rax, [rsi+30h]
0x1800307b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307b7  mov     r12, rax
0x1800307ba  test    rax, rax
0x1800307bd  jnz     short loc_180030816
0x1800307bf  lea     edx, [rbx+2]
0x1800307c2  call    WppTraceIndent
0x1800307c7  lea     ebx, [r12+8]
0x1800307cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307d3  lea     r14, WPP_GLOBAL_Control
0x1800307da  cmp     rcx, r14
0x1800307dd  jz      loc_180030724
0x1800307e3  test    byte ptr [rcx+1Ch], 1
0x1800307e7  jz      loc_180030724
0x1800307ed  cmp     byte ptr [rcx+19h], 2
0x1800307f1  jb      loc_180030724
0x1800307f7  mov     r9, cs:WPP_pszIndent
0x1800307fe  lea     edx, [rbx+3]
0x180030801  mov     rcx, [rcx+10h]
0x180030805  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x18003080c  call    WPP_SF_s
0x180030811  jmp     loc_180030724
0x180030816  mov     ecx, [rdi+8]
0x180030819  lea     r8, [rbp+arg_10]
0x18003081d  mov     r9, r12
0x180030820  mov     rdx, r15
0x180030823  call    UncompressData
0x180030828  mov     ebx, eax
0x18003082a  test    eax, eax
0x18003082c  jz      short loc_18003084A
0x18003082e  lea     r14, WPP_GLOBAL_Control
0x180030835  cmp     eax, 54Fh
0x18003083a  jnz     loc_180030BF3
0x180030840  mov     ebx, 80090005h
0x180030845  jmp     loc_180030BF3
0x18003084a  mov     r10d, [rbp+arg_10]
0x18003084e  mov     r15, r12
0x180030851  mov     [rbp+arg_8], r10
0x180030855  jmp     short loc_18003085A
0x180030857  mov     r12, r13
0x18003085a  mov     r14d, r13d
0x18003085d  cmp     r14d, r10d
0x180030860  jnb     loc_180030BE3
0x180030866  mov     rax, [rsi+30h]
0x18003086a  mov     ecx, 50h ; 'P'
0x18003086f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030874  mov     rdi, rax
0x180030877  test    rax, rax
0x18003087a  jz      loc_180030B99
0x180030880  mov     eax, r14d
0x180030883  mov     ecx, [rax+r15]
0x180030887  mov     [rdi+8], ecx
0x18003088a  mov     rax, [rsi+30h]
0x18003088e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030893  mov     [rdi], rax
0x180030896  test    rax, rax
0x180030899  jz      loc_180030B52
0x18003089f  mov     r8d, [rdi+8]; Size
0x1800308a3  lea     ebx, [r14+4]
0x1800308a7  mov     edx, ebx
0x1800308a9  mov     rcx, rax; void *
0x1800308ac  add     rdx, r15; Src
0x1800308af  call    memcpy_0
0x1800308b4  mov     edx, [rdi+8]
0x1800308b7  add     edx, 7
0x1800308ba  and     edx, 0FFFFFFF8h
0x1800308bd  add     edx, ebx
0x1800308bf  mov     ecx, [rdx+r15]
0x1800308c3  add     edx, 4
0x1800308c6  mov     [rdi+0Ch], ecx
0x1800308c9  mov     rcx, [rdx+r15]
0x1800308cd  add     edx, 8
0x1800308d0  mov     [rdi+10h], rcx
0x1800308d4  movups  xmm0, xmmword ptr [rdx+r15]
0x1800308d9  lea     r14d, [rdx+10h]
0x1800308dd  mov     ebx, r14d
0x1800308e0  add     rbx, r15
0x1800308e3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800308e7  movdqu  xmmword ptr [rdi+18h], xmm0
0x1800308ec  inc     rcx
0x1800308ef  cmp     [rbx+rcx*2], r13w
0x1800308f4  jnz     short loc_1800308EC
0x1800308f6  mov     rax, [rsi+30h]
0x1800308fa  lea     rcx, ds:2[rcx*2]
0x180030902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030907  mov     [rdi+28h], rax
0x18003090b  test    rax, rax
0x18003090e  jz      loc_180030B08
0x180030914  or      r8, 0FFFFFFFFFFFFFFFFh
0x180030918  inc     r8
0x18003091b  cmp     [rbx+r8*2], r13w
0x180030920  jnz     short loc_180030918
0x180030922  lea     r8, ds:2[r8*2]; Size
0x18003092a  mov     rdx, rbx; Src
0x18003092d  mov     rcx, rax; void *
0x180030930  call    memcpy_0
0x180030935  mov     rcx, [rdi+28h]
0x180030939  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003093d  inc     rax
0x180030940  cmp     [rcx+rax*2], r13w
0x180030945  jnz     short loc_18003093D
0x180030947  lea     r14d, [r14+rax*2]
0x18003094b  add     r14d, 2
0x18003094f  mov     ecx, [r14+r15]
0x180030953  mov     [rdi+48h], ecx
0x180030956  mov     rax, [rsi+30h]
0x18003095a  shl     rcx, 3
0x18003095e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030963  mov     [rdi+40h], rax
0x180030967  test    rax, rax
0x18003096a  jz      loc_180030AC9
0x180030970  add     r14d, 4
0x180030974  mov     ebx, r13d
0x180030977  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003097b  cmp     ebx, [rdi+48h]
0x18003097e  jnb     loc_180030A14
0x180030984  mov     r13d, r14d
0x180030987  mov     rcx, rdx
0x18003098a  add     r13, r15
0x18003098d  xor     eax, eax
0x18003098f  inc     rcx
0x180030992  cmp     [r13+rcx*2+0], ax
0x180030998  jnz     short loc_18003098F
0x18003099a  mov     rax, [rsi+30h]
0x18003099e  lea     rcx, ds:2[rcx*2]
0x1800309a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309ab  mov     rcx, [rdi+40h]
0x1800309af  mov     edx, ebx
0x1800309b1  mov     [rcx+rdx*8], rax
0x1800309b5  mov     rax, [rdi+40h]
0x1800309b9  mov     rcx, [rax+rdx*8]; void *
0x1800309bd  xor     eax, eax
0x1800309bf  test    rcx, rcx
0x1800309c2  jz      loc_180030A8A
0x1800309c8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800309cc  inc     r8
0x1800309cf  cmp     [r13+r8*2+0], ax
0x1800309d5  jnz     short loc_1800309CC
0x1800309d7  lea     r8, ds:2[r8*2]; Size
0x1800309df  mov     rdx, r13; Src
0x1800309e2  call    memcpy_0
0x1800309e7  mov     rax, [rdi+40h]
0x1800309eb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800309ef  mov     ecx, ebx
0x1800309f1  xor     r13d, r13d
0x1800309f4  mov     rcx, [rax+rcx*8]
0x1800309f8  mov     rax, rdx
0x1800309fb  inc     rax
0x1800309fe  cmp     [rcx+rax*2], r13w
0x180030a03  jnz     short loc_1800309FB
0x180030a05  lea     r14d, [r14+rax*2]
0x180030a09  add     r14d, 2
0x180030a0d  inc     ebx
0x180030a0f  jmp     loc_18003097B
0x180030a14  mov     rcx, [rdi+28h]
0x180030a18  lea     rax, [rdi+18h]
0x180030a1c  mov     [rbp+var_18], rax
0x180030a20  mov     rax, rdx
0x180030a23  mov     qword ptr [rbp+var_2C+4], rdi
0x180030a27  mov     [rbp+var_30], 50h ; 'P'
0x180030a2e  mov     [rbp+var_20], 10h
0x180030a35  inc     rax
0x180030a38  cmp     [rcx+rax*2], r13w
0x180030a3d  jnz     short loc_180030A35
0x180030a3f  add     eax, eax
0x180030a41  mov     [rbp+var_8], rcx
0x180030a45  mov     rcx, [rsi+28h]
0x180030a49  lea     r9, [rbp+var_30]
0x180030a4d  lea     rdx, [rbp+var_20]
0x180030a51  mov     [rbp+var_10], eax
0x180030a54  call    CacheAddItem
0x180030a59  mov     ebx, eax
0x180030a5b  test    eax, eax
0x180030a5d  jnz     loc_180030B85
0x180030a63  inc     dword ptr [rsi+54h]
0x180030a66  mov     eax, [rdi+8]
0x180030a69  add     [rsi+50h], eax
0x180030a6c  cmp     [rsi+40h], r13
0x180030a70  jnz     short loc_180030A76
0x180030a72  mov     [rsi+40h], rdi
0x180030a76  mov     rdx, rdi
0x180030a79  mov     rcx, rsi
0x180030a7c  call    I_ServerCacheSetMRU
0x180030a81  mov     r10, [rbp+arg_8]
0x180030a85  jmp     loc_18003085D
0x180030a8a  mov     edx, 2
0x180030a8f  call    WppTraceIndent
0x180030a94  mov     ebx, 8
0x180030a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180030aa0  lea     r14, WPP_GLOBAL_Control
0x180030aa7  cmp     rcx, r14
0x180030aaa  jz      loc_180030B8C
0x180030ab0  test    byte ptr [rcx+1Ch], 1
0x180030ab4  jz      loc_180030B8C
0x180030aba  cmp     byte ptr [rcx+19h], 2
0x180030abe  jb      loc_180030B8C
0x180030ac4  lea     edx, [rbx+8]
0x180030ac7  jmp     short loc_180030B39
0x180030ac9  mov     edx, 2
0x180030ace  call    WppTraceIndent
0x180030ad3  mov     ebx, 8
0x180030ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180030adf  lea     r14, WPP_GLOBAL_Control
0x180030ae6  cmp     rcx, r14
0x180030ae9  jz      loc_180030B8C
0x180030aef  test    byte ptr [rcx+1Ch], 1
0x180030af3  jz      loc_180030B8C
0x180030af9  cmp     byte ptr [rcx+19h], 2
0x180030afd  jb      loc_180030B8C
0x180030b03  lea     edx, [rbx+7]
0x180030b06  jmp     short loc_180030B39
0x180030b08  mov     edx, 2
0x180030b0d  call    WppTraceIndent
0x180030b12  mov     ebx, 8
  ... truncated ...
```
