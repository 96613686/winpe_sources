# NtrbShutdown

- ea: `0x180009384`
- end: `0x18000949b`
- name: `NtrbShutdown`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005ae0`

## callees

- `0x1800029b8`
- `0x180009384`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800093d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800093d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009420`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009420`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000946c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000946c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180009438`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180009438`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180009479`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180009479`

## pseudocode

```c
__int64 NtrbShutdown()
{
  signed __int32 v0; // eax
  unsigned int v1; // ebx
  void **v2; // rdi
  void **v3; // rcx
  void *v5[2]; // [rsp+20h] [rbp-18h] BYREF

  *(_OWORD *)v5 = 0;
  v0 = _InterlockedCompareExchange(&NtrbState, 2, 1);
  if ( v0 == 1 )
  {
    v1 = 0;
    EnterCriticalSection(&NtrbRequestQueuesLock);
    *(_OWORD *)v5 = NtrbRequestQueueListHead;
    *(_QWORD *)(NtrbRequestQueueListHead + 8) = v5;
    **((_QWORD **)&NtrbRequestQueueListHead + 1) = v5;
    *(_QWORD *)&NtrbRequestQueueListHead = &NtrbRequestQueueListHead;
    *((_QWORD *)&NtrbRequestQueueListHead + 1) = &NtrbRequestQueueListHead;
    LeaveCriticalSection(&NtrbRequestQueuesLock);
    v2 = (void **)v5[0];
    CloseThreadpoolCleanupGroupMembers(NtrbTimeoutTimerCleanupGroup, 1, 0);
    while ( v2 != v5 )
    {
      if ( !v2 )
        break;
      v3 = v2;
      v2 = (void **)*v2;
      NtrbpReleaseQueueRef(v3);
    }
    DeleteCriticalSection(&NtrbRequestQueuesLock);
    CloseThreadpoolCleanupGroup(NtrbTimeoutTimerCleanupGroup);
    _InterlockedCompareExchange(&NtrbState, 0, 2);
  }
  else if ( v0 == 2 )
  {
    return 1115;
  }
  else
  {
    v1 = 0;
    if ( v0 == 3 )
      return 21;
  }
  return v1;
}

```

## disassembly

```asm
0x180009384  mov     [rsp+arg_0], rbx
0x180009389  mov     [rsp+arg_8], rsi
0x18000938e  push    rdi
0x18000938f  sub     rsp, 30h
0x180009393  mov     esi, 2
0x180009398  xorps   xmm0, xmm0
0x18000939b  movups  xmmword ptr [rsp+38h+var_18], xmm0
0x1800093a0  lea     eax, [rsi-1]
0x1800093a3  lock cmpxchg cs:NtrbState, esi
0x1800093ab  jz      short loc_1800093CB
0x1800093ad  cmp     eax, esi
0x1800093af  jnz     short loc_1800093BB
0x1800093b1  mov     ebx, 45Bh
0x1800093b6  jmp     loc_180009489
0x1800093bb  xor     ebx, ebx
0x1800093bd  cmp     eax, 3
0x1800093c0  lea     ecx, [rbx+15h]
0x1800093c3  cmovz   ebx, ecx
0x1800093c6  jmp     loc_180009489
0x1800093cb  lea     rcx, NtrbRequestQueuesLock; lpCriticalSection
0x1800093d2  xor     ebx, ebx
0x1800093d4  call    cs:__imp_EnterCriticalSection
0x1800093da  movups  xmm0, cs:NtrbRequestQueueListHead
0x1800093e1  lea     rcx, [rsp+38h+var_18]
0x1800093e6  movq    rax, xmm0
0x1800093eb  movdqu  xmmword ptr [rsp+38h+var_18], xmm0
0x1800093f1  mov     [rax+8], rcx
0x1800093f5  lea     rcx, [rsp+38h+var_18]
0x1800093fa  mov     rax, qword ptr cs:NtrbRequestQueueListHead+8
0x180009401  mov     [rax], rcx
0x180009404  lea     rax, NtrbRequestQueueListHead
0x18000940b  lea     rcx, NtrbRequestQueuesLock; lpCriticalSection
0x180009412  mov     qword ptr cs:NtrbRequestQueueListHead, rax
0x180009419  mov     qword ptr cs:NtrbRequestQueueListHead+8, rax
0x180009420  call    cs:__imp_LeaveCriticalSection
0x180009426  mov     rcx, cs:NtrbTimeoutTimerCleanupGroup; ptpcg
0x18000942d  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x180009430  mov     rdi, [rsp+38h+var_18]
0x180009435  xor     r8d, r8d; pvCleanupContext
0x180009438  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000943e  lea     rax, [rsp+38h+var_18]
0x180009443  cmp     rdi, rax
0x180009446  jz      short loc_180009465
0x180009448  test    rdi, rdi
0x18000944b  jz      short loc_180009465
0x18000944d  mov     rcx, rdi; void *
0x180009450  mov     rdx, rsi
0x180009453  mov     rdi, [rdi]
0x180009456  call    NtrbpReleaseQueueRef
0x18000945b  lea     rdx, [rsp+38h+var_18]
0x180009460  cmp     rdi, rdx
0x180009463  jnz     short loc_180009448
0x180009465  lea     rcx, NtrbRequestQueuesLock; lpCriticalSection
0x18000946c  call    cs:__imp_DeleteCriticalSection
0x180009472  mov     rcx, cs:NtrbTimeoutTimerCleanupGroup; ptpcg
0x180009479  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000947f  mov     eax, esi
0x180009481  lock cmpxchg cs:NtrbState, ebx
0x180009489  mov     rsi, [rsp+38h+arg_8]
0x18000948e  mov     eax, ebx
0x180009490  mov     rbx, [rsp+38h+arg_0]
0x180009495  add     rsp, 30h
0x180009499  pop     rdi
0x18000949a  retn
```
