# CRecursiveRemoveDirectory::RemoveDirectoryW(ulong,wchar_t const * const,wchar_t const * const)

- ea: `0x180146f5c`
- end: `0x18014774b`
- name: `?RemoveDirectoryW@CRecursiveRemoveDirectory@@QEAAJKQEB_W0@Z`
- size: `2031`
- prototype: `__int64 __fastcall(CRecursiveRemoveDirectory *__hidden this, unsigned int, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task`

## callers

- `0x1801492a4`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x180012460`
- `0x180012770`
- `0x18008b38c`
- `0x18008b3bc`
- `0x1800bd064`
- `0x180145bac`
- `0x1801462a8`
- `0x180146f5c`
- `0x180147c54`
- `0x180148614`
- `0x18014b0c8`
- `0x18014ff1c`
- `0x18015018c`
- `0x1801501e0`
- `0x1801505b0`
- `0x1801f2558`
- `0x1801f2604`

## import_xrefs

- `ntdll!NtClose` at `0x180147608`
- `ntdll!NtClose` at `0x18014767a`
- `ntdll!NtClose` at `0x1801476d8`
- `ntdll!NtClose` at `0x180147608`
- `ntdll!NtClose` at `0x18014767a`
- `ntdll!NtClose` at `0x1801476d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801474fa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801474fa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180147353`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180147353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014752f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014752f`

## string_xrefs

- `0x18014713a`: `No directory specified`
- `0x1801470a5`: `Cannot use AllowReparseRoot without ContentsOnly`
- `0x180147288`: `Deleting the contents of directory: {}`
- `0x18014700a`: `Cannot use ContentsOnly with MoveToCbsTempBeforeDelete or RenameToTempBeforeDelete or MoveToCbsTempOnFailures`
- `0x18014736e`: `Deletion of: {} successful; already deleted`
- `0x1801476be`: `Deletion of: {} successful; already deleted`
- `0x1801473e6`: `Unable to move directory to temp, will delete in-place instead`
- `0x180147291`: `Deleting directory: {}`
- `0x1801472d2`: `Failed to acquire current thread token`
- `0x1801475a8`: `Failed removing directory: {}`
- `0x180147441`: `Failed getting parent directory: {}`
- `0x180147566`: `Deletion of directory failed...moving to CbsTemp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
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
  const wchar_t *v14; // rdx
  __int64 v15; // rdx
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  int v18; // eax
  const struct std::nothrow_t *v19; // rdx
  WCHAR *v20; // rbx
  const char *v21; // rcx
  int v22; // eax
  unsigned int v23; // edi
  __int64 v24; // rdx
  unsigned int v25; // edi
  const struct std::nothrow_t *v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  LPCWSTR v28; // rdi
  int v29; // eax
  const struct std::nothrow_t *v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  char *FileW; // rax
  char *v35; // r15
  signed int v36; // esi
  signed int LastError; // eax
  __int64 v38; // rdx
  const struct std::nothrow_t *v39; // rdx
  const struct std::nothrow_t *v40; // rdx
  CRecursiveRemoveDirectory **dwCreationDisposition; // [rsp+28h] [rbp-A9h]
  CRecursiveRemoveDirectory **dwCreationDispositiona; // [rsp+28h] [rbp-A9h]
  bool v43; // [rsp+48h] [rbp-89h]
  LPCWSTR *p_lpFileName; // [rsp+50h] [rbp-81h] BYREF
  CRecursiveRemoveDirectory *v45; // [rsp+58h] [rbp-79h] BYREF
  _QWORD v46[3]; // [rsp+60h] [rbp-71h] BYREF
  const wchar_t *v47; // [rsp+78h] [rbp-59h]
  LPCWSTR lpFileName; // [rsp+80h] [rbp-51h] BYREF
  __int64 v49; // [rsp+88h] [rbp-49h] BYREF
  char v50; // [rsp+90h] [rbp-41h]
  _BYTE v51[80]; // [rsp+98h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  v46[2] = -2;
  v45 = this;
  v47 = a3;
  p_lpFileName = 0;
  lpFileName = 0;
  AutoThreadPriority::AutoThreadPriority((AutoThreadPriority *)v51, a2);
  v49 = 0;
  v50 = 0;
  v6 = a2 & 0x10;
  v7 = a2 & 0x20;
  LOBYTE(v8) = (a2 & 8) != 0;
  v43 = (a2 & 0x40) != 0;
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
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
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
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
    return v10;
  }
  v14 = v47;
  if ( !v47 )
  {
    v10 = -2147024809;
    LODWORD(lpFileName) = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        (unsigned int)((_DWORD)v47 + 3),
        "No directory specified");
      p_lpFileName = &lpFileName;
      dwCreationDisposition = (CRecursiveRemoveDirectory **)&p_lpFileName;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v15,
        (unsigned int)((_DWORD)v47 + 3),
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x313,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
    return v10;
  }
  *((_DWORD *)this + 5) = a2;
  *((_BYTE *)this + 16) = (a2 & 2) != 0;
  if ( (a2 & 4) != 0 )
  {
    AutoThreadPriority::SetPriority(v51, 3);
    v14 = v47;
  }
  v16 = SczAllocFromSz(&lpFileName, v14);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x320,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v16,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
    if ( lpFileName )
      operator delete((void *)(lpFileName - 4), v17);
    return v10;
  }
  v18 = PathPrefix(&lpFileName);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x321,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v18,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
    if ( lpFileName )
      operator delete((void *)(lpFileName - 4), v19);
    return v10;
  }
  v20 = (WCHAR *)lpFileName;
  v21 = "Deleting the contents of directory: {}";
  if ( !v9 )
    v21 = "Deleting directory: {}";
  LogAdapter::TraceInfo<wchar_t const *>(v21, &lpFileName);
  v46[0] = &RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
  v46[1] = 3;
  v22 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v49, v46);
  v23 = v22;
  if ( v22 < 0 )
  {
    LODWORD(lpFileName) = v22;
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
        v24,
        3,
        ": {}");
    }
    v25 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x336,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
            (const char *)v23,
            (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
    if ( v20 )
      operator delete(v20 - 4, v26);
    return v25;
  }
  if ( GetFileAttributesW(v20) == -1 )
  {
    p_lpFileName = (LPCWSTR *)v20;
    LogAdapter::TraceInfo<wchar_t const *>("Deletion of: {} successful; already deleted", &p_lpFileName);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
    if ( v20 )
      operator delete(v20 - 4, v27);
    return 0;
  }
  if ( v6 || v7 )
  {
    v28 = v20;
    lpFileName = 0;
    if ( v6 )
    {
      v29 = MoveToCbsTemp(v20, 0, &lpFileName);
      v8 = (unsigned int)v29 >> 31;
    }
    else
    {
      LOBYTE(v8) = 0;
      v29 = RenameToTemp(v20, &lpFileName);
    }
    if ( v29 >= 0 )
    {
      v20 = (WCHAR *)lpFileName;
    }
    else
    {
      v28 = lpFileName;
      LogAdapter::TraceAtLevelHr<long,>(
        1,
        (unsigned int)v29,
        "Unable to move directory to temp, will delete in-place instead");
    }
    if ( v28 )
      operator delete((void *)(v28 - 4), v30);
  }
  v31 = DirectoryFromPath(v20);
  v25 = v31;
  if ( v31 < 0 )
  {
    LODWORD(lpFileName) = v31;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v46[0] = v20;
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed getting parent directory: {}");
      v45 = (CRecursiveRemoveDirectory *)&lpFileName;
      dwCreationDisposition = &v45;
      LOBYTE(v32) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v32,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v25,
      (int)dwCreationDisposition);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
    if ( v20 )
      operator delete(v20 - 4, v33);
    if ( p_lpFileName )
      operator delete(p_lpFileName - 1, v33);
    return v25;
  }
  FileW = (char *)CreateFileW((LPCWSTR)p_lpFileName, 0x100080u, 7u, 0, 3u, 0x2200000u, 0);
  v35 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v36 = LastError;
    if ( LastError > 0 )
      v36 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)(v36 + 2147024894) <= 1 )
    {
      v45 = (CRecursiveRemoveDirectory *)v20;
      LogAdapter::TraceInfo<wchar_t const *>("Deletion of: {} successful; already deleted", &v45);
      if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v35) < 0 )
        __fastfail(7u);
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
      AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
      if ( v20 )
        operator delete(v20 - 4, v40);
      goto LABEL_87;
    }
  }
  else
  {
    v36 = CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(v45, v43, v9, FileW, v20);
  }
  if ( v36 >= 0
    || (_BYTE)v8
    && (LogAdapter::TraceAtLevelHr<long,>(1, (unsigned int)v36, "Deletion of directory failed...moving to CbsTemp"),
        v36 = MoveToCbsTemp(v20, 0, 0),
        v36 >= 0) )
  {
    v45 = (CRecursiveRemoveDirectory *)v20;
    LogAdapter::TraceInfo<wchar_t const *>("Deletion of: {} successful", &v45);
    if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v35) < 0 )
      __fastfail(7u);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
    AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
    if ( v20 )
      operator delete(v20 - 4, v40);
LABEL_87:
    if ( p_lpFileName )
      operator delete(p_lpFileName - 1, v40);
    return 0;
  }
  LODWORD(lpFileName) = v36;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Failed removing directory: {}");
    v45 = (CRecursiveRemoveDirectory *)&lpFileName;
    dwCreationDispositiona = &v45;
    LOBYTE(v38) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v38,
      3,
      ": {}");
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x382,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)(unsigned int)v36,
    (int)dwCreationDispositiona);
  if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v35) < 0 )
    __fastfail(7u);
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
  AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
  if ( v20 )
    operator delete(v20 - 4, v39);
  if ( p_lpFileName )
    operator delete(p_lpFileName - 1, v39);
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x180146f5c  mov     rax, rsp
0x180146f5f  push    rbp
0x180146f60  push    rsi
0x180146f61  push    rdi
0x180146f62  push    r12
0x180146f64  push    r13
0x180146f66  push    r14
0x180146f68  push    r15
0x180146f6a  lea     rbp, [rax-5Fh]
0x180146f6e  sub     rsp, 0F0h
0x180146f75  mov     [rbp+57h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180146f7d  mov     [rax+10h], rbx
0x180146f81  mov     rax, cs:__security_cookie
0x180146f88  xor     rax, rsp
0x180146f8b  mov     [rbp+57h+var_40], rax
0x180146f8f  mov     ebx, edx
0x180146f91  mov     rdi, rcx
0x180146f94  mov     [rbp+57h+var_D0], rcx
0x180146f98  mov     [rbp+57h+var_B0], r8
0x180146f9c  xor     r14d, r14d
0x180146f9f  mov     [rsp+120h+var_D8], r14
0x180146fa4  mov     [rbp+57h+lpFileName], r14
0x180146fa8  lea     rcx, [rbp+57h+var_90]; this
0x180146fac  call    ??0AutoThreadPriority@@QEAA@_N@Z; AutoThreadPriority::AutoThreadPriority(bool)
0x180146fb1  mov     [rbp+57h+var_A0], r14
0x180146fb5  mov     [rbp+57h+var_98], r14b
0x180146fb9  mov     r13b, bl
0x180146fbc  mov     esi, ebx
0x180146fbe  and     esi, 10h
0x180146fc1  mov     r15d, ebx
0x180146fc4  and     r15d, 20h
0x180146fc8  mov     eax, ebx
0x180146fca  and     eax, 8
0x180146fcd  setnz   r12b
0x180146fd1  mov     ecx, ebx
0x180146fd3  and     ecx, 40h
0x180146fd6  setnz   [rsp+120h+var_E0]
0x180146fdb  and     r13b, 1
0x180146fdf  jz      loc_180147080
0x180146fe5  test    esi, esi
0x180146fe7  jnz     short loc_180146FF6
0x180146fe9  test    r15d, r15d
0x180146fec  jnz     short loc_180146FF6
0x180146fee  test    eax, eax
0x180146ff0  jz      loc_180147080
0x180146ff6  mov     ebx, 80070057h
0x180146ffb  mov     dword ptr [rbp+57h+lpFileName], ebx
0x180146ffe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180147005  test    rcx, rcx
0x180147008  jz      short loc_18014704C
0x18014700a  lea     r9, aCannotUseConte; "Cannot use ContentsOnly with MoveToCbsT"...
0x180147011  mov     r14d, 3
0x180147017  mov     r8d, r14d
0x18014701a  xor     edx, edx
0x18014701c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180147021  lea     rax, [rbp+57h+lpFileName]
0x180147025  mov     [rsp+120h+var_D8], rax
0x18014702a  lea     rax, [rsp+120h+var_D8]
0x18014702f  mov     [rsp+120h+dwCreationDisposition], rax; int
0x180147034  lea     r9, asc_1802C6678; ": {}"
0x18014703b  mov     r8d, r14d
0x18014703e  mov     dl, 1
0x180147040  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180147047  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18014704c  mov     rcx, [rbp+5Fh]; this
0x180147050  mov     r9d, ebx; char *
0x180147053  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18014705a  mov     edx, 30Bh; void *
0x18014705f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147064  nop
0x180147065  lea     rcx, [rbp+57h+var_A0]; this
0x180147069  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18014706e  nop
0x18014706f  lea     rcx, [rbp+57h+var_90]; this
0x180147073  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x180147078  nop
0x180147079  mov     eax, ebx
0x18014707b  jmp     loc_180147723
0x180147080  test    ecx, ecx
0x180147082  jz      loc_180147119
0x180147088  test    r13b, r13b
0x18014708b  jnz     loc_180147119
0x180147091  mov     ebx, 80070057h
0x180147096  mov     dword ptr [rbp+57h+lpFileName], ebx
0x180147099  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801470a0  test    rcx, rcx
0x1801470a3  jz      short loc_1801470E7
0x1801470a5  lea     r9, aCannotUseAllow; "Cannot use AllowReparseRoot without Con"...
0x1801470ac  mov     r14d, 3
0x1801470b2  mov     r8d, r14d
0x1801470b5  xor     edx, edx
0x1801470b7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801470bc  lea     rax, [rbp+57h+lpFileName]
0x1801470c0  mov     [rsp+120h+var_D8], rax
0x1801470c5  lea     rax, [rsp+120h+var_D8]
0x1801470ca  mov     [rsp+120h+dwCreationDisposition], rax; int
0x1801470cf  lea     r9, asc_1802C6678; ": {}"
0x1801470d6  mov     r8d, r14d
0x1801470d9  mov     dl, 1
0x1801470db  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801470e2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801470e7  mov     rcx, [rbp+5Fh]; this
0x1801470eb  mov     r9d, ebx; char *
0x1801470ee  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1801470f5  mov     edx, 310h; void *
0x1801470fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801470ff  nop
0x180147100  lea     rcx, [rbp+57h+var_A0]; this
0x180147104  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180147109  nop
0x18014710a  lea     rcx, [rbp+57h+var_90]; this
0x18014710e  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x180147113  nop
0x180147114  jmp     loc_180147079
0x180147119  mov     rdx, [rbp+57h+var_B0]
0x18014711d  test    rdx, rdx
0x180147120  jnz     loc_1801471AA
0x180147126  mov     ebx, 80070057h
0x18014712b  mov     dword ptr [rbp+57h+lpFileName], ebx
0x18014712e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180147135  test    rcx, rcx
0x180147138  jz      short loc_180147178
0x18014713a  lea     r9, aNoDirectorySpe; "No directory specified"
0x180147141  lea     r14d, [rdx+3]
0x180147145  mov     r8d, r14d
0x180147148  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18014714d  lea     rax, [rbp+57h+lpFileName]
0x180147151  mov     [rsp+120h+var_D8], rax
0x180147156  lea     rax, [rsp+120h+var_D8]
0x18014715b  mov     [rsp+120h+dwCreationDisposition], rax; int
0x180147160  lea     r9, asc_1802C6678; ": {}"
0x180147167  mov     r8d, r14d
0x18014716a  mov     dl, 1
0x18014716c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180147173  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180147178  mov     rcx, [rbp+5Fh]; this
0x18014717c  mov     r9d, ebx; char *
0x18014717f  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180147186  mov     edx, 313h; void *
0x18014718b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147190  nop
0x180147191  lea     rcx, [rbp+57h+var_A0]; this
0x180147195  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18014719a  nop
0x18014719b  lea     rcx, [rbp+57h+var_90]; this
0x18014719f  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x1801471a4  nop
0x1801471a5  jmp     loc_180147079
0x1801471aa  mov     [rdi+14h], ebx
0x1801471ad  mov     eax, ebx
0x1801471af  shr     eax, 1
0x1801471b1  and     al, 1
0x1801471b3  mov     [rdi+10h], al
0x1801471b6  mov     r14d, 3
0x1801471bc  test    bl, 4
0x1801471bf  jz      short loc_1801471D1
0x1801471c1  mov     edx, r14d
0x1801471c4  lea     rcx, [rbp+57h+var_90]
0x1801471c8  call    ?SetPriority@AutoThreadPriority@@QEAAXW4PriorityType@1@@Z; AutoThreadPriority::SetPriority(AutoThreadPriority::PriorityType)
0x1801471cd  mov     rdx, [rbp+57h+var_B0]
0x1801471d1  lea     rcx, [rbp+57h+lpFileName]
0x1801471d5  call    SczAllocFromSz
0x1801471da  mov     ebx, eax
0x1801471dc  test    eax, eax
0x1801471de  jns     short loc_180147225
0x1801471e0  mov     rcx, [rbp+5Fh]; this
0x1801471e4  mov     r9d, eax; char *
0x1801471e7  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1801471ee  mov     edx, 320h; void *
0x1801471f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801471f8  nop
0x1801471f9  lea     rcx, [rbp+57h+var_A0]; this
0x1801471fd  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180147202  nop
0x180147203  lea     rcx, [rbp+57h+var_90]; this
0x180147207  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x18014720c  nop
0x18014720d  mov     rcx, [rbp+57h+lpFileName]
0x180147211  test    rcx, rcx
0x180147214  jz      short loc_180147220
0x180147216  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18014721a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18014721f  nop
0x180147220  jmp     loc_180147079
0x180147225  lea     rcx, [rbp+57h+lpFileName]
0x180147229  call    PathPrefix
0x18014722e  mov     ebx, eax
0x180147230  test    eax, eax
0x180147232  jns     short loc_180147279
0x180147234  mov     rcx, [rbp+5Fh]; this
0x180147238  mov     r9d, eax; char *
0x18014723b  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180147242  mov     edx, 321h; void *
0x180147247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014724c  nop
0x18014724d  lea     rcx, [rbp+57h+var_A0]; this
0x180147251  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180147256  nop
0x180147257  lea     rcx, [rbp+57h+var_90]; this
0x18014725b  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x180147260  nop
0x180147261  mov     rcx, [rbp+57h+lpFileName]
0x180147265  test    rcx, rcx
0x180147268  jz      short loc_180147274
0x18014726a  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18014726e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180147273  nop
0x180147274  jmp     loc_180147079
0x180147279  mov     rbx, [rbp+57h+lpFileName]
0x18014727d  lea     rdx, [rbp+57h+lpFileName]
0x180147281  mov     [rbp+57h+lpFileName], rbx
0x180147285  test    r13b, r13b
0x180147288  lea     rcx, aDeletingTheCon; "Deleting the contents of directory: {}"
0x18014728f  jnz     short loc_180147298
0x180147291  lea     rcx, aDeletingDirect; "Deleting directory: {}"
0x180147298  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x18014729d  lea     rax, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x1801472a4  mov     [rbp+57h+var_C8], rax
0x1801472a8  mov     [rbp+57h+var_C0], r14
0x1801472ac  lea     rdx, [rbp+57h+var_C8]
0x1801472b0  lea     rcx, [rbp+57h+var_A0]
0x1801472b4  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x1801472b9  mov     edi, eax
0x1801472bb  test    eax, eax
0x1801472bd  jns     loc_180147350
0x1801472c3  mov     dword ptr [rbp+57h+lpFileName], eax
0x1801472c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801472cd  test    rcx, rcx
0x1801472d0  jz      short loc_18014730C
0x1801472d2  lea     r9, aFailedToAcquir_0; "Failed to acquire current thread token"
0x1801472d9  mov     r8d, r14d
0x1801472dc  xor     edx, edx
0x1801472de  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801472e3  lea     rax, [rbp+57h+lpFileName]
0x1801472e7  mov     [rsp+120h+var_D8], rax
0x1801472ec  lea     rax, [rsp+120h+var_D8]
0x1801472f1  mov     [rsp+120h+dwCreationDisposition], rax; int
0x1801472f6  lea     r9, asc_1802C6678; ": {}"
0x1801472fd  mov     r8d, r14d
0x180147300  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180147307  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18014730c  mov     rcx, [rbp+5Fh]; this
0x180147310  mov     r9d, edi; char *
0x180147313  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18014731a  mov     edx, 336h; void *
0x18014731f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180147324  mov     edi, eax
0x180147326  lea     rcx, [rbp+57h+var_A0]; this
0x18014732a  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18014732f  nop
0x180147330  lea     rcx, [rbp+57h+var_90]; this
0x180147334  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x180147339  nop
0x18014733a  test    rbx, rbx
0x18014733d  jz      short loc_180147349
0x18014733f  lea     rcx, [rbx-8]; void *
0x180147343  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180147348  nop
0x180147349  mov     eax, edi
0x18014734b  jmp     loc_180147723
0x180147350  mov     rcx, rbx; lpFileName
0x180147353  call    cs:__imp_GetFileAttributesW
0x18014735a  nop     dword ptr [rax+rax+00h]
0x18014735f  cmp     eax, 0FFFFFFFFh
0x180147362  jnz     short loc_1801473A3
0x180147364  mov     [rsp+120h+var_D8], rbx
0x180147369  lea     rdx, [rsp+120h+var_D8]
0x18014736e  lea     rcx, aDeletionOfSucc; "Deletion of: {} successful; already del"...
0x180147375  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x18014737a  nop
0x18014737b  lea     rcx, [rbp+57h+var_A0]; this
0x18014737f  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180147384  nop
0x180147385  lea     rcx, [rbp+57h+var_90]; this
0x180147389  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x18014738e  nop
0x18014738f  test    rbx, rbx
0x180147392  jz      short loc_18014739E
0x180147394  lea     rcx, [rbx-8]; void *
0x180147398  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18014739d  nop
0x18014739e  jmp     loc_180147721
0x1801473a3  test    esi, esi
0x1801473a5  jnz     short loc_1801473AC
0x1801473a7  test    r15d, r15d
0x1801473aa  jz      short loc_18014740E
0x1801473ac  mov     rdi, rbx
0x1801473af  mov     [rbp+57h+lpFileName], 0
0x1801473b7  mov     rcx, rbx
0x1801473ba  test    esi, esi
0x1801473bc  jz      short loc_1801473D2
0x1801473be  lea     r8, [rbp+57h+lpFileName]
0x1801473c2  xor     edx, edx
0x1801473c4  call    MoveToCbsTemp
0x1801473c9  mov     r12d, eax
0x1801473cc  shr     r12d, 1Fh
0x1801473d0  jmp     short loc_1801473DE
0x1801473d2  xor     r12b, r12b
0x1801473d5  lea     rdx, [rbp+57h+lpFileName]
0x1801473d9  call    RenameToTemp
  ... truncated ...
```
