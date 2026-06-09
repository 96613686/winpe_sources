# BCryptEnumAlgorithms

- ea: `0x180001590`
- end: `0x1800019c8`
- name: `BCryptEnumAlgorithms`
- size: `1080`
- prototype: `NTSTATUS __stdcall(ULONG dwAlgOperations, ULONG *pAlgCount, BCRYPT_ALGORITHM_IDENTIFIER **ppAlgList, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001590`
- `0x1800030a0`
- `0x180004200`
- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x180015360`
- `0x18001b79d`
- `0x18001b7e0`

## string_xrefs

- `0x1800017db`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180001836`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180001889`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptEnumAlgorithms(
        ULONG dwAlgOperations,
        ULONG *pAlgCount,
        BCRYPT_ALGORITHM_IDENTIFIER **ppAlgList,
        ULONG dwFlags)
{
  ULONG *v5; // rax
  int v7; // edx
  _QWORD *v8; // rcx
  unsigned int v9; // esi
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  BCRYPT_ALGORITHM_IDENTIFIER *v12; // r14
  int v13; // r9d
  ULONG v14; // edi
  __int64 i; // rdx
  __int64 v16; // rcx
  __int64 k; // rdi
  __int64 v18; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // edi
  __int64 v23; // rbx
  __int64 v24; // rax
  int v25; // edx
  int v26; // r8d
  WCHAR *v27; // r15
  __int64 j; // rsi
  __int64 v29; // rax
  __int64 v30; // r12
  unsigned int v31; // r8d
  __int64 v32; // rax
  ULONG v33; // ecx
  unsigned int v34; // esi
  __int64 v35; // rax
  __int64 v36; // rax
  _WORD *v37; // rdx
  size_t v38; // rbx
  ULONG v39; // [rsp+40h] [rbp-C0h]
  __int64 v40; // [rsp+48h] [rbp-B8h]
  BCRYPT_ALGORITHM_IDENTIFIER **v42; // [rsp+58h] [rbp-A8h]
  ULONG dwInterface; // [rsp+60h] [rbp-A0h]
  __int64 v44; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h] BYREF
  int v46; // [rsp+78h] [rbp-88h]
  __int64 v47; // [rsp+7Ch] [rbp-84h]
  __int64 v48; // [rsp+88h] [rbp-78h]
  int v49; // [rsp+90h] [rbp-70h]
  __int64 v50; // [rsp+94h] [rbp-6Ch]
  __int64 v51; // [rsp+A0h] [rbp-60h]
  int v52; // [rsp+A8h] [rbp-58h]
  __int64 v53; // [rsp+ACh] [rbp-54h]
  __int64 v54; // [rsp+B8h] [rbp-48h]
  int v55; // [rsp+C0h] [rbp-40h]
  __int64 v56; // [rsp+C4h] [rbp-3Ch]
  __int64 v57; // [rsp+D0h] [rbp-30h]
  int v58; // [rsp+D8h] [rbp-28h]
  __int64 v59; // [rsp+DCh] [rbp-24h]
  __int64 v60; // [rsp+E8h] [rbp-18h]
  int v61; // [rsp+F0h] [rbp-10h]
  __int64 v62; // [rsp+F4h] [rbp-Ch]
  __int64 v63; // [rsp+100h] [rbp+0h]
  int v64; // [rsp+108h] [rbp+8h]
  __int64 v65; // [rsp+10Ch] [rbp+Ch]
  __int64 v66; // [rsp+118h] [rbp+18h]

  v42 = ppAlgList;
  v5 = pAlgCount;
  dwInterface = 1;
  v44 = 1;
  v45 = 0;
  v7 = 4;
  v46 = 2;
  v50 = 4;
  v52 = 4;
  v47 = 2;
  v48 = 0;
  v49 = 3;
  v51 = 0;
  v53 = 8;
  v54 = 0;
  v55 = 5;
  v56 = 16;
  v57 = 0;
  v58 = 6;
  v59 = 32;
  v60 = 0;
  v61 = 7;
  v62 = 64;
  v63 = 0;
  v64 = 8;
  v65 = 128;
  v66 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_DqqD(*((_QWORD *)WPP_GLOBAL_Control + 2), 4, ppAlgList, dwAlgOperations, v5, ppAlgList, dwFlags);
    v8 = WPP_GLOBAL_Control;
    v5 = pAlgCount;
    ppAlgList = v42;
  }
  if ( dwAlgOperations < 0x100 && v5 && ppAlgList && !dwFlags )
  {
    *v5 = 0;
    v9 = 0;
    *ppAlgList = 0;
    while ( v9 < 8 )
    {
      if ( (dwAlgOperations & *(_DWORD *)(&v44 + 3 * v9)) != 0 || !dwAlgOperations )
      {
        while ( 1 )
        {
          v10 = BCryptResolveProviders(
                  0,
                  *(&dwInterface + 6 * v9),
                  0,
                  0,
                  1u,
                  1u,
                  (ULONG *)&v44 + 6 * v9 + 1,
                  (PCRYPT_PROVIDER_REFS *)&v45 + 3 * v9);
          v11 = v10;
          if ( v10 != -1073741789 )
            break;
          v20 = *(&v45 + 3 * v9);
          if ( v20 )
            MSCryptFree(v20);
          v21 = SafeAllocaAllocateFromHeap(*((unsigned int *)&v44 + 6 * v9 + 1));
          *(&v45 + 3 * v9) = v21;
          if ( !v21 )
          {
            v11 = -1073741801;
LABEL_29:
            DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
            goto LABEL_20;
          }
        }
        if ( v10 != -1073741275 && v10 < 0 )
          goto LABEL_29;
      }
      ++v9;
    }
    v12 = 0;
    v13 = 0;
    v14 = 0;
    for ( i = 0; i != 8; ++i )
    {
      v16 = *(&v45 + 3 * i);
      if ( v16 && *(_DWORD *)v16 )
      {
        v31 = 0;
        do
        {
          v32 = -1;
          do
            ++v32;
          while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 8) + 8LL * v31) + 8LL) + 2 * v32) );
          ++v14;
          v13 += 2 * v32 + 2;
          ++v31;
        }
        while ( v31 < *(_DWORD *)v16 );
      }
    }
    if ( !v14 )
      goto LABEL_19;
    v22 = 16 * v14;
    v23 = v22;
    v24 = SafeAllocaAllocateFromHeap(v22 + v13);
    v12 = (BCRYPT_ALGORITHM_IDENTIFIER *)v24;
    if ( v24 )
    {
      v14 = 0;
      v40 = 0;
      v27 = (WCHAR *)(v24 + v23);
      for ( j = 0; j != 8; v40 = j )
      {
        v29 = 3 * j;
        v30 = *(&v45 + 3 * j);
        if ( v30 && *(_DWORD *)v30 )
        {
          v33 = *(&dwInterface + 6 * j);
          v34 = 0;
          v39 = *(&dwInterface + 2 * v29);
          do
          {
            v35 = v14;
            v12[v35].dwClass = v33;
            v12[v35].pszName = v27;
            v12[v35].dwFlags = 0;
            v36 = -1;
            v37 = *(_WORD **)(*(_QWORD *)(*(_QWORD *)(v30 + 8) + 8LL * v34) + 8LL);
            do
              ++v36;
            while ( v37[v36] );
            v38 = 2LL * (unsigned int)(v36 + 1);
            memcpy_0(v27, v37, v38);
            v33 = v39;
            v27 = (WCHAR *)((char *)v27 + v38);
            ++v14;
            ++v34;
          }
          while ( v34 < *(_DWORD *)v30 );
          j = v40;
        }
        ++j;
      }
LABEL_19:
      v11 = 0;
      *pAlgCount = v14;
      *v42 = v12;
      goto LABEL_20;
    }
    v11 = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v25,
        v26,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        86);
  }
  else
  {
    v11 = -1073741811;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v8[2],
        v7,
        (_DWORD)ppAlgList,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        243);
  }
LABEL_20:
  for ( k = 0; k != 8; ++k )
  {
    v18 = *(&v45 + 3 * k);
    if ( v18 )
      MSCryptFree(v18);
  }
  return v11;
}

```

## disassembly

```asm
0x180001590  mov     [rsp-8+arg_18], rbx
0x180001595  push    rbp
0x180001596  push    rsi
0x180001597  push    rdi
0x180001598  push    r12
0x18000159a  push    r13
0x18000159c  push    r14
0x18000159e  push    r15
0x1800015a0  lea     rbp, [rsp-30h]
0x1800015a5  sub     rsp, 130h
0x1800015ac  mov     rax, cs:__security_cookie
0x1800015b3  xor     rax, rsp
0x1800015b6  mov     [rbp+60h+var_40], rax
0x1800015ba  xor     r13d, r13d
0x1800015bd  mov     [rsp+160h+var_110], rdx
0x1800015c2  mov     r14d, ecx
0x1800015c5  mov     [rsp+160h+var_108], r8
0x1800015ca  mov     rax, rdx
0x1800015cd  mov     [rsp+160h+dwInterface], 1
0x1800015d5  mov     ebx, r9d
0x1800015d8  mov     [rsp+160h+var_FC], 1
0x1800015e1  lea     ecx, [r13+2]
0x1800015e5  mov     [rsp+160h+var_F0], r13
0x1800015ea  lea     edx, [rcx+2]
0x1800015ed  mov     [rsp+160h+var_E8], ecx
0x1800015f1  mov     [rbp+60h+var_CC], rdx
0x1800015f5  mov     [rbp+60h+var_B8], edx
0x1800015f8  mov     [rsp+160h+var_E4], rcx
0x1800015fd  mov     [rbp+60h+var_D8], r13
0x180001601  mov     [rbp+60h+var_D0], 3
0x180001608  mov     [rbp+60h+var_C0], r13
0x18000160c  mov     [rbp+60h+var_B4], 8
0x180001614  mov     [rbp+60h+var_A8], r13
0x180001618  mov     [rbp+60h+var_A0], 5
0x18000161f  mov     [rbp+60h+var_9C], 10h
0x180001627  mov     [rbp+60h+var_90], r13
0x18000162b  mov     [rbp+60h+var_88], 6
0x180001632  mov     [rbp+60h+var_84], 20h ; ' '
0x18000163a  mov     [rbp+60h+var_78], r13
0x18000163e  mov     [rbp+60h+var_70], 7
0x180001645  mov     [rbp+60h+var_6C], 40h ; '@'
0x18000164d  mov     [rbp+60h+var_60], r13
0x180001651  mov     [rbp+60h+var_58], 8
0x180001658  mov     [rbp+60h+var_54], 80h
0x180001660  mov     [rbp+60h+var_48], r13
0x180001664  mov     rcx, cs:WPP_GLOBAL_Control
0x18000166b  lea     r15, WPP_GLOBAL_Control
0x180001672  cmp     rcx, r15
0x180001675  jnz     loc_180001985
0x18000167b  cmp     r14d, 100h
0x180001682  jnb     loc_180001869
0x180001688  test    rax, rax
0x18000168b  jz      loc_180001869
0x180001691  test    r8, r8
0x180001694  jz      loc_180001869
0x18000169a  test    ebx, ebx
0x18000169c  jnz     loc_180001869
0x1800016a2  mov     [rax], r13d
0x1800016a5  mov     esi, r13d
0x1800016a8  mov     [r8], r13
0x1800016ab  cmp     esi, 8
0x1800016ae  jnb     short loc_180001722
0x1800016b0  mov     eax, esi
0x1800016b2  lea     rdi, [rax+rax*2]
0x1800016b6  shl     rdi, 3
0x1800016ba  test    dword ptr [rsp+rdi+160h+var_FC], r14d
0x1800016bf  jnz     short loc_1800016CA
0x1800016c1  test    r14d, r14d
0x1800016c4  jz      short loc_1800016CA
0x1800016c6  inc     esi
0x1800016c8  jmp     short loc_1800016AB
0x1800016ca  mov     edx, [rsp+rdi+160h+dwInterface]; dwInterface
0x1800016ce  lea     rax, [rsp+160h+var_F0]
0x1800016d3  add     rax, rdi
0x1800016d6  lea     rcx, [rsp+160h+var_FC+4]
0x1800016db  mov     [rsp+160h+ppBuffer], rax; ppBuffer
0x1800016e0  add     rcx, rdi
0x1800016e3  mov     [rsp+160h+pcbBuffer], rcx; pcbBuffer
0x1800016e8  xor     r9d, r9d; pszProvider
0x1800016eb  mov     [rsp+160h+dwFlags], 1; dwFlags
0x1800016f3  xor     ecx, ecx; pszContext
0x1800016f5  xor     r8d, r8d; pszFunction
0x1800016f8  mov     [rsp+160h+dwMode], 1; dwMode
0x180001700  call    BCryptResolveProviders
0x180001705  mov     ebx, eax
0x180001707  cmp     eax, 0C0000023h
0x18000170c  jz      loc_1800017AB
0x180001712  cmp     eax, 0C0000225h
0x180001717  jz      short loc_1800016C6
0x180001719  test    eax, eax
0x18000171b  jns     short loc_1800016C6
0x18000171d  jmp     loc_1800017D5
0x180001722  mov     r14, r13
0x180001725  mov     r9d, r13d
0x180001728  mov     edi, r13d
0x18000172b  mov     rdx, r13
0x18000172e  lea     rax, [rdx+rdx*2]
0x180001732  mov     rcx, [rsp+rax*8+160h+var_F0]
0x180001737  test    rcx, rcx
0x18000173a  jnz     loc_1800018CF
0x180001740  inc     rdx
0x180001743  cmp     rdx, 8
0x180001747  jnz     short loc_18000172E
0x180001749  test    edi, edi
0x18000174b  jnz     loc_1800017F5
0x180001751  mov     rax, [rsp+160h+var_110]
0x180001756  mov     ebx, r13d
0x180001759  mov     [rax], edi
0x18000175b  mov     rax, [rsp+160h+var_108]
0x180001760  mov     [rax], r14
0x180001763  mov     rdi, r13
0x180001766  lea     rcx, [rdi+rdi*2]
0x18000176a  mov     rcx, [rsp+rcx*8+160h+var_F0]
0x18000176f  test    rcx, rcx
0x180001772  jnz     loc_18000185F
0x180001778  inc     rdi
0x18000177b  cmp     rdi, 8
0x18000177f  jnz     short loc_180001766
0x180001781  mov     eax, ebx
0x180001783  mov     rcx, [rbp+60h+var_40]
0x180001787  xor     rcx, rsp; StackCookie
0x18000178a  call    __security_check_cookie
0x18000178f  mov     rbx, [rsp+160h+arg_18]
0x180001797  add     rsp, 130h
0x18000179e  pop     r15
0x1800017a0  pop     r14
0x1800017a2  pop     r13
0x1800017a4  pop     r12
0x1800017a6  pop     rdi
0x1800017a7  pop     rsi
0x1800017a8  pop     rbp
0x1800017a9  retn
0x1800017ab  mov     rcx, [rsp+rdi+160h+var_F0]
0x1800017b0  test    rcx, rcx
0x1800017b3  jnz     loc_1800019BE
0x1800017b9  mov     ecx, dword ptr [rsp+rdi+160h+var_FC+4]
0x1800017bd  call    SafeAllocaAllocateFromHeap
0x1800017c2  mov     [rsp+rdi+160h+var_F0], rax
0x1800017c7  test    rax, rax
0x1800017ca  jnz     loc_1800016CA
0x1800017d0  mov     ebx, 0C0000017h
0x1800017d5  mov     r9d, 0A2Bh
0x1800017db  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800017e2  lea     rdx, aStatus; "Status"
0x1800017e9  mov     ecx, ebx
0x1800017eb  call    DebugTraceError
0x1800017f0  jmp     loc_180001763
0x1800017f5  shl     edi, 4
0x1800017f8  mov     ebx, edi
0x1800017fa  lea     ecx, [rdi+r9]
0x1800017fe  call    SafeAllocaAllocateFromHeap
0x180001803  mov     r14, rax
0x180001806  test    rax, rax
0x180001809  jnz     loc_18000189F
0x18000180f  mov     ebx, 0C0000017h
0x180001814  mov     rcx, cs:WPP_GLOBAL_Control
0x18000181b  cmp     rcx, r15
0x18000181e  jz      loc_180001763
0x180001824  test    byte ptr [rcx+1Ch], 1
0x180001828  jz      loc_180001763
0x18000182e  mov     dword ptr [rsp+160h+pcbBuffer], 0A56h
0x180001836  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000183d  mov     qword ptr [rsp+160h+dwFlags], rax
0x180001842  mov     [rsp+160h+dwMode], 0C0000017h
0x18000184a  mov     rcx, [rcx+10h]
0x18000184e  lea     r9, aStatus; "Status"
0x180001855  call    WPP_SF_sDsd
0x18000185a  jmp     loc_180001763
0x18000185f  call    MSCryptFree
0x180001864  jmp     loc_180001778
0x180001869  mov     ebx, 0C000000Dh
0x18000186e  cmp     rcx, r15
0x180001871  jz      loc_180001763
0x180001877  test    byte ptr [rcx+1Ch], 1
0x18000187b  jz      loc_180001763
0x180001881  mov     dword ptr [rsp+160h+pcbBuffer], 9F3h
0x180001889  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001890  mov     qword ptr [rsp+160h+dwFlags], rax
0x180001895  mov     [rsp+160h+dwMode], 0C000000Dh
0x18000189d  jmp     short loc_18000184A
0x18000189f  mov     edi, r13d
0x1800018a2  mov     [rsp+160h+var_118], r13
0x1800018a7  lea     r15, [rax+rbx]
0x1800018ab  mov     rsi, r13
0x1800018ae  lea     rax, [rsi+rsi*2]
0x1800018b2  mov     r12, [rsp+rax*8+160h+var_F0]
0x1800018b7  test    r12, r12
0x1800018ba  jnz     short loc_180001912
0x1800018bc  inc     rsi
0x1800018bf  mov     [rsp+160h+var_118], rsi
0x1800018c4  cmp     rsi, 8
0x1800018c8  jnz     short loc_1800018AE
0x1800018ca  jmp     loc_180001751
0x1800018cf  mov     r10d, [rcx]
0x1800018d2  test    r10d, r10d
0x1800018d5  jz      loc_180001740
0x1800018db  mov     rbx, [rcx+8]
0x1800018df  mov     r8d, r13d
0x1800018e2  mov     eax, r8d
0x1800018e5  mov     rcx, [rbx+rax*8]
0x1800018e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800018ed  mov     r11, [rcx+8]
0x1800018f1  inc     rax
0x1800018f4  cmp     [r11+rax*2], r13w
0x1800018f9  jnz     short loc_1800018F1
0x1800018fb  lea     r9d, [r9+rax*2]
0x1800018ff  inc     edi
0x180001901  add     r9d, 2
0x180001905  inc     r8d
0x180001908  cmp     r8d, r10d
0x18000190b  jb      short loc_1800018E2
0x18000190d  jmp     loc_180001740
0x180001912  cmp     [r12], r13d
0x180001916  jbe     short loc_1800018BC
0x180001918  mov     ecx, [rsp+rax*8+160h+dwInterface]
0x18000191c  mov     esi, r13d
0x18000191f  mov     [rsp+160h+var_120], ecx
0x180001923  xor     r8d, r8d
0x180001926  mov     eax, edi
0x180001928  add     rax, rax
0x18000192b  mov     [r14+rax*8+8], ecx
0x180001930  mov     [r14+rax*8], r15
0x180001934  mov     [r14+rax*8+0Ch], r8d
0x180001939  mov     rax, [r12+8]
0x18000193e  mov     ecx, esi
0x180001940  mov     rcx, [rax+rcx*8]
0x180001944  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001948  mov     rdx, [rcx+8]; Src
0x18000194c  inc     rax
0x18000194f  cmp     [rdx+rax*2], r8w
0x180001954  jnz     short loc_18000194C
0x180001956  lea     ebx, [rax+1]
0x180001959  mov     rcx, r15; void *
0x18000195c  add     rbx, rbx
0x18000195f  mov     r8, rbx; Size
0x180001962  call    memcpy_0
0x180001967  mov     ecx, [rsp+160h+var_120]
0x18000196b  add     r15, rbx
0x18000196e  inc     edi
0x180001970  inc     esi
0x180001972  cmp     esi, [r12]
0x180001976  jb      short loc_180001923
0x180001978  mov     rsi, [rsp+160h+var_118]
0x18000197d  xor     r13d, r13d
0x180001980  jmp     loc_1800018BC
0x180001985  test    [rcx+1Ch], dl
0x180001988  jz      loc_18000167B
0x18000198e  mov     rcx, [rcx+10h]
0x180001992  mov     r9d, r14d
0x180001995  mov     dword ptr [rsp+160h+pcbBuffer], ebx
0x180001999  mov     qword ptr [rsp+160h+dwFlags], r8
0x18000199e  mov     qword ptr [rsp+160h+dwMode], rax
0x1800019a3  call    WPP_SF_DqqD
0x1800019a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019af  mov     rax, [rsp+160h+var_110]
0x1800019b4  mov     r8, [rsp+160h+var_108]
0x1800019b9  jmp     loc_18000167B
0x1800019be  call    MSCryptFree
0x1800019c3  jmp     loc_1800017B9
```
