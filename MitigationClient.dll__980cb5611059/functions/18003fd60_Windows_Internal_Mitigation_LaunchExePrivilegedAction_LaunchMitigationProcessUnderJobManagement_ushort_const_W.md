# Windows::Internal::Mitigation::LaunchExePrivilegedAction::LaunchMitigationProcessUnderJobManagement(ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ulong)

- ea: `0x18003fd60`
- end: `0x1800401db`
- name: `?LaunchMitigationProcessUnderJobManagement@LaunchExePrivilegedAction@Mitigation@Internal@Windows@@YAJPEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@34@1K@Z`
- size: `1147`
- prototype: `__int64 __fastcall(unsigned __int16 *, _QWORD *, LPWSTR *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180040220`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x18000e11c`
- `0x18001206c`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x180019ecc`
- `0x18002ab60`
- `0x18003fd60`
- `0x180040740`
- `0x180042ac8`
- `0x180042edc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ffe6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040085`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040122`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ffe6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040085`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800400b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004016b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800400b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004016b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003fecb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003fecb`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003ff5e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180040151`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003ff5e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180040151`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180040106`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180040106`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18003fe1e`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18003fe1e`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1800400a8`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1800400a8`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x180040054`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x180040054`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18003ff1f`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18003ff1f`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18003fdc4`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18003fdc4`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18003ff7c`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18004000f`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18003ff7c`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18004000f`

## string_xrefs

- `0x18003fe5a`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x18003fedc`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x180040063`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Internal::Mitigation::LaunchExePrivilegedAction::LaunchMitigationProcessUnderJobManagement(
        unsigned __int16 *a1,
        _QWORD *a2,
        LPWSTR *a3,
        int a4)
{
  const WCHAR *v8; // rax
  HANDLE JobObjectW; // r15
  unsigned int LastError; // ebx
  __int64 v11; // rdx
  struct MitigationContext *MitigationContext; // rbx
  signed int v13; // eax
  const char *v14; // r9
  char *v15; // rbx
  char v16; // r13
  signed int v17; // eax
  signed int v18; // eax
  DWORD v19; // r12d
  DWORD v20; // r14d
  signed int v21; // eax
  const char *v22; // r9
  __int64 v23; // rdx
  signed int v24; // eax
  signed int v25; // eax
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 CycleTime; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hThread; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hProcess; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v33; // [rsp+88h] [rbp-78h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v35[6]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v36[32]; // [rsp+130h] [rbp+30h] BYREF
  int JobObjectInformation; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v38[12]; // [rsp+154h] [rbp+54h] BYREF
  int v39; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  std::wstring::wstring(v36, L"Mitigation");
  std::wstring::append(v36, *a2);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
  JobObjectW = CreateJobObjectW(0, v8);
  v33 = JobObjectW;
  if ( !JobObjectW )
  {
    LastError = -2147024882;
    v11 = 174;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
      (const char *)LastError,
      bInheritHandles);
    goto LABEL_47;
  }
  MitigationContext = MitigationExecutionContext::GetMitigationContext(a1);
  JobObjectInformation = 0;
  memset_0(v38, 0, 0x8Cu);
  v39 = 0x2000;
  if ( SetInformationJobObject(JobObjectW, JobObjectExtendedLimitInformation, &JobObjectInformation, 0x90u) )
  {
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    if ( !CreateProcessW(0, *a3, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xD0,
                    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
                    v14);
      goto LABEL_47;
    }
    v15 = (char *)MitigationContext + 344;
    hProcess = ProcessInformation.hProcess;
    hThread = ProcessInformation.hThread;
    ExitCode = 0;
    CycleTime = 0;
    v16 = 1;
    if ( !AssignProcessToJobObject(JobObjectW, ProcessInformation.hProcess) )
    {
      v16 = 0;
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      MitigationExecutionContext::DispatchEvent(a1, 6, (unsigned int)v17);
      if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
      {
        if ( ExitCode != 259 )
        {
          if ( !QueryProcessCycleTime(ProcessInformation.hProcess, &CycleTime) )
          {
            v18 = GetLastError();
            if ( v18 > 0 )
              v18 = (unsigned __int16)v18 | 0x80070000;
            MitigationExecutionContext::DispatchEvent(a1, 9, (unsigned int)v18);
          }
          TSExecutionState::SetExitCode((TSExecutionState *)v15, ExitCode);
          *((_QWORD *)v15 + 5) = CycleTime;
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
          LastError = 0;
          goto LABEL_47;
        }
      }
    }
    v19 = 1000 * a4;
    v20 = WaitForSingleObject(ProcessInformation.hProcess, 1000 * a4);
    memset(v35, 0, sizeof(v35));
    if ( QueryProcessCycleTime(ProcessInformation.hProcess, &CycleTime) )
    {
      *((_QWORD *)v15 + 5) = CycleTime;
    }
    else
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      MitigationExecutionContext::DispatchEvent(a1, 9, (unsigned int)v21);
    }
    if ( v16 )
    {
      if ( !TerminateJobObject(JobObjectW, 0x2022u) )
      {
        v23 = 262;
LABEL_29:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v23,
                      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
                      v22);
LABEL_46:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        goto LABEL_47;
      }
      v20 = WaitForSingleObject(ProcessInformation.hProcess, v19);
      if ( QueryInformationJobObject(JobObjectW, JobObjectBasicAccountingInformation, v35, 0x30u, 0) )
      {
        *((_QWORD *)v15 + 6) = v35[0];
        *((_QWORD *)v15 + 7) = v35[1];
        *((_DWORD *)v15 + 16) = HIDWORD(v35[4]);
        *(_QWORD *)(v15 + 68) = v35[5];
      }
      else
      {
        v24 = GetLastError();
        if ( v24 > 0 )
          v24 = (unsigned __int16)v24 | 0x80070000;
        MitigationExecutionContext::DispatchEvent(a1, 8, (unsigned int)v24);
      }
    }
    else if ( v20 )
    {
      if ( !TerminateProcess(ProcessInformation.hProcess, 0x2022u) )
      {
        v23 = 279;
        goto LABEL_29;
      }
      v20 = WaitForSingleObject(ProcessInformation.hProcess, v19);
    }
    if ( v20 == 258 )
      MitigationExecutionContext::DispatchEvent(a1, 10, 2147950626LL);
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      TSExecutionState::SetExitCode((TSExecutionState *)v15, ExitCode);
      LastError = 0;
    }
    else
    {
      v25 = GetLastError();
      LastError = v25;
      if ( v25 > 0 )
        LastError = (unsigned __int16)v25 | 0x80070000;
      MitigationExecutionContext::DispatchEvent(a1, 7, LastError);
    }
    goto LABEL_46;
  }
  v13 = GetLastError();
  LastError = v13;
  if ( v13 > 0 )
    LastError = (unsigned __int16)v13 | 0x80070000;
  MitigationExecutionContext::DispatchEvent(a1, 19, LastError);
  if ( (LastError & 0x80000000) != 0 )
  {
    v11 = 188;
    goto LABEL_8;
  }
LABEL_47:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
  std::wstring::_Tidy_deallocate(v36);
  return LastError;
}

```

## disassembly

```asm
0x18003fd60  push    rbp
0x18003fd62  push    rbx
0x18003fd63  push    rsi
0x18003fd64  push    rdi
0x18003fd65  push    r12
0x18003fd67  push    r13
0x18003fd69  push    r14
0x18003fd6b  push    r15
0x18003fd6d  lea     rbp, [rsp-0F8h]
0x18003fd75  sub     rsp, 1F8h
0x18003fd7c  mov     rax, cs:__security_cookie
0x18003fd83  xor     rax, rsp
0x18003fd86  mov     [rbp+130h+var_50], rax
0x18003fd8d  mov     r14d, r9d
0x18003fd90  mov     rdi, r8
0x18003fd93  mov     rbx, rdx
0x18003fd96  mov     rsi, rcx
0x18003fd99  lea     rdx, aMitigation; "Mitigation"
0x18003fda0  lea     rcx, [rbp+130h+var_100]
0x18003fda4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003fda9  nop
0x18003fdaa  mov     rdx, [rbx]
0x18003fdad  lea     rcx, [rbp+130h+var_100]
0x18003fdb1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003fdb6  lea     rcx, [rbp+130h+var_100]
0x18003fdba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003fdbf  mov     rdx, rax; lpName
0x18003fdc2  xor     ecx, ecx; lpJobAttributes
0x18003fdc4  call    cs:__imp_CreateJobObjectW
0x18003fdca  mov     r15, rax
0x18003fdcd  mov     [rbp+130h+var_1A8], rax
0x18003fdd1  xor     r12d, r12d
0x18003fdd4  test    rax, rax
0x18003fdd7  jnz     short loc_18003FDE5
0x18003fdd9  mov     ebx, 8007000Eh
0x18003fdde  mov     edx, 0AEh
0x18003fde3  jmp     short loc_18003FE5A
0x18003fde5  mov     rcx, rsi; unsigned __int16 *
0x18003fde8  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@PEBG@Z; MitigationExecutionContext::GetMitigationContext(ushort const *)
0x18003fded  mov     rbx, rax
0x18003fdf0  mov     [rbp+130h+JobObjectInformation], r12d
0x18003fdf4  xor     edx, edx; Val
0x18003fdf6  mov     r8d, 8Ch; Size
0x18003fdfc  lea     rcx, [rbp+130h+var_DC]; void *
0x18003fe00  call    memset_0
0x18003fe05  mov     [rbp+130h+var_D0], 2000h
0x18003fe0c  mov     r9d, 90h; cbJobObjectInformationLength
0x18003fe12  lea     r8, [rbp+130h+JobObjectInformation]; lpJobObjectInformation
0x18003fe16  mov     edx, 9; JobObjectInformationClass
0x18003fe1b  mov     rcx, r15; hJob
0x18003fe1e  call    cs:__imp_SetInformationJobObject
0x18003fe24  test    eax, eax
0x18003fe26  jnz     short loc_18003FE75
0x18003fe28  call    cs:__imp_GetLastError
0x18003fe2e  mov     ebx, eax
0x18003fe30  test    eax, eax
0x18003fe32  jle     short loc_18003FE3D
0x18003fe34  movzx   ebx, ax
0x18003fe37  or      ebx, 80070000h
0x18003fe3d  mov     r8d, ebx
0x18003fe40  mov     edx, 13h
0x18003fe45  mov     rcx, rsi
0x18003fe48  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x18003fe4d  test    ebx, ebx
0x18003fe4f  jns     loc_1800401A3
0x18003fe55  mov     edx, 0BCh; void *
0x18003fe5a  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003fe61  mov     r9d, ebx; char *
0x18003fe64  mov     rcx, [rbp+138h]; this
0x18003fe6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fe70  jmp     loc_1800401A3
0x18003fe75  xorps   xmm0, xmm0
0x18003fe78  xor     eax, eax
0x18003fe7a  movups  xmmword ptr [rsp+230h+ProcessInformation.hProcess], xmm0
0x18003fe7f  mov     qword ptr [rbp+130h+ProcessInformation.dwProcessId], rax
0x18003fe83  xor     edx, edx; Val
0x18003fe85  lea     r8d, [rax+64h]; Size
0x18003fe89  lea     rcx, [rbp+130h+StartupInfo+4]; void *
0x18003fe8d  call    memset_0
0x18003fe92  mov     [rbp+130h+StartupInfo.cb], 68h ; 'h'
0x18003fe99  lea     rax, [rsp+230h+ProcessInformation]
0x18003fe9e  mov     [rsp+230h+lpProcessInformation], rax; lpProcessInformation
0x18003fea3  lea     rax, [rbp+130h+StartupInfo]
0x18003fea7  mov     [rsp+230h+lpStartupInfo], rax; lpStartupInfo
0x18003feac  mov     [rsp+230h+lpCurrentDirectory], r12; lpCurrentDirectory
0x18003feb1  mov     [rsp+230h+lpEnvironment], r12; lpEnvironment
0x18003feb6  mov     [rsp+230h+dwCreationFlags], r12d; dwCreationFlags
0x18003febb  mov     [rsp+230h+bInheritHandles], r12d; bInheritHandles
0x18003fec0  xor     r9d, r9d; lpThreadAttributes
0x18003fec3  xor     r8d, r8d; lpProcessAttributes
0x18003fec6  mov     rdx, [rdi]; lpCommandLine
0x18003fec9  xor     ecx, ecx; lpApplicationName
0x18003fecb  call    cs:__imp_CreateProcessW
0x18003fed1  test    eax, eax
0x18003fed3  jnz     short loc_18003FEF4
0x18003fed5  mov     rcx, [rbp+138h]; this
0x18003fedc  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003fee3  mov     edx, 0D0h; void *
0x18003fee8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003feed  mov     ebx, eax
0x18003feef  jmp     loc_1800401A3
0x18003fef4  add     rbx, 158h
0x18003fefb  mov     rdx, [rsp+230h+ProcessInformation.hProcess]; hProcess
0x18003ff00  mov     [rsp+230h+var_1C8], rdx
0x18003ff05  mov     rax, [rsp+230h+ProcessInformation.hThread]
0x18003ff0a  mov     [rsp+230h+var_1D0], rax
0x18003ff0f  mov     [rsp+230h+ExitCode], r12d
0x18003ff14  mov     [rsp+230h+CycleTime], r12
0x18003ff19  mov     r13b, 1
0x18003ff1c  mov     rcx, r15; hJob
0x18003ff1f  call    cs:__imp_AssignProcessToJobObject
0x18003ff25  mov     edi, 80070000h
0x18003ff2a  test    eax, eax
0x18003ff2c  jnz     loc_18003FFD7
0x18003ff32  mov     r13b, r12b
0x18003ff35  call    cs:__imp_GetLastError
0x18003ff3b  test    eax, eax
0x18003ff3d  jle     short loc_18003FF44
0x18003ff3f  movzx   eax, ax
0x18003ff42  or      eax, edi
0x18003ff44  mov     r8d, eax
0x18003ff47  mov     edx, 6
0x18003ff4c  mov     rcx, rsi
0x18003ff4f  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x18003ff54  lea     rdx, [rsp+230h+ExitCode]; lpExitCode
0x18003ff59  mov     rcx, [rsp+230h+ProcessInformation.hProcess]; hProcess
0x18003ff5e  call    cs:__imp_GetExitCodeProcess
0x18003ff64  test    eax, eax
0x18003ff66  jz      short loc_18003FFD7
0x18003ff68  cmp     [rsp+230h+ExitCode], 103h
0x18003ff70  jz      short loc_18003FFD7
0x18003ff72  lea     rdx, [rsp+230h+CycleTime]; CycleTime
0x18003ff77  mov     rcx, [rsp+230h+ProcessInformation.hProcess]; ProcessHandle
0x18003ff7c  call    cs:__imp_QueryProcessCycleTime
0x18003ff82  test    eax, eax
0x18003ff84  jnz     short loc_18003FFA5
0x18003ff86  call    cs:__imp_GetLastError
0x18003ff8c  test    eax, eax
0x18003ff8e  jle     short loc_18003FF95
0x18003ff90  movzx   eax, ax
0x18003ff93  or      eax, edi
0x18003ff95  mov     r8d, eax
0x18003ff98  mov     edx, 9
0x18003ff9d  mov     rcx, rsi
0x18003ffa0  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x18003ffa5  mov     edx, [rsp+230h+ExitCode]; unsigned int
0x18003ffa9  mov     rcx, rbx; this
0x18003ffac  call    ?SetExitCode@TSExecutionState@@QEAAXK@Z; TSExecutionState::SetExitCode(ulong)
0x18003ffb1  mov     rcx, [rsp+230h+CycleTime]
0x18003ffb6  mov     [rbx+28h], rcx
0x18003ffba  lea     rcx, [rsp+230h+var_1D0]
0x18003ffbf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003ffc4  nop
0x18003ffc5  lea     rcx, [rsp+230h+var_1C8]
0x18003ffca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003ffcf  mov     ebx, r12d
0x18003ffd2  jmp     loc_1800401A3
0x18003ffd7  imul    r12d, r14d, 3E8h
0x18003ffde  mov     edx, r12d; dwMilliseconds
0x18003ffe1  mov     rcx, [rsp+230h+ProcessInformation.hProcess]; hHandle
0x18003ffe6  call    cs:__imp_WaitForSingleObject
0x18003ffec  mov     r14d, eax
0x18003ffef  mov     dword ptr [rbp+130h+var_130], 0
0x18003fff6  xorps   xmm0, xmm0
0x18003fff9  movups  xmmword ptr [rbp+130h+var_130+4], xmm0
0x18003fffd  movups  [rbp+130h+var_11C], xmm0
0x180040001  movups  [rbp+130h+var_11C+0Ch], xmm0
0x180040005  lea     rdx, [rsp+230h+CycleTime]; CycleTime
0x18004000a  mov     rcx, [rsp+230h+ProcessInformation.hProcess]; ProcessHandle
0x18004000f  call    cs:__imp_QueryProcessCycleTime
0x180040015  test    eax, eax
0x180040017  jnz     short loc_18004003A
0x180040019  call    cs:__imp_GetLastError
0x18004001f  test    eax, eax
0x180040021  jle     short loc_180040028
0x180040023  movzx   eax, ax
0x180040026  or      eax, edi
0x180040028  mov     r8d, eax
0x18004002b  mov     edx, 9
0x180040030  mov     rcx, rsi
0x180040033  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x180040038  jmp     short loc_180040043
0x18004003a  mov     rax, [rsp+230h+CycleTime]
0x18004003f  mov     [rbx+28h], rax
0x180040043  test    r13b, r13b
0x180040046  jz      loc_1800400F7
0x18004004c  mov     edx, 2022h; uExitCode
0x180040051  mov     rcx, r15; hJob
0x180040054  call    cs:__imp_TerminateJobObject
0x18004005a  test    eax, eax
0x18004005c  jnz     short loc_18004007D
0x18004005e  mov     edx, 106h; void *
0x180040063  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18004006a  mov     rcx, [rbp+138h]; this
0x180040071  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040076  mov     ebx, eax
0x180040078  jmp     loc_18004018D
0x18004007d  mov     edx, r12d; dwMilliseconds
0x180040080  mov     rcx, [rsp+230h+ProcessInformation.hProcess]; hHandle
0x180040085  call    cs:__imp_WaitForSingleObject
0x18004008b  mov     r14d, eax
0x18004008e  mov     qword ptr [rsp+230h+bInheritHandles], 0; lpReturnLength
0x180040097  mov     r9d, 30h ; '0'; cbJobObjectInformationLength
0x18004009d  lea     r8, [rbp+130h+var_130]; lpJobObjectInformation
0x1800400a1  lea     edx, [r9-2Fh]; JobObjectInformationClass
0x1800400a5  mov     rcx, r15; hJob
0x1800400a8  call    cs:__imp_QueryInformationJobObject
0x1800400ae  test    eax, eax
0x1800400b0  jnz     short loc_1800400D3
0x1800400b2  call    cs:__imp_GetLastError
0x1800400b8  test    eax, eax
0x1800400ba  jle     short loc_1800400C1
0x1800400bc  movzx   eax, ax
0x1800400bf  or      eax, edi
0x1800400c1  mov     r8d, eax
0x1800400c4  mov     edx, 8
0x1800400c9  mov     rcx, rsi
0x1800400cc  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x1800400d1  jmp     short loc_18004012B
0x1800400d3  mov     rax, [rbp+130h+var_130]
0x1800400d7  mov     [rbx+30h], rax
0x1800400db  mov     rax, [rbp+130h+var_128]
0x1800400df  mov     [rbx+38h], rax
0x1800400e3  mov     eax, [rbp+130h+var_10C]
0x1800400e6  mov     [rbx+40h], eax
0x1800400e9  mov     eax, [rbp+130h+var_108]
0x1800400ec  mov     [rbx+44h], eax
0x1800400ef  mov     eax, [rbp+130h+var_104]
0x1800400f2  mov     [rbx+48h], eax
0x1800400f5  jmp     short loc_18004012B
0x1800400f7  test    r14d, r14d
0x1800400fa  jz      short loc_18004012B
0x1800400fc  mov     edx, 2022h; uExitCode
0x180040101  mov     rcx, [rsp+230h+ProcessInformation.hProcess]; hProcess
0x180040106  call    cs:__imp_TerminateProcess
0x18004010c  test    eax, eax
0x18004010e  jnz     short loc_18004011A
0x180040110  mov     edx, 117h
0x180040115  jmp     loc_180040063
0x18004011a  mov     edx, r12d; dwMilliseconds
0x18004011d  mov     rcx, [rsp+230h+ProcessInformation.hProcess]; hHandle
0x180040122  call    cs:__imp_WaitForSingleObject
0x180040128  mov     r14d, eax
0x18004012b  cmp     r14d, 102h
0x180040132  jnz     short loc_180040147
0x180040134  mov     edx, 0Ah
0x180040139  mov     r8d, 80072022h
0x18004013f  mov     rcx, rsi
0x180040142  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x180040147  lea     rdx, [rsp+230h+ExitCode]; lpExitCode
0x18004014c  mov     rcx, [rsp+230h+ProcessInformation.hProcess]; hProcess
0x180040151  call    cs:__imp_GetExitCodeProcess
0x180040157  test    eax, eax
0x180040159  jz      short loc_18004016B
0x18004015b  mov     edx, [rsp+230h+ExitCode]; unsigned int
0x18004015f  mov     rcx, rbx; this
0x180040162  call    ?SetExitCode@TSExecutionState@@QEAAXK@Z; TSExecutionState::SetExitCode(ulong)
0x180040167  xor     ebx, ebx
0x180040169  jmp     short loc_18004018D
0x18004016b  call    cs:__imp_GetLastError
0x180040171  mov     ebx, eax
0x180040173  test    eax, eax
0x180040175  jle     short loc_18004017C
0x180040177  movzx   ebx, ax
0x18004017a  or      ebx, edi
0x18004017c  mov     r8d, ebx
0x18004017f  mov     edx, 7
0x180040184  mov     rcx, rsi
0x180040187  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x18004018c  nop
0x18004018d  lea     rcx, [rsp+230h+var_1D0]
0x180040192  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040197  nop
0x180040198  lea     rcx, [rsp+230h+var_1C8]
0x18004019d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800401a2  nop
0x1800401a3  lea     rcx, [rbp+130h+var_1A8]
0x1800401a7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800401ac  nop
0x1800401ad  lea     rcx, [rbp+130h+var_100]
0x1800401b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800401b6  mov     eax, ebx
0x1800401b8  mov     rcx, [rbp+130h+var_50]
0x1800401bf  xor     rcx, rsp; StackCookie
0x1800401c2  call    __security_check_cookie
0x1800401c7  add     rsp, 1F8h
0x1800401ce  pop     r15
0x1800401d0  pop     r14
0x1800401d2  pop     r13
0x1800401d4  pop     r12
0x1800401d6  pop     rdi
0x1800401d7  pop     rsi
0x1800401d8  pop     rbx
0x1800401d9  pop     rbp
0x1800401da  retn
```
