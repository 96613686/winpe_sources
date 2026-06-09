# AfdWaitForListen

- ea: `0x14002f800`
- end: `0x14002fb0a`
- name: `AfdWaitForListen`
- size: `778`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001ef30`
- `0x14002e9c0`

## callees

- `0x1400049b0`
- `0x140004c10`
- `0x14002f800`
- `0x14002fd40`
- `0x140036dcc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002f8d4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002fabd`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002f8d4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002fabd`
- `ntoskrnl!IofCompleteRequest` at `0x14002faec`
- `ntoskrnl!IofCompleteRequest` at `0x14002faec`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002f8c5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002faae`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002f8c5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002faae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f86c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f919`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f98c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa34`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa94`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f86c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f919`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f98c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa34`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa94`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f854`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f854`

## pseudocode

```c
__int64 __fastcall AfdWaitForListen(PIRP Irp, __int64 a2)
{
  bool v2; // zf
  __int64 v5; // rax
  __int64 v6; // r14
  unsigned int v7; // r15d
  __int64 v8; // rdx
  __int64 Status; // r9
  __int64 v10; // rcx
  __int64 UnacceptedConnection; // rax
  __int64 v12; // r13
  struct _LIST_ENTRY *v13; // r14
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v15; // r14
  struct _LIST_ENTRY *Blink; // rcx
  __int64 result; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  CCHAR v20; // dl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF
  KIRQL Irql; // [rsp+88h] [rbp+40h] BYREF

  v2 = *(_BYTE *)a2 == 15;
  v5 = *(_QWORD *)(a2 + 48);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v6 = *(_QWORD *)(v5 + 24);
  if ( !v2 && *(_DWORD *)(a2 + 8) < 0xCu )
  {
    v7 = -1073741811;
    v8 = 6217;
    Status = 3221225485LL;
    v10 = 0;
LABEL_34:
    AFDETW_TRACEWAITLISTEN(v10, v8, v6, Status);
    goto LABEL_35;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 56), &LockHandle);
  if ( (*(_DWORD *)(v6 + 8) & 1) == 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v7 = -1073741811;
    AFDETW_TRACEWAITLISTEN(0, 6218, v6, 3221225485LL);
    if ( *(_BYTE *)a2 != 15 || *(_BYTE *)(a2 + 1) != 32 )
      goto LABEL_35;
    goto LABEL_7;
  }
  AFDETW_TRACEWAITLISTEN(0, 6216, v6, 0);
  UnacceptedConnection = AfdGetUnacceptedConnection(v6);
  v12 = UnacceptedConnection;
  if ( UnacceptedConnection )
  {
    result = AfdServiceWaitForListen(Irp, UnacceptedConnection, &LockHandle, 0);
    v7 = result;
    if ( (int)result >= 0 )
      return result;
    v18 = (_QWORD *)(v6 + 96);
    v19 = *(_QWORD *)(v6 + 96);
    if ( *(_QWORD *)(v19 + 8) == v6 + 96 )
    {
      *(_QWORD *)(v12 + 184) = v18;
      *(_QWORD *)(v12 + 176) = v19;
      *(_QWORD *)(v19 + 8) = v12 + 176;
      *v18 = v12 + 176;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( Irp->Cancel )
      {
        Irql = 0;
        IoAcquireCancelSpinLock(&Irql);
        IoReleaseCancelSpinLock(Irql);
      }
      Status = (unsigned int)Irp->IoStatus.Status;
      v8 = 6223;
      v10 = 1;
      goto LABEL_34;
    }
    goto LABEL_30;
  }
  if ( (*(_DWORD *)(v6 + 8) & 0x800) != 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v7 = -1073741536;
    AFDETW_TRACEWAITLISTEN(1, 6205, v6, 3221225760LL);
    if ( *(_BYTE *)a2 != 15 )
      goto LABEL_35;
    if ( *(_BYTE *)(a2 + 1) != 32 )
      goto LABEL_35;
    AfdCleanupSuperAccept(Irp, 3221225760LL);
    if ( !Irp->Cancel )
      goto LABEL_35;
    goto LABEL_9;
  }
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdCancelWaitForListen);
  if ( !Irp->Cancel )
  {
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    if ( *(_BYTE *)a2 == 15 && *(_BYTE *)(a2 + 1) == 32 || *(_DWORD *)(a2 + 24) == 73872 )
    {
      v13 = (struct _LIST_ENTRY *)(v6 + 128);
      Flink = v13->Flink;
      if ( v13->Flink->Blink == v13 )
      {
        Irp->Tail.Overlay.ListEntry.Flink = Flink;
        Irp->Tail.Overlay.ListEntry.Blink = v13;
        Flink->Blink = &Irp->Tail.Overlay.ListEntry;
        v13->Flink = &Irp->Tail.Overlay.ListEntry;
LABEL_27:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        return 259;
      }
    }
    else
    {
      v15 = (struct _LIST_ENTRY *)(v6 + 128);
      Blink = v15->Blink;
      if ( Blink->Flink == v15 )
      {
        Irp->Tail.Overlay.ListEntry.Flink = v15;
        Irp->Tail.Overlay.ListEntry.Blink = Blink;
        Blink->Flink = &Irp->Tail.Overlay.ListEntry;
        v15->Blink = &Irp->Tail.Overlay.ListEntry;
        goto LABEL_27;
      }
    }
LABEL_30:
    __fastfail(3u);
  }
  Irp->Tail.Overlay.ListEntry.Flink = 0;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v7 = -1073741536;
  AFDETW_TRACEWAITLISTEN(1, 6206, v6, 3221225760LL);
  if ( *(_BYTE *)a2 == 15 && *(_BYTE *)(a2 + 1) == 32 )
LABEL_7:
    AfdCleanupSuperAccept(Irp, v7);
  if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
  {
LABEL_9:
    Irql = 0;
    IoAcquireCancelSpinLock(&Irql);
    IoReleaseCancelSpinLock(Irql);
  }
LABEL_35:
  v20 = AfdPriorityBoost;
  Irp->IoStatus.Status = v7;
  IofCompleteRequest(Irp, v20);
  return v7;
}

```

## disassembly

```asm
0x14002f800  push    rbp
0x14002f802  push    rbx
0x14002f803  push    rsi
0x14002f804  push    r13
0x14002f806  push    r14
0x14002f808  push    r15
0x14002f80a  mov     rbp, rsp
0x14002f80d  sub     rsp, 48h
0x14002f811  xor     eax, eax
0x14002f813  xorps   xmm0, xmm0
0x14002f816  cmp     byte ptr [rdx], 0Fh
0x14002f819  mov     rsi, rdx
0x14002f81c  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14002f820  mov     rbx, rcx
0x14002f823  mov     rax, [rdx+30h]
0x14002f827  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14002f82b  mov     r14, [rax+18h]
0x14002f82f  jz      short loc_14002F84C
0x14002f831  cmp     dword ptr [rdx+8], 0Ch
0x14002f835  jnb     short loc_14002F84C
0x14002f837  mov     r15d, 0C000000Dh
0x14002f83d  mov     edx, 1849h
0x14002f842  mov     r9d, r15d
0x14002f845  xor     ecx, ecx
0x14002f847  jmp     loc_14002FAD7
0x14002f84c  lea     rcx, [r14+38h]; SpinLock
0x14002f850  lea     rdx, [rbp+LockHandle]; LockHandle
0x14002f854  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002f85b  nop     dword ptr [rax+rax+00h]
0x14002f860  mov     eax, [r14+8]
0x14002f864  test    al, 1
0x14002f866  jnz     short loc_14002F8E5
0x14002f868  lea     rcx, [rbp+LockHandle]; LockHandle
0x14002f86c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002f873  nop     dword ptr [rax+rax+00h]
0x14002f878  mov     r15d, 0C000000Dh
0x14002f87e  mov     r8, r14
0x14002f881  mov     r9d, r15d
0x14002f884  mov     edx, 184Ah
0x14002f889  xor     ecx, ecx
0x14002f88b  call    AFDETW_TRACEWAITLISTEN
0x14002f890  cmp     byte ptr [rsi], 0Fh
0x14002f893  jnz     loc_14002FADF
0x14002f899  cmp     byte ptr [rsi+1], 20h ; ' '
0x14002f89d  jnz     loc_14002FADF
0x14002f8a3  mov     edx, r15d
0x14002f8a6  mov     rcx, rbx
0x14002f8a9  call    AfdCleanupSuperAccept
0x14002f8ae  xor     eax, eax
0x14002f8b0  xchg    rax, [rbx+68h]
0x14002f8b4  test    rax, rax
0x14002f8b7  jnz     loc_14002FADF
0x14002f8bd  lea     rcx, [rbp+Irql]; Irql
0x14002f8c1  mov     [rbp+Irql], 0
0x14002f8c5  call    cs:__imp_IoAcquireCancelSpinLock
0x14002f8cc  nop     dword ptr [rax+rax+00h]
0x14002f8d1  mov     cl, [rbp+Irql]; Irql
0x14002f8d4  call    cs:__imp_IoReleaseCancelSpinLock
0x14002f8db  nop     dword ptr [rax+rax+00h]
0x14002f8e0  jmp     loc_14002FADF
0x14002f8e5  xor     r9d, r9d
0x14002f8e8  mov     r8, r14
0x14002f8eb  mov     edx, 1848h
0x14002f8f0  xor     ecx, ecx
0x14002f8f2  call    AFDETW_TRACEWAITLISTEN
0x14002f8f7  mov     rcx, r14
0x14002f8fa  call    AfdGetUnacceptedConnection
0x14002f8ff  mov     r13, rax
0x14002f902  test    rax, rax
0x14002f905  jnz     loc_14002FA4A
0x14002f90b  test    dword ptr [r14+8], 800h
0x14002f913  jz      short loc_14002F96C
0x14002f915  lea     rcx, [rbp+LockHandle]; LockHandle
0x14002f919  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002f920  nop     dword ptr [rax+rax+00h]
0x14002f925  mov     r15d, 0C0000120h
0x14002f92b  lea     ecx, [r13+1]
0x14002f92f  mov     r9d, r15d
0x14002f932  mov     r8, r14
0x14002f935  mov     edx, 183Dh
0x14002f93a  call    AFDETW_TRACEWAITLISTEN
0x14002f93f  cmp     byte ptr [rsi], 0Fh
0x14002f942  jnz     loc_14002FADF
0x14002f948  cmp     byte ptr [rsi+1], 20h ; ' '
0x14002f94c  jnz     loc_14002FADF
0x14002f952  mov     edx, r15d
0x14002f955  mov     rcx, rbx
0x14002f958  call    AfdCleanupSuperAccept
0x14002f95d  cmp     [rbx+44h], r13b
0x14002f961  jz      loc_14002FADF
0x14002f967  jmp     loc_14002F8BD
0x14002f96c  lea     rax, AfdCancelWaitForListen
0x14002f973  xchg    rax, [rbx+68h]
0x14002f977  cmp     byte ptr [rbx+44h], 0
0x14002f97b  jz      short loc_14002F9CB
0x14002f97d  lea     rcx, [rbp+LockHandle]; LockHandle
0x14002f981  mov     qword ptr [rbx+0A8h], 0
0x14002f98c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002f993  nop     dword ptr [rax+rax+00h]
0x14002f998  mov     r15d, 0C0000120h
0x14002f99e  mov     r8, r14
0x14002f9a1  mov     r9d, r15d
0x14002f9a4  mov     edx, 183Eh
0x14002f9a9  mov     ecx, 1
0x14002f9ae  call    AFDETW_TRACEWAITLISTEN
0x14002f9b3  cmp     byte ptr [rsi], 0Fh
0x14002f9b6  jnz     loc_14002F8AE
0x14002f9bc  cmp     byte ptr [rsi+1], 20h ; ' '
0x14002f9c0  jnz     loc_14002F8AE
0x14002f9c6  jmp     loc_14002F8A3
0x14002f9cb  mov     rax, [rbx+0B8h]
0x14002f9d2  or      byte ptr [rax+3], 1
0x14002f9d6  cmp     byte ptr [rsi], 0Fh
0x14002f9d9  jnz     short loc_14002F9E1
0x14002f9db  cmp     byte ptr [rsi+1], 20h ; ' '
0x14002f9df  jz      short loc_14002F9EA
0x14002f9e1  cmp     dword ptr [rsi+18h], 12090h
0x14002f9e8  jnz     short loc_14002FA0E
0x14002f9ea  sub     r14, 0FFFFFFFFFFFFFF80h
0x14002f9ee  mov     rcx, [r14]
0x14002f9f1  cmp     [rcx+8], r14
0x14002f9f5  jnz     short loc_14002FA74
0x14002f9f7  lea     rax, [rbx+0A8h]
0x14002f9fe  mov     [rax], rcx
0x14002fa01  mov     [rax+8], r14
0x14002fa05  mov     [rcx+8], rax
0x14002fa09  mov     [r14], rax
0x14002fa0c  jmp     short loc_14002FA30
0x14002fa0e  sub     r14, 0FFFFFFFFFFFFFF80h
0x14002fa12  mov     rcx, [r14+8]
0x14002fa16  cmp     [rcx], r14
0x14002fa19  jnz     short loc_14002FA74
0x14002fa1b  lea     rax, [rbx+0A8h]
0x14002fa22  mov     [rax], r14
0x14002fa25  mov     [rax+8], rcx
0x14002fa29  mov     [rcx], rax
0x14002fa2c  mov     [r14+8], rax
0x14002fa30  lea     rcx, [rbp+LockHandle]; LockHandle
0x14002fa34  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002fa3b  nop     dword ptr [rax+rax+00h]
0x14002fa40  mov     eax, 103h
0x14002fa45  jmp     loc_14002FAFB
0x14002fa4a  xor     r9d, r9d
0x14002fa4d  lea     r8, [rbp+LockHandle]
0x14002fa51  mov     rdx, r13
0x14002fa54  mov     rcx, rbx; Irp
0x14002fa57  call    AfdServiceWaitForListen
0x14002fa5c  mov     r15d, eax
0x14002fa5f  test    eax, eax
0x14002fa61  jns     loc_14002FAFB
0x14002fa67  lea     rcx, [r14+60h]
0x14002fa6b  mov     rdx, [rcx]
0x14002fa6e  cmp     [rdx+8], rcx
0x14002fa72  jz      short loc_14002FA7B
0x14002fa74  mov     ecx, 3
0x14002fa79  int     29h; Win8: RtlFailFast(ecx)
0x14002fa7b  lea     rax, [r13+0B0h]
0x14002fa82  mov     [rax+8], rcx
0x14002fa86  mov     [rax], rdx
0x14002fa89  mov     [rdx+8], rax
0x14002fa8d  mov     [rcx], rax
0x14002fa90  lea     rcx, [rbp+LockHandle]; LockHandle
0x14002fa94  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002fa9b  nop     dword ptr [rax+rax+00h]
0x14002faa0  cmp     byte ptr [rbx+44h], 0
0x14002faa4  jz      short loc_14002FAC9
0x14002faa6  lea     rcx, [rbp+Irql]; Irql
0x14002faaa  mov     [rbp+Irql], 0
0x14002faae  call    cs:__imp_IoAcquireCancelSpinLock
0x14002fab5  nop     dword ptr [rax+rax+00h]
0x14002faba  mov     cl, [rbp+Irql]; Irql
0x14002fabd  call    cs:__imp_IoReleaseCancelSpinLock
0x14002fac4  nop     dword ptr [rax+rax+00h]
0x14002fac9  mov     r9d, [rbx+30h]
0x14002facd  mov     edx, 184Fh
0x14002fad2  mov     ecx, 1
0x14002fad7  mov     r8, r14
0x14002fada  call    AFDETW_TRACEWAITLISTEN
0x14002fadf  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14002fae5  mov     rcx, rbx; Irp
0x14002fae8  mov     [rbx+30h], r15d
0x14002faec  call    cs:__imp_IofCompleteRequest
0x14002faf3  nop     dword ptr [rax+rax+00h]
0x14002faf8  mov     eax, r15d
0x14002fafb  add     rsp, 48h
0x14002faff  pop     r15
0x14002fb01  pop     r14
0x14002fb03  pop     r13
0x14002fb05  pop     rsi
0x14002fb06  pop     rbx
0x14002fb07  pop     rbp
0x14002fb08  retn
```
