# ORCreateKey

- ea: `0x1801a3750`
- end: `0x1801a3da4`
- name: `ORCreateKey`
- size: `1620`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180199658`

## callees

- `0x1800055d0`
- `0x1800055dc`
- `0x180005704`
- `0x1800069db`
- `0x1800375ac`
- `0x1800379e0`
- `0x180037a34`
- `0x180037adc`
- `0x1801a3628`
- `0x1801a3750`
- `0x1801a42a8`
- `0x1801a730c`
- `0x1801a7f20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x1801a3b3a`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x1801a3b3a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1801a3a91`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1801a3a91`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1801a3d62`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1801a3d62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a3d7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a3d7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a3804`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a3804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3b4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801a39d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801a39d2`

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
0x1801a3750  mov     [rsp-8+arg_8], rbx
0x1801a3755  mov     [rsp-8+Src], r8
0x1801a375a  push    rbp
0x1801a375b  push    rsi
0x1801a375c  push    rdi
0x1801a375d  push    r12
0x1801a375f  push    r13
0x1801a3761  push    r14
0x1801a3763  push    r15
0x1801a3765  lea     rbp, [rsp-0Fh]
0x1801a376a  sub     rsp, 100h
0x1801a3771  mov     r12, [rbp+3Fh+arg_28]
0x1801a3775  xor     r10d, r10d
0x1801a3778  mov     eax, 746Eh
0x1801a377d  mov     [rsp+130h+var_C0], r10
0x1801a3782  xorps   xmm0, xmm0
0x1801a3785  mov     [rbp+3Fh+var_A8], r10
0x1801a3789  xorps   xmm1, xmm1
0x1801a378c  mov     [rsp+130h+var_D8], r10d
0x1801a3791  mov     [r12], r10
0x1801a3795  mov     rdi, rdx
0x1801a3798  mov     rsi, rcx
0x1801a379b  mov     [rsp+130h+var_E0], r10
0x1801a37a0  mov     r15d, r10d
0x1801a37a3  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r10
0x1801a37a8  movups  [rbp+3Fh+var_90], xmm0
0x1801a37ac  mov     [rbp+3Fh+CreatorDescriptor], r10
0x1801a37b0  movups  [rbp+3Fh+var_A0], xmm1
0x1801a37b4  mov     [rbp+3Fh+NewDescriptor], r10
0x1801a37b8  cmp     [rcx+1Ch], ax
0x1801a37bc  jnz     loc_1801A3D35
0x1801a37c2  mov     r13, [rcx+10h]
0x1801a37c6  mov     [rsp+130h+var_E0], r13
0x1801a37cb  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x1801a37d3  jnz     loc_1801A3D35
0x1801a37d9  test    rdx, rdx
0x1801a37dc  jz      short loc_1801A37F0
0x1801a37de  cmp     [rdx], r10w
0x1801a37e2  jz      short loc_1801A37F0
0x1801a37e4  mov     r14d, r9d
0x1801a37e7  and     r14d, 2
0x1801a37eb  cmp     r9d, r14d
0x1801a37ee  jz      short loc_1801A37FD
0x1801a37f0  mov     ebx, 57h ; 'W'
0x1801a37f5  mov     rsi, r13
0x1801a37f8  jmp     loc_1801A3D3F
0x1801a37fd  lea     rcx, [r13+88h]; lpCriticalSection
0x1801a3804  call    cs:__imp_EnterCriticalSection
0x1801a380b  nop     dword ptr [rax+rax+00h]
0x1801a3810  mov     r15d, 1
0x1801a3816  lea     rcx, [rbp+3Fh+var_A0]
0x1801a381a  mov     rdx, rdi
0x1801a381d  mov     qword ptr [rsp+130h+var_C8], r15
0x1801a3822  call    ORInitUnicodeStringEx
0x1801a3827  xor     r10d, r10d
0x1801a382a  mov     ebx, eax
0x1801a382c  test    eax, eax
0x1801a382e  jnz     loc_1801A3D3A
0x1801a3834  movzx   ecx, word ptr [rbp+3Fh+var_A0]
0x1801a3838  lea     r8d, [r15+5Bh]
0x1801a383c  test    cx, cx
0x1801a383f  jz      short loc_1801A3861
0x1801a3841  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x1801a3845  movzx   eax, cx
0x1801a3848  shr     rax, 1
0x1801a384b  cmp     [rdx+rax*2-2], r8w
0x1801a3851  jnz     short loc_1801A385D
0x1801a3853  mov     eax, 0FFFEh
0x1801a3858  add     cx, ax
0x1801a385b  jnz     short loc_1801A3845
0x1801a385d  mov     word ptr [rbp+3Fh+var_A0], cx
0x1801a3861  cmp     [rsi+1Eh], r10w
0x1801a3866  jz      short loc_1801A386F
0x1801a3868  mov     ebx, 3FAh
0x1801a386d  jmp     short loc_1801A37F5
0x1801a386f  test    cx, cx
0x1801a3872  jz      loc_1801A37F0
0x1801a3878  lea     r9, [rsp+130h+var_C0]
0x1801a387d  mov     rdx, rsi
0x1801a3880  lea     r8, [rsp+130h+var_D8]
0x1801a3885  lea     rcx, [rbp+3Fh+var_A0]
0x1801a3889  call    ORParseSubKey
0x1801a388e  xor     r10d, r10d
0x1801a3891  mov     ebx, eax
0x1801a3893  test    eax, eax
0x1801a3895  jnz     loc_1801A3D3A
0x1801a389b  cmp     [rsp+130h+var_D8], 2
0x1801a38a0  jnz     short loc_1801A3901
0x1801a38a2  mov     rcx, [rsp+130h+var_C0]
0x1801a38a7  test    r14d, r14d
0x1801a38aa  jz      short loc_1801A38C2
0x1801a38ac  mov     rax, [rcx+28h]
0x1801a38b0  lea     r12d, [rbx+10h]
0x1801a38b4  test    [rax+2], r12b
0x1801a38b8  jz      loc_1801A37F0
0x1801a38be  mov     r12, [rbp+3Fh+arg_28]
0x1801a38c2  cmp     rcx, [r13+38h]
0x1801a38c6  jz      loc_1801A37F0
0x1801a38cc  mov     edx, [rcx+18h]
0x1801a38cf  or      eax, 0FFFFFFFFh
0x1801a38d2  cmp     edx, eax
0x1801a38d4  jnz     short loc_1801A38E0
0x1801a38d6  mov     ebx, 5AAh
0x1801a38db  jmp     loc_1801A37F5
0x1801a38e0  lea     eax, [rdx+1]
0x1801a38e3  mov     [rcx+18h], eax
0x1801a38e6  mov     rax, [rbp+3Fh+arg_30]
0x1801a38ea  test    rax, rax
0x1801a38ed  jz      short loc_1801A38F5
0x1801a38ef  mov     dword ptr [rax], 2
0x1801a38f5  mov     [r12], rcx
0x1801a38f9  mov     ebx, r10d
0x1801a38fc  jmp     loc_1801A37F5
0x1801a3901  mov     r13, [rsp+130h+var_C0]
0x1801a3906  mov     r12d, 10h
0x1801a390c  mov     rax, [r13+28h]
0x1801a3910  test    [rax+2], r12b
0x1801a3914  jz      short loc_1801A3920
0x1801a3916  mov     ebx, 5
0x1801a391b  jmp     loc_1801A3D3A
0x1801a3920  mov     al, [rax+0Dh]
0x1801a3923  and     al, 3
0x1801a3925  cmp     al, r15b
0x1801a3928  jz      short loc_1801A3916
0x1801a392a  mov     eax, 1FEh
0x1801a392f  cmp     [r13+20h], ax
0x1801a3934  jnz     short loc_1801A3940
0x1801a3936  mov     ebx, 57h ; 'W'
0x1801a393b  jmp     loc_1801A3D3A
0x1801a3940  mov     rdx, r10
0x1801a3943  mov     rax, rdi
0x1801a3946  add     rax, 2
0x1801a394a  movzx   ecx, word ptr [rax]
0x1801a394d  test    cx, cx
0x1801a3950  jnz     short loc_1801A3946
0x1801a3952  mov     r8d, 5Ch ; '\'
0x1801a3958  cmp     rax, rdi
0x1801a395b  jbe     short loc_1801A396C
0x1801a395d  sub     rax, 2
0x1801a3961  movzx   ecx, word ptr [rax]
0x1801a3964  cmp     cx, r8w
0x1801a3968  jnz     short loc_1801A3972
0x1801a396a  jmp     short loc_1801A3958
0x1801a396c  cmp     cx, r8w
0x1801a3970  jz      short loc_1801A3985
0x1801a3972  cmp     rax, rdi
0x1801a3975  jz      short loc_1801A3985
0x1801a3977  sub     rax, 2
0x1801a397b  add     rdx, 2
0x1801a397f  cmp     [rax], r8w
0x1801a3983  jnz     short loc_1801A3972
0x1801a3985  cmp     r8w, [rax]
0x1801a3989  lea     rsi, [rax+2]
0x1801a398d  lea     rbx, [rdx+2]
0x1801a3991  cmovnz  rsi, rax
0x1801a3995  cmp     rsi, rdi
0x1801a3998  cmovnz  rbx, rdx
0x1801a399c  cmp     rbx, 200h
0x1801a39a3  ja      short loc_1801A3936
0x1801a39a5  xor     edx, edx; Val
0x1801a39a7  lea     rcx, [rbp+3Fh+var_80]; void *
0x1801a39ab  lea     r8d, [rdx+50h]; Size
0x1801a39af  call    memset_0
0x1801a39b4  xor     edi, edi
0x1801a39b6  mov     eax, 6B6Eh
0x1801a39bb  mov     word ptr [rbp+3Fh+var_80], ax
0x1801a39bf  test    r14d, r14d
0x1801a39c2  jz      short loc_1801A39CA
0x1801a39c4  movzx   r14d, r12w
0x1801a39c8  jmp     short loc_1801A39CD
0x1801a39ca  mov     r14d, edi
0x1801a39cd  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801a39d2  call    cs:__imp_GetSystemTimeAsFileTime
0x1801a39d9  nop     dword ptr [rax+rax+00h]
0x1801a39de  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x1801a39e2  lea     rdx, [rbp+3Fh+var_90]
0x1801a39e6  mov     r10, [rsp+130h+var_E0]
0x1801a39eb  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x1801a39ee  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x1801a39f2  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x1801a39f5  or      eax, 0FFFFFFFFh
0x1801a39f8  mov     dword ptr [rbp+3Fh+var_70], eax
0x1801a39fb  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x1801a39fe  mov     dword ptr [rbp+3Fh+var_60], eax
0x1801a3a01  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x1801a3a04  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x1801a3a07  mov     dword ptr [rbp+3Fh+var_50], eax
0x1801a3a0a  mov     eax, edi
0x1801a3a0c  mov     [rbp+3Fh+arg_0], eax
0x1801a3a0f  mov     [rbp+3Fh+var_36], ax
0x1801a3a13  mov     rax, [r10+10h]
0x1801a3a17  mov     rcx, rax
0x1801a3a1a  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x1801a3a1e  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x1801a3a22  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x1801a3a25  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x1801a3a29  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x1801a3a2d  mov     qword ptr [rbp+3Fh+var_90+8], rsi
0x1801a3a31  mov     word ptr [rbp+3Fh+var_90], bx
0x1801a3a35  mov     [rsp+130h+var_C0], rax
0x1801a3a3a  mov     word ptr [rbp+3Fh+var_90+2], bx
0x1801a3a3e  call    ORGetCompressedLength
0x1801a3a43  movzx   esi, ax
0x1801a3a46  mov     [rbp+3Fh+var_38], si
0x1801a3a4a  cmp     rsi, rbx
0x1801a3a4d  jnb     short loc_1801A3A56
0x1801a3a4f  or      r14w, 20h
0x1801a3a54  jmp     short loc_1801A3A5F
0x1801a3a56  mov     eax, 0FFDFh
0x1801a3a5b  and     r14w, ax
0x1801a3a5f  mov     rdx, r13
0x1801a3a62  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x1801a3a67  mov     rcx, r10
0x1801a3a6a  call    ORAllocNode
0x1801a3a6f  xor     r10d, r10d
0x1801a3a72  mov     rdi, rax
0x1801a3a75  test    rax, rax
0x1801a3a78  jnz     short loc_1801A3A82
0x1801a3a7a  lea     ebx, [rax+8]
0x1801a3a7d  jmp     loc_1801A3D3A
0x1801a3a82  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x1801a3a86  mov     r15, r10
0x1801a3a89  test    rbx, rbx
0x1801a3a8c  jz      short loc_1801A3AC1
0x1801a3a8e  mov     rcx, rbx; pSecurityDescriptor
0x1801a3a91  call    cs:__imp_IsValidSecurityDescriptor
0x1801a3a98  nop     dword ptr [rax+rax+00h]
0x1801a3a9d  test    eax, eax
0x1801a3a9f  jnz     short loc_1801A3AAB
0x1801a3aa1  mov     ebx, 53Ah
0x1801a3aa6  jmp     loc_1801A3D0B
0x1801a3aab  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x1801a3aaf  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1801a3ab2  call    ORMakeSDRelative
0x1801a3ab7  mov     ebx, eax
0x1801a3ab9  test    eax, eax
0x1801a3abb  jnz     loc_1801A3D0B
0x1801a3ac1  mov     rax, [r13+60h]
0x1801a3ac5  xor     ebx, ebx
0x1801a3ac7  mov     rdx, [rbp+3Fh+CreatorDescriptor]; CreatorDescriptor
0x1801a3acb  mov     r10, [rax+10h]
0x1801a3acf  test    rdx, rdx
0x1801a3ad2  jz      short loc_1801A3AE1
0x1801a3ad4  test    byte ptr [rdx+2], 4
0x1801a3ad8  jz      short loc_1801A3AE1
0x1801a3ada  mov     eax, 1078h
0x1801a3adf  jmp     short loc_1801A3AF8
0x1801a3ae1  movzx   eax, word ptr [r10+16h]
0x1801a3ae6  and     eax, 400h
0x1801a3aeb  or      eax, 41E000h
0x1801a3af0  shr     eax, 0Ah
0x1801a3af3  test    rdx, rdx
0x1801a3af6  jz      short loc_1801A3AFE
0x1801a3af8  test    [rdx+2], r12b
0x1801a3afc  jnz     short loc_1801A3B0D
0x1801a3afe  mov     ecx, 800h
0x1801a3b03  test    [r10+16h], cx
0x1801a3b08  jz      short loc_1801A3B0D
0x1801a3b0a  or      eax, 2
0x1801a3b0d  lea     rcx, CmKeyMapping
0x1801a3b14  xor     r9d, r9d; ObjectTypes
0x1801a3b17  mov     [rsp+130h+GenericMapping], rcx; GenericMapping
0x1801a3b1c  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x1801a3b20  mov     [rsp+130h+Token], rbx; Token
0x1801a3b25  lea     rcx, [r10+14h]; ParentDescriptor
0x1801a3b29  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x1801a3b2d  mov     rax, qword ptr [rsp+130h+var_C8]
0x1801a3b32  mov     [rsp+130h+IsContainerObject], eax; IsContainerObject
0x1801a3b36  mov     [rsp+130h+GuidCount], ebx; GuidCount
0x1801a3b3a  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x1801a3b41  nop     dword ptr [rax+rax+00h]
0x1801a3b46  test    eax, eax
0x1801a3b48  jnz     short loc_1801A3B60
0x1801a3b4a  call    cs:__imp_GetLastError
0x1801a3b51  nop     dword ptr [rax+rax+00h]
0x1801a3b56  mov     ebx, eax
0x1801a3b58  test    eax, eax
0x1801a3b5a  jnz     loc_1801A3D0B
0x1801a3b60  mov     rdx, [rbp+3Fh+NewDescriptor]
0x1801a3b64  lea     r8, [rbp+3Fh+var_A8]
0x1801a3b68  mov     rcx, [rsp+130h+var_E0]
0x1801a3b6d  call    ORProcessSecurityDescriptor
0x1801a3b72  mov     ebx, eax
0x1801a3b74  test    eax, eax
0x1801a3b76  jnz     loc_1801A3D0B
0x1801a3b7c  mov     rax, [rbp+3Fh+var_A8]
0x1801a3b80  xor     ebx, ebx
0x1801a3b82  mov     [rdi+60h], rax
0x1801a3b86  mov     rcx, [rax+10h]
0x1801a3b8a  mov     rax, qword ptr [rsp+130h+var_C8]
0x1801a3b8f  add     [rcx+0Ch], eax
0x1801a3b92  mov     rcx, [rbp+3Fh+Src]
0x1801a3b96  test    rcx, rcx
0x1801a3b99  jz      short loc_1801A3BEB
0x1801a3b9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a3b9f  inc     rax
0x1801a3ba2  cmp     [rcx+rax*2], bx
0x1801a3ba6  jnz     short loc_1801A3B9F
0x1801a3ba8  add     rax, rax
0x1801a3bab  cmp     rax, 0FFFFh
  ... truncated ...
```
