# CfgMgr32Load(wchar_t const *,HINSTANCE__ * *)

- ea: `0x1800cf2f0`
- end: `0x1800cf6f1`
- name: `?CfgMgr32Load@@YAJPEB_WPEAPEAUHINSTANCE__@@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(const wchar_t *, HINSTANCE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800f3f0c`

## callees

- `0x180013250`
- `0x180015420`
- `0x180016d40`
- `0x180049ec0`
- `0x18005aa38`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800cf2f0`
- `0x1800eb920`
- `0x1800ec920`
- `0x18012cfe0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800cf535`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800cf5ff`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800cf535`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800cf5ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf34b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf34b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf617`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800cf465`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800cf465`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800cf337`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800cf337`

## string_xrefs

- `0x1800cf570`: `Failed to get proc address for CMP_WaitNoPendingInstallEvents`
- `0x1800cf636`: `Failed to get proc address for CMP_GetServerSideDeviceInstallFlags`
- `0x1800cf4a1`: `Failed to load DrUpdate DLL: {}`
- `0x1800cf36a`: `Failed to get windows directory Drupdate path.`
- `0x1800cf442`: `system32\`
- `0x1800cf526`: `CMP_WaitNoPendingInstallEvents`
- `0x1800cf5f5`: `CMP_GetServerSideDeviceInstallFlags`
- `0x1800cf43b`: `CfgMgr32.dll`

## pseudocode

```c
int __fastcall CfgMgr32Load(const wchar_t *a1, HINSTANCE *a2)
{
  signed int v2; // edi
  unsigned int v3; // eax
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rdx
  HMODULE LibraryW; // rax
  HMODULE v9; // rbx
  signed int LastError; // edi
  unsigned int v11; // eax
  signed int v12; // edi
  unsigned int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // [rsp+20h] [rbp-E0h]
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE v18; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpLibFileName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  memset_0(Buffer, 0, 0x208u);
  if ( GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    lpLibFileName = 0;
    v5 = SczAllocFromSz(&lpLibFileName, Buffer);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 392;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsdrupwrapper.cpp",
        (const char *)(unsigned int)v5,
        v16);
LABEL_46:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
      return v6;
    }
    v5 = SczEnsureBackslashTerminated(&lpLibFileName);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 394;
      goto LABEL_14;
    }
    v5 = SczAllocConcat2Sz(&lpLibFileName, L"system32\\", L"CfgMgr32.dll");
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 396;
      goto LABEL_14;
    }
    LibraryW = LoadLibraryW(lpLibFileName);
    v18 = LibraryW;
    v9 = LibraryW;
    if ( !LibraryW )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load DrUpdate DLL: {}");
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        else
          v11 = LastError;
        v17 = v11;
        *(_QWORD *)v20 = &v17;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v20);
      }
      if ( LastError )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x18F,
               (unsigned int)"onecore\\base\\cbs\\core\\cbsdrupwrapper.cpp",
               (const char *)(unsigned int)LastError,
               v16);
LABEL_25:
        Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v18);
        goto LABEL_46;
      }
LABEL_45:
      Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v18);
      v6 = 0;
      goto LABEL_46;
    }
    LOBYTE(v17) = 1;
    vpfnCMP_WaitNoPendingInstallEvents = (unsigned int (*)(unsigned int))GetProcAddress(
                                                                           LibraryW,
                                                                           "CMP_WaitNoPendingInstallEvents");
    if ( vpfnCMP_WaitNoPendingInstallEvents )
    {
      vpfnCMP_GetServerSideDeviceInstallFlags = (unsigned int (*)(unsigned int *, unsigned int, void *))GetProcAddress(v9, "CMP_GetServerSideDeviceInstallFlags");
      if ( vpfnCMP_GetServerSideDeviceInstallFlags )
      {
        v18 = 0;
        vhCfgMgr32Dll = v9;
        LOBYTE(v17) = 0;
      }
      else
      {
        v12 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for CMP_GetServerSideDeviceInstallFlags");
          if ( v12 > 0 )
            v15 = (unsigned __int16)v12 | 0x80070000;
          else
            v15 = v12;
          v20[0] = v15;
          *(_QWORD *)v21 = v20;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v21);
        }
        if ( v12 )
        {
          v14 = 416;
          goto LABEL_34;
        }
      }
    }
    else
    {
      v12 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for CMP_WaitNoPendingInstallEvents");
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        else
          v13 = v12;
        v20[0] = v13;
        *(_QWORD *)v21 = v20;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v21);
      }
      if ( v12 )
      {
        v14 = 411;
LABEL_34:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v14,
               (unsigned int)"onecore\\base\\cbs\\core\\cbsdrupwrapper.cpp",
               (const char *)(unsigned int)v12,
               v16);
        Windows::Detail::OnBlockExitImpl__CfgMgr32Load_::_2_::_lambda_1___::_OnBlockExitImpl__CfgMgr32Load_::_2_::_lambda_1___(&v17);
        goto LABEL_25;
      }
    }
    Windows::Detail::OnBlockExitImpl__CfgMgr32Load_::_2_::_lambda_1___::_OnBlockExitImpl__CfgMgr32Load_::_2_::_lambda_1___(&v17);
    goto LABEL_45;
  }
  v2 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get windows directory Drupdate path.");
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    else
      v3 = v2;
    v17 = v3;
    lpLibFileName = (LPCWSTR)&v17;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {0}",
      (__int64)&lpLibFileName);
  }
  if ( v2 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x185,
             (unsigned int)"onecore\\base\\cbs\\core\\cbsdrupwrapper.cpp",
             (const char *)(unsigned int)v2,
             v16);
  else
    return 0;
}

```

## disassembly

```asm
0x1800cf2f0  mov     [rsp-8+arg_0], rbx
0x1800cf2f5  mov     [rsp-8+arg_8], rdi
0x1800cf2fa  push    rbp
0x1800cf2fb  lea     rbp, [rsp-180h]
0x1800cf303  sub     rsp, 280h
0x1800cf30a  mov     rax, cs:__security_cookie
0x1800cf311  xor     rax, rsp
0x1800cf314  mov     [rbp+180h+var_10], rax
0x1800cf31b  xor     edx, edx; Val
0x1800cf31d  lea     rcx, [rsp+280h+Buffer]; void *
0x1800cf322  mov     r8d, 208h; Size
0x1800cf328  call    memset_0
0x1800cf32d  mov     edx, 104h; uSize
0x1800cf332  lea     rcx, [rsp+280h+Buffer]; lpBuffer
0x1800cf337  call    cs:__imp_GetWindowsDirectoryW
0x1800cf33e  nop     dword ptr [rax+rax+00h]
0x1800cf343  test    eax, eax
0x1800cf345  jnz     loc_1800CF3E6
0x1800cf34b  call    cs:__imp_GetLastError
0x1800cf352  nop     dword ptr [rax+rax+00h]
0x1800cf357  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf35e  mov     edi, eax
0x1800cf360  test    rcx, rcx
0x1800cf363  jz      short loc_1800CF3BB
0x1800cf365  mov     ebx, 3
0x1800cf36a  lea     r9, aFailedToGetWin_5; "Failed to get windows directory Drupdat"...
0x1800cf371  mov     r8d, ebx
0x1800cf374  xor     edx, edx
0x1800cf376  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cf37b  test    edi, edi
0x1800cf37d  jg      short loc_1800CF383
0x1800cf37f  mov     eax, edi
0x1800cf381  jmp     short loc_1800CF38B
0x1800cf383  movzx   eax, di
0x1800cf386  or      eax, 80070000h
0x1800cf38b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf392  lea     r9, a0; ": {0}"
0x1800cf399  mov     [rsp+280h+var_250], eax
0x1800cf39d  mov     r8d, ebx
0x1800cf3a0  lea     rax, [rsp+280h+var_250]
0x1800cf3a5  mov     dl, 1
0x1800cf3a7  mov     [rsp+280h+lpLibFileName], rax
0x1800cf3ac  lea     rax, [rsp+280h+lpLibFileName]
0x1800cf3b1  mov     qword ptr [rsp+280h+var_260], rax; unsigned int
0x1800cf3b6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cf3bb  test    edi, edi
0x1800cf3bd  jz      short loc_1800CF3DF
0x1800cf3bf  mov     rcx, [rbp+188h]; this
0x1800cf3c6  lea     r8, aOnecoreBaseCbs_45; "onecore\\base\\cbs\\core\\cbsdrupwrappe"...
0x1800cf3cd  mov     r9d, edi; char *
0x1800cf3d0  mov     edx, 185h; void *
0x1800cf3d5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cf3da  jmp     loc_1800CF6CC
0x1800cf3df  xor     eax, eax
0x1800cf3e1  jmp     loc_1800CF6CC
0x1800cf3e6  lea     rdx, [rsp+280h+Buffer]
0x1800cf3eb  mov     [rsp+280h+lpLibFileName], 0
0x1800cf3f4  lea     rcx, [rsp+280h+lpLibFileName]
0x1800cf3f9  call    SczAllocFromSz
0x1800cf3fe  mov     ebx, eax
0x1800cf400  test    eax, eax
0x1800cf402  jns     short loc_1800CF40B
0x1800cf404  mov     edx, 188h
0x1800cf409  jmp     short loc_1800CF420
0x1800cf40b  lea     rcx, [rsp+280h+lpLibFileName]
0x1800cf410  call    SczEnsureBackslashTerminated
0x1800cf415  mov     ebx, eax
0x1800cf417  test    eax, eax
0x1800cf419  jns     short loc_1800CF43B
0x1800cf41b  mov     edx, 18Ah; void *
0x1800cf420  mov     rcx, [rbp+188h]; this
0x1800cf427  lea     r8, aOnecoreBaseCbs_45; "onecore\\base\\cbs\\core\\cbsdrupwrappe"...
0x1800cf42e  mov     r9d, eax; char *
0x1800cf431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf436  jmp     loc_1800CF6C0
0x1800cf43b  lea     r8, aCfgmgr32Dll; "CfgMgr32.dll"
0x1800cf442  lea     rdx, aSystem32; "system32\\"
0x1800cf449  lea     rcx, [rsp+280h+lpLibFileName]
0x1800cf44e  call    SczAllocConcat2Sz
0x1800cf453  mov     ebx, eax
0x1800cf455  test    eax, eax
0x1800cf457  jns     short loc_1800CF460
0x1800cf459  mov     edx, 18Ch
0x1800cf45e  jmp     short loc_1800CF420
0x1800cf460  mov     rcx, [rsp+280h+lpLibFileName]; lpLibFileName
0x1800cf465  call    cs:__imp_LoadLibraryW
0x1800cf46c  nop     dword ptr [rax+rax+00h]
0x1800cf471  mov     [rsp+280h+var_248], rax
0x1800cf476  mov     rbx, rax
0x1800cf479  test    rax, rax
0x1800cf47c  jnz     loc_1800CF526
0x1800cf482  call    cs:__imp_GetLastError
0x1800cf489  nop     dword ptr [rax+rax+00h]
0x1800cf48e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf495  mov     edi, eax
0x1800cf497  test    rcx, rcx
0x1800cf49a  jz      short loc_1800CF4F2
0x1800cf49c  mov     ebx, 3
0x1800cf4a1  lea     r9, aFailedToLoadDr_0; "Failed to load DrUpdate DLL: {}"
0x1800cf4a8  mov     r8d, ebx
0x1800cf4ab  xor     edx, edx
0x1800cf4ad  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cf4b2  test    edi, edi
0x1800cf4b4  jg      short loc_1800CF4BA
0x1800cf4b6  mov     eax, edi
0x1800cf4b8  jmp     short loc_1800CF4C2
0x1800cf4ba  movzx   eax, di
0x1800cf4bd  or      eax, 80070000h
0x1800cf4c2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf4c9  lea     r9, a0; ": {0}"
0x1800cf4d0  mov     [rsp+280h+var_250], eax
0x1800cf4d4  mov     r8d, ebx
0x1800cf4d7  lea     rax, [rsp+280h+var_250]
0x1800cf4dc  mov     dl, 1
0x1800cf4de  mov     qword ptr [rsp+280h+var_238], rax
0x1800cf4e3  lea     rax, [rsp+280h+var_238]
0x1800cf4e8  mov     qword ptr [rsp+280h+var_260], rax; unsigned int
0x1800cf4ed  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cf4f2  test    edi, edi
0x1800cf4f4  jz      loc_1800CF6B4
0x1800cf4fa  mov     rcx, [rbp+188h]; this
0x1800cf501  lea     r8, aOnecoreBaseCbs_45; "onecore\\base\\cbs\\core\\cbsdrupwrappe"...
0x1800cf508  mov     r9d, edi; char *
0x1800cf50b  mov     edx, 18Fh; void *
0x1800cf510  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cf515  mov     ebx, eax
0x1800cf517  lea     rcx, [rsp+280h+var_248]
0x1800cf51c  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800cf521  jmp     loc_1800CF6C0
0x1800cf526  lea     rdx, aCmpWaitnopendi; "CMP_WaitNoPendingInstallEvents"
0x1800cf52d  mov     byte ptr [rsp+280h+var_250], 1
0x1800cf532  mov     rcx, rbx; hModule
0x1800cf535  call    cs:__imp_GetProcAddress
0x1800cf53c  nop     dword ptr [rax+rax+00h]
0x1800cf541  mov     cs:?vpfnCMP_WaitNoPendingInstallEvents@@3P6AKK@ZEA, rax; ulong (*vpfnCMP_WaitNoPendingInstallEvents)(ulong)
0x1800cf548  test    rax, rax
0x1800cf54b  jnz     loc_1800CF5F5
0x1800cf551  call    cs:__imp_GetLastError
0x1800cf558  nop     dword ptr [rax+rax+00h]
0x1800cf55d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf564  mov     edi, eax
0x1800cf566  test    rcx, rcx
0x1800cf569  jz      short loc_1800CF5C1
0x1800cf56b  mov     ebx, 3
0x1800cf570  lea     r9, aFailedToGetPro_47; "Failed to get proc address for CMP_Wait"...
0x1800cf577  mov     r8d, ebx
0x1800cf57a  xor     edx, edx
0x1800cf57c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cf581  test    edi, edi
0x1800cf583  jg      short loc_1800CF589
0x1800cf585  mov     eax, edi
0x1800cf587  jmp     short loc_1800CF591
0x1800cf589  movzx   eax, di
0x1800cf58c  or      eax, 80070000h
0x1800cf591  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf598  lea     r9, a0; ": {0}"
0x1800cf59f  mov     [rsp+280h+var_238], eax
0x1800cf5a3  mov     r8d, ebx
0x1800cf5a6  lea     rax, [rsp+280h+var_238]
0x1800cf5ab  mov     dl, 1
0x1800cf5ad  mov     qword ptr [rsp+280h+var_230], rax
0x1800cf5b2  lea     rax, [rsp+280h+var_230]
0x1800cf5b7  mov     qword ptr [rsp+280h+var_260], rax; unsigned int
0x1800cf5bc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cf5c1  test    edi, edi
0x1800cf5c3  jz      loc_1800CF6AA
0x1800cf5c9  mov     edx, 19Bh; void *
0x1800cf5ce  mov     rcx, [rbp+188h]; this
0x1800cf5d5  lea     r8, aOnecoreBaseCbs_45; "onecore\\base\\cbs\\core\\cbsdrupwrappe"...
0x1800cf5dc  mov     r9d, edi; char *
0x1800cf5df  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cf5e4  lea     rcx, [rsp+280h+var_250]
0x1800cf5e9  mov     ebx, eax
0x1800cf5eb  call    Windows__Detail__OnBlockExitImpl__CfgMgr32Load____2____lambda_1______OnBlockExitImpl__CfgMgr32Load____2____lambda_1___
0x1800cf5f0  jmp     loc_1800CF517
0x1800cf5f5  lea     rdx, aCmpGetserversi; "CMP_GetServerSideDeviceInstallFlags"
0x1800cf5fc  mov     rcx, rbx; hModule
0x1800cf5ff  call    cs:__imp_GetProcAddress
0x1800cf606  nop     dword ptr [rax+rax+00h]
0x1800cf60b  mov     cs:?vpfnCMP_GetServerSideDeviceInstallFlags@@3P6AKPEAKKPEAX@ZEA, rax; ulong (*vpfnCMP_GetServerSideDeviceInstallFlags)(ulong *,ulong,void *)
0x1800cf612  test    rax, rax
0x1800cf615  jnz     short loc_1800CF695
0x1800cf617  call    cs:__imp_GetLastError
0x1800cf61e  nop     dword ptr [rax+rax+00h]
0x1800cf623  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf62a  mov     edi, eax
0x1800cf62c  test    rcx, rcx
0x1800cf62f  jz      short loc_1800CF687
0x1800cf631  mov     ebx, 3
0x1800cf636  lea     r9, aFailedToGetPro_50; "Failed to get proc address for CMP_GetS"...
0x1800cf63d  mov     r8d, ebx
0x1800cf640  xor     edx, edx
0x1800cf642  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cf647  test    edi, edi
0x1800cf649  jg      short loc_1800CF64F
0x1800cf64b  mov     eax, edi
0x1800cf64d  jmp     short loc_1800CF657
0x1800cf64f  movzx   eax, di
0x1800cf652  or      eax, 80070000h
0x1800cf657  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf65e  lea     r9, a0; ": {0}"
0x1800cf665  mov     [rsp+280h+var_238], eax
0x1800cf669  mov     r8d, ebx
0x1800cf66c  lea     rax, [rsp+280h+var_238]
0x1800cf671  mov     dl, 1
0x1800cf673  mov     qword ptr [rsp+280h+var_230], rax
0x1800cf678  lea     rax, [rsp+280h+var_230]
0x1800cf67d  mov     qword ptr [rsp+280h+var_260], rax
0x1800cf682  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cf687  test    edi, edi
0x1800cf689  jz      short loc_1800CF6AA
0x1800cf68b  mov     edx, 1A0h
0x1800cf690  jmp     loc_1800CF5CE
0x1800cf695  mov     [rsp+280h+var_248], 0
0x1800cf69e  mov     cs:?vhCfgMgr32Dll@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * vhCfgMgr32Dll
0x1800cf6a5  mov     byte ptr [rsp+280h+var_250], 0
0x1800cf6aa  lea     rcx, [rsp+280h+var_250]
0x1800cf6af  call    Windows__Detail__OnBlockExitImpl__CfgMgr32Load____2____lambda_1______OnBlockExitImpl__CfgMgr32Load____2____lambda_1___
0x1800cf6b4  lea     rcx, [rsp+280h+var_248]
0x1800cf6b9  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800cf6be  xor     ebx, ebx
0x1800cf6c0  lea     rcx, [rsp+280h+lpLibFileName]
0x1800cf6c5  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800cf6ca  mov     eax, ebx
0x1800cf6cc  mov     rcx, [rbp+180h+var_10]
0x1800cf6d3  xor     rcx, rsp; StackCookie
0x1800cf6d6  call    __security_check_cookie
0x1800cf6db  lea     r11, [rsp+280h+var_s0]
0x1800cf6e3  mov     rbx, [r11+10h]
0x1800cf6e7  mov     rdi, [r11+18h]
0x1800cf6eb  mov     rsp, r11
0x1800cf6ee  pop     rbp
0x1800cf6ef  retn
```
