# AfdTLDgramConnectComplete

- ea: `0x14001af00`
- end: `0x14001b0ca`
- name: `AfdTLDgramConnectComplete`
- size: `458`
- prototype: `void __fastcall(PIRP Irp, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14000f450`
- `0x140010670`
- `0x1400137a0`
- `0x14001af00`
- `0x14001b0d0`
- `0x14001b0f8`
- `0x14001b800`
- `0x140050be4`
- `0x1400931f0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14001b087`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001b087`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001b0b9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001b0b9`
- `ntoskrnl!IofCompleteRequest` at `0x14001b029`
- `ntoskrnl!IofCompleteRequest` at `0x14001b029`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b008`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b008`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001afe9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001afe9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001af67`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001af67`

## pseudocode

```c
void __fastcall AfdTLDgramConnectComplete(PIRP Irp, unsigned int a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _QWORD *p_Type; // r15
  __int64 v6; // rdi
  int v7; // eax
  unsigned __int16 v8; // r14
  __int64 v9; // rcx
  char v10; // bl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-68h] BYREF
  __int128 v12; // [rsp+48h] [rbp-50h]
  __int64 v13; // [rsp+58h] [rbp-40h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  memset(&LockHandle, 0, sizeof(LockHandle));
  p_Type = &CurrentStackLocation->FileObject->Type;
  v6 = p_Type[3];
  if ( (xmmword_1400875E0 & 0x80u) != 0LL )
    WPP_SF_Dq(1031, 23, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids, a2, p_Type[3]);
  Irp->IoStatus.Status = a2;
  AFDETW_TRACECONNECT(1, 5506, v6, a2, 0);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 56), &LockHandle);
  if ( (a2 & 0x80000000) != 0 )
  {
    v8 = 256;
  }
  else
  {
    v7 = *(_DWORD *)(v6 + 8);
    v8 = 68;
    *(_BYTE *)(v6 + 2) = 4;
    *(_DWORD *)(v6 + 8) = v7 | 0x2000000;
  }
  AfdIndicateEventSelectEvent(v6, v8, a2);
  AfdNotifySockEventsChangedUnderLock(v6, v8, 0);
  if ( AfdIndicatePollEvent(v9, v8, a2, &LockHandle) )
  {
    AfdNotifySockIndicateEventsUnlock(v6, 0, 0);
  }
  else
  {
    v10 = 0;
    v13 = 0;
    v12 = 0;
    if ( *(_QWORD *)(v6 + 384) && ExAcquireRundownProtection((PEX_RUNDOWN_REF)(v6 + 392)) )
    {
      v10 = 1;
      AfdNotifyPostEvents(v6, &LockHandle, 0);
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v10 )
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v6 + 392));
  }
  _InterlockedExchange((volatile __int32 *)(v6 + 368), 0);
  ObfDereferenceObject(p_Type);
  if ( AfdTLCompleteRequest((__int64)Irp) )
    IofCompleteRequest(Irp, AfdPriorityBoost);
}

```

## disassembly

```asm
0x14001af00  push    rbx
0x14001af02  push    rbp
0x14001af03  push    rsi
0x14001af04  push    rdi
0x14001af05  push    r14
0x14001af07  push    r15
0x14001af09  sub     rsp, 68h
0x14001af0d  xor     eax, eax
0x14001af0f  xorps   xmm0, xmm0
0x14001af12  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x14001af17  mov     esi, edx
0x14001af19  mov     rax, [rcx+0B8h]
0x14001af20  mov     rbp, rcx
0x14001af23  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x14001af28  mov     r15, [rax+30h]
0x14001af2c  mov     rdi, [r15+18h]
0x14001af30  cmp     byte ptr cs:xmmword_1400875E0, 0
0x14001af37  jl      loc_14001B05D
0x14001af3d  mov     r9d, esi
0x14001af40  mov     [rbp+30h], esi
0x14001af43  mov     r8, rdi
0x14001af46  mov     [rsp+98h+var_78], 0
0x14001af4f  mov     edx, 1582h
0x14001af54  mov     ecx, 1
0x14001af59  call    AFDETW_TRACECONNECT
0x14001af5e  lea     rcx, [rdi+38h]; SpinLock
0x14001af62  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x14001af67  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001af6e  nop     dword ptr [rax+rax+00h]
0x14001af73  test    esi, esi
0x14001af75  js      loc_14001B043
0x14001af7b  mov     eax, [rdi+8]
0x14001af7e  mov     r14d, 44h ; 'D'
0x14001af84  bts     eax, 19h
0x14001af88  mov     byte ptr [rdi+2], 4
0x14001af8c  mov     [rdi+8], eax
0x14001af8f  movzx   ebx, r14w
0x14001af93  mov     r8d, esi
0x14001af96  mov     edx, ebx
0x14001af98  mov     rcx, rdi
0x14001af9b  call    AfdIndicateEventSelectEvent
0x14001afa0  xor     r8d, r8d
0x14001afa3  movzx   edx, r14w
0x14001afa7  mov     rcx, rdi
0x14001afaa  call    AfdNotifySockEventsChangedUnderLock
0x14001afaf  mov     r8d, esi
0x14001afb2  lea     r9, [rsp+98h+LockHandle]
0x14001afb7  mov     edx, ebx
0x14001afb9  call    AfdIndicatePollEvent
0x14001afbe  test    al, al
0x14001afc0  jnz     loc_14001B04E
0x14001afc6  xor     eax, eax
0x14001afc8  xor     bl, bl
0x14001afca  xorps   xmm0, xmm0
0x14001afcd  mov     [rsp+98h+var_40], rax
0x14001afd2  movups  [rsp+98h+var_50], xmm0
0x14001afd7  cmp     [rdi+180h], rax
0x14001afde  jnz     loc_14001B080
0x14001afe4  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x14001afe9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001aff0  nop     dword ptr [rax+rax+00h]
0x14001aff5  test    bl, bl
0x14001aff7  jnz     loc_14001B0B2
0x14001affd  xor     eax, eax
0x14001afff  mov     rcx, r15; Object
0x14001b002  xchg    eax, [rdi+170h]
0x14001b008  call    cs:__imp_ObfDereferenceObject
0x14001b00f  nop     dword ptr [rax+rax+00h]
0x14001b014  mov     rcx, rbp
0x14001b017  call    AfdTLCompleteRequest
0x14001b01c  test    al, al
0x14001b01e  jz      short loc_14001B035
0x14001b020  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14001b026  mov     rcx, rbp; Irp
0x14001b029  call    cs:__imp_IofCompleteRequest
0x14001b030  nop     dword ptr [rax+rax+00h]
0x14001b035  add     rsp, 68h
0x14001b039  pop     r15
0x14001b03b  pop     r14
0x14001b03d  pop     rdi
0x14001b03e  pop     rsi
0x14001b03f  pop     rbp
0x14001b040  pop     rbx
0x14001b041  retn
0x14001b043  mov     r14d, 100h
0x14001b049  jmp     loc_14001AF8F
0x14001b04e  xor     r8d, r8d
0x14001b051  xor     edx, edx
0x14001b053  mov     rcx, rdi
0x14001b056  call    AfdNotifySockIndicateEventsUnlock
0x14001b05b  jmp     short loc_14001AFFD
0x14001b05d  mov     edx, 17h
0x14001b062  mov     [rsp+98h+var_78], rdi
0x14001b067  mov     ecx, 407h
0x14001b06c  lea     r8, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids
0x14001b073  mov     r9d, esi
0x14001b076  call    WPP_SF_Dq
0x14001b07b  jmp     loc_14001AF3D
0x14001b080  lea     rcx, [rdi+188h]; RunRef
0x14001b087  call    cs:__imp_ExAcquireRundownProtection
0x14001b08e  nop     dword ptr [rax+rax+00h]
0x14001b093  test    al, al
0x14001b095  jz      loc_14001AFE4
0x14001b09b  xor     r8d, r8d
0x14001b09e  lea     rdx, [rsp+98h+LockHandle]
0x14001b0a3  mov     rcx, rdi
0x14001b0a6  mov     bl, 1
0x14001b0a8  call    AfdNotifyPostEvents
0x14001b0ad  jmp     loc_14001AFE4
0x14001b0b2  lea     rcx, [rdi+188h]; RunRef
0x14001b0b9  call    cs:__imp_ExReleaseRundownProtection
0x14001b0c0  nop     dword ptr [rax+rax+00h]
0x14001b0c5  jmp     loc_14001AFFD
```
