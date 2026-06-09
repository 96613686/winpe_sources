# GetFileContents(wchar_t const *,Windows::Auto<_LBLOB> *)

- ea: `0x180183bf0`
- end: `0x18018423a`
- name: `?GetFileContents@@YAJPEB_WPEAV?$Auto@U_LBLOB@@@Windows@@@Z`
- size: `1610`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180056c70`
- `0x1800852dc`
- `0x1800f6b20`
- `0x18010da6c`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000f874`
- `0x18001a810`
- `0x1800497c0`
- `0x18004be10`
- `0x18004d970`
- `0x18005060c`
- `0x180183bf0`

## import_xrefs

- `ntdll!NtClose` at `0x180183de2`
- `ntdll!NtClose` at `0x180183ee6`
- `ntdll!NtClose` at `0x180183fb0`
- `ntdll!NtClose` at `0x18018400a`
- `ntdll!NtClose` at `0x18018412e`
- `ntdll!NtClose` at `0x1801841a8`
- `ntdll!NtClose` at `0x1801841ed`
- `ntdll!NtClose` at `0x180183de2`
- `ntdll!NtClose` at `0x180183ee6`
- `ntdll!NtClose` at `0x180183fb0`
- `ntdll!NtClose` at `0x18018400a`
- `ntdll!NtClose` at `0x18018412e`
- `ntdll!NtClose` at `0x1801841a8`
- `ntdll!NtClose` at `0x1801841ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180183d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180183e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018405c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180183d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180183e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018405c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180184048`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180184048`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180183e0f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180183e0f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180183cf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180183cf5`

## string_xrefs

- `0x180183f8b`: `__tempE`
- `0x180183c51`: `Not-null check failed: szWin32FilePath`
- `0x180183d3d`: `Could not open file {0}`
- `0x18018416d`: `dwBytesRead == dwSizeToRead`
- `0x180184084`: `Failed to read file {0}`
- `0x180183daf`: `__tempErr`
- `0x180183ebd`: `__tempErr`
- `0x1801840f6`: `__tempErr`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFileContents(const WCHAR *a1, __int64 a2)
{
  const char *v3; // rax
  char *FileW; // rax
  char *v6; // rdi
  signed int LastError; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  DWORD LowPart; // ebx
  __int64 v13; // rdx
  NTSTATUS LBlob; // eax
  LPVOID v15; // r14
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // xmm2_8
  const char *v19; // [rsp+50h] [rbp-B8h] BYREF
  const char *v20; // [rsp+58h] [rbp-B0h]
  __int64 v21; // [rsp+60h] [rbp-A8h]
  _QWORD v22[3]; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID lpBuffer; // [rsp+80h] [rbp-88h]
  _QWORD v24[4]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v25[4]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v26[4]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v27[4]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v28[5]; // [rsp+108h] [rbp+0h] BYREF
  LPCWSTR lpFileName; // [rsp+130h] [rbp+28h] BYREF
  int v30; // [rsp+138h] [rbp+30h]
  DWORD NumberOfBytesRead; // [rsp+13Ch] [rbp+34h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+140h] [rbp+38h] BYREF

  v28[4] = -2;
  lpFileName = a1;
  if ( !a1 )
  {
    v19 = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    v20 = "GetFileContents";
    v21 = 58;
    v3 = "Not-null check failed: szWin32FilePath";
LABEL_3:
    v22[0] = v3;
    RtlReportErrorOrigination(&v19, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147500035LL);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    v19 = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    v20 = "GetFileContents";
    v21 = 59;
    v3 = "Not-null check failed: pContents";
    goto LABEL_3;
  }
  if ( *(_QWORD *)(a2 + 16) )
  {
    anonymous_namespace_::OurRtlFreeStringRoutine(*(_QWORD *)(a2 + 16));
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    a1 = lpFileName;
  }
  FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Could not open file {0}",
        &lpFileName);
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = LastError;
      v30 = v9;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v8,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v24[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
      v24[1] = "GetFileContents";
      v24[2] = 74;
      v24[3] = "__tempErr";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(v24, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
      if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v6) < 0 )
        __fastfail(7u);
      return (unsigned int)LastError;
    }
    goto LABEL_70;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Could not query file size for {0}",
        &lpFileName);
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      else
        v11 = LastError;
      v30 = v11;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v25[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
      v25[1] = "GetFileContents";
      v25[2] = 78;
      v25[3] = "__tempErr";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(v25, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
      if ( NtClose(v6) < 0 )
        __fastfail(7u);
      return (unsigned int)LastError;
    }
LABEL_70:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180184239LL);
  }
  LowPart = FileSize.LowPart;
  if ( FileSize.QuadPart > 0xFFFFFFFFLL )
  {
    LastError = -2147024673;
    v30 = -2147024673;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "File too large {0}",
        &lpFileName);
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v13,
        3,
        ": {}");
    }
    v26[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    v26[1] = "GetFileContents";
    v26[2] = 82;
    v26[3] = "__tempE";
    RtlReportErrorOrigination(v26, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942623LL);
    if ( NtClose(v6) < 0 )
      __fastfail(7u);
    return (unsigned int)LastError;
  }
  *(_OWORD *)&v22[1] = 0;
  lpBuffer = 0;
  LBlob = RtlAllocateLBlob(FileSize.LowPart, &v22[1]);
  if ( LBlob < 0 )
  {
    LastError = ConvertNtStatusToHResult(LBlob);
    if ( lpBuffer )
      anonymous_namespace_::OurRtlFreeStringRoutine(lpBuffer);
    if ( NtClose(v6) < 0 )
      __fastfail(7u);
    return (unsigned int)LastError;
  }
  NumberOfBytesRead = 0;
  v15 = lpBuffer;
  if ( !ReadFile(v6, lpBuffer, LowPart, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to read file {0}",
        &lpFileName);
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      else
        v17 = LastError;
      v30 = v17;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v16,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v27[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
      v27[1] = "GetFileContents";
      v27[2] = 91;
      v27[3] = "__tempErr";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(v27, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
      if ( v15 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v15);
      if ( NtClose(v6) < 0 )
        __fastfail(7u);
      return (unsigned int)LastError;
    }
    goto LABEL_70;
  }
  if ( NumberOfBytesRead != LowPart )
  {
    v28[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    v28[1] = "GetFileContents";
    v28[2] = 93;
    v28[3] = "dwBytesRead == dwSizeToRead";
    LastError = ConvertNtStatusToHResult(-1073741823);
    RtlReportErrorOrigination(v28, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( v15 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v15);
    if ( NtClose(v6) < 0 )
      __fastfail(7u);
    return (unsigned int)LastError;
  }
  v22[1] = LowPart;
  v18 = *(_QWORD *)(a2 + 16);
  *(_OWORD *)a2 = *(_OWORD *)&v22[1];
  *(_QWORD *)(a2 + 16) = v15;
  if ( v18 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v18);
  if ( NtClose(v6) < 0 )
    __fastfail(7u);
  return 0;
}

```

## disassembly

```asm
0x180183bf0  mov     rax, rsp
0x180183bf3  push    rbp
0x180183bf4  push    rdi
0x180183bf5  push    r13
0x180183bf7  push    r14
0x180183bf9  push    r15
0x180183bfb  lea     rbp, [rax-78h]
0x180183bff  sub     rsp, 150h
0x180183c06  mov     [rbp+70h+var_50], 0FFFFFFFFFFFFFFFEh
0x180183c0e  mov     [rax+18h], rbx
0x180183c12  mov     [rax+20h], rsi
0x180183c16  mov     rax, cs:__security_cookie
0x180183c1d  xor     rax, rsp
0x180183c20  mov     [rbp+70h+var_30], rax
0x180183c24  mov     rsi, rdx
0x180183c27  mov     [rbp+70h+lpFileName], rcx
0x180183c2b  test    rcx, rcx
0x180183c2e  jnz     short loc_180183C7E
0x180183c30  lea     rax, aOnecoreBaseSer_35; "onecore\\base\\servicing\\util\\servici"...
0x180183c37  mov     [rsp+170h+var_128], rax
0x180183c3c  lea     rax, aGetfilecontent; "GetFileContents"
0x180183c43  mov     [rsp+170h+var_120], rax
0x180183c48  mov     [rsp+170h+var_118], 3Ah ; ':'
0x180183c51  lea     rax, aNotNullCheckFa_23; "Not-null check failed: szWin32FilePath"
0x180183c58  mov     qword ptr [rsp+170h+var_110], rax
0x180183c5d  mov     r8d, 80004003h
0x180183c63  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180183c6a  lea     rcx, [rsp+170h+var_128]
0x180183c6f  call    RtlReportErrorOrigination
0x180183c74  mov     eax, 80004003h
0x180183c79  jmp     loc_180184206
0x180183c7e  test    rsi, rsi
0x180183c81  jnz     short loc_180183CAD
0x180183c83  lea     rax, aOnecoreBaseSer_35; "onecore\\base\\servicing\\util\\servici"...
0x180183c8a  mov     [rsp+170h+var_128], rax
0x180183c8f  lea     rax, aGetfilecontent; "GetFileContents"
0x180183c96  mov     [rsp+170h+var_120], rax
0x180183c9b  mov     [rsp+170h+var_118], 3Bh ; ';'
0x180183ca4  lea     rax, aNotNullCheckFa_80; "Not-null check failed: pContents"
0x180183cab  jmp     short loc_180183C58
0x180183cad  cmp     qword ptr [rdx+10h], 0
0x180183cb2  jz      short loc_180183CCD
0x180183cb4  mov     rcx, [rdx+10h]
0x180183cb8  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180183cbd  xorps   xmm0, xmm0
0x180183cc0  xor     eax, eax
0x180183cc2  movups  xmmword ptr [rsi], xmm0
0x180183cc5  mov     [rsi+10h], rax
0x180183cc9  mov     rcx, [rbp+70h+lpFileName]; lpFileName
0x180183ccd  mov     [rsp+170h+hTemplateFile], 0; hTemplateFile
0x180183cd6  mov     [rsp+170h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180183cde  mov     r13d, 3
0x180183ce4  mov     [rsp+170h+dwCreationDisposition], r13d; dwCreationDisposition
0x180183ce9  xor     r9d, r9d; lpSecurityAttributes
0x180183cec  mov     edx, 80000000h; dwDesiredAccess
0x180183cf1  lea     r8d, [r13-2]; dwShareMode
0x180183cf5  call    cs:__imp_CreateFileW
0x180183cfc  nop     dword ptr [rax+rax+00h]
0x180183d01  mov     rdi, rax
0x180183d04  lea     rcx, [rax+1]
0x180183d08  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180183d0f  jnz     loc_180183E00
0x180183d15  call    cs:__imp_GetLastError
0x180183d1c  nop     dword ptr [rax+rax+00h]
0x180183d21  mov     ebx, eax
0x180183d23  mov     esi, 80070000h
0x180183d28  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180183d2f  test    rcx, rcx
0x180183d32  jz      short loc_180183D89
0x180183d34  lea     rax, [rbp+70h+lpFileName]
0x180183d38  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x180183d3d  lea     r9, aCouldNotOpenFi; "Could not open file {0}"
0x180183d44  mov     r8d, r13d
0x180183d47  xor     edx, edx
0x180183d49  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180183d4e  test    ebx, ebx
0x180183d50  jg      short loc_180183D56
0x180183d52  mov     eax, ebx
0x180183d54  jmp     short loc_180183D5B
0x180183d56  movzx   eax, bx
0x180183d59  or      eax, esi
0x180183d5b  mov     [rbp+70h+var_40], eax
0x180183d5e  lea     rax, [rbp+70h+var_40]
0x180183d62  mov     [rsp+170h+var_130], rax
0x180183d67  lea     rax, [rsp+170h+var_130]
0x180183d6c  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x180183d71  lea     r9, a0; ": {0}"
0x180183d78  mov     r8d, r13d
0x180183d7b  mov     dl, 1
0x180183d7d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180183d84  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180183d89  test    ebx, ebx
0x180183d8b  jz      loc_18018422F
0x180183d91  lea     rax, aOnecoreBaseSer_35; "onecore\\base\\servicing\\util\\servici"...
0x180183d98  mov     [rbp+70h+var_F0], rax
0x180183d9c  lea     rax, aGetfilecontent; "GetFileContents"
0x180183da3  mov     [rbp+70h+var_E8], rax
0x180183da7  mov     [rbp+70h+var_E0], 4Ah ; 'J'
0x180183daf  lea     rax, aTemperr; "__tempErr"
0x180183db6  mov     [rbp+70h+var_D8], rax
0x180183dba  jle     short loc_180183DC1
0x180183dbc  movzx   ebx, bx
0x180183dbf  or      ebx, esi
0x180183dc1  mov     r8d, ebx
0x180183dc4  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180183dcb  lea     rcx, [rbp+70h+var_F0]
0x180183dcf  call    RtlReportErrorOrigination
0x180183dd4  nop
0x180183dd5  lea     rax, [rdi-1]
0x180183dd9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180183ddd  ja      short loc_180183DF9
0x180183ddf  mov     rcx, rdi; Handle
0x180183de2  call    cs:__imp_NtClose
0x180183de9  nop     dword ptr [rax+rax+00h]
0x180183dee  test    eax, eax
0x180183df0  jns     short loc_180183DF9
0x180183df2  mov     ecx, 7
0x180183df7  int     29h; Win8: RtlFailFast(ecx)
0x180183df9  mov     eax, ebx
0x180183dfb  jmp     loc_180184206
0x180183e00  mov     qword ptr [rbp+70h+FileSize], 0
0x180183e08  lea     rdx, [rbp+70h+FileSize]; lpFileSize
0x180183e0c  mov     rcx, rdi; hFile
0x180183e0f  call    cs:__imp_GetFileSizeEx
0x180183e16  nop     dword ptr [rax+rax+00h]
0x180183e1b  test    eax, eax
0x180183e1d  jnz     loc_180183F02
0x180183e23  call    cs:__imp_GetLastError
0x180183e2a  nop     dword ptr [rax+rax+00h]
0x180183e2f  mov     ebx, eax
0x180183e31  mov     esi, 80070000h
0x180183e36  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180183e3d  test    rcx, rcx
0x180183e40  jz      short loc_180183E97
0x180183e42  lea     rax, [rbp+70h+lpFileName]
0x180183e46  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x180183e4b  lea     r9, aCouldNotQueryF; "Could not query file size for {0}"
0x180183e52  mov     r8d, r13d
0x180183e55  xor     edx, edx
0x180183e57  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180183e5c  test    ebx, ebx
0x180183e5e  jg      short loc_180183E64
0x180183e60  mov     eax, ebx
0x180183e62  jmp     short loc_180183E69
0x180183e64  movzx   eax, bx
0x180183e67  or      eax, esi
0x180183e69  mov     [rbp+70h+var_40], eax
0x180183e6c  lea     rax, [rbp+70h+var_40]
0x180183e70  mov     [rsp+170h+var_130], rax
0x180183e75  lea     rax, [rsp+170h+var_130]
0x180183e7a  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x180183e7f  lea     r9, a0; ": {0}"
0x180183e86  mov     r8d, r13d
0x180183e89  mov     dl, 1
0x180183e8b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180183e92  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180183e97  test    ebx, ebx
0x180183e99  jz      loc_18018422F
0x180183e9f  lea     rax, aOnecoreBaseSer_35; "onecore\\base\\servicing\\util\\servici"...
0x180183ea6  mov     [rbp+70h+var_D0], rax
0x180183eaa  lea     rax, aGetfilecontent; "GetFileContents"
0x180183eb1  mov     [rbp+70h+var_C8], rax
0x180183eb5  mov     [rbp+70h+var_C0], 4Eh ; 'N'
0x180183ebd  lea     rax, aTemperr; "__tempErr"
0x180183ec4  mov     [rbp+70h+var_B8], rax
0x180183ec8  jle     short loc_180183ECF
0x180183eca  movzx   ebx, bx
0x180183ecd  or      ebx, esi
0x180183ecf  mov     r8d, ebx
0x180183ed2  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180183ed9  lea     rcx, [rbp+70h+var_D0]
0x180183edd  call    RtlReportErrorOrigination
0x180183ee2  nop
0x180183ee3  mov     rcx, rdi; Handle
0x180183ee6  call    cs:__imp_NtClose
0x180183eed  nop     dword ptr [rax+rax+00h]
0x180183ef2  test    eax, eax
0x180183ef4  jns     short loc_180183EFD
0x180183ef6  mov     ecx, 7
0x180183efb  int     29h; Win8: RtlFailFast(ecx)
0x180183efd  jmp     loc_180183DF9
0x180183f02  mov     eax, 0FFFFFFFFh
0x180183f07  mov     rbx, qword ptr [rbp+70h+FileSize]
0x180183f0b  cmp     rbx, rax
0x180183f0e  jle     loc_180183FCC
0x180183f14  mov     ebx, 800700DFh
0x180183f19  mov     [rbp+70h+var_40], ebx
0x180183f1c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180183f23  test    rcx, rcx
0x180183f26  jz      short loc_180183F6D
0x180183f28  lea     rax, [rbp+70h+lpFileName]
0x180183f2c  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x180183f31  lea     r9, aFileTooLarge0; "File too large {0}"
0x180183f38  mov     r8d, r13d
0x180183f3b  xor     edx, edx
0x180183f3d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180183f42  lea     rax, [rbp+70h+var_40]
0x180183f46  mov     [rsp+170h+var_130], rax
0x180183f4b  lea     rax, [rsp+170h+var_130]
0x180183f50  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x180183f55  lea     r9, asc_1801CAFB4; ": {}"
0x180183f5c  mov     r8d, r13d
0x180183f5f  mov     dl, 1
0x180183f61  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180183f68  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180183f6d  lea     rax, aOnecoreBaseSer_35; "onecore\\base\\servicing\\util\\servici"...
0x180183f74  mov     [rbp+70h+var_B0], rax
0x180183f78  lea     rax, aGetfilecontent; "GetFileContents"
0x180183f7f  mov     [rbp+70h+var_A8], rax
0x180183f83  mov     [rbp+70h+var_A0], 52h ; 'R'
0x180183f8b  lea     rax, aTempe; "__tempE"
0x180183f92  mov     [rbp+70h+var_98], rax
0x180183f96  mov     r8d, 800700DFh
0x180183f9c  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180183fa3  lea     rcx, [rbp+70h+var_B0]
0x180183fa7  call    RtlReportErrorOrigination
0x180183fac  nop
0x180183fad  mov     rcx, rdi; Handle
0x180183fb0  call    cs:__imp_NtClose
0x180183fb7  nop     dword ptr [rax+rax+00h]
0x180183fbc  test    eax, eax
0x180183fbe  jns     short loc_180183FC7
0x180183fc0  mov     ecx, 7
0x180183fc5  int     29h; Win8: RtlFailFast(ecx)
0x180183fc7  jmp     loc_180183DF9
0x180183fcc  xorps   xmm0, xmm0
0x180183fcf  xor     eax, eax
0x180183fd1  movups  xmmword ptr [rsp+170h+var_110+8], xmm0
0x180183fd6  mov     [rsp+170h+lpBuffer], rax
0x180183fdb  mov     r15d, ebx
0x180183fde  lea     rdx, [rsp+170h+var_110+8]
0x180183fe3  mov     ecx, ebx
0x180183fe5  call    RtlAllocateLBlob
0x180183fea  test    eax, eax
0x180183fec  jns     short loc_180184026
0x180183fee  mov     ecx, eax; Status
0x180183ff0  call    ConvertNtStatusToHResult
0x180183ff5  mov     ebx, eax
0x180183ff7  mov     rcx, [rsp+170h+lpBuffer]
0x180183ffc  test    rcx, rcx
0x180183fff  jz      short loc_180184007
0x180184001  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180184006  nop
0x180184007  mov     rcx, rdi; Handle
0x18018400a  call    cs:__imp_NtClose
0x180184011  nop     dword ptr [rax+rax+00h]
0x180184016  test    eax, eax
0x180184018  jns     short loc_180184021
0x18018401a  mov     ecx, 7
0x18018401f  int     29h; Win8: RtlFailFast(ecx)
0x180184021  jmp     loc_180183DF9
0x180184026  mov     [rbp+70h+NumberOfBytesRead], 0
0x18018402d  mov     r14, [rsp+170h+lpBuffer]
0x180184032  mov     qword ptr [rsp+170h+dwCreationDisposition], 0; lpOverlapped
0x18018403b  lea     r9, [rbp+70h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18018403f  mov     r8d, ebx; nNumberOfBytesToRead
0x180184042  mov     rdx, r14; lpBuffer
0x180184045  mov     rcx, rdi; hFile
0x180184048  call    cs:__imp_ReadFile
0x18018404f  nop     dword ptr [rax+rax+00h]
0x180184054  test    eax, eax
0x180184056  jnz     loc_18018414A
0x18018405c  call    cs:__imp_GetLastError
0x180184063  nop     dword ptr [rax+rax+00h]
0x180184068  mov     ebx, eax
0x18018406a  mov     esi, 80070000h
0x18018406f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180184076  test    rcx, rcx
0x180184079  jz      short loc_1801840D0
0x18018407b  lea     rax, [rbp+70h+lpFileName]
0x18018407f  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x180184084  lea     r9, aFailedToReadFi; "Failed to read file {0}"
0x18018408b  mov     r8d, r13d
0x18018408e  xor     edx, edx
0x180184090  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180184095  test    ebx, ebx
0x180184097  jg      short loc_18018409D
0x180184099  mov     eax, ebx
0x18018409b  jmp     short loc_1801840A2
0x18018409d  movzx   eax, bx
0x1801840a0  or      eax, esi
0x1801840a2  mov     [rbp+70h+var_40], eax
0x1801840a5  lea     rax, [rbp+70h+var_40]
0x1801840a9  mov     [rsp+170h+var_130], rax
0x1801840ae  lea     rax, [rsp+170h+var_130]
0x1801840b3  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x1801840b8  lea     r9, a0; ": {0}"
0x1801840bf  mov     r8d, r13d
0x1801840c2  mov     dl, 1
0x1801840c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801840cb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801840d0  test    ebx, ebx
0x1801840d2  jz      loc_18018422F
0x1801840d8  lea     rax, aOnecoreBaseSer_35; "onecore\\base\\servicing\\util\\servici"...
0x1801840df  mov     [rbp+70h+var_90], rax
0x1801840e3  lea     rax, aGetfilecontent; "GetFileContents"
0x1801840ea  mov     [rbp+70h+var_88], rax
0x1801840ee  mov     [rbp+70h+var_80], 5Bh ; '['
0x1801840f6  lea     rax, aTemperr; "__tempErr"
0x1801840fd  mov     [rbp+70h+var_78], rax
  ... truncated ...
```
