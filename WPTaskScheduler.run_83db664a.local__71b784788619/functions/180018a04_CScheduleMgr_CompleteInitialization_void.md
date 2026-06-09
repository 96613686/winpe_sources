# CScheduleMgr::CompleteInitialization(void)

- ea: `0x180018a04`
- end: `0x180018b1b`
- name: `?CompleteInitialization@CScheduleMgr@@QEAAJXZ`
- size: `279`
- prototype: `__int64 __fastcall(CScheduleMgr *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018b30`

## callees

- `0x18000ea40`
- `0x180018a04`
- `0x18001e978`
- `0x18001edf0`
- `0x18001f918`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018a28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018a28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018afd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018afd`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::CompleteInitialization(CScheduleMgr *this)
{
  unsigned int All; // edi
  const struct _GUID *v3; // rdx
  TaskStore *v4; // rcx
  __int64 v5; // r8
  TaskStore *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-48h] BYREF

  All = -2147467259;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)v4,
      (const EVENT_DESCRIPTOR *)ServiceInitializePhase2Started,
      v5,
      1u,
      &v10);
  if ( *((_QWORD *)this + 7) )
  {
    TaskStore::PurgeSchedules(v4, v3);
    TaskStore::CleanSchedulesStore(v6);
    if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(v7, (const EVENT_DESCRIPTOR *)LoadSchedulesStarted, v8, 1u, &v10);
    All = TaskStore::LoadAll(*((TaskStore **)this + 7));
    if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer((__int64)v4, (const EVENT_DESCRIPTOR *)LoadSchedulesCompleted, v5, 1u, &v10);
  }
  if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)v4,
      (const EVENT_DESCRIPTOR *)ServiceInitializePhase2Completed,
      v5,
      1u,
      &v10);
  if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer((__int64)v4, (const EVENT_DESCRIPTOR *)ServiceInitializeCompleted, v5, 1u, &v10);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return All;
}

```

## disassembly

```asm
0x180018a04  push    rbx
0x180018a06  push    rbp
0x180018a07  push    rsi
0x180018a08  push    rdi
0x180018a09  sub     rsp, 58h
0x180018a0d  mov     rax, cs:__security_cookie
0x180018a14  xor     rax, rsp
0x180018a17  mov     [rsp+78h+var_38], rax
0x180018a1c  mov     rbx, rcx
0x180018a1f  mov     edi, 80004005h
0x180018a24  add     rcx, 10h; lpCriticalSection
0x180018a28  call    cs:__imp_EnterCriticalSection
0x180018a2e  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 8
0x180018a35  mov     ebp, 1
0x180018a3a  jz      short loc_180018A55
0x180018a3c  lea     rax, [rsp+78h+var_48]
0x180018a41  mov     r9d, ebp
0x180018a44  lea     rdx, ServiceInitializePhase2Started
0x180018a4b  mov     [rsp+78h+var_58], rax
0x180018a50  call    McGenEventWrite_EventWriteTransfer
0x180018a55  cmp     qword ptr [rbx+38h], 0
0x180018a5a  jz      short loc_180018AB5
0x180018a5c  call    ?PurgeSchedules@TaskStore@@QEAAJPEBU_GUID@@K@Z; TaskStore::PurgeSchedules(_GUID const *,ulong)
0x180018a61  call    ?CleanSchedulesStore@TaskStore@@QEAAJXZ; TaskStore::CleanSchedulesStore(void)
0x180018a66  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 10h
0x180018a6d  jz      short loc_180018A88
0x180018a6f  lea     rax, [rsp+78h+var_48]
0x180018a74  mov     r9d, ebp
0x180018a77  lea     rdx, LoadSchedulesStarted
0x180018a7e  mov     [rsp+78h+var_58], rax
0x180018a83  call    McGenEventWrite_EventWriteTransfer
0x180018a88  mov     rcx, [rbx+38h]; this
0x180018a8c  call    ?LoadAll@TaskStore@@QEAAJXZ; TaskStore::LoadAll(void)
0x180018a91  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 10h
0x180018a98  mov     edi, eax
0x180018a9a  jz      short loc_180018AB5
0x180018a9c  lea     rax, [rsp+78h+var_48]
0x180018aa1  mov     r9d, ebp
0x180018aa4  lea     rdx, LoadSchedulesCompleted
0x180018aab  mov     [rsp+78h+var_58], rax
0x180018ab0  call    McGenEventWrite_EventWriteTransfer
0x180018ab5  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 8
0x180018abc  jz      short loc_180018AD7
0x180018abe  lea     rax, [rsp+78h+var_48]
0x180018ac3  mov     r9d, ebp
0x180018ac6  lea     rdx, ServiceInitializePhase2Completed
0x180018acd  mov     [rsp+78h+var_58], rax
0x180018ad2  call    McGenEventWrite_EventWriteTransfer
0x180018ad7  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 4
0x180018ade  jz      short loc_180018AF9
0x180018ae0  lea     rax, [rsp+78h+var_48]
0x180018ae5  mov     r9d, ebp
0x180018ae8  lea     rdx, ServiceInitializeCompleted
0x180018aef  mov     [rsp+78h+var_58], rax
0x180018af4  call    McGenEventWrite_EventWriteTransfer
0x180018af9  lea     rcx, [rbx+10h]; lpCriticalSection
0x180018afd  call    cs:__imp_LeaveCriticalSection
0x180018b03  mov     eax, edi
0x180018b05  mov     rcx, [rsp+78h+var_38]
0x180018b0a  xor     rcx, rsp; StackCookie
0x180018b0d  call    __security_check_cookie
0x180018b12  add     rsp, 58h
0x180018b16  pop     rdi
0x180018b17  pop     rsi
0x180018b18  pop     rbp
0x180018b19  pop     rbx
0x180018b1a  retn
```
