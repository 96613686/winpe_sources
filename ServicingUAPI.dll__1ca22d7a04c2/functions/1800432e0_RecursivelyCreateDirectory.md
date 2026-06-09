# RecursivelyCreateDirectory

- ea: `0x1800432e0`
- end: `0x1800437e2`
- name: `RecursivelyCreateDirectory`
- size: `1282`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800375fc`
- `0x1800432e0`
- `0x18006def0`
- `0x1800a2fcc`
- `0x1800aa4c8`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000636c`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x18001b0a4`
- `0x180022a18`
- `0x18003bdb4`
- `0x18003ddc8`
- `0x1800432e0`
- `0x180046348`
- `0x18004f088`
- `0x18004fcf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180043551`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180043551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043766`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004351e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180043756`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004351e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180043756`

## string_xrefs

- `0x180043346`: `No path specified`
- `0x18004358f`: `Cannot find parent for path: {}.`
- `0x18004366c`: `Failed to copy parent of path: {}`
- `0x1800434a6`: `Failed calling GetSystemSecurity`
- `0x18004370f`: `Failed to create path: {}`

## pseudocode

```c
__int64 __fastcall RecursivelyCreateDirectory(__int64 a1, struct _SECURITY_ATTRIBUTES *a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v6; // rdx
  bool *v7; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdx
  int SystemSecurity; // eax
  __int64 v14; // rdx
  const wchar_t *v15; // rbx
  wchar_t *v16; // rax
  __int64 v17; // rdx
  size_t v18; // r14
  unsigned __int64 v19; // r15
  wchar_t *v20; // rax
  wchar_t *v21; // rsi
  HRESULT v22; // eax
  unsigned int v23; // r14d
  __int64 v24; // rdx
  __int64 v25; // rdx
  int Directory; // eax
  __int64 v27; // rdx
  signed int LastError; // eax
  unsigned int v29; // edi
  void *p_lpPathName; // [rsp+20h] [rbp-49h]
  _BYTE v31[8]; // [rsp+30h] [rbp-39h] BYREF
  LPCWSTR lpPathName; // [rsp+38h] [rbp-31h] BYREF
  int v33[2]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v34; // [rsp+48h] [rbp-21h]
  __int64 v35; // [rsp+58h] [rbp-11h]
  __int64 v36; // [rsp+60h] [rbp-9h] BYREF
  __int64 v37; // [rsp+68h] [rbp-1h] BYREF
  __int128 v38; // [rsp+70h] [rbp+7h] BYREF
  __int64 v39; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v36 = a1;
  v39 = 0;
  lpPathName = 0;
  v38 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    LODWORD(v37) = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No path specified");
      lpPathName = (LPCWSTR)&v37;
      LOBYTE(v4) = 1;
      p_lpPathName = &lpPathName;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v4,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      (int)p_lpPathName);
    return (unsigned int)v3;
  }
  v3 = SczAllocFromSz(&lpPathName);
  if ( v3 < 0 )
  {
    v6 = 360;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v3,
      (int)p_lpPathName);
    goto LABEL_9;
  }
  v3 = PathPrefix(&lpPathName);
  if ( v3 < 0 )
  {
    v6 = 361;
    goto LABEL_8;
  }
  if ( !a2 )
  {
    v31[0] = 0;
    CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                          (Windows::WCP::Implementation::Rtl *)v31,
                          v7);
    v10 = CanSetSystemOwner;
    if ( CanSetSystemOwner < 0 )
    {
      LODWORD(v37) = CanSetSystemOwner;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed calling CanSetSystemOwner");
        *(_QWORD *)v33 = &v37;
        p_lpPathName = v33;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v11,
          3,
          ": {}");
      }
      v12 = 367;
LABEL_18:
      v3 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
             (const char *)v10,
             (int)p_lpPathName);
LABEL_9:
      if ( lpPathName )
        operator delete((void *)(lpPathName - 4));
      return (unsigned int)v3;
    }
    if ( v31[0] )
    {
      v37 = 0;
      SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                         (Windows::WCP::Implementation::Rtl *)&v37,
                         v9);
      v10 = SystemSecurity;
      if ( SystemSecurity < 0 )
      {
        LODWORD(v37) = SystemSecurity;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed calling GetSystemSecurity");
          *(_QWORD *)v33 = &v37;
          p_lpPathName = v33;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v14,
            3,
            ": {}");
        }
        v12 = 373;
        goto LABEL_18;
      }
      a2 = (struct _SECURITY_ATTRIBUTES *)&v38;
      *((_QWORD *)&v34 + 1) = v37;
      *(_QWORD *)&v34 = 24;
      v35 = 0;
      v39 = 0;
      v38 = v34;
    }
  }
  v15 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, a2) && GetLastError() != 183 )
  {
    v16 = wcsrchr(v15, 0x5Cu);
    if ( !v16 )
    {
      LODWORD(v37) = -2147024893;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Cannot find parent for path: {}.",
          &v36);
        *(_QWORD *)v33 = &v37;
        LOBYTE(v17) = 1;
        p_lpPathName = v33;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v17,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x188,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
        (const char *)0x80070003LL,
        (int)p_lpPathName);
      if ( v15 )
        operator delete((void *)(v15 - 4));
      return 2147942403LL;
    }
    v18 = v16 - v15;
    v19 = -1;
    v20 = (wchar_t *)operator new[](saturated_mul(v18 + 1, 2u));
    v21 = v20;
    do
      ++v19;
    while ( v15[v19] );
    if ( v18 <= v19 )
    {
      v22 = StringCchCopyNW(v20, v18 + 1, v15, v18);
      v23 = v22;
      if ( v22 < 0 )
      {
        LODWORD(v37) = v22;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          *(_QWORD *)v33 = v15;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to copy parent of path: {}",
            v33);
          lpPathName = (LPCWSTR)&v37;
          LOBYTE(v24) = 1;
          p_lpPathName = &lpPathName;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v24,
            3,
            ": {}");
        }
        v25 = 406;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v23,
          (int)p_lpPathName);
        operator delete(v21);
        if ( v15 )
          operator delete((void *)(v15 - 4));
        return v23;
      }
    }
    Directory = RecursivelyCreateDirectory(v21, a2);
    v23 = Directory;
    if ( Directory < 0 )
    {
      LODWORD(v37) = Directory;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        *(_QWORD *)v33 = v21;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to create path: {}",
          v33);
        lpPathName = (LPCWSTR)&v37;
        LOBYTE(v27) = 1;
        p_lpPathName = &lpPathName;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v27,
          3,
          ": {}");
      }
      v25 = 408;
      goto LABEL_40;
    }
    if ( !CreateDirectoryW(v15, a2) )
    {
      LastError = GetLastError();
      v29 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v29 = (unsigned __int16)LastError | 0x80070000;
        operator delete(v21);
        if ( v15 )
          operator delete((void *)(v15 - 4));
        return v29;
      }
    }
    operator delete(v21);
  }
  if ( v15 )
    operator delete((void *)(v15 - 4));
  return 0;
}

```

## disassembly

```asm
0x1800432e0  mov     [rsp-8+arg_10], rbx
0x1800432e5  push    rbp
0x1800432e6  push    rsi
0x1800432e7  push    rdi
0x1800432e8  push    r12
0x1800432ea  push    r13
0x1800432ec  push    r14
0x1800432ee  push    r15
0x1800432f0  lea     rbp, [rsp-27h]
0x1800432f5  sub     rsp, 90h
0x1800432fc  mov     rax, cs:__security_cookie
0x180043303  xor     rax, rsp
0x180043306  mov     [rbp+57h+var_38], rax
0x18004330a  xor     eax, eax
0x18004330c  mov     [rbp+57h+var_60], rcx
0x180043310  xor     r13d, r13d
0x180043313  mov     [rbp+57h+var_40], rax
0x180043317  mov     [rbp+57h+lpPathName], r13
0x18004331b  xorps   xmm0, xmm0
0x18004331e  mov     rdi, rdx
0x180043321  movups  [rbp+57h+var_50], xmm0
0x180043325  test    rcx, rcx
0x180043328  jnz     short loc_18004339A
0x18004332a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180043331  mov     ebx, 80070057h
0x180043336  mov     dword ptr [rbp+57h+var_58], ebx
0x180043339  test    rcx, rcx
0x18004333c  jz      short loc_18004337B
0x18004333e  lea     edi, [rax+3]
0x180043341  xor     edx, edx
0x180043343  mov     r8d, edi
0x180043346  lea     r9, aNoPathSpecifie; "No path specified"
0x18004334d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180043352  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180043359  lea     rax, [rbp+57h+var_58]
0x18004335d  mov     [rbp+57h+lpPathName], rax
0x180043361  lea     r9, asc_1801CAFB4; ": {}"
0x180043368  lea     rax, [rbp+57h+lpPathName]
0x18004336c  mov     r8d, edi
0x18004336f  mov     dl, 1
0x180043371  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180043376  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004337b  mov     rcx, [rbp+5Fh]; this
0x18004337f  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180043386  mov     r9d, ebx; char *
0x180043389  mov     edx, 163h; void *
0x18004338e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043393  mov     eax, ebx
0x180043395  jmp     loc_1800437BA
0x18004339a  mov     rdx, rcx
0x18004339d  lea     rcx, [rbp+57h+lpPathName]
0x1800433a1  call    SczAllocFromSz
0x1800433a6  mov     ebx, eax
0x1800433a8  test    eax, eax
0x1800433aa  jns     short loc_1800433D8
0x1800433ac  mov     edx, 168h; void *
0x1800433b1  mov     rcx, [rbp+5Fh]; this
0x1800433b5  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800433bc  mov     r9d, ebx; char *
0x1800433bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800433c4  mov     rcx, [rbp+57h+lpPathName]
0x1800433c8  test    rcx, rcx
0x1800433cb  jz      short loc_180043393
0x1800433cd  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800433d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800433d6  jmp     short loc_180043393
0x1800433d8  lea     rcx, [rbp+57h+lpPathName]
0x1800433dc  call    PathPrefix
0x1800433e1  mov     ebx, eax
0x1800433e3  test    eax, eax
0x1800433e5  jns     short loc_1800433EE
0x1800433e7  mov     edx, 169h
0x1800433ec  jmp     short loc_1800433B1
0x1800433ee  test    rdi, rdi
0x1800433f1  jnz     loc_180043514
0x1800433f7  lea     rcx, [rbp+57h+var_90]; this
0x1800433fb  mov     [rbp+57h+var_90], r13b
0x1800433ff  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x180043404  mov     ebx, eax
0x180043406  test    eax, eax
0x180043408  jns     short loc_180043475
0x18004340a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180043411  mov     dword ptr [rbp+57h+var_58], eax
0x180043414  test    rcx, rcx
0x180043417  jz      short loc_180043456
0x180043419  mov     edi, 3
0x18004341e  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x180043425  mov     r8d, edi
0x180043428  xor     edx, edx
0x18004342a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004342f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180043436  lea     rax, [rbp+57h+var_58]
0x18004343a  mov     qword ptr [rbp+57h+var_80], rax
0x18004343e  lea     r9, asc_1801CAFB4; ": {}"
0x180043445  lea     rax, [rbp+57h+var_80]
0x180043449  mov     r8d, edi
0x18004344c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180043451  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x180043456  mov     edx, 16Fh; void *
0x18004345b  mov     rcx, [rbp+5Fh]; this
0x18004345f  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180043466  mov     r9d, ebx; char *
0x180043469  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004346e  mov     ebx, eax
0x180043470  jmp     loc_1800433C4
0x180043475  cmp     [rbp+57h+var_90], r13b
0x180043479  jz      loc_180043514
0x18004347f  lea     rcx, [rbp+57h+var_58]; this
0x180043483  mov     [rbp+57h+var_58], r13
0x180043487  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x18004348c  mov     ebx, eax
0x18004348e  test    eax, eax
0x180043490  jns     short loc_1800434E8
0x180043492  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180043499  mov     dword ptr [rbp+57h+var_58], eax
0x18004349c  test    rcx, rcx
0x18004349f  jz      short loc_1800434DE
0x1800434a1  mov     edi, 3
0x1800434a6  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x1800434ad  mov     r8d, edi
0x1800434b0  xor     edx, edx
0x1800434b2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800434b7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800434be  lea     rax, [rbp+57h+var_58]
0x1800434c2  mov     qword ptr [rbp+57h+var_80], rax
0x1800434c6  lea     r9, asc_1801CAFB4; ": {}"
0x1800434cd  lea     rax, [rbp+57h+var_80]
0x1800434d1  mov     r8d, edi
0x1800434d4  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800434d9  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1800434de  mov     edx, 175h
0x1800434e3  jmp     loc_18004345B
0x1800434e8  mov     rax, [rbp+57h+var_58]
0x1800434ec  lea     rdi, [rbp+57h+var_50]
0x1800434f0  mov     qword ptr [rbp+57h+var_78+8], rax
0x1800434f4  xor     eax, eax
0x1800434f6  mov     qword ptr [rbp+57h+var_78], 18h
0x1800434fe  movups  xmm0, [rbp+57h+var_78]
0x180043502  mov     [rbp+57h+var_68], rax
0x180043506  movsd   xmm1, [rbp+57h+var_68]
0x18004350b  movsd   [rbp+57h+var_40], xmm1
0x180043510  movups  [rbp+57h+var_50], xmm0
0x180043514  mov     rbx, [rbp+57h+lpPathName]
0x180043518  mov     rdx, rdi; lpSecurityAttributes
0x18004351b  mov     rcx, rbx; lpPathName
0x18004351e  call    cs:__imp_CreateDirectoryW
0x180043525  nop     dword ptr [rax+rax+00h]
0x18004352a  test    eax, eax
0x18004352c  jnz     loc_1800437AA
0x180043532  call    cs:__imp_GetLastError
0x180043539  nop     dword ptr [rax+rax+00h]
0x18004353e  cmp     eax, 0B7h
0x180043543  jz      loc_1800437AA
0x180043549  mov     edx, 5Ch ; '\'; Ch
0x18004354e  mov     rcx, rbx; Str
0x180043551  call    cs:__imp_wcsrchr
0x180043558  nop     dword ptr [rax+rax+00h]
0x18004355d  mov     r14, rax
0x180043560  test    rax, rax
0x180043563  jnz     loc_1800435F1
0x180043569  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180043570  mov     esi, 80070003h
0x180043575  mov     dword ptr [rbp+57h+var_58], esi
0x180043578  test    rcx, rcx
0x18004357b  jz      short loc_1800435C4
0x18004357d  lea     rax, [rbp+57h+var_60]
0x180043581  xor     edx, edx
0x180043583  lea     edi, [r14+3]
0x180043587  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004358c  mov     r8d, edi
0x18004358f  lea     r9, aCannotFindPare; "Cannot find parent for path: {}."
0x180043596  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004359b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800435a2  lea     rax, [rbp+57h+var_58]
0x1800435a6  mov     qword ptr [rbp+57h+var_80], rax
0x1800435aa  lea     r9, asc_1801CAFB4; ": {}"
0x1800435b1  lea     rax, [rbp+57h+var_80]
0x1800435b5  mov     r8d, edi
0x1800435b8  mov     dl, 1
0x1800435ba  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800435bf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800435c4  mov     rcx, [rbp+5Fh]; this
0x1800435c8  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800435cf  mov     r9d, esi; char *
0x1800435d2  mov     edx, 188h; void *
0x1800435d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800435dc  test    rbx, rbx
0x1800435df  jz      short loc_1800435EA
0x1800435e1  lea     rcx, [rbx-8]; Block
0x1800435e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800435ea  mov     eax, esi
0x1800435ec  jmp     loc_1800437BA
0x1800435f1  sub     r14, rbx
0x1800435f4  mov     eax, 2
0x1800435f9  sar     r14, 1
0x1800435fc  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180043603  lea     r12, [r14+1]
0x180043607  mul     r12
0x18004360a  cmovb   rax, r15
0x18004360e  mov     rcx, rax; unsigned __int64
0x180043611  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180043616  mov     rsi, rax
0x180043619  inc     r15
0x18004361c  cmp     [rbx+r15*2], r13w
0x180043621  jnz     short loc_180043619
0x180043623  cmp     r14, r15
0x180043626  ja      loc_1800436D9
0x18004362c  mov     r9, r14; cchToCopy
0x18004362f  mov     r8, rbx; pszSrc
0x180043632  mov     rdx, r12; cchDest
0x180043635  mov     rcx, rsi; pszDest
0x180043638  call    StringCchCopyNW
0x18004363d  mov     r14d, eax
0x180043640  test    eax, eax
0x180043642  jns     loc_1800436D9
0x180043648  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004364f  mov     dword ptr [rbp+57h+var_58], eax
0x180043652  test    rcx, rcx
0x180043655  jz      short loc_1800436A3
0x180043657  lea     rax, [rbp+57h+var_80]
0x18004365b  mov     qword ptr [rbp+57h+var_80], rbx
0x18004365f  mov     edi, 3
0x180043664  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180043669  mov     r8d, edi
0x18004366c  lea     r9, aFailedToCopyPa; "Failed to copy parent of path: {}"
0x180043673  xor     edx, edx
0x180043675  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004367a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180043681  lea     rax, [rbp+57h+var_58]
0x180043685  mov     [rbp+57h+lpPathName], rax
0x180043689  lea     r9, asc_1801CAFB4; ": {}"
0x180043690  lea     rax, [rbp+57h+lpPathName]
0x180043694  mov     r8d, edi
0x180043697  mov     dl, 1
0x180043699  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004369e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800436a3  mov     edx, 196h; void *
0x1800436a8  mov     rcx, [rbp+5Fh]; this
0x1800436ac  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1800436b3  mov     r9d, r14d; char *
0x1800436b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800436bb  mov     rcx, rsi; Block
0x1800436be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800436c3  test    rbx, rbx
0x1800436c6  jz      short loc_1800436D1
0x1800436c8  lea     rcx, [rbx-8]; Block
0x1800436cc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800436d1  mov     eax, r14d
0x1800436d4  jmp     loc_1800437BA
0x1800436d9  mov     rdx, rdi
0x1800436dc  mov     rcx, rsi
0x1800436df  call    RecursivelyCreateDirectory
0x1800436e4  mov     r14d, eax
0x1800436e7  test    eax, eax
0x1800436e9  jns     short loc_180043750
0x1800436eb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800436f2  mov     dword ptr [rbp+57h+var_58], eax
0x1800436f5  test    rcx, rcx
0x1800436f8  jz      short loc_180043746
0x1800436fa  lea     rax, [rbp+57h+var_80]
0x1800436fe  mov     qword ptr [rbp+57h+var_80], rsi
0x180043702  mov     edi, 3
0x180043707  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004370c  mov     r8d, edi
0x18004370f  lea     r9, aFailedToCreate_0; "Failed to create path: {}"
0x180043716  xor     edx, edx
0x180043718  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004371d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180043724  lea     rax, [rbp+57h+var_58]
0x180043728  mov     [rbp+57h+lpPathName], rax
0x18004372c  lea     r9, asc_1801CAFB4; ": {}"
0x180043733  lea     rax, [rbp+57h+lpPathName]
0x180043737  mov     r8d, edi
0x18004373a  mov     dl, 1
0x18004373c  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180043741  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180043746  mov     edx, 198h
0x18004374b  jmp     loc_1800436A8
0x180043750  mov     rdx, rdi; lpSecurityAttributes
0x180043753  mov     rcx, rbx; lpPathName
0x180043756  call    cs:__imp_CreateDirectoryW
0x18004375d  nop     dword ptr [rax+rax+00h]
0x180043762  test    eax, eax
0x180043764  jnz     short loc_1800437A2
0x180043766  call    cs:__imp_GetLastError
0x18004376d  nop     dword ptr [rax+rax+00h]
0x180043772  mov     edi, eax
0x180043774  cmp     eax, 0B7h
0x180043779  jz      short loc_1800437A2
0x18004377b  test    eax, eax
0x18004377d  jle     short loc_180043788
0x18004377f  movzx   edi, ax
0x180043782  or      edi, 80070000h
0x180043788  mov     rcx, rsi; Block
0x18004378b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180043790  test    rbx, rbx
0x180043793  jz      short loc_18004379E
0x180043795  lea     rcx, [rbx-8]; Block
0x180043799  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004379e  mov     eax, edi
  ... truncated ...
```
