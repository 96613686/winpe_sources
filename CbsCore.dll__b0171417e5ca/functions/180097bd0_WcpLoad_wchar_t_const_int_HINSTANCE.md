# WcpLoad(wchar_t const *,int,HINSTANCE__ * *)

- ea: `0x180097bd0`
- end: `0x180098531`
- name: `?WcpLoad@@YAJPEB_WHPEAPEAUHINSTANCE__@@@Z`
- size: `2401`
- prototype: `__int64 __fastcall(const wchar_t *, int, HINSTANCE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f3f0c`

## callees

- `0x180013250`
- `0x180016d40`
- `0x180095e34`
- `0x180097bd0`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800fe364`
- `0x180125964`
- `0x18012b630`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097d98`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097e39`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097eda`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097f7b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18009801c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800980bd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18009815e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180098395`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097d98`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097e39`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097eda`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097f7b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18009801c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800980bd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18009815e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180098395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009817a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800983b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009817a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800983b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180097ce1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180097ce1`

## string_xrefs

- `0x180097d35`: `Failed to load WCP DLL: {}`
- `0x1800983d0`: `Failed to get proc address for RtlWcpDllEntrypoint.`
- `0x180097fb2`: `Failed to get proc address for OpenExistingOfflineStore.`
- `0x180097c14`: `No core DLL path specified`
- `0x180097c77`: `wcp.dll`
- `0x180097f74`: `OpenExistingOfflineStore`
- `0x1800984a1`: `Failed to call RtlWcpDllDebugEntrypoint`
- `0x18009838e`: `RtlWcpDllDebugEntrypoint`

## pseudocode

```c
__int64 __fastcall WcpLoad(const wchar_t *a1, __int64 a2, HINSTANCE *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  LPCWSTR v6; // rbx
  HMODULE LibraryW; // rax
  signed int LastError; // edi
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  int (*ProcAddress)(struct ICBSHelper *); // rax
  unsigned int v18; // eax
  int v19; // eax
  int v20; // eax
  unsigned int v21; // edi
  FARPROC v22; // rax
  unsigned int v23; // eax
  int v24; // eax
  unsigned int v25; // edi
  int v26; // edx
  unsigned int v27; // [rsp+20h] [rbp-58h]
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-48h] BYREF
  int v29[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v30; // [rsp+40h] [rbp-38h]
  int *v31; // [rsp+48h] [rbp-30h] BYREF
  int v32; // [rsp+50h] [rbp-28h] BYREF
  HMODULE hModule; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v34[2]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  vhWcpDll = 0;
  if ( a1 )
  {
    lpLibFileName = 0;
    hModule = 0;
    v4 = SczAllocConcat2Sz(&lpLibFileName, a1, L"wcp.dll");
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecore\\base\\cbs\\core\\cbswcpwrapper.cpp",
        (const char *)(unsigned int)v4,
        v27);
      if ( hModule )
      {
        vpfnWcpInitialize = 0;
        vpfnWcpShutdown = 0;
        vpfnOpenExistingOfflineStore = 0;
        vpfnGetSystemStore = 0;
        vpfnGetIdentityAuthority = 0;
        vpfnSetIsolationIMalloc = 0;
      }
      goto LABEL_105;
    }
    v6 = lpLibFileName;
    LibraryW = LoadLibraryW(lpLibFileName);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      &hModule,
      LibraryW);
    if ( !hModule )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v34 = v6;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to load WCP DLL: {}",
          (__int64)v34);
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        else
          v9 = LastError;
        v32 = v9;
        v31 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&v31);
      }
      if ( LastError )
      {
        v10 = 332;
LABEL_72:
        v19 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v10,
                (unsigned int)"onecore\\base\\cbs\\core\\cbswcpwrapper.cpp",
                (const char *)(unsigned int)LastError,
                v27);
LABEL_73:
        if ( hModule )
        {
          vpfnWcpShutdown = 0;
          vpfnOpenExistingOfflineStore = 0;
          vpfnGetSystemStore = 0;
          vpfnGetIdentityAuthority = 0;
          vpfnSetIsolationIMalloc = 0;
          vpfnWcpInitialize = 0;
        }
        v5 = v19;
        goto LABEL_105;
      }
      goto LABEL_76;
    }
    vpfnSetIsolationIMalloc = (int (*)(struct IMalloc *))GetProcAddress(hModule, "SetIsolationIMalloc");
    if ( !vpfnSetIsolationIMalloc )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for SetIsolationIMalloc.");
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        else
          v11 = LastError;
        v32 = v11;
        *(_QWORD *)v34 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v34);
      }
      if ( LastError )
      {
        v10 = 335;
        goto LABEL_72;
      }
      goto LABEL_76;
    }
    vpfnGetIdentityAuthority = (int (*)(struct IIdentityAuthority **))GetProcAddress(hModule, "GetIdentityAuthority");
    if ( !vpfnGetIdentityAuthority )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for GetIdentityAuthority.");
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        else
          v12 = LastError;
        v32 = v12;
        *(_QWORD *)v34 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v34);
      }
      if ( LastError )
      {
        v10 = 338;
        goto LABEL_72;
      }
      goto LABEL_76;
    }
    vpfnGetSystemStore = (int (*)(unsigned int, const struct _GUID *, struct IUnknown **))GetProcAddress(
                                                                                            hModule,
                                                                                            "GetSystemStore");
    if ( !vpfnGetSystemStore )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for GetSystemStore.");
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        else
          v13 = LastError;
        v32 = v13;
        *(_QWORD *)v34 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v34);
      }
      if ( LastError )
      {
        v10 = 341;
        goto LABEL_72;
      }
      goto LABEL_76;
    }
    vpfnOpenExistingOfflineStore = (int (*)(unsigned int, const struct _OFFLINE_STORE_CREATION_PARAMETERS *, const struct _GUID *, struct IUnknown **, unsigned int *))GetProcAddress(hModule, "OpenExistingOfflineStore");
    if ( !vpfnOpenExistingOfflineStore )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for OpenExistingOfflineStore.");
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        else
          v14 = LastError;
        v32 = v14;
        *(_QWORD *)v34 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v34);
      }
      if ( LastError )
      {
        v10 = 345;
        goto LABEL_72;
      }
      goto LABEL_76;
    }
    vpfnWcpInitialize = (int (*)(unsigned __int64 *))GetProcAddress(hModule, "WcpInitialize");
    if ( !vpfnWcpInitialize )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for WcpInitialize.");
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        else
          v15 = LastError;
        v32 = v15;
        *(_QWORD *)v34 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v34);
      }
      if ( LastError )
      {
        v10 = 348;
        goto LABEL_72;
      }
      goto LABEL_76;
    }
    vpfnWcpShutdown = (void (*)(unsigned __int64))GetProcAddress(hModule, "WcpShutdown");
    if ( !vpfnWcpShutdown )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for WcpShutdown.");
        if ( LastError > 0 )
          v16 = (unsigned __int16)LastError | 0x80070000;
        else
          v16 = LastError;
        v32 = v16;
        *(_QWORD *)v34 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v34);
      }
      if ( LastError )
      {
        v10 = 351;
        goto LABEL_72;
      }
      goto LABEL_76;
    }
    ProcAddress = (int (*)(struct ICBSHelper *))GetProcAddress(hModule, "WcpSetHelperCallback");
    vpfnWcpSetHelperCallback = ProcAddress;
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for WcpSetHelperCallback.");
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        else
          v18 = LastError;
        v32 = v18;
        *(_QWORD *)v34 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v34);
      }
      if ( LastError )
      {
        v10 = 354;
        goto LABEL_72;
      }
LABEL_76:
      if ( hModule )
      {
        vpfnSetIsolationIMalloc = 0;
        vpfnGetIdentityAuthority = 0;
        vpfnGetSystemStore = 0;
        vpfnOpenExistingOfflineStore = 0;
        vpfnWcpShutdown = 0;
        vpfnWcpInitialize = 0;
      }
      goto LABEL_104;
    }
    ((void (__fastcall *)(char *))ProcAddress)((char *)&off_1803AF1F8 + off_1803AF1F8[1]);
    if ( vpfnWcpInitialize && !gulpWcpCookie )
    {
      v31 = 0;
      v20 = vpfnWcpInitialize((unsigned __int64 *)&v31);
      v21 = v20;
      if ( v20 < 0 )
      {
        v32 = v20;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to call WcpInitialize");
          *(_QWORD *)v34 = &v32;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v34);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16B,
          (unsigned int)"onecore\\base\\cbs\\core\\cbswcpwrapper.cpp",
          (const char *)v21,
          v27);
        if ( hModule )
        {
          vpfnWcpInitialize = 0;
          vpfnWcpShutdown = 0;
          vpfnOpenExistingOfflineStore = 0;
          vpfnGetSystemStore = 0;
          vpfnGetIdentityAuthority = 0;
          vpfnSetIsolationIMalloc = 0;
        }
        v5 = v21;
        goto LABEL_105;
      }
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&gulpWcpCookie, (signed __int64)v31, 0) )
        ((void (__fastcall *)(int *))vpfnWcpShutdown)(v31);
    }
    if ( vbInTestMode )
    {
      v22 = GetProcAddress(hModule, "RtlWcpDllDebugEntrypoint");
      vpfnWcpDllDebugEntryPoint = (__int64)v22;
      if ( !v22 )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for RtlWcpDllEntrypoint.");
          if ( LastError > 0 )
            v23 = (unsigned __int16)LastError | 0x80070000;
          else
            v23 = LastError;
          v32 = v23;
          *(_QWORD *)v29 = &v32;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v29);
        }
        if ( LastError )
        {
          v10 = 383;
          goto LABEL_72;
        }
        if ( hModule )
        {
          vpfnWcpInitialize = 0;
          vpfnWcpShutdown = 0;
          vpfnOpenExistingOfflineStore = 0;
          vpfnGetSystemStore = 0;
          vpfnGetIdentityAuthority = 0;
          vpfnSetIsolationIMalloc = 0;
        }
LABEL_104:
        v5 = 0;
LABEL_105:
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
        return v5;
      }
      *(_QWORD *)v34 = 0x100000000LL;
      *(_QWORD *)v29 = v34;
      v30 = 1;
      v24 = ((__int64 (__fastcall *)(_QWORD, int *))v22)(0, v29);
      v25 = v24;
      if ( v24 < 0 )
      {
        v32 = v24;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to call RtlWcpDllDebugEntrypoint");
          *(_QWORD *)v29 = &v32;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v26,
            3,
            (unsigned int)": {}",
            (__int64)v29);
        }
        v19 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x185,
                (unsigned int)"onecore\\base\\cbs\\core\\cbswcpwrapper.cpp",
                (const char *)v25,
                v27);
        goto LABEL_73;
      }
    }
    vhWcpDll = hModule;
    hModule = 0;
    goto LABEL_104;
  }
  v32 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No core DLL path specified");
    *(_QWORD *)v34 = &v32;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v34);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x131,
    (unsigned int)"onecore\\base\\cbs\\core\\cbswcpwrapper.cpp",
    (const char *)0x80070057LL,
    v27);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180097bd0  push    rbp
0x180097bd2  push    rbx
0x180097bd3  push    rsi
0x180097bd4  push    rdi
0x180097bd5  mov     rbp, rsp
0x180097bd8  sub     rsp, 78h
0x180097bdc  mov     rax, cs:__security_cookie
0x180097be3  xor     rax, rsp
0x180097be6  mov     [rbp+var_10], rax
0x180097bea  xor     esi, esi
0x180097bec  mov     cs:?vhWcpDll@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * vhWcpDll
0x180097bf3  test    rcx, rcx
0x180097bf6  jnz     short loc_180097C68
0x180097bf8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097bff  mov     edi, 80070057h
0x180097c04  mov     [rbp+var_28], edi
0x180097c07  test    rcx, rcx
0x180097c0a  jz      short loc_180097C49
0x180097c0c  lea     ebx, [rsi+3]
0x180097c0f  xor     edx, edx
0x180097c11  mov     r8d, ebx
0x180097c14  lea     r9, aNoCoreDllPathS_0; "No core DLL path specified"
0x180097c1b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097c20  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097c27  lea     rax, [rbp+var_28]
0x180097c2b  mov     qword ptr [rbp+var_18], rax
0x180097c2f  lea     r9, asc_1802EE7AC; ": {}"
0x180097c36  lea     rax, [rbp+var_18]
0x180097c3a  mov     r8d, ebx
0x180097c3d  mov     dl, 1
0x180097c3f  mov     qword ptr [rsp+78h+var_58], rax; int
0x180097c44  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097c49  mov     rcx, [rbp+20h]; this
0x180097c4d  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\core\\cbswcpwrapper"...
0x180097c54  mov     r9d, edi; char *
0x180097c57  mov     edx, 131h; void *
0x180097c5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097c61  mov     eax, edi
0x180097c63  jmp     loc_18009851B
0x180097c68  mov     rdx, rcx
0x180097c6b  mov     [rbp+lpLibFileName], rsi
0x180097c6f  lea     rcx, [rbp+lpLibFileName]
0x180097c73  mov     [rbp+hModule], rsi
0x180097c77  lea     r8, aWcpDll; "wcp.dll"
0x180097c7e  call    SczAllocConcat2Sz
0x180097c83  mov     ebx, eax
0x180097c85  test    eax, eax
0x180097c87  jns     short loc_180097CDA
0x180097c89  mov     rcx, [rbp+20h]; this
0x180097c8d  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\core\\cbswcpwrapper"...
0x180097c94  mov     r9d, eax; char *
0x180097c97  mov     edx, 146h; void *
0x180097c9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097ca1  cmp     [rbp+hModule], rsi
0x180097ca5  jz      loc_180098507
0x180097cab  mov     cs:?vpfnWcpInitialize@@3P6AJPEA_K@ZEA, rsi; long (*vpfnWcpInitialize)(unsigned __int64 *)
0x180097cb2  mov     cs:?vpfnWcpShutdown@@3P6AX_K@ZEA, rsi; void (*vpfnWcpShutdown)(unsigned __int64)
0x180097cb9  mov     cs:?vpfnOpenExistingOfflineStore@@3P6AJKPEBU_OFFLINE_STORE_CREATION_PARAMETERS@@AEBU_GUID@@PEAPEAUIUnknown@@PEAK@ZEA, rsi; long (*vpfnOpenExistingOfflineStore)(ulong,_OFFLINE_STORE_CREATION_PARAMETERS const *,_GUID const &,IUnknown * *,ulong *)
0x180097cc0  mov     cs:?vpfnGetSystemStore@@3P6AJKAEBU_GUID@@PEAPEAUIUnknown@@@ZEA, rsi; long (*vpfnGetSystemStore)(ulong,_GUID const &,IUnknown * *)
0x180097cc7  mov     cs:?vpfnGetIdentityAuthority@@3P6AJPEAPEAUIIdentityAuthority@@@ZEA, rsi; long (*vpfnGetIdentityAuthority)(IIdentityAuthority * *)
0x180097cce  mov     cs:?vpfnSetIsolationIMalloc@@3P6AJPEAUIMalloc@@@ZEA, rsi; long (*vpfnSetIsolationIMalloc)(IMalloc *)
0x180097cd5  jmp     loc_180098507
0x180097cda  mov     rbx, [rbp+lpLibFileName]
0x180097cde  mov     rcx, rbx; lpLibFileName
0x180097ce1  call    cs:__imp_LoadLibraryW
0x180097ce8  nop     dword ptr [rax+rax+00h]
0x180097ced  mov     rdx, rax
0x180097cf0  lea     rcx, [rbp+hModule]
0x180097cf4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180097cf9  mov     rcx, [rbp+hModule]; hModule
0x180097cfd  test    rcx, rcx
0x180097d00  jnz     loc_180097D91
0x180097d06  call    cs:__imp_GetLastError
0x180097d0d  nop     dword ptr [rax+rax+00h]
0x180097d12  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097d19  mov     edi, eax
0x180097d1b  test    rcx, rcx
0x180097d1e  jz      short loc_180097D7F
0x180097d20  mov     qword ptr [rbp+var_18], rbx
0x180097d24  lea     rax, [rbp+var_18]
0x180097d28  mov     ebx, 3
0x180097d2d  mov     qword ptr [rsp+78h+var_58], rax
0x180097d32  mov     r8d, ebx
0x180097d35  lea     r9, aFailedToLoadWc_0; "Failed to load WCP DLL: {}"
0x180097d3c  xor     edx, edx
0x180097d3e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180097d43  test    edi, edi
0x180097d45  jg      short loc_180097D4B
0x180097d47  mov     eax, edi
0x180097d49  jmp     short loc_180097D53
0x180097d4b  movzx   eax, di
0x180097d4e  or      eax, 80070000h
0x180097d53  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097d5a  lea     r9, a0; ": {0}"
0x180097d61  mov     [rbp+var_28], eax
0x180097d64  mov     r8d, ebx
0x180097d67  lea     rax, [rbp+var_28]
0x180097d6b  mov     dl, 1
0x180097d6d  mov     [rbp+var_30], rax
0x180097d71  lea     rax, [rbp+var_30]
0x180097d75  mov     qword ptr [rsp+78h+var_58], rax
0x180097d7a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097d7f  test    edi, edi
0x180097d81  jz      loc_180098239
0x180097d87  mov     edx, 14Ch
0x180097d8c  jmp     loc_1800981EF
0x180097d91  lea     rdx, aSetisolationim; "SetIsolationIMalloc"
0x180097d98  call    cs:__imp_GetProcAddress
0x180097d9f  nop     dword ptr [rax+rax+00h]
0x180097da4  mov     cs:?vpfnSetIsolationIMalloc@@3P6AJPEAUIMalloc@@@ZEA, rax; long (*vpfnSetIsolationIMalloc)(IMalloc *)
0x180097dab  test    rax, rax
0x180097dae  jnz     short loc_180097E2E
0x180097db0  call    cs:__imp_GetLastError
0x180097db7  nop     dword ptr [rax+rax+00h]
0x180097dbc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097dc3  mov     edi, eax
0x180097dc5  test    rcx, rcx
0x180097dc8  jz      short loc_180097E1C
0x180097dca  mov     ebx, 3
0x180097dcf  lea     r9, aFailedToGetPro_75; "Failed to get proc address for SetIsola"...
0x180097dd6  mov     r8d, ebx
0x180097dd9  xor     edx, edx
0x180097ddb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097de0  test    edi, edi
0x180097de2  jg      short loc_180097DE8
0x180097de4  mov     eax, edi
0x180097de6  jmp     short loc_180097DF0
0x180097de8  movzx   eax, di
0x180097deb  or      eax, 80070000h
0x180097df0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097df7  lea     r9, a0; ": {0}"
0x180097dfe  mov     [rbp+var_28], eax
0x180097e01  mov     r8d, ebx
0x180097e04  lea     rax, [rbp+var_28]
0x180097e08  mov     dl, 1
0x180097e0a  mov     qword ptr [rbp+var_18], rax
0x180097e0e  lea     rax, [rbp+var_18]
0x180097e12  mov     qword ptr [rsp+78h+var_58], rax
0x180097e17  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097e1c  test    edi, edi
0x180097e1e  jz      loc_180098239
0x180097e24  mov     edx, 14Fh
0x180097e29  jmp     loc_1800981EF
0x180097e2e  mov     rcx, [rbp+hModule]; hModule
0x180097e32  lea     rdx, aGetidentityaut; "GetIdentityAuthority"
0x180097e39  call    cs:__imp_GetProcAddress
0x180097e40  nop     dword ptr [rax+rax+00h]
0x180097e45  mov     cs:?vpfnGetIdentityAuthority@@3P6AJPEAPEAUIIdentityAuthority@@@ZEA, rax; long (*vpfnGetIdentityAuthority)(IIdentityAuthority * *)
0x180097e4c  test    rax, rax
0x180097e4f  jnz     short loc_180097ECF
0x180097e51  call    cs:__imp_GetLastError
0x180097e58  nop     dword ptr [rax+rax+00h]
0x180097e5d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097e64  mov     edi, eax
0x180097e66  test    rcx, rcx
0x180097e69  jz      short loc_180097EBD
0x180097e6b  mov     ebx, 3
0x180097e70  lea     r9, aFailedToGetPro_23; "Failed to get proc address for GetIdent"...
0x180097e77  mov     r8d, ebx
0x180097e7a  xor     edx, edx
0x180097e7c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097e81  test    edi, edi
0x180097e83  jg      short loc_180097E89
0x180097e85  mov     eax, edi
0x180097e87  jmp     short loc_180097E91
0x180097e89  movzx   eax, di
0x180097e8c  or      eax, 80070000h
0x180097e91  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097e98  lea     r9, a0; ": {0}"
0x180097e9f  mov     [rbp+var_28], eax
0x180097ea2  mov     r8d, ebx
0x180097ea5  lea     rax, [rbp+var_28]
0x180097ea9  mov     dl, 1
0x180097eab  mov     qword ptr [rbp+var_18], rax
0x180097eaf  lea     rax, [rbp+var_18]
0x180097eb3  mov     qword ptr [rsp+78h+var_58], rax
0x180097eb8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097ebd  test    edi, edi
0x180097ebf  jz      loc_180098239
0x180097ec5  mov     edx, 152h
0x180097eca  jmp     loc_1800981EF
0x180097ecf  mov     rcx, [rbp+hModule]; hModule
0x180097ed3  lea     rdx, aGetsystemstore; "GetSystemStore"
0x180097eda  call    cs:__imp_GetProcAddress
0x180097ee1  nop     dword ptr [rax+rax+00h]
0x180097ee6  mov     cs:?vpfnGetSystemStore@@3P6AJKAEBU_GUID@@PEAPEAUIUnknown@@@ZEA, rax; long (*vpfnGetSystemStore)(ulong,_GUID const &,IUnknown * *)
0x180097eed  test    rax, rax
0x180097ef0  jnz     short loc_180097F70
0x180097ef2  call    cs:__imp_GetLastError
0x180097ef9  nop     dword ptr [rax+rax+00h]
0x180097efe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097f05  mov     edi, eax
0x180097f07  test    rcx, rcx
0x180097f0a  jz      short loc_180097F5E
0x180097f0c  mov     ebx, 3
0x180097f11  lea     r9, aFailedToGetPro_49; "Failed to get proc address for GetSyste"...
0x180097f18  mov     r8d, ebx
0x180097f1b  xor     edx, edx
0x180097f1d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097f22  test    edi, edi
0x180097f24  jg      short loc_180097F2A
0x180097f26  mov     eax, edi
0x180097f28  jmp     short loc_180097F32
0x180097f2a  movzx   eax, di
0x180097f2d  or      eax, 80070000h
0x180097f32  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097f39  lea     r9, a0; ": {0}"
0x180097f40  mov     [rbp+var_28], eax
0x180097f43  mov     r8d, ebx
0x180097f46  lea     rax, [rbp+var_28]
0x180097f4a  mov     dl, 1
0x180097f4c  mov     qword ptr [rbp+var_18], rax
0x180097f50  lea     rax, [rbp+var_18]
0x180097f54  mov     qword ptr [rsp+78h+var_58], rax
0x180097f59  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097f5e  test    edi, edi
0x180097f60  jz      loc_180098239
0x180097f66  mov     edx, 155h
0x180097f6b  jmp     loc_1800981EF
0x180097f70  mov     rcx, [rbp+hModule]; hModule
0x180097f74  lea     rdx, aOpenexistingof; "OpenExistingOfflineStore"
0x180097f7b  call    cs:__imp_GetProcAddress
0x180097f82  nop     dword ptr [rax+rax+00h]
0x180097f87  mov     cs:?vpfnOpenExistingOfflineStore@@3P6AJKPEBU_OFFLINE_STORE_CREATION_PARAMETERS@@AEBU_GUID@@PEAPEAUIUnknown@@PEAK@ZEA, rax; long (*vpfnOpenExistingOfflineStore)(ulong,_OFFLINE_STORE_CREATION_PARAMETERS const *,_GUID const &,IUnknown * *,ulong *)
0x180097f8e  test    rax, rax
0x180097f91  jnz     short loc_180098011
0x180097f93  call    cs:__imp_GetLastError
0x180097f9a  nop     dword ptr [rax+rax+00h]
0x180097f9f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097fa6  mov     edi, eax
0x180097fa8  test    rcx, rcx
0x180097fab  jz      short loc_180097FFF
0x180097fad  mov     ebx, 3
0x180097fb2  lea     r9, aFailedToGetPro_46; "Failed to get proc address for OpenExis"...
0x180097fb9  mov     r8d, ebx
0x180097fbc  xor     edx, edx
0x180097fbe  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097fc3  test    edi, edi
0x180097fc5  jg      short loc_180097FCB
0x180097fc7  mov     eax, edi
0x180097fc9  jmp     short loc_180097FD3
0x180097fcb  movzx   eax, di
0x180097fce  or      eax, 80070000h
0x180097fd3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097fda  lea     r9, a0; ": {0}"
0x180097fe1  mov     [rbp+var_28], eax
0x180097fe4  mov     r8d, ebx
0x180097fe7  lea     rax, [rbp+var_28]
0x180097feb  mov     dl, 1
0x180097fed  mov     qword ptr [rbp+var_18], rax
0x180097ff1  lea     rax, [rbp+var_18]
0x180097ff5  mov     qword ptr [rsp+78h+var_58], rax
0x180097ffa  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097fff  test    edi, edi
0x180098001  jz      loc_180098239
0x180098007  mov     edx, 159h
0x18009800c  jmp     loc_1800981EF
0x180098011  mov     rcx, [rbp+hModule]; hModule
0x180098015  lea     rdx, aWcpinitialize; "WcpInitialize"
0x18009801c  call    cs:__imp_GetProcAddress
0x180098023  nop     dword ptr [rax+rax+00h]
0x180098028  mov     cs:?vpfnWcpInitialize@@3P6AJPEA_K@ZEA, rax; long (*vpfnWcpInitialize)(unsigned __int64 *)
0x18009802f  test    rax, rax
0x180098032  jnz     short loc_1800980B2
0x180098034  call    cs:__imp_GetLastError
0x18009803b  nop     dword ptr [rax+rax+00h]
0x180098040  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180098047  mov     edi, eax
0x180098049  test    rcx, rcx
0x18009804c  jz      short loc_1800980A0
0x18009804e  mov     ebx, 3
0x180098053  lea     r9, aFailedToGetPro_10; "Failed to get proc address for WcpIniti"...
0x18009805a  mov     r8d, ebx
0x18009805d  xor     edx, edx
0x18009805f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180098064  test    edi, edi
0x180098066  jg      short loc_18009806C
0x180098068  mov     eax, edi
0x18009806a  jmp     short loc_180098074
0x18009806c  movzx   eax, di
0x18009806f  or      eax, 80070000h
0x180098074  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009807b  lea     r9, a0; ": {0}"
0x180098082  mov     [rbp+var_28], eax
0x180098085  mov     r8d, ebx
0x180098088  lea     rax, [rbp+var_28]
0x18009808c  mov     dl, 1
0x18009808e  mov     qword ptr [rbp+var_18], rax
0x180098092  lea     rax, [rbp+var_18]
0x180098096  mov     qword ptr [rsp+78h+var_58], rax
0x18009809b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800980a0  test    edi, edi
0x1800980a2  jz      loc_180098239
0x1800980a8  mov     edx, 15Ch
0x1800980ad  jmp     loc_1800981EF
0x1800980b2  mov     rcx, [rbp+hModule]; hModule
0x1800980b6  lea     rdx, aWcpshutdown; "WcpShutdown"
0x1800980bd  call    cs:__imp_GetProcAddress
0x1800980c4  nop     dword ptr [rax+rax+00h]
0x1800980c9  mov     cs:?vpfnWcpShutdown@@3P6AX_K@ZEA, rax; void (*vpfnWcpShutdown)(unsigned __int64)
  ... truncated ...
```
