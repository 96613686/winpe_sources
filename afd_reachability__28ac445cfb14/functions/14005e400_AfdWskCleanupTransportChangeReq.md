# AfdWskCleanupTransportChangeReq

- ea: `0x14005e400`
- end: `0x14005e52f`
- name: `AfdWskCleanupTransportChangeReq`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14005e400`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005e4ac`
- `ntoskrnl!IofCompleteRequest` at `0x14005e4ac`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e4e8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e510`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e4e8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e510`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e4cc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e4cc`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e43f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e43f`
- `NDIS!NdisReleaseRWLock` at `0x14005e47c`
- `NDIS!NdisReleaseRWLock` at `0x14005e47c`

## pseudocode

```c
char __fastcall AfdWskCleanupTransportChangeReq(__int64 a1, __int64 a2)
{
  __int64 *v2; // rbx
  __int64 v5; // rdx
  __int64 **v6; // rax
  IRP *v7; // rcx
  IRP *v9; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(__int64 **)(a2 + 24);
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  NdisAcquireRWLockWrite(AfdTlTransportLock, &LockState, 0);
  v5 = *v2;
  if ( *v2 )
  {
    if ( *(__int64 **)(v5 + 8) != v2 || (v6 = (__int64 **)v2[1], *v6 != v2) )
      __fastfail(3u);
    *v6 = (__int64 *)v5;
    *(_QWORD *)(v5 + 8) = v6;
    *v2 = 0;
  }
  NdisReleaseRWLock(AfdTlTransportLock, &LockState);
  if ( _InterlockedExchange64((volatile __int64 *)(v2[3] + 104), 0) )
  {
    v7 = (IRP *)v2[3];
    v7->IoStatus.Status = -1073741536;
    v7->IoStatus.Information = 0;
LABEL_7:
    IofCompleteRequest(v7, 0);
    return 1;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 24), &LockHandle);
  if ( !*(_QWORD *)(a2 + 8) )
  {
    v9 = (IRP *)v2[3];
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v7 = v9;
    v9->IoStatus.Status = -1073741536;
    v9->IoStatus.Information = 0;
    goto LABEL_7;
  }
  *(_QWORD *)(a2 + 8) = 0;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return 0;
}

```

## disassembly

```asm
0x14005e400  mov     r11, rsp
0x14005e403  mov     [r11+10h], rbx
0x14005e407  mov     [r11+18h], rsi
0x14005e40b  push    rdi
0x14005e40c  sub     rsp, 40h
0x14005e410  mov     rbx, [rdx+18h]
0x14005e414  xor     eax, eax
0x14005e416  xorps   xmm0, xmm0
0x14005e419  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14005e41e  mov     rdi, rdx
0x14005e421  mov     [rsp+48h+LockState.Flags], al
0x14005e425  mov     rsi, rcx
0x14005e428  lea     rdx, [r11+8]; LockState
0x14005e42c  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e433  xor     r8d, r8d; Flags
0x14005e436  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14005e43b  mov     [r11-18h], rax
0x14005e43f  call    cs:__imp_NdisAcquireRWLockWrite
0x14005e446  nop     dword ptr [rax+rax+00h]
0x14005e44b  mov     rdx, [rbx]
0x14005e44e  test    rdx, rdx
0x14005e451  jz      short loc_14005E470
0x14005e453  cmp     [rdx+8], rbx
0x14005e457  jnz     short loc_14005E4BC
0x14005e459  mov     rax, [rbx+8]
0x14005e45d  cmp     [rax], rbx
0x14005e460  jnz     short loc_14005E4BC
0x14005e462  mov     [rax], rdx
0x14005e465  mov     [rdx+8], rax
0x14005e469  mov     qword ptr [rbx], 0
0x14005e470  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e477  lea     rdx, [rsp+48h+LockState]; LockState
0x14005e47c  call    cs:__imp_NdisReleaseRWLock
0x14005e483  nop     dword ptr [rax+rax+00h]
0x14005e488  mov     rax, [rbx+18h]
0x14005e48c  xor     ecx, ecx
0x14005e48e  xchg    rcx, [rax+68h]
0x14005e492  test    rcx, rcx
0x14005e495  jz      short loc_14005E4C3
0x14005e497  mov     rcx, [rbx+18h]; Irp
0x14005e49b  mov     dword ptr [rcx+30h], 0C0000120h
0x14005e4a2  mov     qword ptr [rcx+38h], 0
0x14005e4aa  xor     edx, edx; PriorityBoost
0x14005e4ac  call    cs:__imp_IofCompleteRequest
0x14005e4b3  nop     dword ptr [rax+rax+00h]
0x14005e4b8  mov     al, 1
0x14005e4ba  jmp     short loc_14005E51E
0x14005e4bc  mov     ecx, 3
0x14005e4c1  int     29h; Win8: RtlFailFast(ecx)
0x14005e4c3  lea     rcx, [rsi+18h]; SpinLock
0x14005e4c7  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14005e4cc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005e4d3  nop     dword ptr [rax+rax+00h]
0x14005e4d8  cmp     qword ptr [rdi+8], 0
0x14005e4dd  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14005e4e2  jnz     short loc_14005E508
0x14005e4e4  mov     rbx, [rbx+18h]
0x14005e4e8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e4ef  nop     dword ptr [rax+rax+00h]
0x14005e4f4  mov     rcx, rbx
0x14005e4f7  mov     dword ptr [rbx+30h], 0C0000120h
0x14005e4fe  mov     qword ptr [rbx+38h], 0
0x14005e506  jmp     short loc_14005E4AA
0x14005e508  mov     qword ptr [rdi+8], 0
0x14005e510  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e517  nop     dword ptr [rax+rax+00h]
0x14005e51c  xor     al, al
0x14005e51e  mov     rbx, [rsp+48h+arg_8]
0x14005e523  mov     rsi, [rsp+48h+arg_10]
0x14005e528  add     rsp, 40h
0x14005e52c  pop     rdi
0x14005e52d  retn
```
