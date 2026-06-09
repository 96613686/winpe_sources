# BipWorkItemTpWorkerQueueTaskInstanceDestroy

- ea: `0x18000e360`
- end: `0x18000e45e`
- name: `BipWorkItemTpWorkerQueueTaskInstanceDestroy`
- size: `254`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180011850`
- `0x180012960`
- `0x1800163d0`
- `0x180016a9c`
- `0x180057990`
- `0x18005a570`

## callees

- `0x18000e360`
- `0x18000e470`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e37b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e3c5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e37b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e3c5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e38d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e421`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e38d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e421`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e3cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e3cb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e43c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e43c`

## pseudocode

```c
__int64 __fastcall BipWorkItemTpWorkerQueueTaskInstanceDestroy(__int64 a1, __int64 a2)
{
  struct _BI_LOCK *v4; // rdi
  unsigned int v5; // ebp
  __int64 v6; // rbx
  DWORD CurrentThreadId; // eax
  _QWORD *v8; // rdx
  int v9; // esi
  __int64 result; // rax

  RtlAcquireSRWLockExclusive(a2 + 48);
  *(_DWORD *)(a2 + 136) |= 0x40u;
  RtlReleaseSRWLockExclusive(a2 + 48);
  v4 = (struct _BI_LOCK *)(a1 + 56);
  v5 = 1 << *(_DWORD *)(a1 + 64);
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_DWORD *)(v6 + 4) >= v5 && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug(v4);
  RtlAcquireSRWLockExclusive(v4);
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(v6 + 4) |= v5;
  *(_DWORD *)(a1 + 68) = CurrentThreadId;
  v8 = *(_QWORD **)(a1 + 496);
  *(_DWORD *)(v6 + 8) |= v5;
  if ( *v8 != a1 + 488 )
    __fastfail(3u);
  *(_QWORD *)(a2 + 96) = a1 + 488;
  *(_QWORD *)(a2 + 104) = v8;
  *v8 = a2 + 96;
  *(_QWORD *)(a1 + 496) = a2 + 96;
  BipWorkItemTpWorkerQueueNewWork(a1);
  v9 = ~(1 << *(_DWORD *)(a1 + 64));
  *(_DWORD *)(a1 + 68) = 0;
  *(_DWORD *)(v6 + 8) &= v9;
  result = RtlReleaseSRWLockExclusive(a1 + 56);
  *(_DWORD *)(v6 + 4) &= v9;
  return result;
}

```

## disassembly

```asm
0x18000e360  push    rbx
0x18000e362  push    rbp
0x18000e363  push    rsi
0x18000e364  push    rdi
0x18000e365  push    r12
0x18000e367  push    r13
0x18000e369  push    r14
0x18000e36b  push    r15
0x18000e36d  sub     rsp, 28h
0x18000e371  mov     r14, rcx
0x18000e374  mov     r15, rdx
0x18000e377  lea     rcx, [rdx+30h]
0x18000e37b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e381  or      dword ptr [r15+88h], 40h
0x18000e389  lea     rcx, [r15+30h]
0x18000e38d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e393  mov     rax, gs:58h
0x18000e39c  lea     rdi, [r14+38h]
0x18000e3a0  mov     ecx, [rdi+8]
0x18000e3a3  mov     esi, 1
0x18000e3a8  mov     ebp, esi
0x18000e3aa  mov     r13d, 4
0x18000e3b0  shl     ebp, cl
0x18000e3b2  mov     ecx, cs:_tls_index
0x18000e3b8  mov     rbx, [rax+rcx*8]
0x18000e3bc  cmp     [rbx+r13], ebp
0x18000e3c0  jnb     short loc_18000E43C
0x18000e3c2  mov     rcx, rdi
0x18000e3c5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e3cb  call    cs:__imp_GetCurrentThreadId
0x18000e3d1  or      [rbx+r13], ebp
0x18000e3d5  lea     rcx, [r14+1E8h]
0x18000e3dc  mov     [rdi+0Ch], eax
0x18000e3df  mov     rdx, [rcx+8]
0x18000e3e3  mov     r12d, 8
0x18000e3e9  or      [r12+rbx], ebp
0x18000e3ed  cmp     [rdx], rcx
0x18000e3f0  jnz     short loc_18000E457
0x18000e3f2  lea     rax, [r15+60h]
0x18000e3f6  mov     [rax], rcx
0x18000e3f9  mov     [rax+8], rdx
0x18000e3fd  mov     [rdx], rax
0x18000e400  mov     [rcx+8], rax
0x18000e404  mov     rcx, r14
0x18000e407  call    BipWorkItemTpWorkerQueueNewWork
0x18000e40c  mov     ecx, [rdi+8]
0x18000e40f  shl     esi, cl
0x18000e411  mov     rcx, rdi
0x18000e414  not     esi
0x18000e416  mov     dword ptr [rdi+0Ch], 0
0x18000e41d  and     [r12+rbx], esi
0x18000e421  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e427  and     [rbx+r13], esi
0x18000e42b  add     rsp, 28h
0x18000e42f  pop     r15
0x18000e431  pop     r14
0x18000e433  pop     r13
0x18000e435  pop     r12
0x18000e437  pop     rdi
0x18000e438  pop     rsi
0x18000e439  pop     rbp
0x18000e43a  pop     rbx
0x18000e43b  retn
0x18000e43c  call    cs:__imp_IsDebuggerPresent
0x18000e442  test    eax, eax
0x18000e444  jz      loc_18000E3C2
0x18000e44a  mov     rcx, rdi; struct _BI_LOCK *
0x18000e44d  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18000e452  jmp     loc_18000E3C2
0x18000e457  mov     ecx, 3
0x18000e45c  int     29h; Win8: RtlFailFast(ecx)
```
