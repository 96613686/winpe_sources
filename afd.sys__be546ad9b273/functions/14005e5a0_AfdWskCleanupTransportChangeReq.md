# AfdWskCleanupTransportChangeReq

- ea: `0x14005e5a0`
- end: `0x14005e6cf`
- name: `AfdWskCleanupTransportChangeReq`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14005e5a0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005e64c`
- `ntoskrnl!IofCompleteRequest` at `0x14005e64c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e688`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e6b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e688`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e6b0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e66c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e66c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e5df`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e5df`
- `NDIS!NdisReleaseRWLock` at `0x14005e61c`
- `NDIS!NdisReleaseRWLock` at `0x14005e61c`

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
0x14005e5a0  mov     r11, rsp
0x14005e5a3  mov     [r11+10h], rbx
0x14005e5a7  mov     [r11+18h], rsi
0x14005e5ab  push    rdi
0x14005e5ac  sub     rsp, 40h
0x14005e5b0  mov     rbx, [rdx+18h]
0x14005e5b4  xor     eax, eax
0x14005e5b6  xorps   xmm0, xmm0
0x14005e5b9  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14005e5be  mov     rdi, rdx
0x14005e5c1  mov     [rsp+48h+LockState.Flags], al
0x14005e5c5  mov     rsi, rcx
0x14005e5c8  lea     rdx, [r11+8]; LockState
0x14005e5cc  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e5d3  xor     r8d, r8d; Flags
0x14005e5d6  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14005e5db  mov     [r11-18h], rax
0x14005e5df  call    cs:__imp_NdisAcquireRWLockWrite
0x14005e5e6  nop     dword ptr [rax+rax+00h]
0x14005e5eb  mov     rdx, [rbx]
0x14005e5ee  test    rdx, rdx
0x14005e5f1  jz      short loc_14005E610
0x14005e5f3  cmp     [rdx+8], rbx
0x14005e5f7  jnz     short loc_14005E65C
0x14005e5f9  mov     rax, [rbx+8]
0x14005e5fd  cmp     [rax], rbx
0x14005e600  jnz     short loc_14005E65C
0x14005e602  mov     [rax], rdx
0x14005e605  mov     [rdx+8], rax
0x14005e609  mov     qword ptr [rbx], 0
0x14005e610  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e617  lea     rdx, [rsp+48h+LockState]; LockState
0x14005e61c  call    cs:__imp_NdisReleaseRWLock
0x14005e623  nop     dword ptr [rax+rax+00h]
0x14005e628  mov     rax, [rbx+18h]
0x14005e62c  xor     ecx, ecx
0x14005e62e  xchg    rcx, [rax+68h]
0x14005e632  test    rcx, rcx
0x14005e635  jz      short loc_14005E663
0x14005e637  mov     rcx, [rbx+18h]; Irp
0x14005e63b  mov     dword ptr [rcx+30h], 0C0000120h
0x14005e642  mov     qword ptr [rcx+38h], 0
0x14005e64a  xor     edx, edx; PriorityBoost
0x14005e64c  call    cs:__imp_IofCompleteRequest
0x14005e653  nop     dword ptr [rax+rax+00h]
0x14005e658  mov     al, 1
0x14005e65a  jmp     short loc_14005E6BE
0x14005e65c  mov     ecx, 3
0x14005e661  int     29h; Win8: RtlFailFast(ecx)
0x14005e663  lea     rcx, [rsi+18h]; SpinLock
0x14005e667  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14005e66c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005e673  nop     dword ptr [rax+rax+00h]
0x14005e678  cmp     qword ptr [rdi+8], 0
0x14005e67d  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14005e682  jnz     short loc_14005E6A8
0x14005e684  mov     rbx, [rbx+18h]
0x14005e688  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e68f  nop     dword ptr [rax+rax+00h]
0x14005e694  mov     rcx, rbx
0x14005e697  mov     dword ptr [rbx+30h], 0C0000120h
0x14005e69e  mov     qword ptr [rbx+38h], 0
0x14005e6a6  jmp     short loc_14005E64A
0x14005e6a8  mov     qword ptr [rdi+8], 0
0x14005e6b0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e6b7  nop     dword ptr [rax+rax+00h]
0x14005e6bc  xor     al, al
0x14005e6be  mov     rbx, [rsp+48h+arg_8]
0x14005e6c3  mov     rsi, [rsp+48h+arg_10]
0x14005e6c8  add     rsp, 40h
0x14005e6cc  pop     rdi
0x14005e6cd  retn
```
