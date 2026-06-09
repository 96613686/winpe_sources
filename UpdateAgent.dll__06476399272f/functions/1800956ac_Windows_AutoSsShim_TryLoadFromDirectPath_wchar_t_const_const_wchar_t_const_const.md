# Windows::AutoSsShim::TryLoadFromDirectPath(wchar_t const * const,wchar_t const * const)

- ea: `0x1800956ac`
- end: `0x180095d52`
- name: `?TryLoadFromDirectPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z`
- size: `1702`
- prototype: `int(Windows::AutoSsShim *__hidden this, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180095d58`

## callees

- `0x1800059d0`
- `0x1800692fc`
- `0x1800956ac`
- `0x18009acb0`
- `0x1801ee64c`
- `0x1801efdc0`
- `0x1801f01e4`
- `0x1801f250c`
- `0x1801f8f3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095960`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095a33`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095b06`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095bd9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095cb3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095ccd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095960`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095a33`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095b06`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095bd9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095cb3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180095ccd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800959f3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180095ac6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180095b99`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180095c58`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180095ce5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800959f3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180095ac6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180095b99`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180095c58`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180095ce5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18009589f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18009589f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009581a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009584f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800958b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009581a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009584f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800958b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095cf5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18009580a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18009580a`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180095883`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x1800958ee`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180095942`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180095883`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x1800958ee`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180095942`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x18009586e`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x1800958d9`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x18009592d`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x18009586e`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x1800958d9`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x18009592d`

## string_xrefs

- `0x180095735`: `ssshim.dll`
- `0x1800959b1`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180095a84`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180095b57`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180095c16`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x1800959c4`: `m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>("SssBindServicingStack", LocalSsShimDll)`
- `0x180095a97`: `m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>("SssReleaseServicingStack", LocalSsShimDll)`
- `0x180095afc`: `SssGetServicingStackFilePathLength`
- `0x180095b6a`: `m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>("SssGetServicingStackFilePathLength", LocalSsShimDll)`
- `0x180095bcf`: `SssGetServicingStackFilePath`
- `0x180095c29`: `m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>("SssGetServicingStackFilePath", LocalSsShimDll)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::AutoSsShim::TryLoadFromDirectPath(
        Windows::AutoSsShim *this,
        const WCHAR *a2,
        const wchar_t *const a3)
{
  const WCHAR *v5; // rdi
  __int64 v6; // rax
  NTSTATUS v7; // eax
  __int64 v8; // rcx
  __int128 v9; // kr00_16
  signed int LastError; // ebx
  DWORD ThreadErrorMode; // eax
  wil::details::in1diag3 *v13; // rcx
  HMODULE Library; // rsi
  FARPROC ProcAddress; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  const char *v19; // [rsp+28h] [rbp-29h] BYREF
  const char *v20; // [rsp+30h] [rbp-21h]
  __int64 v21; // [rsp+38h] [rbp-19h]
  const char *v22; // [rsp+40h] [rbp-11h]
  __int64 v23; // [rsp+48h] [rbp-9h]
  const wchar_t *v24; // [rsp+50h] [rbp-1h]
  __int128 v25; // [rsp+58h] [rbp+7h] BYREF
  LPCWSTR lpNewFileName; // [rsp+68h] [rbp+17h]
  __int64 v27; // [rsp+70h] [rbp+1Fh]
  HMODULE v28; // [rsp+78h] [rbp+27h]
  DWORD OldMode; // [rsp+80h] [rbp+2Fh] BYREF

  v27 = -2;
  if ( *(_QWORD *)this )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    goto LABEL_95;
  }
  v5 = 0;
  v25 = 0;
  lpNewFileName = 0;
  if ( !a3 )
    goto LABEL_28;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v19 = (const char *)(2 * v6);
  v20 = (const char *)(2 * v6 + 2);
  v21 = (__int64)a3;
  v22 = (const char *)20;
  v23 = 22;
  v24 = L"ssshim.dll";
  v7 = RtlCombineNtPathSegments(2, &v19, &v25);
  if ( v7 < 0 )
    goto LABEL_10;
  v9 = v25;
  if ( *((_QWORD *)&v25 + 1) - (_QWORD)v25 < 2u )
  {
    if ( (__int64)v25 + 2 < (unsigned __int64)v25 )
    {
      v7 = -1073741675;
      goto LABEL_10;
    }
    v7 = RtlReallocateLUnicodeString(v8, v25 + 2, &v25);
    if ( v7 < 0 )
    {
LABEL_10:
      LastError = ConvertNtStatusToHResult(v7);
      if ( lpNewFileName )
        anonymous_namespace_::OurRtlFreeStringRoutine(lpNewFileName);
      return (unsigned int)LastError;
    }
    v9 = v25;
  }
  v5 = lpNewFileName;
  *(LPCWSTR)((char *)lpNewFileName + (v9 & 0xFFFFFFFFFFFFFFFEuLL)) = 0;
  if ( v5 && (*((_QWORD *)&v9 + 1) - (_QWORD)v9 < 2u || v5[(unsigned __int64)v9 >> 1]) )
  {
LABEL_95:
    INTERNAL_ERROR_ACTION(-1073741595);
LABEL_96:
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  if ( !CopyFileW(a2, v5, 0) )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_20:
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( v5 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v5);
      return (unsigned int)LastError;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_20;
    goto LABEL_95;
  }
  a2 = v5;
LABEL_28:
  OldMode = 0;
  ThreadErrorMode = GetThreadErrorMode();
  if ( !SetThreadErrorMode(ThreadErrorMode | 1, &OldMode) )
    goto LABEL_98;
  Library = LoadLibraryExW(a2, 0, 0);
  v28 = Library;
  if ( !Library )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_96;
    }
    else
    {
      LastError = 14077;
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( OldMode == GetThreadErrorMode() || SetThreadErrorMode(OldMode, 0) )
    {
      if ( v5 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v5);
      return (unsigned int)LastError;
    }
LABEL_98:
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  }
  if ( OldMode != GetThreadErrorMode() && !SetThreadErrorMode(OldMode, 0) )
    goto LABEL_98;
  ProcAddress = GetProcAddress(Library, "SssBindServicingStack");
  *((_QWORD *)this + 2) = ProcAddress;
  if ( !ProcAddress )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_47:
      v19 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
      v20 = "Windows::AutoSsShim::TryLoadFromDirectPath";
      v21 = 115;
      v22 = "m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>(\"SssBindServicingStack\", LocalSsShimDll)";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(&v19, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
      if ( !FreeLibrary(Library) )
      {
        GetLastError();
        __fastfail(7u);
      }
      if ( v5 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v5);
      return (unsigned int)LastError;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_47;
LABEL_97:
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  v16 = GetProcAddress(Library, "SssReleaseServicingStack");
  *((_QWORD *)this + 3) = v16;
  if ( !v16 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_97;
    }
    else
    {
      LastError = 14077;
    }
    v19 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v20 = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v21 = 116;
    v22 = "m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>(\"SssReleaseServicingStack\", LocalSsShimDll)";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(&v19, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( !FreeLibrary(Library) )
    {
      GetLastError();
      __fastfail(7u);
    }
    if ( v5 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v5);
    return (unsigned int)LastError;
  }
  v17 = GetProcAddress(Library, "SssGetServicingStackFilePathLength");
  *((_QWORD *)this + 5) = v17;
  if ( !v17 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_97;
    }
    else
    {
      LastError = 14077;
    }
    v19 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v20 = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v21 = 117;
    v22 = "m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>(\"SssGetServic"
          "ingStackFilePathLength\", LocalSsShimDll)";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(&v19, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( !FreeLibrary(Library) )
    {
      GetLastError();
      __fastfail(7u);
    }
    if ( v5 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v5);
    return (unsigned int)LastError;
  }
  v18 = GetProcAddress(Library, "SssGetServicingStackFilePath");
  *((_QWORD *)this + 6) = v18;
  if ( !v18 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_97;
    }
    else
    {
      LastError = 14077;
    }
    v19 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v20 = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v21 = 118;
    v22 = "m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>(\"SssGetServicingStackFile"
          "Path\", LocalSsShimDll)";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(&v19, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( !FreeLibrary(Library) )
    {
      GetLastError();
      __fastfail(7u);
    }
    if ( v5 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v5);
    return (unsigned int)LastError;
  }
  *((_QWORD *)this + 4) = GetProcAddress(Library, "SssPreloadDownlevelDependencies");
  *((_QWORD *)this + 7) = GetProcAddress(Library, "SssGetServicingStackVersion");
  if ( *(_QWORD *)this && !FreeLibrary(*(HMODULE *)this) )
  {
    GetLastError();
    __fastfail(7u);
  }
  *(_QWORD *)this = Library;
  if ( v5 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v5);
  return 0;
}

```

## disassembly

```asm
0x1800956ac  mov     rax, rsp
0x1800956af  push    rbp
0x1800956b0  push    rdi
0x1800956b1  push    r14
0x1800956b3  lea     rbp, [rax-5Fh]
0x1800956b7  sub     rsp, 90h
0x1800956be  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800956c6  mov     [rax+18h], rbx
0x1800956ca  mov     [rax+20h], rsi
0x1800956ce  mov     rax, cs:__security_cookie
0x1800956d5  xor     rax, rsp
0x1800956d8  mov     [rbp+57h+var_20], rax
0x1800956dc  mov     rsi, rdx
0x1800956df  mov     rbx, rcx
0x1800956e2  xor     r14d, r14d
0x1800956e5  cmp     [rcx], r14
0x1800956e8  jnz     loc_180095D20
0x1800956ee  xorps   xmm0, xmm0
0x1800956f1  xor     edi, edi
0x1800956f3  movups  [rbp+57h+var_50], xmm0
0x1800956f7  mov     [rbp+57h+lpNewFileName], rdi
0x1800956fb  test    r8, r8
0x1800956fe  jz      loc_18009586A
0x180095704  or      rax, 0FFFFFFFFFFFFFFFFh
0x180095708  inc     rax
0x18009570b  cmp     [r8+rax*2], r14w
0x180095710  jnz     short loc_180095708
0x180095712  add     rax, rax
0x180095715  lea     rcx, [rax+2]
0x180095719  mov     [rbp+57h+var_80], rax
0x18009571d  mov     [rbp+57h+var_78], rcx
0x180095721  mov     [rbp+57h+var_70], r8
0x180095725  mov     [rbp+57h+var_68], 14h
0x18009572d  mov     [rbp+57h+var_60], 16h
0x180095735  lea     rax, aSsshimDll; "ssshim.dll"
0x18009573c  mov     [rbp+57h+var_58], rax
0x180095740  lea     r8, [rbp+57h+var_50]
0x180095744  lea     rdx, [rbp+57h+var_80]
0x180095748  mov     ecx, 2
0x18009574d  call    RtlCombineNtPathSegments
0x180095752  test    eax, eax
0x180095754  js      short loc_18009578A
0x180095756  mov     rdx, qword ptr [rbp+57h+var_50]
0x18009575a  mov     r8, qword ptr [rbp+57h+var_50+8]
0x18009575e  mov     rax, r8
0x180095761  sub     rax, rdx
0x180095764  cmp     rax, 2
0x180095768  jnb     short loc_1800957D1
0x18009576a  lea     rax, [rdx+2]
0x18009576e  cmp     rax, rdx
0x180095771  jnb     short loc_18009577A
0x180095773  mov     eax, 0C0000095h
0x180095778  jmp     short loc_18009578A
0x18009577a  lea     r8, [rbp+57h+var_50]
0x18009577e  mov     rdx, rax
0x180095781  call    RtlReallocateLUnicodeString
0x180095786  test    eax, eax
0x180095788  jns     short loc_1800957C9
0x18009578a  mov     ecx, eax; Status
0x18009578c  call    ConvertNtStatusToHResult
0x180095791  mov     ebx, eax
0x180095793  mov     rcx, [rbp+57h+lpNewFileName]
0x180095797  test    rcx, rcx
0x18009579a  jz      short loc_1800957A2
0x18009579c  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800957a1  nop
0x1800957a2  mov     eax, ebx
0x1800957a4  mov     rcx, [rbp+57h+var_20]
0x1800957a8  xor     rcx, rsp; StackCookie
0x1800957ab  call    __security_check_cookie
0x1800957b0  lea     r11, [rsp+0A0h+var_10]
0x1800957b8  mov     rbx, [r11+30h]
0x1800957bc  mov     rsi, [r11+38h]
0x1800957c0  mov     rsp, r11
0x1800957c3  pop     r14
0x1800957c5  pop     rdi
0x1800957c6  pop     rbp
0x1800957c7  retn
0x1800957c9  mov     r8, qword ptr [rbp+57h+var_50+8]
0x1800957cd  mov     rdx, qword ptr [rbp+57h+var_50]
0x1800957d1  mov     rcx, rdx
0x1800957d4  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800957d8  mov     rdi, [rbp+57h+lpNewFileName]
0x1800957dc  mov     [rcx+rdi], r14w
0x1800957e1  test    rdi, rdi
0x1800957e4  jz      short loc_180095801
0x1800957e6  sub     r8, rdx
0x1800957e9  cmp     r8, 2
0x1800957ed  jb      loc_180095D2B
0x1800957f3  shr     rdx, 1
0x1800957f6  cmp     [rdi+rdx*2], r14w
0x1800957fb  jnz     loc_180095D2B
0x180095801  xor     r8d, r8d; bFailIfExists
0x180095804  mov     rdx, rdi; lpNewFileName
0x180095807  mov     rcx, rsi; lpExistingFileName
0x18009580a  call    cs:__imp_CopyFileW
0x180095811  nop     dword ptr [rax+rax+00h]
0x180095816  test    eax, eax
0x180095818  jnz     short loc_180095867
0x18009581a  call    cs:__imp_GetLastError
0x180095821  nop     dword ptr [rax+rax+00h]
0x180095826  test    eax, eax
0x180095828  jnz     short loc_18009584F
0x18009582a  mov     ebx, 36FDh
0x18009582f  test    ebx, ebx
0x180095831  jle     short loc_18009583C
0x180095833  movzx   ebx, bx
0x180095836  or      ebx, 80070000h
0x18009583c  test    rdi, rdi
0x18009583f  jz      short loc_18009584A
0x180095841  mov     rcx, rdi
0x180095844  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180095849  nop
0x18009584a  jmp     loc_1800957A2
0x18009584f  call    cs:__imp_GetLastError
0x180095856  nop     dword ptr [rax+rax+00h]
0x18009585b  mov     ebx, eax
0x18009585d  test    eax, eax
0x18009585f  jz      loc_180095D2B
0x180095865  jmp     short loc_18009582F
0x180095867  mov     rsi, rdi
0x18009586a  mov     [rbp+57h+OldMode], r14d
0x18009586e  call    cs:__imp_GetThreadErrorMode
0x180095875  nop     dword ptr [rax+rax+00h]
0x18009587a  or      eax, 1
0x18009587d  lea     rdx, [rbp+57h+OldMode]; lpOldMode
0x180095881  mov     ecx, eax; dwNewMode
0x180095883  call    cs:__imp_SetThreadErrorMode
0x18009588a  nop     dword ptr [rax+rax+00h]
0x18009588f  test    eax, eax
0x180095891  jz      loc_180095D4C
0x180095897  xor     r8d, r8d; dwFlags
0x18009589a  xor     edx, edx; hFile
0x18009589c  mov     rcx, rsi; lpLibFileName
0x18009589f  call    cs:__imp_LoadLibraryExW
0x1800958a6  nop     dword ptr [rax+rax+00h]
0x1800958ab  mov     rsi, rax
0x1800958ae  mov     [rbp+57h+var_30], rax
0x1800958b2  test    rax, rax
0x1800958b5  jnz     short loc_18009592D
0x1800958b7  call    cs:__imp_GetLastError
0x1800958be  nop     dword ptr [rax+rax+00h]
0x1800958c3  test    eax, eax
0x1800958c5  jnz     short loc_180095915
0x1800958c7  mov     ebx, 36FDh
0x1800958cc  test    ebx, ebx
0x1800958ce  jle     short loc_1800958D9
0x1800958d0  movzx   ebx, bx
0x1800958d3  or      ebx, 80070000h
0x1800958d9  call    cs:__imp_GetThreadErrorMode
0x1800958e0  nop     dword ptr [rax+rax+00h]
0x1800958e5  mov     ecx, [rbp+57h+OldMode]; dwNewMode
0x1800958e8  cmp     ecx, eax
0x1800958ea  jz      short loc_180095902
0x1800958ec  xor     edx, edx; lpOldMode
0x1800958ee  call    cs:__imp_SetThreadErrorMode
0x1800958f5  nop     dword ptr [rax+rax+00h]
0x1800958fa  test    eax, eax
0x1800958fc  jz      loc_180095D4C
0x180095902  test    rdi, rdi
0x180095905  jz      short loc_180095910
0x180095907  mov     rcx, rdi
0x18009590a  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18009590f  nop
0x180095910  jmp     loc_1800957A2
0x180095915  call    cs:__imp_GetLastError
0x18009591c  nop     dword ptr [rax+rax+00h]
0x180095921  mov     ebx, eax
0x180095923  test    eax, eax
0x180095925  jz      loc_180095D36
0x18009592b  jmp     short loc_1800958CC
0x18009592d  call    cs:__imp_GetThreadErrorMode
0x180095934  nop     dword ptr [rax+rax+00h]
0x180095939  mov     ecx, [rbp+57h+OldMode]; dwNewMode
0x18009593c  cmp     ecx, eax
0x18009593e  jz      short loc_180095956
0x180095940  xor     edx, edx; lpOldMode
0x180095942  call    cs:__imp_SetThreadErrorMode
0x180095949  nop     dword ptr [rax+rax+00h]
0x18009594e  test    eax, eax
0x180095950  jz      loc_180095D4C
0x180095956  lea     rdx, aSssbindservici; "SssBindServicingStack"
0x18009595d  mov     rcx, rsi; hModule
0x180095960  call    cs:__imp_GetProcAddress
0x180095967  nop     dword ptr [rax+rax+00h]
0x18009596c  mov     [rbx+10h], rax
0x180095970  test    rax, rax
0x180095973  jnz     loc_180095A29
0x180095979  call    cs:__imp_GetLastError
0x180095980  nop     dword ptr [rax+rax+00h]
0x180095985  test    eax, eax
0x180095987  jnz     short loc_180095990
0x180095989  mov     ebx, 36FDh
0x18009598e  jmp     short loc_1800959A6
0x180095990  call    cs:__imp_GetLastError
0x180095997  nop     dword ptr [rax+rax+00h]
0x18009599c  mov     ebx, eax
0x18009599e  test    eax, eax
0x1800959a0  jz      loc_180095D41
0x1800959a6  lea     rax, aOnecoreBaseWcp_38; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x1800959ad  mov     [rbp+57h+var_80], rax
0x1800959b1  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x1800959b8  mov     [rbp+57h+var_78], rax
0x1800959bc  mov     [rbp+57h+var_70], 73h ; 's'
0x1800959c4  lea     rax, aMPfnsssbindser; "m_pfnSssBindServicingStack = GetProc<de"...
0x1800959cb  mov     [rbp+57h+var_68], rax
0x1800959cf  test    ebx, ebx
0x1800959d1  jle     short loc_1800959DC
0x1800959d3  movzx   ebx, bx
0x1800959d6  or      ebx, 80070000h
0x1800959dc  mov     r8d, ebx
0x1800959df  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800959e6  lea     rcx, [rbp+57h+var_80]
0x1800959ea  call    RtlReportErrorOrigination
0x1800959ef  nop
0x1800959f0  mov     rcx, rsi; hLibModule
0x1800959f3  call    cs:__imp_FreeLibrary
0x1800959fa  nop     dword ptr [rax+rax+00h]
0x1800959ff  test    eax, eax
0x180095a01  jnz     short loc_180095A16
0x180095a03  call    cs:__imp_GetLastError
0x180095a0a  nop     dword ptr [rax+rax+00h]
0x180095a0f  mov     ecx, 7
0x180095a14  int     29h; Win8: RtlFailFast(ecx)
0x180095a16  test    rdi, rdi
0x180095a19  jz      short loc_180095A24
0x180095a1b  mov     rcx, rdi
0x180095a1e  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180095a23  nop
0x180095a24  jmp     loc_1800957A2
0x180095a29  lea     rdx, aSssreleaseserv; "SssReleaseServicingStack"
0x180095a30  mov     rcx, rsi; hModule
0x180095a33  call    cs:__imp_GetProcAddress
0x180095a3a  nop     dword ptr [rax+rax+00h]
0x180095a3f  mov     [rbx+18h], rax
0x180095a43  test    rax, rax
0x180095a46  jnz     loc_180095AFC
0x180095a4c  call    cs:__imp_GetLastError
0x180095a53  nop     dword ptr [rax+rax+00h]
0x180095a58  test    eax, eax
0x180095a5a  jnz     short loc_180095A63
0x180095a5c  mov     ebx, 36FDh
0x180095a61  jmp     short loc_180095A79
0x180095a63  call    cs:__imp_GetLastError
0x180095a6a  nop     dword ptr [rax+rax+00h]
0x180095a6f  mov     ebx, eax
0x180095a71  test    eax, eax
0x180095a73  jz      loc_180095D41
0x180095a79  lea     rax, aOnecoreBaseWcp_38; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180095a80  mov     [rbp+57h+var_80], rax
0x180095a84  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180095a8b  mov     [rbp+57h+var_78], rax
0x180095a8f  mov     [rbp+57h+var_70], 74h ; 't'
0x180095a97  lea     rax, aMPfnsssrelease; "m_pfnSssReleaseServicingStack = GetProc"...
0x180095a9e  mov     [rbp+57h+var_68], rax
0x180095aa2  test    ebx, ebx
0x180095aa4  jle     short loc_180095AAF
0x180095aa6  movzx   ebx, bx
0x180095aa9  or      ebx, 80070000h
0x180095aaf  mov     r8d, ebx
0x180095ab2  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180095ab9  lea     rcx, [rbp+57h+var_80]
0x180095abd  call    RtlReportErrorOrigination
0x180095ac2  nop
0x180095ac3  mov     rcx, rsi; hLibModule
0x180095ac6  call    cs:__imp_FreeLibrary
0x180095acd  nop     dword ptr [rax+rax+00h]
0x180095ad2  test    eax, eax
0x180095ad4  jnz     short loc_180095AE9
0x180095ad6  call    cs:__imp_GetLastError
0x180095add  nop     dword ptr [rax+rax+00h]
0x180095ae2  mov     ecx, 7
0x180095ae7  int     29h; Win8: RtlFailFast(ecx)
0x180095ae9  test    rdi, rdi
0x180095aec  jz      short loc_180095AF7
0x180095aee  mov     rcx, rdi
0x180095af1  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180095af6  nop
0x180095af7  jmp     loc_1800957A2
0x180095afc  lea     rdx, aSssgetservicin; "SssGetServicingStackFilePathLength"
0x180095b03  mov     rcx, rsi; hModule
0x180095b06  call    cs:__imp_GetProcAddress
0x180095b0d  nop     dword ptr [rax+rax+00h]
0x180095b12  mov     [rbx+28h], rax
0x180095b16  test    rax, rax
0x180095b19  jnz     loc_180095BCF
0x180095b1f  call    cs:__imp_GetLastError
0x180095b26  nop     dword ptr [rax+rax+00h]
0x180095b2b  test    eax, eax
0x180095b2d  jnz     short loc_180095B36
0x180095b2f  mov     ebx, 36FDh
0x180095b34  jmp     short loc_180095B4C
0x180095b36  call    cs:__imp_GetLastError
0x180095b3d  nop     dword ptr [rax+rax+00h]
0x180095b42  mov     ebx, eax
0x180095b44  test    eax, eax
0x180095b46  jz      loc_180095D41
0x180095b4c  lea     rax, aOnecoreBaseWcp_38; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180095b53  mov     [rbp+57h+var_80], rax
0x180095b57  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
  ... truncated ...
```
