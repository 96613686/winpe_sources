# Windows::AutoSsShim::TryLoadFromDirectPath(wchar_t const * const,wchar_t const * const)

- ea: `0x1801946dc`
- end: `0x180194d53`
- name: `?TryLoadFromDirectPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z`
- size: `1655`
- prototype: `int(Windows::AutoSsShim *__hidden this, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180194d5c`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000c9e4`
- `0x18000e098`
- `0x180049274`
- `0x1800497c0`
- `0x180049c6c`
- `0x18005060c`
- `0x1801946dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019484f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801948e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801949a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801949bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194b00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194b46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194bd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194c2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019484f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801948e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801949a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801949bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194b00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194b46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194bd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194c2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194d0f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18019498b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194a5d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194b2d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194bfd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194ccd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194ce7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18019498b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194a5d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194b2d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194bfd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194ccd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180194ce7`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194a20`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194af0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194bc0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194c90`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194cff`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194a20`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194af0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194bc0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194c90`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180194cff`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801948d1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801948d1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18019483f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18019483f`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x1801948a0`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x180194907`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x180194958`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x1801948a0`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x180194907`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x180194958`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x1801948b5`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18019491c`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18019496d`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x1801948b5`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18019491c`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18019496d`

## string_xrefs

- `0x180194767`: `ssshim.dll`
- `0x180194ac1`: `m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>("SssReleaseServicingStack", LocalSsShimDll)`
- `0x1801949f0`: `m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>("SssBindServicingStack", LocalSsShimDll)`
- `0x180194bf3`: `SssGetServicingStackFilePath`
- `0x180194c61`: `m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>("SssGetServicingStackFilePath", LocalSsShimDll)`
- `0x1801949dd`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180194aae`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180194b7e`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180194c4e`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180194b23`: `SssGetServicingStackFilePathLength`
- `0x180194b91`: `m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>("SssGetServicingStackFilePathLength", LocalSsShimDll)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AutoSsShim::TryLoadFromDirectPath(
        Windows::AutoSsShim *this,
        const WCHAR *a2,
        const wchar_t *const a3)
{
  __int64 v5; // rax
  NTSTATUS v6; // eax
  __int64 v7; // rcx
  __int128 v8; // kr00_16
  signed int LastError; // ebx
  const WCHAR *v11; // rdi
  DWORD ThreadErrorMode; // eax
  wil::details::in1diag3 *v13; // rcx
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  __int128 v19; // [rsp+28h] [rbp-99h] BYREF
  LPCWSTR lpNewFileName; // [rsp+38h] [rbp-89h]
  _QWORD v21[4]; // [rsp+40h] [rbp-81h] BYREF
  _QWORD v22[4]; // [rsp+60h] [rbp-61h] BYREF
  _QWORD v23[4]; // [rsp+80h] [rbp-41h] BYREF
  _QWORD v24[4]; // [rsp+A0h] [rbp-21h] BYREF
  _QWORD v25[7]; // [rsp+C0h] [rbp-1h] BYREF
  DWORD OldMode; // [rsp+F8h] [rbp+37h] BYREF

  v25[6] = -2;
  if ( *(_QWORD *)this )
    goto LABEL_79;
  v19 = 0;
  lpNewFileName = 0;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v25[0] = 2 * v5;
    v25[1] = 2 * v5 + 2;
    v25[2] = a3;
    v25[3] = 20;
    v25[4] = 22;
    v25[5] = L"ssshim.dll";
    v6 = RtlCombineNtPathSegments(2, v25, &v19);
    if ( v6 < 0 )
      goto LABEL_10;
    v8 = v19;
    if ( *((_QWORD *)&v19 + 1) - (_QWORD)v19 < 2u )
    {
      if ( (__int64)v19 + 2 < (unsigned __int64)v19 )
      {
        v6 = -1073741675;
LABEL_10:
        LastError = ConvertNtStatusToHResult(v6);
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v19);
        return (unsigned int)LastError;
      }
      v6 = RtlReallocateLUnicodeString(v7, v19 + 2, &v19);
      if ( v6 < 0 )
        goto LABEL_10;
      v8 = v19;
    }
    v11 = lpNewFileName;
    *(LPCWSTR)((char *)lpNewFileName + (v8 & 0xFFFFFFFFFFFFFFFEuLL)) = 0;
    if ( v11 && (*((_QWORD *)&v8 + 1) - (_QWORD)v8 < 2u || v11[(unsigned __int64)v8 >> 1]) )
      goto LABEL_79;
    if ( !CopyFileW(a2, v11, 0) )
    {
      if ( !GetLastError() )
      {
        LastError = 14077;
        goto LABEL_20;
      }
      LastError = GetLastError();
      if ( LastError )
      {
LABEL_20:
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_22:
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v19);
        return (unsigned int)LastError;
      }
LABEL_79:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x180194D52LL);
    }
  }
  else
  {
    v11 = a2;
  }
  OldMode = 0;
  ThreadErrorMode = GetThreadErrorMode();
  if ( !SetThreadErrorMode(ThreadErrorMode | 1, &OldMode) )
LABEL_77:
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  Library = LoadLibraryExW(v11, 0, 0);
  if ( !Library )
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
    if ( OldMode == GetThreadErrorMode() || SetThreadErrorMode(OldMode, 0) )
      goto LABEL_22;
    goto LABEL_77;
  }
  if ( OldMode != GetThreadErrorMode() && !SetThreadErrorMode(OldMode, 0) )
    goto LABEL_77;
  ProcAddress = GetProcAddress(Library, "SssBindServicingStack");
  *((_QWORD *)this + 2) = ProcAddress;
  if ( !ProcAddress )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_79;
    }
    else
    {
      LastError = 14077;
    }
    v21[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v21[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v21[2] = 115;
    v21[3] = "m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>(\"SssBindServicingStack\", LocalSsShimDll)";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(v21, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( !FreeLibrary(Library) )
    {
      GetLastError();
      __fastfail(7u);
    }
    goto LABEL_22;
  }
  v16 = GetProcAddress(Library, "SssReleaseServicingStack");
  *((_QWORD *)this + 3) = v16;
  if ( !v16 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_79;
    }
    else
    {
      LastError = 14077;
    }
    v22[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v22[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v22[2] = 116;
    v22[3] = "m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>(\"SssReleaseServicingStack\", LocalSsShimDll)";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(v22, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( !FreeLibrary(Library) )
    {
      GetLastError();
      __fastfail(7u);
    }
    goto LABEL_22;
  }
  v17 = GetProcAddress(Library, "SssGetServicingStackFilePathLength");
  *((_QWORD *)this + 5) = v17;
  if ( !v17 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_79;
    }
    else
    {
      LastError = 14077;
    }
    v23[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v23[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v23[2] = 117;
    v23[3] = "m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>(\"SssGetSer"
             "vicingStackFilePathLength\", LocalSsShimDll)";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(v23, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( !FreeLibrary(Library) )
    {
      GetLastError();
      __fastfail(7u);
    }
    goto LABEL_22;
  }
  v18 = GetProcAddress(Library, "SssGetServicingStackFilePath");
  *((_QWORD *)this + 6) = v18;
  if ( !v18 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_79;
    }
    else
    {
      LastError = 14077;
    }
    v24[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v24[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v24[2] = 118;
    v24[3] = "m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>(\"SssGetServicingStackF"
             "ilePath\", LocalSsShimDll)";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(v24, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( !FreeLibrary(Library) )
    {
      GetLastError();
      __fastfail(7u);
    }
    goto LABEL_22;
  }
  *((_QWORD *)this + 4) = GetProcAddress(Library, "SssPreloadDownlevelDependencies");
  *((_QWORD *)this + 7) = GetProcAddress(Library, "SssGetServicingStackVersion");
  if ( *(_QWORD *)this && !FreeLibrary(*(HMODULE *)this) )
  {
    GetLastError();
    __fastfail(7u);
  }
  *(_QWORD *)this = Library;
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v19);
  return 0;
}

```

## disassembly

```asm
0x1801946dc  mov     rax, rsp
0x1801946df  push    rbp
0x1801946e0  push    rdi
0x1801946e1  push    r14
0x1801946e3  lea     rbp, [rax-5Fh]
0x1801946e7  sub     rsp, 100h
0x1801946ee  mov     [rbp+57h+var_28], 0FFFFFFFFFFFFFFFEh
0x1801946f6  mov     [rax+18h], rbx
0x1801946fa  mov     [rax+20h], rsi
0x1801946fe  mov     rax, cs:__security_cookie
0x180194705  xor     rax, rsp
0x180194708  mov     [rbp+57h+var_18], rax
0x18019470c  mov     rsi, rdx
0x18019470f  mov     rbx, rcx
0x180194712  xor     r14d, r14d
0x180194715  cmp     [rcx], r14
0x180194718  jnz     loc_180194D48
0x18019471e  xorps   xmm0, xmm0
0x180194721  xor     eax, eax
0x180194723  movups  [rsp+110h+var_F8+8], xmm0
0x180194728  mov     [rsp+110h+lpNewFileName], rax
0x18019472d  test    r8, r8
0x180194730  jz      loc_180194899
0x180194736  or      rax, 0FFFFFFFFFFFFFFFFh
0x18019473a  inc     rax
0x18019473d  cmp     [r8+rax*2], r14w
0x180194742  jnz     short loc_18019473A
0x180194744  add     rax, rax
0x180194747  lea     rcx, [rax+2]
0x18019474b  mov     [rbp+57h+var_58], rax
0x18019474f  mov     [rbp+57h+var_50], rcx
0x180194753  mov     [rbp+57h+var_48], r8
0x180194757  mov     [rbp+57h+var_40], 14h
0x18019475f  mov     [rbp+57h+var_38], 16h
0x180194767  lea     rax, aSsshimDll; "ssshim.dll"
0x18019476e  mov     [rbp+57h+var_30], rax
0x180194772  lea     r8, [rsp+110h+var_F8+8]
0x180194777  lea     rdx, [rbp+57h+var_58]
0x18019477b  mov     ecx, 2
0x180194780  call    RtlCombineNtPathSegments
0x180194785  test    eax, eax
0x180194787  js      short loc_1801947C0
0x180194789  mov     rdx, qword ptr [rsp+110h+var_F8+8]
0x18019478e  mov     r8, [rsp+110h+var_E8]
0x180194793  mov     rax, r8
0x180194796  sub     rax, rdx
0x180194799  cmp     rax, 2
0x18019479d  jnb     short loc_180194805
0x18019479f  lea     rax, [rdx+2]
0x1801947a3  cmp     rax, rdx
0x1801947a6  jnb     short loc_1801947AF
0x1801947a8  mov     eax, 0C0000095h
0x1801947ad  jmp     short loc_1801947C0
0x1801947af  lea     r8, [rsp+110h+var_F8+8]
0x1801947b4  mov     rdx, rax
0x1801947b7  call    RtlReallocateLUnicodeString
0x1801947bc  test    eax, eax
0x1801947be  jns     short loc_1801947FB
0x1801947c0  mov     ecx, eax; Status
0x1801947c2  call    ConvertNtStatusToHResult
0x1801947c7  mov     ebx, eax
0x1801947c9  lea     rcx, [rsp+110h+var_F8+8]
0x1801947ce  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801947d3  nop
0x1801947d4  mov     eax, ebx
0x1801947d6  mov     rcx, [rbp+57h+var_18]
0x1801947da  xor     rcx, rsp; StackCookie
0x1801947dd  call    __security_check_cookie
0x1801947e2  lea     r11, [rsp+110h+var_10]
0x1801947ea  mov     rbx, [r11+30h]
0x1801947ee  mov     rsi, [r11+38h]
0x1801947f2  mov     rsp, r11
0x1801947f5  pop     r14
0x1801947f7  pop     rdi
0x1801947f8  pop     rbp
0x1801947f9  retn
0x1801947fb  mov     r8, [rsp+110h+var_E8]
0x180194800  mov     rdx, qword ptr [rsp+110h+var_F8+8]
0x180194805  mov     rcx, rdx
0x180194808  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18019480c  mov     rdi, [rsp+110h+lpNewFileName]
0x180194811  mov     [rcx+rdi], r14w
0x180194816  test    rdi, rdi
0x180194819  jz      short loc_180194836
0x18019481b  sub     r8, rdx
0x18019481e  cmp     r8, 2
0x180194822  jb      loc_180194D48
0x180194828  shr     rdx, 1
0x18019482b  cmp     [rdi+rdx*2], r14w
0x180194830  jnz     loc_180194D48
0x180194836  xor     r8d, r8d; bFailIfExists
0x180194839  mov     rdx, rdi; lpNewFileName
0x18019483c  mov     rcx, rsi; lpExistingFileName
0x18019483f  call    cs:__imp_CopyFileW
0x180194846  nop     dword ptr [rax+rax+00h]
0x18019484b  test    eax, eax
0x18019484d  jnz     short loc_18019489C
0x18019484f  call    cs:__imp_GetLastError
0x180194856  nop     dword ptr [rax+rax+00h]
0x18019485b  test    eax, eax
0x18019485d  jnz     short loc_180194866
0x18019485f  mov     ebx, 36FDh
0x180194864  jmp     short loc_18019487C
0x180194866  call    cs:__imp_GetLastError
0x18019486d  nop     dword ptr [rax+rax+00h]
0x180194872  mov     ebx, eax
0x180194874  test    eax, eax
0x180194876  jz      loc_180194D48
0x18019487c  test    ebx, ebx
0x18019487e  jle     short loc_180194889
0x180194880  movzx   ebx, bx
0x180194883  or      ebx, 80070000h
0x180194889  lea     rcx, [rsp+110h+var_F8+8]
0x18019488e  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180194893  nop
0x180194894  jmp     loc_1801947D4
0x180194899  mov     rdi, rsi
0x18019489c  mov     [rbp+57h+OldMode], r14d
0x1801948a0  call    cs:__imp_GetThreadErrorMode
0x1801948a7  nop     dword ptr [rax+rax+00h]
0x1801948ac  or      eax, 1
0x1801948af  lea     rdx, [rbp+57h+OldMode]; lpOldMode
0x1801948b3  mov     ecx, eax; dwNewMode
0x1801948b5  call    cs:__imp_SetThreadErrorMode
0x1801948bc  nop     dword ptr [rax+rax+00h]
0x1801948c1  test    eax, eax
0x1801948c3  jz      loc_180194D37
0x1801948c9  xor     r8d, r8d; dwFlags
0x1801948cc  xor     edx, edx; hFile
0x1801948ce  mov     rcx, rdi; lpLibFileName
0x1801948d1  call    cs:__imp_LoadLibraryExW
0x1801948d8  nop     dword ptr [rax+rax+00h]
0x1801948dd  mov     rdi, rax
0x1801948e0  test    rax, rax
0x1801948e3  jnz     short loc_180194958
0x1801948e5  call    cs:__imp_GetLastError
0x1801948ec  nop     dword ptr [rax+rax+00h]
0x1801948f1  test    eax, eax
0x1801948f3  jnz     short loc_180194940
0x1801948f5  mov     ebx, 36FDh
0x1801948fa  test    ebx, ebx
0x1801948fc  jle     short loc_180194907
0x1801948fe  movzx   ebx, bx
0x180194901  or      ebx, 80070000h
0x180194907  call    cs:__imp_GetThreadErrorMode
0x18019490e  nop     dword ptr [rax+rax+00h]
0x180194913  mov     ecx, [rbp+57h+OldMode]; dwNewMode
0x180194916  cmp     ecx, eax
0x180194918  jz      short loc_180194930
0x18019491a  xor     edx, edx; lpOldMode
0x18019491c  call    cs:__imp_SetThreadErrorMode
0x180194923  nop     dword ptr [rax+rax+00h]
0x180194928  test    eax, eax
0x18019492a  jz      loc_180194D37
0x180194930  lea     rcx, [rsp+110h+var_F8+8]
0x180194935  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x18019493a  nop
0x18019493b  jmp     loc_1801947D4
0x180194940  call    cs:__imp_GetLastError
0x180194947  nop     dword ptr [rax+rax+00h]
0x18019494c  mov     ebx, eax
0x18019494e  test    eax, eax
0x180194950  jz      loc_180194D3D
0x180194956  jmp     short loc_1801948FA
0x180194958  call    cs:__imp_GetThreadErrorMode
0x18019495f  nop     dword ptr [rax+rax+00h]
0x180194964  mov     ecx, [rbp+57h+OldMode]; dwNewMode
0x180194967  cmp     ecx, eax
0x180194969  jz      short loc_180194981
0x18019496b  xor     edx, edx; lpOldMode
0x18019496d  call    cs:__imp_SetThreadErrorMode
0x180194974  nop     dword ptr [rax+rax+00h]
0x180194979  test    eax, eax
0x18019497b  jz      loc_180194D37
0x180194981  lea     rdx, aSssbindservici; "SssBindServicingStack"
0x180194988  mov     rcx, rdi; hModule
0x18019498b  call    cs:__imp_GetProcAddress
0x180194992  nop     dword ptr [rax+rax+00h]
0x180194997  mov     [rbx+10h], rax
0x18019499b  test    rax, rax
0x18019499e  jnz     loc_180194A53
0x1801949a4  call    cs:__imp_GetLastError
0x1801949ab  nop     dword ptr [rax+rax+00h]
0x1801949b0  test    eax, eax
0x1801949b2  jnz     short loc_1801949BB
0x1801949b4  mov     ebx, 36FDh
0x1801949b9  jmp     short loc_1801949D1
0x1801949bb  call    cs:__imp_GetLastError
0x1801949c2  nop     dword ptr [rax+rax+00h]
0x1801949c7  mov     ebx, eax
0x1801949c9  test    eax, eax
0x1801949cb  jz      loc_180194D48
0x1801949d1  lea     rax, aOnecoreBaseWcp_38; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x1801949d8  mov     [rsp+110h+var_D8], rax
0x1801949dd  lea     rax, aWindowsAutosss_0; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x1801949e4  mov     [rbp+57h+var_D0], rax
0x1801949e8  mov     [rbp+57h+var_C8], 73h ; 's'
0x1801949f0  lea     rax, aMPfnsssbindser; "m_pfnSssBindServicingStack = GetProc<de"...
0x1801949f7  mov     [rbp+57h+var_C0], rax
0x1801949fb  test    ebx, ebx
0x1801949fd  jle     short loc_180194A08
0x1801949ff  movzx   ebx, bx
0x180194a02  or      ebx, 80070000h
0x180194a08  mov     r8d, ebx
0x180194a0b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180194a12  lea     rcx, [rsp+110h+var_D8]
0x180194a17  call    RtlReportErrorOrigination
0x180194a1c  nop
0x180194a1d  mov     rcx, rdi; hLibModule
0x180194a20  call    cs:__imp_FreeLibrary
0x180194a27  nop     dword ptr [rax+rax+00h]
0x180194a2c  test    eax, eax
0x180194a2e  jnz     short loc_180194A43
0x180194a30  call    cs:__imp_GetLastError
0x180194a37  nop     dword ptr [rax+rax+00h]
0x180194a3c  mov     ecx, 7
0x180194a41  int     29h; Win8: RtlFailFast(ecx)
0x180194a43  lea     rcx, [rsp+110h+var_F8+8]
0x180194a48  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180194a4d  nop
0x180194a4e  jmp     loc_1801947D4
0x180194a53  lea     rdx, aSssreleaseserv; "SssReleaseServicingStack"
0x180194a5a  mov     rcx, rdi; hModule
0x180194a5d  call    cs:__imp_GetProcAddress
0x180194a64  nop     dword ptr [rax+rax+00h]
0x180194a69  mov     [rbx+18h], rax
0x180194a6d  test    rax, rax
0x180194a70  jnz     loc_180194B23
0x180194a76  call    cs:__imp_GetLastError
0x180194a7d  nop     dword ptr [rax+rax+00h]
0x180194a82  test    eax, eax
0x180194a84  jnz     short loc_180194A8D
0x180194a86  mov     ebx, 36FDh
0x180194a8b  jmp     short loc_180194AA3
0x180194a8d  call    cs:__imp_GetLastError
0x180194a94  nop     dword ptr [rax+rax+00h]
0x180194a99  mov     ebx, eax
0x180194a9b  test    eax, eax
0x180194a9d  jz      loc_180194D48
0x180194aa3  lea     rax, aOnecoreBaseWcp_38; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180194aaa  mov     [rbp+57h+var_B8], rax
0x180194aae  lea     rax, aWindowsAutosss_0; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180194ab5  mov     [rbp+57h+var_B0], rax
0x180194ab9  mov     [rbp+57h+var_A8], 74h ; 't'
0x180194ac1  lea     rax, aMPfnsssrelease; "m_pfnSssReleaseServicingStack = GetProc"...
0x180194ac8  mov     [rbp+57h+var_A0], rax
0x180194acc  test    ebx, ebx
0x180194ace  jle     short loc_180194AD9
0x180194ad0  movzx   ebx, bx
0x180194ad3  or      ebx, 80070000h
0x180194ad9  mov     r8d, ebx
0x180194adc  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180194ae3  lea     rcx, [rbp+57h+var_B8]
0x180194ae7  call    RtlReportErrorOrigination
0x180194aec  nop
0x180194aed  mov     rcx, rdi; hLibModule
0x180194af0  call    cs:__imp_FreeLibrary
0x180194af7  nop     dword ptr [rax+rax+00h]
0x180194afc  test    eax, eax
0x180194afe  jnz     short loc_180194B13
0x180194b00  call    cs:__imp_GetLastError
0x180194b07  nop     dword ptr [rax+rax+00h]
0x180194b0c  mov     ecx, 7
0x180194b11  int     29h; Win8: RtlFailFast(ecx)
0x180194b13  lea     rcx, [rsp+110h+var_F8+8]
0x180194b18  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180194b1d  nop
0x180194b1e  jmp     loc_1801947D4
0x180194b23  lea     rdx, aSssgetservicin; "SssGetServicingStackFilePathLength"
0x180194b2a  mov     rcx, rdi; hModule
0x180194b2d  call    cs:__imp_GetProcAddress
0x180194b34  nop     dword ptr [rax+rax+00h]
0x180194b39  mov     [rbx+28h], rax
0x180194b3d  test    rax, rax
0x180194b40  jnz     loc_180194BF3
0x180194b46  call    cs:__imp_GetLastError
0x180194b4d  nop     dword ptr [rax+rax+00h]
0x180194b52  test    eax, eax
0x180194b54  jnz     short loc_180194B5D
0x180194b56  mov     ebx, 36FDh
0x180194b5b  jmp     short loc_180194B73
0x180194b5d  call    cs:__imp_GetLastError
0x180194b64  nop     dword ptr [rax+rax+00h]
0x180194b69  mov     ebx, eax
0x180194b6b  test    eax, eax
0x180194b6d  jz      loc_180194D48
0x180194b73  lea     rax, aOnecoreBaseWcp_38; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180194b7a  mov     [rbp+57h+var_98], rax
0x180194b7e  lea     rax, aWindowsAutosss_0; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180194b85  mov     [rbp+57h+var_90], rax
0x180194b89  mov     [rbp+57h+var_88], 75h ; 'u'
0x180194b91  lea     rax, aMPfnsssgetserv_0; "m_pfnSssGetServicingStackFilePathLength"...
0x180194b98  mov     [rbp+57h+var_80], rax
0x180194b9c  test    ebx, ebx
0x180194b9e  jle     short loc_180194BA9
0x180194ba0  movzx   ebx, bx
0x180194ba3  or      ebx, 80070000h
0x180194ba9  mov     r8d, ebx
0x180194bac  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180194bb3  lea     rcx, [rbp+57h+var_98]
  ... truncated ...
```
