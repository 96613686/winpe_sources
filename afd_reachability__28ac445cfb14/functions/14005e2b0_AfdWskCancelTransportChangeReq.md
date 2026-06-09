# AfdWskCancelTransportChangeReq

- ea: `0x14005e2b0`
- end: `0x14005e3ed`
- name: `AfdWskCancelTransportChangeReq`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14005e2b0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005e2d7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005e2d7`
- `ntoskrnl!IofCompleteRequest` at `0x14005e3ae`
- `ntoskrnl!IofCompleteRequest` at `0x14005e3ae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e38e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e3df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e38e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e3df`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e35f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e35f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e305`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e305`
- `NDIS!NdisReleaseRWLock` at `0x14005e34a`
- `NDIS!NdisReleaseRWLock` at `0x14005e34a`

## pseudocode

```c
void __fastcall AfdWskCancelTransportChangeReq(__int64 a1, IRP *a2)
{
  KIRQL CancelIrql; // cl
  struct _IO_STACK_LOCATION::$3F40624FA6BA75D391A2F4D7FEA8ACCF::$D24474CE3B68EBF89E5A61C71CBC75EE *p_Parameters; // rbx
  _QWORD *p_NamedPipeType; // rdi
  __int64 v6; // rbp
  __int64 v7; // rcx
  _QWORD *v8; // rax
  ULONG_PTR ProviderId; // rax
  struct _IO_STACK_LOCATION::$3F40624FA6BA75D391A2F4D7FEA8ACCF::$D24474CE3B68EBF89E5A61C71CBC75EE **DataPath; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+10h] BYREF

  CancelIrql = a2->CancelIrql;
  memset(&LockHandle, 0, sizeof(LockHandle));
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  IoReleaseCancelSpinLock(CancelIrql);
  p_Parameters = (struct _IO_STACK_LOCATION::$3F40624FA6BA75D391A2F4D7FEA8ACCF::$D24474CE3B68EBF89E5A61C71CBC75EE *)&a2->Tail.Overlay.CurrentStackLocation->Parameters;
  p_NamedPipeType = &a2->Tail.Overlay.CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
  v6 = p_NamedPipeType[2];
  NdisAcquireRWLockWrite(AfdTlTransportLock, &LockState, 0);
  v7 = *p_NamedPipeType;
  if ( *p_NamedPipeType )
  {
    if ( *(_QWORD **)(v7 + 8) != p_NamedPipeType )
      goto LABEL_10;
    v8 = (_QWORD *)p_NamedPipeType[1];
    if ( (_QWORD *)*v8 != p_NamedPipeType )
      goto LABEL_10;
    *v8 = v7;
    *(_QWORD *)(v7 + 8) = v8;
    *p_NamedPipeType = 0;
  }
  NdisReleaseRWLock(AfdTlTransportLock, &LockState);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 24), &LockHandle);
  ProviderId = p_Parameters->ProviderId;
  if ( p_Parameters->ProviderId )
  {
    if ( *(struct _IO_STACK_LOCATION::$3F40624FA6BA75D391A2F4D7FEA8ACCF::$D24474CE3B68EBF89E5A61C71CBC75EE **)(ProviderId + 8) == p_Parameters )
    {
      DataPath = (struct _IO_STACK_LOCATION::$3F40624FA6BA75D391A2F4D7FEA8ACCF::$D24474CE3B68EBF89E5A61C71CBC75EE **)p_Parameters->DataPath;
      if ( *DataPath == p_Parameters )
      {
        *DataPath = (struct _IO_STACK_LOCATION::$3F40624FA6BA75D391A2F4D7FEA8ACCF::$D24474CE3B68EBF89E5A61C71CBC75EE *)ProviderId;
        *(_QWORD *)(ProviderId + 8) = DataPath;
LABEL_9:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        a2->IoStatus.Status = -1073741536;
        a2->IoStatus.Information = 0;
        IofCompleteRequest(a2, 0);
        return;
      }
    }
LABEL_10:
    __fastfail(3u);
  }
  if ( !p_Parameters->DataPath )
    goto LABEL_9;
  p_Parameters->DataPath = 0;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
}

```

## disassembly

```asm
0x14005e2b0  push    rbx
0x14005e2b2  push    rbp
0x14005e2b3  push    rsi
0x14005e2b4  push    rdi
0x14005e2b5  sub     rsp, 48h
0x14005e2b9  mov     cl, [rdx+45h]; Irql
0x14005e2bc  xor     eax, eax
0x14005e2be  xorps   xmm0, xmm0
0x14005e2c1  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x14005e2c6  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14005e2cb  mov     word ptr [rsp+68h+LockState.OldIrql], ax
0x14005e2d0  mov     rsi, rdx
0x14005e2d3  mov     [rsp+68h+LockState.Flags], al
0x14005e2d7  call    cs:__imp_IoReleaseCancelSpinLock
0x14005e2de  nop     dword ptr [rax+rax+00h]
0x14005e2e3  mov     rbx, [rsi+0B8h]
0x14005e2ea  lea     rdx, [rsp+68h+LockState]; LockState
0x14005e2ef  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e2f6  add     rbx, 8
0x14005e2fa  xor     r8d, r8d; Flags
0x14005e2fd  mov     rdi, [rbx+18h]
0x14005e301  mov     rbp, [rdi+10h]
0x14005e305  call    cs:__imp_NdisAcquireRWLockWrite
0x14005e30c  nop     dword ptr [rax+rax+00h]
0x14005e311  mov     rcx, [rdi]
0x14005e314  test    rcx, rcx
0x14005e317  jz      short loc_14005E33E
0x14005e319  cmp     [rcx+8], rdi
0x14005e31d  jnz     loc_14005E3C4
0x14005e323  mov     rax, [rdi+8]
0x14005e327  cmp     [rax], rdi
0x14005e32a  jnz     loc_14005E3C4
0x14005e330  mov     [rax], rcx
0x14005e333  mov     [rcx+8], rax
0x14005e337  mov     qword ptr [rdi], 0
0x14005e33e  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e345  lea     rdx, [rsp+68h+LockState]; LockState
0x14005e34a  call    cs:__imp_NdisReleaseRWLock
0x14005e351  nop     dword ptr [rax+rax+00h]
0x14005e356  lea     rcx, [rbp+18h]; SpinLock
0x14005e35a  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x14005e35f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005e366  nop     dword ptr [rax+rax+00h]
0x14005e36b  mov     rax, [rbx]
0x14005e36e  test    rax, rax
0x14005e371  jz      short loc_14005E3CB
0x14005e373  cmp     [rax+8], rbx
0x14005e377  jnz     short loc_14005E3C4
0x14005e379  mov     rcx, [rbx+8]
0x14005e37d  cmp     [rcx], rbx
0x14005e380  jnz     short loc_14005E3C4
0x14005e382  mov     [rcx], rax
0x14005e385  mov     [rax+8], rcx
0x14005e389  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14005e38e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e395  nop     dword ptr [rax+rax+00h]
0x14005e39a  xor     edx, edx; PriorityBoost
0x14005e39c  mov     dword ptr [rsi+30h], 0C0000120h
0x14005e3a3  mov     rcx, rsi; Irp
0x14005e3a6  mov     qword ptr [rsi+38h], 0
0x14005e3ae  call    cs:__imp_IofCompleteRequest
0x14005e3b5  nop     dword ptr [rax+rax+00h]
0x14005e3ba  add     rsp, 48h
0x14005e3be  pop     rdi
0x14005e3bf  pop     rsi
0x14005e3c0  pop     rbp
0x14005e3c1  pop     rbx
0x14005e3c2  retn
0x14005e3c4  mov     ecx, 3
0x14005e3c9  int     29h; Win8: RtlFailFast(ecx)
0x14005e3cb  cmp     qword ptr [rbx+8], 0
0x14005e3d0  jz      short loc_14005E389
0x14005e3d2  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14005e3d7  mov     qword ptr [rbx+8], 0
0x14005e3df  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e3e6  nop     dword ptr [rax+rax+00h]
0x14005e3eb  jmp     short loc_14005E3BA
```
