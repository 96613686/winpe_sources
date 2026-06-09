# CKernelReport::ReportFromWinRE(wchar_t const *)

- ea: `0x14003be5c`
- end: `0x14003c2b3`
- name: `?ReportFromWinRE@CKernelReport@@QEAAJPEB_W@Z`
- size: `1111`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140036e5c`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x1400054e4`
- `0x14000ca20`
- `0x14000cf48`
- `0x1400372dc`
- `0x14003b56c`
- `0x14003b5b4`
- `0x14003bbd4`
- `0x14003be5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003c216`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003c216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c1eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c1eb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14003c1ac`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14003c1ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c236`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14003c071`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14003c071`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003bef9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003bef9`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14003bf0d`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14003bf0d`
- `RPCRT4!UuidCreate` at `0x14003bf20`
- `RPCRT4!UuidCreate` at `0x14003bf20`
- `DiagnosticDataSettings!TelGetWerTelemetryModeWinRE` at `0x14003be95`
- `DiagnosticDataSettings!TelGetWerTelemetryModeWinRE` at `0x14003be95`

## string_xrefs

- `0x14003bf40`: `UuidCreate failed`
- `0x14003c10c`: `Failed to build the command line for wermgr.exe in WinRE`
- `0x14003c1c3`: `CreateProcess failed for wermgr.exe in WinRE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CKernelReport::ReportFromWinRE(CKernelReport *this, const wchar_t *a2)
{
  __int64 v5; // r8
  RPC_STATUS v6; // eax
  CKernelReport *v7; // rcx
  signed int v8; // ebx
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
  wil::details::in1diag4 *retaddr; // [rsp+188h] [rbp+88h]

  if ( !a2 )
    return 2147942487LL;
  if ( (int)TelGetWerTelemetryModeWinRE() <= 1 )
    return 1;
  v26[0] = v27;
  v26[1] = v27;
  v27[0] = 0;
  *(_OWORD *)&LocalFileTime[0].dwLowDateTime = 0;
  v29 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v26, a2) )
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
      (void *)0xC96,
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
    v10 = 3230;
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
    v10 = 3238;
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
         lpCommandLine,
         L"%ws\\%ws %ws",
         lpBuffer,
         L"wermgr.exe",
         L"-upload");
  if ( v8 < 0 )
  {
    LODWORD(bInheritHandlesa) = v8;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0xCBD,
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
      (void *)0xCD0,
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
0x14003be5c  mov     [rsp-8+arg_10], rbx
0x14003be61  push    rbp
0x14003be62  push    rsi
0x14003be63  push    rdi
0x14003be64  lea     rbp, [rsp-70h]
0x14003be69  sub     rsp, 170h
0x14003be70  mov     rax, cs:__security_cookie
0x14003be77  xor     rax, rsp
0x14003be7a  mov     [rbp+80h+var_20], rax
0x14003be7e  mov     rbx, rdx
0x14003be81  mov     rdi, rcx
0x14003be84  xor     esi, esi
0x14003be86  test    rdx, rdx
0x14003be89  jnz     short loc_14003BE95
0x14003be8b  mov     eax, 80070057h
0x14003be90  jmp     loc_14003C293
0x14003be95  call    cs:__imp_TelGetWerTelemetryModeWinRE
0x14003be9c  nop     dword ptr [rax+rax+00h]
0x14003bea1  cmp     eax, 1
0x14003bea4  jg      short loc_14003BEB0
0x14003bea6  mov     eax, 1
0x14003beab  jmp     loc_14003C293
0x14003beb0  lea     rax, [rbp+80h+var_50]
0x14003beb4  mov     [rbp+80h+var_60], rax
0x14003beb8  lea     rax, [rbp+80h+var_50]
0x14003bebc  mov     [rbp+80h+var_58], rax
0x14003bec0  mov     [rbp+80h+var_50], si
0x14003bec4  xorps   xmm0, xmm0
0x14003bec7  movups  xmmword ptr [rbp+80h+LocalFileTime.dwLowDateTime], xmm0
0x14003becb  movups  [rbp+80h+var_30], xmm0
0x14003becf  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003bed3  inc     r8
0x14003bed6  cmp     [rbx+r8*2], si
0x14003bedb  jnz     short loc_14003BED3
0x14003bedd  mov     rdx, rbx
0x14003bee0  lea     rcx, [rbp+80h+var_60]
0x14003bee4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003bee9  test    al, al
0x14003beeb  jz      loc_14003C043
0x14003bef1  mov     qword ptr [rbp+80h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x14003bef5  lea     rcx, [rbp+80h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14003bef9  call    cs:__imp_GetSystemTimeAsFileTime
0x14003bf00  nop     dword ptr [rax+rax+00h]
0x14003bf05  lea     rdx, [rbp+80h+LocalFileTime]; lpLocalFileTime
0x14003bf09  lea     rcx, [rbp+80h+SystemTimeAsFileTime]; lpFileTime
0x14003bf0d  call    cs:__imp_FileTimeToLocalFileTime
0x14003bf14  nop     dword ptr [rax+rax+00h]
0x14003bf19  mov     dword ptr [rbp+80h+var_30+8], esi
0x14003bf1c  lea     rcx, [rbp+80h+LocalFileTime.dwLowDateTime+8]; Uuid
0x14003bf20  call    cs:__imp_UuidCreate
0x14003bf27  nop     dword ptr [rax+rax+00h]
0x14003bf2c  mov     ebx, eax
0x14003bf2e  test    eax, eax
0x14003bf30  jz      short loc_14003BF9F
0x14003bf32  cmp     eax, 720h
0x14003bf37  jz      short loc_14003BF9F
0x14003bf39  mov     rcx, [rbp+88h]; this
0x14003bf40  lea     rax, aUuidcreateFail; "UuidCreate failed"
0x14003bf47  mov     qword ptr [rsp+180h+dwCreationFlags], rax; unsigned int
0x14003bf4c  mov     [rsp+180h+bInheritHandles], ebx; wil::details *
0x14003bf50  lea     r9, aCkernelreportR; "CKernelReport::ReportFromWinRE"
0x14003bf57  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003bf5e  mov     edx, 0C96h; void *
0x14003bf63  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003bf68  test    ebx, ebx
0x14003bf6a  jle     short loc_14003BF75
0x14003bf6c  movzx   ebx, bx
0x14003bf6f  or      ebx, 80070000h
0x14003bf75  mov     eax, 80004005h
0x14003bf7a  test    ebx, ebx
0x14003bf7c  cmovns  ebx, eax
0x14003bf7f  mov     rcx, [rbp+80h+var_60]; void *
0x14003bf83  lea     rax, [rbp+80h+var_50]
0x14003bf87  cmp     rcx, rax
0x14003bf8a  jz      short loc_14003BF98
0x14003bf8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003bf93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003bf98  mov     eax, ebx
0x14003bf9a  jmp     loc_14003C293
0x14003bf9f  lea     rdx, [rbp+80h+var_60]; struct KERNEL_QUEUED_REPORT *
0x14003bfa3  call    ?QueueKernelReport@CKernelReport@@AEAAJPEBUKERNEL_QUEUED_REPORT@@@Z; CKernelReport::QueueKernelReport(KERNEL_QUEUED_REPORT const *)
0x14003bfa8  mov     ebx, eax
0x14003bfaa  test    eax, eax
0x14003bfac  jns     short loc_14003BFDF
0x14003bfae  lea     rax, aQueuekernelrep; "QueueKernelReport failed"
0x14003bfb5  mov     edx, 0C9Eh; void *
0x14003bfba  mov     qword ptr [rsp+180h+dwCreationFlags], rax; int
0x14003bfbf  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003bfc6  lea     r9, aCkernelreportR; "CKernelReport::ReportFromWinRE"
0x14003bfcd  mov     [rsp+180h+bInheritHandles], ebx; wil::details *
0x14003bfd1  mov     rcx, [rbp+88h]; this
0x14003bfd8  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003bfdd  jmp     short loc_14003BF7F
0x14003bfdf  mov     rcx, rdi; this
0x14003bfe2  call    ?ReportFromKQueue@CKernelReport@@QEAAJXZ; CKernelReport::ReportFromKQueue(void)
0x14003bfe7  mov     ebx, eax
0x14003bfe9  test    eax, eax
0x14003bfeb  jns     short loc_14003BFFB
0x14003bfed  lea     rax, aReportfromkque; "ReportFromKQueue failed"
0x14003bff4  mov     edx, 0CA6h
0x14003bff9  jmp     short loc_14003BFBA
0x14003bffb  lea     rax, [rsp+180h+var_120]
0x14003c000  mov     [rsp+180h+lpBuffer], rax
0x14003c005  lea     rax, [rsp+180h+var_120]
0x14003c00a  mov     [rsp+180h+var_128], rax
0x14003c00f  mov     [rsp+180h+var_120], si
0x14003c014  mov     edx, 104h
0x14003c019  lea     rcx, [rsp+180h+lpBuffer]
0x14003c01e  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14003c023  mov     rcx, [rsp+180h+lpBuffer]; void *
0x14003c028  test    al, al
0x14003c02a  jnz     short loc_14003C066
0x14003c02c  lea     rax, [rsp+180h+var_120]
0x14003c031  cmp     rcx, rax
0x14003c034  jz      short loc_14003C043
0x14003c036  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003c03d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c042  nop
0x14003c043  lea     rax, [rbp+80h+var_50]
0x14003c047  mov     rcx, [rbp+80h+var_60]; void *
0x14003c04b  cmp     rcx, rax
0x14003c04e  jz      short loc_14003C05C
0x14003c050  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003c057  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c05c  mov     eax, 8007000Eh
0x14003c061  jmp     loc_14003C293
0x14003c066  mov     rdx, [rsp+180h+var_128]
0x14003c06b  sub     rdx, rcx
0x14003c06e  sar     rdx, 1; uSize
0x14003c071  call    cs:__imp_GetSystemDirectoryW
0x14003c078  nop     dword ptr [rax+rax+00h]
0x14003c07d  test    eax, eax
0x14003c07f  jnz     short loc_14003C0C0
0x14003c081  call    cs:__imp_GetLastError
0x14003c088  nop     dword ptr [rax+rax+00h]
0x14003c08d  mov     ebx, eax
0x14003c08f  test    eax, eax
0x14003c091  jle     short loc_14003C09C
0x14003c093  movzx   ebx, ax
0x14003c096  or      ebx, 80070000h
0x14003c09c  lea     rax, [rsp+180h+var_120]
0x14003c0a1  mov     rcx, [rsp+180h+lpBuffer]; void *
0x14003c0a6  cmp     rcx, rax
0x14003c0a9  jz      loc_14003BF7F
0x14003c0af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003c0b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c0bb  jmp     loc_14003BF7F
0x14003c0c0  lea     rax, [rbp+80h+var_100]
0x14003c0c4  mov     [rsp+180h+lpCommandLine], rax
0x14003c0c9  lea     rax, [rbp+80h+var_100]
0x14003c0cd  mov     [rsp+180h+var_108], rax
0x14003c0d2  mov     [rbp+80h+var_100], si
0x14003c0d6  lea     rax, aUpload; "-upload"
0x14003c0dd  mov     qword ptr [rsp+180h+bInheritHandles], rax
0x14003c0e2  lea     r9, aWermgrExe; "wermgr.exe"
0x14003c0e9  mov     r8, [rsp+180h+lpBuffer]
0x14003c0ee  lea     rdx, aWsWsWs; "%ws\\%ws %ws"
0x14003c0f5  lea     rcx, [rsp+180h+lpCommandLine]
0x14003c0fa  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003c0ff  mov     ebx, eax
0x14003c101  test    eax, eax
0x14003c103  jns     short loc_14003C157
0x14003c105  mov     rcx, [rbp+88h]; this
0x14003c10c  lea     rax, aFailedToBuildT; "Failed to build the command line for we"...
0x14003c113  mov     qword ptr [rsp+180h+dwCreationFlags], rax; int
0x14003c118  mov     [rsp+180h+bInheritHandles], ebx; wil::details *
0x14003c11c  lea     r9, aCkernelreportR; "CKernelReport::ReportFromWinRE"
0x14003c123  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c12a  mov     edx, 0CBDh; void *
0x14003c12f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c134  lea     rax, [rbp+80h+var_100]
0x14003c138  mov     rcx, [rsp+180h+lpCommandLine]; void *
0x14003c13d  cmp     rcx, rax
0x14003c140  jz      loc_14003C09C
0x14003c146  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003c14d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c152  jmp     loc_14003C09C
0x14003c157  xorps   xmm0, xmm0
0x14003c15a  xor     eax, eax
0x14003c15c  movups  xmmword ptr [rbp+80h+ProcessInformation.hProcess], xmm0
0x14003c160  mov     qword ptr [rbp+80h+ProcessInformation.dwProcessId], rax
0x14003c164  mov     qword ptr [rbp+80h+StartupInfo.cb], 68h ; 'h'
0x14003c16c  xor     edx, edx; Val
0x14003c16e  lea     r8d, [rax+60h]; Size
0x14003c172  lea     rcx, [rbp+80h+StartupInfo.lpReserved]; void *
0x14003c176  call    memset_0
0x14003c17b  lea     rax, [rbp+80h+ProcessInformation]
0x14003c17f  mov     [rsp+180h+lpProcessInformation], rax; lpProcessInformation
0x14003c184  lea     rax, [rbp+80h+StartupInfo]
0x14003c188  mov     [rsp+180h+lpStartupInfo], rax; lpStartupInfo
0x14003c18d  mov     [rsp+180h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x14003c192  mov     [rsp+180h+lpEnvironment], rsi; char *
0x14003c197  mov     [rsp+180h+dwCreationFlags], esi; dwCreationFlags
0x14003c19b  mov     [rsp+180h+bInheritHandles], esi; bInheritHandles
0x14003c19f  xor     r9d, r9d; lpThreadAttributes
0x14003c1a2  xor     r8d, r8d; lpProcessAttributes
0x14003c1a5  mov     rdx, [rsp+180h+lpCommandLine]; lpCommandLine
0x14003c1aa  xor     ecx, ecx; lpApplicationName
0x14003c1ac  call    cs:__imp_CreateProcessW
0x14003c1b3  nop     dword ptr [rax+rax+00h]
0x14003c1b8  test    eax, eax
0x14003c1ba  jnz     short loc_14003C20F
0x14003c1bc  mov     rcx, [rbp+88h]; this
0x14003c1c3  lea     rax, aCreateprocessF; "CreateProcess failed for wermgr.exe in "...
0x14003c1ca  mov     qword ptr [rsp+180h+dwCreationFlags], rax; int
0x14003c1cf  mov     [rsp+180h+bInheritHandles], ebx; wil::details *
0x14003c1d3  lea     r9, aCkernelreportR; "CKernelReport::ReportFromWinRE"
0x14003c1da  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c1e1  mov     edx, 0CD0h; void *
0x14003c1e6  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c1eb  call    cs:__imp_GetLastError
0x14003c1f2  nop     dword ptr [rax+rax+00h]
0x14003c1f7  mov     ebx, eax
0x14003c1f9  test    eax, eax
0x14003c1fb  jle     loc_14003C134
0x14003c201  movzx   ebx, ax
0x14003c204  or      ebx, 80070000h
0x14003c20a  jmp     loc_14003C134
0x14003c20f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003c212  mov     rcx, [rbp+80h+ProcessInformation.hProcess]; hHandle
0x14003c216  call    cs:__imp_WaitForSingleObject
0x14003c21d  nop     dword ptr [rax+rax+00h]
0x14003c222  mov     rcx, [rbp+80h+ProcessInformation.hProcess]; hObject
0x14003c226  call    cs:__imp_CloseHandle
0x14003c22d  nop     dword ptr [rax+rax+00h]
0x14003c232  mov     rcx, [rbp+80h+ProcessInformation.hThread]; hObject
0x14003c236  call    cs:__imp_CloseHandle
0x14003c23d  nop     dword ptr [rax+rax+00h]
0x14003c242  lea     rax, [rbp+80h+var_100]
0x14003c246  mov     rcx, [rsp+180h+lpCommandLine]; void *
0x14003c24b  cmp     rcx, rax
0x14003c24e  jz      short loc_14003C25C
0x14003c250  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003c257  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c25c  lea     rax, [rsp+180h+var_120]
0x14003c261  mov     rcx, [rsp+180h+lpBuffer]; void *
0x14003c266  cmp     rcx, rax
0x14003c269  jz      short loc_14003C278
0x14003c26b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003c272  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c277  nop
0x14003c278  mov     rcx, [rbp+80h+var_60]; void *
0x14003c27c  lea     rax, [rbp+80h+var_50]
0x14003c280  cmp     rcx, rax
0x14003c283  jz      short loc_14003C291
0x14003c285  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003c28c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c291  xor     eax, eax
0x14003c293  mov     rcx, [rbp+80h+var_20]
0x14003c297  xor     rcx, rsp; StackCookie
0x14003c29a  call    __security_check_cookie
0x14003c29f  mov     rbx, [rsp+180h+arg_10]
0x14003c2a7  add     rsp, 170h
0x14003c2ae  pop     rdi
0x14003c2af  pop     rsi
0x14003c2b0  pop     rbp
0x14003c2b1  retn
```
