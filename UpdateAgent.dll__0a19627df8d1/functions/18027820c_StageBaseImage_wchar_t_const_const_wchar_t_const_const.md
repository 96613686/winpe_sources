# StageBaseImage(wchar_t const * const,wchar_t const * const)

- ea: `0x18027820c`
- end: `0x180278b03`
- name: `?StageBaseImage@@YAJQEB_W0@Z`
- size: `2295`
- prototype: `__int64 __fastcall(const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180271160`

## callees

- `0x1800059d0`
- `0x180006a18`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000b7a4`
- `0x18000c4c4`
- `0x18008b360`
- `0x18008b38c`
- `0x18008b3ec`
- `0x180094d0c`
- `0x180149300`
- `0x18027040c`
- `0x1802706cc`
- `0x180270788`
- `0x180270844`
- `0x180275608`
- `0x180276114`
- `0x18027820c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1802785b3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180278a65`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1802785b3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180278a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802783b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802783b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180278269`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180278269`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18027835f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278476`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18027848f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1802785c7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1802785dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1802785f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278606`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278a79`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278a8e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278aa3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278ab8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18027835f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278476`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18027848f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1802785c7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1802785dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1802785f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278606`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278a79`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278a8e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278aa3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180278ab8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1802783a0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1802783a0`

## string_xrefs

- `0x180278af1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1802784b6`: `\system32\dismapi.dll`
- `0x1802783f4`: `Failed to copy unattend file from {} to {}`
- `0x1802782f6`: `Failed to create container base image directory.`
- `0x1802786d0`: `Failed to get address of DismOpenSession`
- `0x1802786aa`: `DismOpenSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StageBaseImage(const wchar_t *const a1, const wchar_t *a2)
{
  UINT SystemWindowsDirectoryW; // eax
  const char *v3; // r9
  unsigned int v5; // ebx
  int Directory; // eax
  signed int LastError; // ebx
  unsigned int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  HLOCAL v11; // rbx
  int v12; // eax
  unsigned int v13; // esi
  __int64 v14; // rdx
  int FunctionPointer; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  unsigned int v23; // [rsp+28h] [rbp-E0h]
  unsigned int v24[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C8h]
  const wchar_t *v26; // [rsp+48h] [rbp-C0h] BYREF
  HMODULE hLibModule; // [rsp+50h] [rbp-B8h]
  __int64 (*v28[2])(void); // [rsp+58h] [rbp-B0h] BYREF
  __int64 (*v29[2])(void); // [rsp+68h] [rbp-A0h] BYREF
  const wchar_t *v30; // [rsp+78h] [rbp-90h] BYREF
  __int64 (*v31)(void); // [rsp+80h] [rbp-88h] BYREF
  __int64 (*v32)(void); // [rsp+88h] [rbp-80h] BYREF
  HLOCAL v33; // [rsp+90h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-70h] BYREF
  LPCWSTR lpNewFileName; // [rsp+A0h] [rbp-68h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v37; // [rsp+B0h] [rbp-58h] BYREF
  WCHAR Buffer[264]; // [rsp+B8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F0h] [rbp+1E8h]

  v28[1] = (__int64 (*)(void))-2LL;
  v29[0] = (__int64 (*)(void))a1;
  v30 = a2;
  memset_0(Buffer, 0, 0x208u);
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  if ( !SystemWindowsDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x19B,
             (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
             v3);
  if ( SystemWindowsDirectoryW >= 0x104 )
  {
    v5 = -2147024774;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)0x8007007ALL,
      v23);
    return v5;
  }
  wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const * const &,wchar_t const (&)[17]>(
    &hMem,
    &v30);
  Directory = RecursivelyCreateDirectory(hMem, 0);
  v5 = Directory;
  if ( Directory < 0 )
  {
    LODWORD(v33) = Directory;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create container base image directory.");
      v29[0] = (__int64 (*)(void))&v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v29);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v5,
      v23);
LABEL_10:
    if ( hMem )
      LocalFree(hMem);
    return v5;
  }
  wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const * const &,wchar_t const (&)[24]>(
    &lpExistingFileName,
    v29);
  v29[0] = (__int64 (*)(void))hMem;
  wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t *,wchar_t const (&)[14]>(
    &lpNewFileName,
    v29);
  if ( !CopyFileW(lpExistingFileName, lpNewFileName, 0) )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v29[0] = (__int64 (*)(void))lpNewFileName;
      v28[0] = (__int64 (*)(void))lpExistingFileName;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to copy unattend file from {} to {}",
        v28,
        v29);
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      else
        v8 = LastError;
      LODWORD(v33) = v8;
      *(_QWORD *)v24 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)v24);
    }
    if ( LastError )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1A9,
             (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
             (const char *)(unsigned int)LastError,
             v23);
      if ( lpNewFileName )
        LocalFree((HLOCAL)lpNewFileName);
      if ( lpExistingFileName )
        LocalFree((HLOCAL)lpExistingFileName);
      goto LABEL_10;
    }
    goto LABEL_78;
  }
  v33 = 0;
  v9 = -1;
  do
    ++v9;
  while ( Buffer[v9] );
  v26 = L"\\system32\\dismapi.dll";
  hLibModule = (HMODULE)21;
  *(_QWORD *)v24 = Buffer;
  v25 = v9;
  v29[0] = 0;
  v29[1] = 0;
  v10 = wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(
          &v33,
          v29,
          v24,
          &v26);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v10,
      v23);
  LOBYTE(v26) = 0;
  hLibModule = 0;
  v11 = v33;
  v12 = LoadHelper::Initialize((LoadHelper *)&v26, (const wchar_t *)v33);
  v13 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v33) = v12;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      *(_QWORD *)v24 = v11;
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize {}",
        (__int64)v24);
      v29[0] = (__int64 (*)(void))&v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v29);
    }
    v14 = 432;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v13,
      v23);
    goto LABEL_31;
  }
  v33 = 0;
  v28[0] = 0;
  v32 = 0;
  v31 = 0;
  v29[0] = 0;
  FunctionPointer = LoadHelper::GetFunctionPointer((LoadHelper *)&v26, "DismInitialize", (__int64 (**)(void))&v33);
  v13 = FunctionPointer;
  if ( FunctionPointer < 0 )
  {
    LODWORD(v33) = FunctionPointer;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get address of DismInitialize");
      *(_QWORD *)v24 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v24);
    }
    v14 = 441;
    goto LABEL_30;
  }
  v16 = LoadHelper::GetFunctionPointer((LoadHelper *)&v26, "DismOpenSession", v28);
  v13 = v16;
  if ( v16 < 0 )
  {
    LODWORD(v33) = v16;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get address of DismOpenSession");
      *(_QWORD *)v24 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v24);
    }
    v14 = 444;
    goto LABEL_30;
  }
  v17 = LoadHelper::GetFunctionPointer((LoadHelper *)&v26, "DismCloseSession", &v32);
  v13 = v17;
  if ( v17 < 0 )
  {
    LODWORD(v33) = v17;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get address of DismCloseSession");
      *(_QWORD *)v24 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v24);
    }
    v14 = 447;
    goto LABEL_30;
  }
  v18 = LoadHelper::GetFunctionPointer((LoadHelper *)&v26, "DismShutdown", &v31);
  v13 = v18;
  if ( v18 < 0 )
  {
    LODWORD(v33) = v18;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get address of DismShutdown");
      *(_QWORD *)v24 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v24);
    }
    v14 = 450;
    goto LABEL_30;
  }
  v19 = LoadHelper::GetFunctionPointer((LoadHelper *)&v26, "_DismStage", v29);
  v13 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v33) = v19;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get address of _DismStage");
      *(_QWORD *)v24 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v24);
    }
    v14 = 453;
    goto LABEL_30;
  }
  v20 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD))v33)(2, 0, 0);
  v13 = v20;
  if ( v20 < 0 )
  {
    LODWORD(v33) = v20;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize dism.");
      *(_QWORD *)v24 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v24);
    }
    v14 = 455;
    goto LABEL_30;
  }
  v37 = 0;
  v21 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, unsigned int *))v28[0])(v30, 0, 0, &v37);
  v13 = v21;
  if ( v21 >= 0 )
  {
    v22 = ((__int64 (__fastcall *)(_QWORD))v29[0])(v37);
    v13 = v22;
    if ( v22 >= 0 )
    {
      ((void (__fastcall *)(_QWORD))v32)(v37);
      v31();
      if ( hLibModule )
        FreeLibrary(hLibModule);
      if ( v11 )
        LocalFree(v11);
LABEL_78:
      if ( lpNewFileName )
        LocalFree((HLOCAL)lpNewFileName);
      if ( lpExistingFileName )
        LocalFree((HLOCAL)lpExistingFileName);
      if ( hMem )
        LocalFree(hMem);
      return 0;
    }
    LODWORD(v33) = v22;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to run dism stage on image {}",
        (__int64)&v30);
      *(_QWORD *)v24 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v24);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v13,
      v23);
    ((void (__fastcall *)(_QWORD))v32)(v37);
    v31();
  }
  else
  {
    LODWORD(v33) = v21;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize dism session for image {}",
        (__int64)&v30);
      *(_QWORD *)v24 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v24);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v13,
      v23);
    v31();
  }
LABEL_31:
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( v11 )
    LocalFree(v11);
  if ( lpNewFileName )
    LocalFree((HLOCAL)lpNewFileName);
  if ( lpExistingFileName )
    LocalFree((HLOCAL)lpExistingFileName);
  if ( hMem )
    LocalFree(hMem);
  return v13;
}

```

## disassembly

```asm
0x18027820c  mov     rax, rsp
0x18027820f  push    rbp
0x180278210  push    rdi
0x180278211  push    r14
0x180278213  lea     rbp, [rax-1E8h]
0x18027821a  sub     rsp, 2D0h
0x180278221  mov     [rsp+2E0h+var_288], 0FFFFFFFFFFFFFFFEh
0x18027822a  mov     [rax+18h], rbx
0x18027822e  mov     [rax+20h], rsi
0x180278232  mov     rax, cs:__security_cookie
0x180278239  xor     rax, rsp
0x18027823c  mov     [rbp+1E0h+var_20], rax
0x180278243  mov     [rsp+2E0h+var_280], rcx
0x180278248  mov     [rsp+2E0h+var_270], rdx
0x18027824d  xor     edx, edx; Val
0x18027824f  mov     r8d, 208h; Size
0x180278255  lea     rcx, [rbp+1E0h+Buffer]; void *
0x180278259  call    memset_0
0x18027825e  mov     ebx, 104h
0x180278263  mov     edx, ebx; uSize
0x180278265  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x180278269  call    cs:__imp_GetSystemWindowsDirectoryW
0x180278270  nop     dword ptr [rax+rax+00h]
0x180278275  xor     r14d, r14d
0x180278278  test    eax, eax
0x18027827a  jnz     short loc_180278299
0x18027827c  mov     rcx, [rbp+1E8h]; this
0x180278283  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027828a  mov     edx, 19Bh; void *
0x18027828f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180278294  jmp     loc_180278AC6
0x180278299  cmp     eax, ebx
0x18027829b  jb      short loc_1802782C4
0x18027829d  mov     rcx, [rbp+1E8h]; this
0x1802782a4  mov     ebx, 8007007Ah
0x1802782a9  mov     r9d, ebx; char *
0x1802782ac  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x1802782b3  mov     edx, 19Ch; void *
0x1802782b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802782bd  mov     eax, ebx
0x1802782bf  jmp     loc_180278AC6
0x1802782c4  lea     rdx, [rsp+2E0h+var_270]
0x1802782c9  lea     rcx, [rbp+1E0h+hMem]
0x1802782cd  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@AEBQEB_WAEAY0BB@$$CB_W@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@AEBQEB_WAEAY0BB@$$CB_W@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const * const &,wchar_t const (&)[17]>(wchar_t const * const &,wchar_t const (&)[17])
0x1802782d2  xor     edx, edx
0x1802782d4  mov     rcx, [rbp+1E0h+hMem]
0x1802782d8  call    RecursivelyCreateDirectory
0x1802782dd  mov     ebx, eax
0x1802782df  test    eax, eax
0x1802782e1  jns     loc_180278370
0x1802782e7  mov     dword ptr [rbp+1E0h+var_258], eax
0x1802782ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802782f1  test    rcx, rcx
0x1802782f4  jz      short loc_180278337
0x1802782f6  lea     r9, aFailedToCreate_37; "Failed to create container base image d"...
0x1802782fd  mov     edi, 3
0x180278302  mov     r8d, edi
0x180278305  xor     edx, edx
0x180278307  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027830c  lea     rax, [rbp+1E0h+var_258]
0x180278310  mov     [rsp+2E0h+var_280], rax
0x180278315  lea     rax, [rsp+2E0h+var_280]
0x18027831a  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x18027831f  lea     r9, asc_1802C6678; ": {}"
0x180278326  mov     r8d, edi
0x180278329  mov     dl, 1
0x18027832b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180278332  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180278337  mov     rcx, [rbp+1E8h]; this
0x18027833e  mov     r9d, ebx; char *
0x180278341  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180278348  mov     edx, 1A3h; void *
0x18027834d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180278352  mov     rcx, [rbp+1E0h+hMem]; hMem
0x180278356  test    rcx, rcx
0x180278359  jz      loc_1802782BD
0x18027835f  call    cs:__imp_LocalFree
0x180278366  nop     dword ptr [rax+rax+00h]
0x18027836b  jmp     loc_1802782BD
0x180278370  lea     rdx, [rsp+2E0h+var_280]
0x180278375  lea     rcx, [rbp+1E0h+lpExistingFileName]
0x180278379  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@AEBQEB_WAEAY0BI@$$CB_W@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@AEBQEB_WAEAY0BI@$$CB_W@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const * const &,wchar_t const (&)[24]>(wchar_t const * const &,wchar_t const (&)[24])
0x18027837e  mov     rax, [rbp+1E0h+hMem]
0x180278382  mov     [rsp+2E0h+var_280], rax
0x180278387  lea     rdx, [rsp+2E0h+var_280]
0x18027838c  lea     rcx, [rbp+1E0h+lpNewFileName]
0x180278390  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_WAEAY0O@$$CB_W@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@$$QEAPEA_WAEAY0O@$$CB_W@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t *,wchar_t const (&)[14]>(wchar_t * &&,wchar_t const (&)[14])
0x180278395  xor     r8d, r8d; bFailIfExists
0x180278398  mov     rdx, [rbp+1E0h+lpNewFileName]; lpNewFileName
0x18027839c  mov     rcx, [rbp+1E0h+lpExistingFileName]; lpExistingFileName
0x1802783a0  call    cs:__imp_CopyFileW
0x1802783a7  nop     dword ptr [rax+rax+00h]
0x1802783ac  test    eax, eax
0x1802783ae  jnz     loc_1802784A0
0x1802783b4  call    cs:__imp_GetLastError
0x1802783bb  nop     dword ptr [rax+rax+00h]
0x1802783c0  mov     ebx, eax
0x1802783c2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802783c9  test    rcx, rcx
0x1802783cc  jz      short loc_180278448
0x1802783ce  mov     rdx, [rbp+1E0h+lpNewFileName]
0x1802783d2  mov     [rsp+2E0h+var_280], rdx
0x1802783d7  mov     rdx, [rbp+1E0h+lpExistingFileName]
0x1802783db  mov     [rsp+2E0h+var_290], rdx
0x1802783e0  lea     rax, [rsp+2E0h+var_280]
0x1802783e5  mov     [rsp+2E0h+var_2B8], rax
0x1802783ea  lea     rax, [rsp+2E0h+var_290]
0x1802783ef  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x1802783f4  lea     r9, aFailedToCopyUn; "Failed to copy unattend file from {} to"...
0x1802783fb  mov     edi, 3
0x180278400  mov     r8d, edi
0x180278403  xor     edx, edx
0x180278405  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x18027840a  test    ebx, ebx
0x18027840c  jg      short loc_180278412
0x18027840e  mov     eax, ebx
0x180278410  jmp     short loc_18027841A
0x180278412  movzx   eax, bx
0x180278415  or      eax, 80070000h
0x18027841a  mov     dword ptr [rbp+1E0h+var_258], eax
0x18027841d  lea     rax, [rbp+1E0h+var_258]
0x180278421  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x180278426  lea     rax, [rsp+2E0h+var_2B0]
0x18027842b  mov     qword ptr [rsp+2E0h+var_2C0], rax; unsigned int
0x180278430  lea     r9, a0; ": {0}"
0x180278437  mov     r8d, edi
0x18027843a  mov     dl, 1
0x18027843c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180278443  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180278448  test    ebx, ebx
0x18027844a  jz      loc_180278A85
0x180278450  mov     rcx, [rbp+1E8h]; this
0x180278457  mov     r9d, ebx; char *
0x18027845a  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180278461  mov     edx, 1A9h; void *
0x180278466  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18027846b  mov     ebx, eax
0x18027846d  mov     rcx, [rbp+1E0h+lpNewFileName]; hMem
0x180278471  test    rcx, rcx
0x180278474  jz      short loc_180278482
0x180278476  call    cs:__imp_LocalFree
0x18027847d  nop     dword ptr [rax+rax+00h]
0x180278482  mov     rcx, [rbp+1E0h+lpExistingFileName]; hMem
0x180278486  test    rcx, rcx
0x180278489  jz      loc_180278352
0x18027848f  call    cs:__imp_LocalFree
0x180278496  nop     dword ptr [rax+rax+00h]
0x18027849b  jmp     loc_180278352
0x1802784a0  mov     [rbp+1E0h+var_258], r14
0x1802784a4  lea     rcx, [rbp+1E0h+Buffer]
0x1802784a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802784ac  inc     rax
0x1802784af  cmp     [rcx+rax*2], r14w
0x1802784b4  jnz     short loc_1802784AC
0x1802784b6  lea     rcx, aSystem32Dismap; "\\system32\\dismapi.dll"
0x1802784bd  mov     [rsp+2E0h+var_2A0], rcx
0x1802784c2  mov     [rsp+2E0h+hLibModule], 15h
0x1802784cb  lea     rcx, [rbp+1E0h+Buffer]
0x1802784cf  mov     qword ptr [rsp+2E0h+var_2B0], rcx
0x1802784d4  mov     [rsp+2E0h+var_2A8], rax
0x1802784d9  mov     [rsp+2E0h+var_280], r14
0x1802784de  mov     [rsp+2E0h+var_278], r14
0x1802784e3  lea     r9, [rsp+2E0h+var_2A0]
0x1802784e8  lea     r8, [rsp+2E0h+var_2B0]
0x1802784ed  lea     rdx, [rsp+2E0h+var_280]
0x1802784f2  lea     rcx, [rbp+1E0h+var_258]
0x1802784f6  call    ??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@Ustring_view_t@details@2@U342@U342@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@Ustring_view_t@01@11@Z; wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t)
0x1802784fb  mov     rcx, [rbp+1E8h]; this
0x180278502  test    eax, eax
0x180278504  js      loc_180278AEE
0x18027850a  mov     byte ptr [rsp+2E0h+var_2A0], r14b
0x18027850f  mov     [rsp+2E0h+hLibModule], r14
0x180278514  mov     rbx, [rbp+1E0h+var_258]
0x180278518  mov     rdx, rbx; wchar_t *
0x18027851b  lea     rcx, [rsp+2E0h+var_2A0]; this
0x180278520  call    ?Initialize@LoadHelper@@QEAAJPEB_W@Z; LoadHelper::Initialize(wchar_t const *)
0x180278525  mov     esi, eax
0x180278527  test    eax, eax
0x180278529  jns     loc_180278619
0x18027852f  mov     dword ptr [rbp+1E0h+var_258], eax
0x180278532  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180278539  test    rcx, rcx
0x18027853c  jz      short loc_18027858E
0x18027853e  mov     qword ptr [rsp+2E0h+var_2B0], rbx
0x180278543  lea     rax, [rsp+2E0h+var_2B0]
0x180278548  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18027854d  lea     r9, aFailedToInitia_7; "Failed to initialize {}"
0x180278554  mov     edi, 3
0x180278559  mov     r8d, edi
0x18027855c  xor     edx, edx
0x18027855e  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x180278563  lea     rax, [rbp+1E0h+var_258]
0x180278567  mov     [rsp+2E0h+var_280], rax
0x18027856c  lea     rax, [rsp+2E0h+var_280]
0x180278571  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180278576  lea     r9, asc_1802C6678; ": {}"
0x18027857d  mov     r8d, edi
0x180278580  mov     dl, 1
0x180278582  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180278589  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027858e  mov     edx, 1B0h; void *
0x180278593  mov     rcx, [rbp+1E8h]; this
0x18027859a  mov     r9d, esi; char *
0x18027859d  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x1802785a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802785a9  mov     rcx, [rsp+2E0h+hLibModule]; hLibModule
0x1802785ae  test    rcx, rcx
0x1802785b1  jz      short loc_1802785BF
0x1802785b3  call    cs:__imp_FreeLibrary
0x1802785ba  nop     dword ptr [rax+rax+00h]
0x1802785bf  test    rbx, rbx
0x1802785c2  jz      short loc_1802785D3
0x1802785c4  mov     rcx, rbx; hMem
0x1802785c7  call    cs:__imp_LocalFree
0x1802785ce  nop     dword ptr [rax+rax+00h]
0x1802785d3  mov     rcx, [rbp+1E0h+lpNewFileName]; hMem
0x1802785d7  test    rcx, rcx
0x1802785da  jz      short loc_1802785E8
0x1802785dc  call    cs:__imp_LocalFree
0x1802785e3  nop     dword ptr [rax+rax+00h]
0x1802785e8  mov     rcx, [rbp+1E0h+lpExistingFileName]; hMem
0x1802785ec  test    rcx, rcx
0x1802785ef  jz      short loc_1802785FD
0x1802785f1  call    cs:__imp_LocalFree
0x1802785f8  nop     dword ptr [rax+rax+00h]
0x1802785fd  mov     rcx, [rbp+1E0h+hMem]; hMem
0x180278601  test    rcx, rcx
0x180278604  jz      short loc_180278612
0x180278606  call    cs:__imp_LocalFree
0x18027860d  nop     dword ptr [rax+rax+00h]
0x180278612  mov     eax, esi
0x180278614  jmp     loc_180278AC6
0x180278619  mov     [rbp+1E0h+var_258], r14
0x18027861d  mov     [rsp+2E0h+var_290], r14
0x180278622  mov     [rbp+1E0h+var_260], r14
0x180278626  mov     [rsp+2E0h+var_268], r14
0x18027862b  mov     [rsp+2E0h+var_280], r14
0x180278630  lea     r8, [rbp+1E0h+var_258]; __int64 (**)(void)
0x180278634  lea     rdx, aDisminitialize; "DismInitialize"
0x18027863b  lea     rcx, [rsp+2E0h+var_2A0]; this
0x180278640  call    ?GetFunctionPointer@LoadHelper@@QEAAJQEBDPEAP6A_JXZ@Z; LoadHelper::GetFunctionPointer(char const * const,__int64 (**)(void))
0x180278645  mov     esi, eax
0x180278647  test    eax, eax
0x180278649  jns     short loc_1802786A5
0x18027864b  mov     dword ptr [rbp+1E0h+var_258], eax
0x18027864e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180278655  test    rcx, rcx
0x180278658  jz      short loc_18027869B
0x18027865a  lea     r9, aFailedToGetAdd_29; "Failed to get address of DismInitialize"
0x180278661  mov     edi, 3
0x180278666  mov     r8d, edi
0x180278669  xor     edx, edx
0x18027866b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180278670  lea     rax, [rbp+1E0h+var_258]
0x180278674  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x180278679  lea     rax, [rsp+2E0h+var_2B0]
0x18027867e  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180278683  lea     r9, asc_1802C6678; ": {}"
0x18027868a  mov     r8d, edi
0x18027868d  mov     dl, 1
0x18027868f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180278696  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027869b  mov     edx, 1B9h
0x1802786a0  jmp     loc_180278593
0x1802786a5  lea     r8, [rsp+2E0h+var_290]; __int64 (**)(void)
0x1802786aa  lea     rdx, aDismopensessio; "DismOpenSession"
0x1802786b1  lea     rcx, [rsp+2E0h+var_2A0]; this
0x1802786b6  call    ?GetFunctionPointer@LoadHelper@@QEAAJQEBDPEAP6A_JXZ@Z; LoadHelper::GetFunctionPointer(char const * const,__int64 (**)(void))
0x1802786bb  mov     esi, eax
0x1802786bd  test    eax, eax
0x1802786bf  jns     short loc_18027871B
0x1802786c1  mov     dword ptr [rbp+1E0h+var_258], eax
0x1802786c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802786cb  test    rcx, rcx
0x1802786ce  jz      short loc_180278711
0x1802786d0  lea     r9, aFailedToGetAdd_18; "Failed to get address of DismOpenSessio"...
0x1802786d7  mov     edi, 3
0x1802786dc  mov     r8d, edi
0x1802786df  xor     edx, edx
0x1802786e1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802786e6  lea     rax, [rbp+1E0h+var_258]
0x1802786ea  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x1802786ef  lea     rax, [rsp+2E0h+var_2B0]
0x1802786f4  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x1802786f9  lea     r9, asc_1802C6678; ": {}"
0x180278700  mov     r8d, edi
0x180278703  mov     dl, 1
0x180278705  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027870c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180278711  mov     edx, 1BCh
0x180278716  jmp     loc_180278593
0x18027871b  lea     r8, [rbp+1E0h+var_260]; __int64 (**)(void)
0x18027871f  lea     rdx, aDismclosesessi; "DismCloseSession"
0x180278726  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18027872b  call    ?GetFunctionPointer@LoadHelper@@QEAAJQEBDPEAP6A_JXZ@Z; LoadHelper::GetFunctionPointer(char const * const,__int64 (**)(void))
0x180278730  mov     esi, eax
0x180278732  test    eax, eax
0x180278734  jns     short loc_180278790
0x180278736  mov     dword ptr [rbp+1E0h+var_258], eax
0x180278739  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
  ... truncated ...
```
