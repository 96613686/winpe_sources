# CRoamingMonitor::Shutdown(ulong,void *,long *)

- ea: `0x1800f4c10`
- end: `0x1800f4d85`
- name: `?Shutdown@CRoamingMonitor@@UEAAJKPEAXPEAJ@Z`
- size: `373`
- prototype: `int(CRoamingMonitor *__hidden this, unsigned int, void *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004374`
- `0x180015c28`
- `0x180018170`
- `0x180018d3c`
- `0x18001f2e0`
- `0x18001f46c`
- `0x1800f4c10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800f4d35`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800f4d35`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800f4c93`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800f4c93`
- `KERNEL32!CloseHandle` at `0x1800f4cc5`
- `KERNEL32!CloseHandle` at `0x1800f4cc5`
- `KERNEL32!SetEvent` at `0x1800f4d6d`
- `KERNEL32!SetEvent` at `0x1800f4d6d`
- `wevtapi!EvtClose` at `0x1800f4cdc`
- `wevtapi!EvtClose` at `0x1800f4cdc`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800f4cf3`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800f4cf3`

## string_xrefs

- `0x1800f4c7b`: `CreateTimerQueue failed`

## pseudocode

```c
__int64 __fastcall CRoamingMonitor::Shutdown(RTL_SRWLOCK *this, __int64 a2, void *a3, int *a4)
{
  Timer::TimerQueue *v6; // rcx
  void *v7; // rax
  PVOID Ptr; // rcx
  PVOID v9; // rcx
  PVOID v10; // rcx
  HMODULE v11; // rcx
  _BYTE v13[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x10000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_bc905e231a60314e4c513b29466ae090_Traceguids);
  }
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v13, this + 6);
  if ( this[4].Ptr )
  {
    v7 = Timer::TimerQueue::Get(v6);
    if ( !v7 )
      SystemError::Throw(L"CreateTimerQueue failed");
    if ( !DeleteTimerQueueTimer(v7, this[4].Ptr, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      SystemError::Throw(L"Timer::CancelEngine");
    this[4].Ptr = 0;
  }
  LockSentry<ReadersWriterLock,0>::Unlock(v13);
  Ptr = this[7].Ptr;
  if ( Ptr )
  {
    CloseHandle(Ptr);
    this[7].Ptr = 0;
  }
  v9 = this[12].Ptr;
  if ( v9 )
  {
    EvtClose(v9);
    this[12].Ptr = 0;
  }
  v10 = this[8].Ptr;
  if ( v10 )
  {
    CancelMibChangeNotify2(v10);
    this[8].Ptr = 0;
  }
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v13, this + 5);
  this[11].Ptr = 0;
  LockSentry<ReadersWriterLock,0>::Unlock(v13);
  CThreadpoolEnvironment::CleanupGroupMembers((CThreadpoolEnvironment *)&this[15], 1u);
  v11 = (HMODULE)this[10].Ptr;
  if ( v11 )
  {
    FreeLibrary(v11);
    this[10].Ptr = 0;
  }
  this[9].Ptr = 0;
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v13, this + 5);
  HIDWORD(this[14].Ptr) = 0;
  LockSentry<ReadersWriterLock,0>::Unlock(v13);
  SetEvent(a3);
  return 0;
}

```

## disassembly

```asm
0x1800f4c10  mov     [rsp+arg_0], rbx
0x1800f4c15  mov     [rsp+arg_8], rsi
0x1800f4c1a  push    rdi
0x1800f4c1b  sub     rsp, 30h
0x1800f4c1f  mov     rsi, r8
0x1800f4c22  mov     rbx, rcx
0x1800f4c25  lea     rax, WPP_GLOBAL_Control
0x1800f4c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f4c33  cmp     rcx, rax
0x1800f4c36  jz      short loc_1800F4C5C
0x1800f4c38  test    dword ptr [rcx+6Ch], 10000000h
0x1800f4c3f  jz      short loc_1800F4C5C
0x1800f4c41  cmp     byte ptr [rcx+69h], 4
0x1800f4c45  jb      short loc_1800F4C5C
0x1800f4c47  mov     edx, 1Dh
0x1800f4c4c  lea     r8, WPP_bc905e231a60314e4c513b29466ae090_Traceguids
0x1800f4c53  mov     rcx, [rcx+60h]
0x1800f4c57  call    WPP_SF_
0x1800f4c5c  lea     rdx, [rbx+30h]
0x1800f4c60  lea     rcx, [rsp+38h+var_18]
0x1800f4c65  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x1800f4c6a  cmp     qword ptr [rbx+20h], 0
0x1800f4c6f  jz      short loc_1800F4CB2
0x1800f4c71  call    ?Get@TimerQueue@Timer@@QEAAQEAXXZ; Timer::TimerQueue::Get(void)
0x1800f4c76  test    rax, rax
0x1800f4c79  jnz     short loc_1800F4C88
0x1800f4c7b  lea     rcx, aCreatetimerque_0; "CreateTimerQueue failed"
0x1800f4c82  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x1800f4c88  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800f4c8c  mov     rdx, [rbx+20h]; Timer
0x1800f4c90  mov     rcx, rax; TimerQueue
0x1800f4c93  call    cs:__imp_DeleteTimerQueueTimer
0x1800f4c99  test    eax, eax
0x1800f4c9b  jnz     short loc_1800F4CAA
0x1800f4c9d  lea     rcx, aTimerCanceleng; "Timer::CancelEngine"
0x1800f4ca4  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x1800f4caa  mov     qword ptr [rbx+20h], 0
0x1800f4cb2  lea     rcx, [rsp+38h+var_18]
0x1800f4cb7  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x1800f4cbc  mov     rcx, [rbx+38h]; hObject
0x1800f4cc0  test    rcx, rcx
0x1800f4cc3  jz      short loc_1800F4CD3
0x1800f4cc5  call    cs:__imp_CloseHandle
0x1800f4ccb  mov     qword ptr [rbx+38h], 0
0x1800f4cd3  mov     rcx, [rbx+60h]; Object
0x1800f4cd7  test    rcx, rcx
0x1800f4cda  jz      short loc_1800F4CEA
0x1800f4cdc  call    cs:__imp_EvtClose
0x1800f4ce2  mov     qword ptr [rbx+60h], 0
0x1800f4cea  mov     rcx, [rbx+40h]; NotificationHandle
0x1800f4cee  test    rcx, rcx
0x1800f4cf1  jz      short loc_1800F4D01
0x1800f4cf3  call    cs:__imp_CancelMibChangeNotify2
0x1800f4cf9  mov     qword ptr [rbx+40h], 0
0x1800f4d01  lea     rdx, [rbx+28h]
0x1800f4d05  lea     rcx, [rsp+38h+var_18]
0x1800f4d0a  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x1800f4d0f  mov     qword ptr [rbx+58h], 0
0x1800f4d17  lea     rcx, [rsp+38h+var_18]
0x1800f4d1c  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x1800f4d21  lea     rcx, [rbx+78h]; this
0x1800f4d25  mov     dl, 1; bool
0x1800f4d27  call    ?CleanupGroupMembers@CThreadpoolEnvironment@@QEAAX_N@Z; CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x1800f4d2c  mov     rcx, [rbx+50h]; hLibModule
0x1800f4d30  test    rcx, rcx
0x1800f4d33  jz      short loc_1800F4D43
0x1800f4d35  call    cs:__imp_FreeLibrary
0x1800f4d3b  mov     qword ptr [rbx+50h], 0
0x1800f4d43  mov     qword ptr [rbx+48h], 0
0x1800f4d4b  lea     rdx, [rbx+28h]
0x1800f4d4f  lea     rcx, [rsp+38h+var_18]
0x1800f4d54  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x1800f4d59  mov     dword ptr [rbx+74h], 0
0x1800f4d60  lea     rcx, [rsp+38h+var_18]
0x1800f4d65  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x1800f4d6a  mov     rcx, rsi; hEvent
0x1800f4d6d  call    cs:__imp_SetEvent
0x1800f4d73  xor     eax, eax
0x1800f4d75  mov     rbx, [rsp+38h+arg_0]
0x1800f4d7a  mov     rsi, [rsp+38h+arg_8]
0x1800f4d7f  add     rsp, 30h
0x1800f4d83  pop     rdi
0x1800f4d84  retn
```
