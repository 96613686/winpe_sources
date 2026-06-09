# ServiceBase::_ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x1800102c0`
- end: `0x18001043b`
- name: `?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z`
- size: `379`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800071a8`
- `0x18000e904`
- `0x1800102c0`
- `0x18001096c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001036b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010383`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001040e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001036b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010383`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001040e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800103f5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800103f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800102f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800102f5`

## pseudocode

```c
__int64 __fastcall ServiceBase::_ServiceCtrlHandler(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        char *lpContext)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // rax
  int v10; // eax
  int updated; // ebp
  __int64 v13; // r8
  const char *v14; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( dwControl - 1 > 0xFE )
    return 87;
  v8 = (struct _RTL_CRITICAL_SECTION *)(lpContext + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)(lpContext + 136));
  if ( *((_DWORD *)lpContext + 32) )
    goto LABEL_13;
  switch ( dwControl )
  {
    case 1u:
      goto LABEL_19;
    case 4u:
LABEL_31:
      if ( v8 )
        LeaveCriticalSection(v8);
      return 0;
    case 5u:
    case 0xFu:
LABEL_19:
      *((_DWORD *)lpContext + 32) = 1;
      if ( dwControl == 15 || dwControl == 5 )
        *((_DWORD *)lpContext + 33) = 1;
      updated = ServiceBase::_UpdateStatus((ServiceBase *)lpContext, 3u);
      if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)lpContext + 88LL))(lpContext) )
      {
        ServiceBase::QueuePreShutdownCleanupWork(lpContext);
      }
      else if ( !SetEvent(*((HANDLE *)lpContext + 10)) )
      {
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v13, v14);
      }
LABEL_24:
      if ( updated < 0 && dwControl != 15 )
      {
        if ( v8 )
          LeaveCriticalSection(v8);
        return (unsigned __int16)updated;
      }
      goto LABEL_31;
  }
  v9 = *(_QWORD *)lpContext;
  if ( dwControl < 0x80 )
    v10 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, LPVOID))(v9 + 40))(
            lpContext,
            dwControl,
            dwEventType,
            lpEventData);
  else
    v10 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, LPVOID))(v9 + 32))(
            lpContext,
            dwControl,
            dwEventType,
            lpEventData);
  updated = v10;
  if ( v10 != -2147467263 )
    goto LABEL_24;
  if ( dwControl == 32 && *((_DWORD *)lpContext + 32) )
  {
LABEL_13:
    if ( v8 )
      LeaveCriticalSection(v8);
    return 1115;
  }
  if ( v8 )
    LeaveCriticalSection(v8);
  return 120;
}

```

## disassembly

```asm
0x1800102c0  mov     [rsp+arg_0], rbx
0x1800102c5  mov     [rsp+arg_8], rbp
0x1800102ca  push    rsi
0x1800102cb  push    rdi
0x1800102cc  push    r14
0x1800102ce  sub     rsp, 30h
0x1800102d2  mov     rdi, r9
0x1800102d5  mov     rbp, r8
0x1800102d8  mov     r14d, edx
0x1800102db  mov     esi, ecx
0x1800102dd  lea     eax, [rcx-1]
0x1800102e0  cmp     eax, 0FEh
0x1800102e5  ja      loc_180010418
0x1800102eb  lea     rbx, [r9+88h]
0x1800102f2  mov     rcx, rbx; lpCriticalSection
0x1800102f5  call    cs:__imp_EnterCriticalSection
0x1800102fb  mov     [rsp+48h+arg_18], rbx
0x180010300  cmp     dword ptr [rdi+80h], 0
0x180010307  jnz     short loc_180010363
0x180010309  mov     eax, esi
0x18001030b  mov     edx, 3; unsigned int
0x180010310  sub     eax, 1
0x180010313  jz      short loc_180010393
0x180010315  sub     eax, edx
0x180010317  jz      loc_180010406
0x18001031d  sub     eax, 1
0x180010320  jz      short loc_180010393
0x180010322  cmp     eax, 0Ah
0x180010325  jz      short loc_180010393
0x180010327  mov     rax, [rdi]
0x18001032a  mov     r9, rbp
0x18001032d  mov     r8d, r14d
0x180010330  mov     edx, esi
0x180010332  mov     rcx, rdi
0x180010335  cmp     esi, 80h
0x18001033b  jb      short loc_180010343
0x18001033d  mov     rax, [rax+20h]
0x180010341  jmp     short loc_180010347
0x180010343  mov     rax, [rax+28h]
0x180010347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001034c  mov     ebp, eax
0x18001034e  cmp     eax, 80004001h
0x180010353  jnz     short loc_1800103D3
0x180010355  cmp     esi, 20h ; ' '
0x180010358  jnz     short loc_18001037B
0x18001035a  cmp     dword ptr [rdi+80h], 0
0x180010361  jz      short loc_18001037B
0x180010363  test    rbx, rbx
0x180010366  jz      short loc_180010371
0x180010368  mov     rcx, rbx; lpCriticalSection
0x18001036b  call    cs:__imp_LeaveCriticalSection
0x180010371  mov     eax, 45Bh
0x180010376  jmp     loc_18001041D
0x18001037b  test    rbx, rbx
0x18001037e  jz      short loc_180010389
0x180010380  mov     rcx, rbx; lpCriticalSection
0x180010383  call    cs:__imp_LeaveCriticalSection
0x180010389  mov     eax, 78h ; 'x'
0x18001038e  jmp     loc_18001041D
0x180010393  mov     eax, 1
0x180010398  mov     [rdi+80h], eax
0x18001039e  cmp     esi, 0Fh
0x1800103a1  jz      short loc_1800103A8
0x1800103a3  cmp     esi, 5
0x1800103a6  jnz     short loc_1800103AE
0x1800103a8  mov     [rdi+84h], eax
0x1800103ae  mov     rcx, rdi; this
0x1800103b1  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x1800103b6  mov     ebp, eax
0x1800103b8  mov     rax, [rdi]
0x1800103bb  mov     rcx, rdi
0x1800103be  mov     rax, [rax+58h]
0x1800103c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103c7  test    al, al
0x1800103c9  jz      short loc_1800103F1
0x1800103cb  mov     rcx, rdi; Context
0x1800103ce  call    ?QueuePreShutdownCleanupWork@ServiceBase@@QEAAXXZ; ServiceBase::QueuePreShutdownCleanupWork(void)
0x1800103d3  test    ebp, ebp
0x1800103d5  jns     short loc_180010406
0x1800103d7  cmp     esi, 0Fh
0x1800103da  jz      short loc_180010406
0x1800103dc  movzx   edi, bp
0x1800103df  test    rbx, rbx
0x1800103e2  jz      short loc_1800103ED
0x1800103e4  mov     rcx, rbx; lpCriticalSection
0x1800103e7  call    cs:__imp_LeaveCriticalSection
0x1800103ed  mov     eax, edi
0x1800103ef  jmp     short loc_18001041D
0x1800103f1  mov     rcx, [rdi+50h]; hEvent
0x1800103f5  call    cs:__imp_SetEvent
0x1800103fb  mov     rcx, [rsp+48h]; this
0x180010400  test    eax, eax
0x180010402  jz      short loc_180010430
0x180010404  jmp     short loc_1800103D3
0x180010406  test    rbx, rbx
0x180010409  jz      short loc_180010414
0x18001040b  mov     rcx, rbx; lpCriticalSection
0x18001040e  call    cs:__imp_LeaveCriticalSection
0x180010414  xor     eax, eax
0x180010416  jmp     short loc_18001041D
0x180010418  mov     eax, 57h ; 'W'
0x18001041d  mov     rbx, [rsp+48h+arg_0]
0x180010422  mov     rbp, [rsp+48h+arg_8]
0x180010427  add     rsp, 30h
0x18001042b  pop     r14
0x18001042d  pop     rdi
0x18001042e  pop     rsi
0x18001042f  retn
0x180010430  mov     edx, 0A01h; void *
0x180010435  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
