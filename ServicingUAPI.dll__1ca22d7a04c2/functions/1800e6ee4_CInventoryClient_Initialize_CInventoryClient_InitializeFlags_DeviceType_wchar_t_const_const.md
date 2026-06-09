# CInventoryClient::Initialize(CInventoryClient::InitializeFlags,DeviceType,wchar_t const * const)

- ea: `0x1800e6ee4`
- end: `0x1800e75f1`
- name: `?Initialize@CInventoryClient@@QEAAJW4InitializeFlags@1@W4DeviceType@@QEB_W@Z`
- size: `1805`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008aff4`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x180009750`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x18001b0a4`
- `0x18001d650`
- `0x180022a18`
- `0x1800296a4`
- `0x18002fda0`
- `0x18003ddc8`
- `0x180042764`
- `0x18004d970`
- `0x180050fd0`
- `0x180067014`
- `0x18009e7f0`
- `0x1800e6c90`
- `0x1800e6ee4`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e722c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e732d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e722c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e732d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e7318`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e7318`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800e7209`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800e7209`

## string_xrefs

- `0x1800e6fc4`: `Invalid windir path: {}`
- `0x1800e7246`: `Failed to load AppXDeviceInventory DLL`
- `0x1800e709f`: `Failed to get path to AppXDeviceInventory.dll`
- `0x1800e7073`: `AppXDeviceInventory.dll`
- `0x1800e7520`: `Cannot create DeviceInventoryCreator session`
- `0x1800e7449`: `Failed to load DllGetClassObject`
- `0x1800e7347`: `Failed to get proc address for DllGetClassObject.`
- `0x1800e730e`: `DllGetClassObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CInventoryClient::Initialize(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rax
  int Win32PathOfSiblingFile; // eax
  __int64 v13; // rdx
  __int64 v14; // rbx
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  unsigned int v19; // edi
  HMODULE Library; // rax
  signed int LastError; // esi
  __int64 v22; // rdx
  unsigned int v23; // eax
  FARPROC ProcAddress; // rax
  signed int v25; // esi
  __int64 v26; // rdx
  unsigned int v27; // eax
  int v28; // eax
  unsigned int v29; // esi
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  unsigned int *v33; // [rsp+28h] [rbp-69h]
  unsigned int v34[2]; // [rsp+38h] [rbp-59h] BYREF
  __int128 v35; // [rsp+40h] [rbp-51h] BYREF
  __int64 v36; // [rsp+50h] [rbp-41h]
  _QWORD v37[4]; // [rsp+58h] [rbp-39h] BYREF
  __int128 v38; // [rsp+78h] [rbp-19h] BYREF
  __int64 v39; // [rsp+88h] [rbp-9h]
  __int64 v40; // [rsp+90h] [rbp-1h]
  __int64 v41; // [rsp+98h] [rbp+7h] BYREF
  __int64 v42; // [rsp+A0h] [rbp+Fh] BYREF
  unsigned int v43; // [rsp+A8h] [rbp+17h] BYREF
  LPCWSTR lpLibFileName; // [rsp+B0h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v40 = -2;
  v41 = a4;
  lpLibFileName = 0;
  v35 = 0;
  v36 = 0;
  v42 = 0;
  if ( a3 != 1 )
    return 0;
  if ( a4 )
  {
    v38 = 0;
    v39 = 0;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a4 + 2 * v6) );
    v37[0] = 2 * v6;
    v37[1] = 2 * v6 + 2;
    v37[2] = a4;
    v7 = Windows::StringUtil::Rtl::SplitWin32Path<_LUNICODE_STRING>(v37, &v38, 0);
    v8 = v7;
    if ( v7 < 0 )
    {
      v43 = v7;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Invalid windir path: {}",
          &v41);
        *(_QWORD *)v34 = &v43;
        v33 = v34;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v9,
          3,
          ": {}");
      }
      v10 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cappxclient.cpp",
              (const char *)v8,
              (int)v33);
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        v42 = 0;
      }
LABEL_11:
      if ( lpLibFileName )
        operator delete((void *)(lpLibFileName - 4));
      return v10;
    }
    v11 = to_wstring(v37, &v38);
    std::wstring::operator=(a1 + 24, v11);
    std::wstring::~wstring(v37);
  }
  Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(byte_18023FAC5, L"AppXDeviceInventory.dll", &v35);
  v10 = Win32PathOfSiblingFile;
  if ( Win32PathOfSiblingFile < 0 )
  {
    v43 = Win32PathOfSiblingFile;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get path to AppXDeviceInventory.dll");
      *(_QWORD *)v34 = &v43;
      v33 = v34;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v13,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cappxclient.cpp",
      (const char *)v10,
      (int)v33);
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
    }
    if ( v36 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v36);
    goto LABEL_11;
  }
  v14 = v36;
  v15 = SczAllocFromSz(&lpLibFileName);
  v19 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cappxclient.cpp",
      (const char *)(unsigned int)v15,
      (int)v33);
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
    }
    if ( v14 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
LABEL_28:
    if ( lpLibFileName )
      operator delete((void *)(lpLibFileName - 4));
    return v19;
  }
  if ( *(_QWORD *)&LogAdapter::g_Logger )
    LogAdapter::Logger::LogNumObjects<wchar_t [23],AutoScz>(LogAdapter::g_Logger, v16, v17, v18);
  if ( !(unsigned int)DoesFileExist(lpLibFileName) )
  {
    LogAdapter::TraceAtLevelHr<long,AutoScz>(1, 2147942402LL, "File [{0}] doesn't exist", &lpLibFileName);
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
    }
    if ( v14 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
    goto LABEL_98;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 8u);
  if ( *(_QWORD *)(a1 + 8) )
    goto LABEL_100;
  *(_QWORD *)(a1 + 8) = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to load AppXDeviceInventory DLL");
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      else
        v23 = LastError;
      v43 = v23;
      *(_QWORD *)v34 = &v43;
      v33 = v34;
      LOBYTE(v22) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v22,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cappxclient.cpp",
              (const char *)(unsigned int)LastError,
              (unsigned int)v33);
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        v42 = 0;
      }
      if ( v14 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v14);
      goto LABEL_28;
    }
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
    }
    if ( v14 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
LABEL_98:
    if ( lpLibFileName )
      operator delete((void *)(lpLibFileName - 4));
    return 0;
  }
  ProcAddress = GetProcAddress(Library, "DllGetClassObject");
  if ( !ProcAddress )
  {
    v25 = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get proc address for DllGetClassObject.");
      if ( v25 > 0 )
        v27 = (unsigned __int16)v25 | 0x80070000;
      else
        v27 = v25;
      v43 = v27;
      *(_QWORD *)v34 = &v43;
      v33 = v34;
      LOBYTE(v26) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v26,
        3,
        ": {0}");
    }
    if ( v25 )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xBF,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cappxclient.cpp",
              (const char *)(unsigned int)v25,
              (unsigned int)v33);
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        v42 = 0;
      }
      if ( v14 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v14);
      goto LABEL_28;
    }
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
    }
    if ( v14 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
    goto LABEL_98;
  }
  if ( v42 )
    goto LABEL_100;
  v28 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
          &GUID_fb86ef7a_4b0d_4cff_8536_5f56b79a6f76,
          &GUID_00000001_0000_0000_c000_000000000046,
          &v42);
  v29 = v28;
  if ( v28 < 0 )
  {
    v43 = v28;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to load DllGetClassObject");
      *(_QWORD *)v34 = &v43;
      v33 = v34;
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v30,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cappxclient.cpp",
      (const char *)v29,
      (int)v33);
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
    }
    if ( v14 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
    goto LABEL_82;
  }
  if ( *(_QWORD *)(a1 + 16) )
  {
LABEL_100:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1800E75F0LL);
  }
  v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *))(*(_QWORD *)v42 + 24LL))(
          v42,
          0,
          &GUID_fb86ef7a_4b0d_4cff_8536_5f56b79a6f76);
  v29 = v31;
  if ( v31 >= 0 )
  {
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
    }
    if ( v14 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
    goto LABEL_98;
  }
  v43 = v31;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Cannot create DeviceInventoryCreator session");
    *(_QWORD *)v34 = &v43;
    v33 = v34;
    LOBYTE(v32) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v32,
      3,
      ": {}");
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCA,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\cappxclient.cpp",
    (const char *)v29,
    (int)v33);
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v14 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v14);
LABEL_82:
  if ( lpLibFileName )
    operator delete((void *)(lpLibFileName - 4));
  return v29;
}

```

## disassembly

```asm
0x1800e6ee4  mov     rax, rsp
0x1800e6ee7  push    rbp
0x1800e6ee8  push    rsi
0x1800e6ee9  push    rdi
0x1800e6eea  push    r14
0x1800e6eec  push    r15
0x1800e6eee  lea     rbp, [rax-5Fh]
0x1800e6ef2  sub     rsp, 0C0h
0x1800e6ef9  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800e6f01  mov     [rax+10h], rbx
0x1800e6f05  mov     rax, cs:__security_cookie
0x1800e6f0c  xor     rax, rsp
0x1800e6f0f  mov     [rbp+57h+var_30], rax
0x1800e6f13  mov     r14, rcx
0x1800e6f16  mov     [rbp+57h+var_50], r9
0x1800e6f1a  xor     r15d, r15d
0x1800e6f1d  mov     [rbp+57h+lpLibFileName], r15
0x1800e6f21  xorps   xmm0, xmm0
0x1800e6f24  xor     esi, esi
0x1800e6f26  movups  [rbp+57h+var_A8], xmm0
0x1800e6f2a  mov     [rbp+57h+var_98], rsi
0x1800e6f2e  mov     [rbp+57h+var_48], r15
0x1800e6f32  cmp     r8d, 1
0x1800e6f36  jz      short loc_1800E6F5E
0x1800e6f38  xor     eax, eax
0x1800e6f3a  mov     rcx, [rbp+57h+var_30]
0x1800e6f3e  xor     rcx, rsp; StackCookie
0x1800e6f41  call    __security_check_cookie
0x1800e6f46  mov     rbx, [rsp+0E0h+arg_8]
0x1800e6f4e  add     rsp, 0C0h
0x1800e6f55  pop     r15
0x1800e6f57  pop     r14
0x1800e6f59  pop     rdi
0x1800e6f5a  pop     rsi
0x1800e6f5b  pop     rbp
0x1800e6f5c  retn
0x1800e6f5e  test    r9, r9
0x1800e6f61  jz      loc_1800E706F
0x1800e6f67  xor     eax, eax
0x1800e6f69  movups  [rbp+57h+var_70], xmm0
0x1800e6f6d  mov     [rbp+57h+var_60], rax
0x1800e6f71  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e6f75  inc     rax
0x1800e6f78  cmp     [r9+rax*2], r15w
0x1800e6f7d  jnz     short loc_1800E6F75
0x1800e6f7f  add     rax, rax
0x1800e6f82  lea     rcx, [rax+2]
0x1800e6f86  mov     [rbp+57h+var_90], rax
0x1800e6f8a  mov     [rbp+57h+var_88], rcx
0x1800e6f8e  mov     [rbp+57h+var_80], r9
0x1800e6f92  xor     r8d, r8d
0x1800e6f95  lea     rdx, [rbp+57h+var_70]
0x1800e6f99  lea     rcx, [rbp+57h+var_90]
0x1800e6f9d  call    ??$SplitWin32Path@U_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAU3@1@Z; Windows::StringUtil::Rtl::SplitWin32Path<_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING *,_LUNICODE_STRING *)
0x1800e6fa2  mov     ebx, eax
0x1800e6fa4  test    eax, eax
0x1800e6fa6  jns     loc_1800E704D
0x1800e6fac  mov     [rbp+57h+var_40], eax
0x1800e6faf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e6fb6  test    rcx, rcx
0x1800e6fb9  jz      short loc_1800E7001
0x1800e6fbb  lea     rax, [rbp+57h+var_50]
0x1800e6fbf  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800e6fc4  lea     r9, aInvalidWindirP; "Invalid windir path: {}"
0x1800e6fcb  mov     edi, 3
0x1800e6fd0  mov     r8d, edi
0x1800e6fd3  xor     edx, edx
0x1800e6fd5  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800e6fda  lea     rax, [rbp+57h+var_40]
0x1800e6fde  mov     qword ptr [rbp+57h+var_B0], rax
0x1800e6fe2  lea     rax, [rbp+57h+var_B0]
0x1800e6fe6  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800e6feb  lea     r9, asc_1801CAFB4; ": {}"
0x1800e6ff2  mov     r8d, edi
0x1800e6ff5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e6ffc  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1800e7001  mov     rcx, [rbp+5Fh]; this
0x1800e7005  mov     r9d, ebx; char *
0x1800e7008  lea     r8, aOnecoreBaseSer_18; "onecore\\base\\servicing\\arbiter\\capp"...
0x1800e700f  mov     edx, 0A1h; void *
0x1800e7014  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800e7019  mov     ebx, eax
0x1800e701b  mov     rcx, [rbp+57h+var_48]
0x1800e701f  test    rcx, rcx
0x1800e7022  jz      short loc_1800E7034
0x1800e7024  mov     rdx, [rcx]
0x1800e7027  mov     rax, [rdx+10h]
0x1800e702b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7030  mov     [rbp+57h+var_48], r15
0x1800e7034  mov     rcx, [rbp+57h+lpLibFileName]
0x1800e7038  test    rcx, rcx
0x1800e703b  jz      short loc_1800E7046
0x1800e703d  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800e7041  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e7046  mov     eax, ebx
0x1800e7048  jmp     loc_1800E6F3A
0x1800e704d  lea     rdx, [rbp+57h+var_70]
0x1800e7051  lea     rcx, [rbp+57h+var_90]
0x1800e7055  call    ?to_wstring@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_LUNICODE_STRING@@@Z; to_wstring(_LUNICODE_STRING const &)
0x1800e705a  lea     rcx, [r14+18h]
0x1800e705e  mov     rdx, rax
0x1800e7061  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e7066  lea     rcx, [rbp+57h+var_90]; void *
0x1800e706a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e706f  lea     r8, [rbp+57h+var_A8]
0x1800e7073  lea     rdx, aAppxdeviceinve; "AppXDeviceInventory.dll"
0x1800e707a  lea     rcx, byte_18023FAC5
0x1800e7081  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x1800e7086  mov     ebx, eax
0x1800e7088  test    eax, eax
0x1800e708a  jns     loc_1800E7124
0x1800e7090  mov     [rbp+57h+var_40], eax
0x1800e7093  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e709a  test    rcx, rcx
0x1800e709d  jz      short loc_1800E70DE
0x1800e709f  lea     r9, aFailedToGetPat; "Failed to get path to AppXDeviceInvento"...
0x1800e70a6  mov     edi, 3
0x1800e70ab  mov     r8d, edi
0x1800e70ae  xor     edx, edx
0x1800e70b0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e70b5  lea     rax, [rbp+57h+var_40]
0x1800e70b9  mov     qword ptr [rbp+57h+var_B0], rax
0x1800e70bd  lea     rax, [rbp+57h+var_B0]
0x1800e70c1  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800e70c6  lea     r9, asc_1801CAFB4; ": {}"
0x1800e70cd  mov     r8d, edi
0x1800e70d0  mov     dl, 1
0x1800e70d2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e70d9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e70de  mov     rcx, [rbp+5Fh]; this
0x1800e70e2  mov     r9d, ebx; char *
0x1800e70e5  lea     r8, aOnecoreBaseSer_18; "onecore\\base\\servicing\\arbiter\\capp"...
0x1800e70ec  mov     edx, 0AEh; void *
0x1800e70f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e70f6  nop
0x1800e70f7  mov     rcx, [rbp+57h+var_48]
0x1800e70fb  test    rcx, rcx
0x1800e70fe  jz      short loc_1800E7110
0x1800e7100  mov     rax, [rcx]
0x1800e7103  mov     rax, [rax+10h]
0x1800e7107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e710c  mov     [rbp+57h+var_48], r15
0x1800e7110  mov     rcx, [rbp+57h+var_98]
0x1800e7114  test    rcx, rcx
0x1800e7117  jz      short loc_1800E711F
0x1800e7119  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e711e  nop
0x1800e711f  jmp     loc_1800E7034
0x1800e7124  mov     rbx, [rbp+57h+var_98]
0x1800e7128  mov     rdx, rbx
0x1800e712b  lea     rcx, [rbp+57h+lpLibFileName]
0x1800e712f  call    SczAllocFromSz
0x1800e7134  mov     edi, eax
0x1800e7136  test    eax, eax
0x1800e7138  jns     short loc_1800E7193
0x1800e713a  mov     rcx, [rbp+5Fh]; this
0x1800e713e  mov     r9d, eax; char *
0x1800e7141  lea     r8, aOnecoreBaseSer_18; "onecore\\base\\servicing\\arbiter\\capp"...
0x1800e7148  mov     edx, 0B0h; void *
0x1800e714d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7152  nop
0x1800e7153  mov     rcx, [rbp+57h+var_48]
0x1800e7157  test    rcx, rcx
0x1800e715a  jz      short loc_1800E716C
0x1800e715c  mov     rax, [rcx]
0x1800e715f  mov     rax, [rax+10h]
0x1800e7163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7168  mov     [rbp+57h+var_48], r15
0x1800e716c  test    rbx, rbx
0x1800e716f  jz      short loc_1800E717A
0x1800e7171  mov     rcx, rbx
0x1800e7174  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e7179  nop
0x1800e717a  mov     rcx, [rbp+57h+lpLibFileName]
0x1800e717e  test    rcx, rcx
0x1800e7181  jz      short loc_1800E718C
0x1800e7183  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800e7187  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e718c  mov     eax, edi
0x1800e718e  jmp     loc_1800E6F3A
0x1800e7193  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e719a  test    rcx, rcx
0x1800e719d  jz      short loc_1800E71AD
0x1800e719f  lea     rax, [rbp+57h+lpLibFileName]
0x1800e71a3  mov     [rsp+28h], rax
0x1800e71a8  call    ??$LogNumObjects@$$BY0BH@_WVAutoScz@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEAY0BH@$$CB_WAEBVAutoScz@@@Z; LogAdapter::Logger::LogNumObjects<wchar_t [23],AutoScz>(bool,LogAdapter::LogLevel,char const * const,wchar_t const (&)[23],AutoScz const &)
0x1800e71ad  mov     rcx, [rbp+57h+lpLibFileName]
0x1800e71b1  call    DoesFileExist
0x1800e71b6  test    eax, eax
0x1800e71b8  jnz     short loc_1800E71FF
0x1800e71ba  lea     r9, [rbp+57h+lpLibFileName]
0x1800e71be  lea     r8, aFile0DoesnTExi; "File [{0}] doesn't exist"
0x1800e71c5  mov     edx, 80070002h
0x1800e71ca  lea     ecx, [rax+1]
0x1800e71cd  call    ??$TraceAtLevelHr@JVAutoScz@@@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBVAutoScz@@@Z; LogAdapter::TraceAtLevelHr<long,AutoScz>(LogAdapter::LogLevel,long,char const * const,AutoScz const &)
0x1800e71d2  nop
0x1800e71d3  mov     rcx, [rbp+57h+var_48]
0x1800e71d7  test    rcx, rcx
0x1800e71da  jz      short loc_1800E71EC
0x1800e71dc  mov     rax, [rcx]
0x1800e71df  mov     rax, [rax+10h]
0x1800e71e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e71e8  mov     [rbp+57h+var_48], r15
0x1800e71ec  test    rbx, rbx
0x1800e71ef  jz      short loc_1800E71FA
0x1800e71f1  mov     rcx, rbx
0x1800e71f4  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e71f9  nop
0x1800e71fa  jmp     loc_1800E75CB
0x1800e71ff  xor     edx, edx; hFile
0x1800e7201  lea     r8d, [rdx+8]; dwFlags
0x1800e7205  mov     rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x1800e7209  call    cs:__imp_LoadLibraryExW
0x1800e7210  nop     dword ptr [rax+rax+00h]
0x1800e7215  cmp     [r14+8], r15
0x1800e7219  jnz     loc_1800E75E6
0x1800e721f  mov     [r14+8], rax
0x1800e7223  test    rax, rax
0x1800e7226  jnz     loc_1800E730E
0x1800e722c  call    cs:__imp_GetLastError
0x1800e7233  nop     dword ptr [rax+rax+00h]
0x1800e7238  mov     esi, eax
0x1800e723a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e7241  test    rcx, rcx
0x1800e7244  jz      short loc_1800E7298
0x1800e7246  lea     r9, aFailedToLoadAp; "Failed to load AppXDeviceInventory DLL"
0x1800e724d  mov     edi, 3
0x1800e7252  mov     r8d, edi
0x1800e7255  xor     edx, edx
0x1800e7257  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e725c  test    esi, esi
0x1800e725e  jg      short loc_1800E7264
0x1800e7260  mov     eax, esi
0x1800e7262  jmp     short loc_1800E726C
0x1800e7264  movzx   eax, si
0x1800e7267  or      eax, 80070000h
0x1800e726c  mov     [rbp+57h+var_40], eax
0x1800e726f  lea     rax, [rbp+57h+var_40]
0x1800e7273  mov     qword ptr [rbp+57h+var_B0], rax
0x1800e7277  lea     rax, [rbp+57h+var_B0]
0x1800e727b  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x1800e7280  lea     r9, a0; ": {0}"
0x1800e7287  mov     r8d, edi
0x1800e728a  mov     dl, 1
0x1800e728c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e7293  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e7298  test    esi, esi
0x1800e729a  jz      short loc_1800E72E2
0x1800e729c  mov     rcx, [rbp+5Fh]; this
0x1800e72a0  mov     r9d, esi; char *
0x1800e72a3  lea     r8, aOnecoreBaseSer_18; "onecore\\base\\servicing\\arbiter\\capp"...
0x1800e72aa  mov     edx, 0BAh; void *
0x1800e72af  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e72b4  mov     edi, eax
0x1800e72b6  mov     rcx, [rbp+57h+var_48]
0x1800e72ba  test    rcx, rcx
0x1800e72bd  jz      short loc_1800E72CF
0x1800e72bf  mov     rdx, [rcx]
0x1800e72c2  mov     rax, [rdx+10h]
0x1800e72c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e72cb  mov     [rbp+57h+var_48], r15
0x1800e72cf  test    rbx, rbx
0x1800e72d2  jz      short loc_1800E72DD
0x1800e72d4  mov     rcx, rbx
0x1800e72d7  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e72dc  nop
0x1800e72dd  jmp     loc_1800E717A
0x1800e72e2  mov     rcx, [rbp+57h+var_48]
0x1800e72e6  test    rcx, rcx
0x1800e72e9  jz      short loc_1800E72FB
0x1800e72eb  mov     rax, [rcx]
0x1800e72ee  mov     rax, [rax+10h]
0x1800e72f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e72f7  mov     [rbp+57h+var_48], r15
0x1800e72fb  test    rbx, rbx
0x1800e72fe  jz      short loc_1800E7309
0x1800e7300  mov     rcx, rbx
0x1800e7303  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e7308  nop
0x1800e7309  jmp     loc_1800E75CB
0x1800e730e  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x1800e7315  mov     rcx, rax; hModule
0x1800e7318  call    cs:__imp_GetProcAddress
0x1800e731f  nop     dword ptr [rax+rax+00h]
0x1800e7324  test    rax, rax
0x1800e7327  jnz     loc_1800E740F
0x1800e732d  call    cs:__imp_GetLastError
0x1800e7334  nop     dword ptr [rax+rax+00h]
0x1800e7339  mov     esi, eax
0x1800e733b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e7342  test    rcx, rcx
0x1800e7345  jz      short loc_1800E7399
0x1800e7347  lea     r9, aFailedToGetPro_4; "Failed to get proc address for DllGetCl"...
0x1800e734e  mov     edi, 3
0x1800e7353  mov     r8d, edi
0x1800e7356  xor     edx, edx
0x1800e7358  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e735d  test    esi, esi
0x1800e735f  jg      short loc_1800E7365
0x1800e7361  mov     eax, esi
  ... truncated ...
```
