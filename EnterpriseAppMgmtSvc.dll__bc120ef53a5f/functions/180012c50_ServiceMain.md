# ServiceMain

- ea: `0x180012c50`
- end: `0x180012ea5`
- name: `ServiceMain`
- size: `597`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180012388`
- `0x180012760`
- `0x180012c50`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012d8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012db2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012d8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012db2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012cfa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012d1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012cfa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012d1c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180012e75`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180012e75`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180012cd8`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180012cd8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180012d6a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180012d6a`

## pseudocode

```c
void __fastcall ServiceMain(int a1, const WCHAR **a2)
{
  const WCHAR *v4; // rcx
  signed int LastError; // eax
  int v6; // ebx
  unsigned int v7; // edx
  int v8; // eax

  if ( !a1 )
    return;
  ServiceStatus.dwServiceType = 32;
  WaitHandle = 0;
  dwRegister = 0;
  dword_180096A78 = 0;
  LODWORD(dword_180096A7C) = 0;
  ServiceStatus.dwCurrentState = 1;
  *(_QWORD *)&ServiceStatus.dwControlsAccepted = 1;
  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 3000;
  v4 = *a2;
  hObject = (HANDLE)-1LL;
  hHandle = (HANDLE)-1LL;
  hServiceStatus = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(v4, ServiceHandler, 0);
  if ( hServiceStatus )
  {
    hObject = CreateEventW(0, 0, 0, 0);
    if ( hObject )
    {
      hHandle = CreateEventW(0, 0, 0, 0);
      if ( hHandle )
      {
        v8 = (*((__int64 (__fastcall **)(HANDLE *, wchar_t *, HANDLE, void (*)(), _QWORD, int))g_pServiceHostGlobalData
              + 24))(
               &WaitHandle,
               aEntappsvc,
               hObject,
               StopService,
               0,
               24);
        v6 = v8;
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
        if ( v6 >= 0 )
        {
          v6 = SvcInitialize(a1, (unsigned __int16 **const)a2);
          if ( v6 >= 0 )
          {
            ServiceStatus.dwControlsAccepted = 1;
            ServiceStatus.dwCurrentState = 4;
            ServiceStatus.dwWin32ExitCode = 0;
            *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
            SetServiceStatus(hServiceStatus, &ServiceStatus);
            return;
          }
        }
        goto LABEL_8;
      }
    }
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 < 0 )
  {
LABEL_8:
    if ( WaitHandle )
    {
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      WaitHandle = 0;
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( (char *)hHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hHandle);
      hHandle = 0;
    }
    if ( (v6 & 0x1FFF0000) == 0x70000 )
      v7 = (unsigned __int16)v6;
    else
      v7 = -2147467259;
    UpdateServiceStatus(1u, v7, 0);
  }
}

```

## disassembly

```asm
0x180012c50  test    ecx, ecx
0x180012c52  jz      locret_180012EA3
0x180012c58  push    rbx
0x180012c59  push    rbp
0x180012c5a  push    rsi
0x180012c5b  push    rdi
0x180012c5c  push    r15
0x180012c5e  sub     rsp, 40h
0x180012c62  xor     ebp, ebp
0x180012c64  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180012c6e  mov     rsi, rdx
0x180012c71  mov     cs:WaitHandle, rbp
0x180012c78  mov     edi, ecx
0x180012c7a  mov     cs:dwRegister, ebp
0x180012c80  or      r15, 0FFFFFFFFFFFFFFFFh
0x180012c84  mov     cs:dword_180096A78, ebp
0x180012c8a  mov     cs:dword_180096A7C, ebp
0x180012c90  lea     rdx, ServiceHandler; lpHandlerProc
0x180012c97  mov     cs:ServiceStatus.dwCurrentState, 1
0x180012ca1  xor     r8d, r8d; lpContext
0x180012ca4  mov     qword ptr cs:ServiceStatus.dwControlsAccepted, 1
0x180012caf  mov     qword ptr cs:ServiceStatus.dwServiceSpecificExitCode, rbp
0x180012cb6  mov     cs:ServiceStatus.dwWaitHint, 0BB8h
0x180012cc0  mov     rcx, [rsi]; lpServiceName
0x180012cc3  mov     cs:hObject, r15
0x180012cca  mov     cs:hHandle, r15
0x180012cd1  mov     cs:hServiceStatus, rbp
0x180012cd8  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180012cdf  nop     dword ptr [rax+rax+00h]
0x180012ce4  mov     cs:hServiceStatus, rax
0x180012ceb  test    rax, rax
0x180012cee  jz      short loc_180012D38
0x180012cf0  xor     r9d, r9d; lpName
0x180012cf3  xor     r8d, r8d; bInitialState
0x180012cf6  xor     edx, edx; bManualReset
0x180012cf8  xor     ecx, ecx; lpEventAttributes
0x180012cfa  call    cs:__imp_CreateEventW
0x180012d01  nop     dword ptr [rax+rax+00h]
0x180012d06  mov     cs:hObject, rax
0x180012d0d  test    rax, rax
0x180012d10  jz      short loc_180012D38
0x180012d12  xor     r9d, r9d; lpName
0x180012d15  xor     r8d, r8d; bInitialState
0x180012d18  xor     edx, edx; bManualReset
0x180012d1a  xor     ecx, ecx; lpEventAttributes
0x180012d1c  call    cs:__imp_CreateEventW
0x180012d23  nop     dword ptr [rax+rax+00h]
0x180012d28  mov     cs:hHandle, rax
0x180012d2f  test    rax, rax
0x180012d32  jnz     loc_180012DDF
0x180012d38  call    cs:__imp_GetLastError
0x180012d3f  nop     dword ptr [rax+rax+00h]
0x180012d44  mov     ebx, eax
0x180012d46  test    eax, eax
0x180012d48  jle     short loc_180012D53
0x180012d4a  movzx   ebx, ax
0x180012d4d  or      ebx, 80070000h
0x180012d53  test    ebx, ebx
0x180012d55  jns     loc_180012E99
0x180012d5b  mov     rcx, cs:WaitHandle; WaitHandle
0x180012d62  test    rcx, rcx
0x180012d65  jz      short loc_180012D7D
0x180012d67  mov     rdx, r15; CompletionEvent
0x180012d6a  call    cs:__imp_UnregisterWaitEx
0x180012d71  nop     dword ptr [rax+rax+00h]
0x180012d76  mov     cs:WaitHandle, rbp
0x180012d7d  mov     rcx, cs:hObject; hObject
0x180012d84  lea     rax, [rcx-1]
0x180012d88  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012d8c  ja      short loc_180012DA1
0x180012d8e  call    cs:__imp_CloseHandle
0x180012d95  nop     dword ptr [rax+rax+00h]
0x180012d9a  mov     cs:hObject, rbp
0x180012da1  mov     rcx, cs:hHandle; hObject
0x180012da8  lea     rax, [rcx-1]
0x180012dac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012db0  ja      short loc_180012DC5
0x180012db2  call    cs:__imp_CloseHandle
0x180012db9  nop     dword ptr [rax+rax+00h]
0x180012dbe  mov     cs:hHandle, rbp
0x180012dc5  mov     eax, ebx
0x180012dc7  and     eax, 1FFF0000h
0x180012dcc  cmp     eax, 70000h
0x180012dd1  jnz     loc_180012E83
0x180012dd7  movzx   edx, bx
0x180012dda  jmp     loc_180012E8D
0x180012ddf  mov     rax, cs:?g_pServiceHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pServiceHostGlobalData
0x180012de6  lea     r9, StopService
0x180012ded  mov     r8, cs:hObject
0x180012df4  lea     rdx, aEntappsvc; "EntAppSvc"
0x180012dfb  mov     [rsp+68h+var_40], 18h
0x180012e03  lea     rcx, WaitHandle
0x180012e0a  mov     [rsp+68h+var_48], rbp
0x180012e0f  mov     rax, [rax+0C0h]
0x180012e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e1b  mov     ebx, eax
0x180012e1d  test    eax, eax
0x180012e1f  jle     short loc_180012E2A
0x180012e21  movzx   ebx, ax
0x180012e24  or      ebx, 80070000h
0x180012e2a  test    ebx, ebx
0x180012e2c  js      loc_180012D5B
0x180012e32  mov     rdx, rsi; unsigned __int16 **
0x180012e35  mov     ecx, edi; unsigned int
0x180012e37  call    ?SvcInitialize@@YAJKQEAPEAG@Z; SvcInitialize(ulong,ushort * * const)
0x180012e3c  mov     ebx, eax
0x180012e3e  test    eax, eax
0x180012e40  js      loc_180012D5B
0x180012e46  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180012e4d  lea     rdx, ServiceStatus; lpServiceStatus
0x180012e54  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x180012e5e  mov     cs:ServiceStatus.dwCurrentState, 4
0x180012e68  mov     cs:ServiceStatus.dwWin32ExitCode, ebp
0x180012e6e  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rbp
0x180012e75  call    cs:__imp_SetServiceStatus
0x180012e7c  nop     dword ptr [rax+rax+00h]
0x180012e81  jmp     short loc_180012E99
0x180012e83  test    ebx, ebx
0x180012e85  mov     edx, 80004005h
0x180012e8a  cmovns  edx, ebp; unsigned int
0x180012e8d  xor     r8d, r8d; unsigned int
0x180012e90  lea     ecx, [r8+1]; unsigned int
0x180012e94  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180012e99  add     rsp, 40h
0x180012e9d  pop     r15
0x180012e9f  pop     rdi
0x180012ea0  pop     rsi
0x180012ea1  pop     rbp
0x180012ea2  pop     rbx
0x180012ea3  retn
```
