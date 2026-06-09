# FaxSendDocumentInternalW(void *,ushort const * * const,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,ulong,_FAX_PERSONAL_PROFILEW const *,_FAX_JOB_PARAM_EXW const *,ulong *,unsigned __int64 *,unsigned __int64 *,int *)

- ea: `0x180019d54`
- end: `0x18001a35f`
- name: `?FaxSendDocumentInternalW@@YAHPEAXQEAPEBGKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@K3PEBU_FAX_JOB_PARAM_EXW@@PEAKPEA_K6PEAH@Z`
- size: `1547`
- prototype: `__int64 __fastcall(_QWORD **, const unsigned __int16 **const, unsigned int, const struct _FAX_COVERPAGE_INFO_EXW *, const struct _FAX_PERSONAL_PROFILEW *, unsigned int, const struct _FAX_PERSONAL_PROFILEW *, const struct _FAX_JOB_PARAM_EXW *, unsigned int *, unsigned __int64 *, unsigned __int64 *, int *)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180018a10`
- `0x1800190d0`
- `0x180020570`
- `0x180020830`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180016124`
- `0x180019d54`
- `0x18001a82c`
- `0x18001ad28`
- `0x18001b010`
- `0x18001ba58`
- `0x180021530`
- `0x18002161c`
- `0x18002bb58`
- `0x18003cf48`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180019f87`
- `KERNEL32!DeleteFileW` at `0x180019f87`
- `KERNEL32!SetLastError` at `0x180019fdf`
- `KERNEL32!SetLastError` at `0x180019fdf`
- `KERNEL32!GetLastError` at `0x180019eb5`
- `KERNEL32!GetLastError` at `0x180019fae`
- `KERNEL32!GetLastError` at `0x180019eb5`
- `KERNEL32!GetLastError` at `0x180019fae`

## pseudocode

```c
__int64 __fastcall FaxSendDocumentInternalW(
        _QWORD **a1,
        const unsigned __int16 **const a2,
        unsigned int a3,
        const struct _FAX_COVERPAGE_INFO_EXW *a4,
        const struct _FAX_PERSONAL_PROFILEW *a5,
        unsigned int a6,
        const struct _FAX_PERSONAL_PROFILEW *a7,
        const struct _FAX_JOB_PARAM_EXW *a8,
        unsigned int *a9,
        unsigned __int64 *a10,
        unsigned __int64 *a11,
        int *a12)
{
  void *v13; // rbx
  unsigned int v14; // edi
  unsigned __int16 *v15; // r15
  unsigned int v16; // r8d
  const unsigned __int16 **v17; // r12
  unsigned int LastError; // ebx
  unsigned __int16 *v19; // rax
  int v20; // edx
  int v21; // ecx
  char v22; // al
  __int64 v24; // r9
  unsigned int v25; // r9d
  const unsigned __int16 *v26; // r9
  unsigned __int16 *v27; // r13
  unsigned int v28; // eax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // r8
  unsigned int v33; // [rsp+28h] [rbp-790h]
  _OWORD v38[2]; // [rsp+B8h] [rbp-700h] BYREF
  __int64 v39; // [rsp+D8h] [rbp-6E0h]
  _BYTE v40[32]; // [rsp+E0h] [rbp-6D8h] BYREF
  LPVOID lpMem; // [rsp+100h] [rbp-6B8h]
  LPVOID v42; // [rsp+130h] [rbp-688h]
  unsigned __int16 v43[264]; // [rsp+140h] [rbp-678h] BYREF
  unsigned __int16 v44[264]; // [rsp+350h] [rbp-468h] BYREF
  unsigned __int16 v45[264]; // [rsp+560h] [rbp-258h] BYREF

  v13 = a1;
  memset_0(v40, 0, 0x60u);
  memset(v38, 0, sizeof(v38));
  v39 = 0;
  v14 = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
  }
  v16 = a3;
  v17 = a2;
  if ( !(unsigned int)ValidateFaxSendDocumentParams(v13, a2, v16, a4, a5, a8, 0x20000u, a12) )
  {
    LastError = GetLastError();
    goto LABEL_14;
  }
  if ( !a6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    }
LABEL_12:
    LastError = 87;
    goto LABEL_13;
  }
  v24 = 0;
  do
  {
    if ( !*((_QWORD *)a7 + 17 * (unsigned int)v24 + 2) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v24);
      }
      goto LABEL_12;
    }
    v24 = (unsigned int)(v24 + 1);
  }
  while ( (unsigned int)v24 < a6 );
  if ( a3 )
  {
    memset_0(v43, 0, 0x208u);
    LastError = ProcessSendDocumentBodyFile(a2, a3, v43, v25, v44, v33, v13, a12);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( !a12 || *a12 == -1 )
        {
          v26 = &qword_1800435E8;
          v17 = a2;
        }
        else
        {
          v17 = a2;
          v26 = a2[*a12];
        }
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          173,
          (unsigned int)&WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
          (_DWORD)v26,
          LastError);
        goto LABEL_14;
      }
LABEL_13:
      v17 = a2;
      goto LABEL_14;
    }
    v15 = v43;
    v27 = v44;
    v13 = a1;
  }
  else
  {
    LODWORD(v27) = 0;
  }
  v28 = ProcessSendDocumentCoverPage(a4, (struct _FAX_COVERPAGE_INFO_EXW *)v38, v45, v24, v13);
  LastError = v28;
  if ( v28 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v30 = 174;
LABEL_53:
    WPP_SF_d(v29[2], v30, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v28);
    goto LABEL_13;
  }
  v28 = ProcessSendDocumentJobParams(a8, (struct _FAX_JOB_PARAM_EXW *)v40);
  LastError = v28;
  if ( v28 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v30 = 175;
    goto LABEL_53;
  }
  LastError = FAX_SendDocumentEx(
                *a1[4],
                (_DWORD)v27,
                (unsigned int)v38,
                (_DWORD)a5,
                a6,
                (__int64)a7,
                (__int64)v40,
                (__int64)a9,
                (__int64)a10,
                (__int64)a11);
  v17 = a2;
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
      goto LABEL_13;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, LastError);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v32, *a10);
    }
    LastError = 0;
  }
LABEL_14:
  pMemFree(lpMem);
  pMemFree(v42);
  if ( v15 )
  {
    v19 = v15;
    do
    {
      v20 = *(unsigned __int16 *)((char *)v19 + (char *)*v17 - (char *)v15);
      v21 = *v19 - v20;
      if ( v21 )
        break;
      ++v19;
    }
    while ( v20 );
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v15);
      }
      if ( !DeleteFileW(v15)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          180,
          (unsigned int)&WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
          (_DWORD)v15,
          v22);
      }
    }
  }
  SetLastError(LastError);
  LOBYTE(v14) = LastError == 0;
  return v14;
}

```

## disassembly

```asm
0x180019d54  push    rbx
0x180019d56  push    rsi
0x180019d57  push    rdi
0x180019d58  push    r12
0x180019d5a  push    r13
0x180019d5c  push    r14
0x180019d5e  push    r15
0x180019d60  sub     rsp, 780h
0x180019d67  mov     rax, cs:__security_cookie
0x180019d6e  xor     rax, rsp
0x180019d71  mov     [rsp+7B8h+var_48], rax
0x180019d79  mov     [rsp+7B8h+var_750], r9
0x180019d7e  mov     r12d, r8d
0x180019d81  mov     [rsp+7B8h+var_760], r8d
0x180019d86  mov     [rsp+7B8h+var_768], rdx
0x180019d8b  mov     rbx, rcx
0x180019d8e  mov     [rsp+7B8h+var_740], rcx
0x180019d93  mov     [rsp+7B8h+var_710], rdx
0x180019d9b  mov     rax, [rsp+7B8h+arg_20]
0x180019da3  mov     [rsp+7B8h+var_730], rax
0x180019dab  mov     rax, [rsp+7B8h+arg_30]
0x180019db3  mov     [rsp+7B8h+var_738], rax
0x180019dbb  mov     rax, [rsp+7B8h+arg_38]
0x180019dc3  mov     [rsp+7B8h+var_748], rax
0x180019dc8  mov     rax, [rsp+7B8h+arg_40]
0x180019dd0  mov     [rsp+7B8h+var_718], rax
0x180019dd8  mov     rax, [rsp+7B8h+arg_48]
0x180019de0  mov     [rsp+7B8h+var_728], rax
0x180019de8  mov     [rsp+7B8h+var_708], rax
0x180019df0  mov     rax, [rsp+7B8h+arg_50]
0x180019df8  mov     [rsp+7B8h+var_720], rax
0x180019e00  mov     r13, [rsp+7B8h+arg_58]
0x180019e08  xor     edx, edx; Val
0x180019e0a  lea     r8d, [rdx+60h]; Size
0x180019e0e  lea     rcx, [rsp+7B8h+var_6D8]; void *
0x180019e16  call    memset_0
0x180019e1b  xorps   xmm0, xmm0
0x180019e1e  xor     eax, eax
0x180019e20  movups  [rsp+7B8h+var_700], xmm0
0x180019e28  movups  [rsp+7B8h+var_6F0], xmm0
0x180019e30  mov     [rsp+7B8h+var_6E0], rax
0x180019e38  xor     edi, edi
0x180019e3a  mov     r15d, edi
0x180019e3d  lea     r14, WPP_GLOBAL_Control
0x180019e44  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e4b  mov     esi, 1000h
0x180019e50  cmp     rcx, r14
0x180019e53  jz      short loc_180019E75
0x180019e55  test    [rcx+1Ch], esi
0x180019e58  jz      short loc_180019E75
0x180019e5a  cmp     byte ptr [rcx+19h], 5
0x180019e5e  jb      short loc_180019E75
0x180019e60  mov     edx, 0AAh
0x180019e65  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180019e6c  mov     rcx, [rcx+10h]
0x180019e70  call    WPP_SF_
0x180019e75  mov     [rsp+7B8h+var_780], r13; int *
0x180019e7a  mov     dword ptr [rsp+7B8h+var_788], 20000h; unsigned int
0x180019e82  mov     rax, [rsp+7B8h+var_748]
0x180019e87  mov     [rsp+7B8h+var_790], rax; unsigned int
0x180019e8c  mov     rax, [rsp+7B8h+var_730]
0x180019e94  mov     [rsp+7B8h+var_798], rax; struct _FAX_PERSONAL_PROFILEW *
0x180019e99  mov     r9, [rsp+7B8h+var_750]; struct _FAX_COVERPAGE_INFO_EXW *
0x180019e9e  mov     r8d, r12d; unsigned int
0x180019ea1  mov     r12, [rsp+7B8h+var_768]
0x180019ea6  mov     rdx, r12; unsigned __int16 **
0x180019ea9  mov     rcx, rbx; void *
0x180019eac  call    ?ValidateFaxSendDocumentParams@@YAHPEAXQEAPEBGKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@PEBU_FAX_JOB_PARAM_EXW@@KPEAH@Z; ValidateFaxSendDocumentParams(void *,ushort const * * const,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_JOB_PARAM_EXW const *,ulong,int *)
0x180019eb1  test    eax, eax
0x180019eb3  jnz     short loc_180019EC5
0x180019eb5  call    cs:__imp_GetLastError
0x180019ebc  nop     dword ptr [rax+rax+00h]
0x180019ec1  mov     ebx, eax
0x180019ec3  jmp     short loc_180019F0C
0x180019ec5  mov     r12d, [rsp+7B8h+arg_28]
0x180019ecd  test    r12d, r12d
0x180019ed0  jnz     loc_18001A017
0x180019ed6  mov     rcx, cs:WPP_GLOBAL_Control
0x180019edd  cmp     rcx, r14
0x180019ee0  jz      short loc_180019F02
0x180019ee2  test    [rcx+1Ch], esi
0x180019ee5  jz      short loc_180019F02
0x180019ee7  cmp     byte ptr [rcx+19h], 2
0x180019eeb  jb      short loc_180019F02
0x180019eed  mov     edx, 0ABh
0x180019ef2  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180019ef9  mov     rcx, [rcx+10h]
0x180019efd  call    WPP_SF_
0x180019f02  mov     ebx, 57h ; 'W'
0x180019f07  mov     r12, [rsp+7B8h+var_768]
0x180019f0c  mov     rcx, [rsp+7B8h+lpMem]; lpMem
0x180019f14  call    pMemFree
0x180019f19  mov     rcx, [rsp+7B8h+var_688]; lpMem
0x180019f21  call    pMemFree
0x180019f26  test    r15, r15
0x180019f29  jz      loc_180019FDD
0x180019f2f  mov     rax, r15
0x180019f32  mov     r8, [r12]
0x180019f36  sub     r8, r15
0x180019f39  movzx   ecx, word ptr [rax]
0x180019f3c  movzx   edx, word ptr [rax+r8]
0x180019f41  sub     ecx, edx
0x180019f43  jnz     short loc_180019F4D
0x180019f45  add     rax, 2
0x180019f49  test    edx, edx
0x180019f4b  jnz     short loc_180019F39
0x180019f4d  test    ecx, ecx
0x180019f4f  jz      loc_180019FDD
0x180019f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f5c  cmp     rcx, r14
0x180019f5f  jz      short loc_180019F84
0x180019f61  test    [rcx+1Ch], esi
0x180019f64  jz      short loc_180019F84
0x180019f66  cmp     byte ptr [rcx+19h], 5
0x180019f6a  jb      short loc_180019F84
0x180019f6c  mov     edx, 0B3h
0x180019f71  mov     r9, r15
0x180019f74  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180019f7b  mov     rcx, [rcx+10h]
0x180019f7f  call    WPP_SF_S
0x180019f84  mov     rcx, r15; lpFileName
0x180019f87  call    cs:__imp_DeleteFileW
0x180019f8e  nop     dword ptr [rax+rax+00h]
0x180019f93  test    eax, eax
0x180019f95  jnz     short loc_180019FDD
0x180019f97  mov     rax, cs:WPP_GLOBAL_Control
0x180019f9e  cmp     rax, r14
0x180019fa1  jz      short loc_180019FDD
0x180019fa3  test    [rax+1Ch], esi
0x180019fa6  jz      short loc_180019FDD
0x180019fa8  cmp     byte ptr [rax+19h], 2
0x180019fac  jb      short loc_180019FDD
0x180019fae  call    cs:__imp_GetLastError
0x180019fb5  nop     dword ptr [rax+rax+00h]
0x180019fba  mov     edx, 0B4h
0x180019fbf  mov     dword ptr [rsp+7B8h+var_798], eax
0x180019fc3  mov     r9, r15
0x180019fc6  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180019fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fd4  mov     rcx, [rcx+10h]
0x180019fd8  call    WPP_SF_Sd
0x180019fdd  mov     ecx, ebx; dwErrCode
0x180019fdf  call    cs:__imp_SetLastError
0x180019fe6  nop     dword ptr [rax+rax+00h]
0x180019feb  test    ebx, ebx
0x180019fed  setz    dil
0x180019ff1  mov     eax, edi
0x180019ff3  mov     rcx, [rsp+7B8h+var_48]
0x180019ffb  xor     rcx, rsp; StackCookie
0x180019ffe  call    __security_check_cookie
0x18001a003  add     rsp, 780h
0x18001a00a  pop     r15
0x18001a00c  pop     r14
0x18001a00e  pop     r13
0x18001a010  pop     r12
0x18001a012  pop     rdi
0x18001a013  pop     rsi
0x18001a014  pop     rbx
0x18001a015  retn
0x18001a017  mov     r9d, edi
0x18001a01a  test    r12d, r12d
0x18001a01d  jz      short loc_18001A044
0x18001a01f  mov     rdx, [rsp+7B8h+var_738]
0x18001a027  mov     eax, r9d
0x18001a02a  imul    rcx, rax, 88h
0x18001a031  cmp     [rcx+rdx+10h], rdi
0x18001a036  jz      loc_18001A0D8
0x18001a03c  inc     r9d; unsigned int
0x18001a03f  cmp     r9d, r12d
0x18001a042  jb      short loc_18001A027
0x18001a044  cmp     [rsp+7B8h+var_760], edi
0x18001a048  jz      loc_18001A15B
0x18001a04e  xor     edx, edx; Val
0x18001a050  mov     r8d, 208h; Size
0x18001a056  lea     rcx, [rsp+7B8h+var_678]; void *
0x18001a05e  call    memset_0
0x18001a063  mov     [rsp+7B8h+var_780], r13; int *
0x18001a068  mov     [rsp+7B8h+var_788], rbx; void *
0x18001a06d  lea     rax, [rsp+7B8h+var_468]
0x18001a075  mov     [rsp+7B8h+var_798], rax; unsigned __int16 *
0x18001a07a  lea     r8, [rsp+7B8h+var_678]; unsigned __int16 *
0x18001a082  mov     edx, [rsp+7B8h+var_760]; unsigned int
0x18001a086  mov     rcx, [rsp+7B8h+var_768]; unsigned __int16 **
0x18001a08b  call    ?ProcessSendDocumentBodyFile@@YAKQEAPEBGKPEAGK1KPEAXPEAH@Z; ProcessSendDocumentBodyFile(ushort const * * const,ulong,ushort *,ulong,ushort *,ulong,void *,int *)
0x18001a090  mov     ebx, eax
0x18001a092  test    eax, eax
0x18001a094  jz      loc_18001A13F
0x18001a09a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0a1  cmp     rcx, r14
0x18001a0a4  jz      loc_180019F07
0x18001a0aa  test    [rcx+1Ch], esi
0x18001a0ad  jz      loc_180019F07
0x18001a0b3  cmp     byte ptr [rcx+19h], 2
0x18001a0b7  jb      loc_180019F07
0x18001a0bd  test    r13, r13
0x18001a0c0  jz      short loc_18001A115
0x18001a0c2  cmp     dword ptr [r13+0], 0FFFFFFFFh
0x18001a0c7  jz      short loc_18001A115
0x18001a0c9  movsxd  rax, dword ptr [r13+0]
0x18001a0cd  mov     r12, [rsp+7B8h+var_768]
0x18001a0d2  mov     r9, [r12+rax*8]
0x18001a0d6  jmp     short loc_18001A121
0x18001a0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0df  cmp     rcx, r14
0x18001a0e2  jz      loc_180019F02
0x18001a0e8  test    [rcx+1Ch], esi
0x18001a0eb  jz      loc_180019F02
0x18001a0f1  cmp     byte ptr [rcx+19h], 2
0x18001a0f5  jb      loc_180019F02
0x18001a0fb  mov     edx, 0ACh
0x18001a100  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001a107  mov     rcx, [rcx+10h]
0x18001a10b  call    WPP_SF_d
0x18001a110  jmp     loc_180019F02
0x18001a115  lea     r9, qword_1800435E8
0x18001a11c  mov     r12, [rsp+7B8h+var_768]
0x18001a121  mov     edx, 0ADh
0x18001a126  mov     dword ptr [rsp+7B8h+var_798], ebx
0x18001a12a  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001a131  mov     rcx, [rcx+10h]
0x18001a135  call    WPP_SF_Sd
0x18001a13a  jmp     loc_180019F0C
0x18001a13f  lea     r15, [rsp+7B8h+var_678]
0x18001a147  mov     qword ptr [rsp+7B8h+var_760], r15
0x18001a14c  lea     r13, [rsp+7B8h+var_468]
0x18001a154  mov     rbx, [rsp+7B8h+var_740]
0x18001a159  jmp     short loc_18001A163
0x18001a15b  mov     qword ptr [rsp+7B8h+var_760], rdi
0x18001a160  mov     r13, rdi
0x18001a163  mov     [rsp+7B8h+var_798], rbx; void *
0x18001a168  lea     r8, [rsp+7B8h+var_258]; unsigned __int16 *
0x18001a170  lea     rdx, [rsp+7B8h+var_700]; struct _FAX_COVERPAGE_INFO_EXW *
0x18001a178  mov     rcx, [rsp+7B8h+var_750]; struct _FAX_COVERPAGE_INFO_EXW *
0x18001a17d  call    ?ProcessSendDocumentCoverPage@@YAKPEBU_FAX_COVERPAGE_INFO_EXW@@PEAU1@PEAGKPEAX@Z; ProcessSendDocumentCoverPage(_FAX_COVERPAGE_INFO_EXW const *,_FAX_COVERPAGE_INFO_EXW *,ushort *,ulong,void *)
0x18001a182  mov     ebx, eax
0x18001a184  test    eax, eax
0x18001a186  jz      short loc_18001A1C8
0x18001a188  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a18f  cmp     rcx, r14
0x18001a192  jz      loc_180019F07
0x18001a198  test    [rcx+1Ch], esi
0x18001a19b  jz      loc_180019F07
0x18001a1a1  cmp     byte ptr [rcx+19h], 2
0x18001a1a5  jb      loc_180019F07
0x18001a1ab  mov     edx, 0AEh
0x18001a1b0  mov     r9d, eax
0x18001a1b3  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001a1ba  mov     rcx, [rcx+10h]
0x18001a1be  call    WPP_SF_d
0x18001a1c3  jmp     loc_180019F07
0x18001a1c8  lea     rdx, [rsp+7B8h+var_6D8]; struct _FAX_JOB_PARAM_EXW *
0x18001a1d0  mov     rcx, [rsp+7B8h+var_748]; struct _FAX_JOB_PARAM_EXW *
0x18001a1d5  call    ?ProcessSendDocumentJobParams@@YAKPEBU_FAX_JOB_PARAM_EXW@@PEAU1@@Z; ProcessSendDocumentJobParams(_FAX_JOB_PARAM_EXW const *,_FAX_JOB_PARAM_EXW *)
0x18001a1da  mov     ebx, eax
0x18001a1dc  test    eax, eax
0x18001a1de  jz      short loc_18001A20A
0x18001a1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1e7  cmp     rcx, r14
0x18001a1ea  jz      loc_180019F07
0x18001a1f0  test    [rcx+1Ch], esi
0x18001a1f3  jz      loc_180019F07
0x18001a1f9  cmp     byte ptr [rcx+19h], 2
0x18001a1fd  jb      loc_180019F07
0x18001a203  mov     edx, 0AFh
0x18001a208  jmp     short loc_18001A1B0
0x18001a20a  mov     rcx, [rsp+7B8h+var_740]
0x18001a20f  mov     rcx, [rcx+20h]
0x18001a213  mov     rax, [rsp+7B8h+var_720]
0x18001a21b  mov     [rsp+7B8h+var_770], rax
0x18001a220  mov     rax, [rsp+7B8h+var_728]
0x18001a228  mov     [rsp+7B8h+var_778], rax
0x18001a22d  mov     rax, [rsp+7B8h+var_718]
0x18001a235  mov     [rsp+7B8h+var_780], rax
0x18001a23a  lea     rax, [rsp+7B8h+var_6D8]
0x18001a242  mov     [rsp+7B8h+var_788], rax
0x18001a247  mov     rax, [rsp+7B8h+var_738]
0x18001a24f  mov     [rsp+7B8h+var_790], rax
0x18001a254  mov     dword ptr [rsp+7B8h+var_798], r12d
0x18001a259  mov     r9, [rsp+7B8h+var_730]
0x18001a261  lea     r8, [rsp+7B8h+var_700]
0x18001a269  mov     rdx, r13
0x18001a26c  mov     rcx, [rcx]
0x18001a26f  call    FAX_SendDocumentEx
0x18001a274  mov     ebx, eax
0x18001a276  mov     [rsp+7B8h+var_758], eax
0x18001a27a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a281  mov     rax, [rsp+7B8h+var_728]
0x18001a289  mov     r12, [rsp+7B8h+var_768]
0x18001a28e  jmp     short loc_18001A2FF
0x18001a290  mov     ebx, eax
0x18001a292  mov     [rsp+7B8h+var_758], eax
0x18001a296  lea     rax, WPP_GLOBAL_Control
0x18001a29d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2a4  cmp     rcx, rax
0x18001a2a7  jz      short loc_18001A2D7
0x18001a2a9  test    dword ptr [rcx+1Ch], 1000h
0x18001a2b0  jz      short loc_18001A2D7
0x18001a2b2  cmp     byte ptr [rcx+19h], 2
0x18001a2b6  jb      short loc_18001A2D7
0x18001a2b8  mov     edx, 0B0h
  ... truncated ...
```
