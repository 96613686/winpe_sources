# PrepareSandboxForInboxUseOneCore(wchar_t const * const,wchar_t *,unsigned __int64)

- ea: `0x180021c88`
- end: `0x180022418`
- name: `?PrepareSandboxForInboxUseOneCore@@YAXQEB_WPEA_W_K@Z`
- size: `1936`
- prototype: `void __fastcall(const wchar_t *const, wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f310`

## callees

- `0x1800031d0`
- `0x180008a90`
- `0x180009750`
- `0x18000c2dc`
- `0x18000c468`
- `0x18000ccb8`
- `0x18000f5cc`
- `0x18000f614`
- `0x18000f874`
- `0x1800126b8`
- `0x180016558`
- `0x18001675c`
- `0x18001b0a4`
- `0x18001d650`
- `0x180021c88`
- `0x18002bc54`
- `0x18002c100`
- `0x18002c298`
- `0x18002c7e8`
- `0x18002d49c`
- `0x18002dd20`
- `0x18002ea4c`
- `0x18002f428`
- `0x18004e028`
- `0x18004e0d4`
- `0x1801b31e0`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222dc`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800222cc`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800222cc`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x180022153`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x180022226`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x180022153`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x180022226`

## string_xrefs

- `0x180021ddb`: `UpdateAPI.dll`
- `0x180021d40`: `Failed to get current running path`
- `0x180021e34`: `GetRootPath`
- `0x180021ef9`: `\Windows\ImageUpdate\CompDBs`
- `0x180021d8c`: `UpdateAgent.dll`
- `0x18002234b`: `Provided sandbox directory does not exist or is not accessible.`
- `0x180021f92`: `Failed to acquire required privileges`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PrepareSandboxForInboxUseOneCore(const wchar_t *const a1, wchar_t *a2, unsigned __int64 a3)
{
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rcx
  int RunningDllPath; // eax
  int v10; // edi
  __int64 v11; // rdx
  HMODULE v12; // rax
  const wchar_t *v13; // rax
  __int64 v14; // rax
  int LibraryAndFunction; // eax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // eax
  int v21; // edi
  __int64 v22; // rdx
  __int64 v23; // rax
  const wchar_t *v24; // rax
  const wchar_t *v25; // rax
  int AllFilesAndDirectories; // eax
  LPCWSTR v27; // rbx
  LPCWSTR v28; // rdi
  const wchar_t *v29; // rcx
  const wchar_t *FileName; // rax
  __int64 v31; // rcx
  _QWORD *v32; // rax
  const WCHAR *v33; // rax
  const WCHAR *v34; // rdx
  const WCHAR *v35; // rcx
  const char *v36; // r9
  const wchar_t *v37; // rcx
  const wchar_t *v38; // rax
  _QWORD *v39; // rax
  LPCWSTR *v40; // rax
  const WCHAR *v41; // rdx
  const WCHAR *v42; // rcx
  const char *v43; // r9
  const wchar_t *v44; // r8
  int v45; // eax
  unsigned int v46; // eax
  void *v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  const wchar_t *v49; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+38h] [rbp-C8h]
  int v51[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+48h] [rbp-B8h]
  HMODULE hLibModule[3]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR v54[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+78h] [rbp-88h]
  unsigned __int64 v56; // [rsp+80h] [rbp-80h]
  _QWORD v57[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v58; // [rsp+98h] [rbp-68h]
  unsigned __int64 v59; // [rsp+A0h] [rbp-60h]
  __int128 v60; // [rsp+A8h] [rbp-58h] BYREF
  HMODULE v61; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v62; // [rsp+C0h] [rbp-40h]
  LPCWSTR lpSymlinkFileName[3]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v64; // [rsp+E0h] [rbp-20h]
  __int128 v65; // [rsp+E8h] [rbp-18h] BYREF
  __m128i v66; // [rsp+F8h] [rbp-8h]
  __int64 v67; // [rsp+108h] [rbp+8h] BYREF
  char v68; // [rsp+110h] [rbp+10h]
  LPCWSTR lpTargetFileName[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v70; // [rsp+128h] [rbp+28h]
  LPCWSTR v71[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v72; // [rsp+148h] [rbp+48h]
  __int128 v73; // [rsp+150h] [rbp+50h] BYREF
  __m128i si128; // [rsp+160h] [rbp+60h]
  _WORD v75[2048]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+11B8h] [rbp+10B8h]

  hLibModule[2] = (HMODULE)-2LL;
  *(_QWORD *)v51 = a1;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v52 = v7;
  if ( !(unsigned __int8)DirectoryExists(v51) )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
      LogAdapter::Logger::Log<>(v8, 3, "Provided sandbox directory does not exist or is not accessible.");
    v46 = EnsureNTSTATUS<long>(2147942403LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D9,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      (const char *)v46,
      (int)v47);
  }
  v60 = 0;
  v61 = 0;
  v62 = 7;
  LOWORD(v60) = 0;
  RunningDllPath = GetRunningDllPath(&v60);
  v10 = RunningDllPath;
  if ( RunningDllPath < 0 )
  {
    LODWORD(v54[0]) = RunningDllPath;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get current running path");
      hLibModule[0] = (HMODULE)v54;
      v47 = hLibModule;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v11,
        3,
        ": {}");
    }
  }
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5DC,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      (const char *)(unsigned int)v10,
      (int)v47);
  *(_QWORD *)v51 = L"UpdateAgent.dll";
  v52 = 15;
  v12 = (HMODULE)&v60;
  if ( v62 > 7 )
    v12 = (HMODULE)v60;
  hLibModule[0] = v12;
  hLibModule[1] = v61;
  CreatePath(v71, hLibModule, v51);
  hLibModule[0] = 0;
  v54[0] = 0;
  *(_QWORD *)v51 = L"UpdateAPI.dll";
  v52 = 13;
  v13 = (const wchar_t *)&v60;
  if ( v62 > 7 )
    v13 = (const wchar_t *)v60;
  v49 = v13;
  v50 = (__int64)v61;
  v14 = CreatePath(&v73, &v49, v51);
  if ( *(_QWORD *)(v14 + 24) > 7u )
    v14 = *(_QWORD *)v14;
  LibraryAndFunction = LoadLibraryAndFunction(
                         (const wchar_t *const)v14,
                         "GetRootPath",
                         hLibModule,
                         (__int64 (**)(void))v54);
  if ( LibraryAndFunction < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E6,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      (const char *)(unsigned int)LibraryAndFunction,
      (int)v47);
  std::wstring::~wstring(&v73);
  v73 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v73) = 0;
  v65 = 0;
  v66 = si128;
  LOWORD(v65) = 0;
  ((void (__fastcall *)(const wchar_t *, _WORD *, __int64))v54[0])(L"MAINOS", v75, 2048);
  v49 = L"\\Windows";
  v50 = 8;
  *(_QWORD *)v51 = v75;
  v16 = -1;
  do
    ++v16;
  while ( v75[v16] );
  v52 = v16;
  v17 = CreatePath(lpSymlinkFileName, v51, &v49);
  std::wstring::operator=(&v73, v17);
  std::wstring::~wstring(lpSymlinkFileName);
  v49 = L"\\Windows\\ImageUpdate\\CompDBs";
  v50 = 28;
  *(_QWORD *)v51 = v75;
  v18 = -1;
  do
    ++v18;
  while ( v75[v18] );
  v52 = v18;
  v19 = CreatePath(lpSymlinkFileName, v51, &v49);
  std::wstring::operator=(&v65, v19);
  std::wstring::~wstring(lpSymlinkFileName);
  v67 = 0;
  v68 = 0;
  v49 = (const wchar_t *)&RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
  v50 = 3;
  v20 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v67, &v49);
  v21 = v20;
  if ( v20 < 0 )
  {
    LODWORD(v54[0]) = v20;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to acquire required privileges");
      *(_QWORD *)v51 = v54;
      v47 = v51;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v22,
        3,
        ": {}");
    }
  }
  if ( v21 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x5F2,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      (const char *)(unsigned int)v21,
      (int)v47);
  v49 = L"metadata";
  v50 = 8;
  *(_QWORD *)v51 = a1;
  v23 = -1;
  do
    ++v23;
  while ( a1[v23] );
  v52 = v23;
  CreatePath(v57, v51, &v49);
  v24 = (const wchar_t *)v57;
  if ( v59 > 7 )
    v24 = (const wchar_t *)v57[0];
  v49 = v24;
  v50 = v58;
  EnsureDirectoryExistsHr(&v49);
  *(_OWORD *)lpTargetFileName = 0;
  v70 = 0;
  wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v51);
  v25 = (const wchar_t *)&v65;
  if ( v66.m128i_i64[1] > 7uLL )
    v25 = (const wchar_t *)v65;
  v49 = v25;
  v50 = v66.m128i_i64[0];
  AllFilesAndDirectories = GetAllFilesAndDirectories(
                             (unsigned int)&v49,
                             (unsigned int)v51,
                             0,
                             (unsigned int)lpTargetFileName,
                             0);
  if ( AllFilesAndDirectories < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x604,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      (const char *)(unsigned int)AllFilesAndDirectories,
      v48);
  v27 = lpTargetFileName[0];
  v28 = lpTargetFileName[1];
  while ( v27 != v28 )
  {
    if ( *((_QWORD *)v27 + 3) <= 7u )
      v29 = v27;
    else
      v29 = *(const wchar_t **)v27;
    FileName = GetFileName(v29);
    v49 = FileName;
    v31 = -1;
    do
      ++v31;
    while ( FileName[v31] );
    v50 = v31;
    v32 = v57;
    if ( v59 > 7 )
      v32 = (_QWORD *)v57[0];
    *(_QWORD *)v51 = v32;
    v52 = v58;
    CreatePath(lpSymlinkFileName, v51, &v49);
    v33 = (const WCHAR *)lpSymlinkFileName;
    if ( v64 > 7 )
      v33 = lpSymlinkFileName[0];
    v54[0] = v33;
    v54[1] = lpSymlinkFileName[2];
    SetAttrAndDeleteFile(v54);
    if ( *((_QWORD *)v27 + 3) <= 7u )
      v34 = v27;
    else
      v34 = *(const WCHAR **)v27;
    v35 = (const WCHAR *)lpSymlinkFileName;
    if ( v64 > 7 )
      v35 = lpSymlinkFileName[0];
    if ( !CreateSymbolicLinkW(v35, v34, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x610,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
        v36);
    std::wstring::~wstring(lpSymlinkFileName);
    v27 += 16;
  }
  v37 = (const wchar_t *)v71;
  if ( v72 > 7 )
    v37 = v71[0];
  v38 = GetFileName(v37);
  v49 = v38;
  do
    ++v6;
  while ( v38[v6] );
  v50 = v6;
  v39 = v57;
  if ( v59 > 7 )
    v39 = (_QWORD *)v57[0];
  *(_QWORD *)v51 = v39;
  v52 = v58;
  CreatePath(v54, v51, &v49);
  v40 = v54;
  if ( v56 > 7 )
    v40 = (LPCWSTR *)v54[0];
  v49 = (const wchar_t *)v40;
  v50 = v55;
  SetAttrAndDeleteFile(&v49);
  v41 = (const WCHAR *)v71;
  if ( v72 > 7 )
    v41 = v71[0];
  v42 = (const WCHAR *)v54;
  if ( v56 > 7 )
    v42 = v54[0];
  if ( !CreateSymbolicLinkW(v42, v41, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x61D,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      v43);
  if ( a2 )
  {
    if ( a3 < v55 + 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x621,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
        (const char *)0x8007007ALL,
        v48);
    *a2 = 0;
    v44 = (const wchar_t *)v54;
    if ( v56 > 7 )
      v44 = v54[0];
    v45 = StringCchCopyW(a2, a3, v44);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x624,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
        (const char *)(unsigned int)v45,
        v48);
  }
  std::wstring::~wstring(v54);
  std::vector<std::wstring>::_Tidy(lpTargetFileName);
  std::wstring::~wstring(v57);
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v67);
  std::wstring::~wstring(&v65);
  std::wstring::~wstring(&v73);
  if ( hLibModule[0] && !FreeLibrary(hLibModule[0]) )
  {
    GetLastError();
    __fastfail(7u);
  }
  std::wstring::~wstring(v71);
  std::wstring::~wstring(&v60);
}

```

## disassembly

```asm
0x180021c88  push    rbp
0x180021c8a  push    rsi
0x180021c8b  push    rdi
0x180021c8c  push    r12
0x180021c8e  push    r13
0x180021c90  push    r14
0x180021c92  push    r15
0x180021c94  lea     rbp, [rsp-1080h]
0x180021c9c  mov     eax, 1180h
0x180021ca1  call    _alloca_probe
0x180021ca6  sub     rsp, rax
0x180021ca9  mov     [rsp+11B0h+var_1150], 0FFFFFFFFFFFFFFFEh
0x180021cb2  mov     [rsp+11B0h+arg_0], rbx
0x180021cba  mov     rax, cs:__security_cookie
0x180021cc1  xor     rax, rsp
0x180021cc4  mov     [rbp+10B0h+var_40], rax
0x180021ccb  mov     r12, r8
0x180021cce  mov     r15, rdx
0x180021cd1  mov     r14, rcx
0x180021cd4  mov     qword ptr [rsp+11B0h+var_1170], rcx
0x180021cd9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180021cdd  mov     rax, rsi
0x180021ce0  xor     r13d, r13d
0x180021ce3  inc     rax
0x180021ce6  cmp     [rcx+rax*2], r13w
0x180021ceb  jnz     short loc_180021CE3
0x180021ced  mov     [rsp+11B0h+var_1168], rax
0x180021cf2  lea     rcx, [rsp+11B0h+var_1170]
0x180021cf7  call    ?DirectoryExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; DirectoryExists(wil::basic_zstring_view<wchar_t> const &)
0x180021cfc  test    al, al
0x180021cfe  jz      loc_180022342
0x180021d04  xorps   xmm0, xmm0
0x180021d07  movups  [rbp+10B0h+var_1108], xmm0
0x180021d0b  mov     [rbp+10B0h+var_10F8], r13
0x180021d0f  mov     [rbp+10B0h+var_10F0], 7
0x180021d17  mov     word ptr [rbp+10B0h+var_1108], r13w
0x180021d1c  lea     rcx, [rbp+10B0h+var_1108]
0x180021d20  call    ?GetRunningDllPath@@YAJPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetRunningDllPath(std::wstring *)
0x180021d25  mov     edi, eax
0x180021d27  mov     ebx, 3
0x180021d2c  test    eax, eax
0x180021d2e  jns     short loc_180021D7D
0x180021d30  mov     dword ptr [rsp+11B0h+var_1148], eax
0x180021d34  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180021d3b  test    rcx, rcx
0x180021d3e  jz      short loc_180021D7D
0x180021d40  lea     r9, aFailedToGetCur_1; "Failed to get current running path"
0x180021d47  mov     r8d, ebx
0x180021d4a  xor     edx, edx
0x180021d4c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180021d51  lea     rax, [rsp+11B0h+var_1148]
0x180021d56  mov     [rsp+11B0h+hLibModule], rax
0x180021d5b  lea     rax, [rsp+11B0h+hLibModule]
0x180021d60  mov     qword ptr [rsp+11B0h+var_1190], rax; int
0x180021d65  lea     r9, asc_1801CAFB4; ": {}"
0x180021d6c  mov     r8d, ebx
0x180021d6f  mov     dl, 1
0x180021d71  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180021d78  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180021d7d  mov     rcx, [rbp+10B8h]; this
0x180021d84  test    edi, edi
0x180021d86  js      loc_180022382
0x180021d8c  lea     rax, aUpdateagentDll; "UpdateAgent.dll"
0x180021d93  mov     qword ptr [rsp+11B0h+var_1170], rax
0x180021d98  mov     [rsp+11B0h+var_1168], 0Fh
0x180021da1  lea     rax, [rbp+10B0h+var_1108]
0x180021da5  cmp     [rbp+10B0h+var_10F0], 7
0x180021daa  cmova   rax, qword ptr [rbp+10B0h+var_1108]
0x180021daf  mov     [rsp+11B0h+hLibModule], rax
0x180021db4  mov     rax, [rbp+10B0h+var_10F8]
0x180021db8  mov     [rsp+11B0h+var_1158], rax
0x180021dbd  lea     r8, [rsp+11B0h+var_1170]
0x180021dc2  lea     rdx, [rsp+11B0h+hLibModule]
0x180021dc7  lea     rcx, [rbp+10B0h+var_1080]
0x180021dcb  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180021dd0  nop
0x180021dd1  mov     [rsp+11B0h+hLibModule], r13
0x180021dd6  mov     [rsp+11B0h+var_1148], r13
0x180021ddb  lea     rax, aUpdateapiDll_0; "UpdateAPI.dll"
0x180021de2  mov     qword ptr [rsp+11B0h+var_1170], rax
0x180021de7  mov     [rsp+11B0h+var_1168], 0Dh
0x180021df0  lea     rax, [rbp+10B0h+var_1108]
0x180021df4  cmp     [rbp+10B0h+var_10F0], 7
0x180021df9  cmova   rax, qword ptr [rbp+10B0h+var_1108]
0x180021dfe  mov     [rsp+11B0h+var_1180], rax
0x180021e03  mov     rax, [rbp+10B0h+var_10F8]
0x180021e07  mov     [rsp+11B0h+var_1178], rax
0x180021e0c  lea     r8, [rsp+11B0h+var_1170]
0x180021e11  lea     rdx, [rsp+11B0h+var_1180]
0x180021e16  lea     rcx, [rbp+10B0h+var_1060]
0x180021e1a  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180021e1f  nop
0x180021e20  cmp     qword ptr [rax+18h], 7
0x180021e25  jbe     short loc_180021E2A
0x180021e27  mov     rax, [rax]
0x180021e2a  lea     r9, [rsp+11B0h+var_1148]; __int64 (**)(void)
0x180021e2f  lea     r8, [rsp+11B0h+hLibModule]; HINSTANCE *
0x180021e34  lea     rdx, aGetrootpath; "GetRootPath"
0x180021e3b  mov     rcx, rax; wchar_t *
0x180021e3e  call    ?LoadLibraryAndFunction@@YAJQEB_WQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; LoadLibraryAndFunction(wchar_t const * const,char const * const,HINSTANCE__ * *,__int64 (**)(void))
0x180021e43  mov     rcx, [rbp+10B8h]; this
0x180021e4a  test    eax, eax
0x180021e4c  js      loc_180022397
0x180021e52  lea     rcx, [rbp+10B0h+var_1060]; void *
0x180021e56  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021e5b  xorps   xmm0, xmm0
0x180021e5e  movups  [rbp+10B0h+var_1060], xmm0
0x180021e62  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180021e6a  movdqu  [rbp+10B0h+var_1050], xmm1
0x180021e6f  mov     word ptr [rbp+10B0h+var_1060], r13w
0x180021e74  movups  [rbp+10B0h+var_10C8], xmm0
0x180021e78  movdqu  [rbp+10B0h+var_10B8], xmm1
0x180021e7d  mov     word ptr [rbp+10B0h+var_10C8], r13w
0x180021e82  mov     r8d, 800h
0x180021e88  lea     rdx, [rbp+10B0h+var_1040]
0x180021e8c  lea     rcx, aMainos_1; "MAINOS"
0x180021e93  mov     rax, [rsp+11B0h+var_1148]
0x180021e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e9d  lea     rax, aWindows; "\\Windows"
0x180021ea4  mov     [rsp+11B0h+var_1180], rax
0x180021ea9  mov     [rsp+11B0h+var_1178], 8
0x180021eb2  lea     rax, [rbp+10B0h+var_1040]
0x180021eb6  mov     qword ptr [rsp+11B0h+var_1170], rax
0x180021ebb  lea     rcx, [rbp+10B0h+var_1040]
0x180021ebf  mov     rax, rsi
0x180021ec2  inc     rax
0x180021ec5  cmp     [rcx+rax*2], r13w
0x180021eca  jnz     short loc_180021EC2
0x180021ecc  mov     [rsp+11B0h+var_1168], rax
0x180021ed1  lea     r8, [rsp+11B0h+var_1180]
0x180021ed6  lea     rdx, [rsp+11B0h+var_1170]
0x180021edb  lea     rcx, [rbp+10B0h+lpSymlinkFileName]
0x180021edf  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180021ee4  mov     rdx, rax
0x180021ee7  lea     rcx, [rbp+10B0h+var_1060]
0x180021eeb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180021ef0  lea     rcx, [rbp+10B0h+lpSymlinkFileName]; void *
0x180021ef4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021ef9  lea     rax, aWindowsImageup; "\\Windows\\ImageUpdate\\CompDBs"
0x180021f00  mov     [rsp+11B0h+var_1180], rax
0x180021f05  mov     [rsp+11B0h+var_1178], 1Ch
0x180021f0e  lea     rax, [rbp+10B0h+var_1040]
0x180021f12  mov     qword ptr [rsp+11B0h+var_1170], rax
0x180021f17  lea     rcx, [rbp+10B0h+var_1040]
0x180021f1b  mov     rax, rsi
0x180021f1e  inc     rax
0x180021f21  cmp     [rcx+rax*2], r13w
0x180021f26  jnz     short loc_180021F1E
0x180021f28  mov     [rsp+11B0h+var_1168], rax
0x180021f2d  lea     r8, [rsp+11B0h+var_1180]
0x180021f32  lea     rdx, [rsp+11B0h+var_1170]
0x180021f37  lea     rcx, [rbp+10B0h+lpSymlinkFileName]
0x180021f3b  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180021f40  mov     rdx, rax
0x180021f43  lea     rcx, [rbp+10B0h+var_10C8]
0x180021f47  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180021f4c  lea     rcx, [rbp+10B0h+lpSymlinkFileName]; void *
0x180021f50  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021f55  mov     [rbp+10B0h+var_10A8], r13
0x180021f59  mov     [rbp+10B0h+var_10A0], r13b
0x180021f5d  lea     rax, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x180021f64  mov     [rsp+11B0h+var_1180], rax
0x180021f69  mov     [rsp+11B0h+var_1178], rbx
0x180021f6e  lea     rdx, [rsp+11B0h+var_1180]
0x180021f73  lea     rcx, [rbp+10B0h+var_10A8]
0x180021f77  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x180021f7c  mov     edi, eax
0x180021f7e  test    eax, eax
0x180021f80  jns     short loc_180021FCD
0x180021f82  mov     dword ptr [rsp+11B0h+var_1148], eax
0x180021f86  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180021f8d  test    rcx, rcx
0x180021f90  jz      short loc_180021FCD
0x180021f92  lea     r9, aFailedToAcquir_0; "Failed to acquire required privileges"
0x180021f99  mov     r8d, ebx
0x180021f9c  xor     edx, edx
0x180021f9e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180021fa3  lea     rax, [rsp+11B0h+var_1148]
0x180021fa8  mov     qword ptr [rsp+11B0h+var_1170], rax
0x180021fad  lea     rax, [rsp+11B0h+var_1170]
0x180021fb2  mov     qword ptr [rsp+11B0h+var_1190], rax; int
0x180021fb7  lea     r9, asc_1801CAFB4; ": {}"
0x180021fbe  mov     r8d, ebx
0x180021fc1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180021fc8  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x180021fcd  mov     rcx, [rbp+10B8h]; this
0x180021fd4  test    edi, edi
0x180021fd6  js      loc_1800223AC
0x180021fdc  lea     rax, aMetadata_1; "metadata"
0x180021fe3  mov     [rsp+11B0h+var_1180], rax
0x180021fe8  mov     [rsp+11B0h+var_1178], 8
0x180021ff1  mov     qword ptr [rsp+11B0h+var_1170], r14
0x180021ff6  mov     rax, rsi
0x180021ff9  inc     rax
0x180021ffc  cmp     [r14+rax*2], r13w
0x180022001  jnz     short loc_180021FF9
0x180022003  mov     [rsp+11B0h+var_1168], rax
0x180022008  lea     r8, [rsp+11B0h+var_1180]
0x18002200d  lea     rdx, [rsp+11B0h+var_1170]
0x180022012  lea     rcx, [rbp+10B0h+var_1128]
0x180022016  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x18002201b  nop
0x18002201c  mov     rcx, [rbp+10B0h+var_1118]
0x180022020  lea     rax, [rbp+10B0h+var_1128]
0x180022024  cmp     [rbp+10B0h+var_1110], 7
0x180022029  cmova   rax, [rbp+10B0h+var_1128]
0x18002202e  mov     [rsp+11B0h+var_1180], rax
0x180022033  mov     [rsp+11B0h+var_1178], rcx
0x180022038  lea     rcx, [rsp+11B0h+var_1180]
0x18002203d  call    ?EnsureDirectoryExistsHr@@YAJAEBV?$basic_zstring_view@_W@wil@@@Z; EnsureDirectoryExistsHr(wil::basic_zstring_view<wchar_t> const &)
0x180022042  xorps   xmm0, xmm0
0x180022045  movdqu  xmmword ptr [rbp+10B0h+lpTargetFileName], xmm0
0x18002204a  mov     [rbp+10B0h+var_1088], r13
0x18002204e  lea     rcx, [rsp+11B0h+var_1170]
0x180022053  call    ??$?0$01@?$basic_zstring_view@_W@wil@@QEAA@AEAY01$$CB_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t const (&)[2])
0x180022058  mov     rcx, qword ptr [rbp+10B0h+var_10B8]
0x18002205c  lea     rax, [rbp+10B0h+var_10C8]
0x180022060  cmp     qword ptr [rbp+10B0h+var_10B8+8], 7
0x180022065  cmova   rax, qword ptr [rbp+10B0h+var_10C8]
0x18002206a  mov     [rsp+11B0h+var_1180], rax
0x18002206f  mov     [rsp+11B0h+var_1178], rcx
0x180022074  mov     qword ptr [rsp+11B0h+var_1190], r13; int
0x180022079  lea     r9, [rbp+10B0h+lpTargetFileName]
0x18002207d  xor     r8d, r8d
0x180022080  lea     rdx, [rsp+11B0h+var_1170]
0x180022085  lea     rcx, [rsp+11B0h+var_1180]
0x18002208a  call    ?GetAllFilesAndDirectories@@YAJAEBV?$basic_zstring_view@_W@wil@@0HPEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@1@Z; GetAllFilesAndDirectories(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,int,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x18002208f  mov     rcx, [rbp+10B8h]; this
0x180022096  test    eax, eax
0x180022098  js      loc_1800223C1
0x18002209e  mov     rbx, [rbp+10B0h+lpTargetFileName]
0x1800220a2  mov     rdi, [rbp+10B0h+lpTargetFileName+8]
0x1800220a6  jmp     loc_180022174
0x1800220ab  cmp     qword ptr [rbx+18h], 7
0x1800220b0  jbe     short loc_1800220B7
0x1800220b2  mov     rcx, [rbx]
0x1800220b5  jmp     short loc_1800220BA
0x1800220b7  mov     rcx, rbx; FullPath
0x1800220ba  call    ?GetFileName@@YAPEB_WQEB_W@Z; GetFileName(wchar_t const * const)
0x1800220bf  mov     [rsp+11B0h+var_1180], rax
0x1800220c4  mov     rcx, rsi
0x1800220c7  inc     rcx
0x1800220ca  cmp     [rax+rcx*2], r13w
0x1800220cf  jnz     short loc_1800220C7
0x1800220d1  mov     [rsp+11B0h+var_1178], rcx
0x1800220d6  lea     rax, [rbp+10B0h+var_1128]
0x1800220da  cmp     [rbp+10B0h+var_1110], 7
0x1800220df  cmova   rax, [rbp+10B0h+var_1128]
0x1800220e4  mov     qword ptr [rsp+11B0h+var_1170], rax
0x1800220e9  mov     rax, [rbp+10B0h+var_1118]
0x1800220ed  mov     [rsp+11B0h+var_1168], rax
0x1800220f2  lea     r8, [rsp+11B0h+var_1180]
0x1800220f7  lea     rdx, [rsp+11B0h+var_1170]
0x1800220fc  lea     rcx, [rbp+10B0h+lpSymlinkFileName]
0x180022100  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180022105  nop
0x180022106  mov     rcx, [rbp+10B0h+var_10D8]
0x18002210a  lea     rax, [rbp+10B0h+lpSymlinkFileName]
0x18002210e  cmp     [rbp+10B0h+var_10D0], 7
0x180022113  cmova   rax, [rbp+10B0h+lpSymlinkFileName]
0x180022118  mov     [rsp+11B0h+var_1148], rax
0x18002211d  mov     [rsp+11B0h+var_1140], rcx
0x180022122  lea     rcx, [rsp+11B0h+var_1148]
0x180022127  call    ?SetAttrAndDeleteFile@@YAHAEBV?$basic_zstring_view@_W@wil@@@Z; SetAttrAndDeleteFile(wil::basic_zstring_view<wchar_t> const &)
0x18002212c  cmp     qword ptr [rbx+18h], 7
0x180022131  jbe     short loc_180022138
0x180022133  mov     rdx, [rbx]
0x180022136  jmp     short loc_18002213B
0x180022138  mov     rdx, rbx; lpTargetFileName
0x18002213b  lea     rcx, [rbp+10B0h+lpSymlinkFileName]
0x18002213f  cmp     [rbp+10B0h+var_10D0], 7
0x180022144  cmova   rcx, [rbp+10B0h+lpSymlinkFileName]; lpSymlinkFileName
0x180022149  mov     r14, [rbp+10B8h]
0x180022150  xor     r8d, r8d; dwFlags
0x180022153  call    cs:__imp_CreateSymbolicLinkW
0x18002215a  nop     dword ptr [rax+rax+00h]
0x18002215f  test    al, al
0x180022161  jz      loc_1800223EB
0x180022167  lea     rcx, [rbp+10B0h+lpSymlinkFileName]; void *
0x18002216b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022170  add     rbx, 20h ; ' '
0x180022174  cmp     rbx, rdi
0x180022177  jnz     loc_1800220AB
0x18002217d  lea     rcx, [rbp+10B0h+var_1080]
0x180022181  cmp     [rbp+10B0h+var_1068], 7
0x180022186  cmova   rcx, [rbp+10B0h+var_1080]; FullPath
0x18002218b  call    ?GetFileName@@YAPEB_WQEB_W@Z; GetFileName(wchar_t const * const)
0x180022190  mov     [rsp+11B0h+var_1180], rax
0x180022195  inc     rsi
0x180022198  cmp     [rax+rsi*2], r13w
0x18002219d  jnz     short loc_180022195
0x18002219f  mov     [rsp+11B0h+var_1178], rsi
0x1800221a4  lea     rax, [rbp+10B0h+var_1128]
0x1800221a8  cmp     [rbp+10B0h+var_1110], 7
0x1800221ad  cmova   rax, [rbp+10B0h+var_1128]
0x1800221b2  mov     qword ptr [rsp+11B0h+var_1170], rax
0x1800221b7  mov     rax, [rbp+10B0h+var_1118]
0x1800221bb  mov     [rsp+11B0h+var_1168], rax
0x1800221c0  lea     r8, [rsp+11B0h+var_1180]
0x1800221c5  lea     rdx, [rsp+11B0h+var_1170]
  ... truncated ...
```
