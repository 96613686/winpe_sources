# Windows::AutoSsShim::TryLoadFromDirectPath(wchar_t const * const,wchar_t const * const)

- ea: `0x18003fdac`
- end: `0x180040275`
- name: `?TryLoadFromDirectPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z`
- size: `1225`
- prototype: `__int64 __fastcall(Windows::AutoSsShim *this, const WCHAR *, const wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004027c`

## callees

- `0x180002564`
- `0x18001f604`
- `0x18001f660`
- `0x18001fd10`
- `0x1800293a0`
- `0x18003d9e8`
- `0x18003e8f8`
- `0x18003e9c8`
- `0x18003ea38`
- `0x18003eaa0`
- `0x18003eb0c`
- `0x18003fdac`
- `0x180069248`
- `0x18006b1e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003fe8c`
- `KERNEL32!GetLastError` at `0x18003fea3`
- `KERNEL32!GetLastError` at `0x18003ff33`
- `KERNEL32!GetLastError` at `0x18003ff63`
- `KERNEL32!GetLastError` at `0x18003ffa3`
- `KERNEL32!GetLastError` at `0x18003ffba`
- `KERNEL32!GetLastError` at `0x18004002e`
- `KERNEL32!GetLastError` at `0x180040045`
- `KERNEL32!GetLastError` at `0x1800400b9`
- `KERNEL32!GetLastError` at `0x1800400d0`
- `KERNEL32!GetLastError` at `0x180040148`
- `KERNEL32!GetLastError` at `0x18004015f`
- `KERNEL32!GetLastError` at `0x18003fe8c`
- `KERNEL32!GetLastError` at `0x18003fea3`
- `KERNEL32!GetLastError` at `0x18003ff33`
- `KERNEL32!GetLastError` at `0x18003ff63`
- `KERNEL32!GetLastError` at `0x18003ffa3`
- `KERNEL32!GetLastError` at `0x18003ffba`
- `KERNEL32!GetLastError` at `0x18004002e`
- `KERNEL32!GetLastError` at `0x180040045`
- `KERNEL32!GetLastError` at `0x1800400b9`
- `KERNEL32!GetLastError` at `0x1800400d0`
- `KERNEL32!GetLastError` at `0x180040148`
- `KERNEL32!GetLastError` at `0x18004015f`
- `KERNEL32!GetProcAddress` at `0x18003ff8e`
- `KERNEL32!GetProcAddress` at `0x180040019`
- `KERNEL32!GetProcAddress` at `0x1800400a4`
- `KERNEL32!GetProcAddress` at `0x18004012f`
- `KERNEL32!GetProcAddress` at `0x1800401fb`
- `KERNEL32!GetProcAddress` at `0x180040215`
- `KERNEL32!GetProcAddress` at `0x18003ff8e`
- `KERNEL32!GetProcAddress` at `0x180040019`
- `KERNEL32!GetProcAddress` at `0x1800400a4`
- `KERNEL32!GetProcAddress` at `0x18004012f`
- `KERNEL32!GetProcAddress` at `0x1800401fb`
- `KERNEL32!GetProcAddress` at `0x180040215`
- `KERNEL32!LoadLibraryExW` at `0x18003ff12`
- `KERNEL32!LoadLibraryExW` at `0x18003ff12`
- `KERNEL32!SetThreadErrorMode` at `0x18003fef6`
- `KERNEL32!SetThreadErrorMode` at `0x18003fef6`
- `KERNEL32!GetThreadErrorMode` at `0x18003fee1`
- `KERNEL32!GetThreadErrorMode` at `0x18003fee1`
- `KERNEL32!CopyFileW` at `0x18003fe7c`
- `KERNEL32!CopyFileW` at `0x18003fe7c`

## string_xrefs

- `0x18003fe0b`: `ssshim.dll`
- `0x18003ffee`: `m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>("SssBindServicingStack", LocalSsShimDll)`
- `0x180040079`: `m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>("SssReleaseServicingStack", LocalSsShimDll)`
- `0x18004009a`: `SssGetServicingStackFilePathLength`
- `0x180040104`: `m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>("SssGetServicingStackFilePathLength", LocalSsShimDll)`
- `0x180040125`: `SssGetServicingStackFilePath`
- `0x18003ffe3`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x18004006e`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x1800400f9`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180040188`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180040193`: `m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>("SssGetServicingStackFilePath", LocalSsShimDll)`

## pseudocode

```c
__int64 __fastcall Windows::AutoSsShim::TryLoadFromDirectPath(
        Windows::AutoSsShim *this,
        const WCHAR *a2,
        const wchar_t *a3)
{
  bool v3; // zf
  __int64 v6; // rcx
  int v7; // eax
  signed int LastError; // ebx
  const WCHAR *v9; // rbx
  DWORD ThreadErrorMode; // eax
  wil::details::in1diag3 *v11; // rcx
  HMODULE Library; // rax
  HMODULE v13; // rbx
  FARPROC ProcAddress; // rax
  signed int v15; // ebx
  __int128 *v16; // rdx
  FARPROC v17; // rax
  FARPROC v18; // rax
  FARPROC v19; // rax
  HMODULE hModule; // [rsp+20h] [rbp-79h] BYREF
  __int128 v22; // [rsp+28h] [rbp-71h] BYREF
  __int64 v23; // [rsp+38h] [rbp-61h]
  const char *v24; // [rsp+40h] [rbp-59h]
  __int128 v25; // [rsp+48h] [rbp-51h] BYREF
  __int64 v26; // [rsp+58h] [rbp-41h]
  __int128 v27; // [rsp+60h] [rbp-39h] BYREF
  __int64 v28; // [rsp+70h] [rbp-29h]
  __int128 v29; // [rsp+78h] [rbp-21h]
  __int64 v30; // [rsp+88h] [rbp-11h]
  _QWORD v31[4]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v32[4]; // [rsp+B0h] [rbp+17h] BYREF
  int v33; // [rsp+D0h] [rbp+37h] BYREF
  DWORD OldMode; // [rsp+D4h] [rbp+3Bh] BYREF

  v3 = *(_QWORD *)this == 0;
  v33 = 0;
  if ( !v3 )
    goto LABEL_56;
  v26 = 0;
  v25 = 0;
  if ( a3 )
  {
    Windows::StringUtil::AsLUnicode(&v22, a3);
    v27 = v22;
    v28 = v23;
    Windows::StringUtil::AsLUnicode(&v22, L"ssshim.dll");
    v29 = v22;
    v30 = v23;
    v7 = RtlCombineNtPathSegments(v6, &v27, &v25);
    if ( v7 < 0
      || (v7 = Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::Auto<_LUNICODE_STRING> *>(&v25), v7 < 0) )
    {
      LastError = ConvertNtStatusToHResult((unsigned int)v7);
LABEL_52:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v25);
      return (unsigned int)LastError;
    }
    v9 = (const WCHAR *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v25);
    if ( !CopyFileW(a2, v9, 0) )
    {
      if ( !GetLastError() )
      {
        LastError = 14077;
        goto LABEL_10;
      }
      LastError = GetLastError();
      if ( LastError )
      {
LABEL_10:
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_52;
      }
LABEL_56:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x180040274LL);
    }
  }
  else
  {
    v9 = a2;
  }
  hModule = 0;
  OldMode = 0;
  ThreadErrorMode = GetThreadErrorMode();
  if ( !SetThreadErrorMode(ThreadErrorMode | 1, &OldMode) )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v11);
  Library = LoadLibraryExW(v9, 0, 0);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(&hModule, Library);
  v13 = hModule;
  if ( !hModule )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        __debugbreak();
      }
    }
    else
    {
      LastError = 14077;
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Windows::AutoThreadMode::~AutoThreadMode((Windows::AutoThreadMode *)&OldMode);
    goto LABEL_51;
  }
  Windows::AutoThreadMode::~AutoThreadMode((Windows::AutoThreadMode *)&OldMode);
  ProcAddress = GetProcAddress(v13, "SssBindServicingStack");
  *((_QWORD *)this + 2) = ProcAddress;
  if ( !ProcAddress )
  {
    if ( GetLastError() )
    {
      v15 = GetLastError();
      if ( !v15 )
        goto LABEL_56;
    }
    else
    {
      v15 = 14077;
    }
    v23 = 115;
    *(_QWORD *)&v22 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    *((_QWORD *)&v22 + 1) = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v24 = "m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>(\"SssBindServicingStack\", LocalSsShimDll)";
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v16 = &v22;
    goto LABEL_50;
  }
  v17 = GetProcAddress(v13, "SssReleaseServicingStack");
  *((_QWORD *)this + 3) = v17;
  if ( !v17 )
  {
    if ( GetLastError() )
    {
      v15 = GetLastError();
      if ( !v15 )
        goto LABEL_56;
    }
    else
    {
      v15 = 14077;
    }
    v31[2] = 116;
    v31[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v31[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v31[3] = "m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>(\"SssReleaseServicingStack\", LocalSsShimDll)";
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v16 = (__int128 *)v31;
    goto LABEL_50;
  }
  v18 = GetProcAddress(v13, "SssGetServicingStackFilePathLength");
  *((_QWORD *)this + 5) = v18;
  if ( !v18 )
  {
    if ( GetLastError() )
    {
      v15 = GetLastError();
      if ( !v15 )
        goto LABEL_56;
    }
    else
    {
      v15 = 14077;
    }
    v32[2] = 117;
    v32[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v32[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v32[3] = "m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>(\"SssGetSer"
             "vicingStackFilePathLength\", LocalSsShimDll)";
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v16 = (__int128 *)v32;
    goto LABEL_50;
  }
  v19 = GetProcAddress(v13, "SssGetServicingStackFilePath");
  *((_QWORD *)this + 6) = v19;
  if ( !v19 )
  {
    if ( GetLastError() )
    {
      v15 = GetLastError();
      if ( !v15 )
        goto LABEL_56;
    }
    else
    {
      v15 = 14077;
    }
    v28 = 118;
    *(_QWORD *)&v27 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    *((_QWORD *)&v27 + 1) = "Windows::AutoSsShim::TryLoadFromDirectPath";
    *(_QWORD *)&v29 = "m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>(\"SssGetServic"
                      "ingStackFilePath\", LocalSsShimDll)";
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v16 = &v27;
LABEL_50:
    LastError = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
                  &v33,
                  v16,
                  (unsigned int)v15);
LABEL_51:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
    goto LABEL_52;
  }
  *((_QWORD *)this + 4) = GetProcAddress(v13, "SssPreloadDownlevelDependencies");
  *((_QWORD *)this + 7) = GetProcAddress(v13, "SssGetServicingStackVersion");
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(this);
  hModule = 0;
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(this, v13);
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v25);
  return 0;
}

```

## disassembly

```asm
0x18003fdac  mov     [rsp-8+arg_18], rbx
0x18003fdb1  push    rbp
0x18003fdb2  push    rsi
0x18003fdb3  push    rdi
0x18003fdb4  lea     rbp, [rsp-47h]
0x18003fdb9  sub     rsp, 0E0h
0x18003fdc0  mov     rax, cs:__security_cookie
0x18003fdc7  xor     rax, rsp
0x18003fdca  mov     [rbp+57h+var_18], rax
0x18003fdce  cmp     qword ptr [rcx], 0
0x18003fdd2  mov     rsi, rdx
0x18003fdd5  mov     rdi, rcx
0x18003fdd8  mov     [rbp+57h+var_20], 0
0x18003fddf  jnz     loc_18004026A
0x18003fde5  xor     eax, eax
0x18003fde7  xorps   xmm0, xmm0
0x18003fdea  mov     [rbp+57h+var_98], rax
0x18003fdee  movups  [rbp+57h+var_A8], xmm0
0x18003fdf2  test    r8, r8
0x18003fdf5  jz      loc_18003FECF
0x18003fdfb  mov     rdx, r8
0x18003fdfe  lea     rcx, [rbp+57h+var_C8]
0x18003fe02  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x18003fe07  movups  xmm1, [rbp+57h+var_C8]
0x18003fe0b  lea     rdx, aSsshimDll; "ssshim.dll"
0x18003fe12  movsd   xmm2, [rbp+57h+var_B8]
0x18003fe17  lea     rcx, [rbp+57h+var_C8]
0x18003fe1b  movups  [rbp+57h+var_90], xmm1
0x18003fe1f  movsd   [rbp+57h+var_80], xmm2
0x18003fe24  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x18003fe29  movups  xmm1, [rbp+57h+var_C8]
0x18003fe2d  lea     r8, [rbp+57h+var_A8]
0x18003fe31  movsd   xmm2, [rbp+57h+var_B8]
0x18003fe36  lea     rdx, [rbp+57h+var_90]
0x18003fe3a  movups  [rbp+57h+var_78], xmm1
0x18003fe3e  movsd   [rbp+57h+var_68], xmm2
0x18003fe43  call    RtlCombineNtPathSegments
0x18003fe48  test    eax, eax
0x18003fe4a  js      short loc_18003FE59
0x18003fe4c  lea     rcx, [rbp+57h+var_A8]
0x18003fe50  call    ??$EnsureNullTerminated@PEAV?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@StringUtil@Windows@@YAJPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::Auto<_LUNICODE_STRING> *>(Windows::Auto<_LUNICODE_STRING> *)
0x18003fe55  test    eax, eax
0x18003fe57  jns     short loc_18003FE67
0x18003fe59  mov     ecx, eax
0x18003fe5b  call    ConvertNtStatusToHResult
0x18003fe60  mov     ebx, eax
0x18003fe62  jmp     loc_1800401C6
0x18003fe67  lea     rcx, [rbp+57h+var_A8]
0x18003fe6b  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x18003fe70  xor     r8d, r8d; bFailIfExists
0x18003fe73  mov     rdx, rax; lpNewFileName
0x18003fe76  mov     rcx, rsi; lpExistingFileName
0x18003fe79  mov     rbx, rax
0x18003fe7c  call    cs:__imp_CopyFileW
0x18003fe83  nop     dword ptr [rax+rax+00h]
0x18003fe88  test    eax, eax
0x18003fe8a  jnz     short loc_18003FED2
0x18003fe8c  call    cs:__imp_GetLastError
0x18003fe93  nop     dword ptr [rax+rax+00h]
0x18003fe98  test    eax, eax
0x18003fe9a  jnz     short loc_18003FEA3
0x18003fe9c  mov     ebx, 36FDh
0x18003fea1  jmp     short loc_18003FEB9
0x18003fea3  call    cs:__imp_GetLastError
0x18003feaa  nop     dword ptr [rax+rax+00h]
0x18003feaf  mov     ebx, eax
0x18003feb1  test    eax, eax
0x18003feb3  jz      loc_18004026A
0x18003feb9  test    ebx, ebx
0x18003febb  jle     loc_1800401C6
0x18003fec1  movzx   ebx, bx
0x18003fec4  or      ebx, 80070000h
0x18003feca  jmp     loc_1800401C6
0x18003fecf  mov     rbx, rsi
0x18003fed2  mov     [rbp+57h+hModule], 0
0x18003feda  mov     [rbp+57h+OldMode], 0
0x18003fee1  call    cs:__imp_GetThreadErrorMode
0x18003fee8  nop     dword ptr [rax+rax+00h]
0x18003feed  or      eax, 1
0x18003fef0  lea     rdx, [rbp+57h+OldMode]; lpOldMode
0x18003fef4  mov     ecx, eax; dwNewMode
0x18003fef6  call    cs:__imp_SetThreadErrorMode
0x18003fefd  nop     dword ptr [rax+rax+00h]
0x18003ff02  test    eax, eax
0x18003ff04  jz      loc_180040259
0x18003ff0a  xor     r8d, r8d; dwFlags
0x18003ff0d  xor     edx, edx; hFile
0x18003ff0f  mov     rcx, rbx; lpLibFileName
0x18003ff12  call    cs:__imp_LoadLibraryExW
0x18003ff19  nop     dword ptr [rax+rax+00h]
0x18003ff1e  mov     rdx, rax
0x18003ff21  lea     rcx, [rbp+57h+hModule]
0x18003ff25  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x18003ff2a  mov     rbx, [rbp+57h+hModule]
0x18003ff2e  test    rbx, rbx
0x18003ff31  jnz     short loc_18003FF7B
0x18003ff33  call    cs:__imp_GetLastError
0x18003ff3a  nop     dword ptr [rax+rax+00h]
0x18003ff3f  test    eax, eax
0x18003ff41  jnz     short loc_18003FF63
0x18003ff43  mov     ebx, 36FDh
0x18003ff48  test    ebx, ebx
0x18003ff4a  jle     short loc_18003FF55
0x18003ff4c  movzx   ebx, bx
0x18003ff4f  or      ebx, 80070000h
0x18003ff55  lea     rcx, [rbp+57h+OldMode]; this
0x18003ff59  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x18003ff5e  jmp     loc_1800401BD
0x18003ff63  call    cs:__imp_GetLastError
0x18003ff6a  nop     dword ptr [rax+rax+00h]
0x18003ff6f  mov     ebx, eax
0x18003ff71  test    eax, eax
0x18003ff73  jz      loc_18004025F
0x18003ff79  jmp     short loc_18003FF48
0x18003ff7b  lea     rcx, [rbp+57h+OldMode]; this
0x18003ff7f  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x18003ff84  lea     rdx, aSssbindservici; "SssBindServicingStack"
0x18003ff8b  mov     rcx, rbx; hModule
0x18003ff8e  call    cs:__imp_GetProcAddress
0x18003ff95  nop     dword ptr [rax+rax+00h]
0x18003ff9a  mov     [rdi+10h], rax
0x18003ff9e  test    rax, rax
0x18003ffa1  jnz     short loc_18004000F
0x18003ffa3  call    cs:__imp_GetLastError
0x18003ffaa  nop     dword ptr [rax+rax+00h]
0x18003ffaf  test    eax, eax
0x18003ffb1  jnz     short loc_18003FFBA
0x18003ffb3  mov     ebx, 36FDh
0x18003ffb8  jmp     short loc_18003FFD0
0x18003ffba  call    cs:__imp_GetLastError
0x18003ffc1  nop     dword ptr [rax+rax+00h]
0x18003ffc6  mov     ebx, eax
0x18003ffc8  test    eax, eax
0x18003ffca  jz      loc_18004026A
0x18003ffd0  mov     [rbp+57h+var_B8], 73h ; 's'
0x18003ffd8  lea     rax, aOnecoreBaseWcp_16; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x18003ffdf  mov     qword ptr [rbp+57h+var_C8], rax
0x18003ffe3  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x18003ffea  mov     qword ptr [rbp+57h+var_C8+8], rax
0x18003ffee  lea     rax, aMPfnsssbindser; "m_pfnSssBindServicingStack = GetProc<de"...
0x18003fff5  mov     [rbp+57h+var_B0], rax
0x18003fff9  test    ebx, ebx
0x18003fffb  jle     short loc_180040006
0x18003fffd  movzx   ebx, bx
0x180040000  or      ebx, 80070000h
0x180040006  lea     rdx, [rbp+57h+var_C8]
0x18004000a  jmp     loc_1800401AF
0x18004000f  lea     rdx, aSssreleaseserv; "SssReleaseServicingStack"
0x180040016  mov     rcx, rbx; hModule
0x180040019  call    cs:__imp_GetProcAddress
0x180040020  nop     dword ptr [rax+rax+00h]
0x180040025  mov     [rdi+18h], rax
0x180040029  test    rax, rax
0x18004002c  jnz     short loc_18004009A
0x18004002e  call    cs:__imp_GetLastError
0x180040035  nop     dword ptr [rax+rax+00h]
0x18004003a  test    eax, eax
0x18004003c  jnz     short loc_180040045
0x18004003e  mov     ebx, 36FDh
0x180040043  jmp     short loc_18004005B
0x180040045  call    cs:__imp_GetLastError
0x18004004c  nop     dword ptr [rax+rax+00h]
0x180040051  mov     ebx, eax
0x180040053  test    eax, eax
0x180040055  jz      loc_18004026A
0x18004005b  mov     [rbp+57h+var_50], 74h ; 't'
0x180040063  lea     rax, aOnecoreBaseWcp_16; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x18004006a  mov     [rbp+57h+var_60], rax
0x18004006e  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180040075  mov     [rbp+57h+var_58], rax
0x180040079  lea     rax, aMPfnsssrelease; "m_pfnSssReleaseServicingStack = GetProc"...
0x180040080  mov     [rbp+57h+var_48], rax
0x180040084  test    ebx, ebx
0x180040086  jle     short loc_180040091
0x180040088  movzx   ebx, bx
0x18004008b  or      ebx, 80070000h
0x180040091  lea     rdx, [rbp+57h+var_60]
0x180040095  jmp     loc_1800401AF
0x18004009a  lea     rdx, aSssgetservicin; "SssGetServicingStackFilePathLength"
0x1800400a1  mov     rcx, rbx; hModule
0x1800400a4  call    cs:__imp_GetProcAddress
0x1800400ab  nop     dword ptr [rax+rax+00h]
0x1800400b0  mov     [rdi+28h], rax
0x1800400b4  test    rax, rax
0x1800400b7  jnz     short loc_180040125
0x1800400b9  call    cs:__imp_GetLastError
0x1800400c0  nop     dword ptr [rax+rax+00h]
0x1800400c5  test    eax, eax
0x1800400c7  jnz     short loc_1800400D0
0x1800400c9  mov     ebx, 36FDh
0x1800400ce  jmp     short loc_1800400E6
0x1800400d0  call    cs:__imp_GetLastError
0x1800400d7  nop     dword ptr [rax+rax+00h]
0x1800400dc  mov     ebx, eax
0x1800400de  test    eax, eax
0x1800400e0  jz      loc_18004026A
0x1800400e6  mov     [rbp+57h+var_30], 75h ; 'u'
0x1800400ee  lea     rax, aOnecoreBaseWcp_16; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x1800400f5  mov     [rbp+57h+var_40], rax
0x1800400f9  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180040100  mov     [rbp+57h+var_38], rax
0x180040104  lea     rax, aMPfnsssgetserv_0; "m_pfnSssGetServicingStackFilePathLength"...
0x18004010b  mov     [rbp+57h+var_28], rax
0x18004010f  test    ebx, ebx
0x180040111  jle     short loc_18004011C
0x180040113  movzx   ebx, bx
0x180040116  or      ebx, 80070000h
0x18004011c  lea     rdx, [rbp+57h+var_40]
0x180040120  jmp     loc_1800401AF
0x180040125  lea     rdx, aSssgetservicin_0; "SssGetServicingStackFilePath"
0x18004012c  mov     rcx, rbx; hModule
0x18004012f  call    cs:__imp_GetProcAddress
0x180040136  nop     dword ptr [rax+rax+00h]
0x18004013b  mov     [rdi+30h], rax
0x18004013f  test    rax, rax
0x180040142  jnz     loc_1800401F1
0x180040148  call    cs:__imp_GetLastError
0x18004014f  nop     dword ptr [rax+rax+00h]
0x180040154  test    eax, eax
0x180040156  jnz     short loc_18004015F
0x180040158  mov     ebx, 36FDh
0x18004015d  jmp     short loc_180040175
0x18004015f  call    cs:__imp_GetLastError
0x180040166  nop     dword ptr [rax+rax+00h]
0x18004016b  mov     ebx, eax
0x18004016d  test    eax, eax
0x18004016f  jz      loc_18004026A
0x180040175  mov     [rbp+57h+var_80], 76h ; 'v'
0x18004017d  lea     rax, aOnecoreBaseWcp_16; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180040184  mov     qword ptr [rbp+57h+var_90], rax
0x180040188  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x18004018f  mov     qword ptr [rbp+57h+var_90+8], rax
0x180040193  lea     rax, aMPfnsssgetserv; "m_pfnSssGetServicingStackFilePath = Get"...
0x18004019a  mov     qword ptr [rbp+57h+var_78], rax
0x18004019e  test    ebx, ebx
0x1800401a0  jle     short loc_1800401AB
0x1800401a2  movzx   ebx, bx
0x1800401a5  or      ebx, 80070000h
0x1800401ab  lea     rdx, [rbp+57h+var_90]
0x1800401af  mov     r8d, ebx
0x1800401b2  lea     rcx, [rbp+57h+var_20]
0x1800401b6  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800401bb  mov     ebx, eax
0x1800401bd  lea     rcx, [rbp+57h+hModule]
0x1800401c1  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800401c6  lea     rcx, [rbp+57h+var_A8]
0x1800401ca  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800401cf  mov     eax, ebx
0x1800401d1  mov     rcx, [rbp+57h+var_18]
0x1800401d5  xor     rcx, rsp; StackCookie
0x1800401d8  call    __security_check_cookie
0x1800401dd  mov     rbx, [rsp+0F0h+arg_18]
0x1800401e5  add     rsp, 0E0h
0x1800401ec  pop     rdi
0x1800401ed  pop     rsi
0x1800401ee  pop     rbp
0x1800401ef  retn
0x1800401f1  lea     rdx, aSsspreloaddown; "SssPreloadDownlevelDependencies"
0x1800401f8  mov     rcx, rbx; hModule
0x1800401fb  call    cs:__imp_GetProcAddress
0x180040202  nop     dword ptr [rax+rax+00h]
0x180040207  lea     rdx, aSssgetservicin_1; "SssGetServicingStackVersion"
0x18004020e  mov     rcx, rbx; hModule
0x180040211  mov     [rdi+20h], rax
0x180040215  call    cs:__imp_GetProcAddress
0x18004021c  nop     dword ptr [rax+rax+00h]
0x180040221  mov     rcx, rdi
0x180040224  mov     [rdi+38h], rax
0x180040228  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18004022d  mov     rdx, rbx
0x180040230  mov     [rbp+57h+hModule], 0
0x180040238  mov     rcx, rdi
0x18004023b  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x180040240  lea     rcx, [rbp+57h+hModule]
0x180040244  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180040249  lea     rcx, [rbp+57h+var_A8]
0x18004024d  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180040252  xor     eax, eax
0x180040254  jmp     loc_1800401D1
0x180040259  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18004025f  mov     ecx, 0C00000E5h; int
0x180040264  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x180040269  int     3; Trap to Debugger
0x18004026a  mov     ecx, 0C00000E5h; int
0x18004026f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
