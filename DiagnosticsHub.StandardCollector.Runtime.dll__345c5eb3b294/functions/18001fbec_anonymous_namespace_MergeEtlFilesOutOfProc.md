# _anonymous_namespace_::MergeEtlFilesOutOfProc

- ea: `0x18001fbec`
- end: `0x180020001`
- name: `_anonymous_namespace_::MergeEtlFilesOutOfProc`
- size: `1045`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020004`

## callees

- `0x1800021fc`
- `0x1800022f4`
- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18000a17c`
- `0x18001fbec`
- `0x1800257bc`
- `0x180027bc8`
- `0x18003d864`
- `0x180040d8c`
- `0x180049b50`
- `0x18004ad26`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18001fd52`
- `VCRUNTIME140!memcpy` at `0x18001fd52`
- `KERNEL32!WaitForSingleObject` at `0x18001ff09`
- `KERNEL32!WaitForSingleObject` at `0x18001ff09`
- `KERNEL32!GetEnvironmentStringsW` at `0x18001fc9d`
- `KERNEL32!GetEnvironmentStringsW` at `0x18001fc9d`
- `KERNEL32!FreeEnvironmentStringsW` at `0x18001fd5c`
- `KERNEL32!FreeEnvironmentStringsW` at `0x18001fd5c`
- `KERNEL32!CreateProcessW` at `0x18001fe72`
- `KERNEL32!CreateProcessW` at `0x18001fe72`
- `KERNEL32!GetExitCodeProcess` at `0x18001ff2a`
- `KERNEL32!GetExitCodeProcess` at `0x18001ff2a`
- `KERNEL32!CloseHandle` at `0x18001ff50`
- `KERNEL32!CloseHandle` at `0x18001ff5f`
- `KERNEL32!CloseHandle` at `0x18001ff50`
- `KERNEL32!CloseHandle` at `0x18001ff5f`
- `KERNEL32!GetLastError` at `0x18001fe7c`
- `KERNEL32!GetLastError` at `0x18001ff1b`
- `KERNEL32!GetLastError` at `0x18001fe7c`
- `KERNEL32!GetLastError` at `0x18001ff1b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18001fd38`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18001fd38`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18001fd44`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18001fd44`

## string_xrefs

- `0x18001fef0`: `Merge is not complete after waiting for %u minutes. Waiting again.`
- `0x18001fd65`: `XPERF_EmbeddedPdbPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall anonymous_namespace_::MergeEtlFilesOutOfProc(__int64 a1, _QWORD *a2, __int64 a3, char a4)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  _QWORD *v9; // rdi
  _QWORD *i; // rbx
  LPWCH EnvironmentStringsW; // rax
  LPWCH v12; // rdi
  unsigned int v13; // r15d
  WCHAR *v14; // rbx
  int j; // ebx
  _WORD *v16; // rcx
  bool v17; // zf
  int v18; // ebx
  struct ATL::IAtlStringMgr *v19; // rax
  _DWORD *v20; // rax
  char *v21; // rcx
  size_t v22; // r8
  void *lpEnvironment; // rsi
  signed int v24; // eax
  HANDLE hProcess; // rdi
  HANDLE hThread; // r14
  DWORD v27; // eax
  signed int LastError; // eax
  LPVOID v30; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR lpCommandLine[3]; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  DWORD ExitCode; // [rsp+88h] [rbp-78h] BYREF
  __int128 v34; // [rsp+90h] [rbp-70h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-60h]
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF

  v34 = 0;
  v35 = 0;
  DiagHubCommon::ModulePath::GetModulePath(0);
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  lpCommandLine[0] = (LPWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                            + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    lpCommandLine,
    L"\"%s\" merge \"%s\"",
    (_QWORD)v34,
    a1);
  v9 = (_QWORD *)a2[1];
  for ( i = (_QWORD *)*a2; i != v9; ++i )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      lpCommandLine,
      L" \"%s\"",
      *i);
  EnvironmentStringsW = GetEnvironmentStringsW();
  v12 = EnvironmentStringsW;
  if ( EnvironmentStringsW )
  {
    for ( j = 0; ; ++j )
    {
      v16 = EnvironmentStringsW + 1;
      v17 = *EnvironmentStringsW++ == 0;
      if ( v17 && !*v16 )
        break;
    }
    v18 = j + 1;
    v19 = ATL::CAtlStringMgr::GetInstance();
    if ( !v19 )
      ATL::AtlThrowImpl(-2147467259);
    v20 = (_DWORD *)(**(__int64 (__fastcall ***)(struct ATL::IAtlStringMgr *, _QWORD, __int64))v19)(
                      v19,
                      (unsigned int)v18,
                      2);
    if ( !v20 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    v21 = (char *)(v20 + 6);
    v30 = v20 + 6;
    if ( v18 < 0 || v18 > v20[3] )
      ATL::AtlThrowImpl(-2147024809);
    v20[2] = v18;
    v22 = 2LL * v18;
    *(_WORD *)&v21[v22] = 0;
    if ( v22 )
    {
      if ( v20 == (_DWORD *)-24LL )
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
      else
      {
        _mm_lfence();
        memcpy(v21, v12, v22);
      }
    }
    FreeEnvironmentStringsW(v12);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &v30,
      L"%s=%s",
      L"XPERF_EmbeddedPdbPath",
      a3);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v30, 0);
    if ( a4 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v30,
        L"%s=1",
        L"DIAGHUB_DataInjectOnly");
      ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v30, 0);
    }
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v30, 0);
    v14 = lpCommandLine[0];
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
      L"Merging out-of-proc (%s)",
      lpCommandLine[0]);
    StartupInfo.cb = 104;
    memset_0(&StartupInfo.lpReserved, 0, 0x60u);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    lpEnvironment = v30;
    if ( *((int *)v30 - 2) > 1 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Fork(&v30, *((unsigned int *)v30 - 4));
      lpEnvironment = v30;
    }
    if ( *((int *)v14 - 2) > 1 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Fork(lpCommandLine, *((unsigned int *)v14 - 4));
      v14 = lpCommandLine[0];
    }
    if ( CreateProcessW(0, v14, 0, 0, 0, 0x400u, lpEnvironment, 0, &StartupInfo, &ProcessInformation) )
    {
      hProcess = ProcessInformation.hProcess;
      lpCommandLine[1] = (LPWSTR)ProcessInformation.hProcess;
      hThread = ProcessInformation.hThread;
      lpCommandLine[2] = (LPWSTR)ProcessInformation.hThread;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
        L"Waiting on merge running in process with PID %u",
        ProcessInformation.dwProcessId);
      while ( 1 )
      {
        v27 = WaitForSingleObject(hProcess, 0x1D4C0u);
        if ( v27 != 258 )
          break;
        if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 56),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
            L"Merge is not complete after waiting for %u minutes. Waiting again.",
            2);
      }
      if ( v27 == -1 || !GetExitCodeProcess(hProcess, &ExitCode) )
        LastError = GetLastError();
      else
        LastError = ExitCode;
      v13 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v13 = LastError;
      if ( hThread )
        CloseHandle(hThread);
      if ( hProcess )
        CloseHandle(hProcess);
    }
    else
    {
      v24 = GetLastError();
      v13 = (unsigned __int16)v24 | 0x80070000;
      if ( v24 <= 0 )
        v13 = v24;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpEnvironment - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpEnvironment - 3) + 8LL))(*((_QWORD *)lpEnvironment - 3));
    }
  }
  else
  {
    v13 = -2147418113;
    v14 = lpCommandLine[0];
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
  }
  std::vector<unsigned short>::~vector<unsigned short>(&v34);
  return v13;
}

```

## disassembly

```asm
0x18001fbec  push    rbp
0x18001fbee  push    rbx
0x18001fbef  push    rsi
0x18001fbf0  push    rdi
0x18001fbf1  push    r12
0x18001fbf3  push    r14
0x18001fbf5  push    r15
0x18001fbf7  lea     rbp, [rsp-30h]
0x18001fbfc  sub     rsp, 130h
0x18001fc03  mov     rax, cs:__security_cookie
0x18001fc0a  xor     rax, rsp
0x18001fc0d  mov     [rbp+60h+var_40], rax
0x18001fc11  mov     sil, r9b
0x18001fc14  mov     r14, r8
0x18001fc17  mov     rbx, rdx
0x18001fc1a  mov     rdi, rcx
0x18001fc1d  xorps   xmm1, xmm1
0x18001fc20  movdqu  [rbp+60h+var_D0], xmm1
0x18001fc25  xor     r12d, r12d
0x18001fc28  mov     [rbp+60h+var_C0], r12
0x18001fc2c  lea     rdx, [rbp+60h+var_D0]
0x18001fc30  xor     ecx, ecx; hModule
0x18001fc32  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x18001fc37  nop
0x18001fc38  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18001fc3d  mov     rcx, rax
0x18001fc40  test    rax, rax
0x18001fc43  jz      loc_18001FFEB
0x18001fc49  mov     rax, [rax]
0x18001fc4c  mov     rax, [rax+18h]
0x18001fc50  call    cs:__guard_dispatch_icall_fptr
0x18001fc56  add     rax, 18h
0x18001fc5a  mov     [rsp+160h+lpCommandLine], rax
0x18001fc5f  mov     r9, rdi
0x18001fc62  mov     r8, qword ptr [rbp+60h+var_D0]
0x18001fc66  lea     rdx, aSMergeS; "\"%s\" merge \"%s\""
0x18001fc6d  lea     rcx, [rsp+160h+lpCommandLine]
0x18001fc72  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001fc77  mov     rdi, [rbx+8]
0x18001fc7b  mov     rbx, [rbx]
0x18001fc7e  jmp     short loc_18001FC98
0x18001fc80  mov     r8, [rbx]
0x18001fc83  lea     rdx, aS_4; " \"%s\""
0x18001fc8a  lea     rcx, [rsp+160h+lpCommandLine]
0x18001fc8f  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001fc94  add     rbx, 8
0x18001fc98  cmp     rbx, rdi
0x18001fc9b  jnz     short loc_18001FC80
0x18001fc9d  call    cs:__imp_GetEnvironmentStringsW
0x18001fca3  mov     rdi, rax
0x18001fca6  test    rax, rax
0x18001fca9  jnz     short loc_18001FCBB
0x18001fcab  mov     r15d, 8000FFFFh
0x18001fcb1  mov     rbx, [rsp+160h+lpCommandLine]
0x18001fcb6  jmp     loc_18001FF8B
0x18001fcbb  mov     ebx, r12d
0x18001fcbe  lea     rcx, [rax+2]
0x18001fcc2  cmp     [rax], r12w
0x18001fcc6  mov     rax, rcx
0x18001fcc9  jnz     short loc_18001FCD1
0x18001fccb  cmp     [rcx], r12w
0x18001fccf  jz      short loc_18001FCD5
0x18001fcd1  inc     ebx
0x18001fcd3  jmp     short loc_18001FCBE
0x18001fcd5  inc     ebx
0x18001fcd7  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18001fcdc  mov     rcx, rax
0x18001fcdf  test    rax, rax
0x18001fce2  jz      loc_18001FFF6
0x18001fce8  mov     rax, [rax]
0x18001fceb  mov     r8d, 2
0x18001fcf1  mov     edx, ebx
0x18001fcf3  mov     rax, [rax]
0x18001fcf6  call    cs:__guard_dispatch_icall_fptr
0x18001fcfc  test    rax, rax
0x18001fcff  jz      loc_18001FFDA
0x18001fd05  lea     rcx, [rax+18h]; void *
0x18001fd09  mov     [rsp+160h+var_110], rcx
0x18001fd0e  test    ebx, ebx
0x18001fd10  js      loc_18001FFE0
0x18001fd16  cmp     ebx, [rcx-0Ch]
0x18001fd19  jg      loc_18001FFE0
0x18001fd1f  mov     [rcx-10h], ebx
0x18001fd22  movsxd  rax, ebx
0x18001fd25  lea     r8, [rax+rax]; Size
0x18001fd29  mov     [r8+rcx], r12w
0x18001fd2e  test    r8, r8
0x18001fd31  jz      short loc_18001FD59
0x18001fd33  test    rcx, rcx
0x18001fd36  jnz     short loc_18001FD4C
0x18001fd38  call    cs:__imp__errno
0x18001fd3e  mov     dword ptr [rax], 16h
0x18001fd44  call    cs:__imp__invalid_parameter_noinfo
0x18001fd4a  jmp     short loc_18001FD59
0x18001fd4c  lfence
0x18001fd4f  mov     rdx, rdi; Src
0x18001fd52  call    cs:__imp_memcpy
0x18001fd58  nop
0x18001fd59  mov     rcx, rdi; penv
0x18001fd5c  call    cs:__imp_FreeEnvironmentStringsW
0x18001fd62  mov     r9, r14
0x18001fd65  lea     r8, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x18001fd6c  lea     rdx, aSS_1; "%s=%s"
0x18001fd73  lea     rcx, [rsp+160h+var_110]
0x18001fd78  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001fd7d  xor     edx, edx
0x18001fd7f  lea     rcx, [rsp+160h+var_110]
0x18001fd84  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001fd89  test    sil, sil
0x18001fd8c  jz      short loc_18001FDB2
0x18001fd8e  lea     r8, aDiaghubDatainj; "DIAGHUB_DataInjectOnly"
0x18001fd95  lea     rdx, aS1; "%s=1"
0x18001fd9c  lea     rcx, [rsp+160h+var_110]
0x18001fda1  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001fda6  xor     edx, edx
0x18001fda8  lea     rcx, [rsp+160h+var_110]
0x18001fdad  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001fdb2  xor     edx, edx
0x18001fdb4  lea     rcx, [rsp+160h+var_110]
0x18001fdb9  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001fdbe  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001fdc5  add     rcx, 38h ; '8'; this
0x18001fdc9  mov     rbx, [rsp+160h+lpCommandLine]
0x18001fdce  mov     r9, rbx
0x18001fdd1  lea     r8, aMergingOutOfPr; "Merging out-of-proc (%s)"
0x18001fdd8  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001fddf  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001fde4  mov     [rbp+60h+StartupInfo.cb], 68h ; 'h'
0x18001fdeb  xor     edx, edx; Val
0x18001fded  lea     r8d, [rdx+60h]; Size
0x18001fdf1  lea     rcx, [rbp+60h+StartupInfo.lpReserved]; void *
0x18001fdf5  call    memset_0
0x18001fdfa  xorps   xmm0, xmm0
0x18001fdfd  xor     eax, eax
0x18001fdff  movups  xmmword ptr [rsp+160h+ProcessInformation.hProcess], xmm0
0x18001fe04  mov     qword ptr [rbp+60h+ProcessInformation.dwProcessId], rax
0x18001fe08  mov     rsi, [rsp+160h+var_110]
0x18001fe0d  cmp     dword ptr [rsi-8], 1
0x18001fe11  jle     short loc_18001FE25
0x18001fe13  mov     edx, [rsi-10h]
0x18001fe16  lea     rcx, [rsp+160h+var_110]
0x18001fe1b  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18001fe20  mov     rsi, [rsp+160h+var_110]
0x18001fe25  cmp     dword ptr [rbx-8], 1
0x18001fe29  jle     short loc_18001FE3D
0x18001fe2b  mov     edx, [rbx-10h]
0x18001fe2e  lea     rcx, [rsp+160h+lpCommandLine]
0x18001fe33  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18001fe38  mov     rbx, [rsp+160h+lpCommandLine]
0x18001fe3d  lea     rax, [rsp+160h+ProcessInformation]
0x18001fe42  mov     [rsp+160h+lpProcessInformation], rax; lpProcessInformation
0x18001fe47  lea     rax, [rbp+60h+StartupInfo]
0x18001fe4b  mov     [rsp+160h+lpStartupInfo], rax; lpStartupInfo
0x18001fe50  mov     [rsp+160h+lpCurrentDirectory], r12; lpCurrentDirectory
0x18001fe55  mov     [rsp+160h+lpEnvironment], rsi; lpEnvironment
0x18001fe5a  mov     [rsp+160h+dwCreationFlags], 400h; dwCreationFlags
0x18001fe62  mov     [rsp+160h+bInheritHandles], r12d; bInheritHandles
0x18001fe67  xor     r9d, r9d; lpThreadAttributes
0x18001fe6a  xor     r8d, r8d; lpProcessAttributes
0x18001fe6d  mov     rdx, rbx; lpCommandLine
0x18001fe70  xor     ecx, ecx; lpApplicationName
0x18001fe72  call    cs:__imp_CreateProcessW
0x18001fe78  test    eax, eax
0x18001fe7a  jnz     short loc_18001FE98
0x18001fe7c  call    cs:__imp_GetLastError
0x18001fe82  movzx   r15d, ax
0x18001fe86  or      r15d, 80070000h
0x18001fe8d  test    eax, eax
0x18001fe8f  cmovle  r15d, eax
0x18001fe93  jmp     loc_18001FF66
0x18001fe98  mov     rdi, [rsp+160h+ProcessInformation.hProcess]
0x18001fe9d  mov     [rsp+160h+var_100], rdi
0x18001fea2  mov     r14, [rsp+160h+ProcessInformation.hThread]
0x18001fea7  mov     [rsp+160h+var_F8], r14
0x18001feac  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001feb3  add     rcx, 38h ; '8'; this
0x18001feb7  mov     r9d, [rbp+60h+ProcessInformation.dwProcessId]
0x18001febb  lea     r8, aWaitingOnMerge; "Waiting on merge running in process wit"...
0x18001fec2  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001fec9  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001fece  mov     r15d, 1D4C0h
0x18001fed4  jmp     short loc_18001FF03
0x18001fed6  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001fedd  add     rcx, 38h ; '8'; this
0x18001fee1  mov     rax, [rcx+8]
0x18001fee5  cmp     [rcx], rax
0x18001fee8  jz      short loc_18001FF03
0x18001feea  mov     r9d, 2
0x18001fef0  lea     r8, aMergeIsNotComp; "Merge is not complete after waiting for"...
0x18001fef7  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001fefe  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001ff03  mov     edx, r15d; dwMilliseconds
0x18001ff06  mov     rcx, rdi; hHandle
0x18001ff09  call    cs:__imp_WaitForSingleObject
0x18001ff0f  cmp     eax, 102h
0x18001ff14  jz      short loc_18001FED6
0x18001ff16  cmp     eax, 0FFFFFFFFh
0x18001ff19  jnz     short loc_18001FF23
0x18001ff1b  call    cs:__imp_GetLastError
0x18001ff21  jmp     short loc_18001FF37
0x18001ff23  lea     rdx, [rbp+60h+ExitCode]; lpExitCode
0x18001ff27  mov     rcx, rdi; hProcess
0x18001ff2a  call    cs:__imp_GetExitCodeProcess
0x18001ff30  test    eax, eax
0x18001ff32  jz      short loc_18001FF1B
0x18001ff34  mov     eax, [rbp+60h+ExitCode]
0x18001ff37  movzx   r15d, ax
0x18001ff3b  or      r15d, 80070000h
0x18001ff42  test    eax, eax
0x18001ff44  cmovle  r15d, eax
0x18001ff48  test    r14, r14
0x18001ff4b  jz      short loc_18001FF57
0x18001ff4d  mov     rcx, r14; hObject
0x18001ff50  call    cs:__imp_CloseHandle
0x18001ff56  nop
0x18001ff57  test    rdi, rdi
0x18001ff5a  jz      short loc_18001FF66
0x18001ff5c  mov     rcx, rdi; hObject
0x18001ff5f  call    cs:__imp_CloseHandle
0x18001ff65  nop
0x18001ff66  lea     rdx, [rsi-18h]
0x18001ff6a  or      eax, 0FFFFFFFFh
0x18001ff6d  lock xadd [rdx+10h], eax
0x18001ff72  sub     eax, 1
0x18001ff75  jg      short loc_18001FF8B
0x18001ff77  lfence
0x18001ff7a  mov     rcx, [rdx]
0x18001ff7d  mov     rax, [rcx]
0x18001ff80  mov     rax, [rax+8]
0x18001ff84  call    cs:__guard_dispatch_icall_fptr
0x18001ff8a  nop
0x18001ff8b  lea     rdx, [rbx-18h]
0x18001ff8f  or      eax, 0FFFFFFFFh
0x18001ff92  lock xadd [rdx+10h], eax
0x18001ff97  sub     eax, 1
0x18001ff9a  jg      short loc_18001FFB0
0x18001ff9c  lfence
0x18001ff9f  mov     rcx, [rdx]
0x18001ffa2  mov     r8, [rcx]
0x18001ffa5  mov     rax, [r8+8]
0x18001ffa9  call    cs:__guard_dispatch_icall_fptr
0x18001ffaf  nop
0x18001ffb0  lea     rcx, [rbp+60h+var_D0]
0x18001ffb4  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001ffb9  mov     eax, r15d
0x18001ffbc  mov     rcx, [rbp+60h+var_40]
0x18001ffc0  xor     rcx, rsp; StackCookie
0x18001ffc3  call    __security_check_cookie
0x18001ffc8  add     rsp, 130h
0x18001ffcf  pop     r15
0x18001ffd1  pop     r14
0x18001ffd3  pop     r12
0x18001ffd5  pop     rdi
0x18001ffd6  pop     rsi
0x18001ffd7  pop     rbx
0x18001ffd8  pop     rbp
0x18001ffd9  retn
0x18001ffda  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x18001ffe0  mov     ecx, 80070057h; int
0x18001ffe5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001ffeb  mov     ecx, 80004005h; int
0x18001fff0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001fff6  mov     ecx, 80004005h; int
0x18001fffb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
