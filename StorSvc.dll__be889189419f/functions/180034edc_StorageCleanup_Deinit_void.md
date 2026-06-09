# StorageCleanup::Deinit(void)

- ea: `0x180034edc`
- end: `0x180034ffb`
- name: `?Deinit@StorageCleanup@@QEAAJXZ`
- size: `287`
- prototype: `__int64 __fastcall(StorageCleanup *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800206d4`

## callees

- `0x180030ab0`
- `0x180034edc`
- `0x1800350b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034f35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034f35`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180034fd2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180034fd2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180034fc5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180034fc5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180034f55`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180034f55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034f1a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034f1a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180034f62`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180034f62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034f0d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034f0d`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x180034f80`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x180034f80`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageCleanup::Deinit(StorageCleanup *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rcx
  struct _TP_WORK *v4; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 69) )
  {
    Microsoft::WRL::Wrappers::CriticalSection::Lock((char *)this + 616, &lpCriticalSection);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 69), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 69));
    *((_QWORD *)this + 69) = 0;
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
  }
  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 68);
  if ( v2 )
  {
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 68));
    *((_QWORD *)this + 68) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 67);
  if ( v3 != (void *)-1LL )
  {
    FindCloseChangeNotification(v3);
    *((_QWORD *)this + 67) = -1;
  }
  if ( *(_QWORD *)this )
  {
    _InterlockedExchange((volatile __int32 *)this + 142, 0);
    StorageCleanup::PublishTempCleanupState(this, 0);
  }
  *(_QWORD *)this = 0;
  *((_WORD *)this + 6) = 0;
  v4 = (struct _TP_WORK *)*((_QWORD *)this + 84);
  if ( v4 )
  {
    WaitForThreadpoolWorkCallbacks(v4, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 84));
    *((_QWORD *)this + 84) = 0;
  }
  if ( *((_BYTE *)this + 752) )
    *((_BYTE *)this + 752) = 0;
  return 0;
}

```

## disassembly

```asm
0x180034edc  push    rbx
0x180034ede  sub     rsp, 20h
0x180034ee2  mov     rbx, rcx
0x180034ee5  cmp     qword ptr [rcx+228h], 0
0x180034eed  jz      short loc_180034F44
0x180034eef  add     rcx, 268h
0x180034ef6  lea     rdx, [rsp+28h+lpCriticalSection]
0x180034efb  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockCriticalSection@Details@234@XZ; Microsoft::WRL::Wrappers::CriticalSection::Lock(void)
0x180034f00  nop
0x180034f01  mov     edx, 1; fCancelPendingCallbacks
0x180034f06  mov     rcx, [rbx+228h]; pti
0x180034f0d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180034f13  mov     rcx, [rbx+228h]; pti
0x180034f1a  call    cs:__imp_CloseThreadpoolTimer
0x180034f20  mov     qword ptr [rbx+228h], 0
0x180034f2b  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x180034f30  test    rcx, rcx
0x180034f33  jz      short loc_180034F44
0x180034f35  call    cs:__imp_LeaveCriticalSection
0x180034f3b  mov     [rsp+28h+lpCriticalSection], 0
0x180034f44  mov     rcx, [rbx+220h]; pwa
0x180034f4b  test    rcx, rcx
0x180034f4e  jz      short loc_180034F73
0x180034f50  mov     edx, 1; fCancelPendingCallbacks
0x180034f55  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180034f5b  mov     rcx, [rbx+220h]; pwa
0x180034f62  call    cs:__imp_CloseThreadpoolWait
0x180034f68  mov     qword ptr [rbx+220h], 0
0x180034f73  mov     rcx, [rbx+218h]; hChangeHandle
0x180034f7a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180034f7e  jz      short loc_180034F91
0x180034f80  call    cs:__imp_FindCloseChangeNotification
0x180034f86  mov     qword ptr [rbx+218h], 0FFFFFFFFFFFFFFFFh
0x180034f91  cmp     qword ptr [rbx], 0
0x180034f95  jz      short loc_180034FA9
0x180034f97  xor     eax, eax
0x180034f99  xchg    eax, [rbx+238h]
0x180034f9f  xor     edx, edx
0x180034fa1  mov     rcx, rbx
0x180034fa4  call    ?PublishTempCleanupState@StorageCleanup@@QEAAJW4_STORAGE_TEMP_CLEANUP_STATE@@@Z; StorageCleanup::PublishTempCleanupState(_STORAGE_TEMP_CLEANUP_STATE)
0x180034fa9  mov     qword ptr [rbx], 0
0x180034fb0  xor     eax, eax
0x180034fb2  mov     [rbx+0Ch], ax
0x180034fb6  mov     rcx, [rbx+2A0h]; pwk
0x180034fbd  test    rcx, rcx
0x180034fc0  jz      short loc_180034FE3
0x180034fc2  lea     edx, [rax+1]; fCancelPendingCallbacks
0x180034fc5  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180034fcb  mov     rcx, [rbx+2A0h]; pwk
0x180034fd2  call    cs:__imp_CloseThreadpoolWork
0x180034fd8  mov     qword ptr [rbx+2A0h], 0
0x180034fe3  cmp     byte ptr [rbx+2F0h], 0
0x180034fea  jz      short loc_180034FF3
0x180034fec  mov     byte ptr [rbx+2F0h], 0
0x180034ff3  xor     eax, eax
0x180034ff5  add     rsp, 20h
0x180034ff9  pop     rbx
0x180034ffa  retn
```
