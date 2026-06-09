# AfdWskCancelTransportChangeReq

- ea: `0x14005e450`
- end: `0x14005e58d`
- name: `AfdWskCancelTransportChangeReq`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14005e450`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005e477`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005e477`
- `ntoskrnl!IofCompleteRequest` at `0x14005e54e`
- `ntoskrnl!IofCompleteRequest` at `0x14005e54e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e52e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e57f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e52e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e57f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e4ff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e4ff`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e4a5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e4a5`
- `NDIS!NdisReleaseRWLock` at `0x14005e4ea`
- `NDIS!NdisReleaseRWLock` at `0x14005e4ea`

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
0x14005e450  push    rbx
0x14005e452  push    rbp
0x14005e453  push    rsi
0x14005e454  push    rdi
0x14005e455  sub     rsp, 48h
0x14005e459  mov     cl, [rdx+45h]; Irql
0x14005e45c  xor     eax, eax
0x14005e45e  xorps   xmm0, xmm0
0x14005e461  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x14005e466  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14005e46b  mov     word ptr [rsp+68h+LockState.OldIrql], ax
0x14005e470  mov     rsi, rdx
0x14005e473  mov     [rsp+68h+LockState.Flags], al
0x14005e477  call    cs:__imp_IoReleaseCancelSpinLock
0x14005e47e  nop     dword ptr [rax+rax+00h]
0x14005e483  mov     rbx, [rsi+0B8h]
0x14005e48a  lea     rdx, [rsp+68h+LockState]; LockState
0x14005e48f  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e496  add     rbx, 8
0x14005e49a  xor     r8d, r8d; Flags
0x14005e49d  mov     rdi, [rbx+18h]
0x14005e4a1  mov     rbp, [rdi+10h]
0x14005e4a5  call    cs:__imp_NdisAcquireRWLockWrite
0x14005e4ac  nop     dword ptr [rax+rax+00h]
0x14005e4b1  mov     rcx, [rdi]
0x14005e4b4  test    rcx, rcx
0x14005e4b7  jz      short loc_14005E4DE
0x14005e4b9  cmp     [rcx+8], rdi
0x14005e4bd  jnz     loc_14005E564
0x14005e4c3  mov     rax, [rdi+8]
0x14005e4c7  cmp     [rax], rdi
0x14005e4ca  jnz     loc_14005E564
0x14005e4d0  mov     [rax], rcx
0x14005e4d3  mov     [rcx+8], rax
0x14005e4d7  mov     qword ptr [rdi], 0
0x14005e4de  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e4e5  lea     rdx, [rsp+68h+LockState]; LockState
0x14005e4ea  call    cs:__imp_NdisReleaseRWLock
0x14005e4f1  nop     dword ptr [rax+rax+00h]
0x14005e4f6  lea     rcx, [rbp+18h]; SpinLock
0x14005e4fa  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x14005e4ff  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005e506  nop     dword ptr [rax+rax+00h]
0x14005e50b  mov     rax, [rbx]
0x14005e50e  test    rax, rax
0x14005e511  jz      short loc_14005E56B
0x14005e513  cmp     [rax+8], rbx
0x14005e517  jnz     short loc_14005E564
0x14005e519  mov     rcx, [rbx+8]
0x14005e51d  cmp     [rcx], rbx
0x14005e520  jnz     short loc_14005E564
0x14005e522  mov     [rcx], rax
0x14005e525  mov     [rax+8], rcx
0x14005e529  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14005e52e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e535  nop     dword ptr [rax+rax+00h]
0x14005e53a  xor     edx, edx; PriorityBoost
0x14005e53c  mov     dword ptr [rsi+30h], 0C0000120h
0x14005e543  mov     rcx, rsi; Irp
0x14005e546  mov     qword ptr [rsi+38h], 0
0x14005e54e  call    cs:__imp_IofCompleteRequest
0x14005e555  nop     dword ptr [rax+rax+00h]
0x14005e55a  add     rsp, 48h
0x14005e55e  pop     rdi
0x14005e55f  pop     rsi
0x14005e560  pop     rbp
0x14005e561  pop     rbx
0x14005e562  retn
0x14005e564  mov     ecx, 3
0x14005e569  int     29h; Win8: RtlFailFast(ecx)
0x14005e56b  cmp     qword ptr [rbx+8], 0
0x14005e570  jz      short loc_14005E529
0x14005e572  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14005e577  mov     qword ptr [rbx+8], 0
0x14005e57f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e586  nop     dword ptr [rax+rax+00h]
0x14005e58b  jmp     short loc_14005E55A
```
