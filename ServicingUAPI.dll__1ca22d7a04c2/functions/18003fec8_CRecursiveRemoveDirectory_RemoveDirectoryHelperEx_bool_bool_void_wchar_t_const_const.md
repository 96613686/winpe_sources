# CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(bool,bool,void *,wchar_t const * const)

- ea: `0x18003fec8`
- end: `0x180040bad`
- name: `?RemoveDirectoryHelperEx@CRecursiveRemoveDirectory@@AEAAJ_N0PEAXQEB_W@Z`
- size: `3301`
- prototype: `int(CRecursiveRemoveDirectory *__hidden this, bool, bool, void *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180040bb4`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800062b8`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18000fe74`
- `0x18001a810`
- `0x18001b964`
- `0x18001b9e4`
- `0x18003cd78`
- `0x18003ddc8`
- `0x18003e9cc`
- `0x18003f554`
- `0x18003f6e0`
- `0x18003f780`
- `0x18003f804`
- `0x18003fc14`
- `0x18003fec8`
- `0x180041348`
- `0x180041cb4`

## import_xrefs

- `ntdll!NtClose` at `0x18003ffc9`
- `ntdll!NtClose` at `0x1800400e7`
- `ntdll!NtClose` at `0x1800401ab`
- `ntdll!NtClose` at `0x18004021a`
- `ntdll!NtClose` at `0x1800402d8`
- `ntdll!NtClose` at `0x18004061d`
- `ntdll!NtClose` at `0x180040650`
- `ntdll!NtClose` at `0x180040703`
- `ntdll!NtClose` at `0x1800407b7`
- `ntdll!NtClose` at `0x1800407eb`
- `ntdll!NtClose` at `0x18004089b`
- `ntdll!NtClose` at `0x1800408cf`
- `ntdll!NtClose` at `0x18004092c`
- `ntdll!NtClose` at `0x180040960`
- `ntdll!NtClose` at `0x1800409f7`
- `ntdll!NtClose` at `0x180040a2b`
- `ntdll!NtClose` at `0x180040ae7`
- `ntdll!NtClose` at `0x180040b20`
- `ntdll!NtClose` at `0x180040b59`
- `ntdll!NtClose` at `0x18003ffc9`
- `ntdll!NtClose` at `0x1800400e7`
- `ntdll!NtClose` at `0x1800401ab`
- `ntdll!NtClose` at `0x18004021a`
- `ntdll!NtClose` at `0x1800402d8`
- `ntdll!NtClose` at `0x18004061d`
- `ntdll!NtClose` at `0x180040650`
- `ntdll!NtClose` at `0x180040703`
- `ntdll!NtClose` at `0x1800407b7`
- `ntdll!NtClose` at `0x1800407eb`
- `ntdll!NtClose` at `0x18004089b`
- `ntdll!NtClose` at `0x1800408cf`
- `ntdll!NtClose` at `0x18004092c`
- `ntdll!NtClose` at `0x180040960`
- `ntdll!NtClose` at `0x1800409f7`
- `ntdll!NtClose` at `0x180040a2b`
- `ntdll!NtClose` at `0x180040ae7`
- `ntdll!NtClose` at `0x180040b20`
- `ntdll!NtClose` at `0x180040b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800403e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800403e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040320`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040320`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800403aa`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800403aa`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004042d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004042d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800403d3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800403d3`

## string_xrefs

- `0x18003ff56`: `No directory specified`
- `0x180040369`: `Remove directory cancelled`
- `0x180040070`: `Failed to open {} for deletion`
- `0x180040991`: `Failed to open {} for deletion`
- `0x180040261`: `Failed to backslash-terminate directory path.`
- `0x180040134`: `Failed to add item to directory stack`
- `0x180040737`: `Failed to add item to directory stack`
- `0x1800404de`: `Unable to remove file {}.`
- `0x18004081b`: `Failed to backslash-terminate subdirectory path.`
- `0x1800406b5`: `Unable to remove directory {}.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(
        CRecursiveRemoveDirectory *this,
        char a2,
        char a3,
        void *a4,
        const wchar_t *a5)
{
  unsigned int v5; // esi
  __int64 v6; // rdx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx
  char *v11; // r13
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // r14d
  __int64 v16; // rdx
  char *v17; // r12
  CRecursiveRemoveDirectory *v18; // rbx
  void *v19; // rcx
  DWORD v20; // eax
  signed int LastError; // eax
  bool v22; // sf
  char *v23; // r15
  char *v24; // rcx
  char v25; // r8
  int v26; // r9d
  char *v27; // rcx
  LPCWSTR v28; // rbx
  HANDLE FirstFileW; // rax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // ebx
  __int64 v34; // rdx
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rcx
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rdx
  CRecursiveRemoveDirectory **v46; // [rsp+28h] [rbp-E0h]
  void *v47; // [rsp+28h] [rbp-E0h]
  CRecursiveRemoveDirectory *v48; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+40h] [rbp-C8h]
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-C0h] BYREF
  const wchar_t *v51; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+60h] [rbp-A8h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE v54[5]; // [rsp+70h] [rbp-98h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+98h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+330h] [rbp+228h]

  lpFileName[1] = (LPCWSTR)-2LL;
  LOBYTE(v49) = a3;
  v48 = this;
  v51 = a5;
  Handle = 0;
  *(__m128i *)&v54[1] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v54[3] = (HANDLE)-1LL;
  if ( !a5 )
  {
    v5 = -2147024809;
    LODWORD(v52) = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No directory specified");
      v48 = (CRecursiveRemoveDirectory *)&v52;
      v46 = &v48;
      LOBYTE(v6) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v6,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x479,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      (int)v46);
    utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    return v5;
  }
  v8 = OpenFileRelativeToParent((_DWORD)a4, (_DWORD)a5, a3, (_DWORD)a4, a2, (__int64)&Handle);
  v5 = v8;
  if ( (unsigned int)(v8 + 2147024894) <= 1
    || v8 == -2147024773
    || v8 == -2147022975
    || (unsigned int)(v8 + 805306317) <= 1
    || v8 == -805306310
    || v8 == -805305728 )
  {
    utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    return 0;
  }
  else
  {
    if ( v8 < 0 )
    {
      LODWORD(v52) = v8;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to open {} for deletion",
          &v51);
        v48 = (CRecursiveRemoveDirectory *)&v52;
        v47 = &v48;
        LOBYTE(v9) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v9,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48E,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)v5,
        (int)v47);
      utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(Handle) < 0 )
          __fastfail(7u);
        Handle = 0;
      }
      return v5;
    }
    if ( !(unsigned __int8)utl::vector<DeleteContext,utl::allocator<DeleteContext>>::emplace_back<Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>,0>(
                             &v54[1],
                             &Handle) )
    {
      v5 = -2147024882;
      LODWORD(v52) = -2147024882;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to add item to directory stack");
        v48 = (CRecursiveRemoveDirectory *)&v52;
        v47 = &v48;
        LOBYTE(v10) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v10,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x491,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)0x8007000ELL,
        (int)v47);
      utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(Handle) < 0 )
          __fastfail(7u);
        Handle = 0;
      }
      return v5;
    }
    v11 = (char *)v54[2];
    v12 = SczAllocFromSz((char *)v54[2] - 16);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v14 = SczEnsureBackslashTerminated(v11 - 16);
      v15 = v14;
      if ( v14 >= 0 )
      {
        v17 = (char *)v54[1];
        while ( 1 )
        {
          v18 = v48;
          if ( *((_BYTE *)v48 + 32) )
            break;
          v19 = (void *)*((_QWORD *)v48 + 3);
          if ( v19 )
          {
            v20 = WaitForSingleObject(v19, 0);
            if ( (v20 & 0xFFFFFF7F) != 0 )
            {
              if ( v20 == -1 )
              {
                LastError = GetLastError();
                v22 = LastError < 0;
                if ( LastError > 0 )
                {
                  LastError = (unsigned __int16)LastError | 0x80070000;
                  v22 = LastError < 0;
                }
                if ( v22 )
                  LogAdapter::TraceAtLevelHr<long,>(1, (unsigned int)LastError, "Error getting cancel event status");
              }
            }
            else
            {
              LogAdapter::TraceInfo<>("Remove directory cancelled");
              *((_BYTE *)v48 + 32) = 1;
            }
          }
          if ( *((_BYTE *)v18 + 32) )
            break;
          v23 = v11 - 24;
          memset_0(&FindFileData, 0, sizeof(FindFileData));
          v24 = (char *)*((_QWORD *)v11 - 1);
          if ( (unsigned __int64)(v24 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            lpFileName[0] = 0;
            v15 = SczAllocConcat2Sz(lpFileName, *((_QWORD *)v23 + 1), L"*.*");
            if ( (v15 & 0x80000000) != 0 )
            {
              LODWORD(v52) = v15;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to append wildcard to search pattern.");
                v48 = (CRecursiveRemoveDirectory *)&v52;
                v47 = &v48;
                LOBYTE(v45) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v45,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x4AA,
                (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                (const char *)v15,
                (int)v47);
              if ( lpFileName[0] )
                operator delete((void *)(lpFileName[0] - 4));
              utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
              if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                if ( NtClose(Handle) < 0 )
                  __fastfail(7u);
                Handle = 0;
              }
              return v15;
            }
            v28 = lpFileName[0];
            FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
            if ( ((*((_QWORD *)v23 + 2) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
            {
              INTERNAL_ERROR_ACTION(-1073741595);
              JUMPOUT(0x180040BACLL);
            }
            *((_QWORD *)v23 + 2) = FirstFileW;
            if ( v28 )
              operator delete((void *)(v28 - 4));
            v18 = v48;
          }
          else if ( !FindNextFileW(v24, &FindFileData) )
          {
            v27 = (char *)*((_QWORD *)v23 + 2);
            if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              if ( !FindClose(v27) )
              {
                GetLastError();
                __fastfail(7u);
              }
              *((_QWORD *)v23 + 2) = 0;
            }
          }
          if ( (unsigned __int64)(*((_QWORD *)v23 + 2) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            if ( 0xAAAAAAAAAAAAAAABuLL * ((v11 - v17) >> 3) > 1 || !(_BYTE)v49 )
            {
              v40 = CRecursiveRemoveDirectory::UnlinkOrDelete(v18, *(void **)v23);
              v41 = v40;
              lpFileName[0] = *((LPCWSTR *)v23 + 1);
              if ( v40 < 0 )
              {
                LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
                  1,
                  (unsigned int)v40,
                  "Unable to remove directory {}.",
                  lpFileName);
                if ( (v5 & 0x80000000) == 0 )
                  v5 = v41;
              }
            }
            v11 -= 24;
            v54[2] = v23;
            DeleteContext::~DeleteContext((DeleteContext *)v23);
          }
          else if ( FindFileData.cFileName[0] != 46
                 || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
          {
            if ( (FindFileData.dwFileAttributes & 0x410) == 0x10 )
            {
              v54[0] = 0;
              v35 = OpenFileRelativeToParent(
                      *(_QWORD *)v23,
                      (unsigned int)FindFileData.cFileName,
                      v25,
                      v26,
                      0,
                      (__int64)v54);
              v15 = v35;
              if ( (unsigned int)(v35 + 2147024894) <= 1
                || v35 == -2147024773
                || v35 == -2147022975
                || (v37 = (unsigned int)(v35 + 805306317), (unsigned int)v37 <= 1)
                || v35 == -805306310
                || v35 == -805305728 )
              {
                if ( (unsigned __int64)v54[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                {
                  if ( NtClose(v54[0]) < 0 )
                    __fastfail(7u);
                  v54[0] = 0;
                }
              }
              else
              {
                if ( v35 < 0 )
                {
                  LODWORD(v52) = v35;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogPartial<wchar_t [260]>(
                      v37,
                      v36,
                      "Failed to open {} for deletion",
                      FindFileData.cFileName);
                    v48 = (CRecursiveRemoveDirectory *)&v52;
                    v47 = &v48;
                    LOBYTE(v44) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v44,
                      3,
                      ": {}");
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x4F9,
                    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                    (const char *)v15,
                    (int)v47);
                  if ( (unsigned __int64)v54[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                  {
                    if ( NtClose(v54[0]) < 0 )
                      __fastfail(7u);
                    v54[0] = 0;
                  }
                  utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
                  if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                  {
                    if ( NtClose(Handle) < 0 )
                      __fastfail(7u);
                    Handle = 0;
                  }
                  return v15;
                }
                lpFileName[0] = 0;
                v38 = SczAllocConcat2Sz(lpFileName, *((_QWORD *)v23 + 1), FindFileData.cFileName);
                v13 = v38;
                if ( v38 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x4FC,
                    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                    (const char *)(unsigned int)v38,
                    (int)v47);
                  if ( lpFileName[0] )
                    operator delete((void *)(lpFileName[0] - 4));
                  if ( (unsigned __int64)v54[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                  {
                    if ( NtClose(v54[0]) < 0 )
                      __fastfail(7u);
                    v54[0] = 0;
                  }
                  utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
                  if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                  {
                    if ( NtClose(Handle) < 0 )
                      __fastfail(7u);
                    Handle = 0;
                  }
                  return v13;
                }
                v15 = SczEnsureBackslashTerminated(lpFileName);
                if ( (v15 & 0x80000000) != 0 )
                {
                  LODWORD(v52) = v15;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to backslash-terminate subdirectory path.");
                    v48 = (CRecursiveRemoveDirectory *)&v52;
                    v47 = &v48;
                    LOBYTE(v43) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v43,
                      3,
                      ": {}");
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x4FE,
                    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                    (const char *)v15,
                    (int)v47);
                  if ( lpFileName[0] )
                    operator delete((void *)(lpFileName[0] - 4));
                  if ( (unsigned __int64)v54[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                  {
                    if ( NtClose(v54[0]) < 0 )
                      __fastfail(7u);
                    v54[0] = 0;
                  }
                  utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
                  if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                  {
                    if ( NtClose(Handle) < 0 )
                      __fastfail(7u);
                    Handle = 0;
                  }
                  return v15;
                }
                if ( !(unsigned __int8)utl::vector<DeleteContext,utl::allocator<DeleteContext>>::emplace_back<Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>,0>(
                                         &v54[1],
                                         v54) )
                {
                  v5 = -2147024882;
                  LODWORD(v52) = -2147024882;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to add item to directory stack");
                    v48 = (CRecursiveRemoveDirectory *)&v52;
                    v47 = &v48;
                    LOBYTE(v42) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v42,
                      3,
                      ": {}");
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x508,
                    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                    (const char *)0x8007000ELL,
                    (int)v47);
                  if ( lpFileName[0] )
                    operator delete((void *)(lpFileName[0] - 4));
                  if ( (unsigned __int64)v54[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                  {
                    if ( NtClose(v54[0]) < 0 )
                      __fastfail(7u);
                    v54[0] = 0;
                  }
                  utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
                  if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                  {
                    if ( NtClose(Handle) < 0 )
                      __fastfail(7u);
                    Handle = 0;
                  }
                  return v5;
                }
                v11 = (char *)v54[2];
                v39 = *((_QWORD *)v54[2] - 2);
                if ( v39 )
                  operator delete((void *)(v39 - 8));
                *((LPCWSTR *)v11 - 2) = lpFileName[0];
                if ( (unsigned __int64)v54[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                {
                  if ( NtClose(v54[0]) < 0 )
                    __fastfail(7u);
                  v54[0] = 0;
                }
                v17 = (char *)v54[1];
              }
            }
            else
            {
              v30 = CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(
                      v18,
                      *(void **)v23,
                      FindFileData.cFileName,
                      v26);
              v33 = v30;
              if ( v30 < 0 )
              {
                LODWORD(v52) = v30;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogPartial<wchar_t [260]>(
                    v32,
                    v31,
                    "Unable to remove file {}.",
                    FindFileData.cFileName);
                  lpFileName[0] = (LPCWSTR)&v52;
                  v47 = lpFileName;
                  LOBYTE(v34) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v34,
                    1,
                    ": {0}");
                }
                if ( (v5 & 0x80000000) == 0 )
                  v5 = v33;
              }
            }
          }
          if ( v17 == v11 )
          {
            utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
            if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            {
              if ( NtClose(Handle) < 0 )
                __fastfail(7u);
              Handle = 0;
            }
            return v5;
          }
        }
        utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
        if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          if ( NtClose(Handle) < 0 )
            __fastfail(7u);
          Handle = 0;
        }
        return v5;
      }
      LODWORD(v52) = v14;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to backslash-terminate directory path.");
        v48 = (CRecursiveRemoveDirectory *)&v52;
        v47 = &v48;
        LOBYTE(v16) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v16,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x497,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)v15,
        (int)v47);
      utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(Handle) < 0 )
          __fastfail(7u);
        Handle = 0;
      }
      return v15;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x493,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)(unsigned int)v12,
        (int)v47);
      utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(&v54[1]);
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(Handle) < 0 )
          __fastfail(7u);
        Handle = 0;
      }
      return v13;
    }
  }
}

```

## disassembly

```asm
0x18003fec8  mov     rax, rsp
0x18003fecb  push    rbp
0x18003fecc  push    rsi
0x18003fecd  push    rdi
0x18003fece  push    r12
0x18003fed0  push    r13
0x18003fed2  push    r14
0x18003fed4  push    r15
0x18003fed6  lea     rbp, [rax-228h]
0x18003fedd  sub     rsp, 2F0h
0x18003fee4  mov     [rsp+320h+var_2D8], 0FFFFFFFFFFFFFFFEh
0x18003feed  mov     [rax+18h], rbx
0x18003fef1  mov     rax, cs:__security_cookie
0x18003fef8  xor     rax, rsp
0x18003fefb  mov     [rbp+220h+var_40], rax
0x18003ff02  mov     byte ptr [rsp+320h+var_2E8], r8b
0x18003ff07  mov     al, dl
0x18003ff09  mov     [rsp+320h+var_2F0], rcx
0x18003ff0e  mov     rdx, [rbp+220h+arg_20]
0x18003ff15  mov     [rsp+320h+var_2D0], rdx
0x18003ff1a  xor     r15d, r15d
0x18003ff1d  mov     [rsp+320h+Handle], r15
0x18003ff22  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003ff2a  movdqu  xmmword ptr [rsp+320h+var_2B8+8], xmm0
0x18003ff30  mov     [rbp+220h+var_2A0], 0FFFFFFFFFFFFFFFFh
0x18003ff38  test    rdx, rdx
0x18003ff3b  jnz     loc_18003FFEC
0x18003ff41  mov     esi, 80070057h
0x18003ff46  mov     dword ptr [rsp+320h+var_2C8], esi
0x18003ff4a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003ff51  test    rcx, rcx
0x18003ff54  jz      short loc_18003FF94
0x18003ff56  lea     r9, aNoDirectorySpe; "No directory specified"
0x18003ff5d  lea     ebx, [rdx+3]
0x18003ff60  mov     r8d, ebx
0x18003ff63  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18003ff68  lea     rax, [rsp+320h+var_2C8]
0x18003ff6d  mov     [rsp+320h+var_2F0], rax
0x18003ff72  lea     rax, [rsp+320h+var_2F0]
0x18003ff77  mov     qword ptr [rsp+320h+var_300], rax; int
0x18003ff7c  lea     r9, asc_1801CAFB4; ": {}"
0x18003ff83  mov     r8d, ebx
0x18003ff86  mov     dl, 1
0x18003ff88  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003ff8f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18003ff94  mov     rcx, [rbp+228h]; this
0x18003ff9b  mov     r9d, esi; char *
0x18003ff9e  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18003ffa5  mov     edx, 479h; void *
0x18003ffaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ffaf  lea     rcx, [rsp+320h+var_2B8+8]
0x18003ffb4  call    ??1?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@QEAA@XZ; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(void)
0x18003ffb9  nop
0x18003ffba  mov     rcx, [rsp+320h+Handle]; Handle
0x18003ffbf  lea     rax, [rcx-1]
0x18003ffc3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003ffc7  ja      short loc_18003FFE5
0x18003ffc9  call    cs:__imp_NtClose
0x18003ffd0  nop     dword ptr [rax+rax+00h]
0x18003ffd5  test    eax, eax
0x18003ffd7  jns     short loc_18003FFE0
0x18003ffd9  mov     ecx, 7
0x18003ffde  int     29h; Win8: RtlFailFast(ecx)
0x18003ffe0  mov     [rsp+320h+Handle], r15
0x18003ffe5  mov     eax, esi
0x18003ffe7  jmp     loc_180040B77
0x18003ffec  lea     rcx, [rsp+320h+Handle]
0x18003fff1  mov     [rsp+320h+var_2F8], rcx
0x18003fff6  mov     byte ptr [rsp+320h+var_300], al; int
0x18003fffa  mov     rcx, r9
0x18003fffd  call    OpenFileRelativeToParent
0x180040002  mov     esi, eax
0x180040004  lea     ecx, [rax+7FF8FFFEh]
0x18004000a  cmp     ecx, 1
0x18004000d  jbe     loc_180040B3F
0x180040013  cmp     eax, 8007007Bh
0x180040018  jz      loc_180040B3F
0x18004001e  cmp     eax, 80070781h
0x180040023  jz      loc_180040B3F
0x180040029  lea     ecx, [rax+2FFFFFCDh]
0x18004002f  cmp     ecx, 1
0x180040032  jbe     loc_180040B3F
0x180040038  cmp     eax, 0D000003Ah
0x18004003d  jz      loc_180040B3F
0x180040043  cmp     eax, 0D0000280h
0x180040048  jz      loc_180040B3F
0x18004004e  test    eax, eax
0x180040050  jns     loc_180040108
0x180040056  mov     dword ptr [rsp+320h+var_2C8], eax
0x18004005a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040061  test    rcx, rcx
0x180040064  jz      short loc_1800400B2
0x180040066  lea     rax, [rsp+320h+var_2D0]
0x18004006b  mov     qword ptr [rsp+320h+var_300], rax
0x180040070  lea     r9, aFailedToOpenFo; "Failed to open {} for deletion"
0x180040077  mov     ebx, 3
0x18004007c  mov     r8d, ebx
0x18004007f  xor     edx, edx
0x180040081  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180040086  lea     rax, [rsp+320h+var_2C8]
0x18004008b  mov     [rsp+320h+var_2F0], rax
0x180040090  lea     rax, [rsp+320h+var_2F0]
0x180040095  mov     qword ptr [rsp+320h+var_300], rax; int
0x18004009a  lea     r9, asc_1801CAFB4; ": {}"
0x1800400a1  mov     r8d, ebx
0x1800400a4  mov     dl, 1
0x1800400a6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800400ad  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800400b2  mov     rcx, [rbp+228h]; this
0x1800400b9  mov     r9d, esi; char *
0x1800400bc  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800400c3  mov     edx, 48Eh; void *
0x1800400c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800400cd  lea     rcx, [rsp+320h+var_2B8+8]
0x1800400d2  call    ??1?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@QEAA@XZ; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(void)
0x1800400d7  nop
0x1800400d8  mov     rcx, [rsp+320h+Handle]; Handle
0x1800400dd  lea     rax, [rcx-1]
0x1800400e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800400e5  ja      short loc_180040103
0x1800400e7  call    cs:__imp_NtClose
0x1800400ee  nop     dword ptr [rax+rax+00h]
0x1800400f3  test    eax, eax
0x1800400f5  jns     short loc_1800400FE
0x1800400f7  mov     ecx, 7
0x1800400fc  int     29h; Win8: RtlFailFast(ecx)
0x1800400fe  mov     [rsp+320h+Handle], r15
0x180040103  jmp     loc_18003FFE5
0x180040108  lea     rdx, [rsp+320h+Handle]
0x18004010d  lea     rcx, [rsp+320h+var_2B8+8]
0x180040112  call    ??$emplace_back@V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@$0A@@?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@QEAA_N$$QEAV?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Z; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::emplace_back<Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>,0>(Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)> &&)
0x180040117  test    al, al
0x180040119  jnz     loc_1800401CC
0x18004011f  mov     esi, 8007000Eh
0x180040124  mov     dword ptr [rsp+320h+var_2C8], esi
0x180040128  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004012f  test    rcx, rcx
0x180040132  jz      short loc_180040176
0x180040134  lea     r9, aFailedToAddIte; "Failed to add item to directory stack"
0x18004013b  mov     ebx, 3
0x180040140  mov     r8d, ebx
0x180040143  xor     edx, edx
0x180040145  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004014a  lea     rax, [rsp+320h+var_2C8]
0x18004014f  mov     [rsp+320h+var_2F0], rax
0x180040154  lea     rax, [rsp+320h+var_2F0]
0x180040159  mov     qword ptr [rsp+320h+var_300], rax; int
0x18004015e  lea     r9, asc_1801CAFB4; ": {}"
0x180040165  mov     r8d, ebx
0x180040168  mov     dl, 1
0x18004016a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180040171  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180040176  mov     rcx, [rbp+228h]; this
0x18004017d  mov     r9d, esi; char *
0x180040180  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180040187  mov     edx, 491h; void *
0x18004018c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040191  lea     rcx, [rsp+320h+var_2B8+8]
0x180040196  call    ??1?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@QEAA@XZ; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(void)
0x18004019b  nop
0x18004019c  mov     rcx, [rsp+320h+Handle]; Handle
0x1800401a1  lea     rax, [rcx-1]
0x1800401a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800401a9  ja      short loc_1800401C7
0x1800401ab  call    cs:__imp_NtClose
0x1800401b2  nop     dword ptr [rax+rax+00h]
0x1800401b7  test    eax, eax
0x1800401b9  jns     short loc_1800401C2
0x1800401bb  mov     ecx, 7
0x1800401c0  int     29h; Win8: RtlFailFast(ecx)
0x1800401c2  mov     [rsp+320h+Handle], r15
0x1800401c7  jmp     loc_18003FFE5
0x1800401cc  mov     r13, qword ptr [rsp+320h+var_2B8+10h]
0x1800401d1  mov     rdx, [rsp+320h+var_2D0]
0x1800401d6  lea     rcx, [r13-10h]
0x1800401da  call    SczAllocFromSz
0x1800401df  mov     ebx, eax
0x1800401e1  test    eax, eax
0x1800401e3  jns     short loc_18004023D
0x1800401e5  mov     rcx, [rbp+228h]; this
0x1800401ec  mov     r9d, eax; char *
0x1800401ef  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800401f6  mov     edx, 493h; void *
0x1800401fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040200  lea     rcx, [rsp+320h+var_2B8+8]
0x180040205  call    ??1?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@QEAA@XZ; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(void)
0x18004020a  nop
0x18004020b  mov     rcx, [rsp+320h+Handle]; Handle
0x180040210  lea     rax, [rcx-1]
0x180040214  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040218  ja      short loc_180040236
0x18004021a  call    cs:__imp_NtClose
0x180040221  nop     dword ptr [rax+rax+00h]
0x180040226  test    eax, eax
0x180040228  jns     short loc_180040231
0x18004022a  mov     ecx, 7
0x18004022f  int     29h; Win8: RtlFailFast(ecx)
0x180040231  mov     [rsp+320h+Handle], r15
0x180040236  mov     eax, ebx
0x180040238  jmp     loc_180040B77
0x18004023d  lea     rcx, [r13-10h]
0x180040241  call    SczEnsureBackslashTerminated
0x180040246  mov     r14d, eax
0x180040249  test    eax, eax
0x18004024b  jns     loc_1800402FC
0x180040251  mov     dword ptr [rsp+320h+var_2C8], eax
0x180040255  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004025c  test    rcx, rcx
0x18004025f  jz      short loc_1800402A3
0x180040261  lea     r9, aFailedToBacksl_0; "Failed to backslash-terminate directory"...
0x180040268  mov     ebx, 3
0x18004026d  mov     r8d, ebx
0x180040270  xor     edx, edx
0x180040272  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180040277  lea     rax, [rsp+320h+var_2C8]
0x18004027c  mov     [rsp+320h+var_2F0], rax
0x180040281  lea     rax, [rsp+320h+var_2F0]
0x180040286  mov     qword ptr [rsp+320h+var_300], rax; int
0x18004028b  lea     r9, asc_1801CAFB4; ": {}"
0x180040292  mov     r8d, ebx
0x180040295  mov     dl, 1
0x180040297  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004029e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800402a3  mov     rcx, [rbp+228h]; this
0x1800402aa  mov     r9d, r14d; char *
0x1800402ad  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800402b4  mov     edx, 497h; void *
0x1800402b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800402be  lea     rcx, [rsp+320h+var_2B8+8]
0x1800402c3  call    ??1?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@QEAA@XZ; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::~vector<DeleteContext,utl::allocator<DeleteContext>>(void)
0x1800402c8  nop
0x1800402c9  mov     rcx, [rsp+320h+Handle]; Handle
0x1800402ce  lea     rax, [rcx-1]
0x1800402d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800402d6  ja      short loc_1800402F4
0x1800402d8  call    cs:__imp_NtClose
0x1800402df  nop     dword ptr [rax+rax+00h]
0x1800402e4  test    eax, eax
0x1800402e6  jns     short loc_1800402EF
0x1800402e8  mov     ecx, 7
0x1800402ed  int     29h; Win8: RtlFailFast(ecx)
0x1800402ef  mov     [rsp+320h+Handle], r15
0x1800402f4  mov     eax, r14d
0x1800402f7  jmp     loc_180040B77
0x1800402fc  mov     edi, 7
0x180040301  mov     r12, qword ptr [rsp+320h+var_2B8+8]
0x180040306  mov     rbx, [rsp+320h+var_2F0]
0x18004030b  cmp     [rbx+20h], r15b
0x18004030f  jnz     loc_180040B06
0x180040315  mov     rcx, [rbx+18h]; hHandle
0x180040319  test    rcx, rcx
0x18004031c  jz      short loc_180040379
0x18004031e  xor     edx, edx; dwMilliseconds
0x180040320  call    cs:__imp_WaitForSingleObject
0x180040327  nop     dword ptr [rax+rax+00h]
0x18004032c  test    eax, 0FFFFFF7Fh
0x180040331  jz      short loc_180040369
0x180040333  cmp     eax, 0FFFFFFFFh
0x180040336  jnz     short loc_180040379
0x180040338  call    cs:__imp_GetLastError
0x18004033f  nop     dword ptr [rax+rax+00h]
0x180040344  test    eax, eax
0x180040346  jle     short loc_180040352
0x180040348  movzx   eax, ax
0x18004034b  or      eax, 80070000h
0x180040350  test    eax, eax
0x180040352  jns     short loc_180040379
0x180040354  lea     r8, aErrorGettingCa; "Error getting cancel event status"
0x18004035b  mov     edx, eax
0x18004035d  mov     ecx, 1
0x180040362  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180040367  jmp     short loc_180040379
0x180040369  lea     rcx, aRemoveDirector; "Remove directory cancelled"
0x180040370  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180040375  mov     byte ptr [rbx+20h], 1
0x180040379  cmp     [rbx+20h], r15b
0x18004037d  jnz     loc_180040B06
0x180040383  lea     r15, [r13-18h]
0x180040387  xor     edx, edx; Val
0x180040389  mov     r8d, 250h; Size
0x18004038f  lea     rcx, [rbp+220h+FindFileData]; void *
0x180040393  call    memset_0
0x180040398  mov     rcx, [r15+10h]; hFindFile
0x18004039c  lea     rax, [rcx-1]
0x1800403a0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800403a4  ja      short loc_1800403FA
0x1800403a6  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x1800403aa  call    cs:__imp_FindNextFileW
0x1800403b1  nop     dword ptr [rax+rax+00h]
0x1800403b6  xor     r14d, r14d
0x1800403b9  test    eax, eax
0x1800403bb  jnz     loc_180040467
0x1800403c1  mov     rcx, [r15+10h]; hFindFile
0x1800403c5  lea     rax, [rcx-1]
0x1800403c9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800403cd  ja      loc_180040467
0x1800403d3  call    cs:__imp_FindClose
0x1800403da  nop     dword ptr [rax+rax+00h]
0x1800403df  test    eax, eax
0x1800403e1  jnz     short loc_1800403F4
  ... truncated ...
```
