# CDeviceInfo::SaveFlush(bool,CDeviceInfo::CollectionBehavior const &,wchar_t const * const)

- ea: `0x1800e0048`
- end: `0x1800e041f`
- name: `?SaveFlush@CDeviceInfo@@AEAAJ_NAEBUCollectionBehavior@1@QEB_W@Z`
- size: `983`
- prototype: `__int64 __fastcall(CDeviceInfo *__hidden this, bool, const struct CDeviceInfo::CollectionBehavior *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x1800df09c`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18008b3bc`
- `0x18008b3ec`
- `0x1800bd064`
- `0x1800e0048`
- `0x1801f250c`
- `0x1802b1010`

## import_xrefs

- `ntdll!NtClose` at `0x1800e020d`
- `ntdll!NtClose` at `0x1800e0247`
- `ntdll!NtClose` at `0x1800e0330`
- `ntdll!NtClose` at `0x1800e035e`
- `ntdll!NtClose` at `0x1800e03d2`
- `ntdll!NtClose` at `0x1800e020d`
- `ntdll!NtClose` at `0x1800e0247`
- `ntdll!NtClose` at `0x1800e0330`
- `ntdll!NtClose` at `0x1800e035e`
- `ntdll!NtClose` at `0x1800e03d2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e0286`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e0286`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e014b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e014b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e016d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e029a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e016d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e029a`

## string_xrefs

- `0x1800e0190`: `Failed to create device info file: {0}`
- `0x1800e02bd`: `Failed to write device info file: {0}`

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
  unsigned int v12; // eax
  unsigned int v13; // edi
  LPCVOID v14; // rcx
  signed int LastError; // esi
  unsigned int v16; // eax
  void (__fastcall ***v17)(_QWORD); // rcx
  void (__fastcall ***v18)(_QWORD); // rcx
  void (__fastcall ***v19)(_QWORD); // rcx
  DWORD dwCreationDisposition; // [rsp+28h] [rbp-29h]
  DWORD dwCreationDispositiona; // [rsp+28h] [rbp-29h]
  DWORD dwCreationDispositionb; // [rsp+28h] [rbp-29h]
  unsigned int v23[2]; // [rsp+48h] [rbp-9h] BYREF
  char *v24; // [rsp+50h] [rbp-1h]
  __int64 v25; // [rsp+58h] [rbp+7h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp+Fh] BYREF
  unsigned int v27; // [rsp+68h] [rbp+17h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+6Ch] [rbp+1Bh] BYREF
  DWORD nNumberOfBytesToWrite[4]; // [rsp+70h] [rbp+1Fh] BYREF
  LPCVOID lpBuffer; // [rsp+80h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  v25 = -2;
  lpFileName = a4;
  *(_OWORD *)nNumberOfBytesToWrite = 0;
  lpBuffer = 0;
  v24 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, DWORD *))(**((_QWORD **)this + 5) + 16LL))(
         *((_QWORD *)this + 5),
         0,
         nNumberOfBytesToWrite);
  v6 = v5;
  if ( v5 >= 0 )
  {
    FileW = (char *)CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v24 = FileW;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      NumberOfBytesWritten = 0;
      if ( WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite[0], &NumberOfBytesWritten, 0) )
      {
        v17 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 7);
        if ( v17 )
        {
          *((_QWORD *)this + 7) = 0;
          (**v17)(v17);
        }
        v18 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 6);
        if ( v18 )
        {
          *((_QWORD *)this + 6) = 0;
          (**v18)(v18);
        }
        v19 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 5);
        if ( v19 )
        {
          *((_QWORD *)this + 5) = 0;
          (**v19)(v19);
        }
        if ( NtClose(FileW) < 0 )
          __fastfail(7u);
        v14 = lpBuffer;
        if ( !lpBuffer )
          return 0;
        goto LABEL_48;
      }
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to write device info file: {0}",
          (__int64)&lpFileName);
        if ( LastError > 0 )
          v16 = (unsigned __int16)LastError | 0x80070000;
        else
          v16 = LastError;
        v27 = v16;
        *(_QWORD *)v23 = &v27;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)v23);
      }
      if ( LastError )
      {
        v13 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x14F9,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
                (const char *)(unsigned int)LastError,
                dwCreationDispositionb);
        if ( NtClose(FileW) < 0 )
          __fastfail(7u);
        if ( lpBuffer )
          anonymous_namespace_::OurRtlFreeStringRoutine(lpBuffer);
        return v13;
      }
      if ( NtClose(FileW) < 0 )
        __fastfail(7u);
    }
    else
    {
      v11 = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create device info file: {0}",
          (__int64)&lpFileName);
        if ( v11 > 0 )
          v12 = (unsigned __int16)v11 | 0x80070000;
        else
          v12 = v11;
        v27 = v12;
        *(_QWORD *)v23 = &v27;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)v23);
      }
      if ( v11 )
      {
        v13 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x14F4,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
                (const char *)(unsigned int)v11,
                dwCreationDispositiona);
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
          __fastfail(7u);
        if ( lpBuffer )
          anonymous_namespace_::OurRtlFreeStringRoutine(lpBuffer);
        return v13;
      }
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
        __fastfail(7u);
    }
    v14 = lpBuffer;
LABEL_48:
    if ( v14 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
    return 0;
  }
  v27 = v5;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(__int64 *)&LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get data out of builder.");
    *(_QWORD *)v23 = &v27;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      v7,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
      (__int64)v23);
  }
  v8 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x14F1,
         (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
         (const char *)v6,
         dwCreationDisposition);
  if ( lpBuffer )
    anonymous_namespace_::OurRtlFreeStringRoutine(lpBuffer);
  return v8;
}

```

## disassembly

```asm
0x1800e0048  mov     rax, rsp
0x1800e004b  push    rbp
0x1800e004c  push    rsi
0x1800e004d  push    rdi
0x1800e004e  lea     rbp, [rax-5Fh]
0x1800e0052  sub     rsp, 90h
0x1800e0059  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1800e0061  mov     [rax+10h], rbx
0x1800e0065  mov     rax, cs:__security_cookie
0x1800e006c  xor     rax, rsp
0x1800e006f  mov     [rbp+57h+var_20], rax
0x1800e0073  mov     rdi, rcx
0x1800e0076  mov     [rbp+57h+lpFileName], r9
0x1800e007a  xorps   xmm0, xmm0
0x1800e007d  xor     eax, eax
0x1800e007f  movups  xmmword ptr [rbp+57h+nNumberOfBytesToWrite], xmm0
0x1800e0083  mov     [rbp+57h+lpBuffer], rax
0x1800e0087  mov     [rbp+57h+var_58], rax
0x1800e008b  mov     rcx, [rcx+28h]
0x1800e008f  mov     rax, [rcx]
0x1800e0092  lea     r8, [rbp+57h+nNumberOfBytesToWrite]
0x1800e0096  xor     edx, edx
0x1800e0098  mov     rax, [rax+10h]
0x1800e009c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e00a1  mov     ebx, eax
0x1800e00a3  test    eax, eax
0x1800e00a5  jns     short loc_1800E0123
0x1800e00a7  mov     [rbp+57h+var_40], eax
0x1800e00aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e00b1  test    rcx, rcx
0x1800e00b4  jz      short loc_1800E00F3
0x1800e00b6  lea     r9, aFailedToGetDat; "Failed to get data out of builder."
0x1800e00bd  mov     edi, 3
0x1800e00c2  mov     r8d, edi
0x1800e00c5  xor     edx, edx
0x1800e00c7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e00cc  lea     rax, [rbp+57h+var_40]
0x1800e00d0  mov     qword ptr [rbp+57h+var_60], rax
0x1800e00d4  lea     rax, [rbp+57h+var_60]
0x1800e00d8  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax; int
0x1800e00dd  lea     r9, asc_1802C6678; ": {}"
0x1800e00e4  mov     r8d, edi
0x1800e00e7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e00ee  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1800e00f3  mov     rcx, [rbp+5Fh]; this
0x1800e00f7  mov     r9d, ebx; char *
0x1800e00fa  lea     r8, aOnecoreBaseSer_7; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800e0101  mov     edx, 14F1h; void *
0x1800e0106  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800e010b  mov     ebx, eax
0x1800e010d  mov     rcx, [rbp+57h+lpBuffer]
0x1800e0111  test    rcx, rcx
0x1800e0114  jz      short loc_1800E011C
0x1800e0116  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e011b  nop
0x1800e011c  mov     eax, ebx
0x1800e011e  jmp     loc_1800E03FF
0x1800e0123  mov     qword ptr [rsp+30h], 0; hTemplateFile
0x1800e012c  mov     [rsp+0A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e0134  mov     [rsp+0A0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800e013c  xor     r9d, r9d; lpSecurityAttributes
0x1800e013f  xor     r8d, r8d; dwShareMode
0x1800e0142  mov     edx, 40000000h; dwDesiredAccess
0x1800e0147  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800e014b  call    cs:__imp_CreateFileW
0x1800e0152  nop     dword ptr [rax+rax+00h]
0x1800e0157  mov     rbx, rax
0x1800e015a  mov     [rbp+57h+var_58], rax
0x1800e015e  inc     rax
0x1800e0161  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e0167  jnz     loc_1800E0267
0x1800e016d  call    cs:__imp_GetLastError
0x1800e0174  nop     dword ptr [rax+rax+00h]
0x1800e0179  mov     esi, eax
0x1800e017b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e0182  test    rcx, rcx
0x1800e0185  jz      short loc_1800E01E2
0x1800e0187  lea     rax, [rbp+57h+lpFileName]
0x1800e018b  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax
0x1800e0190  lea     r9, aFailedToCreate; "Failed to create device info file: {0}"
0x1800e0197  mov     edi, 3
0x1800e019c  mov     r8d, edi
0x1800e019f  xor     edx, edx
0x1800e01a1  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x1800e01a6  test    esi, esi
0x1800e01a8  jg      short loc_1800E01AE
0x1800e01aa  mov     eax, esi
0x1800e01ac  jmp     short loc_1800E01B6
0x1800e01ae  movzx   eax, si
0x1800e01b1  or      eax, 80070000h
0x1800e01b6  mov     [rbp+57h+var_40], eax
0x1800e01b9  lea     rax, [rbp+57h+var_40]
0x1800e01bd  mov     qword ptr [rbp+57h+var_60], rax
0x1800e01c1  lea     rax, [rbp+57h+var_60]
0x1800e01c5  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax; unsigned int
0x1800e01ca  lea     r9, a0; ": {0}"
0x1800e01d1  mov     r8d, edi
0x1800e01d4  mov     dl, 1
0x1800e01d6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e01dd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e01e2  test    esi, esi
0x1800e01e4  jz      short loc_1800E023A
0x1800e01e6  mov     rcx, [rbp+5Fh]; this
0x1800e01ea  mov     r9d, esi; char *
0x1800e01ed  lea     r8, aOnecoreBaseSer_7; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800e01f4  mov     edx, 14F4h; void *
0x1800e01f9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e01fe  mov     edi, eax
0x1800e0200  lea     rcx, [rbx-1]
0x1800e0204  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800e0208  ja      short loc_1800E0224
0x1800e020a  mov     rcx, rbx; Handle
0x1800e020d  call    cs:__imp_NtClose
0x1800e0214  nop     dword ptr [rax+rax+00h]
0x1800e0219  test    eax, eax
0x1800e021b  jns     short loc_1800E0224
0x1800e021d  mov     ecx, 7
0x1800e0222  int     29h; Win8: RtlFailFast(ecx)
0x1800e0224  mov     rcx, [rbp+57h+lpBuffer]
0x1800e0228  test    rcx, rcx
0x1800e022b  jz      short loc_1800E0233
0x1800e022d  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e0232  nop
0x1800e0233  mov     eax, edi
0x1800e0235  jmp     loc_1800E03FF
0x1800e023a  lea     rax, [rbx-1]
0x1800e023e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e0242  ja      short loc_1800E025E
0x1800e0244  mov     rcx, rbx; Handle
0x1800e0247  call    cs:__imp_NtClose
0x1800e024e  nop     dword ptr [rax+rax+00h]
0x1800e0253  test    eax, eax
0x1800e0255  jns     short loc_1800E025E
0x1800e0257  mov     ecx, 7
0x1800e025c  int     29h; Win8: RtlFailFast(ecx)
0x1800e025e  mov     rcx, [rbp+57h+lpBuffer]
0x1800e0262  jmp     loc_1800E03F2
0x1800e0267  mov     [rbp+57h+NumberOfBytesWritten], 0
0x1800e026e  mov     qword ptr [rsp+0A0h+dwCreationDisposition], 0; lpOverlapped
0x1800e0277  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800e027b  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800e027f  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1800e0283  mov     rcx, rbx; hFile
0x1800e0286  call    cs:__imp_WriteFile
0x1800e028d  nop     dword ptr [rax+rax+00h]
0x1800e0292  test    eax, eax
0x1800e0294  jnz     loc_1800E037A
0x1800e029a  call    cs:__imp_GetLastError
0x1800e02a1  nop     dword ptr [rax+rax+00h]
0x1800e02a6  mov     esi, eax
0x1800e02a8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e02af  test    rcx, rcx
0x1800e02b2  jz      short loc_1800E030F
0x1800e02b4  lea     rax, [rbp+57h+lpFileName]
0x1800e02b8  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax
0x1800e02bd  lea     r9, aFailedToWriteD_0; "Failed to write device info file: {0}"
0x1800e02c4  mov     edi, 3
0x1800e02c9  mov     r8d, edi
0x1800e02cc  xor     edx, edx
0x1800e02ce  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x1800e02d3  test    esi, esi
0x1800e02d5  jg      short loc_1800E02DB
0x1800e02d7  mov     eax, esi
0x1800e02d9  jmp     short loc_1800E02E3
0x1800e02db  movzx   eax, si
0x1800e02de  or      eax, 80070000h
0x1800e02e3  mov     [rbp+57h+var_40], eax
0x1800e02e6  lea     rax, [rbp+57h+var_40]
0x1800e02ea  mov     qword ptr [rbp+57h+var_60], rax
0x1800e02ee  lea     rax, [rbp+57h+var_60]
0x1800e02f2  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax; unsigned int
0x1800e02f7  lea     r9, a0; ": {0}"
0x1800e02fe  mov     r8d, edi
0x1800e0301  mov     dl, 1
0x1800e0303  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e030a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e030f  test    esi, esi
0x1800e0311  jz      short loc_1800E035B
0x1800e0313  mov     rcx, [rbp+5Fh]; this
0x1800e0317  mov     r9d, esi; char *
0x1800e031a  lea     r8, aOnecoreBaseSer_7; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800e0321  mov     edx, 14F9h; void *
0x1800e0326  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e032b  mov     edi, eax
0x1800e032d  mov     rcx, rbx; Handle
0x1800e0330  call    cs:__imp_NtClose
0x1800e0337  nop     dword ptr [rax+rax+00h]
0x1800e033c  test    eax, eax
0x1800e033e  jns     short loc_1800E0347
0x1800e0340  mov     ecx, 7
0x1800e0345  int     29h; Win8: RtlFailFast(ecx)
0x1800e0347  mov     rcx, [rbp+57h+lpBuffer]
0x1800e034b  test    rcx, rcx
0x1800e034e  jz      short loc_1800E0356
0x1800e0350  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e0355  nop
0x1800e0356  jmp     loc_1800E0233
0x1800e035b  mov     rcx, rbx; Handle
0x1800e035e  call    cs:__imp_NtClose
0x1800e0365  nop     dword ptr [rax+rax+00h]
0x1800e036a  test    eax, eax
0x1800e036c  jns     short loc_1800E0375
0x1800e036e  mov     ecx, 7
0x1800e0373  int     29h; Win8: RtlFailFast(ecx)
0x1800e0375  jmp     loc_1800E025E
0x1800e037a  mov     rcx, [rdi+38h]
0x1800e037e  test    rcx, rcx
0x1800e0381  jz      short loc_1800E0396
0x1800e0383  mov     qword ptr [rdi+38h], 0
0x1800e038b  mov     rax, [rcx]
0x1800e038e  mov     rax, [rax]
0x1800e0391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0396  mov     rcx, [rdi+30h]
0x1800e039a  test    rcx, rcx
0x1800e039d  jz      short loc_1800E03B2
0x1800e039f  mov     qword ptr [rdi+30h], 0
0x1800e03a7  mov     rax, [rcx]
0x1800e03aa  mov     rax, [rax]
0x1800e03ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e03b2  mov     rcx, [rdi+28h]
0x1800e03b6  test    rcx, rcx
0x1800e03b9  jz      short loc_1800E03CF
0x1800e03bb  mov     qword ptr [rdi+28h], 0
0x1800e03c3  mov     rax, [rcx]
0x1800e03c6  mov     rax, [rax]
0x1800e03c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e03ce  nop
0x1800e03cf  mov     rcx, rbx; Handle
0x1800e03d2  call    cs:__imp_NtClose
0x1800e03d9  nop     dword ptr [rax+rax+00h]
0x1800e03de  test    eax, eax
0x1800e03e0  jns     short loc_1800E03E9
0x1800e03e2  mov     ecx, 7
0x1800e03e7  int     29h; Win8: RtlFailFast(ecx)
0x1800e03e9  mov     rcx, [rbp+57h+lpBuffer]
0x1800e03ed  test    rcx, rcx
0x1800e03f0  jz      short loc_1800E03FD
0x1800e03f2  test    rcx, rcx
0x1800e03f5  jz      short loc_1800E03FD
0x1800e03f7  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e03fc  nop
0x1800e03fd  xor     eax, eax
0x1800e03ff  mov     rcx, [rbp+57h+var_20]
0x1800e0403  xor     rcx, rsp; StackCookie
0x1800e0406  call    __security_check_cookie
0x1800e040b  mov     rbx, [rsp+0A0h+arg_8]
0x1800e0413  add     rsp, 90h
0x1800e041a  pop     rdi
0x1800e041b  pop     rsi
0x1800e041c  pop     rbp
0x1800e041d  retn
```
