# FaxSendDocumentForBroadcastInternal(void *,ushort const *,ulong *,int,int (*)(void *,ulong,void *,_FAX_JOB_PARAMW *,_FAX_COVERPAGE_INFOW *),void *)

- ea: `0x180018a10`
- end: `0x1800190c8`
- name: `?FaxSendDocumentForBroadcastInternal@@YAHPEAXPEBGPEAKHP6AH0K0PEAU_FAX_JOB_PARAMW@@PEAU_FAX_COVERPAGE_INFOW@@@Z0@Z`
- size: `1720`
- prototype: `__int64 __fastcall(_DWORD *, LPCWCH lpWideCharStr, unsigned int *, int, int (*)(void *, unsigned int, void *, struct _FAX_JOB_PARAMW *, struct _FAX_COVERPAGE_INFOW *), void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1800206d0`
- `0x180020800`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180016424`
- `0x1800166c4`
- `0x180018a10`
- `0x180019d54`
- `0x18001a6f8`
- `0x18002bb58`
- `0x18002c890`
- `0x18003d4ca`
- `0x18003d510`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180018c59`
- `KERNEL32!GetFullPathNameW` at `0x180018c59`
- `KERNEL32!GetFileAttributesW` at `0x180018c7b`
- `KERNEL32!GetFileAttributesW` at `0x180018c7b`
- `KERNEL32!SetLastError` at `0x180018b62`
- `KERNEL32!SetLastError` at `0x180018bad`
- `KERNEL32!SetLastError` at `0x180018c03`
- `KERNEL32!SetLastError` at `0x180018c91`
- `KERNEL32!SetLastError` at `0x18001904f`
- `KERNEL32!SetLastError` at `0x180018b62`
- `KERNEL32!SetLastError` at `0x180018bad`
- `KERNEL32!SetLastError` at `0x180018c03`
- `KERNEL32!SetLastError` at `0x180018c91`
- `KERNEL32!SetLastError` at `0x18001904f`
- `KERNEL32!GetLastError` at `0x180018d8c`
- `KERNEL32!GetLastError` at `0x180018f5c`
- `KERNEL32!GetLastError` at `0x180018fba`
- `KERNEL32!GetLastError` at `0x180018ffd`
- `KERNEL32!GetLastError` at `0x180019037`
- `KERNEL32!GetLastError` at `0x180018d8c`
- `KERNEL32!GetLastError` at `0x180018f5c`
- `KERNEL32!GetLastError` at `0x180018fba`
- `KERNEL32!GetLastError` at `0x180018ffd`
- `KERNEL32!GetLastError` at `0x180019037`

## pseudocode

```c
__int64 __fastcall FaxSendDocumentForBroadcastInternal(
        _DWORD *a1,
        LPCWCH lpWideCharStr,
        unsigned int *a3,
        int a4,
        int (*a5)(void *, unsigned int, void *, struct _FAX_JOB_PARAMW *, struct _FAX_COVERPAGE_INFOW *),
        void *a6)
{
  unsigned int v9; // r12d
  void *v10; // rsi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  DWORD FullPathNameW; // ebx
  DWORD v14; // ecx
  unsigned int v15; // ebx
  DWORD v16; // eax
  __int64 v17; // rdx
  DWORD v18; // eax
  DWORD LastError; // eax
  DWORD v20; // eax
  unsigned int v23; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR FilePart; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  LPVOID lpMem[2]; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v28[2]; // [rsp+90h] [rbp-70h]
  LPVOID v29; // [rsp+A0h] [rbp-60h]
  _BYTE v30[144]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[144]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v32[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  LPVOID v33; // [rsp+1F0h] [rbp+F0h]
  LPVOID v34; // [rsp+220h] [rbp+120h]
  _FAX_JOB_PARAMA v35; // [rsp+230h] [rbp+130h] BYREF
  struct _FAX_JOB_PARAMW v36; // [rsp+2C0h] [rbp+1C0h] BYREF
  _FAX_COVERPAGE_INFOA v37; // [rsp+350h] [rbp+250h] BYREF
  struct _FAX_COVERPAGE_INFOW v38; // [rsp+440h] [rbp+340h] BYREF
  WCHAR Buffer[264]; // [rsp+530h] [rbp+430h] BYREF

  v23 = 0;
  v26 = 0;
  v24 = 0;
  v9 = 0;
  v10 = 0;
  memset_0(&v35, 0, sizeof(v35));
  memset_0(&v37, 0, sizeof(v37));
  memset_0(&v36, 0, sizeof(v36));
  memset_0(&v38, 0, sizeof(v38));
  memset_0(v32, 0, 0x60u);
  v29 = 0;
  *(_OWORD *)lpMem = 0;
  *(_OWORD *)v28 = 0;
  memset_0(v30, 0, 0x88u);
  memset_0(v31, 0, 0x88u);
  FilePart = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
  }
  if ( !a1 || !*a1 || a1[4] )
  {
    SetLastError(6u);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_68;
    }
    v12 = 66;
LABEL_67:
    WPP_SF_(v11[2], v12, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    goto LABEL_68;
  }
  if ( !lpWideCharStr )
  {
    SetLastError(0x57u);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_68;
    }
    v12 = 67;
    goto LABEL_67;
  }
  if ( !a5 )
  {
    SetLastError(0x57u);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_68;
    }
    v12 = 68;
    goto LABEL_67;
  }
  v10 = (void *)UnicodeStringToAnsiString(lpWideCharStr);
  if ( !v10 )
  {
    SetLastError(8u);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_68;
    }
    v12 = 69;
    goto LABEL_67;
  }
  FullPathNameW = GetFullPathNameW(lpWideCharStr, 0x104u, Buffer, &FilePart);
  if ( FullPathNameW - 1 > 0x103 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, LastError);
    }
    if ( FullPathNameW <= 0x104 )
      v20 = GetLastError();
    else
      v20 = 111;
    v14 = v20;
    goto LABEL_26;
  }
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    v14 = 2;
LABEL_26:
    SetLastError(v14);
    goto LABEL_68;
  }
  v15 = 1;
  while ( a4 )
  {
    memset_0(&v35.SizeOfStruct + 1, 0, 0x84u);
    v35.SizeOfStruct = 136;
    memset_0(&v37.SizeOfStruct + 1, 0, 0xECu);
    v37.SizeOfStruct = 240;
    if ( !((unsigned int (__fastcall *)(_DWORD *, _QWORD, void *, _FAX_JOB_PARAMA *, _FAX_COVERPAGE_INFOA *))a5)(
            a1,
            v15,
            a6,
            &v35,
            &v37) )
      goto LABEL_54;
    if ( v35.RecipientNumber )
    {
      if ( !(unsigned int)CopyCallbackDataAnsiToNeutral(
                            &v35,
                            &v37,
                            (struct _FAX_JOB_PARAM_EXW *)v32,
                            (struct _FAX_COVERPAGE_INFO_EXW *)lpMem,
                            (struct _FAX_PERSONAL_PROFILEW *)v30,
                            (struct _FAX_PERSONAL_PROFILEW *)v31) )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v16 = GetLastError();
        v17 = 71;
        goto LABEL_36;
      }
      goto LABEL_40;
    }
LABEL_45:
    ++v15;
  }
  memset_0(&v36.SizeOfStruct + 1, 0, 0x84u);
  v36.SizeOfStruct = 136;
  memset_0(&v38.SizeOfStruct + 1, 0, 0xECu);
  v38.SizeOfStruct = 240;
  if ( !((unsigned int (__fastcall *)(_DWORD *, _QWORD, void *, struct _FAX_JOB_PARAMW *, struct _FAX_COVERPAGE_INFOW *))a5)(
          a1,
          v15,
          a6,
          &v36,
          &v38) )
  {
LABEL_54:
    v9 = 1;
    goto LABEL_68;
  }
  if ( !v36.RecipientNumber )
    goto LABEL_45;
  if ( !(unsigned int)CopyCallbackDataWideToNeutral(
                        &v36,
                        &v38,
                        (struct _FAX_JOB_PARAM_EXW *)v32,
                        (struct _FAX_COVERPAGE_INFO_EXW *)lpMem,
                        (struct _FAX_PERSONAL_PROFILEW *)v30,
                        (struct _FAX_PERSONAL_PROFILEW *)v31) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_68;
    }
    v16 = GetLastError();
    v17 = 72;
LABEL_36:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v16);
    goto LABEL_68;
  }
LABEL_40:
  if ( (unsigned int)FaxSendDocumentInternalW(
                       (_QWORD **)a1,
                       (const unsigned __int16 **const)Buffer,
                       1u,
                       (const struct _FAX_COVERPAGE_INFO_EXW *)((unsigned __int64)lpMem & -(__int64)(lpMem[1] != 0)),
                       (const struct _FAX_PERSONAL_PROFILEW *)v30,
                       1u,
                       (const struct _FAX_PERSONAL_PROFILEW *)v31,
                       (const struct _FAX_JOB_PARAM_EXW *)v32,
                       &v23,
                       &v24,
                       &v26,
                       0) )
  {
    if ( v15 == 1 && a3 )
      *a3 = v24;
    pMemFree(lpMem[1]);
    pMemFree(v28[1]);
    pMemFree(v29);
    pMemFree(v33);
    pMemFree(v34);
    FreePersonalProfileStrings((struct _FAX_PERSONAL_PROFILEW *)v30);
    FreePersonalProfileStrings((struct _FAX_PERSONAL_PROFILEW *)v31);
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v18);
  }
LABEL_68:
  pMemFree(v10);
  return v9;
}

```

## disassembly

```asm
0x180018a10  mov     [rsp-8+arg_18], rbx
0x180018a15  push    rbp
0x180018a16  push    rsi
0x180018a17  push    rdi
0x180018a18  push    r12
0x180018a1a  push    r13
0x180018a1c  push    r14
0x180018a1e  push    r15
0x180018a20  lea     rbp, [rsp-650h]
0x180018a28  sub     rsp, 750h
0x180018a2f  mov     rax, cs:__security_cookie
0x180018a36  xor     rax, rsp
0x180018a39  mov     [rbp+680h+var_40], rax
0x180018a40  mov     r14, [rbp+680h+arg_20]
0x180018a47  xor     eax, eax
0x180018a49  mov     r13, [rbp+680h+arg_28]
0x180018a50  mov     r15, r8
0x180018a53  mov     rbx, rdx
0x180018a56  mov     [rsp+780h+var_71C], eax
0x180018a5a  mov     rdi, rcx
0x180018a5d  mov     [rsp+780h+var_708], rax
0x180018a62  xor     edx, edx; Val
0x180018a64  mov     [rsp+780h+var_718], rax
0x180018a69  mov     r8d, 88h; Size
0x180018a6f  mov     [rsp+780h+var_720], r9d
0x180018a74  lea     rcx, [rbp+680h+var_550]; void *
0x180018a7b  mov     r12d, eax
0x180018a7e  mov     esi, eax
0x180018a80  call    memset_0
0x180018a85  xor     edx, edx; Val
0x180018a87  lea     rcx, [rbp+680h+var_430]; void *
0x180018a8e  mov     r8d, 0F0h; Size
0x180018a94  call    memset_0
0x180018a99  xor     edx, edx; Val
0x180018a9b  lea     rcx, [rbp+680h+var_4C0]; void *
0x180018aa2  mov     r8d, 88h; Size
0x180018aa8  call    memset_0
0x180018aad  xor     edx, edx; Val
0x180018aaf  lea     rcx, [rbp+680h+var_340]; void *
0x180018ab6  mov     r8d, 0F0h; Size
0x180018abc  call    memset_0
0x180018ac1  xor     edx, edx; Val
0x180018ac3  lea     r8d, [rsi+60h]; Size
0x180018ac7  lea     rcx, [rbp+680h+var_5B0]; void *
0x180018ace  call    memset_0
0x180018ad3  xorps   xmm0, xmm0
0x180018ad6  lea     rcx, [rbp+680h+var_6D0]; void *
0x180018ada  xor     eax, eax
0x180018adc  xor     edx, edx; Val
0x180018ade  mov     r8d, 88h; Size
0x180018ae4  mov     [rbp+680h+var_6E0], rax
0x180018ae8  movups  xmmword ptr [rbp+680h+lpMem], xmm0
0x180018aec  movups  xmmword ptr [rbp+680h+var_6F0], xmm0
0x180018af0  call    memset_0
0x180018af5  xor     edx, edx; Val
0x180018af7  lea     rcx, [rbp+680h+var_640]; void *
0x180018afb  mov     r8d, 88h; Size
0x180018b01  call    memset_0
0x180018b06  mov     [rsp+780h+FilePart], rsi
0x180018b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b12  lea     rax, WPP_GLOBAL_Control
0x180018b19  cmp     rcx, rax
0x180018b1c  jz      short loc_180018B40
0x180018b1e  test    dword ptr [rcx+1Ch], 1000h
0x180018b25  jz      short loc_180018B40
0x180018b27  cmp     byte ptr [rcx+19h], 5
0x180018b2b  jb      short loc_180018B40
0x180018b2d  mov     rcx, [rcx+10h]
0x180018b31  lea     edx, [rsi+41h]
0x180018b34  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180018b3b  call    WPP_SF_
0x180018b40  test    rdi, rdi
0x180018b43  jz      loc_18001904A
0x180018b49  cmp     [rdi], esi
0x180018b4b  jz      loc_18001904A
0x180018b51  cmp     [rdi+10h], esi
0x180018b54  jnz     loc_18001904A
0x180018b5a  test    rbx, rbx
0x180018b5d  jnz     short loc_180018BA4
0x180018b5f  lea     ecx, [rbx+57h]; dwErrCode
0x180018b62  call    cs:__imp_SetLastError
0x180018b69  nop     dword ptr [rax+rax+00h]
0x180018b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b75  lea     rdx, WPP_GLOBAL_Control
0x180018b7c  cmp     rcx, rdx
0x180018b7f  jz      loc_180019092
0x180018b85  test    dword ptr [rcx+1Ch], 1000h
0x180018b8c  jz      loc_180019092
0x180018b92  cmp     byte ptr [rcx+19h], 2
0x180018b96  jb      loc_180019092
0x180018b9c  lea     edx, [rbx+43h]
0x180018b9f  jmp     loc_180019082
0x180018ba4  test    r14, r14
0x180018ba7  jnz     short loc_180018BF0
0x180018ba9  lea     ecx, [r14+57h]; dwErrCode
0x180018bad  call    cs:__imp_SetLastError
0x180018bb4  nop     dword ptr [rax+rax+00h]
0x180018bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bc0  lea     rdx, WPP_GLOBAL_Control
0x180018bc7  cmp     rcx, rdx
0x180018bca  jz      loc_180019092
0x180018bd0  test    dword ptr [rcx+1Ch], 1000h
0x180018bd7  jz      loc_180019092
0x180018bdd  cmp     byte ptr [rcx+19h], 2
0x180018be1  jb      loc_180019092
0x180018be7  lea     edx, [r14+44h]
0x180018beb  jmp     loc_180019082
0x180018bf0  mov     rcx, rbx; lpWideCharStr
0x180018bf3  call    UnicodeStringToAnsiString
0x180018bf8  mov     rsi, rax
0x180018bfb  test    rax, rax
0x180018bfe  jnz     short loc_180018C45
0x180018c00  lea     ecx, [rax+8]; dwErrCode
0x180018c03  call    cs:__imp_SetLastError
0x180018c0a  nop     dword ptr [rax+rax+00h]
0x180018c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c16  lea     rdx, WPP_GLOBAL_Control
0x180018c1d  cmp     rcx, rdx
0x180018c20  jz      loc_180019092
0x180018c26  test    dword ptr [rcx+1Ch], 1000h
0x180018c2d  jz      loc_180019092
0x180018c33  cmp     byte ptr [rcx+19h], 2
0x180018c37  jb      loc_180019092
0x180018c3d  lea     edx, [rsi+45h]
0x180018c40  jmp     loc_180019082
0x180018c45  lea     r9, [rsp+780h+FilePart]; lpFilePart
0x180018c4a  mov     edx, 104h; nBufferLength
0x180018c4f  lea     r8, [rbp+680h+Buffer]; lpBuffer
0x180018c56  mov     rcx, rbx; lpFileName
0x180018c59  call    cs:__imp_GetFullPathNameW
0x180018c60  nop     dword ptr [rax+rax+00h]
0x180018c65  mov     ebx, eax
0x180018c67  dec     eax
0x180018c69  cmp     eax, 103h
0x180018c6e  ja      loc_180018FDB
0x180018c74  lea     rcx, [rbp+680h+Buffer]; lpFileName
0x180018c7b  call    cs:__imp_GetFileAttributesW
0x180018c82  nop     dword ptr [rax+rax+00h]
0x180018c87  cmp     eax, 0FFFFFFFFh
0x180018c8a  jnz     short loc_180018CA2
0x180018c8c  mov     ecx, 2; dwErrCode
0x180018c91  call    cs:__imp_SetLastError
0x180018c98  nop     dword ptr [rax+rax+00h]
0x180018c9d  jmp     loc_180019092
0x180018ca2  mov     ebx, 1
0x180018ca7  xor     edx, edx; Val
0x180018ca9  mov     r8d, 84h; Size
0x180018caf  cmp     [rsp+780h+var_720], r12d
0x180018cb4  jz      loc_180018DBC
0x180018cba  lea     rcx, [rbp+680h+var_550+4]; void *
0x180018cc1  call    memset_0
0x180018cc6  xor     edx, edx; Val
0x180018cc8  mov     [rbp+680h+var_550.SizeOfStruct], 88h
0x180018cd2  mov     r8d, 0ECh; Size
0x180018cd8  lea     rcx, [rbp+680h+var_430+4]; void *
0x180018cdf  call    memset_0
0x180018ce4  lea     rax, [rbp+680h+var_430]
0x180018ceb  mov     [rbp+680h+var_430.SizeOfStruct], 0F0h
0x180018cf5  mov     [rsp+780h+var_760], rax
0x180018cfa  lea     r9, [rbp+680h+var_550]
0x180018d01  mov     rax, r14
0x180018d04  mov     r8, r13
0x180018d07  mov     edx, ebx
0x180018d09  mov     rcx, rdi
0x180018d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d11  test    eax, eax
0x180018d13  jz      loc_180018FD0
0x180018d19  cmp     [rbp+680h+var_550.RecipientNumber], r12
0x180018d20  jz      loc_180018F27
0x180018d26  lea     rax, [rbp+680h+var_640]
0x180018d2a  mov     [rsp+780h+var_758], rax; struct _FAX_PERSONAL_PROFILEW *
0x180018d2f  lea     r9, [rbp+680h+lpMem]; struct _FAX_COVERPAGE_INFO_EXW *
0x180018d33  lea     rax, [rbp+680h+var_6D0]
0x180018d37  lea     r8, [rbp+680h+var_5B0]; struct _FAX_JOB_PARAM_EXW *
0x180018d3e  mov     [rsp+780h+var_760], rax; struct _FAX_PERSONAL_PROFILEW *
0x180018d43  lea     rdx, [rbp+680h+var_430]; struct _FAX_COVERPAGE_INFOA *
0x180018d4a  lea     rcx, [rbp+680h+var_550]; struct _FAX_JOB_PARAMA *
0x180018d51  call    ?CopyCallbackDataAnsiToNeutral@@YAHPEAU_FAX_JOB_PARAMA@@PEAU_FAX_COVERPAGE_INFOA@@PEAU_FAX_JOB_PARAM_EXW@@PEAU_FAX_COVERPAGE_INFO_EXW@@PEAU_FAX_PERSONAL_PROFILEW@@4@Z; CopyCallbackDataAnsiToNeutral(_FAX_JOB_PARAMA *,_FAX_COVERPAGE_INFOA *,_FAX_JOB_PARAM_EXW *,_FAX_COVERPAGE_INFO_EXW *,_FAX_PERSONAL_PROFILEW *,_FAX_PERSONAL_PROFILEW *)
0x180018d56  test    eax, eax
0x180018d58  jnz     loc_180018E60
0x180018d5e  mov     rax, cs:WPP_GLOBAL_Control
0x180018d65  lea     rdx, WPP_GLOBAL_Control
0x180018d6c  cmp     rax, rdx
0x180018d6f  jz      loc_180019092
0x180018d75  test    dword ptr [rax+1Ch], 1000h
0x180018d7c  jz      loc_180019092
0x180018d82  cmp     byte ptr [rax+19h], 2
0x180018d86  jb      loc_180019092
0x180018d8c  call    cs:__imp_GetLastError
0x180018d93  nop     dword ptr [rax+rax+00h]
0x180018d98  mov     edx, 47h ; 'G'
0x180018d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018da4  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180018dab  mov     r9d, eax
0x180018dae  mov     rcx, [rcx+10h]
0x180018db2  call    WPP_SF_d
0x180018db7  jmp     loc_180019092
0x180018dbc  lea     rcx, [rbp+680h+var_4C0+4]; void *
0x180018dc3  call    memset_0
0x180018dc8  xor     edx, edx; Val
0x180018dca  mov     [rbp+680h+var_4C0.SizeOfStruct], 88h
0x180018dd4  mov     r8d, 0ECh; Size
0x180018dda  lea     rcx, [rbp+680h+var_340+4]; void *
0x180018de1  call    memset_0
0x180018de6  lea     rax, [rbp+680h+var_340]
0x180018ded  mov     [rbp+680h+var_340.SizeOfStruct], 0F0h
0x180018df7  mov     [rsp+780h+var_760], rax
0x180018dfc  lea     r9, [rbp+680h+var_4C0]
0x180018e03  mov     rax, r14
0x180018e06  mov     r8, r13
0x180018e09  mov     edx, ebx
0x180018e0b  mov     rcx, rdi
0x180018e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e13  test    eax, eax
0x180018e15  jz      loc_180018FD0
0x180018e1b  cmp     [rbp+680h+var_4C0.RecipientNumber], r12
0x180018e22  jz      loc_180018F27
0x180018e28  lea     rax, [rbp+680h+var_640]
0x180018e2c  mov     [rsp+780h+var_758], rax; struct _FAX_PERSONAL_PROFILEW *
0x180018e31  lea     r9, [rbp+680h+lpMem]; struct _FAX_COVERPAGE_INFO_EXW *
0x180018e35  lea     rax, [rbp+680h+var_6D0]
0x180018e39  lea     r8, [rbp+680h+var_5B0]; struct _FAX_JOB_PARAM_EXW *
0x180018e40  mov     [rsp+780h+var_760], rax; struct _FAX_PERSONAL_PROFILEW *
0x180018e45  lea     rdx, [rbp+680h+var_340]; struct _FAX_COVERPAGE_INFOW *
0x180018e4c  lea     rcx, [rbp+680h+var_4C0]; struct _FAX_JOB_PARAMW *
0x180018e53  call    ?CopyCallbackDataWideToNeutral@@YAHPEAU_FAX_JOB_PARAMW@@PEAU_FAX_COVERPAGE_INFOW@@PEAU_FAX_JOB_PARAM_EXW@@PEAU_FAX_COVERPAGE_INFO_EXW@@PEAU_FAX_PERSONAL_PROFILEW@@4@Z; CopyCallbackDataWideToNeutral(_FAX_JOB_PARAMW *,_FAX_COVERPAGE_INFOW *,_FAX_JOB_PARAM_EXW *,_FAX_COVERPAGE_INFO_EXW *,_FAX_PERSONAL_PROFILEW *,_FAX_PERSONAL_PROFILEW *)
0x180018e58  test    eax, eax
0x180018e5a  jz      loc_180018F8C
0x180018e60  mov     rax, [rbp+680h+lpMem+8]
0x180018e64  lea     rdx, [rbp+680h+Buffer]; unsigned __int16 **
0x180018e6b  neg     rax
0x180018e6e  mov     [rsp+780h+var_728], r12; int *
0x180018e73  mov     ecx, 1
0x180018e78  lea     rax, [rbp+680h+lpMem]
0x180018e7c  sbb     r9, r9
0x180018e7f  mov     r8d, ecx; unsigned int
0x180018e82  and     r9, rax; struct _FAX_COVERPAGE_INFO_EXW *
0x180018e85  lea     rax, [rsp+780h+var_708]
0x180018e8a  mov     [rsp+780h+var_730], rax; unsigned __int64 *
0x180018e8f  lea     rax, [rsp+780h+var_718]
0x180018e94  mov     [rsp+780h+var_738], rax; unsigned __int64 *
0x180018e99  lea     rax, [rsp+780h+var_71C]
0x180018e9e  mov     [rsp+780h+var_740], rax; unsigned int *
0x180018ea3  lea     rax, [rbp+680h+var_5B0]
0x180018eaa  mov     [rsp+780h+var_748], rax; struct _FAX_JOB_PARAM_EXW *
0x180018eaf  lea     rax, [rbp+680h+var_640]
0x180018eb3  mov     [rsp+780h+var_750], rax; struct _FAX_PERSONAL_PROFILEW *
0x180018eb8  lea     rax, [rbp+680h+var_6D0]
0x180018ebc  mov     dword ptr [rsp+780h+var_758], ecx; unsigned int
0x180018ec0  mov     rcx, rdi; void *
0x180018ec3  mov     [rsp+780h+var_760], rax; struct _FAX_PERSONAL_PROFILEW *
0x180018ec8  call    ?FaxSendDocumentInternalW@@YAHPEAXQEAPEBGKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@K3PEBU_FAX_JOB_PARAM_EXW@@PEAKPEA_K6PEAH@Z; FaxSendDocumentInternalW(void *,ushort const * * const,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,ulong,_FAX_PERSONAL_PROFILEW const *,_FAX_JOB_PARAM_EXW const *,ulong *,unsigned __int64 *,unsigned __int64 *,int *)
0x180018ecd  test    eax, eax
0x180018ecf  jz      short loc_180018F2E
0x180018ed1  cmp     ebx, 1
0x180018ed4  jnz     short loc_180018EE2
0x180018ed6  test    r15, r15
0x180018ed9  jz      short loc_180018EE2
0x180018edb  mov     eax, dword ptr [rsp+780h+var_718]
0x180018edf  mov     [r15], eax
0x180018ee2  mov     rcx, [rbp+680h+lpMem+8]; lpMem
0x180018ee6  call    pMemFree
0x180018eeb  mov     rcx, [rbp+680h+var_6F0+8]; lpMem
0x180018eef  call    pMemFree
0x180018ef4  mov     rcx, [rbp+680h+var_6E0]; lpMem
0x180018ef8  call    pMemFree
0x180018efd  mov     rcx, [rbp+680h+var_590]; lpMem
0x180018f04  call    pMemFree
0x180018f09  mov     rcx, [rbp+680h+var_560]; lpMem
0x180018f10  call    pMemFree
0x180018f15  lea     rcx, [rbp+680h+var_6D0]; struct _FAX_PERSONAL_PROFILEW *
0x180018f19  call    ?FreePersonalProfileStrings@@YAXPEAU_FAX_PERSONAL_PROFILEW@@@Z; FreePersonalProfileStrings(_FAX_PERSONAL_PROFILEW *)
0x180018f1e  lea     rcx, [rbp+680h+var_640]; struct _FAX_PERSONAL_PROFILEW *
0x180018f22  call    ?FreePersonalProfileStrings@@YAXPEAU_FAX_PERSONAL_PROFILEW@@@Z; FreePersonalProfileStrings(_FAX_PERSONAL_PROFILEW *)
0x180018f27  inc     ebx
0x180018f29  jmp     loc_180018CA7
0x180018f2e  mov     rax, cs:WPP_GLOBAL_Control
0x180018f35  lea     rdx, WPP_GLOBAL_Control
0x180018f3c  cmp     rax, rdx
0x180018f3f  jz      loc_180019092
0x180018f45  test    dword ptr [rax+1Ch], 1000h
0x180018f4c  jz      loc_180019092
0x180018f52  cmp     byte ptr [rax+19h], 2
0x180018f56  jb      loc_180019092
0x180018f5c  call    cs:__imp_GetLastError
0x180018f63  nop     dword ptr [rax+rax+00h]
0x180018f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f6f  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180018f76  mov     edx, 49h ; 'I'
0x180018f7b  mov     r9d, eax
0x180018f7e  mov     rcx, [rcx+10h]
0x180018f82  call    WPP_SF_d
0x180018f87  jmp     loc_180019092
0x180018f8c  mov     rax, cs:WPP_GLOBAL_Control
0x180018f93  lea     rdx, WPP_GLOBAL_Control
0x180018f9a  cmp     rax, rdx
0x180018f9d  jz      loc_180019092
0x180018fa3  test    dword ptr [rax+1Ch], 1000h
0x180018faa  jz      loc_180019092
0x180018fb0  cmp     byte ptr [rax+19h], 2
  ... truncated ...
```
