# Vml::VmExeModule<CExec::Svc::Service>::Run(int)

- ea: `0x1400141b4`
- end: `0x14001435f`
- name: `?Run@?$VmExeModule@VService@Svc@CExec@@@Vml@@QEAAHH@Z`
- size: `427`
- prototype: `__int64 __fastcall(char *lpContext)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400143b0`

## callees

- `0x14000e828`
- `0x14000f1ac`
- `0x1400138a4`
- `0x140013f10`
- `0x1400140d4`
- `0x1400141b4`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400142e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400142e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400141fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014251`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400141fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014251`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014230`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001428b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014230`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001428b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140014227`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140014282`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140014227`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140014282`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1400141dd`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1400141dd`

## string_xrefs

- `0x14001434c`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
__int64 __fastcall Vml::VmExeModule<CExec::Svc::Service>::Run(char *lpContext)
{
  WCHAR *ServiceName; // rax
  SERVICE_STATUS_HANDLE v3; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    ServiceName = Vml::VmServiceModule<CExec::Svc::Service>::GetServiceName((Vml *)lpContext);
    v3 = RegisterServiceCtrlHandlerExW(
           ServiceName,
           Vml::VmServiceModule<CExec::Svc::Service>::ServiceHandlerEx,
           lpContext);
    *((_QWORD *)lpContext + 17) = v3;
    if ( !v3 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC0C,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v4);
    EnterCriticalSection((LPCRITICAL_SECTION)lpContext + 1);
    if ( *((_DWORD *)lpContext + 27) != 2 )
      *(_QWORD *)(lpContext + 124) = 0;
    *((_DWORD *)lpContext + 27) = 2;
    *((_DWORD *)lpContext + 29) = 0;
    SetServiceStatus(*((SERVICE_STATUS_HANDLE *)lpContext + 17), (LPSERVICE_STATUS)(lpContext + 104));
    LeaveCriticalSection((LPCRITICAL_SECTION)lpContext + 1);
    Vml::VmExeModule<CExec::Svc::Service>::PrepareToRun((CExec::Svc::Service *)lpContext);
    if ( *((_DWORD *)lpContext + 27) == 2 && *((_QWORD *)lpContext + 17) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)lpContext + 1);
      if ( *((_DWORD *)lpContext + 27) != 4 )
        *(_QWORD *)(lpContext + 124) = 0;
      *((_DWORD *)lpContext + 27) = 4;
      *((_DWORD *)lpContext + 29) = 0;
      *((_DWORD *)lpContext + 28) |= 1u;
      SetServiceStatus(*((SERVICE_STATUS_HANDLE *)lpContext + 17), (LPSERVICE_STATUS)(lpContext + 104));
      LeaveCriticalSection((LPCRITICAL_SECTION)lpContext + 1);
    }
    if ( ((unsigned __int8)g_TraceEnabled & 4) != 0
      && g_TraceEventEnabled
      && g_TraceLevel >= 3u
      && g_TraceEventEnabled(0xC002u) )
    {
      VmlDebugTrace(49154, L"Waiting for quit event...\n");
    }
    WaitForSingleObject(*((HANDLE *)lpContext + 11), 0xFFFFFFFF);
    if ( ((unsigned __int8)g_TraceEnabled & 4) != 0
      && g_TraceEventEnabled
      && g_TraceLevel >= 3u
      && g_TraceEventEnabled(0xC002u) )
    {
      VmlDebugTrace(49154, L"Quit event signaled - main message loop terminated.\n");
    }
  }
  catch ( ... )
  {
    Vml::VmServiceModule<CExec::Svc::Service>::CleanUpFromRun((__int64)lpContext);
    throw;
  }
  Vml::VmServiceModule<CExec::Svc::Service>::CleanUpFromRun((__int64)lpContext);
  return 0;
}

```

## disassembly

```asm
0x1400141b4  mov     [rsp+arg_8], rbx
0x1400141b9  push    rdi
0x1400141ba  sub     rsp, 30h
0x1400141be  mov     rbx, rcx
0x1400141c1  mov     [rsp+38h+var_10], rcx
0x1400141c6  mov     [rsp+38h+var_18], 0
0x1400141cb  call    ?GetServiceName@?$VmServiceModule@VService@Svc@CExec@@@Vml@@QEBAPEBGXZ; Vml::VmServiceModule<CExec::Svc::Service>::GetServiceName(void)
0x1400141d0  mov     r8, rbx; lpContext
0x1400141d3  lea     rdx, ?ServiceHandlerEx@?$VmServiceModule@VService@Svc@CExec@@@Vml@@CAKKKPEAX0@Z; lpHandlerProc
0x1400141da  mov     rcx, rax; lpServiceName
0x1400141dd  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1400141e3  mov     [rbx+88h], rax
0x1400141ea  test    rax, rax
0x1400141ed  jz      loc_140014347
0x1400141f3  lea     rdi, [rbx+28h]
0x1400141f7  mov     rcx, rdi; lpCriticalSection
0x1400141fa  call    cs:__imp_EnterCriticalSection
0x140014200  lea     rdx, [rbx+68h]; lpServiceStatus
0x140014204  cmp     dword ptr [rdx+4], 2
0x140014208  jz      short loc_140014212
0x14001420a  mov     qword ptr [rbx+7Ch], 0
0x140014212  mov     dword ptr [rbx+6Ch], 2
0x140014219  mov     dword ptr [rbx+74h], 0
0x140014220  mov     rcx, [rbx+88h]; hServiceStatus
0x140014227  call    cs:__imp_SetServiceStatus
0x14001422d  mov     rcx, rdi; lpCriticalSection
0x140014230  call    cs:__imp_LeaveCriticalSection
0x140014236  mov     rcx, rbx
0x140014239  call    ?PrepareToRun@?$VmExeModule@VService@Svc@CExec@@@Vml@@QEAAXXZ; Vml::VmExeModule<CExec::Svc::Service>::PrepareToRun(void)
0x14001423e  cmp     dword ptr [rbx+6Ch], 2
0x140014242  jnz     short loc_140014291
0x140014244  cmp     qword ptr [rbx+88h], 0
0x14001424c  jz      short loc_140014291
0x14001424e  mov     rcx, rdi; lpCriticalSection
0x140014251  call    cs:__imp_EnterCriticalSection
0x140014257  cmp     dword ptr [rbx+6Ch], 4
0x14001425b  jz      short loc_140014265
0x14001425d  mov     qword ptr [rbx+7Ch], 0
0x140014265  mov     dword ptr [rbx+6Ch], 4
0x14001426c  mov     dword ptr [rbx+74h], 0
0x140014273  or      dword ptr [rbx+70h], 1
0x140014277  lea     rdx, [rbx+68h]; lpServiceStatus
0x14001427b  mov     rcx, [rbx+88h]; hServiceStatus
0x140014282  call    cs:__imp_SetServiceStatus
0x140014288  mov     rcx, rdi; lpCriticalSection
0x14001428b  call    cs:__imp_LeaveCriticalSection
0x140014291  mov     [rsp+38h+var_18], 1
0x140014296  mov     rax, cs:?g_TraceEnabled@@3RC_JC; __int64 volatile near * volatile g_TraceEnabled
0x14001429d  test    al, 4
0x14001429f  jz      short loc_1400142DC
0x1400142a1  mov     rax, cs:?g_TraceEventEnabled@@3P6AEG@ZEA; uchar (*g_TraceEventEnabled)(ushort)
0x1400142a8  test    rax, rax
0x1400142ab  jz      short loc_1400142DC
0x1400142ad  mov     edi, 3
0x1400142b2  cmp     di, cs:?g_TraceLevel@@3GA; ushort g_TraceLevel
0x1400142b9  ja      short loc_1400142E1
0x1400142bb  mov     ecx, 0C002h
0x1400142c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400142c5  test    al, al
0x1400142c7  jz      short loc_1400142E1
0x1400142c9  lea     rdx, aWaitingForQuit; "Waiting for quit event...\n"
0x1400142d0  mov     ecx, 0C002h
0x1400142d5  call    VmlDebugTrace
0x1400142da  jmp     short loc_1400142E1
0x1400142dc  mov     edi, 3
0x1400142e1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400142e4  mov     rcx, [rbx+58h]; hHandle
0x1400142e8  call    cs:__imp_WaitForSingleObject
0x1400142ee  mov     rax, cs:?g_TraceEnabled@@3RC_JC; __int64 volatile near * volatile g_TraceEnabled
0x1400142f5  test    al, 4
0x1400142f7  jz      short loc_14001432E
0x1400142f9  mov     rax, cs:?g_TraceEventEnabled@@3P6AEG@ZEA; uchar (*g_TraceEventEnabled)(ushort)
0x140014300  test    rax, rax
0x140014303  jz      short loc_14001432E
0x140014305  cmp     di, cs:?g_TraceLevel@@3GA; ushort g_TraceLevel
0x14001430c  ja      short loc_14001432E
0x14001430e  mov     ecx, 0C002h
0x140014313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014318  test    al, al
0x14001431a  jz      short loc_14001432E
0x14001431c  lea     rdx, aQuitEventSigna; "Quit event signaled - main message loop"...
0x140014323  mov     ecx, 0C002h
0x140014328  call    VmlDebugTrace
0x14001432d  nop
0x14001432e  mov     al, [rsp+38h+var_18]
0x140014332  mov     rcx, rbx
0x140014335  call    ?CleanUpFromRun@?$VmServiceModule@VService@Svc@CExec@@@Vml@@QEAAXXZ; Vml::VmServiceModule<CExec::Svc::Service>::CleanUpFromRun(void)
0x14001433a  xor     eax, eax
0x14001433c  mov     rbx, [rsp+38h+arg_8]
0x140014341  add     rsp, 30h
0x140014345  pop     rdi
0x140014346  retn
0x140014347  mov     rcx, [rsp+38h]; this
0x14001434c  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140014353  mov     edx, 0C0Ch; void *
0x140014358  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
