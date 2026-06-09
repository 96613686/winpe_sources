# CRecursiveRemoveDirectory::RemoveDirectoryW(ulong,wchar_t const * const,wchar_t const * const)

- ea: `0x180040bb4`
- end: `0x18004133f`
- name: `?RemoveDirectoryW@CRecursiveRemoveDirectory@@QEAAJKQEB_W0@Z`
- size: `1931`
- prototype: `__int64 __fastcall(CRecursiveRemoveDirectory *__hidden this, unsigned int, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180043284`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18000fe74`
- `0x18001a810`
- `0x18001b0a4`
- `0x18001ba4c`
- `0x180022a18`
- `0x18003ddc8`
- `0x18003f8a4`
- `0x18003fec8`
- `0x180040bb4`
- `0x180041848`
- `0x180042490`
- `0x180046348`
- `0x180046870`
- `0x1800468c4`
- `0x1800477cc`
- `0x18004e028`
- `0x18004e0d4`

## import_xrefs

- `ntdll!NtClose` at `0x18004121b`
- `ntdll!NtClose` at `0x18004128a`
- `ntdll!NtClose` at `0x1800412cf`
- `ntdll!NtClose` at `0x18004121b`
- `ntdll!NtClose` at `0x18004128a`
- `ntdll!NtClose` at `0x1800412cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041142`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180040f6e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180040f6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004110d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004110d`

## string_xrefs

- `0x180040d7f`: `No directory specified`
- `0x180040c62`: `Cannot use ContentsOnly with MoveToCbsTempBeforeDelete or RenameToTempBeforeDelete or MoveToCbsTempOnFailures`
- `0x180040cf8`: `Cannot use AllowReparseRoot without ContentsOnly`
- `0x180040eef`: `Failed to acquire current thread token`
- `0x180040f89`: `Deletion of: {} successful; already deleted`
- `0x1800412b5`: `Deletion of: {} successful; already deleted`
- `0x180040ea5`: `Deleting the contents of directory: {}`
- `0x180040eae`: `Deleting directory: {}`
- `0x180041179`: `Deletion of directory failed...moving to CbsTemp`
- `0x1800411bb`: `Failed removing directory: {}`
- `0x180040ffe`: `Unable to move directory to temp, will delete in-place instead`
- `0x180041058`: `Failed getting parent directory: {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRecursiveRemoveDirectory::RemoveDirectoryW(
        CRecursiveRemoveDirectory *this,
        BOOL a2,
        const wchar_t *a3,
        const wchar_t *const a4)
{
  int v6; // esi
  int v7; // r15d
  unsigned int v8; // r12d
  bool v9; // r13
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  WCHAR *v17; // rbx
  const char *v18; // rcx
  int v19; // eax
  unsigned int v20; // edi
  __int64 v21; // rdx
  unsigned int v22; // edi
  WCHAR *v23; // rcx
  WCHAR *v24; // rcx
  LPCWSTR v25; // rdi
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  char *FileW; // rax
  char *v30; // r15
  signed int v31; // esi
  signed int LastError; // eax
  __int64 v33; // rdx
  CRecursiveRemoveDirectory **dwCreationDisposition; // [rsp+28h] [rbp-A9h]
  CRecursiveRemoveDirectory **dwCreationDispositiona; // [rsp+28h] [rbp-A9h]
  bool v36; // [rsp+48h] [rbp-89h]
  LPCWSTR *p_lpFileName; // [rsp+50h] [rbp-81h] BYREF
  CRecursiveRemoveDirectory *v38; // [rsp+58h] [rbp-79h] BYREF
  _QWORD v39[3]; // [rsp+60h] [rbp-71h] BYREF
  const wchar_t *v40; // [rsp+78h] [rbp-59h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-51h] BYREF
  __int64 v42; // [rsp+88h] [rbp-49h] BYREF
  char v43; // [rsp+90h] [rbp-41h]
  _BYTE v44[80]; // [rsp+98h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  v39[2] = -2;
  v38 = this;
  v40 = a3;
  p_lpFileName = 0;
  lpFileName = 0;
  AutoThreadPriority::AutoThreadPriority((AutoThreadPriority *)v44, a2);
  v42 = 0;
  v43 = 0;
  v6 = a2 & 0x10;
  v7 = a2 & 0x20;
  LOBYTE(v8) = (a2 & 8) != 0;
  v36 = (a2 & 0x40) != 0;
  v9 = a2;
  if ( a2 && ((a2 & 0x10) != 0 || (a2 & 0x20) != 0 || (a2 & 8) != 0) )
  {
    v10 = -2147024809;
    LODWORD(lpFileName) = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Cannot use ContentsOnly with MoveToCbsTempBeforeDelete or RenameToTempBeforeDelete or MoveToCbsTempOnFailures");
      p_lpFileName = &lpFileName;
      dwCreationDisposition = (CRecursiveRemoveDirectory **)&p_lpFileName;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v11,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30B,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
LABEL_8:
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v44);
    return v10;
  }
  if ( (a2 & 0x40) != 0 && !v9 )
  {
    v10 = -2147024809;
    LODWORD(lpFileName) = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Cannot use AllowReparseRoot without ContentsOnly");
      p_lpFileName = &lpFileName;
      dwCreationDisposition = (CRecursiveRemoveDirectory **)&p_lpFileName;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v13,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x310,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
    goto LABEL_8;
  }
  if ( !v40 )
  {
    v10 = -2147024809;
    LODWORD(lpFileName) = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        (unsigned int)((_DWORD)v40 + 3),
        "No directory specified");
      p_lpFileName = &lpFileName;
      dwCreationDisposition = (CRecursiveRemoveDirectory **)&p_lpFileName;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v14,
        (unsigned int)((_DWORD)v40 + 3),
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x313,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
    goto LABEL_8;
  }
  *((_DWORD *)this + 5) = a2;
  *((_BYTE *)this + 16) = (a2 & 2) != 0;
  if ( (a2 & 4) != 0 )
    AutoThreadPriority::SetPriority(v44, 3);
  v15 = SczAllocFromSz(&lpFileName);
  v10 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x320,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v15,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
    goto LABEL_23;
  }
  v16 = PathPrefix(&lpFileName);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x321,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v16,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
LABEL_23:
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v44);
    if ( lpFileName )
      operator delete((void *)(lpFileName - 4));
    return v10;
  }
  v17 = (WCHAR *)lpFileName;
  v18 = "Deleting the contents of directory: {}";
  if ( !v9 )
    v18 = "Deleting directory: {}";
  LogAdapter::TraceInfo<wchar_t const *>(v18, &lpFileName);
  v39[0] = &RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
  v39[1] = 3;
  v19 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v42, v39);
  v20 = v19;
  if ( v19 < 0 )
  {
    LODWORD(lpFileName) = v19;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to acquire current thread token");
      p_lpFileName = &lpFileName;
      dwCreationDisposition = (CRecursiveRemoveDirectory **)&p_lpFileName;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v21,
        3,
        ": {}");
    }
    v22 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x336,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
            (const char *)v20,
            (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v44);
    if ( !v17 )
      return v22;
    v23 = v17 - 4;
LABEL_34:
    operator delete(v23);
    return v22;
  }
  if ( GetFileAttributesW(v17) == -1 )
  {
    p_lpFileName = (LPCWSTR *)v17;
    LogAdapter::TraceInfo<wchar_t const *>("Deletion of: {} successful; already deleted", &p_lpFileName);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v44);
    if ( !v17 )
      return 0;
    v24 = v17 - 4;
LABEL_85:
    operator delete(v24);
    return 0;
  }
  if ( v6 || v7 )
  {
    v25 = v17;
    lpFileName = 0;
    if ( v6 )
    {
      v26 = MoveToCbsTemp(v17, 0, &lpFileName);
      v8 = (unsigned int)v26 >> 31;
    }
    else
    {
      LOBYTE(v8) = 0;
      v26 = RenameToTemp(v17, &lpFileName);
    }
    if ( v26 >= 0 )
    {
      v17 = (WCHAR *)lpFileName;
    }
    else
    {
      v25 = lpFileName;
      LogAdapter::TraceAtLevelHr<long,>(
        1,
        (unsigned int)v26,
        "Unable to move directory to temp, will delete in-place instead");
    }
    if ( v25 )
      operator delete((void *)(v25 - 4));
  }
  v27 = DirectoryFromPath(v17);
  v22 = v27;
  if ( v27 < 0 )
  {
    LODWORD(lpFileName) = v27;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v39[0] = v17;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed getting parent directory: {}",
        v39);
      v38 = (CRecursiveRemoveDirectory *)&lpFileName;
      dwCreationDisposition = &v38;
      LOBYTE(v28) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v28,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v22,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v44);
    if ( v17 )
      operator delete(v17 - 4);
    if ( !p_lpFileName )
      return v22;
    v23 = (WCHAR *)(p_lpFileName - 1);
    goto LABEL_34;
  }
  FileW = (char *)CreateFileW((LPCWSTR)p_lpFileName, 0x100080u, 7u, 0, 3u, 0x2200000u, 0);
  v30 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v31 = LastError;
    if ( LastError > 0 )
      v31 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)(v31 + 2147024894) <= 1 )
    {
      v38 = (CRecursiveRemoveDirectory *)v17;
      LogAdapter::TraceInfo<wchar_t const *>("Deletion of: {} successful; already deleted", &v38);
      if ( (unsigned __int64)(v30 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v30) < 0 )
        __fastfail(7u);
      goto LABEL_81;
    }
  }
  else
  {
    v31 = CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(v38, v36, v9, FileW, v17);
  }
  if ( v31 >= 0
    || (_BYTE)v8
    && (LogAdapter::TraceAtLevelHr<long,>(1, (unsigned int)v31, "Deletion of directory failed...moving to CbsTemp"),
        v31 = MoveToCbsTemp(v17, 0, 0),
        v31 >= 0) )
  {
    v38 = (CRecursiveRemoveDirectory *)v17;
    LogAdapter::TraceInfo<wchar_t const *>("Deletion of: {} successful", &v38);
    if ( (unsigned __int64)(v30 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v30) < 0 )
      __fastfail(7u);
LABEL_81:
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v44);
    if ( v17 )
      operator delete(v17 - 4);
    if ( !p_lpFileName )
      return 0;
    v24 = (WCHAR *)(p_lpFileName - 1);
    goto LABEL_85;
  }
  LODWORD(lpFileName) = v31;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Failed removing directory: {}",
      &v40);
    v38 = (CRecursiveRemoveDirectory *)&lpFileName;
    dwCreationDispositiona = &v38;
    LOBYTE(v33) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v33,
      3,
      ": {}");
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x382,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)(unsigned int)v31,
    (int)dwCreationDispositiona);
  if ( (unsigned __int64)(v30 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v30) < 0 )
    __fastfail(7u);
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v42);
  AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v44);
  if ( v17 )
    operator delete(v17 - 4);
  if ( p_lpFileName )
    operator delete(p_lpFileName - 1);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x180040bb4  mov     rax, rsp
0x180040bb7  push    rbp
0x180040bb8  push    rsi
0x180040bb9  push    rdi
0x180040bba  push    r12
0x180040bbc  push    r13
0x180040bbe  push    r14
0x180040bc0  push    r15
0x180040bc2  lea     rbp, [rax-5Fh]
0x180040bc6  sub     rsp, 0F0h
0x180040bcd  mov     [rbp+57h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180040bd5  mov     [rax+10h], rbx
0x180040bd9  mov     rax, cs:__security_cookie
0x180040be0  xor     rax, rsp
0x180040be3  mov     [rbp+57h+var_40], rax
0x180040be7  mov     ebx, edx
0x180040be9  mov     rdi, rcx
0x180040bec  mov     [rbp+57h+var_D0], rcx
0x180040bf0  mov     [rbp+57h+var_B0], r8
0x180040bf4  xor     r14d, r14d
0x180040bf7  mov     [rsp+120h+var_D8], r14
0x180040bfc  mov     [rbp+57h+lpFileName], r14
0x180040c00  lea     rcx, [rbp+57h+var_90]; this
0x180040c04  call    ??0AutoThreadPriority@@QEAA@_N@Z; AutoThreadPriority::AutoThreadPriority(bool)
0x180040c09  mov     [rbp+57h+var_A0], r14
0x180040c0d  mov     [rbp+57h+var_98], r14b
0x180040c11  mov     r13b, bl
0x180040c14  mov     esi, ebx
0x180040c16  and     esi, 10h
0x180040c19  mov     r15d, ebx
0x180040c1c  and     r15d, 20h
0x180040c20  mov     eax, ebx
0x180040c22  and     eax, 8
0x180040c25  setnz   r12b
0x180040c29  mov     ecx, ebx
0x180040c2b  and     ecx, 40h
0x180040c2e  setnz   [rsp+120h+var_E0]
0x180040c33  and     r13b, 1
0x180040c37  jz      loc_180040CD7
0x180040c3d  test    esi, esi
0x180040c3f  jnz     short loc_180040C4E
0x180040c41  test    r15d, r15d
0x180040c44  jnz     short loc_180040C4E
0x180040c46  test    eax, eax
0x180040c48  jz      loc_180040CD7
0x180040c4e  mov     ebx, 80070057h
0x180040c53  mov     dword ptr [rbp+57h+lpFileName], ebx
0x180040c56  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040c5d  test    rcx, rcx
0x180040c60  jz      short loc_180040CA4
0x180040c62  lea     r9, aCannotUseConte; "Cannot use ContentsOnly with MoveToCbsT"...
0x180040c69  mov     r14d, 3
0x180040c6f  mov     r8d, r14d
0x180040c72  xor     edx, edx
0x180040c74  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180040c79  lea     rax, [rbp+57h+lpFileName]
0x180040c7d  mov     [rsp+120h+var_D8], rax
0x180040c82  lea     rax, [rsp+120h+var_D8]
0x180040c87  mov     [rsp+120h+dwCreationDisposition], rax; int
0x180040c8c  lea     r9, asc_1801CAFB4; ": {}"
0x180040c93  mov     r8d, r14d
0x180040c96  mov     dl, 1
0x180040c98  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040c9f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180040ca4  mov     rcx, [rbp+5Fh]; this
0x180040ca8  mov     r9d, ebx; char *
0x180040cab  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180040cb2  mov     edx, 30Bh; void *
0x180040cb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040cbc  nop
0x180040cbd  lea     rcx, [rbp+57h+var_A0]; this
0x180040cc1  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180040cc6  nop
0x180040cc7  lea     rcx, [rbp+57h+var_90]; this
0x180040ccb  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x180040cd0  mov     eax, ebx
0x180040cd2  jmp     loc_180041317
0x180040cd7  test    ecx, ecx
0x180040cd9  jz      loc_180040D62
0x180040cdf  test    r13b, r13b
0x180040ce2  jnz     short loc_180040D62
0x180040ce4  mov     ebx, 80070057h
0x180040ce9  mov     dword ptr [rbp+57h+lpFileName], ebx
0x180040cec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040cf3  test    rcx, rcx
0x180040cf6  jz      short loc_180040D3A
0x180040cf8  lea     r9, aCannotUseAllow; "Cannot use AllowReparseRoot without Con"...
0x180040cff  mov     r14d, 3
0x180040d05  mov     r8d, r14d
0x180040d08  xor     edx, edx
0x180040d0a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180040d0f  lea     rax, [rbp+57h+lpFileName]
0x180040d13  mov     [rsp+120h+var_D8], rax
0x180040d18  lea     rax, [rsp+120h+var_D8]
0x180040d1d  mov     [rsp+120h+dwCreationDisposition], rax; int
0x180040d22  lea     r9, asc_1801CAFB4; ": {}"
0x180040d29  mov     r8d, r14d
0x180040d2c  mov     dl, 1
0x180040d2e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040d35  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180040d3a  mov     rcx, [rbp+5Fh]; this
0x180040d3e  mov     r9d, ebx; char *
0x180040d41  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180040d48  mov     edx, 310h; void *
0x180040d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040d52  nop
0x180040d53  lea     rcx, [rbp+57h+var_A0]; this
0x180040d57  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180040d5c  nop
0x180040d5d  jmp     loc_180040CC7
0x180040d62  mov     rdx, [rbp+57h+var_B0]
0x180040d66  test    rdx, rdx
0x180040d69  jnz     short loc_180040DE5
0x180040d6b  mov     ebx, 80070057h
0x180040d70  mov     dword ptr [rbp+57h+lpFileName], ebx
0x180040d73  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040d7a  test    rcx, rcx
0x180040d7d  jz      short loc_180040DBD
0x180040d7f  lea     r9, aNoDirectorySpe; "No directory specified"
0x180040d86  lea     r14d, [rdx+3]
0x180040d8a  mov     r8d, r14d
0x180040d8d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180040d92  lea     rax, [rbp+57h+lpFileName]
0x180040d96  mov     [rsp+120h+var_D8], rax
0x180040d9b  lea     rax, [rsp+120h+var_D8]
0x180040da0  mov     [rsp+120h+dwCreationDisposition], rax; int
0x180040da5  lea     r9, asc_1801CAFB4; ": {}"
0x180040dac  mov     r8d, r14d
0x180040daf  mov     dl, 1
0x180040db1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040db8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180040dbd  mov     rcx, [rbp+5Fh]; this
0x180040dc1  mov     r9d, ebx; char *
0x180040dc4  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180040dcb  mov     edx, 313h; void *
0x180040dd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040dd5  nop
0x180040dd6  lea     rcx, [rbp+57h+var_A0]; this
0x180040dda  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180040ddf  nop
0x180040de0  jmp     loc_180040CC7
0x180040de5  mov     [rdi+14h], ebx
0x180040de8  mov     eax, ebx
0x180040dea  shr     eax, 1
0x180040dec  and     al, 1
0x180040dee  mov     [rdi+10h], al
0x180040df1  mov     r14d, 3
0x180040df7  test    bl, 4
0x180040dfa  jz      short loc_180040E0C
0x180040dfc  mov     edx, r14d
0x180040dff  lea     rcx, [rbp+57h+var_90]
0x180040e03  call    ?SetPriority@AutoThreadPriority@@QEAAXW4PriorityType@1@@Z; AutoThreadPriority::SetPriority(AutoThreadPriority::PriorityType)
0x180040e08  mov     rdx, [rbp+57h+var_B0]
0x180040e0c  lea     rcx, [rbp+57h+lpFileName]
0x180040e10  call    SczAllocFromSz
0x180040e15  mov     ebx, eax
0x180040e17  test    eax, eax
0x180040e19  jns     short loc_180040E62
0x180040e1b  mov     rcx, [rbp+5Fh]; this
0x180040e1f  mov     r9d, eax; char *
0x180040e22  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180040e29  mov     edx, 320h; void *
0x180040e2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040e33  nop
0x180040e34  lea     rcx, [rbp+57h+var_A0]; this
0x180040e38  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180040e3d  nop
0x180040e3e  lea     rcx, [rbp+57h+var_90]; this
0x180040e42  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x180040e47  mov     rcx, [rbp+57h+lpFileName]
0x180040e4b  test    rcx, rcx
0x180040e4e  jz      loc_180040CD0
0x180040e54  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180040e58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040e5d  jmp     loc_180040CD0
0x180040e62  lea     rcx, [rbp+57h+lpFileName]
0x180040e66  call    PathPrefix
0x180040e6b  mov     ebx, eax
0x180040e6d  test    eax, eax
0x180040e6f  jns     short loc_180040E96
0x180040e71  mov     rcx, [rbp+5Fh]; this
0x180040e75  mov     r9d, eax; char *
0x180040e78  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180040e7f  mov     edx, 321h; void *
0x180040e84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040e89  nop
0x180040e8a  lea     rcx, [rbp+57h+var_A0]; this
0x180040e8e  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180040e93  nop
0x180040e94  jmp     short loc_180040E3E
0x180040e96  mov     rbx, [rbp+57h+lpFileName]
0x180040e9a  lea     rdx, [rbp+57h+lpFileName]
0x180040e9e  mov     [rbp+57h+lpFileName], rbx
0x180040ea2  test    r13b, r13b
0x180040ea5  lea     rcx, aDeletingTheCon; "Deleting the contents of directory: {}"
0x180040eac  jnz     short loc_180040EB5
0x180040eae  lea     rcx, aDeletingDirect; "Deleting directory: {}"
0x180040eb5  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x180040eba  lea     rax, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x180040ec1  mov     [rbp+57h+var_C8], rax
0x180040ec5  mov     [rbp+57h+var_C0], r14
0x180040ec9  lea     rdx, [rbp+57h+var_C8]
0x180040ecd  lea     rcx, [rbp+57h+var_A0]
0x180040ed1  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x180040ed6  mov     edi, eax
0x180040ed8  test    eax, eax
0x180040eda  jns     loc_180040F6B
0x180040ee0  mov     dword ptr [rbp+57h+lpFileName], eax
0x180040ee3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040eea  test    rcx, rcx
0x180040eed  jz      short loc_180040F29
0x180040eef  lea     r9, aFailedToAcquir_2; "Failed to acquire current thread token"
0x180040ef6  mov     r8d, r14d
0x180040ef9  xor     edx, edx
0x180040efb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180040f00  lea     rax, [rbp+57h+lpFileName]
0x180040f04  mov     [rsp+120h+var_D8], rax
0x180040f09  lea     rax, [rsp+120h+var_D8]
0x180040f0e  mov     [rsp+120h+dwCreationDisposition], rax; int
0x180040f13  lea     r9, asc_1801CAFB4; ": {}"
0x180040f1a  mov     r8d, r14d
0x180040f1d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040f24  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x180040f29  mov     rcx, [rbp+5Fh]; this
0x180040f2d  mov     r9d, edi; char *
0x180040f30  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180040f37  mov     edx, 336h; void *
0x180040f3c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180040f41  mov     edi, eax
0x180040f43  lea     rcx, [rbp+57h+var_A0]; this
0x180040f47  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180040f4c  nop
0x180040f4d  lea     rcx, [rbp+57h+var_90]; this
0x180040f51  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x180040f56  test    rbx, rbx
0x180040f59  jz      short loc_180040F64
0x180040f5b  lea     rcx, [rbx-8]; Block
0x180040f5f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040f64  mov     eax, edi
0x180040f66  jmp     loc_180041317
0x180040f6b  mov     rcx, rbx; lpFileName
0x180040f6e  call    cs:__imp_GetFileAttributesW
0x180040f75  nop     dword ptr [rax+rax+00h]
0x180040f7a  cmp     eax, 0FFFFFFFFh
0x180040f7d  jnz     short loc_180040FBB
0x180040f7f  mov     [rsp+120h+var_D8], rbx
0x180040f84  lea     rdx, [rsp+120h+var_D8]
0x180040f89  lea     rcx, aDeletionOfSucc; "Deletion of: {} successful; already del"...
0x180040f90  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x180040f95  nop
0x180040f96  lea     rcx, [rbp+57h+var_A0]; this
0x180040f9a  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180040f9f  nop
0x180040fa0  lea     rcx, [rbp+57h+var_90]; this
0x180040fa4  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x180040fa9  test    rbx, rbx
0x180040fac  jz      loc_180041315
0x180040fb2  lea     rcx, [rbx-8]
0x180040fb6  jmp     loc_180041310
0x180040fbb  test    esi, esi
0x180040fbd  jnz     short loc_180040FC4
0x180040fbf  test    r15d, r15d
0x180040fc2  jz      short loc_180041025
0x180040fc4  mov     rdi, rbx
0x180040fc7  mov     [rbp+57h+lpFileName], 0
0x180040fcf  mov     rcx, rbx
0x180040fd2  test    esi, esi
0x180040fd4  jz      short loc_180040FEA
0x180040fd6  lea     r8, [rbp+57h+lpFileName]
0x180040fda  xor     edx, edx
0x180040fdc  call    MoveToCbsTemp
0x180040fe1  mov     r12d, eax
0x180040fe4  shr     r12d, 1Fh
0x180040fe8  jmp     short loc_180040FF6
0x180040fea  xor     r12b, r12b
0x180040fed  lea     rdx, [rbp+57h+lpFileName]
0x180040ff1  call    RenameToTemp
0x180040ff6  test    eax, eax
0x180040ff8  jns     short loc_180041013
0x180040ffa  mov     rdi, [rbp+57h+lpFileName]
0x180040ffe  lea     r8, aUnableToMoveDi; "Unable to move directory to temp, will "...
0x180041005  mov     edx, eax
0x180041007  mov     ecx, 1
0x18004100c  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180041011  jmp     short loc_180041017
0x180041013  mov     rbx, [rbp+57h+lpFileName]
0x180041017  test    rdi, rdi
0x18004101a  jz      short loc_180041025
0x18004101c  lea     rcx, [rdi-8]; Block
0x180041020  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180041025  lea     rdx, [rsp+120h+var_D8]
0x18004102a  mov     rcx, rbx; pszSrc
0x18004102d  call    DirectoryFromPath
0x180041032  mov     edi, eax
0x180041034  test    eax, eax
0x180041036  jns     loc_1800410E3
0x18004103c  mov     dword ptr [rbp+57h+lpFileName], eax
0x18004103f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180041046  test    rcx, rcx
0x180041049  jz      short loc_180041092
  ... truncated ...
```
