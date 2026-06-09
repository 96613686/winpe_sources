# CWinSATTaskMangerTask::DoRunWinSAT(ulong &)

- ea: `0x1800209a8`
- end: `0x180020d2b`
- name: `?DoRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEAK@Z`
- size: `899`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this, LPDWORD lpExitCode)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800213a4`

## callees

- `0x1800020f4`
- `0x180004048`
- `0x180008490`
- `0x18000f0e8`
- `0x180013e69`
- `0x18001b790`
- `0x18001bed0`
- `0x1800209a8`
- `0x180021bc0`
- `0x180021f00`
- `0x18002d7ec`
- `0x180033010`

## import_xrefs

- `msvcrt!_time64` at `0x180020ba0`
- `msvcrt!_time64` at `0x180020ba0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020c1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020c1f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020c79`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ca3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180020afd`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180020afd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180020c8f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180020c8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020cd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ce5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020cd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ce5`

## string_xrefs

- `0x180020a0c`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020a75`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020b3b`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020c69`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020a00`: `cannot get system directory`
- `0x180020a69`: `WinSAT command line = '%S'`
- `0x180020bf7`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180020be8`: `Cannot write %s to the registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWinSATTaskMangerTask::DoRunWinSAT(CWinSATTaskMangerTask *this, LPDWORD lpExitCode)
{
  int SystemDirectoryInMString; // edi
  __int64 result; // rax
  unsigned int v6; // edi
  void (__fastcall *v7)(void *, __int64, _QWORD); // rax
  __int64 LastError; // r8
  void (__fastcall *v9)(void *, __int64, __int64); // rax
  __time64_t v10; // rdi
  __int64 v11; // rcx
  unsigned int v12; // eax
  DWORD v13; // eax
  unsigned int v14; // edi
  __int64 v15; // r8
  void (__fastcall *v16)(void *, __int64, __int64); // rax
  __int64 v17; // [rsp+50h] [rbp-B8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+70h] [rbp-98h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v22; // [rsp+120h] [rbp+18h] BYREF
  __int64 v23; // [rsp+128h] [rbp+20h] BYREF

  v19 = -2;
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v17,
      260);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v23,
      260);
    SystemDirectoryInMString = GetSystemDirectoryInMString((__int64)&v17);
    if ( SystemDirectoryInMString < 0 )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 201, "cannot get system directory");
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v23);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v17);
      return (unsigned int)SystemDirectoryInMString;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      &v23,
      L"%s\\winsat.exe formal -log -cancelevent %s",
      *(_QWORD *)(v17 + 24),
      *(_QWORD *)(*((_QWORD *)this + 15) + 24LL));
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
      209,
      "WinSAT command line = '%S'",
      *(const wchar_t **)(v23 + 24));
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    v6 = CreateProcessW(0, *(LPWSTR *)(v23 + 24), 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation);
    v7 = (void (__fastcall *)(void *, __int64, _QWORD))*((_QWORD *)this + 17);
    if ( v7 )
      v7(&unk_18004A8B0, 10267, v6);
    if ( !v6 )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 231, "cannot start winsat process");
      LastError = GetLastError();
      v9 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
      if ( v9 )
        v9(&unk_18004A8B0, 10269, LastError);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v23);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v17);
      return 2147500037LL;
    }
    v22 = 0;
    v10 = _time64(0);
    if ( CWinSATTaskMangerTask::IncrimentWinSATIdleRunCount(this, &v22) )
    {
      if ( v22 == 1 )
      {
        v12 = RegHelper::WriteQWORDValue(v11, L"FirstIdleRunTimeDate", v10);
        if ( v12 )
          Record_Win32Error_w(
            "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
            0x13Cu,
            v12,
            (char)L"FirstIdleRunTimeDate");
      }
      CWinSATTaskMangerTask::SQMLogWinSATRun(this, v22, v10);
    }
    v13 = WaitForSingleObject(ProcessInformation.hProcess, 0xDE2B0u);
    v14 = -2147467259;
    switch ( v13 )
    {
      case 0xFFFFFFFF:
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 259, "cannot wait for WinSAT, wait failed");
        break;
      case 0x80u:
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 263, "WinSAT process abandoned while waiting");
        break;
      case 0x102u:
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 267, "waiting for WinSAT to finish timed out");
        break;
      default:
        if ( GetExitCodeProcess(ProcessInformation.hProcess, lpExitCode) )
        {
          v14 = 0;
        }
        else
        {
          v15 = GetLastError();
          v16 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
          if ( v16 )
            v16(&unk_18004A8B0, 10269, v15);
        }
        goto LABEL_26;
    }
    SetEvent(*((HANDLE *)this + 14));
LABEL_26:
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v23);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v17);
    result = v14;
  }
  catch ( std::bad_alloc )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 291, "out of memory exception caught");
    if ( *((_QWORD *)this + 17) )
      (*((void (__fastcall **)(void *, __int64, __int64))this + 17))(&unk_18004A8B0, 10269, 8);
    return 2147500037LL;
  }
  catch ( ... )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 295, "unknown exception caught");
    if ( *((_QWORD *)this + 17) )
      (*((void (__fastcall **)(void *, __int64, __int64))this + 17))(&unk_18004A8B0, 10269, 574);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800209a8  mov     rax, rsp
0x1800209ab  mov     [rax+8], rcx
0x1800209af  push    rdi
0x1800209b0  push    r12
0x1800209b2  push    r14
0x1800209b4  sub     rsp, 0F0h
0x1800209bb  mov     [rsp+108h+var_98], 0FFFFFFFFFFFFFFFEh
0x1800209c4  mov     [rax+10h], rbx
0x1800209c8  mov     r14, rdx
0x1800209cb  mov     rbx, rcx
0x1800209ce  mov     edi, 104h
0x1800209d3  mov     edx, edi
0x1800209d5  lea     rcx, [rsp+108h+var_B8]
0x1800209da  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x1800209df  nop
0x1800209e0  mov     edx, edi
0x1800209e2  lea     rcx, [rsp+108h+arg_18]
0x1800209ea  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x1800209ef  nop
0x1800209f0  lea     rcx, [rsp+108h+var_B8]
0x1800209f5  call    ?GetSystemDirectoryInMString@@YAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; GetSystemDirectoryInMString(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x1800209fa  mov     edi, eax
0x1800209fc  test    eax, eax
0x1800209fe  jns     short loc_180020A38
0x180020a00  lea     r8, aCannotGetSyste; "cannot get system directory"
0x180020a07  mov     edx, 0C9h
0x180020a0c  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020a13  call    Log_Text_F
0x180020a18  nop
0x180020a19  lea     rcx, [rsp+108h+arg_18]
0x180020a21  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180020a26  nop
0x180020a27  lea     rcx, [rsp+108h+var_B8]
0x180020a2c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180020a31  mov     eax, edi
0x180020a33  jmp     loc_180020D15
0x180020a38  mov     rax, [rbx+78h]
0x180020a3c  mov     r9, [rax+18h]
0x180020a40  mov     rax, [rsp+108h+var_B8]
0x180020a45  mov     r8, [rax+18h]
0x180020a49  lea     rdx, aSWinsatExeForm; "%s\\winsat.exe formal -log -cancelevent"...
0x180020a50  lea     rcx, [rsp+108h+arg_18]
0x180020a58  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x180020a5d  mov     rax, [rsp+108h+arg_18]
0x180020a65  mov     r9, [rax+18h]
0x180020a69  lea     r8, aWinsatCommandL; "WinSAT command line = '%S'"
0x180020a70  mov     edx, 0D1h
0x180020a75  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020a7c  call    Log_Text_F
0x180020a81  xor     edx, edx; Val
0x180020a83  lea     r8d, [rdx+64h]; Size
0x180020a87  lea     rcx, [rsp+108h+StartupInfo+4]; void *
0x180020a8f  call    memset_0
0x180020a94  xorps   xmm0, xmm0
0x180020a97  xor     eax, eax
0x180020a99  movups  xmmword ptr [rsp+108h+ProcessInformation.hProcess], xmm0
0x180020a9e  mov     qword ptr [rsp+108h+ProcessInformation.dwProcessId], rax
0x180020aa3  lea     rdi, [rsp+108h+StartupInfo]
0x180020aab  lea     edx, [rax+68h]
0x180020aae  mov     ecx, edx
0x180020ab0  rep stosb
0x180020ab2  mov     [rsp+108h+StartupInfo.cb], edx
0x180020ab9  mov     rax, [rsp+108h+arg_18]
0x180020ac1  lea     rcx, [rsp+108h+ProcessInformation]
0x180020ac6  mov     [rsp+108h+lpProcessInformation], rcx; lpProcessInformation
0x180020acb  lea     rcx, [rsp+108h+StartupInfo]
0x180020ad3  mov     [rsp+108h+lpStartupInfo], rcx; lpStartupInfo
0x180020ad8  and     [rsp+108h+var_D0], 0
0x180020ade  and     [rsp+108h+var_D8], 0
0x180020ae4  mov     [rsp+108h+dwCreationFlags], 8000000h; dwCreationFlags
0x180020aec  and     dword ptr [rsp+108h+var_E8], 0
0x180020af1  xor     r9d, r9d; lpThreadAttributes
0x180020af4  xor     r8d, r8d; lpProcessAttributes
0x180020af7  mov     rdx, [rax+18h]; lpCommandLine
0x180020afb  xor     ecx, ecx; lpApplicationName
0x180020afd  call    cs:__imp_CreateProcessW
0x180020b04  nop     dword ptr [rax+rax+00h]
0x180020b09  mov     edi, eax
0x180020b0b  mov     rax, [rbx+88h]
0x180020b12  test    rax, rax
0x180020b15  jz      short loc_180020B2B
0x180020b17  mov     r8d, edi
0x180020b1a  mov     edx, 281Bh
0x180020b1f  lea     rcx, unk_18004A8B0
0x180020b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b2b  test    edi, edi
0x180020b2d  jnz     short loc_180020B96
0x180020b2f  lea     r8, aCannotStartWin; "cannot start winsat process"
0x180020b36  mov     edx, 0E7h
0x180020b3b  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020b42  call    Log_Text_F
0x180020b47  call    cs:__imp_GetLastError
0x180020b4e  nop     dword ptr [rax+rax+00h]
0x180020b53  mov     r8d, eax
0x180020b56  mov     rax, [rbx+88h]
0x180020b5d  test    rax, rax
0x180020b60  jz      short loc_180020B74
0x180020b62  mov     edx, 281Dh
0x180020b67  lea     rcx, unk_18004A8B0
0x180020b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b73  nop
0x180020b74  lea     rcx, [rsp+108h+arg_18]
0x180020b7c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180020b81  nop
0x180020b82  lea     rcx, [rsp+108h+var_B8]
0x180020b87  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180020b8c  mov     eax, 80004005h
0x180020b91  jmp     loc_180020D15
0x180020b96  and     [rsp+108h+arg_10], 0
0x180020b9e  xor     ecx, ecx; Time
0x180020ba0  call    cs:__imp__time64
0x180020ba7  nop     dword ptr [rax+rax+00h]
0x180020bac  mov     rdi, rax
0x180020baf  lea     rdx, [rsp+108h+arg_10]; unsigned int *
0x180020bb7  mov     rcx, rbx; this
0x180020bba  call    ?IncrimentWinSATIdleRunCount@CWinSATTaskMangerTask@@AEAA_NAEAK@Z; CWinSATTaskMangerTask::IncrimentWinSATIdleRunCount(ulong &)
0x180020bbf  test    al, al
0x180020bc1  jz      short loc_180020C15
0x180020bc3  cmp     [rsp+108h+arg_10], 1
0x180020bcb  jnz     short loc_180020C03
0x180020bcd  mov     r8, rdi
0x180020bd0  lea     r12, aFirstidlerunti; "FirstIdleRunTimeDate"
0x180020bd7  mov     rdx, r12
0x180020bda  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x180020bdf  test    eax, eax
0x180020be1  jz      short loc_180020C03
0x180020be3  mov     qword ptr [rsp+108h+var_E8], r12; char
0x180020be8  lea     r9, aCannotWriteSTo; "Cannot write %s to the registry"
0x180020bef  mov     r8d, eax; unsigned int
0x180020bf2  mov     edx, 13Ch; unsigned int
0x180020bf7  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020bfe  call    Record_Win32Error_w
0x180020c03  mov     r8, rdi; unsigned __int64
0x180020c06  mov     edx, [rsp+108h+arg_10]; unsigned int
0x180020c0d  mov     rcx, rbx; this
0x180020c10  call    ?SQMLogWinSATRun@CWinSATTaskMangerTask@@AEAAXK_K@Z; CWinSATTaskMangerTask::SQMLogWinSATRun(ulong,unsigned __int64)
0x180020c15  mov     edx, 0DE2B0h; dwMilliseconds
0x180020c1a  mov     rcx, [rsp+108h+ProcessInformation.hProcess]; hHandle
0x180020c1f  call    cs:__imp_WaitForSingleObject
0x180020c26  nop     dword ptr [rax+rax+00h]
0x180020c2b  mov     edi, 80004005h
0x180020c30  cmp     eax, 0FFFFFFFFh
0x180020c33  jnz     short loc_180020C43
0x180020c35  lea     r8, aCannotWaitForW; "cannot wait for WinSAT, wait failed"
0x180020c3c  mov     edx, 103h
0x180020c41  jmp     short loc_180020C69
0x180020c43  cmp     eax, 80h
0x180020c48  jnz     short loc_180020C58
0x180020c4a  lea     r8, aWinsatProcessA; "WinSAT process abandoned while waiting"
0x180020c51  mov     edx, 107h
0x180020c56  jmp     short loc_180020C69
0x180020c58  cmp     eax, 102h
0x180020c5d  jnz     short loc_180020C87
0x180020c5f  lea     r8, aWaitingForWins; "waiting for WinSAT to finish timed out"
0x180020c66  lea     edx, [rax+9]
0x180020c69  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020c70  call    Log_Text_F
0x180020c75  mov     rcx, [rbx+70h]; hEvent
0x180020c79  call    cs:__imp_SetEvent
0x180020c80  nop     dword ptr [rax+rax+00h]
0x180020c85  jmp     short loc_180020CCF
0x180020c87  mov     rdx, r14; lpExitCode
0x180020c8a  mov     rcx, [rsp+108h+ProcessInformation.hProcess]; hProcess
0x180020c8f  call    cs:__imp_GetExitCodeProcess
0x180020c96  nop     dword ptr [rax+rax+00h]
0x180020c9b  test    eax, eax
0x180020c9d  jz      short loc_180020CA3
0x180020c9f  xor     edi, edi
0x180020ca1  jmp     short loc_180020CCF
0x180020ca3  call    cs:__imp_GetLastError
0x180020caa  nop     dword ptr [rax+rax+00h]
0x180020caf  mov     r8d, eax
0x180020cb2  mov     rax, [rbx+88h]
0x180020cb9  test    rax, rax
0x180020cbc  jz      short loc_180020CCF
0x180020cbe  mov     edx, 281Dh
0x180020cc3  lea     rcx, unk_18004A8B0
0x180020cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ccf  mov     rcx, [rsp+108h+ProcessInformation.hProcess]; hObject
0x180020cd4  call    cs:__imp_CloseHandle
0x180020cdb  nop     dword ptr [rax+rax+00h]
0x180020ce0  mov     rcx, [rsp+108h+ProcessInformation.hThread]; hObject
0x180020ce5  call    cs:__imp_CloseHandle
0x180020cec  nop     dword ptr [rax+rax+00h]
0x180020cf1  nop
0x180020cf2  lea     rcx, [rsp+108h+arg_18]
0x180020cfa  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180020cff  nop
0x180020d00  lea     rcx, [rsp+108h+var_B8]
0x180020d05  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180020d0a  mov     eax, edi
0x180020d0c  jmp     short loc_180020D15
0x180020d0e  jmp     short $+2
0x180020d10  mov     eax, 80004005h
0x180020d15  mov     rbx, [rsp+108h+arg_8]
0x180020d1d  add     rsp, 0F0h
0x180020d24  pop     r14
0x180020d26  pop     r12
0x180020d28  pop     rdi
0x180020d29  retn
```
