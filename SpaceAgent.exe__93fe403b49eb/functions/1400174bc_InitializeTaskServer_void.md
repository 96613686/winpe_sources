# InitializeTaskServer(void)

- ea: `0x1400174bc`
- end: `0x1400176f4`
- name: `?InitializeTaskServer@@YAHXZ`
- size: `568`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140002b98`

## callees

- `0x1400174bc`
- `0x1400176fc`
- `0x1400177d4`
- `0x140019ad8`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140017570`
- `KERNEL32!GetCurrentProcess` at `0x140017570`
- `KERNEL32!LocalFree` at `0x140017655`
- `KERNEL32!LocalFree` at `0x140017655`
- `KERNEL32!EnterCriticalSection` at `0x1400174fe`
- `KERNEL32!EnterCriticalSection` at `0x1400176ad`
- `KERNEL32!EnterCriticalSection` at `0x1400174fe`
- `KERNEL32!EnterCriticalSection` at `0x1400176ad`
- `KERNEL32!LeaveCriticalSection` at `0x140017511`
- `KERNEL32!LeaveCriticalSection` at `0x1400176e7`
- `KERNEL32!LeaveCriticalSection` at `0x140017511`
- `KERNEL32!LeaveCriticalSection` at `0x1400176e7`
- `KERNEL32!CloseHandle` at `0x140017675`
- `KERNEL32!CloseHandle` at `0x140017675`
- `KERNEL32!SetEvent` at `0x140017642`
- `KERNEL32!SetEvent` at `0x140017642`
- `KERNEL32!GetProcessIdOfThread` at `0x14001761a`
- `KERNEL32!GetProcessIdOfThread` at `0x14001761a`
- `KERNEL32!GetCommandLineW` at `0x1400175ce`
- `KERNEL32!GetCommandLineW` at `0x1400175ce`
- `KERNEL32!OpenProcess` at `0x1400175b9`
- `KERNEL32!OpenProcess` at `0x1400175b9`
- `KERNEL32!GetProcessId` at `0x140017625`
- `KERNEL32!GetProcessId` at `0x140017625`
- `KERNEL32!SetLastError` at `0x140017522`
- `KERNEL32!SetLastError` at `0x140017532`
- `KERNEL32!SetLastError` at `0x1400175a4`
- `KERNEL32!SetLastError` at `0x140017636`
- `KERNEL32!SetLastError` at `0x140017522`
- `KERNEL32!SetLastError` at `0x140017532`
- `KERNEL32!SetLastError` at `0x1400175a4`
- `KERNEL32!SetLastError` at `0x140017636`
- `KERNEL32!GetLastError` at `0x140017528`
- `KERNEL32!GetLastError` at `0x1400175ee`
- `KERNEL32!GetLastError` at `0x14001764a`
- `KERNEL32!GetLastError` at `0x140017662`
- `KERNEL32!GetLastError` at `0x140017681`
- `KERNEL32!GetLastError` at `0x140017528`
- `KERNEL32!GetLastError` at `0x1400175ee`
- `KERNEL32!GetLastError` at `0x14001764a`
- `KERNEL32!GetLastError` at `0x140017662`
- `KERNEL32!GetLastError` at `0x140017681`
- `ntdll!NtQueryInformationProcess` at `0x14001758e`
- `ntdll!NtQueryInformationProcess` at `0x14001758e`
- `ntdll!RtlNtStatusToDosError` at `0x14001759c`
- `ntdll!RtlNtStatusToDosError` at `0x14001759c`
- `SHELL32!CommandLineToArgvW` at `0x1400175db`
- `SHELL32!CommandLineToArgvW` at `0x1400175db`

## pseudocode

```c
__int64 InitializeTaskServer(void)
{
  int v0; // ebx
  unsigned int v1; // ebx
  DWORD LastError; // edi
  HANDLE CurrentProcess; // rax
  int InformationProcess; // eax
  DWORD v6; // ebx
  DWORD v7; // eax
  HANDLE v8; // rsi
  const WCHAR *CommandLineW; // rax
  LPWSTR *v10; // r14
  int v11; // r15d
  DWORD v12; // eax
  DWORD ProcessIdOfThread; // ebx
  HLOCAL v14; // r14
  unsigned int v15; // ecx
  BOOL v16; // esi
  int pNumArgs; // [rsp+30h] [rbp-49h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+38h] [rbp-41h] BYREF
  __int128 v19; // [rsp+58h] [rbp-21h]
  void *v20[2]; // [rsp+68h] [rbp-11h] BYREF
  HANDLE hEvent[2]; // [rsp+78h] [rbp-1h]
  HANDLE Thread; // [rsp+88h] [rbp+Fh]

  pNumArgs = 0;
  *(_OWORD *)v20 = 0;
  Thread = 0;
  *(_OWORD *)hEvent = 0;
  EnterCriticalSection(&TaskLock);
  v0 = dword_140027D8C;
  LeaveCriticalSection(&TaskLock);
  if ( v0 )
  {
    v1 = 0;
    SetLastError(0x54Fu);
LABEL_3:
    LastError = GetLastError();
    goto LABEL_4;
  }
  v1 = InitializeTaskServer_AdjustPrivileges();
  if ( !v1 )
    goto LABEL_3;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v19 = 0;
  CurrentProcess = GetCurrentProcess();
  InformationProcess = NtQueryInformationProcess(CurrentProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess >= 0 )
  {
    v6 = DWORD2(v19);
  }
  else
  {
    v6 = 0;
    v7 = RtlNtStatusToDosError(InformationProcess);
    SetLastError(v7);
  }
  v8 = OpenProcess(0x440u, 0, v6);
  if ( !v8 )
  {
    v1 = 0;
    goto LABEL_3;
  }
  CommandLineW = GetCommandLineW();
  v10 = CommandLineToArgvW(CommandLineW, &pNumArgs);
  if ( v10 )
  {
    v11 = InitializeTaskServer_InterpretParameters(v8);
    if ( v11 )
    {
      ProcessIdOfThread = GetProcessIdOfThread(Thread);
      if ( ProcessIdOfThread == GetProcessId(v8) )
      {
        v1 = SetEvent(hEvent[1]);
      }
      else
      {
        v1 = 0;
        SetLastError(0x236u);
      }
    }
    else
    {
      v1 = 0;
    }
    LastError = GetLastError();
    v14 = LocalFree(v10);
    if ( !v1 )
      goto LABEL_21;
    v12 = GetLastError();
    v1 = v14 == 0;
  }
  else
  {
    v11 = 0;
    v1 = 0;
    v12 = GetLastError();
  }
  LastError = v12;
LABEL_21:
  v16 = CloseHandle(v8);
  if ( v1 )
  {
    LastError = GetLastError();
    if ( v16 )
    {
      EnterCriticalSection(&TaskLock);
      dword_140027D8C = 1;
      xmmword_140027AA0 = *(_OWORD *)v20;
      qword_140027AC0 = (__int64)Thread;
      xmmword_140027AB0 = *(_OWORD *)hEvent;
      LeaveCriticalSection(&TaskLock);
      v1 = v16;
      goto LABEL_4;
    }
    v1 = 0;
  }
  if ( v11 )
    CloseMultipleHandles(v15, v20);
LABEL_4:
  SetLastError(LastError);
  return v1;
}

```

## disassembly

```asm
0x1400174bc  push    rbp
0x1400174be  push    rbx
0x1400174bf  push    rsi
0x1400174c0  push    rdi
0x1400174c1  push    r14
0x1400174c3  push    r15
0x1400174c5  lea     rbp, [rsp-2Fh]
0x1400174ca  sub     rsp, 0A8h
0x1400174d1  mov     rax, cs:__security_cookie
0x1400174d8  xor     rax, rsp
0x1400174db  mov     [rbp+57h+var_40], rax
0x1400174df  xorps   xmm0, xmm0
0x1400174e2  mov     [rbp+57h+pNumArgs], 0
0x1400174e9  xor     eax, eax
0x1400174eb  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x1400174f2  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1400174f6  mov     [rbp+57h+Thread], rax
0x1400174fa  movups  xmmword ptr [rbp+57h+hEvent], xmm0
0x1400174fe  call    cs:__imp_EnterCriticalSection
0x140017504  mov     ebx, cs:dword_140027D8C
0x14001750a  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x140017511  call    cs:__imp_LeaveCriticalSection
0x140017517  test    ebx, ebx
0x140017519  jz      short loc_140017556
0x14001751b  xor     ebx, ebx
0x14001751d  mov     ecx, 54Fh; dwErrCode
0x140017522  call    cs:__imp_SetLastError
0x140017528  call    cs:__imp_GetLastError
0x14001752e  mov     edi, eax
0x140017530  mov     ecx, edi; dwErrCode
0x140017532  call    cs:__imp_SetLastError
0x140017538  mov     eax, ebx
0x14001753a  mov     rcx, [rbp+57h+var_40]
0x14001753e  xor     rcx, rsp; StackCookie
0x140017541  call    __security_check_cookie
0x140017546  add     rsp, 0A8h
0x14001754d  pop     r15
0x14001754f  pop     r14
0x140017551  pop     rdi
0x140017552  pop     rsi
0x140017553  pop     rbx
0x140017554  pop     rbp
0x140017555  retn
0x140017556  call    InitializeTaskServer_AdjustPrivileges
0x14001755b  mov     ebx, eax
0x14001755d  test    eax, eax
0x14001755f  jz      short loc_140017528
0x140017561  xorps   xmm0, xmm0
0x140017564  movups  [rbp+57h+ProcessInformation], xmm0
0x140017568  movups  [rbp+57h+var_88], xmm0
0x14001756c  movups  [rbp+57h+var_78], xmm0
0x140017570  call    cs:__imp_GetCurrentProcess
0x140017576  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14001757c  mov     [rsp+0D0h+ReturnLength], 0; ReturnLength
0x140017585  mov     rcx, rax; ProcessHandle
0x140017588  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x14001758c  xor     edx, edx; ProcessInformationClass
0x14001758e  call    cs:__imp_NtQueryInformationProcess
0x140017594  test    eax, eax
0x140017596  jns     short loc_1400175AC
0x140017598  mov     ecx, eax; Status
0x14001759a  xor     ebx, ebx
0x14001759c  call    cs:__imp_RtlNtStatusToDosError
0x1400175a2  mov     ecx, eax; dwErrCode
0x1400175a4  call    cs:__imp_SetLastError
0x1400175aa  jmp     short loc_1400175AF
0x1400175ac  mov     ebx, dword ptr [rbp+57h+var_78+8]
0x1400175af  mov     r8d, ebx; dwProcessId
0x1400175b2  xor     edx, edx; bInheritHandle
0x1400175b4  mov     ecx, 440h; dwDesiredAccess
0x1400175b9  call    cs:__imp_OpenProcess
0x1400175bf  mov     rsi, rax
0x1400175c2  test    rax, rax
0x1400175c5  jnz     short loc_1400175CE
0x1400175c7  xor     ebx, ebx
0x1400175c9  jmp     loc_140017528
0x1400175ce  call    cs:__imp_GetCommandLineW
0x1400175d4  mov     rcx, rax; lpCmdLine
0x1400175d7  lea     rdx, [rbp+57h+pNumArgs]; pNumArgs
0x1400175db  call    cs:__imp_CommandLineToArgvW
0x1400175e1  mov     r14, rax
0x1400175e4  test    rax, rax
0x1400175e7  jnz     short loc_1400175F6
0x1400175e9  xor     r15d, r15d
0x1400175ec  xor     ebx, ebx
0x1400175ee  call    cs:__imp_GetLastError
0x1400175f4  jmp     short loc_140017670
0x1400175f6  mov     edx, [rbp+57h+pNumArgs]
0x1400175f9  lea     r8, [rax+8]
0x1400175fd  dec     edx
0x1400175ff  lea     r9, [rbp+57h+var_68]
0x140017603  mov     rcx, rsi; hSourceProcessHandle
0x140017606  call    InitializeTaskServer_InterpretParameters
0x14001760b  mov     r15d, eax
0x14001760e  test    eax, eax
0x140017610  jnz     short loc_140017616
0x140017612  xor     ebx, ebx
0x140017614  jmp     short loc_14001764A
0x140017616  mov     rcx, [rbp+57h+Thread]; Thread
0x14001761a  call    cs:__imp_GetProcessIdOfThread
0x140017620  mov     rcx, rsi; Process
0x140017623  mov     ebx, eax
0x140017625  call    cs:__imp_GetProcessId
0x14001762b  cmp     ebx, eax
0x14001762d  jz      short loc_14001763E
0x14001762f  xor     ebx, ebx
0x140017631  mov     ecx, 236h; dwErrCode
0x140017636  call    cs:__imp_SetLastError
0x14001763c  jmp     short loc_14001764A
0x14001763e  mov     rcx, [rbp+57h+hEvent+8]; hEvent
0x140017642  call    cs:__imp_SetEvent
0x140017648  mov     ebx, eax
0x14001764a  call    cs:__imp_GetLastError
0x140017650  mov     rcx, r14; hMem
0x140017653  mov     edi, eax
0x140017655  call    cs:__imp_LocalFree
0x14001765b  mov     r14, rax
0x14001765e  test    ebx, ebx
0x140017660  jz      short loc_140017672
0x140017662  call    cs:__imp_GetLastError
0x140017668  xor     ebx, ebx
0x14001766a  test    r14, r14
0x14001766d  setz    bl
0x140017670  mov     edi, eax
0x140017672  mov     rcx, rsi; hObject
0x140017675  call    cs:__imp_CloseHandle
0x14001767b  mov     esi, eax
0x14001767d  test    ebx, ebx
0x14001767f  jz      short loc_14001768F
0x140017681  call    cs:__imp_GetLastError
0x140017687  mov     edi, eax
0x140017689  test    esi, esi
0x14001768b  jnz     short loc_1400176A6
0x14001768d  mov     ebx, esi
0x14001768f  test    r15d, r15d
0x140017692  jz      loc_140017530
0x140017698  lea     rdx, [rbp+57h+var_68]; void **
0x14001769c  call    ?CloseMultipleHandles@@YAHIPEAPEAX@Z; CloseMultipleHandles(uint,void * *)
0x1400176a1  jmp     loc_140017530
0x1400176a6  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x1400176ad  call    cs:__imp_EnterCriticalSection
0x1400176b3  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x1400176b7  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x1400176be  mov     cs:dword_140027D8C, 1
0x1400176c8  movups  xmm1, xmmword ptr [rbp+57h+hEvent]
0x1400176cc  movups  cs:xmmword_140027AA0, xmm0
0x1400176d3  movsd   xmm0, [rbp+57h+Thread]
0x1400176d8  movsd   cs:qword_140027AC0, xmm0
0x1400176e0  movups  cs:xmmword_140027AB0, xmm1
0x1400176e7  call    cs:__imp_LeaveCriticalSection
0x1400176ed  mov     ebx, esi
0x1400176ef  jmp     loc_140017530
```
