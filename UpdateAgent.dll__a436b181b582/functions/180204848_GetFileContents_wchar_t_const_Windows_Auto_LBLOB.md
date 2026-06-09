# GetFileContents(wchar_t const *,Windows::Auto<_LBLOB> *)

- ea: `0x180204848`
- end: `0x180204e91`
- name: `?GetFileContents@@YAJPEB_WPEAV?$Auto@U_LBLOB@@@Windows@@@Z`
- size: `1609`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x1800acf28`
- `0x1800cf750`
- `0x180159c68`
- `0x180170bdc`
- `0x1802522a0`

## callees

- `0x1800059d0`
- `0x18000b508`
- `0x18000c4c4`
- `0x180022940`
- `0x1800692fc`
- `0x1801ea940`
- `0x1801efdc0`
- `0x1801f250c`
- `0x1801f8f3c`
- `0x180204848`

## import_xrefs

- `ntdll!NtClose` at `0x180204a3a`
- `ntdll!NtClose` at `0x180204b3e`
- `ntdll!NtClose` at `0x180204c08`
- `ntdll!NtClose` at `0x180204c5d`
- `ntdll!NtClose` at `0x180204d7c`
- `ntdll!NtClose` at `0x180204df4`
- `ntdll!NtClose` at `0x180204e49`
- `ntdll!NtClose` at `0x180204a3a`
- `ntdll!NtClose` at `0x180204b3e`
- `ntdll!NtClose` at `0x180204c08`
- `ntdll!NtClose` at `0x180204c5d`
- `ntdll!NtClose` at `0x180204d7c`
- `ntdll!NtClose` at `0x180204df4`
- `ntdll!NtClose` at `0x180204e49`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180204c98`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180204c98`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180204a67`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180204a67`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180204949`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180204949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180204969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180204a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180204cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180204969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180204a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180204cac`

## string_xrefs

- `0x180204be3`: `__tempE`
- `0x1802048a4`: `Not-null check failed: szWin32FilePath`
- `0x180204cd4`: `Failed to read file {0}`
- `0x180204dbb`: `dwBytesRead == dwSizeToRead`
- `0x180204991`: `Could not open file {0}`
- `0x180204a06`: `__tempErr`
- `0x180204b15`: `__tempErr`
- `0x180204d46`: `__tempErr`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFileContents(const WCHAR *a1, __int128 *a2)
{
  const char *v3; // rax
  char *FileW; // rax
  char *v6; // rsi
  signed int LastError; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  DWORD LowPart; // ebx
  __int64 v13; // rdx
  NTSTATUS v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int128 v17; // xmm2
  void *v18; // xmm3_8
  __int128 v19; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID lpBuffer; // [rsp+60h] [rbp-A8h]
  const char *v21; // [rsp+68h] [rbp-A0h]
  _QWORD v22[4]; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v23[4]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v24[4]; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v25[4]; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v26[5]; // [rsp+F0h] [rbp-18h] BYREF
  LPCWSTR lpFileName; // [rsp+118h] [rbp+10h] BYREF
  int v28; // [rsp+120h] [rbp+18h]
  DWORD NumberOfBytesRead; // [rsp+124h] [rbp+1Ch] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+128h] [rbp+20h] BYREF

  v26[4] = -2;
  lpFileName = a1;
  if ( !a1 )
  {
    *(_QWORD *)&v19 = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    *((_QWORD *)&v19 + 1) = "GetFileContents";
    lpBuffer = (LPVOID)58;
    v3 = "Not-null check failed: szWin32FilePath";
LABEL_3:
    v21 = v3;
    RtlReportErrorOrigination(&v19, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147500035LL);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    *(_QWORD *)&v19 = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    *((_QWORD *)&v19 + 1) = "GetFileContents";
    lpBuffer = (LPVOID)59;
    v3 = "Not-null check failed: pContents";
    goto LABEL_3;
  }
  if ( *((_QWORD *)a2 + 2) )
  {
    anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)a2 + 2));
    *a2 = 0;
    *((_QWORD *)a2 + 2) = 0;
    a1 = lpFileName;
  }
  FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Could not open file {0}",
        &lpFileName);
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = LastError;
      v28 = v9;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v8,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v22[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
      v22[1] = "GetFileContents";
      v22[2] = 74;
      v22[3] = "__tempErr";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(v22, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
      if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v6) < 0 )
        __fastfail(7u);
      return (unsigned int)LastError;
    }
    goto LABEL_62;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Could not query file size for {0}",
        &lpFileName);
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      else
        v11 = LastError;
      v28 = v11;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v23[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
      v23[1] = "GetFileContents";
      v23[2] = 78;
      v23[3] = "__tempErr";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(v23, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
      if ( NtClose(v6) < 0 )
        __fastfail(7u);
      return (unsigned int)LastError;
    }
LABEL_62:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180204E90LL);
  }
  LowPart = FileSize.LowPart;
  if ( FileSize.QuadPart > 0xFFFFFFFFLL )
  {
    LastError = -2147024673;
    v28 = -2147024673;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
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
    v24[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    v24[1] = "GetFileContents";
    v24[2] = 82;
    v24[3] = "__tempE";
    RtlReportErrorOrigination(v24, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942623LL);
    if ( NtClose(v6) < 0 )
      __fastfail(7u);
    return (unsigned int)LastError;
  }
  v19 = 0;
  lpBuffer = 0;
  v14 = RtlAllocateLBlob(FileSize.LowPart, &v19);
  if ( v14 < 0 )
  {
    LastError = ConvertNtStatusToHResult(v14);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v19);
    if ( NtClose(v6) < 0 )
      __fastfail(7u);
    return (unsigned int)LastError;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(v6, lpBuffer, LowPart, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to read file {0}",
        &lpFileName);
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      else
        v16 = LastError;
      v28 = v16;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v15,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v25[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
      v25[1] = "GetFileContents";
      v25[2] = 91;
      v25[3] = "__tempErr";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(v25, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v19);
      if ( NtClose(v6) < 0 )
        __fastfail(7u);
      return (unsigned int)LastError;
    }
    goto LABEL_62;
  }
  if ( NumberOfBytesRead != LowPart )
  {
    v26[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    v26[1] = "GetFileContents";
    v26[2] = 93;
    v26[3] = "dwBytesRead == dwSizeToRead";
    LastError = ConvertNtStatusToHResult(-1073741823);
    RtlReportErrorOrigination(v26, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v19);
    if ( NtClose(v6) < 0 )
      __fastfail(7u);
    return (unsigned int)LastError;
  }
  *(_QWORD *)&v19 = LowPart;
  v17 = *a2;
  v18 = (void *)*((_QWORD *)a2 + 2);
  *a2 = v19;
  *((_QWORD *)a2 + 2) = lpBuffer;
  v19 = v17;
  lpBuffer = v18;
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v19);
  if ( NtClose(v6) < 0 )
    __fastfail(7u);
  return 0;
}

```

## disassembly

```asm
0x180204848  mov     rax, rsp
0x18020484b  push    rbp
0x18020484c  push    rsi
0x18020484d  push    rdi
0x18020484e  push    r12
0x180204850  push    r14
0x180204852  lea     rbp, [rax-58h]
0x180204856  sub     rsp, 130h
0x18020485d  mov     [rbp+50h+var_48], 0FFFFFFFFFFFFFFFEh
0x180204865  mov     [rax+18h], rbx
0x180204869  mov     rax, cs:__security_cookie
0x180204870  xor     rax, rsp
0x180204873  mov     [rbp+50h+var_28], rax
0x180204877  mov     rdi, rdx
0x18020487a  mov     [rbp+50h+lpFileName], rcx
0x18020487e  test    rcx, rcx
0x180204881  jnz     short loc_1802048D1
0x180204883  lea     rax, aOnecoreBaseSer_32; "onecore\\base\\servicing\\util\\servici"...
0x18020488a  mov     qword ptr [rsp+150h+var_110+8], rax
0x18020488f  lea     rax, aGetfilecontent; "GetFileContents"
0x180204896  mov     [rsp+150h+var_100], rax
0x18020489b  mov     [rsp+150h+lpBuffer], 3Ah ; ':'
0x1802048a4  lea     rax, aNotNullCheckFa_30; "Not-null check failed: szWin32FilePath"
0x1802048ab  mov     [rsp+150h+var_F0], rax
0x1802048b0  mov     r8d, 80004003h
0x1802048b6  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1802048bd  lea     rcx, [rsp+150h+var_110+8]
0x1802048c2  call    RtlReportErrorOrigination
0x1802048c7  mov     eax, 80004003h
0x1802048cc  jmp     loc_180204E62
0x1802048d1  test    rdi, rdi
0x1802048d4  jnz     short loc_180204900
0x1802048d6  lea     rax, aOnecoreBaseSer_32; "onecore\\base\\servicing\\util\\servici"...
0x1802048dd  mov     qword ptr [rsp+150h+var_110+8], rax
0x1802048e2  lea     rax, aGetfilecontent; "GetFileContents"
0x1802048e9  mov     [rsp+150h+var_100], rax
0x1802048ee  mov     [rsp+150h+lpBuffer], 3Bh ; ';'
0x1802048f7  lea     rax, aNotNullCheckFa_103; "Not-null check failed: pContents"
0x1802048fe  jmp     short loc_1802048AB
0x180204900  cmp     qword ptr [rdx+10h], 0
0x180204905  jz      short loc_180204920
0x180204907  mov     rcx, [rdx+10h]
0x18020490b  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180204910  xorps   xmm0, xmm0
0x180204913  xor     eax, eax
0x180204915  movups  xmmword ptr [rdi], xmm0
0x180204918  mov     [rdi+10h], rax
0x18020491c  mov     rcx, [rbp+50h+lpFileName]; lpFileName
0x180204920  mov     qword ptr [rsp+30h], 0; hTemplateFile
0x180204929  mov     [rsp+150h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180204931  mov     r12d, 3
0x180204937  mov     [rsp+150h+dwCreationDisposition], r12d; dwCreationDisposition
0x18020493c  xor     r9d, r9d; lpSecurityAttributes
0x18020493f  mov     edx, 80000000h; dwDesiredAccess
0x180204944  lea     r8d, [r12-2]; dwShareMode
0x180204949  call    cs:__imp_CreateFileW
0x180204950  nop     dword ptr [rax+rax+00h]
0x180204955  mov     rsi, rax
0x180204958  lea     rcx, [rax+1]
0x18020495c  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180204963  jnz     loc_180204A58
0x180204969  call    cs:__imp_GetLastError
0x180204970  nop     dword ptr [rax+rax+00h]
0x180204975  mov     ebx, eax
0x180204977  mov     edi, 80070000h
0x18020497c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180204983  test    rcx, rcx
0x180204986  jz      short loc_1802049DD
0x180204988  lea     rax, [rbp+50h+lpFileName]
0x18020498c  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180204991  lea     r9, aCouldNotOpenFi; "Could not open file {0}"
0x180204998  mov     r8d, r12d
0x18020499b  xor     edx, edx
0x18020499d  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x1802049a2  test    ebx, ebx
0x1802049a4  jg      short loc_1802049AA
0x1802049a6  mov     eax, ebx
0x1802049a8  jmp     short loc_1802049AF
0x1802049aa  movzx   eax, bx
0x1802049ad  or      eax, edi
0x1802049af  mov     [rbp+50h+var_38], eax
0x1802049b2  lea     rax, [rbp+50h+var_38]
0x1802049b6  mov     qword ptr [rsp+150h+var_110], rax
0x1802049bb  lea     rax, [rsp+150h+var_110]
0x1802049c0  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x1802049c5  lea     r9, a0; ": {0}"
0x1802049cc  mov     r8d, r12d
0x1802049cf  mov     dl, 1
0x1802049d1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802049d8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802049dd  test    ebx, ebx
0x1802049df  jz      loc_180204E86
0x1802049e5  lea     rax, aOnecoreBaseSer_32; "onecore\\base\\servicing\\util\\servici"...
0x1802049ec  mov     [rsp+150h+var_E8], rax
0x1802049f1  lea     rax, aGetfilecontent; "GetFileContents"
0x1802049f8  mov     [rsp+150h+var_E0], rax
0x1802049fd  mov     qword ptr [rsp+78h], 4Ah ; 'J'
0x180204a06  lea     rax, aTemperr; "__tempErr"
0x180204a0d  mov     [rbp+50h+var_D0], rax
0x180204a11  jle     short loc_180204A18
0x180204a13  movzx   ebx, bx
0x180204a16  or      ebx, edi
0x180204a18  mov     r8d, ebx
0x180204a1b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180204a22  lea     rcx, [rsp+150h+var_E8]
0x180204a27  call    RtlReportErrorOrigination
0x180204a2c  nop
0x180204a2d  lea     rax, [rsi-1]
0x180204a31  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180204a35  ja      short loc_180204A51
0x180204a37  mov     rcx, rsi; Handle
0x180204a3a  call    cs:__imp_NtClose
0x180204a41  nop     dword ptr [rax+rax+00h]
0x180204a46  test    eax, eax
0x180204a48  jns     short loc_180204A51
0x180204a4a  mov     ecx, 7
0x180204a4f  int     29h; Win8: RtlFailFast(ecx)
0x180204a51  mov     eax, ebx
0x180204a53  jmp     loc_180204E62
0x180204a58  mov     qword ptr [rbp+50h+FileSize], 0
0x180204a60  lea     rdx, [rbp+50h+FileSize]; lpFileSize
0x180204a64  mov     rcx, rsi; hFile
0x180204a67  call    cs:__imp_GetFileSizeEx
0x180204a6e  nop     dword ptr [rax+rax+00h]
0x180204a73  test    eax, eax
0x180204a75  jnz     loc_180204B5A
0x180204a7b  call    cs:__imp_GetLastError
0x180204a82  nop     dword ptr [rax+rax+00h]
0x180204a87  mov     ebx, eax
0x180204a89  mov     edi, 80070000h
0x180204a8e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180204a95  test    rcx, rcx
0x180204a98  jz      short loc_180204AEF
0x180204a9a  lea     rax, [rbp+50h+lpFileName]
0x180204a9e  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180204aa3  lea     r9, aCouldNotQueryF; "Could not query file size for {0}"
0x180204aaa  mov     r8d, r12d
0x180204aad  xor     edx, edx
0x180204aaf  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x180204ab4  test    ebx, ebx
0x180204ab6  jg      short loc_180204ABC
0x180204ab8  mov     eax, ebx
0x180204aba  jmp     short loc_180204AC1
0x180204abc  movzx   eax, bx
0x180204abf  or      eax, edi
0x180204ac1  mov     [rbp+50h+var_38], eax
0x180204ac4  lea     rax, [rbp+50h+var_38]
0x180204ac8  mov     qword ptr [rsp+150h+var_110], rax
0x180204acd  lea     rax, [rsp+150h+var_110]
0x180204ad2  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180204ad7  lea     r9, a0; ": {0}"
0x180204ade  mov     r8d, r12d
0x180204ae1  mov     dl, 1
0x180204ae3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180204aea  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180204aef  test    ebx, ebx
0x180204af1  jz      loc_180204E86
0x180204af7  lea     rax, aOnecoreBaseSer_32; "onecore\\base\\servicing\\util\\servici"...
0x180204afe  mov     [rbp+50h+var_C8], rax
0x180204b02  lea     rax, aGetfilecontent; "GetFileContents"
0x180204b09  mov     [rbp+50h+var_C0], rax
0x180204b0d  mov     [rbp+50h+var_B8], 4Eh ; 'N'
0x180204b15  lea     rax, aTemperr; "__tempErr"
0x180204b1c  mov     [rbp+50h+var_B0], rax
0x180204b20  jle     short loc_180204B27
0x180204b22  movzx   ebx, bx
0x180204b25  or      ebx, edi
0x180204b27  mov     r8d, ebx
0x180204b2a  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180204b31  lea     rcx, [rbp+50h+var_C8]
0x180204b35  call    RtlReportErrorOrigination
0x180204b3a  nop
0x180204b3b  mov     rcx, rsi; Handle
0x180204b3e  call    cs:__imp_NtClose
0x180204b45  nop     dword ptr [rax+rax+00h]
0x180204b4a  test    eax, eax
0x180204b4c  jns     short loc_180204B55
0x180204b4e  mov     ecx, 7
0x180204b53  int     29h; Win8: RtlFailFast(ecx)
0x180204b55  jmp     loc_180204A51
0x180204b5a  mov     eax, 0FFFFFFFFh
0x180204b5f  mov     rbx, qword ptr [rbp+50h+FileSize]
0x180204b63  cmp     rbx, rax
0x180204b66  jle     loc_180204C24
0x180204b6c  mov     ebx, 800700DFh
0x180204b71  mov     [rbp+50h+var_38], ebx
0x180204b74  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180204b7b  test    rcx, rcx
0x180204b7e  jz      short loc_180204BC5
0x180204b80  lea     rax, [rbp+50h+lpFileName]
0x180204b84  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180204b89  lea     r9, aFileTooLarge0; "File too large {0}"
0x180204b90  mov     r8d, r12d
0x180204b93  xor     edx, edx
0x180204b95  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x180204b9a  lea     rax, [rbp+50h+var_38]
0x180204b9e  mov     qword ptr [rsp+150h+var_110], rax
0x180204ba3  lea     rax, [rsp+150h+var_110]
0x180204ba8  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180204bad  lea     r9, asc_1802C6678; ": {}"
0x180204bb4  mov     r8d, r12d
0x180204bb7  mov     dl, 1
0x180204bb9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180204bc0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180204bc5  lea     rax, aOnecoreBaseSer_32; "onecore\\base\\servicing\\util\\servici"...
0x180204bcc  mov     [rbp+50h+var_A8], rax
0x180204bd0  lea     rax, aGetfilecontent; "GetFileContents"
0x180204bd7  mov     [rbp+50h+var_A0], rax
0x180204bdb  mov     [rbp+50h+var_98], 52h ; 'R'
0x180204be3  lea     rax, aTempe; "__tempE"
0x180204bea  mov     [rbp+50h+var_90], rax
0x180204bee  mov     r8d, 800700DFh
0x180204bf4  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180204bfb  lea     rcx, [rbp+50h+var_A8]
0x180204bff  call    RtlReportErrorOrigination
0x180204c04  nop
0x180204c05  mov     rcx, rsi; Handle
0x180204c08  call    cs:__imp_NtClose
0x180204c0f  nop     dword ptr [rax+rax+00h]
0x180204c14  test    eax, eax
0x180204c16  jns     short loc_180204C1F
0x180204c18  mov     ecx, 7
0x180204c1d  int     29h; Win8: RtlFailFast(ecx)
0x180204c1f  jmp     loc_180204A51
0x180204c24  xorps   xmm0, xmm0
0x180204c27  xor     eax, eax
0x180204c29  movups  [rsp+150h+var_110+8], xmm0
0x180204c2e  mov     [rsp+150h+lpBuffer], rax
0x180204c33  mov     r14d, ebx
0x180204c36  lea     rdx, [rsp+150h+var_110+8]
0x180204c3b  mov     ecx, ebx
0x180204c3d  call    RtlAllocateLBlob
0x180204c42  test    eax, eax
0x180204c44  jns     short loc_180204C79
0x180204c46  mov     ecx, eax; Status
0x180204c48  call    ConvertNtStatusToHResult
0x180204c4d  mov     ebx, eax
0x180204c4f  lea     rcx, [rsp+150h+var_110+8]
0x180204c54  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180204c59  nop
0x180204c5a  mov     rcx, rsi; Handle
0x180204c5d  call    cs:__imp_NtClose
0x180204c64  nop     dword ptr [rax+rax+00h]
0x180204c69  test    eax, eax
0x180204c6b  jns     short loc_180204C74
0x180204c6d  mov     ecx, 7
0x180204c72  int     29h; Win8: RtlFailFast(ecx)
0x180204c74  jmp     loc_180204A51
0x180204c79  mov     [rbp+50h+NumberOfBytesRead], 0
0x180204c80  mov     qword ptr [rsp+150h+dwCreationDisposition], 0; lpOverlapped
0x180204c89  lea     r9, [rbp+50h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180204c8d  mov     r8d, ebx; nNumberOfBytesToRead
0x180204c90  mov     rdx, [rsp+150h+lpBuffer]; lpBuffer
0x180204c95  mov     rcx, rsi; hFile
0x180204c98  call    cs:__imp_ReadFile
0x180204c9f  nop     dword ptr [rax+rax+00h]
0x180204ca4  test    eax, eax
0x180204ca6  jnz     loc_180204D98
0x180204cac  call    cs:__imp_GetLastError
0x180204cb3  nop     dword ptr [rax+rax+00h]
0x180204cb8  mov     ebx, eax
0x180204cba  mov     edi, 80070000h
0x180204cbf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180204cc6  test    rcx, rcx
0x180204cc9  jz      short loc_180204D20
0x180204ccb  lea     rax, [rbp+50h+lpFileName]
0x180204ccf  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180204cd4  lea     r9, aFailedToReadFi; "Failed to read file {0}"
0x180204cdb  mov     r8d, r12d
0x180204cde  xor     edx, edx
0x180204ce0  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x180204ce5  test    ebx, ebx
0x180204ce7  jg      short loc_180204CED
0x180204ce9  mov     eax, ebx
0x180204ceb  jmp     short loc_180204CF2
0x180204ced  movzx   eax, bx
0x180204cf0  or      eax, edi
0x180204cf2  mov     [rbp+50h+var_38], eax
0x180204cf5  lea     rax, [rbp+50h+var_38]
0x180204cf9  mov     qword ptr [rsp+150h+var_110], rax
0x180204cfe  lea     rax, [rsp+150h+var_110]
0x180204d03  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180204d08  lea     r9, a0; ": {0}"
0x180204d0f  mov     r8d, r12d
0x180204d12  mov     dl, 1
0x180204d14  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180204d1b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180204d20  test    ebx, ebx
0x180204d22  jz      loc_180204E86
0x180204d28  lea     rax, aOnecoreBaseSer_32; "onecore\\base\\servicing\\util\\servici"...
0x180204d2f  mov     [rbp+50h+var_88], rax
0x180204d33  lea     rax, aGetfilecontent; "GetFileContents"
0x180204d3a  mov     [rbp+50h+var_80], rax
0x180204d3e  mov     [rbp+50h+var_78], 5Bh ; '['
0x180204d46  lea     rax, aTemperr; "__tempErr"
0x180204d4d  mov     [rbp+50h+var_70], rax
0x180204d51  test    ebx, ebx
0x180204d53  jle     short loc_180204D5A
0x180204d55  movzx   ebx, bx
0x180204d58  or      ebx, edi
  ... truncated ...
```
