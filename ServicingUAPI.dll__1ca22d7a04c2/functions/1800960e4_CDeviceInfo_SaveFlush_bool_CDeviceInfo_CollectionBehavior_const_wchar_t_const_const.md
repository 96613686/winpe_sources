# CDeviceInfo::SaveFlush(bool,CDeviceInfo::CollectionBehavior const &,wchar_t const * const)

- ea: `0x1800960e4`
- end: `0x1800964bb`
- name: `?SaveFlush@CDeviceInfo@@AEAAJ_NAEBUCollectionBehavior@1@QEB_W@Z`
- size: `983`
- prototype: `__int64 __fastcall(CDeviceInfo *__hidden this, bool, const struct CDeviceInfo::CollectionBehavior *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180095138`

## callees

- `0x1800031d0`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x18001b0a4`
- `0x180022a18`
- `0x1800296a4`
- `0x18004d970`
- `0x1800960e4`
- `0x1801bd010`

## import_xrefs

- `ntdll!NtClose` at `0x1800962a9`
- `ntdll!NtClose` at `0x1800962e3`
- `ntdll!NtClose` at `0x1800963cc`
- `ntdll!NtClose` at `0x1800963fa`
- `ntdll!NtClose` at `0x18009646e`
- `ntdll!NtClose` at `0x1800962a9`
- `ntdll!NtClose` at `0x1800962e3`
- `ntdll!NtClose` at `0x1800963cc`
- `ntdll!NtClose` at `0x1800963fa`
- `ntdll!NtClose` at `0x18009646e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096336`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180096322`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180096322`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800961e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800961e7`

## string_xrefs

- `0x180096359`: `Failed to write device info file: {0}`
- `0x18009622c`: `Failed to create device info file: {0}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDeviceInfo::SaveFlush(
        CDeviceInfo *this,
        __int64 a2,
        const struct CDeviceInfo::CollectionBehavior *a3,
        const WCHAR *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // ebx
  char *FileW; // rbx
  signed int v11; // esi
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // edi
  LPCVOID v15; // rcx
  signed int LastError; // esi
  __int64 v17; // rdx
  unsigned int v18; // eax
  void (__fastcall ***v19)(_QWORD); // rcx
  void (__fastcall ***v20)(_QWORD); // rcx
  void (__fastcall ***v21)(_QWORD); // rcx
  unsigned int *dwCreationDisposition; // [rsp+28h] [rbp-29h]
  unsigned int *dwCreationDispositiona; // [rsp+28h] [rbp-29h]
  unsigned int *dwCreationDispositionb; // [rsp+28h] [rbp-29h]
  unsigned int v25[2]; // [rsp+48h] [rbp-9h] BYREF
  char *v26; // [rsp+50h] [rbp-1h]
  __int64 v27; // [rsp+58h] [rbp+7h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp+Fh] BYREF
  unsigned int v29; // [rsp+68h] [rbp+17h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+6Ch] [rbp+1Bh] BYREF
  DWORD nNumberOfBytesToWrite[4]; // [rsp+70h] [rbp+1Fh] BYREF
  LPCVOID lpBuffer; // [rsp+80h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  v27 = -2;
  lpFileName = a4;
  *(_OWORD *)nNumberOfBytesToWrite = 0;
  lpBuffer = 0;
  v26 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, DWORD *))(**((_QWORD **)this + 5) + 16LL))(
         *((_QWORD *)this + 5),
         0,
         nNumberOfBytesToWrite);
  v6 = v5;
  if ( v5 >= 0 )
  {
    FileW = (char *)CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v26 = FileW;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      NumberOfBytesWritten = 0;
      if ( WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite[0], &NumberOfBytesWritten, 0) )
      {
        v19 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 7);
        if ( v19 )
        {
          *((_QWORD *)this + 7) = 0;
          (**v19)(v19);
        }
        v20 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 6);
        if ( v20 )
        {
          *((_QWORD *)this + 6) = 0;
          (**v20)(v20);
        }
        v21 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 5);
        if ( v21 )
        {
          *((_QWORD *)this + 5) = 0;
          (**v21)(v21);
        }
        if ( NtClose(FileW) < 0 )
          __fastfail(7u);
        v15 = lpBuffer;
        if ( !lpBuffer )
          return 0;
        goto LABEL_48;
      }
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to write device info file: {0}",
          &lpFileName);
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        else
          v18 = LastError;
        v29 = v18;
        *(_QWORD *)v25 = &v29;
        dwCreationDispositionb = v25;
        LOBYTE(v17) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v17,
          3,
          ": {0}");
      }
      if ( LastError )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x14F9,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
                (const char *)(unsigned int)LastError,
                (unsigned int)dwCreationDispositionb);
        if ( NtClose(FileW) < 0 )
          __fastfail(7u);
        if ( lpBuffer )
          anonymous_namespace_::OurRtlFreeStringRoutine(lpBuffer);
        return v14;
      }
      if ( NtClose(FileW) < 0 )
        __fastfail(7u);
    }
    else
    {
      v11 = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to create device info file: {0}",
          &lpFileName);
        if ( v11 > 0 )
          v13 = (unsigned __int16)v11 | 0x80070000;
        else
          v13 = v11;
        v29 = v13;
        *(_QWORD *)v25 = &v29;
        dwCreationDispositiona = v25;
        LOBYTE(v12) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v12,
          3,
          ": {0}");
      }
      if ( v11 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x14F4,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
                (const char *)(unsigned int)v11,
                (unsigned int)dwCreationDispositiona);
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
          __fastfail(7u);
        if ( lpBuffer )
          anonymous_namespace_::OurRtlFreeStringRoutine(lpBuffer);
        return v14;
      }
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
        __fastfail(7u);
    }
    v15 = lpBuffer;
LABEL_48:
    if ( v15 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v15);
    return 0;
  }
  v29 = v5;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get data out of builder.");
    *(_QWORD *)v25 = &v29;
    dwCreationDisposition = v25;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v7,
      3,
      ": {}");
  }
  v8 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x14F1,
         (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
         (const char *)v6,
         (int)dwCreationDisposition);
  if ( lpBuffer )
    anonymous_namespace_::OurRtlFreeStringRoutine(lpBuffer);
  return v8;
}

```

## disassembly

```asm
0x1800960e4  mov     rax, rsp
0x1800960e7  push    rbp
0x1800960e8  push    rsi
0x1800960e9  push    rdi
0x1800960ea  lea     rbp, [rax-5Fh]
0x1800960ee  sub     rsp, 90h
0x1800960f5  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1800960fd  mov     [rax+10h], rbx
0x180096101  mov     rax, cs:__security_cookie
0x180096108  xor     rax, rsp
0x18009610b  mov     [rbp+57h+var_20], rax
0x18009610f  mov     rdi, rcx
0x180096112  mov     [rbp+57h+lpFileName], r9
0x180096116  xorps   xmm0, xmm0
0x180096119  xor     eax, eax
0x18009611b  movups  xmmword ptr [rbp+57h+nNumberOfBytesToWrite], xmm0
0x18009611f  mov     [rbp+57h+lpBuffer], rax
0x180096123  mov     [rbp+57h+var_58], rax
0x180096127  mov     rcx, [rcx+28h]
0x18009612b  mov     rax, [rcx]
0x18009612e  lea     r8, [rbp+57h+nNumberOfBytesToWrite]
0x180096132  xor     edx, edx
0x180096134  mov     rax, [rax+10h]
0x180096138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009613d  mov     ebx, eax
0x18009613f  test    eax, eax
0x180096141  jns     short loc_1800961BF
0x180096143  mov     [rbp+57h+var_40], eax
0x180096146  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009614d  test    rcx, rcx
0x180096150  jz      short loc_18009618F
0x180096152  lea     r9, aFailedToGetDat; "Failed to get data out of builder."
0x180096159  mov     edi, 3
0x18009615e  mov     r8d, edi
0x180096161  xor     edx, edx
0x180096163  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180096168  lea     rax, [rbp+57h+var_40]
0x18009616c  mov     qword ptr [rbp+57h+var_60], rax
0x180096170  lea     rax, [rbp+57h+var_60]
0x180096174  mov     [rsp+0A0h+dwCreationDisposition], rax; int
0x180096179  lea     r9, asc_1801CAFB4; ": {}"
0x180096180  mov     r8d, edi
0x180096183  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009618a  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18009618f  mov     rcx, [rbp+5Fh]; this
0x180096193  mov     r9d, ebx; char *
0x180096196  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x18009619d  mov     edx, 14F1h; void *
0x1800961a2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800961a7  mov     ebx, eax
0x1800961a9  mov     rcx, [rbp+57h+lpBuffer]
0x1800961ad  test    rcx, rcx
0x1800961b0  jz      short loc_1800961B8
0x1800961b2  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800961b7  nop
0x1800961b8  mov     eax, ebx
0x1800961ba  jmp     loc_18009649B
0x1800961bf  mov     qword ptr [rsp+30h], 0; hTemplateFile
0x1800961c8  mov     [rsp+0A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800961d0  mov     dword ptr [rsp+0A0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800961d8  xor     r9d, r9d; lpSecurityAttributes
0x1800961db  xor     r8d, r8d; dwShareMode
0x1800961de  mov     edx, 40000000h; dwDesiredAccess
0x1800961e3  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800961e7  call    cs:__imp_CreateFileW
0x1800961ee  nop     dword ptr [rax+rax+00h]
0x1800961f3  mov     rbx, rax
0x1800961f6  mov     [rbp+57h+var_58], rax
0x1800961fa  inc     rax
0x1800961fd  test    rax, 0FFFFFFFFFFFFFFFEh
0x180096203  jnz     loc_180096303
0x180096209  call    cs:__imp_GetLastError
0x180096210  nop     dword ptr [rax+rax+00h]
0x180096215  mov     esi, eax
0x180096217  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009621e  test    rcx, rcx
0x180096221  jz      short loc_18009627E
0x180096223  lea     rax, [rbp+57h+lpFileName]
0x180096227  mov     [rsp+0A0h+dwCreationDisposition], rax
0x18009622c  lea     r9, aFailedToCreate; "Failed to create device info file: {0}"
0x180096233  mov     edi, 3
0x180096238  mov     r8d, edi
0x18009623b  xor     edx, edx
0x18009623d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180096242  test    esi, esi
0x180096244  jg      short loc_18009624A
0x180096246  mov     eax, esi
0x180096248  jmp     short loc_180096252
0x18009624a  movzx   eax, si
0x18009624d  or      eax, 80070000h
0x180096252  mov     [rbp+57h+var_40], eax
0x180096255  lea     rax, [rbp+57h+var_40]
0x180096259  mov     qword ptr [rbp+57h+var_60], rax
0x18009625d  lea     rax, [rbp+57h+var_60]
0x180096261  mov     [rsp+0A0h+dwCreationDisposition], rax; unsigned int
0x180096266  lea     r9, a0; ": {0}"
0x18009626d  mov     r8d, edi
0x180096270  mov     dl, 1
0x180096272  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180096279  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009627e  test    esi, esi
0x180096280  jz      short loc_1800962D6
0x180096282  mov     rcx, [rbp+5Fh]; this
0x180096286  mov     r9d, esi; char *
0x180096289  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x180096290  mov     edx, 14F4h; void *
0x180096295  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009629a  mov     edi, eax
0x18009629c  lea     rcx, [rbx-1]
0x1800962a0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800962a4  ja      short loc_1800962C0
0x1800962a6  mov     rcx, rbx; Handle
0x1800962a9  call    cs:__imp_NtClose
0x1800962b0  nop     dword ptr [rax+rax+00h]
0x1800962b5  test    eax, eax
0x1800962b7  jns     short loc_1800962C0
0x1800962b9  mov     ecx, 7
0x1800962be  int     29h; Win8: RtlFailFast(ecx)
0x1800962c0  mov     rcx, [rbp+57h+lpBuffer]
0x1800962c4  test    rcx, rcx
0x1800962c7  jz      short loc_1800962CF
0x1800962c9  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800962ce  nop
0x1800962cf  mov     eax, edi
0x1800962d1  jmp     loc_18009649B
0x1800962d6  lea     rax, [rbx-1]
0x1800962da  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800962de  ja      short loc_1800962FA
0x1800962e0  mov     rcx, rbx; Handle
0x1800962e3  call    cs:__imp_NtClose
0x1800962ea  nop     dword ptr [rax+rax+00h]
0x1800962ef  test    eax, eax
0x1800962f1  jns     short loc_1800962FA
0x1800962f3  mov     ecx, 7
0x1800962f8  int     29h; Win8: RtlFailFast(ecx)
0x1800962fa  mov     rcx, [rbp+57h+lpBuffer]
0x1800962fe  jmp     loc_18009648E
0x180096303  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18009630a  mov     [rsp+0A0h+dwCreationDisposition], 0; lpOverlapped
0x180096313  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180096317  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18009631b  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x18009631f  mov     rcx, rbx; hFile
0x180096322  call    cs:__imp_WriteFile
0x180096329  nop     dword ptr [rax+rax+00h]
0x18009632e  test    eax, eax
0x180096330  jnz     loc_180096416
0x180096336  call    cs:__imp_GetLastError
0x18009633d  nop     dword ptr [rax+rax+00h]
0x180096342  mov     esi, eax
0x180096344  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009634b  test    rcx, rcx
0x18009634e  jz      short loc_1800963AB
0x180096350  lea     rax, [rbp+57h+lpFileName]
0x180096354  mov     [rsp+0A0h+dwCreationDisposition], rax
0x180096359  lea     r9, aFailedToWriteD_0; "Failed to write device info file: {0}"
0x180096360  mov     edi, 3
0x180096365  mov     r8d, edi
0x180096368  xor     edx, edx
0x18009636a  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18009636f  test    esi, esi
0x180096371  jg      short loc_180096377
0x180096373  mov     eax, esi
0x180096375  jmp     short loc_18009637F
0x180096377  movzx   eax, si
0x18009637a  or      eax, 80070000h
0x18009637f  mov     [rbp+57h+var_40], eax
0x180096382  lea     rax, [rbp+57h+var_40]
0x180096386  mov     qword ptr [rbp+57h+var_60], rax
0x18009638a  lea     rax, [rbp+57h+var_60]
0x18009638e  mov     [rsp+0A0h+dwCreationDisposition], rax; unsigned int
0x180096393  lea     r9, a0; ": {0}"
0x18009639a  mov     r8d, edi
0x18009639d  mov     dl, 1
0x18009639f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800963a6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800963ab  test    esi, esi
0x1800963ad  jz      short loc_1800963F7
0x1800963af  mov     rcx, [rbp+5Fh]; this
0x1800963b3  mov     r9d, esi; char *
0x1800963b6  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800963bd  mov     edx, 14F9h; void *
0x1800963c2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800963c7  mov     edi, eax
0x1800963c9  mov     rcx, rbx; Handle
0x1800963cc  call    cs:__imp_NtClose
0x1800963d3  nop     dword ptr [rax+rax+00h]
0x1800963d8  test    eax, eax
0x1800963da  jns     short loc_1800963E3
0x1800963dc  mov     ecx, 7
0x1800963e1  int     29h; Win8: RtlFailFast(ecx)
0x1800963e3  mov     rcx, [rbp+57h+lpBuffer]
0x1800963e7  test    rcx, rcx
0x1800963ea  jz      short loc_1800963F2
0x1800963ec  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800963f1  nop
0x1800963f2  jmp     loc_1800962CF
0x1800963f7  mov     rcx, rbx; Handle
0x1800963fa  call    cs:__imp_NtClose
0x180096401  nop     dword ptr [rax+rax+00h]
0x180096406  test    eax, eax
0x180096408  jns     short loc_180096411
0x18009640a  mov     ecx, 7
0x18009640f  int     29h; Win8: RtlFailFast(ecx)
0x180096411  jmp     loc_1800962FA
0x180096416  mov     rcx, [rdi+38h]
0x18009641a  test    rcx, rcx
0x18009641d  jz      short loc_180096432
0x18009641f  mov     qword ptr [rdi+38h], 0
0x180096427  mov     rax, [rcx]
0x18009642a  mov     rax, [rax]
0x18009642d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096432  mov     rcx, [rdi+30h]
0x180096436  test    rcx, rcx
0x180096439  jz      short loc_18009644E
0x18009643b  mov     qword ptr [rdi+30h], 0
0x180096443  mov     rax, [rcx]
0x180096446  mov     rax, [rax]
0x180096449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009644e  mov     rcx, [rdi+28h]
0x180096452  test    rcx, rcx
0x180096455  jz      short loc_18009646B
0x180096457  mov     qword ptr [rdi+28h], 0
0x18009645f  mov     rax, [rcx]
0x180096462  mov     rax, [rax]
0x180096465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009646a  nop
0x18009646b  mov     rcx, rbx; Handle
0x18009646e  call    cs:__imp_NtClose
0x180096475  nop     dword ptr [rax+rax+00h]
0x18009647a  test    eax, eax
0x18009647c  jns     short loc_180096485
0x18009647e  mov     ecx, 7
0x180096483  int     29h; Win8: RtlFailFast(ecx)
0x180096485  mov     rcx, [rbp+57h+lpBuffer]
0x180096489  test    rcx, rcx
0x18009648c  jz      short loc_180096499
0x18009648e  test    rcx, rcx
0x180096491  jz      short loc_180096499
0x180096493  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180096498  nop
0x180096499  xor     eax, eax
0x18009649b  mov     rcx, [rbp+57h+var_20]
0x18009649f  xor     rcx, rsp; StackCookie
0x1800964a2  call    __security_check_cookie
0x1800964a7  mov     rbx, [rsp+0A0h+arg_8]
0x1800964af  add     rsp, 90h
0x1800964b6  pop     rdi
0x1800964b7  pop     rsi
0x1800964b8  pop     rbp
0x1800964b9  retn
```
