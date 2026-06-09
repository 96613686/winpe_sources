# CreateFileWithRetries

- ea: `0x18004afd8`
- end: `0x18004b2dc`
- name: `CreateFileWithRetries`
- size: `772`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180044c90`
- `0x18004add8`

## callees

- `0x18001e51c`
- `0x1800293a0`
- `0x18003d7d4`
- `0x180041a74`
- `0x180041de8`
- `0x180043380`
- `0x180043c00`
- `0x18004689c`
- `0x18004afd8`
- `0x18006cbdc`
- `0x18006d0a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004b22b`
- `KERNEL32!GetLastError` at `0x18004b22b`
- `KERNEL32!CreateFileW` at `0x18004b1fd`
- `KERNEL32!CreateFileW` at `0x18004b1fd`
- `KERNEL32!Sleep` at `0x18004b218`
- `KERNEL32!Sleep` at `0x18004b218`

## string_xrefs

- `0x18004b035`: `No file path specified`
- `0x18004b189`: `Failed calling GetSystemSecurity`
- `0x18004b249`: `Failed to create file: {}`

## pseudocode

```c
int __fastcall CreateFileWithRetries(
        const WCHAR *a1,
        bool *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        _QWORD *a8)
{
  unsigned int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v12; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v14; // rdx
  unsigned int v15; // edi
  int v16; // edx
  __int64 v17; // rdx
  int SystemSecurity; // eax
  int v19; // edx
  unsigned int i; // edi
  HANDLE v21; // rax
  int v22; // edx
  signed int LastError; // edi
  int v24; // r8d
  __int64 v25; // rdx
  unsigned int v26; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  _BYTE v29[8]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v30[2]; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-30h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-28h] BYREF
  void *v33; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  lpFileName = a1;
  v33 = 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_OWORD *)&SecurityAttributes.lpSecurityDescriptor = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    LODWORD(v33) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file path specified");
      *(_QWORD *)v30 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v30);
    }
    v10 = 1357;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v8,
      dwCreationDisposition);
    return v8;
  }
  if ( !a8 )
  {
    v8 = -2147467261;
    LODWORD(v33) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file handle result specified");
      *(_QWORD *)v30 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v30);
    }
    v10 = 1358;
    goto LABEL_5;
  }
  v29[0] = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner((Windows::WCP::Implementation::Rtl *)v29, a2);
  v15 = CanSetSystemOwner;
  if ( CanSetSystemOwner < 0 )
  {
    LODWORD(v33) = CanSetSystemOwner;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling CanSetSystemOwner");
      *(_QWORD *)v30 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)v30);
    }
    v17 = 1374;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v17,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
             (const char *)v15,
             dwCreationDisposition);
  }
  if ( v29[0] )
  {
    SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                       (Windows::WCP::Implementation::Rtl *)&v33,
                       v14);
    v15 = SystemSecurity;
    if ( SystemSecurity < 0 )
    {
      LODWORD(v33) = SystemSecurity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling GetSystemSecurity");
        *(_QWORD *)v30 = &v33;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v19,
          3,
          (unsigned int)": {}",
          (__int64)v30);
      }
      v17 = 1380;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v17,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)v15,
               dwCreationDisposition);
    }
    SecurityAttributes.lpSecurityDescriptor = v33;
  }
  for ( i = 0; i < 3; ++i )
  {
    v21 = CreateFileW(lpFileName, 0x40000001u, 0, &SecurityAttributes, 2u, 0x2000080u, 0);
    if ( v21 != (HANDLE)-1LL )
    {
      *a8 = v21;
      return 0;
    }
    Sleep(0x3E8u);
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      v22,
      v24,
      (unsigned int)"Failed to create file: {}",
      (__int64)&lpFileName);
    if ( LastError > 0 )
      v26 = (unsigned __int16)LastError | 0x80070000;
    else
      v26 = LastError;
    LODWORD(v33) = v26;
    *(_QWORD *)v30 = &v33;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v25,
      3,
      (__int64)": {0}",
      (__int64)v30);
  }
  if ( LastError )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x580,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
             (const char *)(unsigned int)LastError,
             dwCreationDispositiona);
  return 0;
}

```

## disassembly

```asm
0x18004afd8  mov     [rsp-8+arg_8], rsi
0x18004afdd  mov     [rsp-8+arg_10], rdi
0x18004afe2  push    rbp
0x18004afe3  mov     rbp, rsp
0x18004afe6  sub     rsp, 80h
0x18004afed  mov     rax, cs:__security_cookie
0x18004aff4  xor     rax, rsp
0x18004aff7  mov     [rbp+var_8], rax
0x18004affb  mov     rsi, [rbp+arg_38]
0x18004afff  xorps   xmm0, xmm0
0x18004b002  mov     [rbp+lpFileName], rcx
0x18004b006  mov     [rbp+var_10], 0
0x18004b00e  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x18004b016  movups  xmmword ptr [rbp+SecurityAttributes.lpSecurityDescriptor], xmm0
0x18004b01a  test    rcx, rcx
0x18004b01d  jnz     short loc_18004B08E
0x18004b01f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b026  mov     edi, 80070057h
0x18004b02b  mov     dword ptr [rbp+var_10], edi
0x18004b02e  test    rcx, rcx
0x18004b031  jz      short loc_18004B06F
0x18004b033  xor     edx, edx
0x18004b035  lea     r9, aNoFilePathSpec; "No file path specified"
0x18004b03c  lea     r8d, [rdx+3]
0x18004b040  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004b045  lea     rcx, [rbp+var_38]
0x18004b049  mov     r8d, 3
0x18004b04f  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx; int
0x18004b054  lea     rax, [rbp+var_10]
0x18004b058  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b05f  lea     r9, asc_1800AFB70; ": {}"
0x18004b066  mov     qword ptr [rbp+var_38], rax
0x18004b06a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004b06f  mov     edx, 54Dh; void *
0x18004b074  mov     rcx, [rbp+8]; this
0x18004b078  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004b07f  mov     r9d, edi; char *
0x18004b082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b087  mov     eax, edi
0x18004b089  jmp     loc_18004B2BA
0x18004b08e  test    rsi, rsi
0x18004b091  jnz     short loc_18004B0E8
0x18004b093  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b09a  mov     edi, 80004003h
0x18004b09f  mov     dword ptr [rbp+var_10], edi
0x18004b0a2  test    rcx, rcx
0x18004b0a5  jz      short loc_18004B0E1
0x18004b0a7  lea     r9, aNoFileHandleRe; "No file handle result specified"
0x18004b0ae  xor     edx, edx
0x18004b0b0  lea     r8d, [rsi+3]
0x18004b0b4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004b0b9  lea     rcx, [rbp+var_38]
0x18004b0bd  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x18004b0c2  lea     rax, [rbp+var_10]
0x18004b0c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b0cd  lea     r9, asc_1800AFB70; ": {}"
0x18004b0d4  lea     r8d, [rsi+3]
0x18004b0d8  mov     qword ptr [rbp+var_38], rax
0x18004b0dc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004b0e1  mov     edx, 54Eh; bool *
0x18004b0e6  jmp     short loc_18004B074
0x18004b0e8  lea     rcx, [rbp+var_40]; this
0x18004b0ec  mov     [rbp+var_40], 0
0x18004b0f0  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x18004b0f5  mov     edi, eax
0x18004b0f7  test    eax, eax
0x18004b0f9  jns     short loc_18004B163
0x18004b0fb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b102  mov     dword ptr [rbp+var_10], eax
0x18004b105  test    rcx, rcx
0x18004b108  jz      short loc_18004B146
0x18004b10a  xor     edx, edx
0x18004b10c  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x18004b113  lea     r8d, [rdx+3]
0x18004b117  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004b11c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b123  lea     rax, [rbp+var_10]
0x18004b127  mov     qword ptr [rbp+var_38], rax
0x18004b12b  lea     r9, asc_1800AFB70; ": {}"
0x18004b132  lea     rax, [rbp+var_38]
0x18004b136  mov     r8d, 3
0x18004b13c  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x18004b141  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18004b146  mov     edx, 55Eh; void *
0x18004b14b  mov     rcx, [rbp+8]; this
0x18004b14f  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004b156  mov     r9d, edi; char *
0x18004b159  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004b15e  jmp     loc_18004B2BA
0x18004b163  cmp     [rbp+var_40], 0
0x18004b167  jz      short loc_18004B1D2
0x18004b169  lea     rcx, [rbp+var_10]; this
0x18004b16d  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x18004b172  mov     edi, eax
0x18004b174  test    eax, eax
0x18004b176  jns     short loc_18004B1CA
0x18004b178  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b17f  mov     dword ptr [rbp+var_10], eax
0x18004b182  test    rcx, rcx
0x18004b185  jz      short loc_18004B1C3
0x18004b187  xor     edx, edx
0x18004b189  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x18004b190  lea     r8d, [rdx+3]
0x18004b194  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004b199  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b1a0  lea     rax, [rbp+var_10]
0x18004b1a4  mov     qword ptr [rbp+var_38], rax
0x18004b1a8  lea     r9, asc_1800AFB70; ": {}"
0x18004b1af  lea     rax, [rbp+var_38]
0x18004b1b3  mov     r8d, 3
0x18004b1b9  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x18004b1be  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18004b1c3  mov     edx, 564h
0x18004b1c8  jmp     short loc_18004B14B
0x18004b1ca  mov     rax, [rbp+var_10]
0x18004b1ce  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18004b1d2  xor     edi, edi
0x18004b1d4  mov     rcx, [rbp+lpFileName]; lpFileName
0x18004b1d8  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x18004b1dc  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18004b1e5  xor     r8d, r8d; dwShareMode
0x18004b1e8  mov     [rsp+80h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18004b1f0  mov     edx, 40000001h; dwDesiredAccess
0x18004b1f5  mov     [rsp+80h+dwCreationDisposition], 2; dwCreationDisposition
0x18004b1fd  call    cs:__imp_CreateFileW
0x18004b204  nop     dword ptr [rax+rax+00h]
0x18004b209  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004b20d  jnz     loc_18004B2B5
0x18004b213  mov     ecx, 3E8h; dwMilliseconds
0x18004b218  call    cs:__imp_Sleep
0x18004b21f  nop     dword ptr [rax+rax+00h]
0x18004b224  inc     edi
0x18004b226  cmp     edi, 3
0x18004b229  jb      short loc_18004B1D4
0x18004b22b  call    cs:__imp_GetLastError
0x18004b232  nop     dword ptr [rax+rax+00h]
0x18004b237  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b23e  mov     edi, eax
0x18004b240  test    rcx, rcx
0x18004b243  jz      short loc_18004B297
0x18004b245  lea     rax, [rbp+lpFileName]
0x18004b249  lea     r9, aFailedToCreate_0; "Failed to create file: {}"
0x18004b250  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x18004b255  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004b25a  test    edi, edi
0x18004b25c  jg      short loc_18004B262
0x18004b25e  mov     eax, edi
0x18004b260  jmp     short loc_18004B26A
0x18004b262  movzx   eax, di
0x18004b265  or      eax, 80070000h
0x18004b26a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b271  lea     r9, a0; ": {0}"
0x18004b278  mov     dword ptr [rbp+var_10], eax
0x18004b27b  mov     r8d, 3
0x18004b281  lea     rax, [rbp+var_10]
0x18004b285  mov     qword ptr [rbp+var_38], rax
0x18004b289  lea     rax, [rbp+var_38]
0x18004b28d  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; unsigned int
0x18004b292  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004b297  test    edi, edi
0x18004b299  jz      short loc_18004B2B8
0x18004b29b  mov     rcx, [rbp+8]; this
0x18004b29f  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004b2a6  mov     r9d, edi; char *
0x18004b2a9  mov     edx, 580h; void *
0x18004b2ae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b2b3  jmp     short loc_18004B2BA
0x18004b2b5  mov     [rsi], rax
0x18004b2b8  xor     eax, eax
0x18004b2ba  mov     rcx, [rbp+var_8]
0x18004b2be  xor     rcx, rsp; StackCookie
0x18004b2c1  call    __security_check_cookie
0x18004b2c6  lea     r11, [rsp+80h+var_s0]
0x18004b2ce  mov     rsi, [r11+18h]
0x18004b2d2  mov     rdi, [r11+20h]
0x18004b2d6  mov     rsp, r11
0x18004b2d9  pop     rbp
0x18004b2da  retn
```
