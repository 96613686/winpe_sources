# ORCreateKey

- ea: `0x180179af4`
- end: `0x18017a148`
- name: `ORCreateKey`
- size: `1620`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18014d1c0`

## callees

- `0x180003ae2`
- `0x180003aee`
- `0x180003c64`
- `0x18000693e`
- `0x1801799cc`
- `0x180179af4`
- `0x18017a644`
- `0x18017c3f0`
- `0x18017c7e4`
- `0x18017c838`
- `0x18017c8e0`
- `0x18017de90`
- `0x18017e944`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180179d76`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180179d76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180179eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180179eee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017a11e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017a11e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180179ba8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180179ba8`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180179e35`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180179e35`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18017a106`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18017a106`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x180179ede`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x180179ede`

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
0x180179af4  mov     [rsp-8+arg_8], rbx
0x180179af9  mov     [rsp-8+Src], r8
0x180179afe  push    rbp
0x180179aff  push    rsi
0x180179b00  push    rdi
0x180179b01  push    r12
0x180179b03  push    r13
0x180179b05  push    r14
0x180179b07  push    r15
0x180179b09  lea     rbp, [rsp-0Fh]
0x180179b0e  sub     rsp, 100h
0x180179b15  mov     r12, [rbp+3Fh+arg_28]
0x180179b19  xor     r10d, r10d
0x180179b1c  mov     eax, 746Eh
0x180179b21  mov     [rsp+130h+var_C0], r10
0x180179b26  xorps   xmm0, xmm0
0x180179b29  mov     [rbp+3Fh+var_A8], r10
0x180179b2d  xorps   xmm1, xmm1
0x180179b30  mov     [rsp+130h+var_D8], r10d
0x180179b35  mov     [r12], r10
0x180179b39  mov     rdi, rdx
0x180179b3c  mov     rsi, rcx
0x180179b3f  mov     [rsp+130h+var_E0], r10
0x180179b44  mov     r15d, r10d
0x180179b47  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r10
0x180179b4c  movups  [rbp+3Fh+var_90], xmm0
0x180179b50  mov     [rbp+3Fh+CreatorDescriptor], r10
0x180179b54  movups  [rbp+3Fh+var_A0], xmm1
0x180179b58  mov     [rbp+3Fh+NewDescriptor], r10
0x180179b5c  cmp     [rcx+1Ch], ax
0x180179b60  jnz     loc_18017A0D9
0x180179b66  mov     r13, [rcx+10h]
0x180179b6a  mov     [rsp+130h+var_E0], r13
0x180179b6f  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x180179b77  jnz     loc_18017A0D9
0x180179b7d  test    rdx, rdx
0x180179b80  jz      short loc_180179B94
0x180179b82  cmp     [rdx], r10w
0x180179b86  jz      short loc_180179B94
0x180179b88  mov     r14d, r9d
0x180179b8b  and     r14d, 2
0x180179b8f  cmp     r9d, r14d
0x180179b92  jz      short loc_180179BA1
0x180179b94  mov     ebx, 57h ; 'W'
0x180179b99  mov     rsi, r13
0x180179b9c  jmp     loc_18017A0E3
0x180179ba1  lea     rcx, [r13+88h]; lpCriticalSection
0x180179ba8  call    cs:__imp_EnterCriticalSection
0x180179baf  nop     dword ptr [rax+rax+00h]
0x180179bb4  mov     r15d, 1
0x180179bba  lea     rcx, [rbp+3Fh+var_A0]
0x180179bbe  mov     rdx, rdi
0x180179bc1  mov     qword ptr [rsp+130h+var_C8], r15
0x180179bc6  call    ORInitUnicodeStringEx
0x180179bcb  xor     r10d, r10d
0x180179bce  mov     ebx, eax
0x180179bd0  test    eax, eax
0x180179bd2  jnz     loc_18017A0DE
0x180179bd8  movzx   ecx, word ptr [rbp+3Fh+var_A0]
0x180179bdc  lea     r8d, [r15+5Bh]
0x180179be0  test    cx, cx
0x180179be3  jz      short loc_180179C05
0x180179be5  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x180179be9  movzx   eax, cx
0x180179bec  shr     rax, 1
0x180179bef  cmp     [rdx+rax*2-2], r8w
0x180179bf5  jnz     short loc_180179C01
0x180179bf7  mov     eax, 0FFFEh
0x180179bfc  add     cx, ax
0x180179bff  jnz     short loc_180179BE9
0x180179c01  mov     word ptr [rbp+3Fh+var_A0], cx
0x180179c05  cmp     [rsi+1Eh], r10w
0x180179c0a  jz      short loc_180179C13
0x180179c0c  mov     ebx, 3FAh
0x180179c11  jmp     short loc_180179B99
0x180179c13  test    cx, cx
0x180179c16  jz      loc_180179B94
0x180179c1c  lea     r9, [rsp+130h+var_C0]
0x180179c21  mov     rdx, rsi
0x180179c24  lea     r8, [rsp+130h+var_D8]
0x180179c29  lea     rcx, [rbp+3Fh+var_A0]
0x180179c2d  call    ORParseSubKey
0x180179c32  xor     r10d, r10d
0x180179c35  mov     ebx, eax
0x180179c37  test    eax, eax
0x180179c39  jnz     loc_18017A0DE
0x180179c3f  cmp     [rsp+130h+var_D8], 2
0x180179c44  jnz     short loc_180179CA5
0x180179c46  mov     rcx, [rsp+130h+var_C0]
0x180179c4b  test    r14d, r14d
0x180179c4e  jz      short loc_180179C66
0x180179c50  mov     rax, [rcx+28h]
0x180179c54  lea     r12d, [rbx+10h]
0x180179c58  test    [rax+2], r12b
0x180179c5c  jz      loc_180179B94
0x180179c62  mov     r12, [rbp+3Fh+arg_28]
0x180179c66  cmp     rcx, [r13+38h]
0x180179c6a  jz      loc_180179B94
0x180179c70  mov     edx, [rcx+18h]
0x180179c73  or      eax, 0FFFFFFFFh
0x180179c76  cmp     edx, eax
0x180179c78  jnz     short loc_180179C84
0x180179c7a  mov     ebx, 5AAh
0x180179c7f  jmp     loc_180179B99
0x180179c84  lea     eax, [rdx+1]
0x180179c87  mov     [rcx+18h], eax
0x180179c8a  mov     rax, [rbp+3Fh+arg_30]
0x180179c8e  test    rax, rax
0x180179c91  jz      short loc_180179C99
0x180179c93  mov     dword ptr [rax], 2
0x180179c99  mov     [r12], rcx
0x180179c9d  mov     ebx, r10d
0x180179ca0  jmp     loc_180179B99
0x180179ca5  mov     r13, [rsp+130h+var_C0]
0x180179caa  mov     r12d, 10h
0x180179cb0  mov     rax, [r13+28h]
0x180179cb4  test    [rax+2], r12b
0x180179cb8  jz      short loc_180179CC4
0x180179cba  mov     ebx, 5
0x180179cbf  jmp     loc_18017A0DE
0x180179cc4  mov     al, [rax+0Dh]
0x180179cc7  and     al, 3
0x180179cc9  cmp     al, r15b
0x180179ccc  jz      short loc_180179CBA
0x180179cce  mov     eax, 1FEh
0x180179cd3  cmp     [r13+20h], ax
0x180179cd8  jnz     short loc_180179CE4
0x180179cda  mov     ebx, 57h ; 'W'
0x180179cdf  jmp     loc_18017A0DE
0x180179ce4  mov     rdx, r10
0x180179ce7  mov     rax, rdi
0x180179cea  add     rax, 2
0x180179cee  movzx   ecx, word ptr [rax]
0x180179cf1  test    cx, cx
0x180179cf4  jnz     short loc_180179CEA
0x180179cf6  mov     r8d, 5Ch ; '\'
0x180179cfc  cmp     rax, rdi
0x180179cff  jbe     short loc_180179D10
0x180179d01  sub     rax, 2
0x180179d05  movzx   ecx, word ptr [rax]
0x180179d08  cmp     cx, r8w
0x180179d0c  jnz     short loc_180179D16
0x180179d0e  jmp     short loc_180179CFC
0x180179d10  cmp     cx, r8w
0x180179d14  jz      short loc_180179D29
0x180179d16  cmp     rax, rdi
0x180179d19  jz      short loc_180179D29
0x180179d1b  sub     rax, 2
0x180179d1f  add     rdx, 2
0x180179d23  cmp     [rax], r8w
0x180179d27  jnz     short loc_180179D16
0x180179d29  cmp     r8w, [rax]
0x180179d2d  lea     rsi, [rax+2]
0x180179d31  lea     rbx, [rdx+2]
0x180179d35  cmovnz  rsi, rax
0x180179d39  cmp     rsi, rdi
0x180179d3c  cmovnz  rbx, rdx
0x180179d40  cmp     rbx, 200h
0x180179d47  ja      short loc_180179CDA
0x180179d49  xor     edx, edx; Val
0x180179d4b  lea     rcx, [rbp+3Fh+var_80]; void *
0x180179d4f  lea     r8d, [rdx+50h]; Size
0x180179d53  call    memset_0
0x180179d58  xor     edi, edi
0x180179d5a  mov     eax, 6B6Eh
0x180179d5f  mov     word ptr [rbp+3Fh+var_80], ax
0x180179d63  test    r14d, r14d
0x180179d66  jz      short loc_180179D6E
0x180179d68  movzx   r14d, r12w
0x180179d6c  jmp     short loc_180179D71
0x180179d6e  mov     r14d, edi
0x180179d71  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180179d76  call    cs:__imp_GetSystemTimeAsFileTime
0x180179d7d  nop     dword ptr [rax+rax+00h]
0x180179d82  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x180179d86  lea     rdx, [rbp+3Fh+var_90]
0x180179d8a  mov     r10, [rsp+130h+var_E0]
0x180179d8f  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x180179d92  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x180179d96  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x180179d99  or      eax, 0FFFFFFFFh
0x180179d9c  mov     dword ptr [rbp+3Fh+var_70], eax
0x180179d9f  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x180179da2  mov     dword ptr [rbp+3Fh+var_60], eax
0x180179da5  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x180179da8  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x180179dab  mov     dword ptr [rbp+3Fh+var_50], eax
0x180179dae  mov     eax, edi
0x180179db0  mov     [rbp+3Fh+arg_0], eax
0x180179db3  mov     [rbp+3Fh+var_36], ax
0x180179db7  mov     rax, [r10+10h]
0x180179dbb  mov     rcx, rax
0x180179dbe  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x180179dc2  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x180179dc6  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x180179dc9  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x180179dcd  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x180179dd1  mov     qword ptr [rbp+3Fh+var_90+8], rsi
0x180179dd5  mov     word ptr [rbp+3Fh+var_90], bx
0x180179dd9  mov     [rsp+130h+var_C0], rax
0x180179dde  mov     word ptr [rbp+3Fh+var_90+2], bx
0x180179de2  call    ORGetCompressedLength
0x180179de7  movzx   esi, ax
0x180179dea  mov     [rbp+3Fh+var_38], si
0x180179dee  cmp     rsi, rbx
0x180179df1  jnb     short loc_180179DFA
0x180179df3  or      r14w, 20h
0x180179df8  jmp     short loc_180179E03
0x180179dfa  mov     eax, 0FFDFh
0x180179dff  and     r14w, ax
0x180179e03  mov     rdx, r13
0x180179e06  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x180179e0b  mov     rcx, r10
0x180179e0e  call    ORAllocNode
0x180179e13  xor     r10d, r10d
0x180179e16  mov     rdi, rax
0x180179e19  test    rax, rax
0x180179e1c  jnz     short loc_180179E26
0x180179e1e  lea     ebx, [rax+8]
0x180179e21  jmp     loc_18017A0DE
0x180179e26  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x180179e2a  mov     r15, r10
0x180179e2d  test    rbx, rbx
0x180179e30  jz      short loc_180179E65
0x180179e32  mov     rcx, rbx; pSecurityDescriptor
0x180179e35  call    cs:__imp_IsValidSecurityDescriptor
0x180179e3c  nop     dword ptr [rax+rax+00h]
0x180179e41  test    eax, eax
0x180179e43  jnz     short loc_180179E4F
0x180179e45  mov     ebx, 53Ah
0x180179e4a  jmp     loc_18017A0AF
0x180179e4f  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x180179e53  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180179e56  call    ORMakeSDRelative
0x180179e5b  mov     ebx, eax
0x180179e5d  test    eax, eax
0x180179e5f  jnz     loc_18017A0AF
0x180179e65  mov     rax, [r13+60h]
0x180179e69  xor     ebx, ebx
0x180179e6b  mov     rdx, [rbp+3Fh+CreatorDescriptor]; CreatorDescriptor
0x180179e6f  mov     r10, [rax+10h]
0x180179e73  test    rdx, rdx
0x180179e76  jz      short loc_180179E85
0x180179e78  test    byte ptr [rdx+2], 4
0x180179e7c  jz      short loc_180179E85
0x180179e7e  mov     eax, 1078h
0x180179e83  jmp     short loc_180179E9C
0x180179e85  movzx   eax, word ptr [r10+16h]
0x180179e8a  and     eax, 400h
0x180179e8f  or      eax, 41E000h
0x180179e94  shr     eax, 0Ah
0x180179e97  test    rdx, rdx
0x180179e9a  jz      short loc_180179EA2
0x180179e9c  test    [rdx+2], r12b
0x180179ea0  jnz     short loc_180179EB1
0x180179ea2  mov     ecx, 800h
0x180179ea7  test    [r10+16h], cx
0x180179eac  jz      short loc_180179EB1
0x180179eae  or      eax, 2
0x180179eb1  lea     rcx, CmKeyMapping
0x180179eb8  xor     r9d, r9d; ObjectTypes
0x180179ebb  mov     [rsp+130h+GenericMapping], rcx; GenericMapping
0x180179ec0  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x180179ec4  mov     [rsp+130h+Token], rbx; Token
0x180179ec9  lea     rcx, [r10+14h]; ParentDescriptor
0x180179ecd  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x180179ed1  mov     rax, qword ptr [rsp+130h+var_C8]
0x180179ed6  mov     [rsp+130h+IsContainerObject], eax; IsContainerObject
0x180179eda  mov     [rsp+130h+GuidCount], ebx; GuidCount
0x180179ede  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x180179ee5  nop     dword ptr [rax+rax+00h]
0x180179eea  test    eax, eax
0x180179eec  jnz     short loc_180179F04
0x180179eee  call    cs:__imp_GetLastError
0x180179ef5  nop     dword ptr [rax+rax+00h]
0x180179efa  mov     ebx, eax
0x180179efc  test    eax, eax
0x180179efe  jnz     loc_18017A0AF
0x180179f04  mov     rdx, [rbp+3Fh+NewDescriptor]
0x180179f08  lea     r8, [rbp+3Fh+var_A8]
0x180179f0c  mov     rcx, [rsp+130h+var_E0]
0x180179f11  call    ORProcessSecurityDescriptor
0x180179f16  mov     ebx, eax
0x180179f18  test    eax, eax
0x180179f1a  jnz     loc_18017A0AF
0x180179f20  mov     rax, [rbp+3Fh+var_A8]
0x180179f24  xor     ebx, ebx
0x180179f26  mov     [rdi+60h], rax
0x180179f2a  mov     rcx, [rax+10h]
0x180179f2e  mov     rax, qword ptr [rsp+130h+var_C8]
0x180179f33  add     [rcx+0Ch], eax
0x180179f36  mov     rcx, [rbp+3Fh+Src]
0x180179f3a  test    rcx, rcx
0x180179f3d  jz      short loc_180179F8F
0x180179f3f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180179f43  inc     rax
0x180179f46  cmp     [rcx+rax*2], bx
0x180179f4a  jnz     short loc_180179F43
0x180179f4c  add     rax, rax
0x180179f4f  cmp     rax, 0FFFFh
  ... truncated ...
```
