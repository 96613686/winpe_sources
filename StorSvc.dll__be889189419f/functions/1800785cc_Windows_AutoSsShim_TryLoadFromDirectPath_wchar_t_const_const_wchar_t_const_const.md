# Windows::AutoSsShim::TryLoadFromDirectPath(wchar_t const * const,wchar_t const * const)

- ea: `0x1800785cc`
- end: `0x180078906`
- name: `?TryLoadFromDirectPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z`
- size: `826`
- prototype: `__int64 __fastcall(Windows::AutoSsShim *this, const WCHAR *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007890c`

## callees

- `0x18000d030`
- `0x180013354`
- `0x18006a198`
- `0x18006a2a8`
- `0x180078000`
- `0x180078178`
- `0x180078570`
- `0x1800785cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007869e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007870a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078776`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800787df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007886a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007887e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007869e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007870a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078776`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800787df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007886a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007887e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007863d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007863d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007864f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800786ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800786ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007875a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007884e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007864f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800786ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800786ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007875a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007884e`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180078627`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180078627`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x180078618`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x180078618`

## string_xrefs

- `0x1800786de`: `m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>("SssBindServicingStack", LocalSsShimDll)`
- `0x18007874a`: `m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>("SssReleaseServicingStack", LocalSsShimDll)`
- `0x1800786d3`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x18007873f`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x1800787ab`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180078814`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x1800787b6`: `m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>("SssGetServicingStackFilePathLength", LocalSsShimDll)`
- `0x18007876c`: `SssGetServicingStackFilePathLength`
- `0x18007881f`: `m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>("SssGetServicingStackFilePath", LocalSsShimDll)`
- `0x1800787d5`: `SssGetServicingStackFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AutoSsShim::TryLoadFromDirectPath(
        Windows::AutoSsShim *this,
        const WCHAR *a2,
        const wchar_t *const a3)
{
  bool v3; // zf
  DWORD ThreadErrorMode; // eax
  wil::details::in1diag3 *v7; // rcx
  HMODULE v8; // rbx
  signed int LastError; // ebx
  int v10; // ecx
  FARPROC ProcAddress; // rax
  DWORD v12; // ebx
  _QWORD *v13; // rdx
  int v14; // ecx
  FARPROC v15; // rax
  int v16; // ecx
  FARPROC v17; // rax
  int v18; // ecx
  FARPROC v19; // rax
  int v21; // ecx
  int v22; // ecx
  HMODULE Library; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v24[4]; // [rsp+28h] [rbp-51h] BYREF
  _QWORD v25[4]; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v26[4]; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v27[4]; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v28; // [rsp+A8h] [rbp+2Fh] BYREF
  __int64 v29; // [rsp+B8h] [rbp+3Fh]
  int v30; // [rsp+C0h] [rbp+47h] BYREF
  DWORD OldMode; // [rsp+C4h] [rbp+4Bh] BYREF

  v3 = *(_QWORD *)this == 0;
  v30 = 0;
  if ( !v3 )
    INTERNAL_ERROR_ACTION((int)this);
  v28 = 0;
  v29 = 0;
  OldMode = 0;
  ThreadErrorMode = GetThreadErrorMode();
  if ( !SetThreadErrorMode(ThreadErrorMode | 1, &OldMode) )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v7);
  Library = LoadLibraryExW(a2, 0, 0);
  v8 = Library;
  if ( !Library )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        INTERNAL_ERROR_ACTION(v10);
    }
    else
    {
      LastError = 14077;
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Windows::AutoThreadMode::~AutoThreadMode((Windows::AutoThreadMode *)&OldMode);
    goto LABEL_34;
  }
  Windows::AutoThreadMode::~AutoThreadMode((Windows::AutoThreadMode *)&OldMode);
  ProcAddress = GetProcAddress(Library, "SssBindServicingStack");
  *((_QWORD *)this + 2) = ProcAddress;
  if ( !ProcAddress )
  {
    if ( GetLastError() )
    {
      v12 = GetLastError();
      if ( !v12 )
        INTERNAL_ERROR_ACTION(v14);
    }
    else
    {
      v12 = 14077;
    }
    v24[2] = 115;
    v24[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v13 = v24;
    v24[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v24[3] = "m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>(\"SssBindServicingStack\", LocalSsShimDll)";
LABEL_33:
    LastError = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateWin32Error(
                  &v30,
                  v13,
                  v12);
LABEL_34:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&Library);
    Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v28);
    return (unsigned int)LastError;
  }
  v15 = GetProcAddress(v8, "SssReleaseServicingStack");
  *((_QWORD *)this + 3) = v15;
  if ( !v15 )
  {
    if ( GetLastError() )
    {
      v12 = GetLastError();
      if ( !v12 )
        INTERNAL_ERROR_ACTION(v16);
    }
    else
    {
      v12 = 14077;
    }
    v25[2] = 116;
    v25[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v13 = v25;
    v25[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v25[3] = "m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>(\"SssReleaseServicingStack\", LocalSsShimDll)";
    goto LABEL_33;
  }
  v17 = GetProcAddress(v8, "SssGetServicingStackFilePathLength");
  *((_QWORD *)this + 5) = v17;
  if ( !v17 )
  {
    if ( GetLastError() )
    {
      v12 = GetLastError();
      if ( !v12 )
        INTERNAL_ERROR_ACTION(v18);
    }
    else
    {
      v12 = 14077;
    }
    v26[2] = 117;
    v26[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v13 = v26;
    v26[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v26[3] = "m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>(\"SssGetSer"
             "vicingStackFilePathLength\", LocalSsShimDll)";
    goto LABEL_33;
  }
  v19 = GetProcAddress(v8, "SssGetServicingStackFilePath");
  *((_QWORD *)this + 6) = v19;
  if ( !v19 )
  {
    if ( GetLastError() )
    {
      v12 = GetLastError();
      if ( !v12 )
        INTERNAL_ERROR_ACTION(v21);
    }
    else
    {
      v12 = 14077;
    }
    v27[2] = 118;
    v27[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v13 = v27;
    v27[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v27[3] = "m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>(\"SssGetServicingStackF"
             "ilePath\", LocalSsShimDll)";
    goto LABEL_33;
  }
  *((_QWORD *)this + 4) = GetProcAddress(v8, "SssPreloadDownlevelDependencies");
  *((_QWORD *)this + 7) = GetProcAddress(v8, "SssGetServicingStackVersion");
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(this);
  v3 = *(_QWORD *)this == 0;
  Library = 0;
  if ( !v3 )
    INTERNAL_ERROR_ACTION(v22);
  *(_QWORD *)this = v8;
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&Library);
  Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v28);
  return 0;
}

```

## disassembly

```asm
0x1800785cc  mov     [rsp-8+arg_10], rbx
0x1800785d1  mov     [rsp-8+arg_18], rdi
0x1800785d6  push    rbp
0x1800785d7  lea     rbp, [rsp-57h]
0x1800785dc  sub     rsp, 0D0h
0x1800785e3  mov     rax, cs:__security_cookie
0x1800785ea  xor     rax, rsp
0x1800785ed  mov     [rbp+57h+var_8], rax
0x1800785f1  cmp     qword ptr [rcx], 0
0x1800785f5  mov     rbx, rdx
0x1800785f8  mov     rdi, rcx
0x1800785fb  mov     [rbp+57h+var_10], 0
0x180078602  jnz     loc_1800788FA
0x180078608  xor     eax, eax
0x18007860a  xorps   xmm0, xmm0
0x18007860d  movups  [rbp+57h+var_28], xmm0
0x180078611  mov     [rbp+57h+var_18], rax
0x180078615  mov     [rbp+57h+OldMode], eax
0x180078618  call    cs:__imp_GetThreadErrorMode
0x18007861e  or      eax, 1
0x180078621  lea     rdx, [rbp+57h+OldMode]; lpOldMode
0x180078625  mov     ecx, eax; dwNewMode
0x180078627  call    cs:__imp_SetThreadErrorMode
0x18007862d  test    eax, eax
0x18007862f  jz      loc_180078900
0x180078635  xor     r8d, r8d; dwFlags
0x180078638  xor     edx, edx; hFile
0x18007863a  mov     rcx, rbx; lpLibFileName
0x18007863d  call    cs:__imp_LoadLibraryExW
0x180078643  mov     [rbp+57h+var_B0], rax
0x180078647  mov     rbx, rax
0x18007864a  test    rax, rax
0x18007864d  jnz     short loc_18007868B
0x18007864f  call    cs:__imp_GetLastError
0x180078655  test    eax, eax
0x180078657  jnz     short loc_180078679
0x180078659  mov     ebx, 36FDh
0x18007865e  test    ebx, ebx
0x180078660  jle     short loc_18007866B
0x180078662  movzx   ebx, bx
0x180078665  or      ebx, 80070000h
0x18007866b  lea     rcx, [rbp+57h+OldMode]; this
0x18007866f  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x180078674  jmp     loc_180078838
0x180078679  call    cs:__imp_GetLastError
0x18007867f  mov     ebx, eax
0x180078681  test    eax, eax
0x180078683  jz      loc_1800788DC
0x180078689  jmp     short loc_18007865E
0x18007868b  lea     rcx, [rbp+57h+OldMode]; this
0x18007868f  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x180078694  lea     rdx, aSssbindservici; "SssBindServicingStack"
0x18007869b  mov     rcx, rbx; hModule
0x18007869e  call    cs:__imp_GetProcAddress
0x1800786a4  mov     [rdi+10h], rax
0x1800786a8  test    rax, rax
0x1800786ab  jnz     short loc_180078700
0x1800786ad  call    cs:__imp_GetLastError
0x1800786b3  test    eax, eax
0x1800786b5  jnz     short loc_1800786EE
0x1800786b7  mov     ebx, 36FDh
0x1800786bc  lea     rax, aOnecoreBaseWcp_2; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x1800786c3  mov     [rbp+57h+var_98], 73h ; 's'
0x1800786cb  mov     [rbp+57h+var_A8], rax
0x1800786cf  lea     rdx, [rbp+57h+var_A8]
0x1800786d3  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x1800786da  mov     [rbp+57h+var_A0], rax
0x1800786de  lea     rax, aMPfnsssbindser; "m_pfnSssBindServicingStack = GetProc<de"...
0x1800786e5  mov     [rbp+57h+var_90], rax
0x1800786e9  jmp     loc_18007882A
0x1800786ee  call    cs:__imp_GetLastError
0x1800786f4  mov     ebx, eax
0x1800786f6  test    eax, eax
0x1800786f8  jz      loc_1800788E2
0x1800786fe  jmp     short loc_1800786BC
0x180078700  lea     rdx, aSssreleaseserv; "SssReleaseServicingStack"
0x180078707  mov     rcx, rbx; hModule
0x18007870a  call    cs:__imp_GetProcAddress
0x180078710  mov     [rdi+18h], rax
0x180078714  test    rax, rax
0x180078717  jnz     short loc_18007876C
0x180078719  call    cs:__imp_GetLastError
0x18007871f  test    eax, eax
0x180078721  jnz     short loc_18007875A
0x180078723  mov     ebx, 36FDh
0x180078728  lea     rax, aOnecoreBaseWcp_2; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x18007872f  mov     [rbp+57h+var_78], 74h ; 't'
0x180078737  mov     [rbp+57h+var_88], rax
0x18007873b  lea     rdx, [rbp+57h+var_88]
0x18007873f  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180078746  mov     [rbp+57h+var_80], rax
0x18007874a  lea     rax, aMPfnsssrelease; "m_pfnSssReleaseServicingStack = GetProc"...
0x180078751  mov     [rbp+57h+var_70], rax
0x180078755  jmp     loc_18007882A
0x18007875a  call    cs:__imp_GetLastError
0x180078760  mov     ebx, eax
0x180078762  test    eax, eax
0x180078764  jz      loc_1800788E8
0x18007876a  jmp     short loc_180078728
0x18007876c  lea     rdx, aSssgetservicin; "SssGetServicingStackFilePathLength"
0x180078773  mov     rcx, rbx; hModule
0x180078776  call    cs:__imp_GetProcAddress
0x18007877c  mov     [rdi+28h], rax
0x180078780  test    rax, rax
0x180078783  jnz     short loc_1800787D5
0x180078785  call    cs:__imp_GetLastError
0x18007878b  test    eax, eax
0x18007878d  jnz     short loc_1800787C3
0x18007878f  mov     ebx, 36FDh
0x180078794  lea     rax, aOnecoreBaseWcp_2; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x18007879b  mov     [rbp+57h+var_58], 75h ; 'u'
0x1800787a3  mov     [rbp+57h+var_68], rax
0x1800787a7  lea     rdx, [rbp+57h+var_68]
0x1800787ab  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x1800787b2  mov     [rbp+57h+var_60], rax
0x1800787b6  lea     rax, aMPfnsssgetserv_0; "m_pfnSssGetServicingStackFilePathLength"...
0x1800787bd  mov     [rbp+57h+var_50], rax
0x1800787c1  jmp     short loc_18007882A
0x1800787c3  call    cs:__imp_GetLastError
0x1800787c9  mov     ebx, eax
0x1800787cb  test    eax, eax
0x1800787cd  jz      loc_1800788EE
0x1800787d3  jmp     short loc_180078794
0x1800787d5  lea     rdx, aSssgetservicin_0; "SssGetServicingStackFilePath"
0x1800787dc  mov     rcx, rbx; hModule
0x1800787df  call    cs:__imp_GetProcAddress
0x1800787e5  mov     [rdi+30h], rax
0x1800787e9  test    rax, rax
0x1800787ec  jnz     short loc_180078860
0x1800787ee  call    cs:__imp_GetLastError
0x1800787f4  test    eax, eax
0x1800787f6  jnz     short loc_18007884E
0x1800787f8  mov     ebx, 36FDh
0x1800787fd  lea     rax, aOnecoreBaseWcp_2; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180078804  mov     [rbp+57h+var_38], 76h ; 'v'
0x18007880c  mov     [rbp+57h+var_48], rax
0x180078810  lea     rdx, [rbp+57h+var_48]
0x180078814  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x18007881b  mov     [rbp+57h+var_40], rax
0x18007881f  lea     rax, aMPfnsssgetserv; "m_pfnSssGetServicingStackFilePath = Get"...
0x180078826  mov     [rbp+57h+var_30], rax
0x18007882a  mov     r8d, ebx
0x18007882d  lea     rcx, [rbp+57h+var_10]
0x180078831  call    ?OriginateWin32Error@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@K@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateWin32Error(Windows::ErrorHandling::_RTL_CALL_SITE const &,ulong)
0x180078836  mov     ebx, eax
0x180078838  lea     rcx, [rbp+57h+var_B0]
0x18007883c  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180078841  lea     rcx, [rbp+57h+var_28]
0x180078845  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x18007884a  mov     eax, ebx
0x18007884c  jmp     short loc_1800788B5
0x18007884e  call    cs:__imp_GetLastError
0x180078854  mov     ebx, eax
0x180078856  test    eax, eax
0x180078858  jz      loc_1800788F4
0x18007885e  jmp     short loc_1800787FD
0x180078860  lea     rdx, aSsspreloaddown; "SssPreloadDownlevelDependencies"
0x180078867  mov     rcx, rbx; hModule
0x18007886a  call    cs:__imp_GetProcAddress
0x180078870  lea     rdx, aSssgetservicin_1; "SssGetServicingStackVersion"
0x180078877  mov     rcx, rbx; hModule
0x18007887a  mov     [rdi+20h], rax
0x18007887e  call    cs:__imp_GetProcAddress
0x180078884  mov     rcx, rdi
0x180078887  mov     [rdi+38h], rax
0x18007888b  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180078890  cmp     qword ptr [rdi], 0
0x180078894  mov     [rbp+57h+var_B0], 0
0x18007889c  jnz     short loc_1800788D6
0x18007889e  lea     rcx, [rbp+57h+var_B0]
0x1800788a2  mov     [rdi], rbx
0x1800788a5  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800788aa  lea     rcx, [rbp+57h+var_28]
0x1800788ae  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x1800788b3  xor     eax, eax
0x1800788b5  mov     rcx, [rbp+57h+var_8]
0x1800788b9  xor     rcx, rsp; StackCookie
0x1800788bc  call    __security_check_cookie
0x1800788c1  lea     r11, [rsp+0D0h+var_s0]
0x1800788c9  mov     rbx, [r11+20h]
0x1800788cd  mov     rdi, [r11+28h]
0x1800788d1  mov     rsp, r11
0x1800788d4  pop     rbp
0x1800788d5  retn
0x1800788d6  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1800788dc  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1800788e2  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1800788e8  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1800788ee  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1800788f4  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1800788fa  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x180078900  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
