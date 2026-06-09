# ValidateCimPayloadFiles(wchar_t const * const)

- ea: `0x1801c1e8c`
- end: `0x1801c221b`
- name: `?ValidateCimPayloadFiles@@YAJQEB_W@Z`
- size: `911`
- prototype: `__int64 __fastcall(const wchar_t *const)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800dc9c0`

## callees

- `0x180011a14`
- `0x180013250`
- `0x1800150c0`
- `0x180019bdc`
- `0x180023ca8`
- `0x18002e280`
- `0x180049ec0`
- `0x180055fc8`
- `0x180056e00`
- `0x180070398`
- `0x180093c4c`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800b2fbc`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800fe364`
- `0x18011780c`
- `0x1801bffac`
- `0x1801c098c`
- `0x1801c1e8c`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801c1f10`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801c1f10`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1801c1ee4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1801c1ee4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801c213f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801c213f`

## string_xrefs

- `0x1801c1ed1`: `ntdll.dll`
- `0x1801c1f4c`: `Failed to get directory from path`
- `0x1801c1f09`: `NtSetCachedSigningLevel2`
- `0x1801c21ca`: `NtSetCachedSigningLevel unavailable, skipping validation of cim files.`
- `0x1801c1fea`: `Failed to convert path to NT path`
- `0x1801c21a1`: `Unable to open file: {}`

## pseudocode

```c
__int64 __fastcall ValidateCimPayloadFiles(wchar_t *a1)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // r14
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // edx
  int CimPayloadFiles; // eax
  const WCHAR **v11; // rbx
  const WCHAR **v12; // rsi
  const WCHAR *v13; // rcx
  HANDLE FileW; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  int dwCreationDisposition; // [rsp+20h] [rbp-99h]
  __int64 v19; // [rsp+40h] [rbp-79h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-71h] BYREF
  __int128 v21; // [rsp+50h] [rbp-69h] BYREF
  __int64 v22; // [rsp+60h] [rbp-59h]
  __int64 *v23; // [rsp+68h] [rbp-51h] BYREF
  int v24[2]; // [rsp+70h] [rbp-49h] BYREF
  wchar_t *v25; // [rsp+78h] [rbp-41h] BYREF
  __int64 v26; // [rsp+80h] [rbp-39h] BYREF
  __int128 v27; // [rsp+88h] [rbp-31h] BYREF
  __int64 v28; // [rsp+98h] [rbp-21h]
  _BYTE v29[24]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v30; // [rsp+B8h] [rbp-1h]
  const WCHAR **v31; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v25 = a1;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v29);
  hModule = 0;
  v28 = 0;
  v22 = 0;
  v19 = 0;
  v27 = 0;
  v21 = 0;
  LibraryW = LoadLibraryW(L"ntdll.dll");
  Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hModule, LibraryW);
  if ( hModule && (ProcAddress = GetProcAddress(hModule, "NtSetCachedSigningLevel2")) != 0 )
  {
    v3 = DirectoryFromPath(v25);
    v4 = v3;
    if ( v3 < 0 )
    {
      LODWORD(v26) = v3;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get directory from path");
        v23 = &v26;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v23);
      }
      v5 = 557;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstorage.cpp",
        (const char *)v4,
        dwCreationDisposition);
LABEL_18:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v19);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
      Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v29);
      return v4;
    }
    *(_QWORD *)v24 = v19;
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (__int64)LogAdapter::g_Logger,
        1,
        1,
        (__int64)"Validating CIM payload files in {} with catalog in {}",
        (__int64)&v25,
        (__int64)v24);
    v6 = Windows::StringUtil::Rtl::ConvertWin32FilePathToNtFilePath<wchar_t const *>();
    v7 = v6;
    if ( v6 < 0 )
    {
      LODWORD(v26) = v6;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert path to NT path");
        *(_QWORD *)v24 = &v26;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v8,
          3,
          (unsigned int)": {}",
          (__int64)v24);
      }
      v4 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x232,
             (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstorage.cpp",
             (const char *)v7,
             dwCreationDisposition);
      goto LABEL_18;
    }
    LODWORD(v27) = 24;
    RtlInitUnicodeStringFromLUnicodeString(&v21, (char *)&v27 + 8);
    CimPayloadFiles = GetCimPayloadFiles(v25, v29);
    v4 = CimPayloadFiles;
    if ( CimPayloadFiles < 0 )
    {
      LODWORD(v26) = CimPayloadFiles;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get cim payload files");
        *(_QWORD *)v24 = &v26;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v24);
      }
      v5 = 569;
      goto LABEL_17;
    }
    v11 = v31;
    v12 = &v31[v30];
    while ( v11 != v12 )
    {
      v13 = *v11;
      v26 = 0;
      FileW = CreateFileW(v13, 0x80000000, 1u, 0, 3u, 0x2000000u, 0);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
        &v26,
        FileW);
      if ( (unsigned __int64)(v26 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LogAdapter::TraceAtLevelLastError<wchar_t const *>(1, "Unable to open file: {}", v11);
      }
      else
      {
        *(_QWORD *)v24 = v26;
        v15 = ((__int64 (__fastcall *)(__int64, _QWORD, int *, __int64, __int64, __int128 *))ProcAddress)(
                4,
                0,
                v24,
                1,
                v26,
                &v27);
        if ( v15 < 0 )
          LogAdapter::TraceAtLevelNtStatus<long,wchar_t *>(v16, (unsigned int)v15, v17, v11);
      }
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v26);
      ++v11;
    }
  }
  else
  {
    LogAdapter::TraceAtLevel<>(1, "NtSetCachedSigningLevel unavailable, skipping validation of cim files.");
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v19);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v29);
  return 0;
}

```

## disassembly

```asm
0x1801c1e8c  push    rbp
0x1801c1e8e  push    rbx
0x1801c1e8f  push    rsi
0x1801c1e90  push    r14
0x1801c1e92  lea     rbp, [rsp-3Fh]
0x1801c1e97  sub     rsp, 0F8h
0x1801c1e9e  mov     rax, cs:__security_cookie
0x1801c1ea5  xor     rax, rsp
0x1801c1ea8  mov     [rbp+57h+var_30], rax
0x1801c1eac  mov     [rbp+57h+var_98], rcx
0x1801c1eb0  lea     rcx, [rbp+57h+var_70]; this
0x1801c1eb4  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x1801c1eb9  xor     eax, eax
0x1801c1ebb  mov     [rbp+57h+hModule], 0
0x1801c1ec3  xorps   xmm0, xmm0
0x1801c1ec6  mov     [rbp+57h+var_78], rax
0x1801c1eca  xorps   xmm1, xmm1
0x1801c1ecd  mov     [rbp+57h+var_B0], rax
0x1801c1ed1  lea     rcx, ModuleName; "ntdll.dll"
0x1801c1ed8  mov     [rbp+57h+var_D0], rax
0x1801c1edc  movups  [rbp+57h+var_88], xmm0
0x1801c1ee0  movups  [rbp+57h+var_C0], xmm1
0x1801c1ee4  call    cs:__imp_LoadLibraryW
0x1801c1eeb  nop     dword ptr [rax+rax+00h]
0x1801c1ef0  mov     rdx, rax
0x1801c1ef3  lea     rcx, [rbp+57h+hModule]
0x1801c1ef7  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1801c1efc  mov     rcx, [rbp+57h+hModule]; hModule
0x1801c1f00  test    rcx, rcx
0x1801c1f03  jz      loc_1801C21CA
0x1801c1f09  lea     rdx, aNtsetcachedsig_0; "NtSetCachedSigningLevel2"
0x1801c1f10  call    cs:__imp_GetProcAddress
0x1801c1f17  nop     dword ptr [rax+rax+00h]
0x1801c1f1c  mov     r14, rax
0x1801c1f1f  test    rax, rax
0x1801c1f22  jz      loc_1801C21CA
0x1801c1f28  mov     rcx, [rbp+57h+var_98]; wchar_t *
0x1801c1f2c  lea     rdx, [rbp+57h+var_D0]
0x1801c1f30  call    DirectoryFromPath
0x1801c1f35  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c1f3c  mov     ebx, eax
0x1801c1f3e  test    eax, eax
0x1801c1f40  jns     short loc_1801C1F92
0x1801c1f42  mov     dword ptr [rbp+57h+var_90], eax
0x1801c1f45  test    rcx, rcx
0x1801c1f48  jz      short loc_1801C1F88
0x1801c1f4a  xor     edx, edx
0x1801c1f4c  lea     r9, aFailedToGetDir; "Failed to get directory from path"
0x1801c1f53  lea     r8d, [rdx+3]
0x1801c1f57  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c1f5c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c1f63  lea     rax, [rbp+57h+var_90]
0x1801c1f67  mov     [rbp+57h+var_A8], rax
0x1801c1f6b  lea     r9, asc_1802EE7AC; ": {}"
0x1801c1f72  lea     rax, [rbp+57h+var_A8]
0x1801c1f76  mov     r8d, 3
0x1801c1f7c  mov     dl, 1
0x1801c1f7e  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801c1f83  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c1f88  mov     edx, 22Dh
0x1801c1f8d  jmp     loc_1801C20C0
0x1801c1f92  mov     rax, [rbp+57h+var_D0]
0x1801c1f96  mov     qword ptr [rbp+57h+var_A0], rax
0x1801c1f9a  test    rcx, rcx
0x1801c1f9d  jz      short loc_1801C1FC6
0x1801c1f9f  lea     rax, [rbp+57h+var_A0]
0x1801c1fa3  mov     r8d, 1
0x1801c1fa9  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x1801c1fae  lea     r9, aValidatingCimP; "Validating CIM payload files in {} with"...
0x1801c1fb5  lea     rax, [rbp+57h+var_98]
0x1801c1fb9  mov     dl, r8b
0x1801c1fbc  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801c1fc1  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1801c1fc6  lea     rdx, [rbp+57h+var_C0]
0x1801c1fca  lea     rcx, [rbp+57h+var_D0]
0x1801c1fce  call    ??$ConvertWin32FilePathToNtFilePath@PEB_W@Rtl@StringUtil@Windows@@YAJAEBQEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::ConvertWin32FilePathToNtFilePath<wchar_t const *>(wchar_t const * const &,Windows::Auto<_LUNICODE_STRING> *)
0x1801c1fd3  mov     ebx, eax
0x1801c1fd5  test    eax, eax
0x1801c1fd7  jns     short loc_1801C2043
0x1801c1fd9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c1fe0  mov     dword ptr [rbp+57h+var_90], eax
0x1801c1fe3  test    rcx, rcx
0x1801c1fe6  jz      short loc_1801C2024
0x1801c1fe8  xor     edx, edx
0x1801c1fea  lea     r9, aFailedToConver_20; "Failed to convert path to NT path"
0x1801c1ff1  lea     r8d, [rdx+3]
0x1801c1ff5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c1ffa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c2001  lea     rax, [rbp+57h+var_90]
0x1801c2005  mov     qword ptr [rbp+57h+var_A0], rax
0x1801c2009  lea     r9, asc_1802EE7AC; ": {}"
0x1801c2010  lea     rax, [rbp+57h+var_A0]
0x1801c2014  mov     r8d, 3
0x1801c201a  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; int
0x1801c201f  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1801c2024  mov     rcx, [rbp+5Fh]; this
0x1801c2028  lea     r8, aOnecoreBaseCbs_148; "onecore\\base\\cbs\\core\\cbssessionsto"...
0x1801c202f  mov     r9d, ebx; char *
0x1801c2032  mov     edx, 232h; void *
0x1801c2037  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801c203c  mov     ebx, eax
0x1801c203e  jmp     loc_1801C20D3
0x1801c2043  lea     rdx, [rbp+57h+var_88+8]
0x1801c2047  mov     dword ptr [rbp+57h+var_88], 18h
0x1801c204e  lea     rcx, [rbp+57h+var_C0]
0x1801c2052  call    RtlInitUnicodeStringFromLUnicodeString
0x1801c2057  mov     rcx, [rbp+57h+var_98]
0x1801c205b  lea     rdx, [rbp+57h+var_70]
0x1801c205f  call    GetCimPayloadFiles
0x1801c2064  mov     ebx, eax
0x1801c2066  test    eax, eax
0x1801c2068  jns     loc_1801C20FE
0x1801c206e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c2075  mov     dword ptr [rbp+57h+var_90], eax
0x1801c2078  test    rcx, rcx
0x1801c207b  jz      short loc_1801C20BB
0x1801c207d  xor     edx, edx
0x1801c207f  lea     r9, aFailedToGetCim; "Failed to get cim payload files"
0x1801c2086  lea     r8d, [rdx+3]
0x1801c208a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c208f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c2096  lea     rax, [rbp+57h+var_90]
0x1801c209a  mov     qword ptr [rbp+57h+var_A0], rax
0x1801c209e  lea     r9, asc_1802EE7AC; ": {}"
0x1801c20a5  lea     rax, [rbp+57h+var_A0]
0x1801c20a9  mov     r8d, 3
0x1801c20af  mov     dl, 1
0x1801c20b1  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; int
0x1801c20b6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c20bb  mov     edx, 239h; void *
0x1801c20c0  mov     rcx, [rbp+5Fh]; this
0x1801c20c4  lea     r8, aOnecoreBaseCbs_148; "onecore\\base\\cbs\\core\\cbssessionsto"...
0x1801c20cb  mov     r9d, ebx; char *
0x1801c20ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c20d3  lea     rcx, [rbp+57h+var_D0]
0x1801c20d7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801c20dc  lea     rcx, [rbp+57h+var_C0]
0x1801c20e0  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1801c20e5  lea     rcx, [rbp+57h+hModule]
0x1801c20e9  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1801c20ee  lea     rcx, [rbp+57h+var_70]
0x1801c20f2  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x1801c20f7  mov     eax, ebx
0x1801c20f9  jmp     loc_1801C2201
0x1801c20fe  mov     rbx, [rbp+57h+var_48]
0x1801c2102  mov     rax, [rbp+57h+var_58]
0x1801c2106  lea     rsi, [rbx+rax*8]
0x1801c210a  jmp     loc_1801C21BF
0x1801c210f  mov     rcx, [rbx]; lpFileName
0x1801c2112  xor     r9d, r9d; lpSecurityAttributes
0x1801c2115  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x1801c211e  mov     edx, 80000000h; dwDesiredAccess
0x1801c2123  mov     [rsp+110h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1801c212b  mov     [rbp+57h+var_90], 0
0x1801c2133  lea     r8d, [r9+1]; dwShareMode
0x1801c2137  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x1801c213f  call    cs:__imp_CreateFileW
0x1801c2146  nop     dword ptr [rax+rax+00h]
0x1801c214b  mov     rdx, rax
0x1801c214e  lea     rcx, [rbp+57h+var_90]
0x1801c2152  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x1801c2157  mov     rax, [rbp+57h+var_90]
0x1801c215b  lea     rcx, [rax-1]
0x1801c215f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801c2163  ja      short loc_1801C219E
0x1801c2165  lea     rcx, [rbp+57h+var_88]
0x1801c2169  mov     qword ptr [rbp+57h+var_A0], rax
0x1801c216d  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rcx
0x1801c2172  lea     r8, [rbp+57h+var_A0]
0x1801c2176  xor     edx, edx
0x1801c2178  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801c217d  mov     r9d, 1
0x1801c2183  mov     rax, r14
0x1801c2186  lea     ecx, [rdx+4]
0x1801c2189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c218e  test    eax, eax
0x1801c2190  jns     short loc_1801C21B2
0x1801c2192  mov     r9, rbx
0x1801c2195  mov     edx, eax
0x1801c2197  call    ??$TraceAtLevelNtStatus@JPEA_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEA_W@Z; LogAdapter::TraceAtLevelNtStatus<long,wchar_t *>(LogAdapter::LogLevel,long,char const * const,wchar_t * const &)
0x1801c219c  jmp     short loc_1801C21B2
0x1801c219e  mov     r8, rbx
0x1801c21a1  lea     rdx, aUnableToOpenFi; "Unable to open file: {}"
0x1801c21a8  mov     ecx, 1
0x1801c21ad  call    ??$TraceAtLevelLastError@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelLastError<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801c21b2  lea     rcx, [rbp+57h+var_90]
0x1801c21b6  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1801c21bb  add     rbx, 8
0x1801c21bf  cmp     rbx, rsi
0x1801c21c2  jnz     loc_1801C210F
0x1801c21c8  jmp     short loc_1801C21DB
0x1801c21ca  lea     rdx, aNtsetcachedsig; "NtSetCachedSigningLevel unavailable, sk"...
0x1801c21d1  mov     ecx, 1
0x1801c21d6  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1801c21db  lea     rcx, [rbp+57h+var_D0]
0x1801c21df  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801c21e4  lea     rcx, [rbp+57h+var_C0]
0x1801c21e8  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1801c21ed  lea     rcx, [rbp+57h+hModule]
0x1801c21f1  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1801c21f6  lea     rcx, [rbp+57h+var_70]
0x1801c21fa  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x1801c21ff  xor     eax, eax
0x1801c2201  mov     rcx, [rbp+57h+var_30]
0x1801c2205  xor     rcx, rsp; StackCookie
0x1801c2208  call    __security_check_cookie
0x1801c220d  add     rsp, 0F8h
0x1801c2214  pop     r14
0x1801c2216  pop     rsi
0x1801c2217  pop     rbx
0x1801c2218  pop     rbp
0x1801c2219  retn
```
