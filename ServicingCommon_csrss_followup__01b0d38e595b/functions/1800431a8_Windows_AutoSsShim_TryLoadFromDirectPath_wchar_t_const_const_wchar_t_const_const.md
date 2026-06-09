# Windows::AutoSsShim::TryLoadFromDirectPath(wchar_t const * const,wchar_t const * const)

- ea: `0x1800431a8`
- end: `0x180043679`
- name: `?TryLoadFromDirectPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z`
- size: `1233`
- prototype: `int(Windows::AutoSsShim *__hidden this, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180043680`

## callees

- `0x180004a8c`
- `0x180020dc0`
- `0x1800211f0`
- `0x180023664`
- `0x18002d2b0`
- `0x18004145c`
- `0x18004194c`
- `0x1800419bc`
- `0x180041a28`
- `0x1800431a8`
- `0x180043840`
- `0x18006967c`
- `0x18006b3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180043288`
- `KERNEL32!GetLastError` at `0x18004329f`
- `KERNEL32!GetLastError` at `0x18004332f`
- `KERNEL32!GetLastError` at `0x18004335f`
- `KERNEL32!GetLastError` at `0x1800433ab`
- `KERNEL32!GetLastError` at `0x1800433c2`
- `KERNEL32!GetLastError` at `0x180043436`
- `KERNEL32!GetLastError` at `0x18004344d`
- `KERNEL32!GetLastError` at `0x1800434c1`
- `KERNEL32!GetLastError` at `0x1800434d8`
- `KERNEL32!GetLastError` at `0x180043550`
- `KERNEL32!GetLastError` at `0x180043567`
- `KERNEL32!GetLastError` at `0x180043288`
- `KERNEL32!GetLastError` at `0x18004329f`
- `KERNEL32!GetLastError` at `0x18004332f`
- `KERNEL32!GetLastError` at `0x18004335f`
- `KERNEL32!GetLastError` at `0x1800433ab`
- `KERNEL32!GetLastError` at `0x1800433c2`
- `KERNEL32!GetLastError` at `0x180043436`
- `KERNEL32!GetLastError` at `0x18004344d`
- `KERNEL32!GetLastError` at `0x1800434c1`
- `KERNEL32!GetLastError` at `0x1800434d8`
- `KERNEL32!GetLastError` at `0x180043550`
- `KERNEL32!GetLastError` at `0x180043567`
- `KERNEL32!LoadLibraryExW` at `0x18004330e`
- `KERNEL32!LoadLibraryExW` at `0x18004330e`
- `KERNEL32!GetProcAddress` at `0x180043396`
- `KERNEL32!GetProcAddress` at `0x180043421`
- `KERNEL32!GetProcAddress` at `0x1800434ac`
- `KERNEL32!GetProcAddress` at `0x180043537`
- `KERNEL32!GetProcAddress` at `0x180043603`
- `KERNEL32!GetProcAddress` at `0x18004361d`
- `KERNEL32!GetProcAddress` at `0x180043396`
- `KERNEL32!GetProcAddress` at `0x180043421`
- `KERNEL32!GetProcAddress` at `0x1800434ac`
- `KERNEL32!GetProcAddress` at `0x180043537`
- `KERNEL32!GetProcAddress` at `0x180043603`
- `KERNEL32!GetProcAddress` at `0x18004361d`
- `KERNEL32!SetThreadErrorMode` at `0x1800432f2`
- `KERNEL32!SetThreadErrorMode` at `0x1800432f2`
- `KERNEL32!GetThreadErrorMode` at `0x1800432dd`
- `KERNEL32!GetThreadErrorMode` at `0x1800432dd`
- `KERNEL32!CopyFileW` at `0x180043278`
- `KERNEL32!CopyFileW` at `0x180043278`
- `ntdll!RtlRaiseStatus` at `0x180043376`
- `ntdll!RtlRaiseStatus` at `0x180043666`
- `ntdll!RtlRaiseStatus` at `0x180043376`
- `ntdll!RtlRaiseStatus` at `0x180043666`

## string_xrefs

- `0x180043207`: `ssshim.dll`
- `0x1800433f6`: `m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>("SssBindServicingStack", LocalSsShimDll)`
- `0x180043481`: `m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>("SssReleaseServicingStack", LocalSsShimDll)`
- `0x1800434a2`: `SssGetServicingStackFilePathLength`
- `0x18004350c`: `m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>("SssGetServicingStackFilePathLength", LocalSsShimDll)`
- `0x18004352d`: `SssGetServicingStackFilePath`
- `0x1800433eb`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180043476`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180043501`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180043590`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x18004359b`: `m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>("SssGetServicingStackFilePath", LocalSsShimDll)`

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
    goto LABEL_54;
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
LABEL_54:
      RtlRaiseStatus(-1073741595);
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
        RtlRaiseStatus(-1073741595);
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
        goto LABEL_54;
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
LABEL_50:
    LastError = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
                  &v33,
                  v16,
                  (unsigned int)v15);
LABEL_51:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
    goto LABEL_52;
  }
  v17 = GetProcAddress(v13, "SssReleaseServicingStack");
  *((_QWORD *)this + 3) = v17;
  if ( !v17 )
  {
    if ( GetLastError() )
    {
      v15 = GetLastError();
      if ( !v15 )
        goto LABEL_54;
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
        goto LABEL_54;
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
        goto LABEL_54;
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
    goto LABEL_50;
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
0x1800431a8  mov     [rsp-8+arg_18], rbx
0x1800431ad  push    rbp
0x1800431ae  push    rsi
0x1800431af  push    rdi
0x1800431b0  lea     rbp, [rsp-47h]
0x1800431b5  sub     rsp, 0E0h
0x1800431bc  mov     rax, cs:__security_cookie
0x1800431c3  xor     rax, rsp
0x1800431c6  mov     [rbp+57h+var_18], rax
0x1800431ca  cmp     qword ptr [rcx], 0
0x1800431ce  mov     rsi, rdx
0x1800431d1  mov     rdi, rcx
0x1800431d4  mov     [rbp+57h+var_20], 0
0x1800431db  jnz     loc_180043661
0x1800431e1  xor     eax, eax
0x1800431e3  xorps   xmm0, xmm0
0x1800431e6  mov     [rbp+57h+var_98], rax
0x1800431ea  movups  [rbp+57h+var_A8], xmm0
0x1800431ee  test    r8, r8
0x1800431f1  jz      loc_1800432CB
0x1800431f7  mov     rdx, r8
0x1800431fa  lea     rcx, [rbp+57h+var_C8]
0x1800431fe  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x180043203  movups  xmm1, [rbp+57h+var_C8]
0x180043207  lea     rdx, aSsshimDll; "ssshim.dll"
0x18004320e  movsd   xmm2, [rbp+57h+var_B8]
0x180043213  lea     rcx, [rbp+57h+var_C8]
0x180043217  movups  [rbp+57h+var_90], xmm1
0x18004321b  movsd   [rbp+57h+var_80], xmm2
0x180043220  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x180043225  movups  xmm1, [rbp+57h+var_C8]
0x180043229  lea     r8, [rbp+57h+var_A8]
0x18004322d  movsd   xmm2, [rbp+57h+var_B8]
0x180043232  lea     rdx, [rbp+57h+var_90]
0x180043236  movups  [rbp+57h+var_78], xmm1
0x18004323a  movsd   [rbp+57h+var_68], xmm2
0x18004323f  call    RtlCombineNtPathSegments
0x180043244  test    eax, eax
0x180043246  js      short loc_180043255
0x180043248  lea     rcx, [rbp+57h+var_A8]
0x18004324c  call    ??$EnsureNullTerminated@PEAV?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@StringUtil@Windows@@YAJPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::Auto<_LUNICODE_STRING> *>(Windows::Auto<_LUNICODE_STRING> *)
0x180043251  test    eax, eax
0x180043253  jns     short loc_180043263
0x180043255  mov     ecx, eax
0x180043257  call    ConvertNtStatusToHResult
0x18004325c  mov     ebx, eax
0x18004325e  jmp     loc_1800435CE
0x180043263  lea     rcx, [rbp+57h+var_A8]
0x180043267  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x18004326c  xor     r8d, r8d; bFailIfExists
0x18004326f  mov     rdx, rax; lpNewFileName
0x180043272  mov     rcx, rsi; lpExistingFileName
0x180043275  mov     rbx, rax
0x180043278  call    cs:__imp_CopyFileW
0x18004327f  nop     dword ptr [rax+rax+00h]
0x180043284  test    eax, eax
0x180043286  jnz     short loc_1800432CE
0x180043288  call    cs:__imp_GetLastError
0x18004328f  nop     dword ptr [rax+rax+00h]
0x180043294  test    eax, eax
0x180043296  jnz     short loc_18004329F
0x180043298  mov     ebx, 36FDh
0x18004329d  jmp     short loc_1800432B5
0x18004329f  call    cs:__imp_GetLastError
0x1800432a6  nop     dword ptr [rax+rax+00h]
0x1800432ab  mov     ebx, eax
0x1800432ad  test    eax, eax
0x1800432af  jz      loc_180043661
0x1800432b5  test    ebx, ebx
0x1800432b7  jle     loc_1800435CE
0x1800432bd  movzx   ebx, bx
0x1800432c0  or      ebx, 80070000h
0x1800432c6  jmp     loc_1800435CE
0x1800432cb  mov     rbx, rsi
0x1800432ce  mov     [rbp+57h+hModule], 0
0x1800432d6  mov     [rbp+57h+OldMode], 0
0x1800432dd  call    cs:__imp_GetThreadErrorMode
0x1800432e4  nop     dword ptr [rax+rax+00h]
0x1800432e9  or      eax, 1
0x1800432ec  lea     rdx, [rbp+57h+OldMode]; lpOldMode
0x1800432f0  mov     ecx, eax; dwNewMode
0x1800432f2  call    cs:__imp_SetThreadErrorMode
0x1800432f9  nop     dword ptr [rax+rax+00h]
0x1800432fe  test    eax, eax
0x180043300  jz      loc_180043673
0x180043306  xor     r8d, r8d; dwFlags
0x180043309  xor     edx, edx; hFile
0x18004330b  mov     rcx, rbx; lpLibFileName
0x18004330e  call    cs:__imp_LoadLibraryExW
0x180043315  nop     dword ptr [rax+rax+00h]
0x18004331a  mov     rdx, rax
0x18004331d  lea     rcx, [rbp+57h+hModule]
0x180043321  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x180043326  mov     rbx, [rbp+57h+hModule]
0x18004332a  test    rbx, rbx
0x18004332d  jnz     short loc_180043383
0x18004332f  call    cs:__imp_GetLastError
0x180043336  nop     dword ptr [rax+rax+00h]
0x18004333b  test    eax, eax
0x18004333d  jnz     short loc_18004335F
0x18004333f  mov     ebx, 36FDh
0x180043344  test    ebx, ebx
0x180043346  jle     short loc_180043351
0x180043348  movzx   ebx, bx
0x18004334b  or      ebx, 80070000h
0x180043351  lea     rcx, [rbp+57h+OldMode]; this
0x180043355  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x18004335a  jmp     loc_1800435C5
0x18004335f  call    cs:__imp_GetLastError
0x180043366  nop     dword ptr [rax+rax+00h]
0x18004336b  mov     ebx, eax
0x18004336d  test    eax, eax
0x18004336f  jnz     short loc_180043344
0x180043371  mov     ecx, 0C00000E5h; Status
0x180043376  call    cs:__imp_RtlRaiseStatus
0x18004337d  nop     dword ptr [rax+rax+00h]
0x180043382  int     3; Trap to Debugger
0x180043383  lea     rcx, [rbp+57h+OldMode]; this
0x180043387  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x18004338c  lea     rdx, aSssbindservici; "SssBindServicingStack"
0x180043393  mov     rcx, rbx; hModule
0x180043396  call    cs:__imp_GetProcAddress
0x18004339d  nop     dword ptr [rax+rax+00h]
0x1800433a2  mov     [rdi+10h], rax
0x1800433a6  test    rax, rax
0x1800433a9  jnz     short loc_180043417
0x1800433ab  call    cs:__imp_GetLastError
0x1800433b2  nop     dword ptr [rax+rax+00h]
0x1800433b7  test    eax, eax
0x1800433b9  jnz     short loc_1800433C2
0x1800433bb  mov     ebx, 36FDh
0x1800433c0  jmp     short loc_1800433D8
0x1800433c2  call    cs:__imp_GetLastError
0x1800433c9  nop     dword ptr [rax+rax+00h]
0x1800433ce  mov     ebx, eax
0x1800433d0  test    eax, eax
0x1800433d2  jz      loc_180043661
0x1800433d8  mov     [rbp+57h+var_B8], 73h ; 's'
0x1800433e0  lea     rax, aOnecoreBaseWcp_16; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x1800433e7  mov     qword ptr [rbp+57h+var_C8], rax
0x1800433eb  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x1800433f2  mov     qword ptr [rbp+57h+var_C8+8], rax
0x1800433f6  lea     rax, aMPfnsssbindser; "m_pfnSssBindServicingStack = GetProc<de"...
0x1800433fd  mov     [rbp+57h+var_B0], rax
0x180043401  test    ebx, ebx
0x180043403  jle     short loc_18004340E
0x180043405  movzx   ebx, bx
0x180043408  or      ebx, 80070000h
0x18004340e  lea     rdx, [rbp+57h+var_C8]
0x180043412  jmp     loc_1800435B7
0x180043417  lea     rdx, aSssreleaseserv; "SssReleaseServicingStack"
0x18004341e  mov     rcx, rbx; hModule
0x180043421  call    cs:__imp_GetProcAddress
0x180043428  nop     dword ptr [rax+rax+00h]
0x18004342d  mov     [rdi+18h], rax
0x180043431  test    rax, rax
0x180043434  jnz     short loc_1800434A2
0x180043436  call    cs:__imp_GetLastError
0x18004343d  nop     dword ptr [rax+rax+00h]
0x180043442  test    eax, eax
0x180043444  jnz     short loc_18004344D
0x180043446  mov     ebx, 36FDh
0x18004344b  jmp     short loc_180043463
0x18004344d  call    cs:__imp_GetLastError
0x180043454  nop     dword ptr [rax+rax+00h]
0x180043459  mov     ebx, eax
0x18004345b  test    eax, eax
0x18004345d  jz      loc_180043661
0x180043463  mov     [rbp+57h+var_50], 74h ; 't'
0x18004346b  lea     rax, aOnecoreBaseWcp_16; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180043472  mov     [rbp+57h+var_60], rax
0x180043476  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x18004347d  mov     [rbp+57h+var_58], rax
0x180043481  lea     rax, aMPfnsssrelease; "m_pfnSssReleaseServicingStack = GetProc"...
0x180043488  mov     [rbp+57h+var_48], rax
0x18004348c  test    ebx, ebx
0x18004348e  jle     short loc_180043499
0x180043490  movzx   ebx, bx
0x180043493  or      ebx, 80070000h
0x180043499  lea     rdx, [rbp+57h+var_60]
0x18004349d  jmp     loc_1800435B7
0x1800434a2  lea     rdx, aSssgetservicin; "SssGetServicingStackFilePathLength"
0x1800434a9  mov     rcx, rbx; hModule
0x1800434ac  call    cs:__imp_GetProcAddress
0x1800434b3  nop     dword ptr [rax+rax+00h]
0x1800434b8  mov     [rdi+28h], rax
0x1800434bc  test    rax, rax
0x1800434bf  jnz     short loc_18004352D
0x1800434c1  call    cs:__imp_GetLastError
0x1800434c8  nop     dword ptr [rax+rax+00h]
0x1800434cd  test    eax, eax
0x1800434cf  jnz     short loc_1800434D8
0x1800434d1  mov     ebx, 36FDh
0x1800434d6  jmp     short loc_1800434EE
0x1800434d8  call    cs:__imp_GetLastError
0x1800434df  nop     dword ptr [rax+rax+00h]
0x1800434e4  mov     ebx, eax
0x1800434e6  test    eax, eax
0x1800434e8  jz      loc_180043661
0x1800434ee  mov     [rbp+57h+var_30], 75h ; 'u'
0x1800434f6  lea     rax, aOnecoreBaseWcp_16; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x1800434fd  mov     [rbp+57h+var_40], rax
0x180043501  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180043508  mov     [rbp+57h+var_38], rax
0x18004350c  lea     rax, aMPfnsssgetserv_0; "m_pfnSssGetServicingStackFilePathLength"...
0x180043513  mov     [rbp+57h+var_28], rax
0x180043517  test    ebx, ebx
0x180043519  jle     short loc_180043524
0x18004351b  movzx   ebx, bx
0x18004351e  or      ebx, 80070000h
0x180043524  lea     rdx, [rbp+57h+var_40]
0x180043528  jmp     loc_1800435B7
0x18004352d  lea     rdx, aSssgetservicin_0; "SssGetServicingStackFilePath"
0x180043534  mov     rcx, rbx; hModule
0x180043537  call    cs:__imp_GetProcAddress
0x18004353e  nop     dword ptr [rax+rax+00h]
0x180043543  mov     [rdi+30h], rax
0x180043547  test    rax, rax
0x18004354a  jnz     loc_1800435F9
0x180043550  call    cs:__imp_GetLastError
0x180043557  nop     dword ptr [rax+rax+00h]
0x18004355c  test    eax, eax
0x18004355e  jnz     short loc_180043567
0x180043560  mov     ebx, 36FDh
0x180043565  jmp     short loc_18004357D
0x180043567  call    cs:__imp_GetLastError
0x18004356e  nop     dword ptr [rax+rax+00h]
0x180043573  mov     ebx, eax
0x180043575  test    eax, eax
0x180043577  jz      loc_180043661
0x18004357d  mov     [rbp+57h+var_80], 76h ; 'v'
0x180043585  lea     rax, aOnecoreBaseWcp_16; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x18004358c  mov     qword ptr [rbp+57h+var_90], rax
0x180043590  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180043597  mov     qword ptr [rbp+57h+var_90+8], rax
0x18004359b  lea     rax, aMPfnsssgetserv; "m_pfnSssGetServicingStackFilePath = Get"...
0x1800435a2  mov     qword ptr [rbp+57h+var_78], rax
0x1800435a6  test    ebx, ebx
0x1800435a8  jle     short loc_1800435B3
0x1800435aa  movzx   ebx, bx
0x1800435ad  or      ebx, 80070000h
0x1800435b3  lea     rdx, [rbp+57h+var_90]
0x1800435b7  mov     r8d, ebx
0x1800435ba  lea     rcx, [rbp+57h+var_20]
0x1800435be  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800435c3  mov     ebx, eax
0x1800435c5  lea     rcx, [rbp+57h+hModule]
0x1800435c9  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800435ce  lea     rcx, [rbp+57h+var_A8]
0x1800435d2  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800435d7  mov     eax, ebx
0x1800435d9  mov     rcx, [rbp+57h+var_18]
0x1800435dd  xor     rcx, rsp; StackCookie
0x1800435e0  call    __security_check_cookie
0x1800435e5  mov     rbx, [rsp+0F0h+arg_18]
0x1800435ed  add     rsp, 0E0h
0x1800435f4  pop     rdi
0x1800435f5  pop     rsi
0x1800435f6  pop     rbp
0x1800435f7  retn
0x1800435f9  lea     rdx, aSsspreloaddown; "SssPreloadDownlevelDependencies"
0x180043600  mov     rcx, rbx; hModule
0x180043603  call    cs:__imp_GetProcAddress
0x18004360a  nop     dword ptr [rax+rax+00h]
0x18004360f  lea     rdx, aSssgetservicin_1; "SssGetServicingStackVersion"
0x180043616  mov     rcx, rbx; hModule
0x180043619  mov     [rdi+20h], rax
0x18004361d  call    cs:__imp_GetProcAddress
0x180043624  nop     dword ptr [rax+rax+00h]
0x180043629  mov     rcx, rdi
0x18004362c  mov     [rdi+38h], rax
0x180043630  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180043635  mov     rdx, rbx
0x180043638  mov     [rbp+57h+hModule], 0
0x180043640  mov     rcx, rdi
0x180043643  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x180043648  lea     rcx, [rbp+57h+hModule]
0x18004364c  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180043651  lea     rcx, [rbp+57h+var_A8]
0x180043655  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18004365a  xor     eax, eax
0x18004365c  jmp     loc_1800435D9
0x180043661  mov     ecx, 0C00000E5h; Status
0x180043666  call    cs:__imp_RtlRaiseStatus
0x18004366d  nop     dword ptr [rax+rax+00h]
0x180043672  int     3; Trap to Debugger
0x180043673  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
