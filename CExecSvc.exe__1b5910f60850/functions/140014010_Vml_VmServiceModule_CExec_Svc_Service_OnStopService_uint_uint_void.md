# Vml::VmServiceModule<CExec::Svc::Service>::OnStopService(uint,uint,void *)

- ea: `0x140014010`
- end: `0x1400140ce`
- name: `?OnStopService@?$VmServiceModule@VService@Svc@CExec@@@Vml@@QEAAXIIPEAX@Z`
- size: `190`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140014370`

## callees

- `0x14000f1ac`
- `0x140014010`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140014071`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140014071`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001402b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001402b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014062`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014062`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140014058`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140014058`

## string_xrefs

- `0x1400140ae`: `Vml::VmExeModule<class CExec::Svc::Service>::Quit`

## pseudocode

```c
unsigned __int8 __fastcall Vml::VmServiceModule<CExec::Svc::Service>::OnStopService(__int64 a1)
{
  SERVICE_STATUS_HANDLE v2; // rcx
  void *v3; // rcx
  unsigned __int8 result; // al

  if ( *(_QWORD *)(a1 + 136) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
    if ( *(_DWORD *)(a1 + 108) != 3 )
      *(_QWORD *)(a1 + 124) = 0;
    v2 = *(SERVICE_STATUS_HANDLE *)(a1 + 136);
    *(_DWORD *)(a1 + 108) = 3;
    *(_DWORD *)(a1 + 116) = 0;
    SetServiceStatus(v2, (LPSERVICE_STATUS)(a1 + 104));
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  }
  v3 = *(void **)(a1 + 88);
  if ( v3 )
    return SetEvent(v3);
  result = (unsigned __int8)g_TraceEnabled;
  if ( ((unsigned __int8)g_TraceEnabled & 4) != 0 )
  {
    result = (unsigned __int8)g_TraceEventEnabled;
    if ( g_TraceEventEnabled )
    {
      if ( g_TraceLevel >= 2u )
      {
        result = g_TraceEventEnabled(0x8002u);
        if ( result )
          return VmlDebugTrace(
                   32770,
                   L"%hs calls with quit event NULL - call ignored.\n",
                   "Vml::VmExeModule<class CExec::Svc::Service>::Quit");
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014010  mov     [rsp+arg_8], rbx
0x140014015  push    rdi
0x140014016  sub     rsp, 20h
0x14001401a  cmp     qword ptr [rcx+88h], 0
0x140014022  mov     rbx, rcx
0x140014025  jz      short loc_140014068
0x140014027  add     rcx, 28h ; '('; lpCriticalSection
0x14001402b  call    cs:__imp_EnterCriticalSection
0x140014031  lea     rdx, [rbx+68h]; lpServiceStatus
0x140014035  cmp     dword ptr [rdx+4], 3
0x140014039  jz      short loc_140014043
0x14001403b  mov     qword ptr [rbx+7Ch], 0
0x140014043  mov     rcx, [rbx+88h]; hServiceStatus
0x14001404a  mov     dword ptr [rbx+6Ch], 3
0x140014051  mov     dword ptr [rbx+74h], 0
0x140014058  call    cs:__imp_SetServiceStatus
0x14001405e  lea     rcx, [rbx+28h]; lpCriticalSection
0x140014062  call    cs:__imp_LeaveCriticalSection
0x140014068  mov     rcx, [rbx+58h]; hEvent
0x14001406c  test    rcx, rcx
0x14001406f  jz      short loc_140014079
0x140014071  call    cs:__imp_SetEvent
0x140014077  jmp     short loc_1400140C3
0x140014079  mov     rax, cs:?g_TraceEnabled@@3RC_JC; __int64 volatile near * volatile g_TraceEnabled
0x140014080  test    al, 4
0x140014082  jz      short loc_1400140C3
0x140014084  mov     rax, cs:?g_TraceEventEnabled@@3P6AEG@ZEA; uchar (*g_TraceEventEnabled)(ushort)
0x14001408b  test    rax, rax
0x14001408e  jz      short loc_1400140C3
0x140014090  mov     ecx, 2
0x140014095  cmp     cx, cs:?g_TraceLevel@@3GA; ushort g_TraceLevel
0x14001409c  ja      short loc_1400140C3
0x14001409e  mov     ebx, 8002h
0x1400140a3  mov     ecx, ebx
0x1400140a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400140aa  test    al, al
0x1400140ac  jz      short loc_1400140C3
0x1400140ae  lea     r8, aVmlVmexemodule; "Vml::VmExeModule<class CExec::Svc::Serv"...
0x1400140b5  mov     ecx, ebx
0x1400140b7  lea     rdx, aHsCallsWithQui; "%hs calls with quit event NULL - call i"...
0x1400140be  call    VmlDebugTrace
0x1400140c3  mov     rbx, [rsp+28h+arg_8]
0x1400140c8  add     rsp, 20h
0x1400140cc  pop     rdi
0x1400140cd  retn
```
