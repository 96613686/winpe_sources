# RasmanServiceMonitorThread

- ea: `0x180014270`
- end: `0x1800144d6`
- name: `RasmanServiceMonitorThread`
- size: `614`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180014270`
- `0x1800228ec`
- `0x1800263ce`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014397`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014397`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001431f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001431f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014338`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014338`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001444c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001444c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800144bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800144bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800144a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800144a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001446a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001446a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014472`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800142d5`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800142d5`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x180014377`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x180014377`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800142a9`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800142a9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800143ef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014408`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800143ef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014408`
- `rtutils!TracePrintfExA` at `0x18001445f`
- `rtutils!TracePrintfExA` at `0x180014498`
- `rtutils!TracePrintfExA` at `0x18001445f`
- `rtutils!TracePrintfExA` at `0x180014498`

## string_xrefs

- `0x180014453`: `RasmanServiceMonitor thread Entered ...`
- `0x180014489`: `RasmanServiceMonitorThread: NotifyServiceStatusChange failed, Error=%d`
- `0x1800143b7`: `RasmanServiceMonitor: WaitForSingleObjectEx failed, Error= %d`

## pseudocode

```c
void __fastcall __noreturn RasmanServiceMonitorThread(PVOID Parameter)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rdi
  DWORD v4; // ebx
  DWORD v5; // eax
  DWORD v6; // eax
  HLOCAL *i; // rcx
  SERVICE_NOTIFY_2A pNotifyBuffer; // [rsp+20h] [rbp-68h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasmanServiceMonitor thread Entered ...");
  v1 = OpenSCManagerA(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceA(v1, "RASMAN", 4u);
    if ( v3 )
    {
      v4 = 0;
      while ( 1 )
      {
        *(&pNotifyBuffer.dwVersion + 1) = 0;
        memset_0(&pNotifyBuffer, 0, 0x4Cu);
        EnterCriticalSection(&g_RasCriticalSection);
        if ( !g_fRCNInitialized && g_fRasmanStarted )
        {
          if ( g_pRCNList )
            RasmanAddNotificationForAll();
          g_fRCNInitialized = 1;
        }
        LeaveCriticalSection(&g_RasCriticalSection);
        *(_QWORD *)&pNotifyBuffer.dwVersion = 2;
        memset(&pNotifyBuffer.pContext, 0, 64);
        v4 |= 0xDu;
        pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)RasmanServiceNotify;
        v5 = NotifyServiceStatusChangeA(v3, v4, &pNotifyBuffer);
        if ( v5 )
          break;
        v6 = WaitForSingleObjectEx(g_hEventServiceMonitorTerminate, 0xFFFFFFFF, 1);
        if ( !v6 )
          goto LABEL_16;
        if ( v6 != 192 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "RasmanServiceMonitor: WaitForSingleObjectEx failed, Error= %d", v6);
          goto LABEL_16;
        }
      }
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RasmanServiceMonitorThread: NotifyServiceStatusChange failed, Error=%d", v5);
LABEL_16:
      CloseServiceHandle(v3);
    }
    else
    {
      GetLastError();
    }
    CloseServiceHandle(v2);
  }
  else
  {
    GetLastError();
  }
  if ( g_hEventServiceMonitorTerminate )
  {
    CloseHandle(g_hEventServiceMonitorTerminate);
    g_hEventServiceMonitorTerminate = 0;
  }
  for ( i = (HLOCAL *)g_pRCNList; g_pRCNList; i = (HLOCAL *)g_pRCNList )
  {
    g_pRCNList = *i;
    LocalFree(i);
  }
  g_pRCNList = 0;
  g_fRCNInitialized = 0;
  FreeLibraryAndExitThread(g_hModule, 0);
}

```

## disassembly

```asm
0x180014270  push    rbp
0x180014272  sub     rsp, 80h
0x180014279  mov     rax, cs:__security_cookie
0x180014280  xor     rax, rsp
0x180014283  mov     [rsp+88h+var_18], rax
0x180014288  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001428e  mov     [rsp+88h+arg_8], rsi
0x180014296  cmp     ecx, 0FFFFFFFFh
0x180014299  jnz     loc_180014453
0x18001429f  xor     edx, edx; lpDatabaseName
0x1800142a1  xor     ecx, ecx; lpMachineName
0x1800142a3  mov     r8d, 1; dwDesiredAccess
0x1800142a9  call    cs:__imp_OpenSCManagerA
0x1800142af  xor     ebp, ebp
0x1800142b1  mov     rsi, rax
0x1800142b4  test    rax, rax
0x1800142b7  jz      loc_18001446A
0x1800142bd  mov     r8d, 4; dwDesiredAccess
0x1800142c3  mov     [rsp+88h+arg_10], rdi
0x1800142cb  lea     rdx, aRasman; "RASMAN"
0x1800142d2  mov     rcx, rax; hSCManager
0x1800142d5  call    cs:__imp_OpenServiceA
0x1800142db  mov     rdi, rax
0x1800142de  test    rax, rax
0x1800142e1  jz      loc_180014472
0x1800142e7  mov     [rsp+88h+arg_0], rbx
0x1800142ef  mov     ebx, ebp
0x1800142f1  mov     [rsp+88h+arg_18], r14
0x1800142f9  lea     r14, RasmanServiceNotify
0x180014300  xor     eax, eax
0x180014302  lea     rcx, [rsp+88h+pNotifyBuffer]; void *
0x180014307  xor     edx, edx; Val
0x180014309  mov     dword ptr [rsp+88h+pNotifyBuffer+4], eax
0x18001430d  mov     r8d, 4Ch ; 'L'; Size
0x180014313  call    memset_0
0x180014318  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x18001431f  call    cs:__imp_EnterCriticalSection
0x180014325  cmp     cs:g_fRCNInitialized, ebp
0x18001432b  jz      loc_1800143C3
0x180014331  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x180014338  call    cs:__imp_LeaveCriticalSection
0x18001433e  xorps   xmm0, xmm0
0x180014341  mov     qword ptr [rsp+88h+pNotifyBuffer.dwVersion], 2
0x18001434a  xorps   xmm1, xmm1
0x18001434d  movdqa  xmmword ptr [rsp+88h+pNotifyBuffer.pContext], xmm0
0x180014353  or      ebx, 0Dh
0x180014356  movdqa  xmmword ptr [rsp+88h+pNotifyBuffer.ServiceStatus.dwCurrentState], xmm1
0x18001435c  mov     edx, ebx; dwNotifyMask
0x18001435e  movdqa  xmmword ptr [rsp+88h+pNotifyBuffer.ServiceStatus.dwCheckPoint], xmm0
0x180014364  lea     r8, [rsp+88h+pNotifyBuffer]; pNotifyBuffer
0x180014369  movdqa  xmmword ptr [rsp+88h+pNotifyBuffer.dwNotificationTriggered], xmm1
0x18001436f  mov     rcx, rdi; hService
0x180014372  mov     [rsp+88h+pNotifyBuffer.pfnNotifyCallback], r14
0x180014377  call    cs:__imp_NotifyServiceStatusChangeA
0x18001437d  test    eax, eax
0x18001437f  jnz     loc_18001447A
0x180014385  mov     rcx, cs:g_hEventServiceMonitorTerminate; hHandle
0x18001438c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180014391  mov     r8d, 1; bAlertable
0x180014397  call    cs:__imp_WaitForSingleObjectEx
0x18001439d  test    eax, eax
0x18001439f  jz      short loc_1800143EC
0x1800143a1  cmp     eax, 0C0h
0x1800143a6  jz      loc_180014300
0x1800143ac  mov     ecx, cs:g_dwTraceId
0x1800143b2  cmp     ecx, 0FFFFFFFFh
0x1800143b5  jz      short loc_1800143EC
0x1800143b7  lea     r8, aRasmanservicem; "RasmanServiceMonitor: WaitForSingleObje"...
0x1800143be  jmp     loc_180014490
0x1800143c3  cmp     cs:g_fRasmanStarted, ebp
0x1800143c9  jz      loc_180014331
0x1800143cf  cmp     cs:g_pRCNList, rbp
0x1800143d6  jz      short loc_1800143DD
0x1800143d8  call    RasmanAddNotificationForAll
0x1800143dd  mov     cs:g_fRCNInitialized, 1
0x1800143e7  jmp     loc_180014331
0x1800143ec  mov     rcx, rdi; hSCObject
0x1800143ef  call    cs:__imp_CloseServiceHandle
0x1800143f5  mov     r14, [rsp+88h+arg_18]
0x1800143fd  mov     rbx, [rsp+88h+arg_0]
0x180014405  mov     rcx, rsi; hSCObject
0x180014408  call    cs:__imp_CloseServiceHandle
0x18001440e  mov     rdi, [rsp+88h+arg_10]
0x180014416  mov     rcx, cs:g_hEventServiceMonitorTerminate; hObject
0x18001441d  mov     rsi, [rsp+88h+arg_8]
0x180014425  test    rcx, rcx
0x180014428  jnz     short loc_1800144A3
0x18001442a  mov     rcx, cs:g_pRCNList; hMem
0x180014431  test    rcx, rcx
0x180014434  jnz     short loc_1800144B5
0x180014436  mov     rcx, cs:g_hModule; hLibModule
0x18001443d  xor     edx, edx; dwExitCode
0x18001443f  mov     cs:g_pRCNList, rbp
0x180014446  mov     cs:g_fRCNInitialized, ebp
0x18001444c  call    cs:__imp_FreeLibraryAndExitThread
0x180014452  int     3; Trap to Debugger
0x180014453  lea     r8, aRasmanservicem_0; "RasmanServiceMonitor thread Entered ..."
0x18001445a  mov     edx, 0Ch; dwFlags
0x18001445f  call    cs:__imp_TracePrintfExA
0x180014465  jmp     loc_18001429F
0x18001446a  call    cs:__imp_GetLastError
0x180014470  jmp     short loc_180014416
0x180014472  call    cs:__imp_GetLastError
0x180014478  jmp     short loc_180014405
0x18001447a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014480  cmp     ecx, 0FFFFFFFFh
0x180014483  jz      loc_1800143EC
0x180014489  lea     r8, aRasmanservicem_1; "RasmanServiceMonitorThread: NotifyServi"...
0x180014490  mov     r9d, eax
0x180014493  mov     edx, 0Ch; dwFlags
0x180014498  call    cs:__imp_TracePrintfExA
0x18001449e  jmp     loc_1800143EC
0x1800144a3  call    cs:__imp_CloseHandle
0x1800144a9  mov     cs:g_hEventServiceMonitorTerminate, rbp
0x1800144b0  jmp     loc_18001442A
0x1800144b5  mov     rax, [rcx]
0x1800144b8  mov     cs:g_pRCNList, rax
0x1800144bf  call    cs:__imp_LocalFree
0x1800144c5  mov     rcx, cs:g_pRCNList
0x1800144cc  test    rcx, rcx
0x1800144cf  jnz     short loc_1800144B5
0x1800144d1  jmp     loc_180014436
```
