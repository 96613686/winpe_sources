# CTaskManager::SerialThreadRoutine(void *)

- ea: `0x18009e880`
- end: `0x18009e959`
- name: `?SerialThreadRoutine@CTaskManager@@SAKPEAX@Z`
- size: `217`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180074a40`
- `0x18009e880`
- `0x1800a0540`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18009e8a0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18009e8a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e94e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e94e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e8fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e8fe`
- `msvcrt!_endthreadex` at `0x18009e8e6`
- `msvcrt!_endthreadex` at `0x18009e8e6`

## string_xrefs

- `0x18009e8c8`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`

## pseudocode

```c
__int64 __fastcall CTaskManager::SerialThreadRoutine(PVOID Parameter)
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
        v1 = WaitForMultipleObjectsEx(2u, &CTaskManager::m_rghPendingSerialWorkEvents, 0, 0xFFFFFFFF, 0);
        if ( v1 )
          break;
        while ( 1 )
        {
          v4 = 0;
          EnterCriticalSection(&stru_180153808);
          if ( !(unsigned int)UTStaticList<CAscCall *>::RemoveFirst(&CTaskManager::m_queueOfSerialTasks, &v4) )
            break;
          LeaveCriticalSection(&stru_180153808);
          v3 = *(_QWORD *)(v4 + 8);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
          (**(void (__fastcall ***)(__int64))v3)(v3);
        }
        LeaveCriticalSection(&stru_180153808);
      }
      if ( v1 != 1 )
        break;
      _endthreadex(0);
    }
  }
  while ( v1 == 128 || v1 == 129 );
  if ( v1 != -1 )
    XA_TRACE_FATAL(0xC000110F, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 419);
  return 1;
}

```

## disassembly

```asm
0x18009e880  push    rbx
0x18009e882  sub     rsp, 30h
0x18009e886  xor     r8d, r8d; bWaitAll
0x18009e889  mov     [rsp+38h+bAlertable], 0; bAlertable
0x18009e891  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18009e895  lea     rdx, ?m_rghPendingSerialWorkEvents@CTaskManager@@0PAPEAXA; lpHandles
0x18009e89c  lea     ecx, [r8+2]; nCount
0x18009e8a0  call    cs:__imp_WaitForMultipleObjectsEx
0x18009e8a6  test    eax, eax
0x18009e8a8  jz      short loc_18009E8EE
0x18009e8aa  cmp     eax, 1
0x18009e8ad  jz      short loc_18009E8E4
0x18009e8af  cmp     eax, 80h
0x18009e8b4  jz      short loc_18009E886
0x18009e8b6  cmp     eax, 81h
0x18009e8bb  jz      short loc_18009E886
0x18009e8bd  cmp     eax, 0FFFFFFFFh
0x18009e8c0  jz      short loc_18009E8D9
0x18009e8c2  mov     r8d, 1A3h; int
0x18009e8c8  lea     rdx, aComComplusDtcD_81; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009e8cf  mov     ecx, 0C000110Fh; unsigned int
0x18009e8d4  call    ?XA_TRACE_FATAL@@YAXKPEADH@Z; XA_TRACE_FATAL(ulong,char *,int)
0x18009e8d9  mov     eax, 1
0x18009e8de  add     rsp, 30h
0x18009e8e2  pop     rbx
0x18009e8e3  retn
0x18009e8e4  xor     ecx, ecx; ReturnCode
0x18009e8e6  call    cs:__imp__endthreadex
0x18009e8ec  jmp     short loc_18009E886
0x18009e8ee  lea     rcx, stru_180153808; lpCriticalSection
0x18009e8f5  mov     [rsp+38h+arg_8], 0
0x18009e8fe  call    cs:__imp_EnterCriticalSection
0x18009e904  lea     rdx, [rsp+38h+arg_8]
0x18009e909  lea     rcx, ?m_queueOfSerialTasks@CTaskManager@@0V?$UTStaticList@PEAVCWorkerTask@@@@A; UTStaticList<CWorkerTask *> CTaskManager::m_queueOfSerialTasks
0x18009e910  call    ?RemoveFirst@?$UTStaticList@PEAVCAscCall@@@@UEAAHPEAPEAV?$UTLink@PEAVCAscCall@@@@@Z; UTStaticList<CAscCall *>::RemoveFirst(UTLink<CAscCall *> * *)
0x18009e915  lea     rcx, stru_180153808; lpCriticalSection
0x18009e91c  test    eax, eax
0x18009e91e  jz      short loc_18009E94E
0x18009e920  call    cs:__imp_LeaveCriticalSection
0x18009e926  mov     rax, [rsp+38h+arg_8]
0x18009e92b  mov     rbx, [rax+8]
0x18009e92f  mov     rcx, rbx
0x18009e932  mov     rax, [rbx]
0x18009e935  mov     rax, [rax+10h]
0x18009e939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e93e  mov     rax, [rbx]
0x18009e941  mov     rcx, rbx
0x18009e944  mov     rax, [rax]
0x18009e947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e94c  jmp     short loc_18009E8EE
0x18009e94e  call    cs:__imp_LeaveCriticalSection
0x18009e954  jmp     loc_18009E886
```
