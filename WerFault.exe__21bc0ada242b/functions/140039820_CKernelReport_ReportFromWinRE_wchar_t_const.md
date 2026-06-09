# CKernelReport::ReportFromWinRE(wchar_t const *)

- ea: `0x140039820`
- end: `0x140039c3a`
- name: `?ReportFromWinRE@CKernelReport@@QEAAJPEB_W@Z`
- size: `1050`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003494c`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140005430`
- `0x14000c8a0`
- `0x14000cc58`
- `0x140034d9c`
- `0x14003902c`
- `0x140039074`
- `0x140039614`
- `0x140039820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140039bb0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140039bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039b8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039b8b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140039b52`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140039b52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039bba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039bc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039bba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039bc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140039a23`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140039a23`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400398bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400398bd`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1400398cb`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1400398cb`
- `RPCRT4!UuidCreate` at `0x1400398d8`
- `RPCRT4!UuidCreate` at `0x1400398d8`
- `DiagnosticDataSettings!TelGetWerTelemetryModeWinRE` at `0x140039859`
- `DiagnosticDataSettings!TelGetWerTelemetryModeWinRE` at `0x140039859`

## string_xrefs

- `0x1400398f2`: `UuidCreate failed`
- `0x140039ab2`: `Failed to build the command line for wermgr.exe in WinRE`
- `0x140039b63`: `CreateProcess failed for wermgr.exe in WinRE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CKernelReport::ReportFromWinRE(CKernelReport *this, const wchar_t *a2)
{
  unsigned __int64 v5; // r8
  RPC_STATUS v6; // eax
  CKernelReport *v7; // rcx
  int v8; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  signed int LastError; // eax
  signed int v12; // eax
  wil::details *bInheritHandles; // [rsp+20h] [rbp-E0h]
  wil::details *bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  wil::details *bInheritHandlesb; // [rsp+20h] [rbp-E0h]
  const char *lpEnvironment; // [rsp+30h] [rbp-D0h]
  const char *lpEnvironmenta; // [rsp+30h] [rbp-D0h]
  LPWSTR lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v19; // [rsp+58h] [rbp-A8h]
  _WORD v20[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v22[8]; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-70h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-68h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  void *v26[2]; // [rsp+120h] [rbp+20h] BYREF
  _WORD v27[8]; // [rsp+130h] [rbp+30h] BYREF
  struct _FILETIME LocalFileTime[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v29; // [rsp+150h] [rbp+50h]
  __int64 v30; // [rsp+160h] [rbp+60h]
  wil::details::in1diag4 *retaddr; // [rsp+198h] [rbp+98h]

  if ( !a2 )
    return 2147942487LL;
  if ( (int)TelGetWerTelemetryModeWinRE() <= 1 )
    return 1;
  v26[0] = v27;
  v26[1] = v27;
  v27[0] = 0;
  *(_OWORD *)&LocalFileTime[0].dwLowDateTime = 0;
  v29 = 0;
  v30 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((__int64)v26, a2, v5) )
    goto LABEL_25;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  FileTimeToLocalFileTime(&SystemTimeAsFileTime, LocalFileTime);
  DWORD2(v29) = 0;
  v6 = UuidCreate((UUID *)&LocalFileTime[1]);
  v8 = v6;
  if ( v6 && v6 != 1824 )
  {
    LODWORD(bInheritHandles) = v6;
    wil::details::in1diag4::Log_Win32Msg(
      retaddr,
      (void *)0xC20,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ReportFromWinRE",
      bInheritHandles,
      (unsigned int)"UuidCreate failed",
      lpEnvironment);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    goto LABEL_14;
  }
  v8 = CKernelReport::QueueKernelReport(v7, (const struct KERNEL_QUEUED_REPORT *)v26);
  if ( v8 < 0 )
  {
    v9 = "QueueKernelReport failed";
    v10 = 3112;
LABEL_19:
    LODWORD(bInheritHandles) = v8;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ReportFromWinRE",
      bInheritHandles,
      (int)v9,
      lpEnvironment);
LABEL_14:
    if ( v26[0] != v27 )
      operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v8;
  }
  v8 = CKernelReport::ReportFromKQueue(this);
  if ( v8 < 0 )
  {
    v9 = "ReportFromKQueue failed";
    v10 = 3120;
    goto LABEL_19;
  }
  lpBuffer = v20;
  v19 = v20;
  v20[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                           &lpBuffer,
                           260) )
  {
    if ( lpBuffer != v20 )
      operator delete(lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
LABEL_25:
    if ( v26[0] != v27 )
      operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( !GetSystemDirectoryW(lpBuffer, v19 - lpBuffer) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_31:
    if ( lpBuffer != v20 )
      operator delete(lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_14;
  }
  lpCommandLine[0] = v22;
  lpCommandLine[1] = v22;
  v22[0] = 0;
  v8 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         (__int64)lpCommandLine,
         (__int64)L"%ws\\%ws %ws",
         lpBuffer,
         L"wermgr.exe",
         L"-upload");
  if ( v8 < 0 )
  {
    LODWORD(bInheritHandlesa) = v8;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0xC47,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ReportFromWinRE",
      bInheritHandlesa,
      (int)"Failed to build the command line for wermgr.exe in WinRE",
      lpEnvironment);
LABEL_35:
    if ( lpCommandLine[0] != v22 )
      operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_31;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  if ( !CreateProcessW(0, lpCommandLine[0], 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LODWORD(bInheritHandlesb) = v8;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0xC5A,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ReportFromWinRE",
      bInheritHandlesb,
      (int)"CreateProcess failed for wermgr.exe in WinRE",
      lpEnvironmenta);
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_35;
  }
  WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  if ( lpCommandLine[0] != v22 )
    operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpBuffer != v20 )
    operator delete(lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
  if ( v26[0] != v27 )
    operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x140039820  mov     [rsp-8+arg_10], rbx
0x140039825  push    rbp
0x140039826  push    rsi
0x140039827  push    rdi
0x140039828  lea     rbp, [rsp-80h]
0x14003982d  sub     rsp, 180h
0x140039834  mov     rax, cs:__security_cookie
0x14003983b  xor     rax, rsp
0x14003983e  mov     [rbp+90h+var_20], rax
0x140039842  mov     rbx, rdx
0x140039845  mov     rdi, rcx
0x140039848  xor     esi, esi
0x14003984a  test    rdx, rdx
0x14003984d  jnz     short loc_140039859
0x14003984f  mov     eax, 80070057h
0x140039854  jmp     loc_140039C1B
0x140039859  call    cs:__imp_TelGetWerTelemetryModeWinRE
0x14003985f  cmp     eax, 1
0x140039862  jg      short loc_14003986E
0x140039864  mov     eax, 1
0x140039869  jmp     loc_140039C1B
0x14003986e  lea     rax, [rbp+90h+var_60]
0x140039872  mov     [rbp+90h+var_70], rax
0x140039876  lea     rax, [rbp+90h+var_60]
0x14003987a  mov     [rbp+90h+var_68], rax
0x14003987e  mov     [rbp+90h+var_60], si
0x140039882  xor     eax, eax
0x140039884  xorps   xmm0, xmm0
0x140039887  movups  xmmword ptr [rbp+90h+LocalFileTime.dwLowDateTime], xmm0
0x14003988b  movups  [rbp+90h+var_40], xmm0
0x14003988f  mov     [rbp+90h+var_30], rax
0x140039893  or      r8, 0FFFFFFFFFFFFFFFFh
0x140039897  inc     r8
0x14003989a  cmp     [rbx+r8*2], si
0x14003989f  jnz     short loc_140039897
0x1400398a1  mov     rdx, rbx
0x1400398a4  lea     rcx, [rbp+90h+var_70]
0x1400398a8  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400398ad  test    al, al
0x1400398af  jz      loc_1400399F5
0x1400398b5  mov     qword ptr [rbp+90h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1400398b9  lea     rcx, [rbp+90h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400398bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400398c3  lea     rdx, [rbp+90h+LocalFileTime]; lpLocalFileTime
0x1400398c7  lea     rcx, [rbp+90h+SystemTimeAsFileTime]; lpFileTime
0x1400398cb  call    cs:__imp_FileTimeToLocalFileTime
0x1400398d1  mov     dword ptr [rbp+90h+var_40+8], esi
0x1400398d4  lea     rcx, [rbp+90h+LocalFileTime.dwLowDateTime+8]; Uuid
0x1400398d8  call    cs:__imp_UuidCreate
0x1400398de  mov     ebx, eax
0x1400398e0  test    eax, eax
0x1400398e2  jz      short loc_140039951
0x1400398e4  cmp     eax, 720h
0x1400398e9  jz      short loc_140039951
0x1400398eb  mov     rcx, [rbp+98h]; this
0x1400398f2  lea     rax, aUuidcreateFail; "UuidCreate failed"
0x1400398f9  mov     qword ptr [rsp+190h+dwCreationFlags], rax; unsigned int
0x1400398fe  mov     [rsp+190h+bInheritHandles], ebx; wil::details *
0x140039902  lea     r9, aCkernelreportR; "CKernelReport::ReportFromWinRE"
0x140039909  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140039910  mov     edx, 0C20h; void *
0x140039915  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003991a  test    ebx, ebx
0x14003991c  jle     short loc_140039927
0x14003991e  movzx   ebx, bx
0x140039921  or      ebx, 80070000h
0x140039927  mov     eax, 80004005h
0x14003992c  test    ebx, ebx
0x14003992e  cmovns  ebx, eax
0x140039931  mov     rcx, [rbp+90h+var_70]; void *
0x140039935  lea     rax, [rbp+90h+var_60]
0x140039939  cmp     rcx, rax
0x14003993c  jz      short loc_14003994A
0x14003993e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140039945  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003994a  mov     eax, ebx
0x14003994c  jmp     loc_140039C1B
0x140039951  lea     rdx, [rbp+90h+var_70]; struct KERNEL_QUEUED_REPORT *
0x140039955  call    ?QueueKernelReport@CKernelReport@@AEAAJPEBUKERNEL_QUEUED_REPORT@@@Z; CKernelReport::QueueKernelReport(KERNEL_QUEUED_REPORT const *)
0x14003995a  mov     ebx, eax
0x14003995c  test    eax, eax
0x14003995e  jns     short loc_140039991
0x140039960  lea     rax, aQueuekernelrep; "QueueKernelReport failed"
0x140039967  mov     edx, 0C28h; void *
0x14003996c  mov     qword ptr [rsp+190h+dwCreationFlags], rax; int
0x140039971  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140039978  lea     r9, aCkernelreportR; "CKernelReport::ReportFromWinRE"
0x14003997f  mov     [rsp+190h+bInheritHandles], ebx; wil::details *
0x140039983  mov     rcx, [rbp+98h]; this
0x14003998a  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003998f  jmp     short loc_140039931
0x140039991  mov     rcx, rdi; this
0x140039994  call    ?ReportFromKQueue@CKernelReport@@QEAAJXZ; CKernelReport::ReportFromKQueue(void)
0x140039999  mov     ebx, eax
0x14003999b  test    eax, eax
0x14003999d  jns     short loc_1400399AD
0x14003999f  lea     rax, aReportfromkque; "ReportFromKQueue failed"
0x1400399a6  mov     edx, 0C30h
0x1400399ab  jmp     short loc_14003996C
0x1400399ad  lea     rax, [rsp+190h+var_130]
0x1400399b2  mov     [rsp+190h+lpBuffer], rax
0x1400399b7  lea     rax, [rsp+190h+var_130]
0x1400399bc  mov     [rsp+190h+var_138], rax
0x1400399c1  mov     [rsp+190h+var_130], si
0x1400399c6  mov     edx, 104h
0x1400399cb  lea     rcx, [rsp+190h+lpBuffer]
0x1400399d0  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1400399d5  mov     rcx, [rsp+190h+lpBuffer]; void *
0x1400399da  test    al, al
0x1400399dc  jnz     short loc_140039A18
0x1400399de  lea     rax, [rsp+190h+var_130]
0x1400399e3  cmp     rcx, rax
0x1400399e6  jz      short loc_1400399F5
0x1400399e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400399ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400399f4  nop
0x1400399f5  lea     rax, [rbp+90h+var_60]
0x1400399f9  mov     rcx, [rbp+90h+var_70]; void *
0x1400399fd  cmp     rcx, rax
0x140039a00  jz      short loc_140039A0E
0x140039a02  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140039a09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140039a0e  mov     eax, 8007000Eh
0x140039a13  jmp     loc_140039C1B
0x140039a18  mov     rdx, [rsp+190h+var_138]
0x140039a1d  sub     rdx, rcx
0x140039a20  sar     rdx, 1; uSize
0x140039a23  call    cs:__imp_GetSystemDirectoryW
0x140039a29  test    eax, eax
0x140039a2b  jnz     short loc_140039A66
0x140039a2d  call    cs:__imp_GetLastError
0x140039a33  mov     ebx, eax
0x140039a35  test    eax, eax
0x140039a37  jle     short loc_140039A42
0x140039a39  movzx   ebx, ax
0x140039a3c  or      ebx, 80070000h
0x140039a42  lea     rax, [rsp+190h+var_130]
0x140039a47  mov     rcx, [rsp+190h+lpBuffer]; void *
0x140039a4c  cmp     rcx, rax
0x140039a4f  jz      loc_140039931
0x140039a55  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140039a5c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140039a61  jmp     loc_140039931
0x140039a66  lea     rax, [rbp+90h+var_110]
0x140039a6a  mov     [rsp+190h+lpCommandLine], rax
0x140039a6f  lea     rax, [rbp+90h+var_110]
0x140039a73  mov     [rsp+190h+var_118], rax
0x140039a78  mov     [rbp+90h+var_110], si
0x140039a7c  lea     rax, aUpload; "-upload"
0x140039a83  mov     qword ptr [rsp+190h+bInheritHandles], rax
0x140039a88  lea     r9, aWermgrExe; "wermgr.exe"
0x140039a8f  mov     r8, [rsp+190h+lpBuffer]
0x140039a94  lea     rdx, aWsWsWs; "%ws\\%ws %ws"
0x140039a9b  lea     rcx, [rsp+190h+lpCommandLine]
0x140039aa0  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140039aa5  mov     ebx, eax
0x140039aa7  test    eax, eax
0x140039aa9  jns     short loc_140039AFD
0x140039aab  mov     rcx, [rbp+98h]; this
0x140039ab2  lea     rax, aFailedToBuildT; "Failed to build the command line for we"...
0x140039ab9  mov     qword ptr [rsp+190h+dwCreationFlags], rax; int
0x140039abe  mov     [rsp+190h+bInheritHandles], ebx; wil::details *
0x140039ac2  lea     r9, aCkernelreportR; "CKernelReport::ReportFromWinRE"
0x140039ac9  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140039ad0  mov     edx, 0C47h; void *
0x140039ad5  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140039ada  lea     rax, [rbp+90h+var_110]
0x140039ade  mov     rcx, [rsp+190h+lpCommandLine]; void *
0x140039ae3  cmp     rcx, rax
0x140039ae6  jz      loc_140039A42
0x140039aec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140039af3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140039af8  jmp     loc_140039A42
0x140039afd  xorps   xmm0, xmm0
0x140039b00  xor     eax, eax
0x140039b02  movups  xmmword ptr [rbp+90h+ProcessInformation.hProcess], xmm0
0x140039b06  mov     qword ptr [rbp+90h+ProcessInformation.dwProcessId], rax
0x140039b0a  mov     qword ptr [rbp+90h+StartupInfo.cb], 68h ; 'h'
0x140039b12  xor     edx, edx; Val
0x140039b14  lea     r8d, [rax+60h]; Size
0x140039b18  lea     rcx, [rbp+90h+StartupInfo.lpReserved]; void *
0x140039b1c  call    memset_0
0x140039b21  lea     rax, [rbp+90h+ProcessInformation]
0x140039b25  mov     [rsp+190h+lpProcessInformation], rax; lpProcessInformation
0x140039b2a  lea     rax, [rbp+90h+StartupInfo]
0x140039b2e  mov     [rsp+190h+lpStartupInfo], rax; lpStartupInfo
0x140039b33  mov     [rsp+190h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x140039b38  mov     [rsp+190h+lpEnvironment], rsi; char *
0x140039b3d  mov     [rsp+190h+dwCreationFlags], esi; dwCreationFlags
0x140039b41  mov     [rsp+190h+bInheritHandles], esi; bInheritHandles
0x140039b45  xor     r9d, r9d; lpThreadAttributes
0x140039b48  xor     r8d, r8d; lpProcessAttributes
0x140039b4b  mov     rdx, [rsp+190h+lpCommandLine]; lpCommandLine
0x140039b50  xor     ecx, ecx; lpApplicationName
0x140039b52  call    cs:__imp_CreateProcessW
0x140039b58  test    eax, eax
0x140039b5a  jnz     short loc_140039BA9
0x140039b5c  mov     rcx, [rbp+98h]; this
0x140039b63  lea     rax, aCreateprocessF; "CreateProcess failed for wermgr.exe in "...
0x140039b6a  mov     qword ptr [rsp+190h+dwCreationFlags], rax; int
0x140039b6f  mov     [rsp+190h+bInheritHandles], ebx; wil::details *
0x140039b73  lea     r9, aCkernelreportR; "CKernelReport::ReportFromWinRE"
0x140039b7a  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140039b81  mov     edx, 0C5Ah; void *
0x140039b86  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140039b8b  call    cs:__imp_GetLastError
0x140039b91  mov     ebx, eax
0x140039b93  test    eax, eax
0x140039b95  jle     loc_140039ADA
0x140039b9b  movzx   ebx, ax
0x140039b9e  or      ebx, 80070000h
0x140039ba4  jmp     loc_140039ADA
0x140039ba9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140039bac  mov     rcx, [rbp+90h+ProcessInformation.hProcess]; hHandle
0x140039bb0  call    cs:__imp_WaitForSingleObject
0x140039bb6  mov     rcx, [rbp+90h+ProcessInformation.hProcess]; hObject
0x140039bba  call    cs:__imp_CloseHandle
0x140039bc0  mov     rcx, [rbp+90h+ProcessInformation.hThread]; hObject
0x140039bc4  call    cs:__imp_CloseHandle
0x140039bca  lea     rax, [rbp+90h+var_110]
0x140039bce  mov     rcx, [rsp+190h+lpCommandLine]; void *
0x140039bd3  cmp     rcx, rax
0x140039bd6  jz      short loc_140039BE4
0x140039bd8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140039bdf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140039be4  lea     rax, [rsp+190h+var_130]
0x140039be9  mov     rcx, [rsp+190h+lpBuffer]; void *
0x140039bee  cmp     rcx, rax
0x140039bf1  jz      short loc_140039C00
0x140039bf3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140039bfa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140039bff  nop
0x140039c00  mov     rcx, [rbp+90h+var_70]; void *
0x140039c04  lea     rax, [rbp+90h+var_60]
0x140039c08  cmp     rcx, rax
0x140039c0b  jz      short loc_140039C19
0x140039c0d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140039c14  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140039c19  xor     eax, eax
0x140039c1b  mov     rcx, [rbp+90h+var_20]
0x140039c1f  xor     rcx, rsp; StackCookie
0x140039c22  call    __security_check_cookie
0x140039c27  mov     rbx, [rsp+190h+arg_10]
0x140039c2f  add     rsp, 180h
0x140039c36  pop     rdi
0x140039c37  pop     rsi
0x140039c38  pop     rbp
0x140039c39  retn
```
