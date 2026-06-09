# ReadRoamingData(ushort const *,ushort const *,int,int,ushort const *,CWxString *,ulong *,ulong *,CWxString *,FILETIMEEX *,FILETIMEEX *,FILETIMEEX *)

- ea: `0x1801ab560`
- end: `0x1801abba4`
- name: `?ReadRoamingData@@YAJPEBG0HH0PEAVCWxString@@PEAK21PEATFILETIMEEX@@33@Z`
- size: `1604`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, struct CWxString *, unsigned int *, unsigned int *, struct CWxString *, union FILETIMEEX *, union FILETIMEEX *, union FILETIMEEX *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801aa40c`

## callees

- `0x180019ac4`
- `0x18001eaec`
- `0x1800204f8`
- `0x180025514`
- `0x180025910`
- `0x180025980`
- `0x180027ec0`
- `0x1800701d0`
- `0x180074804`
- `0x1800e8cd0`
- `0x18011a8e8`
- `0x18014a7a0`
- `0x1801ab560`
- `0x1801abbac`
- `0x1801dc680`
- `0x1801dc844`
- `0x1801e1790`
- `0x1801e3c78`
- `0x1801e41b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ab70b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ab70b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801ab7f5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801ab7f5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801ab74c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801ab74c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801abb63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801abb63`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1801aba27`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1801aba27`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801aba67`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801aba67`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801ab881`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801ab881`

## pseudocode

```c
__int64 __fastcall ReadRoamingData(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct CWxString *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        struct CWxString *a9,
        union FILETIMEEX *a10,
        union FILETIMEEX *a11,
        union FILETIMEEX *a12)
{
  char *v13; // rbx
  CWxString *v14; // r8
  unsigned int v15; // r11d
  const unsigned __int16 *v16; // rdx
  char v17; // r11
  __int64 v18; // r8
  __int64 v19; // rcx
  union FILETIMEEX *v20; // rax
  union FILETIMEEX *v21; // rax
  signed int ProcessUserSID; // esi
  __int64 v23; // rdi
  HANDLE FileW; // rax
  int LastError; // eax
  __int64 v26; // rcx
  int v27; // eax
  char *Heap; // rax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  int v33; // esi
  unsigned int v34; // eax
  __int64 v35; // r10
  unsigned int v36; // r10d
  const unsigned __int16 *v37; // r11
  int v38; // eax
  int v39; // eax
  int v40; // eax
  LPCWSTR *v41; // rcx
  union FILETIMEEX *v42; // rcx
  const unsigned __int16 *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *hTemplateFilea; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v50; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v51; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v52; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v53; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v54; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v55; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v56; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v57; // [rsp+50h] [rbp-B0h]
  PSID pSid2; // [rsp+70h] [rbp-90h] BYREF
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  unsigned __int64 v61; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v62; // [rsp+88h] [rbp-78h]
  struct CWxString *v63; // [rsp+90h] [rbp-70h]
  char *v64; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v65[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v66; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 *v67; // [rsp+B8h] [rbp-48h]
  struct CWxString *v68; // [rsp+C0h] [rbp-40h]
  union FILETIMEEX *v69; // [rsp+C8h] [rbp-38h]
  DWORD NumberOfBytesRead; // [rsp+D0h] [rbp-30h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+F0h] [rbp-10h] BYREF

  v13 = 0;
  v69 = a12;
  v59 = (int)a3;
  v67 = a2;
  lpFileName[0] = &Data;
  lpNewFileName[0] = &Data;
  v65[0] = &Data;
  v60 = (int)a4;
  v68 = a6;
  v62 = a5;
  v63 = a9;
  lpFileName[1] = 0;
  lpNewFileName[1] = 0;
  v64 = 0;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  pSid2 = 0;
  v61 = 0;
  v65[1] = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_SSllSqqqqqq(
      (unsigned int)&Data,
      (_DWORD)a5,
      (_DWORD)a9,
      (_DWORD)a1,
      (__int64)a2,
      (char)a3,
      (char)a4,
      (__int64)a5,
      (__int64)a6,
      (__int64)a7,
      (__int64)a8,
      (__int64)a9,
      (__int64)a10,
      (__int64)a11);
  CWxString::Empty(a6);
  if ( a7 )
    *(_DWORD *)a7 = v15;
  if ( a8 )
    *(_DWORD *)a8 = v15;
  CWxString::Empty(v14);
  v18 = 8;
  if ( a10 )
  {
    v19 = 8;
    v20 = a10;
    do
    {
      *(_BYTE *)v20 = v17;
      v20 = (union FILETIMEEX *)((char *)v20 + 1);
      --v19;
    }
    while ( v19 );
  }
  if ( a11 )
  {
    v21 = a11;
    do
    {
      *(_BYTE *)v21 = v17;
      v21 = (union FILETIMEEX *)((char *)v21 + 1);
      --v18;
    }
    while ( v18 );
  }
  ProcessUserSID = CWxString::SetPath(
                     (CWxString *)lpFileName,
                     a1,
                     v16,
                     0,
                     dwCreationDisposition,
                     dwFlagsAndAttributes,
                     hTemplateFile,
                     v50,
                     v52,
                     v54,
                     v56);
  if ( ProcessUserSID < 0 )
  {
    v23 = -1;
    HIDWORD(pSid2) = 449;
    goto LABEL_89;
  }
  FileW = CreateFileW(lpFileName[0], 0x80000000, 0, 0, 3u, 0, 0);
  v23 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = WxGetLastError();
    ProcessUserSID = LastError;
    if ( LastError > 0 )
      ProcessUserSID = (unsigned __int16)LastError | 0x80070000;
    HIDWORD(pSid2) = 462;
    if ( ProcessUserSID >= 0 )
      ProcessUserSID = -2147418113;
    goto LABEL_89;
  }
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v27 = WxGetLastError();
    ProcessUserSID = v27;
    if ( v27 > 0 )
      ProcessUserSID = (unsigned __int16)v27 | 0x80070000;
    HIDWORD(pSid2) = 464;
    if ( ProcessUserSID >= 0 )
      ProcessUserSID = -2147418113;
    goto LABEL_89;
  }
  if ( FileSize.QuadPart <= 0x96uLL )
  {
    HIDWORD(pSid2) = 471;
LABEL_88:
    ProcessUserSID = -2147024894;
    goto LABEL_89;
  }
  if ( FileSize.QuadPart >= 0x10DEuLL )
  {
    HIDWORD(pSid2) = 474;
    goto LABEL_88;
  }
  v66 = 0;
  Heap = (char *)WxAllocateHeapEx(v26, FileSize.LowPart);
  if ( !Heap )
  {
    v66 = 52;
    ProcessUserSID = -2147024882;
    HIDWORD(pSid2) = 480;
    goto LABEL_89;
  }
  v13 = Heap;
  v64 = Heap;
  if ( !ReadFile((HANDLE)v23, Heap, FileSize.LowPart, &NumberOfBytesRead, 0) )
  {
    v29 = WxGetLastError();
    ProcessUserSID = v29;
    if ( v29 > 0 )
      ProcessUserSID = (unsigned __int16)v29 | 0x80070000;
    HIDWORD(pSid2) = 490;
    if ( ProcessUserSID >= 0 )
      ProcessUserSID = -2147418113;
    goto LABEL_89;
  }
  if ( FileSize.LowPart != NumberOfBytesRead )
  {
    HIDWORD(pSid2) = 494;
    goto LABEL_88;
  }
  if ( *(_DWORD *)v13 != 515902494 || *((_DWORD *)v13 + 1) != 1966097 )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_(1036, 23, &WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids);
    HIDWORD(pSid2) = 506;
    goto LABEL_88;
  }
  ProcessUserSID = WxGetProcessUserSID((struct _SID **)&pSid2);
  if ( ProcessUserSID < 0 )
  {
    HIDWORD(pSid2) = 513;
    goto LABEL_89;
  }
  if ( !EqualSid(v13 + 44, pSid2) )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF__sid__sid_(v31, v30, v32, (char *)pSid2, v13 + 44);
    HIDWORD(pSid2) = 521;
    goto LABEL_88;
  }
  v33 = *((_DWORD *)v13 + 2);
  *((_DWORD *)v13 + 2) = 0;
  v34 = crc32(0, v13, NumberOfBytesRead);
  if ( v34 != v33 )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_dd(1036, 25, &WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids, v34, v33);
    HIDWORD(pSid2) = 538;
    goto LABEL_88;
  }
  v35 = *((unsigned int *)v13 + 36);
  if ( 2 * v35 + 150 != NumberOfBytesRead )
  {
    HIDWORD(pSid2) = 547;
    goto LABEL_88;
  }
  ProcessUserSID = StringCchLengthW((const unsigned __int16 *)v13 + 74, (unsigned int)(v35 + 1), &v61);
  if ( ProcessUserSID < 0 )
  {
    HIDWORD(pSid2) = 555;
    goto LABEL_89;
  }
  if ( (_DWORD)v61 != v36 )
  {
    HIDWORD(pSid2) = 558;
    goto LABEL_88;
  }
  ProcessUserSID = CWxString::Set((CWxString *)v65, v37, v36);
  if ( ProcessUserSID < 0 )
  {
    HIDWORD(pSid2) = 564;
    goto LABEL_89;
  }
  ProcessUserSID = ReplaceExtension((CWxString *)lpFileName);
  if ( ProcessUserSID < 0 )
  {
    HIDWORD(pSid2) = 570;
    goto LABEL_89;
  }
  v38 = v59;
  if ( !v59 )
    goto LABEL_82;
  ProcessUserSID = CWxString::SetPath(
                     (CWxString *)lpNewFileName,
                     v67,
                     v62,
                     0,
                     dwCreationDispositiona,
                     dwFlagsAndAttributesa,
                     hTemplateFilea,
                     v51,
                     v53,
                     v55,
                     v57);
  if ( ProcessUserSID < 0 )
  {
    HIDWORD(pSid2) = 574;
    goto LABEL_89;
  }
  ProcessUserSID = ReplaceExtension((CWxString *)lpNewFileName);
  if ( ProcessUserSID < 0 )
  {
    HIDWORD(pSid2) = 575;
    goto LABEL_89;
  }
  if ( v60 )
  {
    if ( !CreateHardLinkW(lpNewFileName[0], lpFileName[0], 0) )
    {
      v39 = WxGetLastError();
      ProcessUserSID = v39;
      if ( v39 > 0 )
        ProcessUserSID = (unsigned __int16)v39 | 0x80070000;
      HIDWORD(pSid2) = 579;
      if ( ProcessUserSID >= 0 )
        ProcessUserSID = -2147418113;
      goto LABEL_89;
    }
    goto LABEL_81;
  }
  if ( CopyFileW(lpFileName[0], lpNewFileName[0], 0) )
  {
LABEL_81:
    v38 = v59;
    ProcessUserSID = 0;
LABEL_82:
    v41 = lpFileName;
    if ( v38 )
      v41 = lpNewFileName;
    CWxString::Transfer((CWxString *)v41, v68);
    CWxString::Transfer((CWxString *)v65, v63);
    v42 = v69;
    *(_DWORD *)a7 = *((_DWORD *)v13 + 28);
    *(_DWORD *)a8 = *((_DWORD *)v13 + 29);
    *(_QWORD *)a10 = *((_QWORD *)v13 + 15);
    *(_QWORD *)a11 = *((_QWORD *)v13 + 16);
    *(_QWORD *)v42 = *((_QWORD *)v13 + 17);
    goto LABEL_89;
  }
  v40 = WxGetLastError();
  ProcessUserSID = v40;
  if ( v40 > 0 )
    ProcessUserSID = (unsigned __int16)v40 | 0x80070000;
  HIDWORD(pSid2) = 583;
  if ( ProcessUserSID >= 0 )
    ProcessUserSID = -2147418113;
LABEL_89:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 26, &WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids, (unsigned int)ProcessUserSID);
  CWxString::_Release((CWxString *)v65);
  if ( v13 )
    WxFreeHeapEx(&v64);
  if ( v23 != -1 )
    CloseHandle((HANDLE)v23);
  CWxString::_Release((CWxString *)lpNewFileName);
  CWxString::_Release((CWxString *)lpFileName);
  return (unsigned int)ProcessUserSID;
}

```

## disassembly

```asm
0x1801ab560  mov     [rsp-8+arg_10], rbx
0x1801ab565  push    rbp
0x1801ab566  push    rsi
0x1801ab567  push    rdi
0x1801ab568  push    r12
0x1801ab56a  push    r13
0x1801ab56c  push    r14
0x1801ab56e  push    r15
0x1801ab570  lea     rbp, [rsp-10h]
0x1801ab575  sub     rsp, 110h
0x1801ab57c  mov     rax, cs:__security_cookie
0x1801ab583  xor     rax, rsp
0x1801ab586  mov     [rbp+40h+var_40], rax
0x1801ab58a  mov     rsi, [rbp+40h+arg_28]
0x1801ab58e  xor     r11d, r11d
0x1801ab591  mov     r12, [rbp+40h+arg_50]
0x1801ab598  mov     rdi, rcx
0x1801ab59b  mov     rcx, [rbp+40h+arg_58]
0x1801ab5a2  mov     eax, r9d
0x1801ab5a5  mov     r13, [rbp+40h+arg_48]
0x1801ab5ac  mov     r10d, r8d
0x1801ab5af  mov     r15, [rbp+40h+arg_30]
0x1801ab5b6  mov     r9, rdx
0x1801ab5b9  mov     r14, [rbp+40h+arg_38]
0x1801ab5c0  mov     ebx, r11d
0x1801ab5c3  mov     [rbp+40h+var_78], rcx
0x1801ab5c7  lea     rcx, Data
0x1801ab5ce  mov     [rsp+140h+var_C8], r8d
0x1801ab5d3  mov     r8, [rbp+40h+arg_40]
0x1801ab5da  mov     [rbp+40h+var_88], rdx
0x1801ab5de  mov     rdx, [rbp+40h+arg_20]
0x1801ab5e2  mov     dword ptr [rsp+140h+pSid2+4], r11d
0x1801ab5e7  mov     [rbp+40h+lpFileName], rcx
0x1801ab5eb  mov     [rbp+40h+lpNewFileName], rcx
0x1801ab5ef  mov     [rbp+40h+var_A0], rcx
0x1801ab5f3  mov     [rsp+140h+var_C4], eax
0x1801ab5f7  mov     [rbp+40h+var_80], rsi
0x1801ab5fb  mov     [rbp+40h+var_B8], rdx
0x1801ab5ff  mov     [rbp+40h+var_B0], r8
0x1801ab603  mov     [rbp+40h+var_58], r11
0x1801ab607  mov     [rbp+40h+var_48], r11
0x1801ab60b  mov     [rbp+40h+var_A8], rbx
0x1801ab60f  mov     [rbp+40h+NumberOfBytesRead], r11d
0x1801ab613  mov     qword ptr [rbp+40h+FileSize], r11
0x1801ab617  mov     [rsp+70h], r11
0x1801ab61c  mov     [rbp+40h+var_C0], r11
0x1801ab620  mov     [rbp+40h+var_98], r11
0x1801ab624  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801ab62b  jz      short loc_1801AB671
0x1801ab62d  mov     [rsp+140h+var_D8], r12
0x1801ab632  mov     [rsp+140h+var_E0], r13
0x1801ab637  mov     [rsp+140h+var_E8], r8
0x1801ab63c  mov     [rsp+140h+var_F0], r14; unsigned __int16 *
0x1801ab641  mov     [rsp+140h+var_F8], r15; unsigned __int16 *
0x1801ab646  mov     [rsp+140h+var_100], rsi; unsigned __int16 *
0x1801ab64b  mov     [rsp+140h+var_108], rdx; unsigned __int16 *
0x1801ab650  mov     dword ptr [rsp+140h+hTemplateFile], eax; unsigned __int16 *
0x1801ab654  mov     dword ptr [rsp+140h+dwFlagsAndAttributes], r10d; unsigned __int16 *
0x1801ab659  mov     qword ptr [rsp+140h+dwCreationDisposition], r9; unsigned __int16 *
0x1801ab65e  mov     r9, rdi
0x1801ab661  call    WPP_SF_SSllSqqqqqq
0x1801ab666  mov     rdx, [rbp+40h+var_B8]
0x1801ab66a  xor     r11d, r11d
0x1801ab66d  mov     r8, [rbp+40h+var_B0]
0x1801ab671  mov     rcx, rsi; this
0x1801ab674  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x1801ab679  test    r15, r15
0x1801ab67c  jz      short loc_1801AB681
0x1801ab67e  mov     [r15], r11d
0x1801ab681  test    r14, r14
0x1801ab684  jz      short loc_1801AB689
0x1801ab686  mov     [r14], r11d
0x1801ab689  mov     rcx, r8; this
0x1801ab68c  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x1801ab691  mov     r8d, 8
0x1801ab697  test    r13, r13
0x1801ab69a  jz      short loc_1801AB6AE
0x1801ab69c  mov     ecx, r8d
0x1801ab69f  mov     rax, r13
0x1801ab6a2  mov     [rax], r11b
0x1801ab6a5  inc     rax
0x1801ab6a8  sub     rcx, 1
0x1801ab6ac  jnz     short loc_1801AB6A2
0x1801ab6ae  test    r12, r12
0x1801ab6b1  jz      short loc_1801AB6C2
0x1801ab6b3  mov     rax, r12
0x1801ab6b6  mov     [rax], r11b
0x1801ab6b9  inc     rax
0x1801ab6bc  sub     r8, 1
0x1801ab6c0  jnz     short loc_1801AB6B6
0x1801ab6c2  mov     r8, rdx; unsigned __int16 *
0x1801ab6c5  lea     rcx, [rbp+40h+lpFileName]; this
0x1801ab6c9  mov     rdx, rdi; unsigned __int16 *
0x1801ab6cc  xor     r9d, r9d; unsigned __int16 *
0x1801ab6cf  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1801ab6d4  mov     esi, eax
0x1801ab6d6  test    eax, eax
0x1801ab6d8  jns     short loc_1801AB6EB
0x1801ab6da  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801ab6de  mov     dword ptr [rsp+140h+pSid2+4], 1C1h
0x1801ab6e6  jmp     loc_1801ABB21
0x1801ab6eb  mov     rcx, [rbp+40h+lpFileName]; lpFileName
0x1801ab6ef  xor     r9d, r9d; lpSecurityAttributes
0x1801ab6f2  mov     [rsp+140h+hTemplateFile], rbx; unsigned __int16 *
0x1801ab6f7  xor     r8d, r8d; dwShareMode
0x1801ab6fa  mov     dword ptr [rsp+140h+dwFlagsAndAttributes], ebx; unsigned __int16 *
0x1801ab6fe  mov     edx, 80000000h; dwDesiredAccess
0x1801ab703  mov     [rsp+140h+dwCreationDisposition], 3; dwCreationDisposition
0x1801ab70b  call    cs:__imp_CreateFileW
0x1801ab711  mov     rdi, rax
0x1801ab714  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801ab718  jnz     short loc_1801AB745
0x1801ab71a  call    WxGetLastError
0x1801ab71f  mov     esi, eax
0x1801ab721  test    eax, eax
0x1801ab723  jle     short loc_1801AB72E
0x1801ab725  movzx   esi, ax
0x1801ab728  or      esi, 80070000h
0x1801ab72e  test    esi, esi
0x1801ab730  mov     dword ptr [rsp+140h+pSid2+4], 1CEh
0x1801ab738  mov     eax, 8000FFFFh
0x1801ab73d  cmovns  esi, eax
0x1801ab740  jmp     loc_1801ABB21
0x1801ab745  lea     rdx, [rbp+40h+FileSize]; lpFileSize
0x1801ab749  mov     rcx, rdi; hFile
0x1801ab74c  call    cs:__imp_GetFileSizeEx
0x1801ab752  test    eax, eax
0x1801ab754  jnz     short loc_1801AB781
0x1801ab756  call    WxGetLastError
0x1801ab75b  mov     esi, eax
0x1801ab75d  test    eax, eax
0x1801ab75f  jle     short loc_1801AB76A
0x1801ab761  movzx   esi, ax
0x1801ab764  or      esi, 80070000h
0x1801ab76a  test    esi, esi
0x1801ab76c  mov     dword ptr [rsp+140h+pSid2+4], 1D0h
0x1801ab774  mov     eax, 8000FFFFh
0x1801ab779  cmovns  esi, eax
0x1801ab77c  jmp     loc_1801ABB21
0x1801ab781  mov     rax, qword ptr [rbp+40h+FileSize]
0x1801ab785  cmp     rax, 96h
0x1801ab78b  ja      short loc_1801AB79A
0x1801ab78d  mov     dword ptr [rsp+140h+pSid2+4], 1D7h
0x1801ab795  jmp     loc_1801ABB1C
0x1801ab79a  cmp     rax, 10DEh
0x1801ab7a0  jb      short loc_1801AB7AF
0x1801ab7a2  mov     dword ptr [rsp+140h+pSid2+4], 1DAh
0x1801ab7aa  jmp     loc_1801ABB1C
0x1801ab7af  mov     edx, eax
0x1801ab7b1  mov     [rbp+40h+var_8C], ebx
0x1801ab7b4  call    WxAllocateHeapEx
0x1801ab7b9  test    rax, rax
0x1801ab7bc  jnz     short loc_1801AB7D7
0x1801ab7be  mov     [rbp+40h+var_8C], 34h ; '4'
0x1801ab7c5  mov     esi, 8007000Eh
0x1801ab7ca  mov     dword ptr [rsp+140h+pSid2+4], 1E0h
0x1801ab7d2  jmp     loc_1801ABB21
0x1801ab7d7  mov     rbx, rax
0x1801ab7da  mov     [rbp+40h+var_A8], rax
0x1801ab7de  mov     r8d, dword ptr [rbp+40h+FileSize]; nNumberOfBytesToRead
0x1801ab7e2  lea     r9, [rbp+40h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801ab7e6  mov     rdx, rax; lpBuffer
0x1801ab7e9  mov     qword ptr [rsp+140h+dwCreationDisposition], 0; unsigned __int16 *
0x1801ab7f2  mov     rcx, rdi; hFile
0x1801ab7f5  call    cs:__imp_ReadFile
0x1801ab7fb  test    eax, eax
0x1801ab7fd  jnz     short loc_1801AB82A
0x1801ab7ff  call    WxGetLastError
0x1801ab804  mov     esi, eax
0x1801ab806  test    eax, eax
0x1801ab808  jle     short loc_1801AB813
0x1801ab80a  movzx   esi, ax
0x1801ab80d  or      esi, 80070000h
0x1801ab813  test    esi, esi
0x1801ab815  mov     dword ptr [rsp+140h+pSid2+4], 1EAh
0x1801ab81d  mov     eax, 8000FFFFh
0x1801ab822  cmovns  esi, eax
0x1801ab825  jmp     loc_1801ABB21
0x1801ab82a  mov     eax, [rbp+40h+NumberOfBytesRead]
0x1801ab82d  cmp     dword ptr [rbp+40h+FileSize], eax
0x1801ab830  jz      short loc_1801AB83F
0x1801ab832  mov     dword ptr [rsp+140h+pSid2+4], 1EEh
0x1801ab83a  jmp     loc_1801ABB1C
0x1801ab83f  cmp     dword ptr [rbx], 1EC00C1Eh
0x1801ab845  jnz     loc_1801ABAF5
0x1801ab84b  cmp     dword ptr [rbx+4], 1E0011h
0x1801ab852  jnz     loc_1801ABAF5
0x1801ab858  lea     rcx, [rsp+140h+pSid2]; struct _SID **
0x1801ab85d  call    ?WxGetProcessUserSID@@YAJPEAPEAU_SID@@@Z; WxGetProcessUserSID(_SID * *)
0x1801ab862  mov     esi, eax
0x1801ab864  test    eax, eax
0x1801ab866  jns     short loc_1801AB875
0x1801ab868  mov     dword ptr [rsp+140h+pSid2+4], 201h
0x1801ab870  jmp     loc_1801ABB21
0x1801ab875  mov     rdx, [rsp+140h+pSid2]; pSid2
0x1801ab87a  lea     rsi, [rbx+2Ch]
0x1801ab87e  mov     rcx, rsi; pSid1
0x1801ab881  call    cs:__imp_EqualSid
0x1801ab887  test    eax, eax
0x1801ab889  jnz     short loc_1801AB8B0
0x1801ab88b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801ab892  jz      short loc_1801AB8A3
0x1801ab894  mov     r9, [rsp+140h+pSid2]
0x1801ab899  mov     qword ptr [rsp+140h+dwCreationDisposition], rsi
0x1801ab89e  call    WPP_SF__sid__sid_
0x1801ab8a3  mov     dword ptr [rsp+140h+pSid2+4], 209h
0x1801ab8ab  jmp     loc_1801ABB1C
0x1801ab8b0  mov     esi, [rbx+8]
0x1801ab8b3  mov     rdx, rbx
0x1801ab8b6  mov     dword ptr [rbx+8], 0
0x1801ab8bd  xor     ecx, ecx
0x1801ab8bf  mov     r8d, [rbp+40h+NumberOfBytesRead]
0x1801ab8c3  call    crc32
0x1801ab8c8  cmp     eax, esi
0x1801ab8ca  jz      short loc_1801AB8FF
0x1801ab8cc  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801ab8d3  jz      short loc_1801AB8F2
0x1801ab8d5  mov     edx, 19h
0x1801ab8da  mov     [rsp+140h+dwCreationDisposition], esi
0x1801ab8de  mov     ecx, 40Ch
0x1801ab8e3  lea     r8, WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids
0x1801ab8ea  mov     r9d, eax
0x1801ab8ed  call    WPP_SF_dd
0x1801ab8f2  mov     dword ptr [rsp+140h+pSid2+4], 21Ah
0x1801ab8fa  jmp     loc_1801ABB1C
0x1801ab8ff  mov     r10d, [rbx+90h]
0x1801ab906  mov     eax, [rbp+40h+NumberOfBytesRead]
0x1801ab909  lea     rcx, ds:96h[r10*2]
0x1801ab911  cmp     rcx, rax
0x1801ab914  jz      short loc_1801AB923
0x1801ab916  mov     dword ptr [rsp+140h+pSid2+4], 223h
0x1801ab91e  jmp     loc_1801ABB1C
0x1801ab923  lea     r11, [rbx+94h]
0x1801ab92a  mov     rcx, r11; unsigned __int16 *
0x1801ab92d  lea     edx, [r10+1]; unsigned __int64
0x1801ab931  lea     r8, [rbp+40h+var_C0]; unsigned __int64 *
0x1801ab935  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801ab93a  mov     esi, eax
0x1801ab93c  test    eax, eax
0x1801ab93e  jns     short loc_1801AB94D
0x1801ab940  mov     dword ptr [rsp+140h+pSid2+4], 22Bh
0x1801ab948  jmp     loc_1801ABB21
0x1801ab94d  cmp     dword ptr [rbp+40h+var_C0], r10d
0x1801ab951  jz      short loc_1801AB960
0x1801ab953  mov     dword ptr [rsp+140h+pSid2+4], 22Eh
0x1801ab95b  jmp     loc_1801ABB1C
0x1801ab960  mov     r8d, r10d; unsigned int
0x1801ab963  lea     rcx, [rbp+40h+var_A0]; this
0x1801ab967  mov     rdx, r11; unsigned __int16 *
0x1801ab96a  call    ?Set@CWxString@@QEAAJPEBGK@Z; CWxString::Set(ushort const *,ulong)
0x1801ab96f  mov     esi, eax
0x1801ab971  test    eax, eax
0x1801ab973  jns     short loc_1801AB982
0x1801ab975  mov     dword ptr [rsp+140h+pSid2+4], 234h
0x1801ab97d  jmp     loc_1801ABB21
0x1801ab982  lea     r9, aCookie_5; ".cookie"
0x1801ab989  mov     r8d, 4
0x1801ab98f  lea     rdx, aDat_0; ".dat"
0x1801ab996  lea     rcx, [rbp+40h+lpFileName]; this
0x1801ab99a  call    ReplaceExtension
0x1801ab99f  mov     esi, eax
0x1801ab9a1  test    eax, eax
0x1801ab9a3  jns     short loc_1801AB9B2
0x1801ab9a5  mov     dword ptr [rsp+140h+pSid2+4], 23Ah
0x1801ab9ad  jmp     loc_1801ABB21
0x1801ab9b2  mov     eax, [rsp+140h+var_C8]
0x1801ab9b6  test    eax, eax
0x1801ab9b8  jz      loc_1801ABAA2
0x1801ab9be  mov     r8, [rbp+40h+var_B8]; unsigned __int16 *
0x1801ab9c2  lea     rcx, [rbp+40h+lpNewFileName]; this
0x1801ab9c6  mov     rdx, [rbp+40h+var_88]; unsigned __int16 *
0x1801ab9ca  xor     r9d, r9d; unsigned __int16 *
0x1801ab9cd  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1801ab9d2  mov     esi, eax
0x1801ab9d4  test    eax, eax
0x1801ab9d6  jns     short loc_1801AB9E5
0x1801ab9d8  mov     dword ptr [rsp+140h+pSid2+4], 23Eh
0x1801ab9e0  jmp     loc_1801ABB21
0x1801ab9e5  lea     r9, aCookie_5; ".cookie"
0x1801ab9ec  mov     r8d, 4
0x1801ab9f2  lea     rdx, aDat_0; ".dat"
0x1801ab9f9  lea     rcx, [rbp+40h+lpNewFileName]; this
0x1801ab9fd  call    ReplaceExtension
0x1801aba02  mov     esi, eax
0x1801aba04  test    eax, eax
0x1801aba06  jns     short loc_1801ABA15
0x1801aba08  mov     dword ptr [rsp+140h+pSid2+4], 23Fh
0x1801aba10  jmp     loc_1801ABB21
0x1801aba15  cmp     [rsp+140h+var_C4], 0
0x1801aba1a  jz      short loc_1801ABA5C
0x1801aba1c  mov     rdx, [rbp+40h+lpFileName]; lpExistingFileName
0x1801aba20  xor     r8d, r8d; lpSecurityAttributes
0x1801aba23  mov     rcx, [rbp+40h+lpNewFileName]; lpFileName
0x1801aba27  call    cs:__imp_CreateHardLinkW
0x1801aba2d  test    eax, eax
0x1801aba2f  jnz     short loc_1801ABA9C
0x1801aba31  call    WxGetLastError
0x1801aba36  mov     esi, eax
0x1801aba38  test    eax, eax
0x1801aba3a  jle     short loc_1801ABA45
  ... truncated ...
```
