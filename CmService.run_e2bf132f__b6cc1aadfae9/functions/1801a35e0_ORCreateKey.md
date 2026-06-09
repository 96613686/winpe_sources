# ORCreateKey

- ea: `0x1801a35e0`
- end: `0x1801a3c34`
- name: `ORCreateKey`
- size: `1620`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801994e8`

## callees

- `0x1800055d0`
- `0x1800055dc`
- `0x180005704`
- `0x1800069db`
- `0x1800375ac`
- `0x1800379e0`
- `0x180037a34`
- `0x180037adc`
- `0x1801a34b8`
- `0x1801a35e0`
- `0x1801a4138`
- `0x1801a719c`
- `0x1801a7db0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x1801a39ca`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x1801a39ca`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1801a3921`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1801a3921`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1801a3bf2`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1801a3bf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a3c0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a3c0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a3694`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a3694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a39da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a39da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801a3862`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801a3862`

## pseudocode

```c
__int64 __fastcall ORCreateKey(
        __int64 a1,
        _WORD *a2,
        _WORD *a3,
        int a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        __int64 *a6,
        _DWORD *a7)
{
  __int64 *v7; // r12
  __int64 v10; // r15
  __int64 v11; // r13
  int v12; // r14d
  DWORD LastError; // ebx
  __int64 v14; // rsi
  unsigned __int16 v15; // cx
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // r13
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  _WORD *v21; // rax
  __int16 v22; // cx
  _WORD *v23; // rsi
  unsigned __int64 v24; // rbx
  __int16 v25; // r14
  __int64 v26; // rcx
  unsigned __int16 v27; // ax
  __int64 v28; // r10
  __int64 v29; // rsi
  __int16 v30; // r14
  __int64 v31; // rdi
  void *v32; // r15
  __int64 v33; // r10
  ULONG AutoInheritFlags; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned __int64 v37; // rax
  unsigned int v38; // ebx
  void *v39; // rax
  _OWORD *v40; // rax
  __int128 v41; // xmm1
  __int64 v42; // r8
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int64 v46; // rdx
  void *v47; // rcx
  __int64 v49; // [rsp+50h] [rbp-A1h]
  int v50; // [rsp+58h] [rbp-99h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-91h] BYREF
  BOOL IsContainerObject[2]; // [rsp+68h] [rbp-89h]
  __int64 v53; // [rsp+70h] [rbp-81h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+78h] [rbp-79h] BYREF
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+80h] [rbp-71h]
  __int64 v56; // [rsp+88h] [rbp-69h] BYREF
  __int128 v57; // [rsp+90h] [rbp-61h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-51h] BYREF
  __int128 v59; // [rsp+B0h] [rbp-41h] BYREF
  __int128 v60; // [rsp+C0h] [rbp-31h]
  __int128 v61; // [rsp+D0h] [rbp-21h]
  _BYTE v62[28]; // [rsp+E0h] [rbp-11h]
  unsigned __int16 v63; // [rsp+140h] [rbp+4Fh]

  v7 = a6;
  v53 = 0;
  v56 = 0;
  v50 = 0;
  *a6 = 0;
  v49 = 0;
  LODWORD(v10) = 0;
  SystemTimeAsFileTime = 0;
  v58 = 0;
  CreatorDescriptor = 0;
  v57 = 0;
  NewDescriptor = 0;
  if ( *(_WORD *)(a1 + 28) != 29806 || (v11 = *(_QWORD *)(a1 + 16), v49 = v11, *(_DWORD *)v11 != -1092567328) )
  {
    LastError = 6;
    goto LABEL_97;
  }
  if ( !a2 )
    goto LABEL_6;
  if ( !*a2 )
    goto LABEL_6;
  v12 = a4 & 2;
  if ( a4 != v12 )
    goto LABEL_6;
  EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 136));
  LODWORD(v10) = 1;
  *(_QWORD *)IsContainerObject = 1;
  LastError = ORInitUnicodeStringEx(&v57, a2);
  if ( LastError )
    goto LABEL_97;
  v15 = v57;
  if ( (_WORD)v57 )
  {
    do
    {
      if ( *(_WORD *)(*((_QWORD *)&v57 + 1) + 2 * ((unsigned __int64)v15 >> 1) - 2) != 92 )
        break;
      v15 -= 2;
    }
    while ( v15 );
    LOWORD(v57) = v15;
  }
  if ( *(_WORD *)(a1 + 30) )
  {
    LastError = 1018;
    goto LABEL_7;
  }
  if ( !v15 )
    goto LABEL_6;
  LastError = ORParseSubKey(&v57, a1, &v50, &v53);
  if ( LastError )
  {
LABEL_97:
    v14 = v49;
    goto LABEL_98;
  }
  if ( v50 == 2 )
  {
    v16 = v53;
    if ( !v12 )
      goto LABEL_21;
    if ( (*(_BYTE *)(*(_QWORD *)(v53 + 40) + 2LL) & 0x10) != 0 )
    {
      v7 = a6;
LABEL_21:
      if ( v53 != *(_QWORD *)(v11 + 56) )
      {
        v17 = *(_DWORD *)(v53 + 24);
        if ( v17 == -1 )
        {
          LastError = 1450;
        }
        else
        {
          *(_DWORD *)(v53 + 24) = v17 + 1;
          if ( a7 )
            *a7 = 2;
          *v7 = v16;
          LastError = 0;
        }
        goto LABEL_7;
      }
    }
LABEL_6:
    LastError = 87;
LABEL_7:
    v14 = v11;
    goto LABEL_98;
  }
  v18 = v53;
  v19 = *(_QWORD *)(v53 + 40);
  if ( (*(_BYTE *)(v19 + 2) & 0x10) != 0 || (*(_BYTE *)(v19 + 13) & 3) == 1 )
  {
    LastError = 5;
    goto LABEL_97;
  }
  if ( *(_WORD *)(v53 + 32) == 510 )
    goto LABEL_31;
  v20 = 0;
  v21 = a2;
  do
    v22 = *++v21;
  while ( *v21 );
  while ( v21 > a2 )
  {
    v22 = *--v21;
    if ( *v21 != 92 )
      goto LABEL_38;
  }
  if ( v22 == 92 )
    goto LABEL_40;
  do
  {
LABEL_38:
    if ( v21 == a2 )
      break;
    --v21;
    v20 += 2LL;
  }
  while ( *v21 != 92 );
LABEL_40:
  v23 = v21 + 1;
  v24 = v20 + 2;
  if ( *v21 != 92 )
    v23 = v21;
  if ( v23 != a2 )
    v24 = v20;
  if ( v24 > 0x200 )
  {
LABEL_31:
    LastError = 87;
    goto LABEL_97;
  }
  memset_0(&v59, 0, 0x50u);
  LOWORD(v59) = 27502;
  if ( v12 )
    v25 = 16;
  else
    v25 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(struct _FILETIME *)((char *)&v59 + 4) = SystemTimeAsFileTime;
  LODWORD(v60) = -1;
  HIDWORD(v60) = -1;
  *(_QWORD *)&v61 = 0xFFFFFFFFLL;
  *((_QWORD *)&v61 + 1) = -1;
  *(_DWORD *)v62 = -1;
  v63 = 0;
  *(_WORD *)&v62[26] = 0;
  v26 = *(_QWORD *)(v49 + 16);
  BYTE12(v59) = 0;
  *(_QWORD *)((char *)&v60 + 4) = 0;
  *(_OWORD *)&v62[4] = 0u;
  *((_QWORD *)&v58 + 1) = v23;
  LOWORD(v58) = v24;
  v53 = v26;
  WORD1(v58) = v24;
  v27 = ORGetCompressedLength(v26, &v58);
  v29 = v27;
  *(_WORD *)&v62[24] = v27;
  if ( v27 >= v24 )
    v30 = v25 & 0xFFDF;
  else
    v30 = v25 | 0x20;
  WORD1(v59) = v30;
  v31 = ORAllocNode(v28, v18);
  if ( !v31 )
  {
    LastError = 8;
    goto LABEL_97;
  }
  v32 = 0;
  if ( pSecurityDescriptor )
  {
    if ( !IsValidSecurityDescriptor(pSecurityDescriptor) )
    {
      LastError = 1338;
LABEL_91:
      v47 = *(void **)(v31 + 120);
      if ( v47 )
        aligned_free(v47);
      aligned_free((void *)v31);
      if ( v32 )
        aligned_free(v32);
      LODWORD(v10) = IsContainerObject[0];
      goto LABEL_97;
    }
    LastError = ORMakeSDRelative(pSecurityDescriptor);
    if ( LastError )
      goto LABEL_91;
  }
  v33 = *(_QWORD *)(*(_QWORD *)(v18 + 96) + 16LL);
  if ( CreatorDescriptor && (*((_BYTE *)CreatorDescriptor + 2) & 4) != 0 )
  {
    AutoInheritFlags = 4216;
  }
  else
  {
    AutoInheritFlags = (*(_WORD *)(v33 + 22) & 0x400 | 0x41E000u) >> 10;
    if ( !CreatorDescriptor )
      goto LABEL_62;
  }
  if ( (*((_BYTE *)CreatorDescriptor + 2) & 0x10) == 0 )
  {
LABEL_62:
    if ( (*(_WORD *)(v33 + 22) & 0x800) != 0 )
      AutoInheritFlags |= 2u;
  }
  if ( !CreatePrivateObjectSecurityWithMultipleInheritance(
          (PSECURITY_DESCRIPTOR)(v33 + 20),
          CreatorDescriptor,
          &NewDescriptor,
          0,
          0,
          IsContainerObject[0],
          AutoInheritFlags,
          0,
          &CmKeyMapping) )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_91;
  }
  LastError = ORProcessSecurityDescriptor(v49, NewDescriptor, &v56);
  if ( LastError )
    goto LABEL_91;
  v35 = v56;
  *(_QWORD *)(v31 + 96) = v56;
  *(_DWORD *)(*(_QWORD *)(v35 + 16) + 12LL) += IsContainerObject[0];
  if ( a3 )
  {
    v36 = -1;
    do
      ++v36;
    while ( a3[v36] );
    v37 = 2 * v36;
    if ( v37 > 0xFFFF )
    {
      LastError = 534;
      goto LABEL_91;
    }
    *(_WORD *)&v62[26] = v37;
    v63 = v37;
    if ( (_WORD)v37 )
    {
      v38 = (unsigned __int16)v37;
      v39 = o__aligned_malloc_0((unsigned __int16)v37, 0x10u);
      *(_QWORD *)(v31 + 120) = v39;
      if ( !v39 )
      {
LABEL_75:
        LastError = 8;
        goto LABEL_91;
      }
      memcpy_0(v39, a3, v38);
    }
  }
  v40 = o__aligned_malloc_0(v29 + 76, 0x10u);
  v32 = v40;
  if ( !v40 )
    goto LABEL_75;
  v41 = v60;
  v42 = v53;
  *v40 = v59;
  v43 = v61;
  v40[1] = v41;
  v44 = *(_OWORD *)v62;
  v40[2] = v43;
  v45 = *(_OWORD *)&v62[12];
  v40[3] = v44;
  *(_OWORD *)((char *)v40 + 60) = v45;
  ORCompressCopyName((char *)v40 + 76, v29 + 76, v42, &v58);
  *(_QWORD *)(v31 + 40) = v32;
  if ( !v18 || *(_WORD *)(v18 + 28) != 29806 || *(_WORD *)(v31 + 28) != 29806 )
  {
    LastError = 87;
    goto LABEL_91;
  }
  ORInsertTreeNodeIntoSubkeyList(v18, v31);
  v46 = *(_QWORD *)(v18 + 40);
  v10 = *(_QWORD *)IsContainerObject;
  *(_DWORD *)(v46 + 20) += IsContainerObject[0];
  *(struct _FILETIME *)(v46 + 4) = SystemTimeAsFileTime;
  if ( (unsigned int)v63 > *(_DWORD *)(v46 + 56) )
    *(_DWORD *)(v46 + 56) = v63;
  if ( (v30 & 0x20) != 0 )
  {
    if ( 2 * v29 > (unsigned __int64)*(unsigned __int16 *)(v46 + 52) )
    {
      LOWORD(v29) = 2 * v29;
LABEL_85:
      *(_WORD *)(v46 + 52) = v29;
    }
  }
  else if ( (unsigned __int16)v29 > *(_WORD *)(v46 + 52) )
  {
    goto LABEL_85;
  }
  *(_QWORD *)(v18 + 168) += v10;
  if ( a7 )
    *a7 = v10;
  v14 = v49;
  LastError = 0;
  *(_DWORD *)(v49 + 180) = v10;
  *(_DWORD *)(v31 + 24) = v10;
  *a6 = v31;
LABEL_98:
  if ( CreatorDescriptor != pSecurityDescriptor && CreatorDescriptor )
    aligned_free(CreatorDescriptor);
  if ( NewDescriptor )
    DestroyPrivateObjectSecurity(&NewDescriptor);
  if ( (_DWORD)v10 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 136));
  return LastError;
}

```

## disassembly

```asm
0x1801a35e0  mov     [rsp-8+arg_8], rbx
0x1801a35e5  mov     [rsp-8+Src], r8
0x1801a35ea  push    rbp
0x1801a35eb  push    rsi
0x1801a35ec  push    rdi
0x1801a35ed  push    r12
0x1801a35ef  push    r13
0x1801a35f1  push    r14
0x1801a35f3  push    r15
0x1801a35f5  lea     rbp, [rsp-0Fh]
0x1801a35fa  sub     rsp, 100h
0x1801a3601  mov     r12, [rbp+3Fh+arg_28]
0x1801a3605  xor     r10d, r10d
0x1801a3608  mov     eax, 746Eh
0x1801a360d  mov     [rsp+130h+var_C0], r10
0x1801a3612  xorps   xmm0, xmm0
0x1801a3615  mov     [rbp+3Fh+var_A8], r10
0x1801a3619  xorps   xmm1, xmm1
0x1801a361c  mov     [rsp+130h+var_D8], r10d
0x1801a3621  mov     [r12], r10
0x1801a3625  mov     rdi, rdx
0x1801a3628  mov     rsi, rcx
0x1801a362b  mov     [rsp+130h+var_E0], r10
0x1801a3630  mov     r15d, r10d
0x1801a3633  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r10
0x1801a3638  movups  [rbp+3Fh+var_90], xmm0
0x1801a363c  mov     [rbp+3Fh+CreatorDescriptor], r10
0x1801a3640  movups  [rbp+3Fh+var_A0], xmm1
0x1801a3644  mov     [rbp+3Fh+NewDescriptor], r10
0x1801a3648  cmp     [rcx+1Ch], ax
0x1801a364c  jnz     loc_1801A3BC5
0x1801a3652  mov     r13, [rcx+10h]
0x1801a3656  mov     [rsp+130h+var_E0], r13
0x1801a365b  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x1801a3663  jnz     loc_1801A3BC5
0x1801a3669  test    rdx, rdx
0x1801a366c  jz      short loc_1801A3680
0x1801a366e  cmp     [rdx], r10w
0x1801a3672  jz      short loc_1801A3680
0x1801a3674  mov     r14d, r9d
0x1801a3677  and     r14d, 2
0x1801a367b  cmp     r9d, r14d
0x1801a367e  jz      short loc_1801A368D
0x1801a3680  mov     ebx, 57h ; 'W'
0x1801a3685  mov     rsi, r13
0x1801a3688  jmp     loc_1801A3BCF
0x1801a368d  lea     rcx, [r13+88h]; lpCriticalSection
0x1801a3694  call    cs:__imp_EnterCriticalSection
0x1801a369b  nop     dword ptr [rax+rax+00h]
0x1801a36a0  mov     r15d, 1
0x1801a36a6  lea     rcx, [rbp+3Fh+var_A0]
0x1801a36aa  mov     rdx, rdi
0x1801a36ad  mov     qword ptr [rsp+130h+var_C8], r15
0x1801a36b2  call    ORInitUnicodeStringEx
0x1801a36b7  xor     r10d, r10d
0x1801a36ba  mov     ebx, eax
0x1801a36bc  test    eax, eax
0x1801a36be  jnz     loc_1801A3BCA
0x1801a36c4  movzx   ecx, word ptr [rbp+3Fh+var_A0]
0x1801a36c8  lea     r8d, [r15+5Bh]
0x1801a36cc  test    cx, cx
0x1801a36cf  jz      short loc_1801A36F1
0x1801a36d1  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x1801a36d5  movzx   eax, cx
0x1801a36d8  shr     rax, 1
0x1801a36db  cmp     [rdx+rax*2-2], r8w
0x1801a36e1  jnz     short loc_1801A36ED
0x1801a36e3  mov     eax, 0FFFEh
0x1801a36e8  add     cx, ax
0x1801a36eb  jnz     short loc_1801A36D5
0x1801a36ed  mov     word ptr [rbp+3Fh+var_A0], cx
0x1801a36f1  cmp     [rsi+1Eh], r10w
0x1801a36f6  jz      short loc_1801A36FF
0x1801a36f8  mov     ebx, 3FAh
0x1801a36fd  jmp     short loc_1801A3685
0x1801a36ff  test    cx, cx
0x1801a3702  jz      loc_1801A3680
0x1801a3708  lea     r9, [rsp+130h+var_C0]
0x1801a370d  mov     rdx, rsi
0x1801a3710  lea     r8, [rsp+130h+var_D8]
0x1801a3715  lea     rcx, [rbp+3Fh+var_A0]
0x1801a3719  call    ORParseSubKey
0x1801a371e  xor     r10d, r10d
0x1801a3721  mov     ebx, eax
0x1801a3723  test    eax, eax
0x1801a3725  jnz     loc_1801A3BCA
0x1801a372b  cmp     [rsp+130h+var_D8], 2
0x1801a3730  jnz     short loc_1801A3791
0x1801a3732  mov     rcx, [rsp+130h+var_C0]
0x1801a3737  test    r14d, r14d
0x1801a373a  jz      short loc_1801A3752
0x1801a373c  mov     rax, [rcx+28h]
0x1801a3740  lea     r12d, [rbx+10h]
0x1801a3744  test    [rax+2], r12b
0x1801a3748  jz      loc_1801A3680
0x1801a374e  mov     r12, [rbp+3Fh+arg_28]
0x1801a3752  cmp     rcx, [r13+38h]
0x1801a3756  jz      loc_1801A3680
0x1801a375c  mov     edx, [rcx+18h]
0x1801a375f  or      eax, 0FFFFFFFFh
0x1801a3762  cmp     edx, eax
0x1801a3764  jnz     short loc_1801A3770
0x1801a3766  mov     ebx, 5AAh
0x1801a376b  jmp     loc_1801A3685
0x1801a3770  lea     eax, [rdx+1]
0x1801a3773  mov     [rcx+18h], eax
0x1801a3776  mov     rax, [rbp+3Fh+arg_30]
0x1801a377a  test    rax, rax
0x1801a377d  jz      short loc_1801A3785
0x1801a377f  mov     dword ptr [rax], 2
0x1801a3785  mov     [r12], rcx
0x1801a3789  mov     ebx, r10d
0x1801a378c  jmp     loc_1801A3685
0x1801a3791  mov     r13, [rsp+130h+var_C0]
0x1801a3796  mov     r12d, 10h
0x1801a379c  mov     rax, [r13+28h]
0x1801a37a0  test    [rax+2], r12b
0x1801a37a4  jz      short loc_1801A37B0
0x1801a37a6  mov     ebx, 5
0x1801a37ab  jmp     loc_1801A3BCA
0x1801a37b0  mov     al, [rax+0Dh]
0x1801a37b3  and     al, 3
0x1801a37b5  cmp     al, r15b
0x1801a37b8  jz      short loc_1801A37A6
0x1801a37ba  mov     eax, 1FEh
0x1801a37bf  cmp     [r13+20h], ax
0x1801a37c4  jnz     short loc_1801A37D0
0x1801a37c6  mov     ebx, 57h ; 'W'
0x1801a37cb  jmp     loc_1801A3BCA
0x1801a37d0  mov     rdx, r10
0x1801a37d3  mov     rax, rdi
0x1801a37d6  add     rax, 2
0x1801a37da  movzx   ecx, word ptr [rax]
0x1801a37dd  test    cx, cx
0x1801a37e0  jnz     short loc_1801A37D6
0x1801a37e2  mov     r8d, 5Ch ; '\'
0x1801a37e8  cmp     rax, rdi
0x1801a37eb  jbe     short loc_1801A37FC
0x1801a37ed  sub     rax, 2
0x1801a37f1  movzx   ecx, word ptr [rax]
0x1801a37f4  cmp     cx, r8w
0x1801a37f8  jnz     short loc_1801A3802
0x1801a37fa  jmp     short loc_1801A37E8
0x1801a37fc  cmp     cx, r8w
0x1801a3800  jz      short loc_1801A3815
0x1801a3802  cmp     rax, rdi
0x1801a3805  jz      short loc_1801A3815
0x1801a3807  sub     rax, 2
0x1801a380b  add     rdx, 2
0x1801a380f  cmp     [rax], r8w
0x1801a3813  jnz     short loc_1801A3802
0x1801a3815  cmp     r8w, [rax]
0x1801a3819  lea     rsi, [rax+2]
0x1801a381d  lea     rbx, [rdx+2]
0x1801a3821  cmovnz  rsi, rax
0x1801a3825  cmp     rsi, rdi
0x1801a3828  cmovnz  rbx, rdx
0x1801a382c  cmp     rbx, 200h
0x1801a3833  ja      short loc_1801A37C6
0x1801a3835  xor     edx, edx; Val
0x1801a3837  lea     rcx, [rbp+3Fh+var_80]; void *
0x1801a383b  lea     r8d, [rdx+50h]; Size
0x1801a383f  call    memset_0
0x1801a3844  xor     edi, edi
0x1801a3846  mov     eax, 6B6Eh
0x1801a384b  mov     word ptr [rbp+3Fh+var_80], ax
0x1801a384f  test    r14d, r14d
0x1801a3852  jz      short loc_1801A385A
0x1801a3854  movzx   r14d, r12w
0x1801a3858  jmp     short loc_1801A385D
0x1801a385a  mov     r14d, edi
0x1801a385d  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801a3862  call    cs:__imp_GetSystemTimeAsFileTime
0x1801a3869  nop     dword ptr [rax+rax+00h]
0x1801a386e  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x1801a3872  lea     rdx, [rbp+3Fh+var_90]
0x1801a3876  mov     r10, [rsp+130h+var_E0]
0x1801a387b  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x1801a387e  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x1801a3882  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x1801a3885  or      eax, 0FFFFFFFFh
0x1801a3888  mov     dword ptr [rbp+3Fh+var_70], eax
0x1801a388b  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x1801a388e  mov     dword ptr [rbp+3Fh+var_60], eax
0x1801a3891  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x1801a3894  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x1801a3897  mov     dword ptr [rbp+3Fh+var_50], eax
0x1801a389a  mov     eax, edi
0x1801a389c  mov     [rbp+3Fh+arg_0], eax
0x1801a389f  mov     [rbp+3Fh+var_36], ax
0x1801a38a3  mov     rax, [r10+10h]
0x1801a38a7  mov     rcx, rax
0x1801a38aa  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x1801a38ae  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x1801a38b2  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x1801a38b5  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x1801a38b9  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x1801a38bd  mov     qword ptr [rbp+3Fh+var_90+8], rsi
0x1801a38c1  mov     word ptr [rbp+3Fh+var_90], bx
0x1801a38c5  mov     [rsp+130h+var_C0], rax
0x1801a38ca  mov     word ptr [rbp+3Fh+var_90+2], bx
0x1801a38ce  call    ORGetCompressedLength
0x1801a38d3  movzx   esi, ax
0x1801a38d6  mov     [rbp+3Fh+var_38], si
0x1801a38da  cmp     rsi, rbx
0x1801a38dd  jnb     short loc_1801A38E6
0x1801a38df  or      r14w, 20h
0x1801a38e4  jmp     short loc_1801A38EF
0x1801a38e6  mov     eax, 0FFDFh
0x1801a38eb  and     r14w, ax
0x1801a38ef  mov     rdx, r13
0x1801a38f2  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x1801a38f7  mov     rcx, r10
0x1801a38fa  call    ORAllocNode
0x1801a38ff  xor     r10d, r10d
0x1801a3902  mov     rdi, rax
0x1801a3905  test    rax, rax
0x1801a3908  jnz     short loc_1801A3912
0x1801a390a  lea     ebx, [rax+8]
0x1801a390d  jmp     loc_1801A3BCA
0x1801a3912  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x1801a3916  mov     r15, r10
0x1801a3919  test    rbx, rbx
0x1801a391c  jz      short loc_1801A3951
0x1801a391e  mov     rcx, rbx; pSecurityDescriptor
0x1801a3921  call    cs:__imp_IsValidSecurityDescriptor
0x1801a3928  nop     dword ptr [rax+rax+00h]
0x1801a392d  test    eax, eax
0x1801a392f  jnz     short loc_1801A393B
0x1801a3931  mov     ebx, 53Ah
0x1801a3936  jmp     loc_1801A3B9B
0x1801a393b  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x1801a393f  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1801a3942  call    ORMakeSDRelative
0x1801a3947  mov     ebx, eax
0x1801a3949  test    eax, eax
0x1801a394b  jnz     loc_1801A3B9B
0x1801a3951  mov     rax, [r13+60h]
0x1801a3955  xor     ebx, ebx
0x1801a3957  mov     rdx, [rbp+3Fh+CreatorDescriptor]; CreatorDescriptor
0x1801a395b  mov     r10, [rax+10h]
0x1801a395f  test    rdx, rdx
0x1801a3962  jz      short loc_1801A3971
0x1801a3964  test    byte ptr [rdx+2], 4
0x1801a3968  jz      short loc_1801A3971
0x1801a396a  mov     eax, 1078h
0x1801a396f  jmp     short loc_1801A3988
0x1801a3971  movzx   eax, word ptr [r10+16h]
0x1801a3976  and     eax, 400h
0x1801a397b  or      eax, 41E000h
0x1801a3980  shr     eax, 0Ah
0x1801a3983  test    rdx, rdx
0x1801a3986  jz      short loc_1801A398E
0x1801a3988  test    [rdx+2], r12b
0x1801a398c  jnz     short loc_1801A399D
0x1801a398e  mov     ecx, 800h
0x1801a3993  test    [r10+16h], cx
0x1801a3998  jz      short loc_1801A399D
0x1801a399a  or      eax, 2
0x1801a399d  lea     rcx, CmKeyMapping
0x1801a39a4  xor     r9d, r9d; ObjectTypes
0x1801a39a7  mov     [rsp+130h+GenericMapping], rcx; GenericMapping
0x1801a39ac  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x1801a39b0  mov     [rsp+130h+Token], rbx; Token
0x1801a39b5  lea     rcx, [r10+14h]; ParentDescriptor
0x1801a39b9  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x1801a39bd  mov     rax, qword ptr [rsp+130h+var_C8]
0x1801a39c2  mov     [rsp+130h+IsContainerObject], eax; IsContainerObject
0x1801a39c6  mov     [rsp+130h+GuidCount], ebx; GuidCount
0x1801a39ca  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x1801a39d1  nop     dword ptr [rax+rax+00h]
0x1801a39d6  test    eax, eax
0x1801a39d8  jnz     short loc_1801A39F0
0x1801a39da  call    cs:__imp_GetLastError
0x1801a39e1  nop     dword ptr [rax+rax+00h]
0x1801a39e6  mov     ebx, eax
0x1801a39e8  test    eax, eax
0x1801a39ea  jnz     loc_1801A3B9B
0x1801a39f0  mov     rdx, [rbp+3Fh+NewDescriptor]
0x1801a39f4  lea     r8, [rbp+3Fh+var_A8]
0x1801a39f8  mov     rcx, [rsp+130h+var_E0]
0x1801a39fd  call    ORProcessSecurityDescriptor
0x1801a3a02  mov     ebx, eax
0x1801a3a04  test    eax, eax
0x1801a3a06  jnz     loc_1801A3B9B
0x1801a3a0c  mov     rax, [rbp+3Fh+var_A8]
0x1801a3a10  xor     ebx, ebx
0x1801a3a12  mov     [rdi+60h], rax
0x1801a3a16  mov     rcx, [rax+10h]
0x1801a3a1a  mov     rax, qword ptr [rsp+130h+var_C8]
0x1801a3a1f  add     [rcx+0Ch], eax
0x1801a3a22  mov     rcx, [rbp+3Fh+Src]
0x1801a3a26  test    rcx, rcx
0x1801a3a29  jz      short loc_1801A3A7B
0x1801a3a2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a3a2f  inc     rax
0x1801a3a32  cmp     [rcx+rax*2], bx
0x1801a3a36  jnz     short loc_1801A3A2F
0x1801a3a38  add     rax, rax
0x1801a3a3b  cmp     rax, 0FFFFh
  ... truncated ...
```
