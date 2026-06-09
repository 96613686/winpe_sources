# AfdReceiveDatagram

- ea: `0x140008210`
- end: `0x1400086c5`
- name: `AfdReceiveDatagram`
- size: `1205`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001ef30`
- `0x140022470`

## callees

- `0x140008210`
- `0x1400086d0`
- `0x140008fb0`
- `0x140009920`
- `0x140012610`
- `0x1400137a0`
- `0x140013dc0`
- `0x14001b0d0`
- `0x14001b800`
- `0x14002b5b0`
- `0x140050be4`
- `0x14009304c`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140008618`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140008618`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000864a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000864a`
- `ntoskrnl!IofCompleteRequest` at `0x1400084a7`
- `ntoskrnl!IofCompleteRequest` at `0x140074f28`
- `ntoskrnl!IofCompleteRequest` at `0x1400084a7`
- `ntoskrnl!IofCompleteRequest` at `0x140074f28`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008349`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008472`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400085b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140074e6a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008349`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008472`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400085b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140074e6a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400082b1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400082b1`

## pseudocode

```c
__int64 __fastcall AfdReceiveDatagram(PIRP Irp, __int64 a2)
{
  __int64 v3; // rax
  __int64 v5; // rbx
  NTSTATUS v6; // r14d
  __int64 v7; // rcx
  int v8; // eax
  int v9; // r14d
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rcx
  struct _LIST_ENTRY *v11; // rax
  struct _LIST_ENTRY *Blink; // rdx
  __int64 v14; // r12
  char *v15; // r9
  __int64 v16; // r15
  int v17; // eax
  char *v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // ecx
  __int64 *v21; // rcx
  __int64 v22; // rdx
  char v23; // r12
  unsigned int v24; // ebx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-9h] BYREF
  __int128 v30; // [rsp+78h] [rbp+Fh]
  __int64 v31; // [rsp+88h] [rbp+1Fh]
  __int64 v32; // [rsp+D8h] [rbp+6Fh] BYREF
  int v33; // [rsp+E0h] [rbp+77h]

  *(_QWORD *)&LockHandle.OldIrql = 0;
  Irp->IoStatus.Information = 0;
  v3 = *(_QWORD *)(a2 + 48);
  LockHandle.LockQueue = 0;
  v33 = 0;
  v5 = *(_QWORD *)(v3 + 24);
  LODWORD(v32) = 0;
  if ( (*(_BYTE *)(v5 + 7) & 0x10) != 0 )
  {
    v6 = -1073741816;
    v27 = 4165;
LABEL_40:
    AFDETW_TRACERECVDATAGRAM(0, v27, v5, 0, 0, Irp->MdlAddress, 0, v6, 0, Irp, 0, 1);
LABEL_55:
    Irp->IoStatus.Status = v6;
    IofCompleteRequest(Irp, 0);
    return (unsigned int)v6;
  }
  if ( *(_WORD *)v5 != 0xAFD1 )
  {
    v6 = -1073741811;
    AFDETW_TRACERECVDATAGRAM(0, 4024, v5, 0, 0, Irp->MdlAddress, 0, -1073741811, 0, Irp, 0, 1);
    goto LABEL_55;
  }
  if ( (*(_DWORD *)(v5 + 8) & 0x20000) != 0 )
  {
    v6 = -1073741648;
    v27 = 4025;
    goto LABEL_40;
  }
  if ( (unsigned __int8)(*(_BYTE *)(v5 + 2) - 3) > 1u )
  {
    v6 = -1073741811;
    AFDETW_TRACERECVDATAGRAM(0, 4026, v5, 0, 0, Irp->MdlAddress, 0, -1073741811, 0, Irp, 0, 1);
    goto LABEL_55;
  }
  v6 = AfdReceiveDatagramProbeAndLockPages(Irp, (__int64)&v32);
  if ( v6 < 0 )
  {
LABEL_50:
    AfdReceiveDatagramUnlockPages(Irp, a2);
    goto LABEL_55;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
  v8 = *(_DWORD *)(v5 + 8);
  if ( (v8 & 0x800) != 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v28 = 4050;
LABEL_52:
    v6 = -1073741536;
    AFDETW_TRACERECVDATAGRAM(
      1,
      v28,
      v5,
      0,
      v32,
      Irp->MdlAddress,
      *((_DWORD *)&Irp->Tail.CompletionKey + 6),
      -1073741536,
      0,
      Irp,
      0,
      1);
    goto LABEL_50;
  }
  v9 = v33 & 0x80;
  if ( !*(_DWORD *)(v5 + 148) )
  {
    if ( (v8 & 0x10) != 0 )
    {
      AfdNotifySockEventsChangedUnderLock(v5, 0, 1);
      *(_DWORD *)(v5 + 72) &= ~1u;
      if ( (xmmword_1400875E0 & 0x20) != 0 )
        WPP_SF_qD(1029, 11, WPP_d0bb78fec14f3c9b0066aa8d66ffb774_Traceguids, v5, *(_DWORD *)(v5 + 72));
      AfdNotifySockIndicateEventsUnlock(v5, &LockHandle, 0);
      v6 = -1073741661;
      AFDETW_TRACERECVDATAGRAM(
        1,
        4053,
        v5,
        0,
        v32,
        Irp->MdlAddress,
        *((_DWORD *)&Irp->Tail.CompletionKey + 6),
        -1073741661,
        0,
        Irp,
        0,
        1);
      goto LABEL_50;
    }
    p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&Irp->Tail.Overlay.ListEntry;
    v11 = (struct _LIST_ENTRY *)(v5 + 112);
    if ( (v33 & 0x80) == 0 )
      v11 = (struct _LIST_ENTRY *)(v5 + 96);
    Blink = v11->Blink;
    if ( Blink->Flink == v11 )
    {
      p_ListEntry->ListEntry.Flink = v11;
      Irp->Tail.Overlay.ListEntry.Blink = Blink;
      Blink->Flink = &p_ListEntry->ListEntry;
      v11->Blink = &p_ListEntry->ListEntry;
      _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdCancelReceiveDatagram);
      if ( !Irp->Cancel )
      {
LABEL_13:
        Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        return 259;
      }
      Flink = p_ListEntry->ListEntry.Flink;
      if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)p_ListEntry->ListEntry.Flink->Blink == p_ListEntry )
      {
        v26 = Irp->Tail.Overlay.ListEntry.Blink;
        if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)v26->Flink == p_ListEntry )
        {
          v26->Flink = Flink;
          Flink->Blink = v26;
          if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
          {
            p_ListEntry->ListEntry.Flink = 0;
            goto LABEL_13;
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          v28 = 4054;
          goto LABEL_52;
        }
      }
    }
LABEL_33:
    __fastfail(3u);
  }
  v14 = v5 + 128;
  v15 = 0;
  v16 = *(_QWORD *)(v5 + 128);
  v17 = *(_DWORD *)(v16 + 48);
  if ( v17 < 0 )
  {
    v18 = 0;
    Irp->IoStatus.Status = v17;
    LODWORD(v19) = 0;
    Irp->IoStatus.Information = 0;
    v20 = 0;
    LOWORD(v17) = 0;
  }
  else
  {
    AFDETW_TRACEBUFFER(v7, (__int64)Irp, *(_QWORD *)(v16 + 56), 0);
    v18 = *(char **)(v16 + 112);
    v19 = *(unsigned int *)(v16 + 64);
    v20 = *(_DWORD *)(v16 + 68);
    v17 = *(_DWORD *)(v16 + 16);
    v15 = &v18[v19];
  }
  LODWORD(v32) = AfdSetupReceiveDatagramIrp(
                   Irp,
                   v18,
                   v19,
                   v15,
                   v20,
                   *(unsigned __int16 **)(v16 + 40),
                   *(_DWORD *)(v16 + 32),
                   v17,
                   0,
                   0);
  if ( !v9 )
  {
    v21 = *(__int64 **)v14;
    if ( *(_QWORD *)(*(_QWORD *)v14 + 8LL) != v14 )
      goto LABEL_33;
    v22 = *v21;
    if ( *(__int64 **)(*v21 + 8) != v21 )
      goto LABEL_33;
    *(_QWORD *)v14 = v22;
    *(_QWORD *)(v22 + 8) = v14;
    --*(_DWORD *)(v5 + 148);
    *(_DWORD *)(v5 + 144) -= *(_DWORD *)(v16 + 64);
    *(_DWORD *)(v5 + 72) &= ~1u;
    if ( (xmmword_1400875E0 & 0x20) != 0 )
      WPP_SF_qD(1029, 10, WPP_d0bb78fec14f3c9b0066aa8d66ffb774_Traceguids, v5, *(_DWORD *)(v5 + 72));
    if ( *(_DWORD *)(v5 + 148) )
    {
      AfdIndicateEventSelectEvent(v5, 1, 0);
    }
    else
    {
      AfdNotifySockEventsChangedUnderLock(v5, 0, 1);
      if ( (*(_DWORD *)(v5 + 8) & 0x10) == 0 )
        *(_BYTE *)(v5 + 33) = 1;
    }
  }
  v23 = 0;
  v31 = 0;
  v30 = 0;
  if ( *(_QWORD *)(v5 + 384) && ExAcquireRundownProtection((PEX_RUNDOWN_REF)(v5 + 392)) )
  {
    v23 = 1;
    AfdNotifyPostEvents(v5, &LockHandle, 0);
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v23 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v5 + 392));
  if ( !v9 )
    AfdReturnBuffer((unsigned __int16 *)v16, *(PEPROCESS *)(v5 + 48));
  v24 = -2147483643;
  if ( (_DWORD)v32 != -2147483643 )
    v24 = v32;
  IofCompleteRequest(Irp, 0);
  return v24;
}

```

## disassembly

```asm
0x140008210  push    rbp
0x140008212  push    rbx
0x140008213  push    rdi
0x140008214  push    r12
0x140008216  push    r13
0x140008218  push    r14
0x14000821a  push    r15
0x14000821c  lea     rbp, [rsp-27h]
0x140008221  sub     rsp, 90h
0x140008228  xor     r13d, r13d
0x14000822b  xor     eax, eax
0x14000822d  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140008231  xorps   xmm0, xmm0
0x140008234  mov     [rcx+38h], r13
0x140008238  mov     r15, rdx
0x14000823b  mov     rax, [rdx+30h]
0x14000823f  mov     rdi, rcx
0x140008242  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140008246  mov     [rbp+57h+arg_10], r13d
0x14000824a  mov     [rbp+57h+arg_0], r13d
0x14000824e  mov     rbx, [rax+18h]
0x140008252  mov     dword ptr [rbp+57h+arg_8], r13d
0x140008256  test    byte ptr [rbx+7], 10h
0x14000825a  jnz     loc_140008507
0x140008260  mov     eax, 0AFD1h
0x140008265  cmp     [rbx], ax
0x140008268  jnz     loc_140008585
0x14000826e  mov     eax, [rbx+8]
0x140008271  bt      eax, 11h
0x140008275  jb      loc_140008514
0x14000827b  mov     al, [rbx+2]
0x14000827e  sub     al, 3
0x140008280  cmp     al, 1
0x140008282  ja      loc_14000853A
0x140008288  lea     rax, [rbp+57h+arg_8]
0x14000828c  lea     r9, [rbp+57h+arg_0]
0x140008290  mov     [rsp+0C0h+var_A0], rax; __int64
0x140008295  lea     r8, [rbp+57h+arg_10]
0x140008299  call    AfdReceiveDatagramProbeAndLockPages
0x14000829e  mov     r14d, eax
0x1400082a1  test    eax, eax
0x1400082a3  js      loc_1400086B4
0x1400082a9  lea     rcx, [rbx+38h]; SpinLock
0x1400082ad  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x1400082b1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400082b8  nop     dword ptr [rax+rax+00h]
0x1400082bd  mov     eax, [rbx+8]
0x1400082c0  bt      eax, 0Bh
0x1400082c4  jb      loc_1400085AC
0x1400082ca  mov     r14d, [rbp+57h+arg_10]
0x1400082ce  and     r14d, 80h
0x1400082d5  cmp     [rbx+94h], r13d
0x1400082dc  jnz     loc_140008374
0x1400082e2  mov     r12d, [rbp+57h+arg_0]
0x1400082e6  test    al, 10h
0x1400082e8  setnz   cl
0x1400082eb  test    r12b, 2
0x1400082ef  setz    al
0x1400082f2  test    al, cl
0x1400082f4  jnz     loc_14000868B
0x1400082fa  lea     rcx, [rdi+0A8h]
0x140008301  lea     rax, [rbx+70h]
0x140008305  test    r14d, r14d
0x140008308  jz      short loc_14000836E
0x14000830a  mov     rdx, [rax+8]
0x14000830e  cmp     [rdx], rax
0x140008311  jnz     loc_1400084CF
0x140008317  mov     [rcx], rax
0x14000831a  mov     [rcx+8], rdx
0x14000831e  mov     [rdx], rcx
0x140008321  mov     [rax+8], rcx
0x140008325  lea     rax, AfdCancelReceiveDatagram
0x14000832c  xchg    rax, [rdi+68h]
0x140008330  cmp     [rdi+44h], r13b
0x140008334  jnz     loc_1400084D6
0x14000833a  mov     rax, [rdi+0B8h]
0x140008341  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140008345  or      byte ptr [rax+3], 1
0x140008349  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140008350  nop     dword ptr [rax+rax+00h]
0x140008355  mov     eax, 103h
0x14000835a  add     rsp, 90h
0x140008361  pop     r15
0x140008363  pop     r14
0x140008365  pop     r13
0x140008367  pop     r12
0x140008369  pop     rdi
0x14000836a  pop     rbx
0x14000836b  pop     rbp
0x14000836c  retn
0x14000836e  lea     rax, [rbx+60h]
0x140008372  jmp     short loc_14000830A
0x140008374  lea     r12, [rbx+80h]
0x14000837b  xor     r9d, r9d
0x14000837e  mov     r15, [r12]
0x140008382  mov     eax, [r15+30h]
0x140008386  test    eax, eax
0x140008388  js      loc_1400084BA
0x14000838e  mov     r8, [r15+38h]
0x140008392  mov     rdx, rdi
0x140008395  call    AFDETW_TRACEBUFFER
0x14000839a  mov     rdx, [r15+70h]; SourceBuffer
0x14000839e  mov     r8d, [r15+40h]; SourceBytesToCopy
0x1400083a2  mov     ecx, [r15+44h]
0x1400083a6  mov     eax, [r15+10h]
0x1400083aa  lea     r9, [rdx+r8]
0x1400083ae  mov     [rsp+0C0h+var_78], r13d; int
0x1400083b3  mov     [rsp+0C0h+var_80], r13b; char
0x1400083b8  mov     [rsp+0C0h+var_88], eax; int
0x1400083bc  mov     eax, [r15+20h]
0x1400083c0  mov     [rsp+0C0h+var_90], eax; int
0x1400083c4  mov     rax, [r15+28h]
0x1400083c8  mov     [rsp+0C0h+Src], rax; Src
0x1400083cd  mov     dword ptr [rsp+0C0h+var_A0], ecx; int
0x1400083d1  mov     rcx, rdi; Irp
0x1400083d4  call    AfdSetupReceiveDatagramIrp
0x1400083d9  mov     dword ptr [rbp+57h+arg_8], eax
0x1400083dc  test    r14d, r14d
0x1400083df  jnz     short loc_140008451
0x1400083e1  mov     rcx, [r12]
0x1400083e5  cmp     [rcx+8], r12
0x1400083e9  jnz     loc_1400084CF
0x1400083ef  mov     rdx, [rcx]
0x1400083f2  cmp     [rdx+8], rcx
0x1400083f6  jnz     loc_1400084CF
0x1400083fc  mov     [r12], rdx
0x140008400  mov     [rdx+8], r12
0x140008404  dec     dword ptr [rbx+94h]
0x14000840a  mov     eax, [r15+40h]
0x14000840e  sub     [rbx+90h], eax
0x140008414  mov     eax, [rbx+48h]
0x140008417  and     eax, 0FFFFFFFEh
0x14000841a  mov     [rbx+48h], eax
0x14000841d  test    byte ptr cs:xmmword_1400875E0, 20h
0x140008424  jnz     loc_1400085D2
0x14000842a  mov     rcx, rbx
0x14000842d  cmp     [rbx+94h], r13d
0x140008434  jnz     loc_1400085F7
0x14000843a  xor     edx, edx
0x14000843c  lea     r8d, [rdx+1]
0x140008440  call    AfdNotifySockEventsChangedUnderLock
0x140008445  mov     ecx, [rbx+8]
0x140008448  test    cl, 10h
0x14000844b  jz      loc_140008608
0x140008451  xor     eax, eax
0x140008453  xor     r12b, r12b
0x140008456  xorps   xmm0, xmm0
0x140008459  mov     [rbp+57h+var_38], rax
0x14000845d  movups  [rbp+57h+var_48], xmm0
0x140008461  cmp     [rbx+180h], rax
0x140008468  jnz     loc_140008611
0x14000846e  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140008472  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140008479  nop     dword ptr [rax+rax+00h]
0x14000847e  test    r12b, r12b
0x140008481  jnz     loc_140008643
0x140008487  test    r14d, r14d
0x14000848a  jz      loc_14000865B
0x140008490  mov     eax, dword ptr [rbp+57h+arg_8]
0x140008493  mov     ebx, 80000005h
0x140008498  cmp     eax, ebx
0x14000849a  jz      loc_14000866C
0x1400084a0  mov     ebx, eax
0x1400084a2  xor     edx, edx; PriorityBoost
0x1400084a4  mov     rcx, rdi; Irp
0x1400084a7  call    cs:__imp_IofCompleteRequest
0x1400084ae  nop     dword ptr [rax+rax+00h]
0x1400084b3  mov     eax, ebx
0x1400084b5  jmp     loc_14000835A
0x1400084ba  xor     edx, edx
0x1400084bc  mov     [rdi+30h], eax
0x1400084bf  xor     r8d, r8d
0x1400084c2  mov     [rdi+38h], r13
0x1400084c6  xor     ecx, ecx
0x1400084c8  xor     eax, eax
0x1400084ca  jmp     loc_1400083AE
0x1400084cf  mov     ecx, 3
0x1400084d4  int     29h; Win8: RtlFailFast(ecx)
0x1400084d6  mov     rax, [rcx]
0x1400084d9  cmp     [rax+8], rcx
0x1400084dd  jnz     short loc_1400084CF
0x1400084df  mov     rdx, [rcx+8]
0x1400084e3  cmp     [rdx], rcx
0x1400084e6  jnz     short loc_1400084CF
0x1400084e8  mov     [rdx], rax
0x1400084eb  mov     [rax+8], rdx
0x1400084ef  mov     rax, r13
0x1400084f2  xchg    rax, [rdi+68h]
0x1400084f6  test    rax, rax
0x1400084f9  jnz     loc_140074E66
0x1400084ff  mov     [rcx], r13
0x140008502  jmp     loc_14000833A
0x140008507  mov     r14d, 0C0000008h
0x14000850d  mov     edx, 1045h
0x140008512  jmp     short loc_14000851F
0x140008514  mov     r14d, 0C00000B0h
0x14000851a  mov     edx, 0FB9h
0x14000851f  mov     [rsp+0C0h+var_68], 1
0x140008524  mov     [rsp+0C0h+var_70], r13d
0x140008529  mov     qword ptr [rsp+0C0h+var_78], rdi
0x14000852e  mov     qword ptr [rsp+0C0h+var_80], r13
0x140008533  mov     [rsp+0C0h+var_88], r14d
0x140008538  jmp     short loc_14000855F
0x14000853a  mov     [rsp+0C0h+var_68], 1
0x14000853f  mov     eax, 0C000000Dh
0x140008544  mov     [rsp+0C0h+var_70], r13d
0x140008549  mov     r14d, eax
0x14000854c  mov     qword ptr [rsp+0C0h+var_78], rdi
0x140008551  mov     edx, 0FBAh
0x140008556  mov     qword ptr [rsp+0C0h+var_80], r13
0x14000855b  mov     [rsp+0C0h+var_88], eax
0x14000855f  mov     rax, [rcx+8]
0x140008563  mov     r8, rbx
0x140008566  mov     [rsp+0C0h+var_90], r13d
0x14000856b  xor     r9d, r9d
0x14000856e  mov     [rsp+0C0h+Src], rax
0x140008573  xor     ecx, ecx
0x140008575  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x14000857a  call    AFDETW_TRACERECVDATAGRAM
0x14000857f  nop
0x140008580  jmp     loc_140074F1F
0x140008585  mov     [rsp+0C0h+var_68], 1
0x14000858a  mov     eax, 0C000000Dh
0x14000858f  mov     [rsp+0C0h+var_70], r13d
0x140008594  mov     r14d, eax
0x140008597  mov     qword ptr [rsp+0C0h+var_78], rdi
0x14000859c  mov     edx, 0FB8h
0x1400085a1  mov     qword ptr [rsp+0C0h+var_80], r13
0x1400085a6  mov     [rsp+0C0h+var_88], eax
0x1400085aa  jmp     short loc_14000855F
0x1400085ac  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400085b0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400085b7  nop     dword ptr [rax+rax+00h]
0x1400085bc  mov     eax, [rbp+57h+arg_0]
0x1400085bf  mov     edx, 0FD2h
0x1400085c4  mov     [rsp+0C0h+var_68], 1
0x1400085c9  mov     [rsp+0C0h+var_70], eax
0x1400085cd  jmp     loc_140074E85
0x1400085d2  mov     eax, [rbx+48h]
0x1400085d5  lea     r8, WPP_d0bb78fec14f3c9b0066aa8d66ffb774_Traceguids
0x1400085dc  mov     edx, 0Ah
0x1400085e1  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1400085e5  mov     ecx, 405h
0x1400085ea  mov     r9, rbx
0x1400085ed  call    WPP_SF_qD
0x1400085f2  jmp     loc_14000842A
0x1400085f7  xor     r8d, r8d
0x1400085fa  lea     edx, [r8+1]
0x1400085fe  call    AfdIndicateEventSelectEvent
0x140008603  jmp     loc_140008451
0x140008608  mov     byte ptr [rbx+21h], 1
0x14000860c  jmp     loc_140008451
0x140008611  lea     rcx, [rbx+188h]; RunRef
0x140008618  call    cs:__imp_ExAcquireRundownProtection
0x14000861f  nop     dword ptr [rax+rax+00h]
0x140008624  test    al, al
0x140008626  jz      loc_14000846E
0x14000862c  xor     r8d, r8d
0x14000862f  lea     rdx, [rbp+57h+LockHandle]
0x140008633  mov     rcx, rbx
0x140008636  mov     r12b, 1
0x140008639  call    AfdNotifyPostEvents
0x14000863e  jmp     loc_14000846E
0x140008643  lea     rcx, [rbx+188h]; RunRef
0x14000864a  call    cs:__imp_ExReleaseRundownProtection
0x140008651  nop     dword ptr [rax+rax+00h]
0x140008656  jmp     loc_140008487
0x14000865b  mov     rdx, [rbx+30h]; Process
0x14000865f  mov     rcx, r15; Entry
0x140008662  call    AfdReturnBuffer
0x140008667  jmp     loc_140008490
0x14000866c  test    byte ptr [rbp+57h+arg_0], 2
0x140008670  jz      loc_1400084A2
0x140008676  mov     rax, [rdi+0B8h]
0x14000867d  mov     ebx, 103h
0x140008682  or      byte ptr [rax+3], 1
0x140008686  jmp     loc_1400084A2
0x14000868b  xor     edx, edx
0x14000868d  mov     rcx, rbx
0x140008690  lea     r8d, [rdx+1]
0x140008694  call    AfdNotifySockEventsChangedUnderLock
0x140008699  mov     eax, [rbx+48h]
0x14000869c  and     eax, 0FFFFFFFEh
0x14000869f  mov     [rbx+48h], eax
0x1400086a2  test    byte ptr cs:xmmword_1400875E0, 20h
0x1400086a9  jnz     loc_140074E9D
0x1400086af  jmp     loc_140074EBD
0x1400086b4  mov     rdx, r15
0x1400086b7  mov     rcx, rdi
0x1400086ba  call    AfdReceiveDatagramUnlockPages
0x1400086bf  nop
0x1400086c0  jmp     loc_140074F1F
0x140074e66  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140074e6a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140074e71  nop     dword ptr [rax+rax+00h]
0x140074e76  mov     [rsp+0C0h+var_68], 1
0x140074e7b  mov     edx, 0FD6h
0x140074e80  mov     [rsp+0C0h+var_70], r12d
0x140074e85  mov     qword ptr [rsp+0C0h+var_78], rdi
0x140074e8a  mov     ecx, 0C0000120h
  ... truncated ...
```
