# Windows::AutoSsShim::TryLoadFromDirectPath(wchar_t const * const,wchar_t const * const)

- ea: `0x140025fb0`
- end: `0x1400263ef`
- name: `?TryLoadFromDirectPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z`
- size: `1087`
- prototype: `int(Windows::AutoSsShim *__hidden this, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400263f8`

## callees

- `0x140002360`
- `0x1400062a4`
- `0x14000731c`
- `0x1400074c0`
- `0x140012a00`
- `0x140024ac0`
- `0x140024b14`
- `0x140024bfc`
- `0x140025934`
- `0x140025fb0`
- `0x140026784`
- `0x140026e18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002614f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400261c8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140026241`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400262b7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002634f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140026363`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002614f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400261c8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140026241`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400262b7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002634f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140026363`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1400260ee`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1400260ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002608b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400260b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002612a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002615e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002629b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400262c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002608b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400260b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002612a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002615e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002629b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400262c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026333`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x140026081`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x140026081`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x1400260d8`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x1400260d8`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x1400260c9`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x1400260c9`

## string_xrefs

- `0x140026039`: `ssshim.dll`
- `0x14002618b`: `m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>("SssBindServicingStack", LocalSsShimDll)`
- `0x140026204`: `m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>("SssReleaseServicingStack", LocalSsShimDll)`
- `0x140026237`: `SssGetServicingStackFilePathLength`
- `0x14002627d`: `m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>("SssGetServicingStackFilePathLength", LocalSsShimDll)`
- `0x1400262ad`: `SssGetServicingStackFilePath`
- `0x140026180`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x1400261f9`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x140026272`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x1400262e8`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x1400262f3`: `m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>("SssGetServicingStackFilePath", LocalSsShimDll)`

## pseudocode

```c
__int64 __fastcall Windows::AutoSsShim::TryLoadFromDirectPath(
        Windows::AutoSsShim *this,
        const WCHAR *a2,
        const wchar_t *const a3)
{
  __int64 v5; // rax
  NTSTATUS v6; // eax
  signed int LastError; // ebx
  const WCHAR *v8; // rbx
  int v9; // ecx
  DWORD ThreadErrorMode; // eax
  wil::details::in1diag3 *v11; // rcx
  HMODULE v12; // rbx
  int v13; // ecx
  FARPROC ProcAddress; // rax
  signed int v15; // ebx
  const char **v16; // rdx
  int v17; // ecx
  FARPROC v18; // rax
  int v19; // ecx
  FARPROC v20; // rax
  int v21; // ecx
  FARPROC v22; // rax
  int v24; // ecx
  int v25; // ecx
  HMODULE Library; // [rsp+20h] [rbp-79h] BYREF
  __int128 v27; // [rsp+28h] [rbp-71h] BYREF
  __int64 v28; // [rsp+38h] [rbp-61h]
  const char *v29; // [rsp+40h] [rbp-59h] BYREF
  const char *v30; // [rsp+48h] [rbp-51h]
  __int64 v31; // [rsp+50h] [rbp-49h]
  __int64 v32; // [rsp+58h] [rbp-41h]
  __int64 v33; // [rsp+60h] [rbp-39h]
  const wchar_t *v34; // [rsp+68h] [rbp-31h]
  _QWORD v35[4]; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v36[4]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v37[4]; // [rsp+B0h] [rbp+17h] BYREF
  int v38; // [rsp+D0h] [rbp+37h] BYREF
  DWORD OldMode; // [rsp+D4h] [rbp+3Bh] BYREF

  v38 = 0;
  if ( *(_QWORD *)this )
    INTERNAL_ERROR_ACTION((int)this);
  v28 = 0;
  v27 = 0;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v31 = (__int64)a3;
    v29 = (const char *)(2 * v5);
    v32 = 20;
    v33 = 22;
    v30 = (const char *)(2 * v5 + 2);
    v34 = L"ssshim.dll";
    v6 = RtlCombineNtPathSegments(v30, &v29, &v27);
    if ( v6 < 0
      || (v6 = Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::Auto<_LUNICODE_STRING> *>(&v27), v6 < 0) )
    {
      LastError = ConvertNtStatusToHResult(v6);
LABEL_57:
      Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v27);
      return (unsigned int)LastError;
    }
    v8 = (const WCHAR *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v27);
    if ( !CopyFileW(a2, v8, 0) )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        if ( !LastError )
          INTERNAL_ERROR_ACTION(v9);
      }
      else
      {
        LastError = 14077;
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_57;
    }
  }
  else
  {
    v8 = a2;
  }
  OldMode = 0;
  ThreadErrorMode = GetThreadErrorMode();
  if ( !SetThreadErrorMode(ThreadErrorMode | 1, &OldMode) )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v11);
  Library = LoadLibraryExW(v8, 0, 0);
  v12 = Library;
  if ( !Library )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        INTERNAL_ERROR_ACTION(v13);
    }
    else
    {
      LastError = 14077;
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Windows::AutoThreadMode::~AutoThreadMode((Windows::AutoThreadMode *)&OldMode);
    goto LABEL_56;
  }
  Windows::AutoThreadMode::~AutoThreadMode((Windows::AutoThreadMode *)&OldMode);
  ProcAddress = GetProcAddress(Library, "SssBindServicingStack");
  *((_QWORD *)this + 2) = ProcAddress;
  if ( !ProcAddress )
  {
    if ( GetLastError() )
    {
      v15 = GetLastError();
      if ( !v15 )
        INTERNAL_ERROR_ACTION(v17);
    }
    else
    {
      v15 = 14077;
    }
    v35[2] = 115;
    v35[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v35[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v35[3] = "m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>(\"SssBindServicingStack\", LocalSsShimDll)";
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v16 = (const char **)v35;
LABEL_55:
    LastError = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
                  &v38,
                  v16,
                  (unsigned int)v15);
LABEL_56:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&Library);
    goto LABEL_57;
  }
  v18 = GetProcAddress(v12, "SssReleaseServicingStack");
  *((_QWORD *)this + 3) = v18;
  if ( !v18 )
  {
    if ( GetLastError() )
    {
      v15 = GetLastError();
      if ( !v15 )
        INTERNAL_ERROR_ACTION(v19);
    }
    else
    {
      v15 = 14077;
    }
    v36[2] = 116;
    v36[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v36[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v36[3] = "m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>(\"SssReleaseServicingStack\", LocalSsShimDll)";
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v16 = (const char **)v36;
    goto LABEL_55;
  }
  v20 = GetProcAddress(v12, "SssGetServicingStackFilePathLength");
  *((_QWORD *)this + 5) = v20;
  if ( !v20 )
  {
    if ( GetLastError() )
    {
      v15 = GetLastError();
      if ( !v15 )
        INTERNAL_ERROR_ACTION(v21);
    }
    else
    {
      v15 = 14077;
    }
    v37[2] = 117;
    v37[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v37[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v37[3] = "m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>(\"SssGetSer"
             "vicingStackFilePathLength\", LocalSsShimDll)";
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v16 = (const char **)v37;
    goto LABEL_55;
  }
  v22 = GetProcAddress(v12, "SssGetServicingStackFilePath");
  *((_QWORD *)this + 6) = v22;
  if ( !v22 )
  {
    if ( GetLastError() )
    {
      v15 = GetLastError();
      if ( !v15 )
        INTERNAL_ERROR_ACTION(v24);
    }
    else
    {
      v15 = 14077;
    }
    v31 = 118;
    v29 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v30 = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v32 = (__int64)"m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>(\"SssGetServicing"
                   "StackFilePath\", LocalSsShimDll)";
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v16 = &v29;
    goto LABEL_55;
  }
  *((_QWORD *)this + 4) = GetProcAddress(v12, "SssPreloadDownlevelDependencies");
  *((_QWORD *)this + 7) = GetProcAddress(v12, "SssGetServicingStackVersion");
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(this);
  Library = 0;
  if ( *(_QWORD *)this )
    INTERNAL_ERROR_ACTION(v25);
  *(_QWORD *)this = v12;
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&Library);
  Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v27);
  return 0;
}

```

## disassembly

```asm
0x140025fb0  mov     [rsp-8+arg_10], rbx
0x140025fb5  mov     [rsp-8+arg_18], rsi
0x140025fba  push    rbp
0x140025fbb  push    rdi
0x140025fbc  push    r14
0x140025fbe  lea     rbp, [rsp-47h]
0x140025fc3  sub     rsp, 0E0h
0x140025fca  mov     rax, cs:__security_cookie
0x140025fd1  xor     rax, rsp
0x140025fd4  mov     [rbp+57h+var_18], rax
0x140025fd8  xor     r14d, r14d
0x140025fdb  mov     rsi, rdx
0x140025fde  mov     rdi, rcx
0x140025fe1  mov     [rbp+57h+var_20], r14d
0x140025fe5  cmp     [rcx], r14
0x140025fe8  jnz     loc_1400263E3
0x140025fee  xor     eax, eax
0x140025ff0  xorps   xmm0, xmm0
0x140025ff3  mov     [rbp+57h+var_B8], rax
0x140025ff7  movups  [rbp+57h+var_C8], xmm0
0x140025ffb  test    r8, r8
0x140025ffe  jz      loc_1400260C2
0x140026004  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026008  inc     rax
0x14002600b  cmp     [r8+rax*2], r14w
0x140026010  jnz     short loc_140026008
0x140026012  add     rax, rax
0x140026015  mov     [rbp+57h+var_A0], r8
0x140026019  mov     [rbp+57h+var_B0], rax
0x14002601d  lea     r8, [rbp+57h+var_C8]
0x140026021  lea     rdx, [rbp+57h+var_B0]
0x140026025  mov     [rbp+57h+var_98], 14h
0x14002602d  mov     [rbp+57h+var_90], 16h
0x140026035  lea     rcx, [rax+2]
0x140026039  lea     rax, aSsshimDll; "ssshim.dll"
0x140026040  mov     [rbp+57h+var_A8], rcx
0x140026044  mov     [rbp+57h+var_88], rax
0x140026048  call    RtlCombineNtPathSegments
0x14002604d  test    eax, eax
0x14002604f  js      short loc_14002605E
0x140026051  lea     rcx, [rbp+57h+var_C8]
0x140026055  call    ??$EnsureNullTerminated@PEAV?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@StringUtil@Windows@@YAJPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::Auto<_LUNICODE_STRING> *>(Windows::Auto<_LUNICODE_STRING> *)
0x14002605a  test    eax, eax
0x14002605c  jns     short loc_14002606C
0x14002605e  mov     ecx, eax; Status
0x140026060  call    ConvertNtStatusToHResult
0x140026065  mov     ebx, eax
0x140026067  jmp     loc_140026326
0x14002606c  lea     rcx, [rbp+57h+var_C8]
0x140026070  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x140026075  xor     r8d, r8d; bFailIfExists
0x140026078  mov     rdx, rax; lpNewFileName
0x14002607b  mov     rcx, rsi; lpExistingFileName
0x14002607e  mov     rbx, rax
0x140026081  call    cs:__imp_CopyFileW
0x140026087  test    eax, eax
0x140026089  jnz     short loc_1400260C5
0x14002608b  call    cs:__imp_GetLastError
0x140026091  test    eax, eax
0x140026093  jnz     short loc_1400260B0
0x140026095  mov     ebx, 36FDh
0x14002609a  test    ebx, ebx
0x14002609c  jle     loc_140026326
0x1400260a2  movzx   ebx, bx
0x1400260a5  or      ebx, 80070000h
0x1400260ab  jmp     loc_140026326
0x1400260b0  call    cs:__imp_GetLastError
0x1400260b6  mov     ebx, eax
0x1400260b8  test    eax, eax
0x1400260ba  jz      loc_1400263BF
0x1400260c0  jmp     short loc_14002609A
0x1400260c2  mov     rbx, rsi
0x1400260c5  mov     [rbp+57h+OldMode], r14d
0x1400260c9  call    cs:__imp_GetThreadErrorMode
0x1400260cf  or      eax, 1
0x1400260d2  lea     rdx, [rbp+57h+OldMode]; lpOldMode
0x1400260d6  mov     ecx, eax; dwNewMode
0x1400260d8  call    cs:__imp_SetThreadErrorMode
0x1400260de  test    eax, eax
0x1400260e0  jz      loc_1400263E9
0x1400260e6  xor     r8d, r8d; dwFlags
0x1400260e9  xor     edx, edx; hFile
0x1400260eb  mov     rcx, rbx; lpLibFileName
0x1400260ee  call    cs:__imp_LoadLibraryExW
0x1400260f4  mov     [rbp+57h+var_D0], rax
0x1400260f8  mov     rbx, rax
0x1400260fb  test    rax, rax
0x1400260fe  jnz     short loc_14002613C
0x140026100  call    cs:__imp_GetLastError
0x140026106  test    eax, eax
0x140026108  jnz     short loc_14002612A
0x14002610a  mov     ebx, 36FDh
0x14002610f  test    ebx, ebx
0x140026111  jle     short loc_14002611C
0x140026113  movzx   ebx, bx
0x140026116  or      ebx, 80070000h
0x14002611c  lea     rcx, [rbp+57h+OldMode]; this
0x140026120  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x140026125  jmp     loc_14002631D
0x14002612a  call    cs:__imp_GetLastError
0x140026130  mov     ebx, eax
0x140026132  test    eax, eax
0x140026134  jz      loc_1400263C5
0x14002613a  jmp     short loc_14002610F
0x14002613c  lea     rcx, [rbp+57h+OldMode]; this
0x140026140  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x140026145  lea     rdx, aSssbindservici; "SssBindServicingStack"
0x14002614c  mov     rcx, rbx; hModule
0x14002614f  call    cs:__imp_GetProcAddress
0x140026155  mov     [rdi+10h], rax
0x140026159  test    rax, rax
0x14002615c  jnz     short loc_1400261BE
0x14002615e  call    cs:__imp_GetLastError
0x140026164  test    eax, eax
0x140026166  jnz     short loc_1400261AC
0x140026168  mov     ebx, 36FDh
0x14002616d  mov     [rbp+57h+var_70], 73h ; 's'
0x140026175  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x14002617c  mov     [rbp+57h+var_80], rax
0x140026180  lea     rax, aWindowsAutosss_0; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x140026187  mov     [rbp+57h+var_78], rax
0x14002618b  lea     rax, aMPfnsssbindser; "m_pfnSssBindServicingStack = GetProc<de"...
0x140026192  mov     [rbp+57h+var_68], rax
0x140026196  test    ebx, ebx
0x140026198  jle     short loc_1400261A3
0x14002619a  movzx   ebx, bx
0x14002619d  or      ebx, 80070000h
0x1400261a3  lea     rdx, [rbp+57h+var_80]
0x1400261a7  jmp     loc_14002630F
0x1400261ac  call    cs:__imp_GetLastError
0x1400261b2  mov     ebx, eax
0x1400261b4  test    eax, eax
0x1400261b6  jz      loc_1400263CB
0x1400261bc  jmp     short loc_14002616D
0x1400261be  lea     rdx, aSssreleaseserv; "SssReleaseServicingStack"
0x1400261c5  mov     rcx, rbx; hModule
0x1400261c8  call    cs:__imp_GetProcAddress
0x1400261ce  mov     [rdi+18h], rax
0x1400261d2  test    rax, rax
0x1400261d5  jnz     short loc_140026237
0x1400261d7  call    cs:__imp_GetLastError
0x1400261dd  test    eax, eax
0x1400261df  jnz     short loc_140026225
0x1400261e1  mov     ebx, 36FDh
0x1400261e6  mov     [rbp+57h+var_50], 74h ; 't'
0x1400261ee  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x1400261f5  mov     [rbp+57h+var_60], rax
0x1400261f9  lea     rax, aWindowsAutosss_0; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x140026200  mov     [rbp+57h+var_58], rax
0x140026204  lea     rax, aMPfnsssrelease; "m_pfnSssReleaseServicingStack = GetProc"...
0x14002620b  mov     [rbp+57h+var_48], rax
0x14002620f  test    ebx, ebx
0x140026211  jle     short loc_14002621C
0x140026213  movzx   ebx, bx
0x140026216  or      ebx, 80070000h
0x14002621c  lea     rdx, [rbp+57h+var_60]
0x140026220  jmp     loc_14002630F
0x140026225  call    cs:__imp_GetLastError
0x14002622b  mov     ebx, eax
0x14002622d  test    eax, eax
0x14002622f  jz      loc_1400263D1
0x140026235  jmp     short loc_1400261E6
0x140026237  lea     rdx, aSssgetservicin; "SssGetServicingStackFilePathLength"
0x14002623e  mov     rcx, rbx; hModule
0x140026241  call    cs:__imp_GetProcAddress
0x140026247  mov     [rdi+28h], rax
0x14002624b  test    rax, rax
0x14002624e  jnz     short loc_1400262AD
0x140026250  call    cs:__imp_GetLastError
0x140026256  test    eax, eax
0x140026258  jnz     short loc_14002629B
0x14002625a  mov     ebx, 36FDh
0x14002625f  mov     [rbp+57h+var_30], 75h ; 'u'
0x140026267  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x14002626e  mov     [rbp+57h+var_40], rax
0x140026272  lea     rax, aWindowsAutosss_0; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x140026279  mov     [rbp+57h+var_38], rax
0x14002627d  lea     rax, aMPfnsssgetserv_0; "m_pfnSssGetServicingStackFilePathLength"...
0x140026284  mov     [rbp+57h+var_28], rax
0x140026288  test    ebx, ebx
0x14002628a  jle     short loc_140026295
0x14002628c  movzx   ebx, bx
0x14002628f  or      ebx, 80070000h
0x140026295  lea     rdx, [rbp+57h+var_40]
0x140026299  jmp     short loc_14002630F
0x14002629b  call    cs:__imp_GetLastError
0x1400262a1  mov     ebx, eax
0x1400262a3  test    eax, eax
0x1400262a5  jz      loc_1400263D7
0x1400262ab  jmp     short loc_14002625F
0x1400262ad  lea     rdx, aSssgetservicin_0; "SssGetServicingStackFilePath"
0x1400262b4  mov     rcx, rbx; hModule
0x1400262b7  call    cs:__imp_GetProcAddress
0x1400262bd  mov     [rdi+30h], rax
0x1400262c1  test    rax, rax
0x1400262c4  jnz     short loc_140026345
0x1400262c6  call    cs:__imp_GetLastError
0x1400262cc  test    eax, eax
0x1400262ce  jnz     short loc_140026333
0x1400262d0  mov     ebx, 36FDh
0x1400262d5  mov     [rbp+57h+var_A0], 76h ; 'v'
0x1400262dd  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x1400262e4  mov     [rbp+57h+var_B0], rax
0x1400262e8  lea     rax, aWindowsAutosss_0; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x1400262ef  mov     [rbp+57h+var_A8], rax
0x1400262f3  lea     rax, aMPfnsssgetserv; "m_pfnSssGetServicingStackFilePath = Get"...
0x1400262fa  mov     [rbp+57h+var_98], rax
0x1400262fe  test    ebx, ebx
0x140026300  jle     short loc_14002630B
0x140026302  movzx   ebx, bx
0x140026305  or      ebx, 80070000h
0x14002630b  lea     rdx, [rbp+57h+var_B0]
0x14002630f  mov     r8d, ebx
0x140026312  lea     rcx, [rbp+57h+var_20]
0x140026316  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x14002631b  mov     ebx, eax
0x14002631d  lea     rcx, [rbp+57h+var_D0]
0x140026321  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140026326  lea     rcx, [rbp+57h+var_C8]
0x14002632a  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x14002632f  mov     eax, ebx
0x140026331  jmp     short loc_140026395
0x140026333  call    cs:__imp_GetLastError
0x140026339  mov     ebx, eax
0x14002633b  test    eax, eax
0x14002633d  jz      loc_1400263DD
0x140026343  jmp     short loc_1400262D5
0x140026345  lea     rdx, aSsspreloaddown; "SssPreloadDownlevelDependencies"
0x14002634c  mov     rcx, rbx; hModule
0x14002634f  call    cs:__imp_GetProcAddress
0x140026355  lea     rdx, aSssgetservicin_1; "SssGetServicingStackVersion"
0x14002635c  mov     rcx, rbx; hModule
0x14002635f  mov     [rdi+20h], rax
0x140026363  call    cs:__imp_GetProcAddress
0x140026369  mov     rcx, rdi
0x14002636c  mov     [rdi+38h], rax
0x140026370  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140026375  mov     [rbp+57h+var_D0], r14
0x140026379  cmp     [rdi], r14
0x14002637c  jnz     short loc_1400263B9
0x14002637e  lea     rcx, [rbp+57h+var_D0]
0x140026382  mov     [rdi], rbx
0x140026385  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x14002638a  lea     rcx, [rbp+57h+var_C8]
0x14002638e  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x140026393  xor     eax, eax
0x140026395  mov     rcx, [rbp+57h+var_18]
0x140026399  xor     rcx, rsp; StackCookie
0x14002639c  call    __security_check_cookie
0x1400263a1  lea     r11, [rsp+0F0h+var_10]
0x1400263a9  mov     rbx, [r11+30h]
0x1400263ad  mov     rsi, [r11+38h]
0x1400263b1  mov     rsp, r11
0x1400263b4  pop     r14
0x1400263b6  pop     rdi
0x1400263b7  pop     rbp
0x1400263b8  retn
0x1400263b9  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1400263bf  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1400263c5  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1400263cb  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1400263d1  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1400263d7  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1400263dd  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1400263e3  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1400263e9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
