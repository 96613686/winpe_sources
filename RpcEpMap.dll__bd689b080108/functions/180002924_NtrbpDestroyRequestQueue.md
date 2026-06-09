# NtrbpDestroyRequestQueue

- ea: `0x180002924`
- end: `0x1800029b2`
- name: `NtrbpDestroyRequestQueue`
- size: `142`
- prototype: `void __fastcall(volatile signed __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002520`

## callees

- `0x180002924`
- `0x1800029b8`
- `0x18000335c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002947`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002947`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000295c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000295c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000296a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000296a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002973`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002973`

## pseudocode

```c
void __fastcall NtrbpDestroyRequestQueue(volatile signed __int64 *a1)
{
  struct _TP_TIMER *v2; // rbx

  if ( (unsigned int)NtrbpUnlinkQueueIfNecessary() )
  {
    _InterlockedOr64(a1 + 6, 1u);
    LeaveCriticalSection(&NtrbRequestQueuesLock);
    v2 = (struct _TP_TIMER *)*((_QWORD *)a1 + 3);
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    if ( (_InterlockedCompareExchange64(a1 + 6, 0, 0) & 2) != 0 )
      NtrbpReleaseQueueRef((void *)a1);
    NtrbpReleaseQueueRef((void *)a1);
  }
  else
  {
    LeaveCriticalSection(&NtrbRequestQueuesLock);
  }
}

```

## disassembly

```asm
0x180002924  mov     [rsp+arg_0], rbx
0x180002929  push    rdi
0x18000292a  sub     rsp, 20h
0x18000292e  mov     rdi, rcx
0x180002931  call    NtrbpUnlinkQueueIfNecessary
0x180002936  lea     rcx, NtrbRequestQueuesLock; lpCriticalSection
0x18000293d  test    eax, eax
0x18000293f  jz      short loc_1800029AA
0x180002941  lock or qword ptr [rdi+30h], 1
0x180002947  call    cs:__imp_LeaveCriticalSection
0x18000294d  mov     rbx, [rdi+18h]
0x180002951  xor     r9d, r9d; msWindowLength
0x180002954  mov     rcx, rbx; pti
0x180002957  xor     r8d, r8d; msPeriod
0x18000295a  xor     edx, edx; pftDueTime
0x18000295c  call    cs:__imp_SetThreadpoolTimer
0x180002962  mov     edx, 1; fCancelPendingCallbacks
0x180002967  mov     rcx, rbx; pti
0x18000296a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002970  mov     rcx, rbx; pti
0x180002973  call    cs:__imp_CloseThreadpoolTimer
0x180002979  xor     ecx, ecx
0x18000297b  xor     eax, eax
0x18000297d  lock cmpxchg [rdi+30h], rcx
0x180002983  lea     edx, [rcx+2]
0x180002986  test    dl, al
0x180002988  jz      short loc_180002992
0x18000298a  mov     rcx, rdi; void *
0x18000298d  call    NtrbpReleaseQueueRef
0x180002992  mov     edx, 1
0x180002997  mov     rcx, rdi; void *
0x18000299a  call    NtrbpReleaseQueueRef
0x18000299f  mov     rbx, [rsp+28h+arg_0]
0x1800029a4  add     rsp, 20h
0x1800029a8  pop     rdi
0x1800029a9  retn
0x1800029aa  call    cs:__imp_LeaveCriticalSection
0x1800029b0  jmp     short loc_18000299F
```
