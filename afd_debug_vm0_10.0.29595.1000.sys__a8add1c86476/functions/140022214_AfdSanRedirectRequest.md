# AfdSanRedirectRequest

- ea: `0x140022214`
- end: `0x140022468`
- name: `AfdSanRedirectRequest`
- size: `596`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001f120`
- `0x140020500`
- `0x140022470`

## callees

- `0x140022214`
- `0x14005ac10`
- `0x14005d83c`
- `0x14009327c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002240f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002240f`
- `ntoskrnl!IofCompleteRequest` at `0x1400223b9`
- `ntoskrnl!IofCompleteRequest` at `0x140022444`
- `ntoskrnl!IofCompleteRequest` at `0x1400223b9`
- `ntoskrnl!IofCompleteRequest` at `0x140022444`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400223ff`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400223ff`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022292`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022349`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400223df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022427`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022292`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022349`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400223df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022427`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002224f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002224f`

## pseudocode

```c
__int64 __fastcall AfdSanRedirectRequest(PIRP Irp, __int64 a2)
{
  __int64 v4; // rsi
  NTSTATUS v5; // ebx
  int v6; // eax
  int v7; // ecx
  __int64 v8; // r14
  char v9; // bp
  struct _LIST_ENTRY *v10; // rbx
  struct _LIST_ENTRY *v11; // r8
  int v12; // edi
  IRP *v13; // rax
  CCHAR v14; // dl
  CCHAR v16; // dl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF
  KIRQL Irql; // [rsp+70h] [rbp+8h] BYREF

  Irp->IoStatus.Information = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 56), &LockHandle);
  if ( *(_WORD *)v4 != 6909 || *(_BYTE *)(v4 + 2) != 4 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v5 = -1073741504;
    goto LABEL_29;
  }
  v5 = *(_DWORD *)(v4 + 156);
  if ( v5 == 259 || v5 == -1073741802 )
  {
    v9 = 0;
    v8 = 0;
    v10 = 0;
  }
  else
  {
    if ( v5 < 0 )
    {
LABEL_6:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_29:
      v16 = AfdPriorityBoost;
      Irp->IoStatus.Status = v5;
      IofCompleteRequest(Irp, v16);
      return (unsigned int)v5;
    }
    if ( *(_BYTE *)a2 == 3 )
    {
      v6 = 1;
    }
    else
    {
      if ( *(_BYTE *)a2 != 4 )
      {
        v5 = -1073741808;
        goto LABEL_6;
      }
      v6 = 2;
    }
    v7 = *(_DWORD *)(v4 + 148);
    v8 = *(unsigned int *)(a2 + 8);
    v9 = 1;
    v10 = (struct _LIST_ENTRY *)(unsigned int)(v6 + 8 * v7);
    *(_DWORD *)(v4 + 148) = v7 + 1;
  }
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v10;
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdSanCancelRequest);
  if ( Irp->Cancel || *(_BYTE *)(v4 + 161) )
  {
    Irp->Tail.Overlay.ListEntry.Flink = 0;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
    {
      Irql = 0;
      IoAcquireCancelSpinLock(&Irql);
      IoReleaseCancelSpinLock(Irql);
    }
    v5 = -1073741536;
    goto LABEL_29;
  }
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  v11 = *(struct _LIST_ENTRY **)(v4 + 136);
  if ( v11->Flink != (struct _LIST_ENTRY *)(v4 + 128) )
    __fastfail(3u);
  Irp->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)(v4 + 128);
  Irp->Tail.Overlay.ListEntry.Blink = v11;
  v11->Flink = &Irp->Tail.Overlay.ListEntry;
  *(_QWORD *)(v4 + 136) = &Irp->Tail.Overlay.ListEntry;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
    WPP_SF_qqq(1043, 32, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v4, Irp, v10, LockHandle.LockQueue.Next);
  if ( v9 )
  {
    v12 = AfdSanNotifyRequest(v4, v10, 0, v8);
    if ( v12 < 0 )
    {
      v13 = (IRP *)AfdSanDequeueRequest(v4, v10);
      if ( v13 )
      {
        v14 = AfdPriorityBoost;
        v13->IoStatus.Status = v12;
        IofCompleteRequest(v13, v14);
      }
    }
  }
  return 259;
}

```

## disassembly

```asm
0x140022214  mov     r11, rsp
0x140022217  mov     [r11+10h], rbx
0x14002221b  mov     [r11+18h], rbp
0x14002221f  push    rsi
0x140022220  push    rdi
0x140022221  push    r14
0x140022223  sub     rsp, 50h
0x140022227  xor     eax, eax
0x140022229  xorps   xmm0, xmm0
0x14002222c  mov     [rcx+38h], rax
0x140022230  mov     rbp, rdx
0x140022233  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140022238  mov     [r11-28h], rax
0x14002223c  mov     rdi, rcx
0x14002223f  mov     rax, [rdx+30h]
0x140022243  lea     rdx, [r11-38h]; LockHandle
0x140022247  mov     rsi, [rax+18h]
0x14002224b  lea     rcx, [rsi+38h]; SpinLock
0x14002224f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140022256  nop     dword ptr [rax+rax+00h]
0x14002225b  mov     eax, 1AFDh
0x140022260  cmp     [rsi], ax
0x140022263  jnz     loc_140022422
0x140022269  cmp     byte ptr [rsi+2], 4
0x14002226d  jnz     loc_140022422
0x140022273  mov     ebx, [rsi+9Ch]
0x140022279  cmp     ebx, 103h
0x14002227f  jz      short loc_1400222DF
0x140022281  cmp     ebx, 0C0000016h
0x140022287  jz      short loc_1400222DF
0x140022289  test    ebx, ebx
0x14002228b  jns     short loc_1400222A3
0x14002228d  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140022292  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140022299  nop     dword ptr [rax+rax+00h]
0x14002229e  jmp     loc_140022438
0x1400222a3  movzx   ecx, byte ptr [rbp+0]
0x1400222a7  sub     ecx, 3
0x1400222aa  jz      short loc_1400222BF
0x1400222ac  cmp     ecx, 1
0x1400222af  jz      short loc_1400222B8
0x1400222b1  mov     ebx, 0C0000010h
0x1400222b6  jmp     short loc_14002228D
0x1400222b8  mov     eax, 2
0x1400222bd  jmp     short loc_1400222C4
0x1400222bf  mov     eax, 1
0x1400222c4  mov     ecx, [rsi+94h]
0x1400222ca  mov     r14d, [rbp+8]
0x1400222ce  mov     bpl, 1
0x1400222d1  lea     ebx, [rax+rcx*8]
0x1400222d4  lea     eax, [rcx+1]
0x1400222d7  mov     [rsi+94h], eax
0x1400222dd  jmp     short loc_1400222E7
0x1400222df  xor     bpl, bpl
0x1400222e2  xor     r14d, r14d
0x1400222e5  xor     ebx, ebx
0x1400222e7  mov     [rdi+78h], rbx
0x1400222eb  lea     rax, AfdSanCancelRequest
0x1400222f2  xchg    rax, [rdi+68h]
0x1400222f6  cmp     byte ptr [rdi+44h], 0
0x1400222fa  jnz     loc_1400223CF
0x140022300  cmp     byte ptr [rsi+0A1h], 0
0x140022307  jnz     loc_1400223CF
0x14002230d  mov     rax, [rdi+0B8h]
0x140022314  lea     rdx, [rsi+80h]
0x14002231b  or      byte ptr [rax+3], 1
0x14002231f  mov     r8, [rdx+8]
0x140022323  cmp     [r8], rdx
0x140022326  jz      short loc_14002232F
0x140022328  mov     ecx, 3
0x14002232d  int     29h; Win8: RtlFailFast(ecx)
0x14002232f  lea     rax, [rdi+0A8h]
0x140022336  mov     [rax], rdx
0x140022339  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14002233e  mov     [rax+8], r8
0x140022342  mov     [r8], rax
0x140022345  mov     [rdx+8], rax
0x140022349  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140022350  nop     dword ptr [rax+rax+00h]
0x140022355  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14002235c  jz      short loc_140022381
0x14002235e  mov     edx, 20h ; ' '
0x140022363  mov     [rsp+68h+var_40], rbx
0x140022368  mov     ecx, 413h
0x14002236d  mov     [rsp+68h+var_48], rdi
0x140022372  mov     r9, rsi
0x140022375  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14002237c  call    WPP_SF_qqq
0x140022381  test    bpl, bpl
0x140022384  jz      short loc_1400223C5
0x140022386  mov     r9, r14
0x140022389  xor     r8d, r8d
0x14002238c  mov     rdx, rbx
0x14002238f  mov     rcx, rsi
0x140022392  call    AfdSanNotifyRequest
0x140022397  mov     edi, eax
0x140022399  test    eax, eax
0x14002239b  jns     short loc_1400223C5
0x14002239d  mov     rdx, rbx
0x1400223a0  mov     rcx, rsi
0x1400223a3  call    AfdSanDequeueRequest
0x1400223a8  test    rax, rax
0x1400223ab  jz      short loc_1400223C5
0x1400223ad  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x1400223b3  mov     rcx, rax; Irp
0x1400223b6  mov     [rax+30h], edi
0x1400223b9  call    cs:__imp_IofCompleteRequest
0x1400223c0  nop     dword ptr [rax+rax+00h]
0x1400223c5  mov     eax, 103h
0x1400223ca  jmp     loc_140022452
0x1400223cf  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x1400223d4  mov     qword ptr [rdi+0A8h], 0
0x1400223df  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400223e6  nop     dword ptr [rax+rax+00h]
0x1400223eb  xor     eax, eax
0x1400223ed  xchg    rax, [rdi+68h]
0x1400223f1  test    rax, rax
0x1400223f4  jnz     short loc_14002241B
0x1400223f6  lea     rcx, [rsp+68h+Irql]; Irql
0x1400223fb  mov     [rsp+68h+Irql], al
0x1400223ff  call    cs:__imp_IoAcquireCancelSpinLock
0x140022406  nop     dword ptr [rax+rax+00h]
0x14002240b  mov     cl, [rsp+68h+Irql]; Irql
0x14002240f  call    cs:__imp_IoReleaseCancelSpinLock
0x140022416  nop     dword ptr [rax+rax+00h]
0x14002241b  mov     ebx, 0C0000120h
0x140022420  jmp     short loc_140022438
0x140022422  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140022427  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002242e  nop     dword ptr [rax+rax+00h]
0x140022433  mov     ebx, 0C0000140h
0x140022438  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14002243e  mov     rcx, rdi; Irp
0x140022441  mov     [rdi+30h], ebx
0x140022444  call    cs:__imp_IofCompleteRequest
0x14002244b  nop     dword ptr [rax+rax+00h]
0x140022450  mov     eax, ebx
0x140022452  lea     r11, [rsp+68h+var_18]
0x140022457  mov     rbx, [r11+28h]
0x14002245b  mov     rbp, [r11+30h]
0x14002245f  mov     rsp, r11
0x140022462  pop     r14
0x140022464  pop     rdi
0x140022465  pop     rsi
0x140022466  retn
```
