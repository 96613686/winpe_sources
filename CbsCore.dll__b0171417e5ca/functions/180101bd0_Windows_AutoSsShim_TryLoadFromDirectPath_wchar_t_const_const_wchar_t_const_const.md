# Windows::AutoSsShim::TryLoadFromDirectPath(wchar_t const * const,wchar_t const * const)

- ea: `0x180101bd0`
- end: `0x18010209e`
- name: `?TryLoadFromDirectPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z`
- size: `1230`
- prototype: `__int64 __fastcall(Windows::AutoSsShim *this, const WCHAR *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801020a4`

## callees

- `0x1800150c0`
- `0x180019bdc`
- `0x18003f40c`
- `0x180049ec0`
- `0x180050f18`
- `0x180056864`
- `0x1800aa104`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800f0df4`
- `0x1801008e0`
- `0x180100910`
- `0x180101bd0`
- `0x1801f8724`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180101db7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180101e42`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180101ecd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180101f58`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180102024`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18010203e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180101db7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180101e42`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180101ecd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180101f58`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180102024`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18010203e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180101d3b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180101d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101e6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101e6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101f88`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180101ca5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180101ca5`
- `KERNEL32!GetThreadErrorMode` at `0x180101d0a`
- `KERNEL32!GetThreadErrorMode` at `0x180101d0a`
- `KERNEL32!SetThreadErrorMode` at `0x180101d1f`
- `KERNEL32!SetThreadErrorMode` at `0x180101d1f`

## string_xrefs

- `0x180101c2f`: `ssshim.dll`
- `0x180101e17`: `m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>("SssBindServicingStack", LocalSsShimDll)`
- `0x180101ec3`: `SssGetServicingStackFilePathLength`
- `0x180101ea2`: `m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>("SssReleaseServicingStack", LocalSsShimDll)`
- `0x180101f4e`: `SssGetServicingStackFilePath`
- `0x180101f2d`: `m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>("SssGetServicingStackFilePathLength", LocalSsShimDll)`
- `0x180101e0c`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180101e97`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180101f22`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180101fb1`: `Windows::AutoSsShim::TryLoadFromDirectPath`
- `0x180101fbc`: `m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>("SssGetServicingStackFilePath", LocalSsShimDll)`

## pseudocode

```c
__int64 __fastcall Windows::AutoSsShim::TryLoadFromDirectPath(
        Windows::AutoSsShim *this,
        const WCHAR *a2,
        const wchar_t *const a3)
{
  bool v3; // zf
  NTSTATUS v6; // eax
  signed int LastError; // ebx
  const WCHAR *v8; // rbx
  DWORD ThreadErrorMode; // eax
  wil::details::in1diag3 *v10; // rcx
  HMODULE Library; // rax
  HMODULE v12; // rbx
  FARPROC ProcAddress; // rax
  signed int v14; // ebx
  __int128 *v15; // rdx
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  HMODULE hModule; // [rsp+20h] [rbp-79h] BYREF
  __int128 v21; // [rsp+28h] [rbp-71h] BYREF
  __int64 v22; // [rsp+38h] [rbp-61h]
  const char *v23; // [rsp+40h] [rbp-59h]
  __int128 v24; // [rsp+48h] [rbp-51h] BYREF
  __int64 v25; // [rsp+58h] [rbp-41h]
  __int128 v26; // [rsp+60h] [rbp-39h] BYREF
  __int64 v27; // [rsp+70h] [rbp-29h]
  __int128 v28; // [rsp+78h] [rbp-21h]
  __int64 v29; // [rsp+88h] [rbp-11h]
  _QWORD v30[4]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v31[4]; // [rsp+B0h] [rbp+17h] BYREF
  int v32; // [rsp+D0h] [rbp+37h] BYREF
  DWORD OldMode; // [rsp+D4h] [rbp+3Bh] BYREF

  v3 = *(_QWORD *)this == 0;
  v32 = 0;
  if ( !v3 )
    goto LABEL_56;
  v25 = 0;
  v24 = 0;
  if ( a3 )
  {
    Windows::StringUtil::AsLUnicode(&v21);
    v26 = v21;
    v27 = v22;
    Windows::StringUtil::AsLUnicode(&v21);
    v28 = v21;
    v29 = v22;
    v6 = RtlCombineNtPathSegments(2, &v26, &v24);
    if ( v6 < 0
      || (v6 = Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::Auto<_LUNICODE_STRING> *>(&v24), v6 < 0) )
    {
      LastError = ConvertNtStatusToHResult(v6);
LABEL_52:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v24);
      return (unsigned int)LastError;
    }
    v8 = (const WCHAR *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v24);
    if ( !CopyFileW(a2, v8, 0) )
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
      JUMPOUT(0x18010209DLL);
    }
  }
  else
  {
    v8 = a2;
  }
  hModule = 0;
  OldMode = 0;
  ThreadErrorMode = GetThreadErrorMode();
  if ( !SetThreadErrorMode(ThreadErrorMode | 1, &OldMode) )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v10);
  Library = LoadLibraryExW(v8, 0, 0);
  Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hModule, Library);
  v12 = hModule;
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
  ProcAddress = GetProcAddress(v12, "SssBindServicingStack");
  *((_QWORD *)this + 2) = ProcAddress;
  if ( !ProcAddress )
  {
    if ( GetLastError() )
    {
      v14 = GetLastError();
      if ( !v14 )
        goto LABEL_56;
    }
    else
    {
      v14 = 14077;
    }
    v22 = 115;
    *(_QWORD *)&v21 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    *((_QWORD *)&v21 + 1) = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v23 = "m_pfnSssBindServicingStack = GetProc<decltype(SssBindServicingStack)>(\"SssBindServicingStack\", LocalSsShimDll)";
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v15 = &v21;
    goto LABEL_50;
  }
  v16 = GetProcAddress(v12, "SssReleaseServicingStack");
  *((_QWORD *)this + 3) = v16;
  if ( !v16 )
  {
    if ( GetLastError() )
    {
      v14 = GetLastError();
      if ( !v14 )
        goto LABEL_56;
    }
    else
    {
      v14 = 14077;
    }
    v30[2] = 116;
    v30[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v30[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v30[3] = "m_pfnSssReleaseServicingStack = GetProc<decltype(SssReleaseServicingStack)>(\"SssReleaseServicingStack\", LocalSsShimDll)";
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v15 = (__int128 *)v30;
    goto LABEL_50;
  }
  v17 = GetProcAddress(v12, "SssGetServicingStackFilePathLength");
  *((_QWORD *)this + 5) = v17;
  if ( !v17 )
  {
    if ( GetLastError() )
    {
      v14 = GetLastError();
      if ( !v14 )
        goto LABEL_56;
    }
    else
    {
      v14 = 14077;
    }
    v31[2] = 117;
    v31[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v31[1] = "Windows::AutoSsShim::TryLoadFromDirectPath";
    v31[3] = "m_pfnSssGetServicingStackFilePathLength = GetProc<decltype(SssGetServicingStackFilePathLength)>(\"SssGetSer"
             "vicingStackFilePathLength\", LocalSsShimDll)";
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v15 = (__int128 *)v31;
    goto LABEL_50;
  }
  v18 = GetProcAddress(v12, "SssGetServicingStackFilePath");
  *((_QWORD *)this + 6) = v18;
  if ( !v18 )
  {
    if ( GetLastError() )
    {
      v14 = GetLastError();
      if ( !v14 )
        goto LABEL_56;
    }
    else
    {
      v14 = 14077;
    }
    v27 = 118;
    *(_QWORD *)&v26 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    *((_QWORD *)&v26 + 1) = "Windows::AutoSsShim::TryLoadFromDirectPath";
    *(_QWORD *)&v28 = "m_pfnSssGetServicingStackFilePath = GetProc<decltype(SssGetServicingStackFilePath)>(\"SssGetServic"
                      "ingStackFilePath\", LocalSsShimDll)";
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v15 = &v26;
LABEL_50:
    LastError = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
                  &v32,
                  v15,
                  (unsigned int)v14);
LABEL_51:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
    goto LABEL_52;
  }
  *((_QWORD *)this + 4) = GetProcAddress(v12, "SssPreloadDownlevelDependencies");
  *((_QWORD *)this + 7) = GetProcAddress(v12, "SssGetServicingStackVersion");
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(this);
  hModule = 0;
  Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(this, v12);
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v24);
  return 0;
}

```

## disassembly

```asm
0x180101bd0  mov     [rsp-8+arg_18], rbx
0x180101bd5  push    rbp
0x180101bd6  push    rsi
0x180101bd7  push    rdi
0x180101bd8  lea     rbp, [rsp-47h]
0x180101bdd  sub     rsp, 0E0h
0x180101be4  mov     rax, cs:__security_cookie
0x180101beb  xor     rax, rsp
0x180101bee  mov     [rbp+57h+var_18], rax
0x180101bf2  cmp     qword ptr [rcx], 0
0x180101bf6  mov     rsi, rdx
0x180101bf9  mov     rdi, rcx
0x180101bfc  mov     [rbp+57h+var_20], 0
0x180101c03  jnz     loc_180102093
0x180101c09  xor     eax, eax
0x180101c0b  xorps   xmm0, xmm0
0x180101c0e  mov     [rbp+57h+var_98], rax
0x180101c12  movups  [rbp+57h+var_A8], xmm0
0x180101c16  test    r8, r8
0x180101c19  jz      loc_180101CF8
0x180101c1f  mov     rdx, r8
0x180101c22  lea     rcx, [rbp+57h+var_C8]
0x180101c26  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x180101c2b  movups  xmm1, [rbp+57h+var_C8]
0x180101c2f  lea     rdx, aSsshimDll; "ssshim.dll"
0x180101c36  movsd   xmm2, [rbp+57h+var_B8]
0x180101c3b  lea     rcx, [rbp+57h+var_C8]
0x180101c3f  movups  [rbp+57h+var_90], xmm1
0x180101c43  movsd   [rbp+57h+var_80], xmm2
0x180101c48  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x180101c4d  movups  xmm1, [rbp+57h+var_C8]
0x180101c51  lea     r8, [rbp+57h+var_A8]
0x180101c55  mov     ecx, 2
0x180101c5a  movsd   xmm2, [rbp+57h+var_B8]
0x180101c5f  lea     rdx, [rbp+57h+var_90]
0x180101c63  movups  [rbp+57h+var_78], xmm1
0x180101c67  movsd   [rbp+57h+var_68], xmm2
0x180101c6c  call    RtlCombineNtPathSegments
0x180101c71  test    eax, eax
0x180101c73  js      short loc_180101C82
0x180101c75  lea     rcx, [rbp+57h+var_A8]
0x180101c79  call    ??$EnsureNullTerminated@PEAV?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@StringUtil@Windows@@YAJPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::Auto<_LUNICODE_STRING> *>(Windows::Auto<_LUNICODE_STRING> *)
0x180101c7e  test    eax, eax
0x180101c80  jns     short loc_180101C90
0x180101c82  mov     ecx, eax; Status
0x180101c84  call    ConvertNtStatusToHResult
0x180101c89  mov     ebx, eax
0x180101c8b  jmp     loc_180101FEF
0x180101c90  lea     rcx, [rbp+57h+var_A8]
0x180101c94  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x180101c99  xor     r8d, r8d; bFailIfExists
0x180101c9c  mov     rdx, rax; lpNewFileName
0x180101c9f  mov     rcx, rsi; lpExistingFileName
0x180101ca2  mov     rbx, rax
0x180101ca5  call    cs:__imp_CopyFileW
0x180101cac  nop     dword ptr [rax+rax+00h]
0x180101cb1  test    eax, eax
0x180101cb3  jnz     short loc_180101CFB
0x180101cb5  call    cs:__imp_GetLastError
0x180101cbc  nop     dword ptr [rax+rax+00h]
0x180101cc1  test    eax, eax
0x180101cc3  jnz     short loc_180101CCC
0x180101cc5  mov     ebx, 36FDh
0x180101cca  jmp     short loc_180101CE2
0x180101ccc  call    cs:__imp_GetLastError
0x180101cd3  nop     dword ptr [rax+rax+00h]
0x180101cd8  mov     ebx, eax
0x180101cda  test    eax, eax
0x180101cdc  jz      loc_180102093
0x180101ce2  test    ebx, ebx
0x180101ce4  jle     loc_180101FEF
0x180101cea  movzx   ebx, bx
0x180101ced  or      ebx, 80070000h
0x180101cf3  jmp     loc_180101FEF
0x180101cf8  mov     rbx, rsi
0x180101cfb  mov     [rbp+57h+hModule], 0
0x180101d03  mov     [rbp+57h+OldMode], 0
0x180101d0a  call    cs:__imp_GetThreadErrorMode
0x180101d11  nop     dword ptr [rax+rax+00h]
0x180101d16  or      eax, 1
0x180101d19  lea     rdx, [rbp+57h+OldMode]; lpOldMode
0x180101d1d  mov     ecx, eax; dwNewMode
0x180101d1f  call    cs:__imp_SetThreadErrorMode
0x180101d26  nop     dword ptr [rax+rax+00h]
0x180101d2b  test    eax, eax
0x180101d2d  jz      loc_180102082
0x180101d33  xor     r8d, r8d; dwFlags
0x180101d36  xor     edx, edx; hFile
0x180101d38  mov     rcx, rbx; lpLibFileName
0x180101d3b  call    cs:__imp_LoadLibraryExW
0x180101d42  nop     dword ptr [rax+rax+00h]
0x180101d47  mov     rdx, rax
0x180101d4a  lea     rcx, [rbp+57h+hModule]
0x180101d4e  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x180101d53  mov     rbx, [rbp+57h+hModule]
0x180101d57  test    rbx, rbx
0x180101d5a  jnz     short loc_180101DA4
0x180101d5c  call    cs:__imp_GetLastError
0x180101d63  nop     dword ptr [rax+rax+00h]
0x180101d68  test    eax, eax
0x180101d6a  jnz     short loc_180101D8C
0x180101d6c  mov     ebx, 36FDh
0x180101d71  test    ebx, ebx
0x180101d73  jle     short loc_180101D7E
0x180101d75  movzx   ebx, bx
0x180101d78  or      ebx, 80070000h
0x180101d7e  lea     rcx, [rbp+57h+OldMode]; this
0x180101d82  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x180101d87  jmp     loc_180101FE6
0x180101d8c  call    cs:__imp_GetLastError
0x180101d93  nop     dword ptr [rax+rax+00h]
0x180101d98  mov     ebx, eax
0x180101d9a  test    eax, eax
0x180101d9c  jz      loc_180102088
0x180101da2  jmp     short loc_180101D71
0x180101da4  lea     rcx, [rbp+57h+OldMode]; this
0x180101da8  call    ??1AutoThreadMode@Windows@@QEAA@XZ; Windows::AutoThreadMode::~AutoThreadMode(void)
0x180101dad  lea     rdx, aSssbindservici; "SssBindServicingStack"
0x180101db4  mov     rcx, rbx; hModule
0x180101db7  call    cs:__imp_GetProcAddress
0x180101dbe  nop     dword ptr [rax+rax+00h]
0x180101dc3  mov     [rdi+10h], rax
0x180101dc7  test    rax, rax
0x180101dca  jnz     short loc_180101E38
0x180101dcc  call    cs:__imp_GetLastError
0x180101dd3  nop     dword ptr [rax+rax+00h]
0x180101dd8  test    eax, eax
0x180101dda  jnz     short loc_180101DE3
0x180101ddc  mov     ebx, 36FDh
0x180101de1  jmp     short loc_180101DF9
0x180101de3  call    cs:__imp_GetLastError
0x180101dea  nop     dword ptr [rax+rax+00h]
0x180101def  mov     ebx, eax
0x180101df1  test    eax, eax
0x180101df3  jz      loc_180102093
0x180101df9  mov     [rbp+57h+var_B8], 73h ; 's'
0x180101e01  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180101e08  mov     qword ptr [rbp+57h+var_C8], rax
0x180101e0c  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180101e13  mov     qword ptr [rbp+57h+var_C8+8], rax
0x180101e17  lea     rax, aMPfnsssbindser; "m_pfnSssBindServicingStack = GetProc<de"...
0x180101e1e  mov     [rbp+57h+var_B0], rax
0x180101e22  test    ebx, ebx
0x180101e24  jle     short loc_180101E2F
0x180101e26  movzx   ebx, bx
0x180101e29  or      ebx, 80070000h
0x180101e2f  lea     rdx, [rbp+57h+var_C8]
0x180101e33  jmp     loc_180101FD8
0x180101e38  lea     rdx, aSssreleaseserv; "SssReleaseServicingStack"
0x180101e3f  mov     rcx, rbx; hModule
0x180101e42  call    cs:__imp_GetProcAddress
0x180101e49  nop     dword ptr [rax+rax+00h]
0x180101e4e  mov     [rdi+18h], rax
0x180101e52  test    rax, rax
0x180101e55  jnz     short loc_180101EC3
0x180101e57  call    cs:__imp_GetLastError
0x180101e5e  nop     dword ptr [rax+rax+00h]
0x180101e63  test    eax, eax
0x180101e65  jnz     short loc_180101E6E
0x180101e67  mov     ebx, 36FDh
0x180101e6c  jmp     short loc_180101E84
0x180101e6e  call    cs:__imp_GetLastError
0x180101e75  nop     dword ptr [rax+rax+00h]
0x180101e7a  mov     ebx, eax
0x180101e7c  test    eax, eax
0x180101e7e  jz      loc_180102093
0x180101e84  mov     [rbp+57h+var_50], 74h ; 't'
0x180101e8c  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180101e93  mov     [rbp+57h+var_60], rax
0x180101e97  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180101e9e  mov     [rbp+57h+var_58], rax
0x180101ea2  lea     rax, aMPfnsssrelease; "m_pfnSssReleaseServicingStack = GetProc"...
0x180101ea9  mov     [rbp+57h+var_48], rax
0x180101ead  test    ebx, ebx
0x180101eaf  jle     short loc_180101EBA
0x180101eb1  movzx   ebx, bx
0x180101eb4  or      ebx, 80070000h
0x180101eba  lea     rdx, [rbp+57h+var_60]
0x180101ebe  jmp     loc_180101FD8
0x180101ec3  lea     rdx, aSssgetservicin; "SssGetServicingStackFilePathLength"
0x180101eca  mov     rcx, rbx; hModule
0x180101ecd  call    cs:__imp_GetProcAddress
0x180101ed4  nop     dword ptr [rax+rax+00h]
0x180101ed9  mov     [rdi+28h], rax
0x180101edd  test    rax, rax
0x180101ee0  jnz     short loc_180101F4E
0x180101ee2  call    cs:__imp_GetLastError
0x180101ee9  nop     dword ptr [rax+rax+00h]
0x180101eee  test    eax, eax
0x180101ef0  jnz     short loc_180101EF9
0x180101ef2  mov     ebx, 36FDh
0x180101ef7  jmp     short loc_180101F0F
0x180101ef9  call    cs:__imp_GetLastError
0x180101f00  nop     dword ptr [rax+rax+00h]
0x180101f05  mov     ebx, eax
0x180101f07  test    eax, eax
0x180101f09  jz      loc_180102093
0x180101f0f  mov     [rbp+57h+var_30], 75h ; 'u'
0x180101f17  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180101f1e  mov     [rbp+57h+var_40], rax
0x180101f22  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180101f29  mov     [rbp+57h+var_38], rax
0x180101f2d  lea     rax, aMPfnsssgetserv_0; "m_pfnSssGetServicingStackFilePathLength"...
0x180101f34  mov     [rbp+57h+var_28], rax
0x180101f38  test    ebx, ebx
0x180101f3a  jle     short loc_180101F45
0x180101f3c  movzx   ebx, bx
0x180101f3f  or      ebx, 80070000h
0x180101f45  lea     rdx, [rbp+57h+var_40]
0x180101f49  jmp     loc_180101FD8
0x180101f4e  lea     rdx, aSssgetservicin_0; "SssGetServicingStackFilePath"
0x180101f55  mov     rcx, rbx; hModule
0x180101f58  call    cs:__imp_GetProcAddress
0x180101f5f  nop     dword ptr [rax+rax+00h]
0x180101f64  mov     [rdi+30h], rax
0x180101f68  test    rax, rax
0x180101f6b  jnz     loc_18010201A
0x180101f71  call    cs:__imp_GetLastError
0x180101f78  nop     dword ptr [rax+rax+00h]
0x180101f7d  test    eax, eax
0x180101f7f  jnz     short loc_180101F88
0x180101f81  mov     ebx, 36FDh
0x180101f86  jmp     short loc_180101F9E
0x180101f88  call    cs:__imp_GetLastError
0x180101f8f  nop     dword ptr [rax+rax+00h]
0x180101f94  mov     ebx, eax
0x180101f96  test    eax, eax
0x180101f98  jz      loc_180102093
0x180101f9e  mov     [rbp+57h+var_80], 76h ; 'v'
0x180101fa6  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x180101fad  mov     qword ptr [rbp+57h+var_90], rax
0x180101fb1  lea     rax, aWindowsAutosss_1; "Windows::AutoSsShim::TryLoadFromDirectP"...
0x180101fb8  mov     qword ptr [rbp+57h+var_90+8], rax
0x180101fbc  lea     rax, aMPfnsssgetserv; "m_pfnSssGetServicingStackFilePath = Get"...
0x180101fc3  mov     qword ptr [rbp+57h+var_78], rax
0x180101fc7  test    ebx, ebx
0x180101fc9  jle     short loc_180101FD4
0x180101fcb  movzx   ebx, bx
0x180101fce  or      ebx, 80070000h
0x180101fd4  lea     rdx, [rbp+57h+var_90]
0x180101fd8  mov     r8d, ebx
0x180101fdb  lea     rcx, [rbp+57h+var_20]
0x180101fdf  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180101fe4  mov     ebx, eax
0x180101fe6  lea     rcx, [rbp+57h+hModule]
0x180101fea  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180101fef  lea     rcx, [rbp+57h+var_A8]
0x180101ff3  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180101ff8  mov     eax, ebx
0x180101ffa  mov     rcx, [rbp+57h+var_18]
0x180101ffe  xor     rcx, rsp; StackCookie
0x180102001  call    __security_check_cookie
0x180102006  mov     rbx, [rsp+0F0h+arg_18]
0x18010200e  add     rsp, 0E0h
0x180102015  pop     rdi
0x180102016  pop     rsi
0x180102017  pop     rbp
0x180102018  retn
0x18010201a  lea     rdx, aSsspreloaddown; "SssPreloadDownlevelDependencies"
0x180102021  mov     rcx, rbx; hModule
0x180102024  call    cs:__imp_GetProcAddress
0x18010202b  nop     dword ptr [rax+rax+00h]
0x180102030  lea     rdx, aSssgetservicin_1; "SssGetServicingStackVersion"
0x180102037  mov     rcx, rbx; hModule
0x18010203a  mov     [rdi+20h], rax
0x18010203e  call    cs:__imp_GetProcAddress
0x180102045  nop     dword ptr [rax+rax+00h]
0x18010204a  mov     rcx, rdi
0x18010204d  mov     [rdi+38h], rax
0x180102051  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180102056  mov     rdx, rbx
0x180102059  mov     [rbp+57h+hModule], 0
0x180102061  mov     rcx, rdi
0x180102064  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x180102069  lea     rcx, [rbp+57h+hModule]
0x18010206d  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180102072  lea     rcx, [rbp+57h+var_A8]
0x180102076  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18010207b  xor     eax, eax
0x18010207d  jmp     loc_180101FFA
0x180102082  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180102088  mov     ecx, 0C00000E5h; int
0x18010208d  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x180102092  int     3; Trap to Debugger
0x180102093  mov     ecx, 0C00000E5h; int
0x180102098  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
