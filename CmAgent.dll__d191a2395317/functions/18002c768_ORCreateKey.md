# ORCreateKey

- ea: `0x18002c768`
- end: `0x18002cdbc`
- name: `ORCreateKey`
- size: `1620`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ac10`

## callees

- `0x180002b28`
- `0x180002b34`
- `0x180002c48`
- `0x18002c640`
- `0x18002c768`
- `0x18002d2b8`
- `0x18002eb7c`
- `0x18002ef40`
- `0x18002ef94`
- `0x18002f03c`
- `0x180030e5c`
- `0x180031a70`
- `0x1800361a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c81c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c81c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cd92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cd92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb62`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c9ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c9ea`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x18002cb52`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x18002cb52`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002caa9`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002caa9`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002cd7a`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002cd7a`

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
0x18002c768  mov     [rsp-8+arg_8], rbx
0x18002c76d  mov     [rsp-8+Src], r8
0x18002c772  push    rbp
0x18002c773  push    rsi
0x18002c774  push    rdi
0x18002c775  push    r12
0x18002c777  push    r13
0x18002c779  push    r14
0x18002c77b  push    r15
0x18002c77d  lea     rbp, [rsp-0Fh]
0x18002c782  sub     rsp, 100h
0x18002c789  mov     r12, [rbp+3Fh+arg_28]
0x18002c78d  xor     r10d, r10d
0x18002c790  mov     eax, 746Eh
0x18002c795  mov     [rsp+130h+var_C0], r10
0x18002c79a  xorps   xmm0, xmm0
0x18002c79d  mov     [rbp+3Fh+var_A8], r10
0x18002c7a1  xorps   xmm1, xmm1
0x18002c7a4  mov     [rsp+130h+var_D8], r10d
0x18002c7a9  mov     [r12], r10
0x18002c7ad  mov     rdi, rdx
0x18002c7b0  mov     rsi, rcx
0x18002c7b3  mov     [rsp+130h+var_E0], r10
0x18002c7b8  mov     r15d, r10d
0x18002c7bb  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r10
0x18002c7c0  movups  [rbp+3Fh+var_90], xmm0
0x18002c7c4  mov     [rbp+3Fh+CreatorDescriptor], r10
0x18002c7c8  movups  [rbp+3Fh+var_A0], xmm1
0x18002c7cc  mov     [rbp+3Fh+NewDescriptor], r10
0x18002c7d0  cmp     [rcx+1Ch], ax
0x18002c7d4  jnz     loc_18002CD4D
0x18002c7da  mov     r13, [rcx+10h]
0x18002c7de  mov     [rsp+130h+var_E0], r13
0x18002c7e3  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x18002c7eb  jnz     loc_18002CD4D
0x18002c7f1  test    rdx, rdx
0x18002c7f4  jz      short loc_18002C808
0x18002c7f6  cmp     [rdx], r10w
0x18002c7fa  jz      short loc_18002C808
0x18002c7fc  mov     r14d, r9d
0x18002c7ff  and     r14d, 2
0x18002c803  cmp     r9d, r14d
0x18002c806  jz      short loc_18002C815
0x18002c808  mov     ebx, 57h ; 'W'
0x18002c80d  mov     rsi, r13
0x18002c810  jmp     loc_18002CD57
0x18002c815  lea     rcx, [r13+88h]; lpCriticalSection
0x18002c81c  call    cs:__imp_EnterCriticalSection
0x18002c823  nop     dword ptr [rax+rax+00h]
0x18002c828  mov     r15d, 1
0x18002c82e  lea     rcx, [rbp+3Fh+var_A0]
0x18002c832  mov     rdx, rdi
0x18002c835  mov     qword ptr [rsp+130h+var_C8], r15
0x18002c83a  call    ORInitUnicodeStringEx
0x18002c83f  xor     r10d, r10d
0x18002c842  mov     ebx, eax
0x18002c844  test    eax, eax
0x18002c846  jnz     loc_18002CD52
0x18002c84c  movzx   ecx, word ptr [rbp+3Fh+var_A0]
0x18002c850  lea     r8d, [r15+5Bh]
0x18002c854  test    cx, cx
0x18002c857  jz      short loc_18002C879
0x18002c859  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x18002c85d  movzx   eax, cx
0x18002c860  shr     rax, 1
0x18002c863  cmp     [rdx+rax*2-2], r8w
0x18002c869  jnz     short loc_18002C875
0x18002c86b  mov     eax, 0FFFEh
0x18002c870  add     cx, ax
0x18002c873  jnz     short loc_18002C85D
0x18002c875  mov     word ptr [rbp+3Fh+var_A0], cx
0x18002c879  cmp     [rsi+1Eh], r10w
0x18002c87e  jz      short loc_18002C887
0x18002c880  mov     ebx, 3FAh
0x18002c885  jmp     short loc_18002C80D
0x18002c887  test    cx, cx
0x18002c88a  jz      loc_18002C808
0x18002c890  lea     r9, [rsp+130h+var_C0]
0x18002c895  mov     rdx, rsi
0x18002c898  lea     r8, [rsp+130h+var_D8]
0x18002c89d  lea     rcx, [rbp+3Fh+var_A0]
0x18002c8a1  call    ORParseSubKey
0x18002c8a6  xor     r10d, r10d
0x18002c8a9  mov     ebx, eax
0x18002c8ab  test    eax, eax
0x18002c8ad  jnz     loc_18002CD52
0x18002c8b3  cmp     [rsp+130h+var_D8], 2
0x18002c8b8  jnz     short loc_18002C919
0x18002c8ba  mov     rcx, [rsp+130h+var_C0]
0x18002c8bf  test    r14d, r14d
0x18002c8c2  jz      short loc_18002C8DA
0x18002c8c4  mov     rax, [rcx+28h]
0x18002c8c8  lea     r12d, [rbx+10h]
0x18002c8cc  test    [rax+2], r12b
0x18002c8d0  jz      loc_18002C808
0x18002c8d6  mov     r12, [rbp+3Fh+arg_28]
0x18002c8da  cmp     rcx, [r13+38h]
0x18002c8de  jz      loc_18002C808
0x18002c8e4  mov     edx, [rcx+18h]
0x18002c8e7  or      eax, 0FFFFFFFFh
0x18002c8ea  cmp     edx, eax
0x18002c8ec  jnz     short loc_18002C8F8
0x18002c8ee  mov     ebx, 5AAh
0x18002c8f3  jmp     loc_18002C80D
0x18002c8f8  lea     eax, [rdx+1]
0x18002c8fb  mov     [rcx+18h], eax
0x18002c8fe  mov     rax, [rbp+3Fh+arg_30]
0x18002c902  test    rax, rax
0x18002c905  jz      short loc_18002C90D
0x18002c907  mov     dword ptr [rax], 2
0x18002c90d  mov     [r12], rcx
0x18002c911  mov     ebx, r10d
0x18002c914  jmp     loc_18002C80D
0x18002c919  mov     r13, [rsp+130h+var_C0]
0x18002c91e  mov     r12d, 10h
0x18002c924  mov     rax, [r13+28h]
0x18002c928  test    [rax+2], r12b
0x18002c92c  jz      short loc_18002C938
0x18002c92e  mov     ebx, 5
0x18002c933  jmp     loc_18002CD52
0x18002c938  mov     al, [rax+0Dh]
0x18002c93b  and     al, 3
0x18002c93d  cmp     al, r15b
0x18002c940  jz      short loc_18002C92E
0x18002c942  mov     eax, 1FEh
0x18002c947  cmp     [r13+20h], ax
0x18002c94c  jnz     short loc_18002C958
0x18002c94e  mov     ebx, 57h ; 'W'
0x18002c953  jmp     loc_18002CD52
0x18002c958  mov     rdx, r10
0x18002c95b  mov     rax, rdi
0x18002c95e  add     rax, 2
0x18002c962  movzx   ecx, word ptr [rax]
0x18002c965  test    cx, cx
0x18002c968  jnz     short loc_18002C95E
0x18002c96a  mov     r8d, 5Ch ; '\'
0x18002c970  cmp     rax, rdi
0x18002c973  jbe     short loc_18002C984
0x18002c975  sub     rax, 2
0x18002c979  movzx   ecx, word ptr [rax]
0x18002c97c  cmp     cx, r8w
0x18002c980  jnz     short loc_18002C98A
0x18002c982  jmp     short loc_18002C970
0x18002c984  cmp     cx, r8w
0x18002c988  jz      short loc_18002C99D
0x18002c98a  cmp     rax, rdi
0x18002c98d  jz      short loc_18002C99D
0x18002c98f  sub     rax, 2
0x18002c993  add     rdx, 2
0x18002c997  cmp     [rax], r8w
0x18002c99b  jnz     short loc_18002C98A
0x18002c99d  cmp     r8w, [rax]
0x18002c9a1  lea     rsi, [rax+2]
0x18002c9a5  lea     rbx, [rdx+2]
0x18002c9a9  cmovnz  rsi, rax
0x18002c9ad  cmp     rsi, rdi
0x18002c9b0  cmovnz  rbx, rdx
0x18002c9b4  cmp     rbx, 200h
0x18002c9bb  ja      short loc_18002C94E
0x18002c9bd  xor     edx, edx; Val
0x18002c9bf  lea     rcx, [rbp+3Fh+var_80]; void *
0x18002c9c3  lea     r8d, [rdx+50h]; Size
0x18002c9c7  call    memset_0
0x18002c9cc  xor     edi, edi
0x18002c9ce  mov     eax, 6B6Eh
0x18002c9d3  mov     word ptr [rbp+3Fh+var_80], ax
0x18002c9d7  test    r14d, r14d
0x18002c9da  jz      short loc_18002C9E2
0x18002c9dc  movzx   r14d, r12w
0x18002c9e0  jmp     short loc_18002C9E5
0x18002c9e2  mov     r14d, edi
0x18002c9e5  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002c9ea  call    cs:__imp_GetSystemTimeAsFileTime
0x18002c9f1  nop     dword ptr [rax+rax+00h]
0x18002c9f6  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x18002c9fa  lea     rdx, [rbp+3Fh+var_90]
0x18002c9fe  mov     r10, [rsp+130h+var_E0]
0x18002ca03  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x18002ca06  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x18002ca0a  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x18002ca0d  or      eax, 0FFFFFFFFh
0x18002ca10  mov     dword ptr [rbp+3Fh+var_70], eax
0x18002ca13  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x18002ca16  mov     dword ptr [rbp+3Fh+var_60], eax
0x18002ca19  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x18002ca1c  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x18002ca1f  mov     dword ptr [rbp+3Fh+var_50], eax
0x18002ca22  mov     eax, edi
0x18002ca24  mov     [rbp+3Fh+arg_0], eax
0x18002ca27  mov     [rbp+3Fh+var_36], ax
0x18002ca2b  mov     rax, [r10+10h]
0x18002ca2f  mov     rcx, rax
0x18002ca32  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x18002ca36  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x18002ca3a  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x18002ca3d  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x18002ca41  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x18002ca45  mov     qword ptr [rbp+3Fh+var_90+8], rsi
0x18002ca49  mov     word ptr [rbp+3Fh+var_90], bx
0x18002ca4d  mov     [rsp+130h+var_C0], rax
0x18002ca52  mov     word ptr [rbp+3Fh+var_90+2], bx
0x18002ca56  call    ORGetCompressedLength
0x18002ca5b  movzx   esi, ax
0x18002ca5e  mov     [rbp+3Fh+var_38], si
0x18002ca62  cmp     rsi, rbx
0x18002ca65  jnb     short loc_18002CA6E
0x18002ca67  or      r14w, 20h
0x18002ca6c  jmp     short loc_18002CA77
0x18002ca6e  mov     eax, 0FFDFh
0x18002ca73  and     r14w, ax
0x18002ca77  mov     rdx, r13
0x18002ca7a  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x18002ca7f  mov     rcx, r10
0x18002ca82  call    ORAllocNode
0x18002ca87  xor     r10d, r10d
0x18002ca8a  mov     rdi, rax
0x18002ca8d  test    rax, rax
0x18002ca90  jnz     short loc_18002CA9A
0x18002ca92  lea     ebx, [rax+8]
0x18002ca95  jmp     loc_18002CD52
0x18002ca9a  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x18002ca9e  mov     r15, r10
0x18002caa1  test    rbx, rbx
0x18002caa4  jz      short loc_18002CAD9
0x18002caa6  mov     rcx, rbx; pSecurityDescriptor
0x18002caa9  call    cs:__imp_IsValidSecurityDescriptor
0x18002cab0  nop     dword ptr [rax+rax+00h]
0x18002cab5  test    eax, eax
0x18002cab7  jnz     short loc_18002CAC3
0x18002cab9  mov     ebx, 53Ah
0x18002cabe  jmp     loc_18002CD23
0x18002cac3  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x18002cac7  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18002caca  call    ORMakeSDRelative
0x18002cacf  mov     ebx, eax
0x18002cad1  test    eax, eax
0x18002cad3  jnz     loc_18002CD23
0x18002cad9  mov     rax, [r13+60h]
0x18002cadd  xor     ebx, ebx
0x18002cadf  mov     rdx, [rbp+3Fh+CreatorDescriptor]; CreatorDescriptor
0x18002cae3  mov     r10, [rax+10h]
0x18002cae7  test    rdx, rdx
0x18002caea  jz      short loc_18002CAF9
0x18002caec  test    byte ptr [rdx+2], 4
0x18002caf0  jz      short loc_18002CAF9
0x18002caf2  mov     eax, 1078h
0x18002caf7  jmp     short loc_18002CB10
0x18002caf9  movzx   eax, word ptr [r10+16h]
0x18002cafe  and     eax, 400h
0x18002cb03  or      eax, 41E000h
0x18002cb08  shr     eax, 0Ah
0x18002cb0b  test    rdx, rdx
0x18002cb0e  jz      short loc_18002CB16
0x18002cb10  test    [rdx+2], r12b
0x18002cb14  jnz     short loc_18002CB25
0x18002cb16  mov     ecx, 800h
0x18002cb1b  test    [r10+16h], cx
0x18002cb20  jz      short loc_18002CB25
0x18002cb22  or      eax, 2
0x18002cb25  lea     rcx, CmKeyMapping
0x18002cb2c  xor     r9d, r9d; ObjectTypes
0x18002cb2f  mov     [rsp+130h+GenericMapping], rcx; GenericMapping
0x18002cb34  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x18002cb38  mov     [rsp+130h+Token], rbx; Token
0x18002cb3d  lea     rcx, [r10+14h]; ParentDescriptor
0x18002cb41  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x18002cb45  mov     rax, qword ptr [rsp+130h+var_C8]
0x18002cb4a  mov     [rsp+130h+IsContainerObject], eax; IsContainerObject
0x18002cb4e  mov     [rsp+130h+GuidCount], ebx; GuidCount
0x18002cb52  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x18002cb59  nop     dword ptr [rax+rax+00h]
0x18002cb5e  test    eax, eax
0x18002cb60  jnz     short loc_18002CB78
0x18002cb62  call    cs:__imp_GetLastError
0x18002cb69  nop     dword ptr [rax+rax+00h]
0x18002cb6e  mov     ebx, eax
0x18002cb70  test    eax, eax
0x18002cb72  jnz     loc_18002CD23
0x18002cb78  mov     rdx, [rbp+3Fh+NewDescriptor]
0x18002cb7c  lea     r8, [rbp+3Fh+var_A8]
0x18002cb80  mov     rcx, [rsp+130h+var_E0]
0x18002cb85  call    ORProcessSecurityDescriptor
0x18002cb8a  mov     ebx, eax
0x18002cb8c  test    eax, eax
0x18002cb8e  jnz     loc_18002CD23
0x18002cb94  mov     rax, [rbp+3Fh+var_A8]
0x18002cb98  xor     ebx, ebx
0x18002cb9a  mov     [rdi+60h], rax
0x18002cb9e  mov     rcx, [rax+10h]
0x18002cba2  mov     rax, qword ptr [rsp+130h+var_C8]
0x18002cba7  add     [rcx+0Ch], eax
0x18002cbaa  mov     rcx, [rbp+3Fh+Src]
0x18002cbae  test    rcx, rcx
0x18002cbb1  jz      short loc_18002CC03
0x18002cbb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002cbb7  inc     rax
0x18002cbba  cmp     [rcx+rax*2], bx
0x18002cbbe  jnz     short loc_18002CBB7
0x18002cbc0  add     rax, rax
0x18002cbc3  cmp     rax, 0FFFFh
  ... truncated ...
```
