# CTaskManager::ValidateThreadRoutine(void *)

- ea: `0x1800a0460`
- end: `0x1800a0539`
- name: `?ValidateThreadRoutine@CTaskManager@@SAKPEAX@Z`
- size: `217`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180074a40`
- `0x1800a0460`
- `0x1800a0540`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800a0480`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800a0480`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0500`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a052e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0500`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a052e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a04de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a04de`
- `msvcrt!_endthreadex` at `0x1800a04c6`
- `msvcrt!_endthreadex` at `0x1800a04c6`

## string_xrefs

- `0x1800a04a8`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`

## pseudocode

```c
__int64 __fastcall CTaskManager::ValidateThreadRoutine(PVOID Parameter)
{
  DWORD v1; // eax
  __int64 v3; // rbx
  __int64 v4; // [rsp+48h] [rbp+10h] BYREF

  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v1 = WaitForMultipleObjectsEx(2u, &CTaskManager::m_rghPendingValidateWorkEvents, 0, 0xFFFFFFFF, 0);
        if ( v1 )
          break;
        while ( 1 )
        {
          v4 = 0;
          EnterCriticalSection(&CriticalSection);
          if ( !(unsigned int)UTStaticList<CAscCall *>::RemoveFirst(&CTaskManager::m_queueOfValidateTasks, &v4) )
            break;
          LeaveCriticalSection(&CriticalSection);
          v3 = *(_QWORD *)(v4 + 8);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
          (**(void (__fastcall ***)(__int64))v3)(v3);
        }
        LeaveCriticalSection(&CriticalSection);
      }
      if ( v1 != 1 )
        break;
      _endthreadex(0);
    }
  }
  while ( v1 == 128 || v1 == 129 );
  if ( v1 != -1 )
    XA_TRACE_FATAL(0xC000110F, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 474);
  return 1;
}

```

## disassembly

```asm
0x1800a0460  push    rbx
0x1800a0462  sub     rsp, 30h
0x1800a0466  xor     r8d, r8d; bWaitAll
0x1800a0469  mov     [rsp+38h+bAlertable], 0; bAlertable
0x1800a0471  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800a0475  lea     rdx, ?m_rghPendingValidateWorkEvents@CTaskManager@@0PAPEAXA; lpHandles
0x1800a047c  lea     ecx, [r8+2]; nCount
0x1800a0480  call    cs:__imp_WaitForMultipleObjectsEx
0x1800a0486  test    eax, eax
0x1800a0488  jz      short loc_1800A04CE
0x1800a048a  cmp     eax, 1
0x1800a048d  jz      short loc_1800A04C4
0x1800a048f  cmp     eax, 80h
0x1800a0494  jz      short loc_1800A0466
0x1800a0496  cmp     eax, 81h
0x1800a049b  jz      short loc_1800A0466
0x1800a049d  cmp     eax, 0FFFFFFFFh
0x1800a04a0  jz      short loc_1800A04B9
0x1800a04a2  mov     r8d, 1DAh; int
0x1800a04a8  lea     rdx, aComComplusDtcD_81; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x1800a04af  mov     ecx, 0C000110Fh; unsigned int
0x1800a04b4  call    ?XA_TRACE_FATAL@@YAXKPEADH@Z; XA_TRACE_FATAL(ulong,char *,int)
0x1800a04b9  mov     eax, 1
0x1800a04be  add     rsp, 30h
0x1800a04c2  pop     rbx
0x1800a04c3  retn
0x1800a04c4  xor     ecx, ecx; ReturnCode
0x1800a04c6  call    cs:__imp__endthreadex
0x1800a04cc  jmp     short loc_1800A0466
0x1800a04ce  lea     rcx, CriticalSection; lpCriticalSection
0x1800a04d5  mov     [rsp+38h+arg_8], 0
0x1800a04de  call    cs:__imp_EnterCriticalSection
0x1800a04e4  lea     rdx, [rsp+38h+arg_8]
0x1800a04e9  lea     rcx, ?m_queueOfValidateTasks@CTaskManager@@0V?$UTStaticList@PEAVCWorkerTask@@@@A; UTStaticList<CWorkerTask *> CTaskManager::m_queueOfValidateTasks
0x1800a04f0  call    ?RemoveFirst@?$UTStaticList@PEAVCAscCall@@@@UEAAHPEAPEAV?$UTLink@PEAVCAscCall@@@@@Z; UTStaticList<CAscCall *>::RemoveFirst(UTLink<CAscCall *> * *)
0x1800a04f5  lea     rcx, CriticalSection; lpCriticalSection
0x1800a04fc  test    eax, eax
0x1800a04fe  jz      short loc_1800A052E
0x1800a0500  call    cs:__imp_LeaveCriticalSection
0x1800a0506  mov     rax, [rsp+38h+arg_8]
0x1800a050b  mov     rbx, [rax+8]
0x1800a050f  mov     rcx, rbx
0x1800a0512  mov     rax, [rbx]
0x1800a0515  mov     rax, [rax+10h]
0x1800a0519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a051e  mov     rax, [rbx]
0x1800a0521  mov     rcx, rbx
0x1800a0524  mov     rax, [rax]
0x1800a0527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a052c  jmp     short loc_1800A04CE
0x1800a052e  call    cs:__imp_LeaveCriticalSection
0x1800a0534  jmp     loc_1800A0466
```
