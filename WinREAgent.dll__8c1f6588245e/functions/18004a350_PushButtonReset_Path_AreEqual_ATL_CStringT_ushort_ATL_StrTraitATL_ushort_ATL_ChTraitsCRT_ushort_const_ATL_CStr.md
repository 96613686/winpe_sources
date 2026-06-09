# PushButtonReset::Path::AreEqual(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)

- ea: `0x18004a350`
- end: `0x18004a872`
- name: `?AreEqual@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_N@Z`
- size: `1314`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x18001aeb0`
- `0x1800323c0`
- `0x180038448`
- `0x18004ebec`
- `0x180050688`
- `0x180053830`

## callees

- `0x180004af8`
- `0x180005cc0`
- `0x18000d92c`
- `0x180023654`
- `0x180037344`
- `0x18004a350`
- `0x18004d404`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004a458`
- `KERNEL32!GetLastError` at `0x18004a49f`
- `KERNEL32!GetLastError` at `0x18004a4dc`
- `KERNEL32!GetLastError` at `0x18004a523`
- `KERNEL32!GetLastError` at `0x18004a5bf`
- `KERNEL32!GetLastError` at `0x18004a606`
- `KERNEL32!GetLastError` at `0x18004a675`
- `KERNEL32!GetLastError` at `0x18004a6bc`
- `KERNEL32!GetLastError` at `0x18004a72a`
- `KERNEL32!GetLastError` at `0x18004a771`
- `KERNEL32!GetLastError` at `0x18004a7cd`
- `KERNEL32!GetLastError` at `0x18004a458`
- `KERNEL32!GetLastError` at `0x18004a49f`
- `KERNEL32!GetLastError` at `0x18004a4dc`
- `KERNEL32!GetLastError` at `0x18004a523`
- `KERNEL32!GetLastError` at `0x18004a5bf`
- `KERNEL32!GetLastError` at `0x18004a606`
- `KERNEL32!GetLastError` at `0x18004a675`
- `KERNEL32!GetLastError` at `0x18004a6bc`
- `KERNEL32!GetLastError` at `0x18004a72a`
- `KERNEL32!GetLastError` at `0x18004a771`
- `KERNEL32!GetLastError` at `0x18004a7cd`
- `KERNEL32!GetFileAttributesW` at `0x18004a447`
- `KERNEL32!GetFileAttributesW` at `0x18004a4d1`
- `KERNEL32!GetFileAttributesW` at `0x18004a447`
- `KERNEL32!GetFileAttributesW` at `0x18004a4d1`
- `KERNEL32!CreateFileW` at `0x18004a58f`
- `KERNEL32!CreateFileW` at `0x18004a64c`
- `KERNEL32!CreateFileW` at `0x18004a58f`
- `KERNEL32!CreateFileW` at `0x18004a64c`
- `KERNEL32!GetFileInformationByHandle` at `0x18004a720`
- `KERNEL32!GetFileInformationByHandle` at `0x18004a7c3`
- `KERNEL32!GetFileInformationByHandle` at `0x18004a720`
- `KERNEL32!GetFileInformationByHandle` at `0x18004a7c3`

## string_xrefs

- `0x18004a3bd`: `PushButtonReset::Path::AreEqual`
- `0x18004a42c`: `PushButtonReset::Path::AreEqual`
- `0x18004a48c`: `PushButtonReset::Path::AreEqual`
- `0x18004a510`: `PushButtonReset::Path::AreEqual`
- `0x18004a5f3`: `PushButtonReset::Path::AreEqual`
- `0x18004a6a9`: `PushButtonReset::Path::AreEqual`
- `0x18004a75e`: `PushButtonReset::Path::AreEqual`
- `0x18004a5d8`: `Failed to open [%s] for read`
- `0x18004a68e`: `Failed to open [%s] for read`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PushButtonReset::Path::AreEqual(_QWORD *a1, _QWORD *a2, bool *a3)
{
  int Canonical; // ebx
  int v8; // esi
  const WCHAR *v9; // rdi
  const WCHAR *v10; // rbx
  DWORD FileAttributesW; // eax
  char v12; // si
  signed int LastError; // eax
  signed int v14; // eax
  unsigned int v15; // r14d
  DWORD v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  unsigned int v19; // r14d
  int v20; // esi
  DWORD dwFlagsAndAttributes; // esi
  signed int v22; // eax
  signed int v23; // eax
  HANDLE v24; // rax
  signed int v25; // eax
  signed int v26; // eax
  HANDLE *v27; // rax
  signed int v28; // eax
  signed int v29; // eax
  HANDLE *v30; // rax
  signed int v31; // eax
  bool v32; // al
  void **v33; // [rsp+40h] [rbp-89h] BYREF
  HANDLE FileW; // [rsp+48h] [rbp-81h] BYREF
  void **v35; // [rsp+50h] [rbp-79h] BYREF
  HANDLE v36; // [rsp+58h] [rbp-71h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-69h] BYREF
  LPCWSTR v38; // [rsp+68h] [rbp-61h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION v39; // [rsp+70h] [rbp-59h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+A8h] [rbp-21h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
  Canonical = PushButtonReset::Path::GetCanonical(a1, &lpFileName);
  if ( Canonical < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Canonical,
      "PushButtonReset::Path::AreEqual",
      "base\\reset\\util\\src\\filesystem.cpp",
      790,
      L"Failed to get canonical form for [%s]",
      *a1);
    ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
    return (unsigned int)Canonical;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v38);
  v8 = PushButtonReset::Path::GetCanonical(a2, &v38);
  v9 = lpFileName;
  v10 = v38;
  if ( v8 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v8,
      "PushButtonReset::Path::AreEqual",
      "base\\reset\\util\\src\\filesystem.cpp",
      795,
      L"Failed to get canonical form for [%s]",
      *a2);
LABEL_49:
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
    goto LABEL_50;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  v12 = FileAttributesW;
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "PushButtonReset::Path::AreEqual",
      "base\\reset\\util\\src\\filesystem.cpp",
      802,
      L"Failed to get attributes for [%s]",
      v9);
    v14 = GetLastError();
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_10;
  }
  v16 = GetFileAttributesW(v10);
  if ( v16 != -1 )
  {
    v20 = v12 & 0x10;
    if ( v20 != (v16 & 0x10) )
    {
      *a3 = 0;
LABEL_48:
      v8 = 0;
      goto LABEL_49;
    }
    dwFlagsAndAttributes = v20 != 0 ? 35651584 : 0x200000;
    v33 = &RAII::CAutoCleanup<void *>::`vftable';
    FileW = CreateFileW(v9, 0, 7u, 0, 3u, dwFlagsAndAttributes, 0);
    if ( *(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v33) == -1 )
    {
      FileW = 0;
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v22,
        "PushButtonReset::Path::AreEqual",
        "base\\reset\\util\\src\\filesystem.cpp",
        834,
        L"Failed to open [%s] for read",
        v9);
      v23 = GetLastError();
      v15 = v23;
      if ( v23 > 0 )
        v15 = (unsigned __int16)v23 | 0x80070000;
LABEL_24:
      v33 = &RAII::CAutoCleanup<void *>::`vftable';
      RAII::CleanupInfo<void *>::Release(&FileW);
LABEL_10:
      ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
      return v15;
    }
    v24 = CreateFileW(v10, 0, 7u, 0, 3u, dwFlagsAndAttributes, 0);
    v35 = &RAII::CAutoCleanup<void *>::`vftable';
    v36 = v24;
    if ( *(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v35) == -1 )
    {
      v36 = 0;
      v25 = GetLastError();
      if ( v25 > 0 )
        v25 = (unsigned __int16)v25 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v25,
        "PushButtonReset::Path::AreEqual",
        "base\\reset\\util\\src\\filesystem.cpp",
        844,
        L"Failed to open [%s] for read",
        v10);
    }
    else
    {
      memset(&FileInformation, 0, sizeof(FileInformation));
      v27 = (HANDLE *)((__int64 (__fastcall *)(void ***))v33[4])(&v33);
      if ( !GetFileInformationByHandle(*v27, &FileInformation) )
      {
        v28 = GetLastError();
        if ( v28 > 0 )
          v28 = (unsigned __int16)v28 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v28,
          "PushButtonReset::Path::AreEqual",
          "base\\reset\\util\\src\\filesystem.cpp",
          851,
          L"Failed to get information for [%s]",
          v9);
        v29 = GetLastError();
        v15 = v29;
        if ( v29 > 0 )
          v15 = (unsigned __int16)v29 | 0x80070000;
        v35 = &RAII::CAutoCleanup<void *>::`vftable';
        RAII::CleanupInfo<void *>::Release(&v36);
        goto LABEL_24;
      }
      memset(&v39, 0, sizeof(v39));
      v30 = (HANDLE *)((__int64 (__fastcall *)(void ***))v35[4])(&v35);
      if ( GetFileInformationByHandle(*v30, &v39) )
      {
        v32 = FileInformation.dwVolumeSerialNumber == v39.dwVolumeSerialNumber
           && FileInformation.nFileIndexLow == v39.nFileIndexLow
           && FileInformation.nFileIndexHigh == v39.nFileIndexHigh;
        *a3 = v32;
        v35 = &RAII::CAutoCleanup<void *>::`vftable';
        RAII::CleanupInfo<void *>::Release(&v36);
        v33 = &RAII::CAutoCleanup<void *>::`vftable';
        RAII::CleanupInfo<void *>::Release(&FileW);
        goto LABEL_48;
      }
      v31 = GetLastError();
      if ( v31 > 0 )
        v31 = (unsigned __int16)v31 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v31,
        "PushButtonReset::Path::AreEqual",
        "base\\reset\\util\\src\\filesystem.cpp",
        858,
        L"Failed to get information for [%s]",
        v10);
    }
    v26 = GetLastError();
    v19 = v26;
    if ( v26 > 0 )
      v19 = (unsigned __int16)v26 | 0x80070000;
    v35 = &RAII::CAutoCleanup<void *>::`vftable';
    RAII::CleanupInfo<void *>::Release(&v36);
    v33 = &RAII::CAutoCleanup<void *>::`vftable';
    RAII::CleanupInfo<void *>::Release(&FileW);
    goto LABEL_16;
  }
  v17 = GetLastError();
  if ( v17 > 0 )
    v17 = (unsigned __int16)v17 | 0x80070000;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)v17,
    "PushButtonReset::Path::AreEqual",
    "base\\reset\\util\\src\\filesystem.cpp",
    810,
    L"Failed to get attributes for [%s]",
    v10);
  v18 = GetLastError();
  v19 = v18;
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
LABEL_16:
  ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
  v8 = v19;
LABEL_50:
  ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004a350  push    rbp
0x18004a352  push    rbx
0x18004a353  push    rsi
0x18004a354  push    rdi
0x18004a355  push    r13
0x18004a357  push    r14
0x18004a359  push    r15
0x18004a35b  lea     rbp, [rsp-27h]
0x18004a360  sub     rsp, 0F0h
0x18004a367  mov     rax, cs:__security_cookie
0x18004a36e  xor     rax, rsp
0x18004a371  mov     [rbp+57h+var_40], rax
0x18004a375  mov     r15, r8
0x18004a378  mov     r14, rdx
0x18004a37b  mov     rdi, rcx
0x18004a37e  lea     rcx, [rbp+57h+lpFileName]
0x18004a382  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004a387  nop
0x18004a388  lea     rdx, [rbp+57h+lpFileName]
0x18004a38c  mov     rcx, rdi
0x18004a38f  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004a394  mov     ebx, eax
0x18004a396  test    eax, eax
0x18004a398  jns     short loc_18004A3E5
0x18004a39a  mov     rcx, [rdi]
0x18004a39d  mov     [rsp+120h+hTemplateFile], rcx
0x18004a3a2  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004a3a9  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rax
0x18004a3ae  mov     [rsp+120h+dwCreationDisposition], 316h
0x18004a3b6  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004a3bd  lea     r8, aPushbuttonrese_17; "PushButtonReset::Path::AreEqual"
0x18004a3c4  mov     edx, ebx
0x18004a3c6  mov     ecx, 2
0x18004a3cb  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004a3d0  nop
0x18004a3d1  mov     rcx, [rbp+57h+lpFileName]
0x18004a3d5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004a3d9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004a3de  mov     eax, ebx
0x18004a3e0  jmp     loc_18004A854
0x18004a3e5  lea     rcx, [rbp+57h+var_B8]
0x18004a3e9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004a3ee  nop
0x18004a3ef  lea     rdx, [rbp+57h+var_B8]
0x18004a3f3  mov     rcx, r14
0x18004a3f6  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004a3fb  mov     esi, eax
0x18004a3fd  mov     rdi, [rbp+57h+lpFileName]
0x18004a401  mov     rbx, [rbp+57h+var_B8]
0x18004a405  test    eax, eax
0x18004a407  jns     short loc_18004A444
0x18004a409  mov     rcx, [r14]
0x18004a40c  mov     [rsp+120h+hTemplateFile], rcx
0x18004a411  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004a418  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rax
0x18004a41d  mov     [rsp+120h+dwCreationDisposition], 31Bh
0x18004a425  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004a42c  lea     r8, aPushbuttonrese_17; "PushButtonReset::Path::AreEqual"
0x18004a433  mov     edx, esi
0x18004a435  mov     ecx, 2
0x18004a43a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004a43f  jmp     loc_18004A83F
0x18004a444  mov     rcx, rdi; lpFileName
0x18004a447  call    cs:__imp_GetFileAttributesW
0x18004a44d  mov     esi, eax
0x18004a44f  or      r14d, 0FFFFFFFFh
0x18004a453  cmp     eax, r14d
0x18004a456  jnz     short loc_18004A4CE
0x18004a458  call    cs:__imp_GetLastError
0x18004a45e  mov     esi, 80070000h
0x18004a463  test    eax, eax
0x18004a465  jle     short loc_18004A46C
0x18004a467  movzx   eax, ax
0x18004a46a  or      eax, esi
0x18004a46c  mov     [rsp+120h+hTemplateFile], rdi
0x18004a471  lea     rcx, aFailedToGetAtt; "Failed to get attributes for [%s]"
0x18004a478  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx
0x18004a47d  mov     [rsp+120h+dwCreationDisposition], 322h
0x18004a485  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004a48c  lea     r8, aPushbuttonrese_17; "PushButtonReset::Path::AreEqual"
0x18004a493  mov     edx, eax
0x18004a495  mov     ecx, 2
0x18004a49a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004a49f  call    cs:__imp_GetLastError
0x18004a4a5  mov     r14d, eax
0x18004a4a8  test    eax, eax
0x18004a4aa  jle     short loc_18004A4B3
0x18004a4ac  movzx   r14d, ax
0x18004a4b0  or      r14d, esi
0x18004a4b3  lea     rcx, [rbx-18h]; this
0x18004a4b7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004a4bc  nop
0x18004a4bd  lea     rcx, [rdi-18h]; this
0x18004a4c1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004a4c6  mov     eax, r14d
0x18004a4c9  jmp     loc_18004A854
0x18004a4ce  mov     rcx, rbx; lpFileName
0x18004a4d1  call    cs:__imp_GetFileAttributesW
0x18004a4d7  cmp     eax, r14d
0x18004a4da  jnz     short loc_18004A548
0x18004a4dc  call    cs:__imp_GetLastError
0x18004a4e2  mov     esi, 80070000h
0x18004a4e7  test    eax, eax
0x18004a4e9  jle     short loc_18004A4F0
0x18004a4eb  movzx   eax, ax
0x18004a4ee  or      eax, esi
0x18004a4f0  mov     [rsp+120h+hTemplateFile], rbx
0x18004a4f5  lea     rcx, aFailedToGetAtt; "Failed to get attributes for [%s]"
0x18004a4fc  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx
0x18004a501  mov     [rsp+120h+dwCreationDisposition], 32Ah
0x18004a509  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004a510  lea     r8, aPushbuttonrese_17; "PushButtonReset::Path::AreEqual"
0x18004a517  mov     edx, eax
0x18004a519  mov     ecx, 2
0x18004a51e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004a523  call    cs:__imp_GetLastError
0x18004a529  mov     r14d, eax
0x18004a52c  test    eax, eax
0x18004a52e  jle     short loc_18004A537
0x18004a530  movzx   r14d, ax
0x18004a534  or      r14d, esi
0x18004a537  lea     rcx, [rbx-18h]; this
0x18004a53b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004a540  mov     esi, r14d
0x18004a543  jmp     loc_18004A849
0x18004a548  and     esi, 10h
0x18004a54b  and     eax, 10h
0x18004a54e  cmp     esi, eax
0x18004a550  jz      short loc_18004A55B
0x18004a552  mov     byte ptr [r15], 0
0x18004a556  jmp     loc_18004A83D
0x18004a55b  neg     esi
0x18004a55d  sbb     esi, esi
0x18004a55f  and     esi, 2000000h
0x18004a565  add     esi, 200000h
0x18004a56b  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x18004a574  mov     [rsp+120h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18004a578  mov     r14d, 3
0x18004a57e  mov     [rsp+120h+dwCreationDisposition], r14d; dwCreationDisposition
0x18004a583  xor     r9d, r9d; lpSecurityAttributes
0x18004a586  xor     edx, edx; dwDesiredAccess
0x18004a588  lea     r8d, [r14+4]; dwShareMode
0x18004a58c  mov     rcx, rdi; lpFileName
0x18004a58f  call    cs:__imp_CreateFileW
0x18004a595  lea     r13, ??_7?$CAutoCleanup@PEAX@RAII@@6B@; const RAII::CAutoCleanup<void *>::`vftable'
0x18004a59c  mov     [rsp+120h+var_E0], r13
0x18004a5a1  mov     [rsp+120h+var_D8], rax
0x18004a5a6  lea     rcx, [rsp+120h+var_E0]
0x18004a5ab  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18004a5b0  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18004a5b4  jnz     short loc_18004A62E
0x18004a5b6  mov     [rsp+120h+var_D8], 0
0x18004a5bf  call    cs:__imp_GetLastError
0x18004a5c5  mov     esi, 80070000h
0x18004a5ca  test    eax, eax
0x18004a5cc  jle     short loc_18004A5D3
0x18004a5ce  movzx   eax, ax
0x18004a5d1  or      eax, esi
0x18004a5d3  mov     [rsp+120h+hTemplateFile], rdi
0x18004a5d8  lea     rcx, aFailedToOpenSF_1; "Failed to open [%s] for read"
0x18004a5df  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx
0x18004a5e4  mov     [rsp+120h+dwCreationDisposition], 342h
0x18004a5ec  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004a5f3  lea     r8, aPushbuttonrese_17; "PushButtonReset::Path::AreEqual"
0x18004a5fa  mov     edx, eax
0x18004a5fc  mov     ecx, 2
0x18004a601  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004a606  call    cs:__imp_GetLastError
0x18004a60c  mov     r14d, eax
0x18004a60f  test    eax, eax
0x18004a611  jle     short loc_18004A61A
0x18004a613  movzx   r14d, ax
0x18004a617  or      r14d, esi
0x18004a61a  mov     [rsp+120h+var_E0], r13
0x18004a61f  lea     rcx, [rsp+120h+var_D8]
0x18004a624  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18004a629  jmp     loc_18004A4B3
0x18004a62e  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x18004a637  mov     [rsp+120h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18004a63b  mov     [rsp+120h+dwCreationDisposition], r14d; dwCreationDisposition
0x18004a640  xor     r9d, r9d; lpSecurityAttributes
0x18004a643  xor     edx, edx; dwDesiredAccess
0x18004a645  lea     r8d, [r9+7]; dwShareMode
0x18004a649  mov     rcx, rbx; lpFileName
0x18004a64c  call    cs:__imp_CreateFileW
0x18004a652  mov     [rbp+57h+var_D0], r13
0x18004a656  mov     [rbp+57h+var_C8], rax
0x18004a65a  lea     rcx, [rbp+57h+var_D0]
0x18004a65e  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18004a663  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18004a667  jnz     loc_18004A6F2
0x18004a66d  mov     [rbp+57h+var_C8], 0
0x18004a675  call    cs:__imp_GetLastError
0x18004a67b  mov     esi, 80070000h
0x18004a680  test    eax, eax
0x18004a682  jle     short loc_18004A689
0x18004a684  movzx   eax, ax
0x18004a687  or      eax, esi
0x18004a689  mov     [rsp+120h+hTemplateFile], rbx
0x18004a68e  lea     rcx, aFailedToOpenSF_1; "Failed to open [%s] for read"
0x18004a695  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx
0x18004a69a  mov     [rsp+120h+dwCreationDisposition], 34Ch
0x18004a6a2  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004a6a9  lea     r8, aPushbuttonrese_17; "PushButtonReset::Path::AreEqual"
0x18004a6b0  mov     edx, eax
0x18004a6b2  mov     ecx, 2
0x18004a6b7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004a6bc  call    cs:__imp_GetLastError
0x18004a6c2  test    eax, eax
0x18004a6c4  mov     r14d, eax
0x18004a6c7  jle     short loc_18004A6D0
0x18004a6c9  movzx   r14d, ax
0x18004a6cd  or      r14d, esi
0x18004a6d0  mov     [rbp+57h+var_D0], r13
0x18004a6d4  lea     rcx, [rbp+57h+var_C8]
0x18004a6d8  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18004a6dd  nop
0x18004a6de  mov     [rsp+120h+var_E0], r13
0x18004a6e3  lea     rcx, [rsp+120h+var_D8]
0x18004a6e8  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18004a6ed  jmp     loc_18004A537
0x18004a6f2  xorps   xmm0, xmm0
0x18004a6f5  xor     eax, eax
0x18004a6f7  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x18004a6fb  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18004a6ff  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x18004a703  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x18004a706  mov     rax, [rsp+120h+var_E0]
0x18004a70b  lea     rcx, [rsp+120h+var_E0]
0x18004a710  mov     rax, [rax+20h]
0x18004a714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a719  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x18004a71d  mov     rcx, [rax]; hFile
0x18004a720  call    cs:__imp_GetFileInformationByHandle
0x18004a726  test    eax, eax
0x18004a728  jnz     short loc_18004A797
0x18004a72a  call    cs:__imp_GetLastError
0x18004a730  mov     esi, 80070000h
0x18004a735  test    eax, eax
0x18004a737  jle     short loc_18004A73E
0x18004a739  movzx   eax, ax
0x18004a73c  or      eax, esi
0x18004a73e  mov     [rsp+120h+hTemplateFile], rdi
0x18004a743  lea     rcx, aFailedToGetInf_4; "Failed to get information for [%s]"
0x18004a74a  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx
0x18004a74f  mov     [rsp+120h+dwCreationDisposition], 353h
0x18004a757  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004a75e  lea     r8, aPushbuttonrese_17; "PushButtonReset::Path::AreEqual"
0x18004a765  mov     edx, eax
0x18004a767  mov     ecx, 2
0x18004a76c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004a771  call    cs:__imp_GetLastError
0x18004a777  mov     r14d, eax
0x18004a77a  test    eax, eax
0x18004a77c  jle     short loc_18004A785
0x18004a77e  movzx   r14d, ax
0x18004a782  or      r14d, esi
0x18004a785  mov     [rbp+57h+var_D0], r13
0x18004a789  lea     rcx, [rbp+57h+var_C8]
0x18004a78d  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18004a792  jmp     loc_18004A61A
0x18004a797  xorps   xmm0, xmm0
0x18004a79a  xor     eax, eax
0x18004a79c  movups  xmmword ptr [rbp+57h+var_B0.dwFileAttributes], xmm0
0x18004a7a0  movups  xmmword ptr [rbp+57h+var_B0.ftLastAccessTime.dwHighDateTime], xmm0
0x18004a7a4  movups  xmmword ptr [rbp+57h+var_B0.nFileSizeHigh], xmm0
0x18004a7a8  mov     [rbp+57h+var_B0.nFileIndexLow], eax
0x18004a7ab  mov     rax, [rbp+57h+var_D0]
0x18004a7af  lea     rcx, [rbp+57h+var_D0]
0x18004a7b3  mov     rax, [rax+20h]
0x18004a7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7bc  lea     rdx, [rbp+57h+var_B0]; lpFileInformation
0x18004a7c0  mov     rcx, [rax]; hFile
0x18004a7c3  call    cs:__imp_GetFileInformationByHandle
0x18004a7c9  test    eax, eax
0x18004a7cb  jnz     short loc_18004A7FF
0x18004a7cd  call    cs:__imp_GetLastError
0x18004a7d3  mov     esi, 80070000h
0x18004a7d8  test    eax, eax
0x18004a7da  jle     short loc_18004A7E1
0x18004a7dc  movzx   eax, ax
0x18004a7df  or      eax, esi
0x18004a7e1  mov     [rsp+120h+hTemplateFile], rbx
0x18004a7e6  lea     rcx, aFailedToGetInf_4; "Failed to get information for [%s]"
0x18004a7ed  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx
0x18004a7f2  mov     [rsp+120h+dwCreationDisposition], 35Ah
0x18004a7fa  jmp     loc_18004A6A2
0x18004a7ff  mov     eax, [rbp+57h+var_B0.dwVolumeSerialNumber]
0x18004a802  cmp     [rbp+57h+FileInformation.dwVolumeSerialNumber], eax
0x18004a805  jnz     short loc_18004A81B
0x18004a807  mov     eax, [rbp+57h+var_B0.nFileIndexLow]
0x18004a80a  cmp     [rbp+57h+FileInformation.nFileIndexLow], eax
0x18004a80d  jnz     short loc_18004A81B
0x18004a80f  mov     eax, [rbp+57h+var_B0.nFileIndexHigh]
0x18004a812  cmp     [rbp+57h+FileInformation.nFileIndexHigh], eax
0x18004a815  jnz     short loc_18004A81B
0x18004a817  mov     al, 1
0x18004a819  jmp     short loc_18004A81D
0x18004a81b  xor     al, al
0x18004a81d  mov     [r15], al
  ... truncated ...
```
