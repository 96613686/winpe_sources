# ServiceMain

- ea: `0x180012390`
- end: `0x1800125b3`
- name: `ServiceMain`
- size: `547`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180011b6c`
- `0x180012390`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800124af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800124cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800124af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800124cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012433`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001244f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012433`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001244f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800125a0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800125a0`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180012417`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180012417`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180012491`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180012491`

## pseudocode

```c
void __fastcall ServiceMain(int a1, const WCHAR **a2)
{
  const WCHAR *v4; // rcx
  signed int LastError; // eax
  int v6; // ebx
  DWORD v7; // ecx
  int v8; // eax

  if ( a1 )
  {
    ServiceStatus.dwServiceType = 32;
    WaitHandle = 0;
    dwRegister = 0;
    dword_180090A80 = 0;
    LODWORD(dword_180090A84) = 0;
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
          v8 = (*((__int64 (__fastcall **)(HANDLE *, wchar_t *, HANDLE, BOOL (*)(), _QWORD, int))g_pServiceHostGlobalData
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
              ServiceStatus.dwCurrentState = 4;
              ServiceStatus.dwWin32ExitCode = 0;
LABEL_24:
              ServiceStatus.dwControlsAccepted = 1;
              *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
              SetServiceStatus(hServiceStatus, &ServiceStatus);
              return;
            }
          }
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
          ServiceStatus.dwCurrentState = 1;
          ServiceStatus.dwWin32ExitCode = v7;
          goto LABEL_24;
        }
      }
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_8;
  }
}

```

## disassembly

```asm
0x180012390  test    ecx, ecx
0x180012392  jz      locret_1800125B2
0x180012398  push    rbx
0x180012399  push    rbp
0x18001239a  push    rsi
0x18001239b  push    rdi
0x18001239c  push    r14
0x18001239e  push    r15
0x1800123a0  sub     rsp, 48h
0x1800123a4  xor     ebp, ebp
0x1800123a6  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x1800123b0  mov     rsi, rdx
0x1800123b3  mov     cs:WaitHandle, rbp
0x1800123ba  mov     edi, ecx
0x1800123bc  mov     cs:dwRegister, ebp
0x1800123c2  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800123c6  mov     cs:dword_180090A80, ebp
0x1800123cc  lea     r14d, [rbp+1]
0x1800123d0  mov     cs:dword_180090A84, ebp
0x1800123d6  mov     cs:ServiceStatus.dwCurrentState, r14d
0x1800123dd  lea     rdx, ServiceHandler; lpHandlerProc
0x1800123e4  mov     qword ptr cs:ServiceStatus.dwControlsAccepted, r14
0x1800123eb  xor     r8d, r8d; lpContext
0x1800123ee  mov     qword ptr cs:ServiceStatus.dwServiceSpecificExitCode, rbp
0x1800123f5  mov     cs:ServiceStatus.dwWaitHint, 0BB8h
0x1800123ff  mov     rcx, [rsi]; lpServiceName
0x180012402  mov     cs:hObject, r15
0x180012409  mov     cs:hHandle, r15
0x180012410  mov     cs:hServiceStatus, rbp
0x180012417  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18001241d  mov     cs:hServiceStatus, rax
0x180012424  test    rax, rax
0x180012427  jz      short loc_180012465
0x180012429  xor     r9d, r9d; lpName
0x18001242c  xor     r8d, r8d; bInitialState
0x18001242f  xor     edx, edx; bManualReset
0x180012431  xor     ecx, ecx; lpEventAttributes
0x180012433  call    cs:__imp_CreateEventW
0x180012439  mov     cs:hObject, rax
0x180012440  test    rax, rax
0x180012443  jz      short loc_180012465
0x180012445  xor     r9d, r9d; lpName
0x180012448  xor     r8d, r8d; bInitialState
0x18001244b  xor     edx, edx; bManualReset
0x18001244d  xor     ecx, ecx; lpEventAttributes
0x18001244f  call    cs:__imp_CreateEventW
0x180012455  mov     cs:hHandle, rax
0x18001245c  test    rax, rax
0x18001245f  jnz     loc_1800124F4
0x180012465  call    cs:__imp_GetLastError
0x18001246b  mov     ebx, eax
0x18001246d  test    eax, eax
0x18001246f  jle     short loc_18001247A
0x180012471  movzx   ebx, ax
0x180012474  or      ebx, 80070000h
0x18001247a  test    ebx, ebx
0x18001247c  jns     loc_1800125A6
0x180012482  mov     rcx, cs:WaitHandle; WaitHandle
0x180012489  test    rcx, rcx
0x18001248c  jz      short loc_18001249E
0x18001248e  mov     rdx, r15; CompletionEvent
0x180012491  call    cs:__imp_UnregisterWaitEx
0x180012497  mov     cs:WaitHandle, rbp
0x18001249e  mov     rcx, cs:hObject; hObject
0x1800124a5  lea     rax, [rcx-1]
0x1800124a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800124ad  ja      short loc_1800124BC
0x1800124af  call    cs:__imp_CloseHandle
0x1800124b5  mov     cs:hObject, rbp
0x1800124bc  mov     rcx, cs:hHandle; hObject
0x1800124c3  lea     rax, [rcx-1]
0x1800124c7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800124cb  ja      short loc_1800124DA
0x1800124cd  call    cs:__imp_CloseHandle
0x1800124d3  mov     cs:hHandle, rbp
0x1800124da  mov     eax, ebx
0x1800124dc  and     eax, 1FFF0000h
0x1800124e1  cmp     eax, 70000h
0x1800124e6  jnz     loc_18001256D
0x1800124ec  movzx   ecx, bx
0x1800124ef  jmp     loc_180012577
0x1800124f4  mov     rax, cs:?g_pServiceHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pServiceHostGlobalData
0x1800124fb  lea     r9, StopService
0x180012502  mov     r8, cs:hObject
0x180012509  lea     rdx, aEntappsvc; "EntAppSvc"
0x180012510  mov     [rsp+78h+var_50], 18h
0x180012518  lea     rcx, WaitHandle
0x18001251f  mov     [rsp+78h+var_58], rbp
0x180012524  mov     rax, [rax+0C0h]
0x18001252b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012530  mov     ebx, eax
0x180012532  test    eax, eax
0x180012534  jle     short loc_18001253F
0x180012536  movzx   ebx, ax
0x180012539  or      ebx, 80070000h
0x18001253f  test    ebx, ebx
0x180012541  js      loc_180012482
0x180012547  mov     rdx, rsi; unsigned __int16 **
0x18001254a  mov     ecx, edi; unsigned int
0x18001254c  call    ?SvcInitialize@@YAJKQEAPEAG@Z; SvcInitialize(ulong,ushort * * const)
0x180012551  mov     ebx, eax
0x180012553  test    eax, eax
0x180012555  js      loc_180012482
0x18001255b  mov     cs:ServiceStatus.dwCurrentState, 4
0x180012565  mov     cs:ServiceStatus.dwWin32ExitCode, ebp
0x18001256b  jmp     short loc_180012584
0x18001256d  test    ebx, ebx
0x18001256f  mov     ecx, 80004005h
0x180012574  cmovns  ecx, ebp
0x180012577  mov     cs:ServiceStatus.dwCurrentState, r14d
0x18001257e  mov     cs:ServiceStatus.dwWin32ExitCode, ecx
0x180012584  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18001258b  lea     rdx, ServiceStatus; lpServiceStatus
0x180012592  mov     cs:ServiceStatus.dwControlsAccepted, r14d
0x180012599  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rbp
0x1800125a0  call    cs:__imp_SetServiceStatus
0x1800125a6  add     rsp, 48h
0x1800125aa  pop     r15
0x1800125ac  pop     r14
0x1800125ae  pop     rdi
0x1800125af  pop     rsi
0x1800125b0  pop     rbp
0x1800125b1  pop     rbx
0x1800125b2  retn
```
