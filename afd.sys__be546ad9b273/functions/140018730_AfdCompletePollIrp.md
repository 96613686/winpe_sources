# AfdCompletePollIrp

- ea: `0x140018730`
- end: `0x1400189e4`
- name: `AfdCompletePollIrp`
- size: `692`
- prototype: `void __fastcall(PIRP Irp, char)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000f450`
- `0x140016710`
- `0x140017390`
- `0x1400189f0`

## callees

- `0x140018730`
- `0x140018b20`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14001886c`
- `ntoskrnl!KeCancelTimer` at `0x14001886c`
- `ntoskrnl!KeInsertQueueApc` at `0x140018963`
- `ntoskrnl!KeInsertQueueApc` at `0x140018963`
- `ntoskrnl!KeInitializeApc` at `0x140018945`
- `ntoskrnl!KeInitializeApc` at `0x140018945`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400188aa`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400188aa`
- `ntoskrnl!IofCompleteRequest` at `0x140018848`
- `ntoskrnl!IofCompleteRequest` at `0x140018848`
- `ntoskrnl!ObfDereferenceObject` at `0x1400187d8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400188c2`
- `ntoskrnl!ObfDereferenceObject` at `0x14001897b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400189d3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400187d8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400188c2`
- `ntoskrnl!ObfDereferenceObject` at `0x14001897b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400189d3`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140018899`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140018899`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018832`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018832`

## pseudocode

```c
void __fastcall AfdCompletePollIrp(PIRP Irp, char a2)
{
  PVOID v4; // rcx
  struct _LIST_ENTRY *Flink; // rbx
  PVOID *p_Blink; // rdi
  unsigned int i; // esi
  int Flink_high; // eax
  KIRQL Irql; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
  {
    do
      v4 = Irp->Tail.Overlay.DriverContext[2];
    while ( v4 != (PVOID)_InterlockedCompareExchange64(
                           (volatile signed __int64 *)&Irp->Tail.Overlay.DriverContext[2],
                           (signed __int64)v4 + 1,
                           (signed __int64)v4) );
    if ( !v4 )
      return;
    if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
    {
      Irql = 0;
      IoAcquireCancelSpinLock(&Irql);
      IoReleaseCancelSpinLock(Irql);
    }
  }
  Flink = Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  if ( LODWORD(Flink[10].Flink) && KeCancelTimer((PKTIMER)&Flink[6]) )
  {
    _InterlockedDecrement((volatile signed __int32 *)Flink);
    LODWORD(Flink[10].Flink) = 0;
  }
  if ( BYTE1(Flink[11].Flink) && (a2 && Irp->CancelIrql > 1u || Irp->Tail.Overlay.Thread != KeGetCurrentThread()) )
  {
    KeInitializeApc(
      &Flink[2],
      Irp->Tail.Overlay.Thread,
      (unsigned int)Irp->ApcEnvironment,
      AfdSanPollApcKernelRoutine,
      AfdSanPollApcRundownRoutine,
      -1,
      0,
      0);
    if ( (unsigned __int8)KeInsertQueueApc(&Flink[2], Flink, Irp, (unsigned int)AfdPriorityBoost) )
      return;
    ObfDereferenceObject(Flink->Blink);
    BYTE1(Flink[11].Flink) = 0;
  }
  if ( !BYTE2(Flink[11].Flink) )
  {
    if ( (BYTE1(xmmword_1400875E0) & 0x40) != 0 )
      WPP_SF_q(1038, 19, WPP_800cc04c3f0a310f2669f157ebd45fd5_Traceguids, Flink);
    p_Blink = (PVOID *)&Flink[11].Blink;
    for ( i = 0; i < LODWORD(Flink[1].Blink); ++i )
    {
      ObfDereferenceObject(p_Blink[2]);
      p_Blink[2] = 0;
      p_Blink += 5;
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Flink, 0xFFFFFFFF) == 1 )
  {
    if ( (BYTE1(xmmword_1400875E0) & 0x40) != 0 )
      WPP_SF_q(1038, 20, WPP_800cc04c3f0a310f2669f157ebd45fd5_Traceguids, Flink);
    if ( BYTE1(Flink[11].Flink) )
      ObfDereferenceObject(Flink->Blink);
    if ( BYTE2(Flink[11].Flink) )
    {
      ObfDereferenceObject(Flink[10].Blink);
      Flink_high = HIDWORD(Flink[10].Flink);
      Flink[10].Blink = 0;
      if ( !Flink_high )
        AfdCachedPollDerefFileObjects((__int64)Flink, 0);
    }
    ExFreePoolWithTag(Flink, 0x50646641u);
  }
  IofCompleteRequest(Irp, AfdPriorityBoost);
}

```

## disassembly

```asm
0x140018730  push    rbp
0x140018732  push    rdi
0x140018733  push    r15
0x140018735  sub     rsp, 40h
0x140018739  xor     r15d, r15d
0x14001873c  movzx   edi, dl
0x14001873f  mov     rbp, rcx
0x140018742  test    dl, dl
0x140018744  jnz     short loc_140018779
0x140018746  mov     rcx, [rbp+88h]
0x14001874d  mov     rax, rcx
0x140018750  lea     r8, [rcx+1]
0x140018754  lock cmpxchg [rbp+88h], r8
0x14001875d  jnz     short loc_140018746
0x14001875f  cmp     rcx, 1
0x140018763  jb      loc_14001885E
0x140018769  mov     rax, r15
0x14001876c  xchg    rax, [rbp+68h]
0x140018770  test    rax, rax
0x140018773  jz      loc_14001888F
0x140018779  mov     [rsp+58h+arg_0], rbx
0x14001877e  mov     rbx, [rbp+78h]
0x140018782  mov     [rsp+58h+arg_18], r14
0x140018787  mov     eax, [rbx+0A0h]
0x14001878d  test    eax, eax
0x14001878f  jnz     loc_140018868
0x140018795  mov     r14, 0FFFFFFFFFFFFFFFFh
0x14001879c  cmp     [rbx+0B1h], r15b
0x1400187a3  jnz     loc_1400188F2
0x1400187a9  cmp     [rbx+0B2h], r15b
0x1400187b0  jnz     short loc_1400187F8
0x1400187b2  mov     [rsp+58h+arg_10], rsi
0x1400187b7  test    byte ptr cs:xmmword_1400875E0+1, 40h
0x1400187be  jnz     loc_140018993
0x1400187c4  lea     rdi, [rbx+0B8h]
0x1400187cb  mov     esi, r15d
0x1400187ce  cmp     [rbx+18h], r15d
0x1400187d2  jbe     short loc_1400187F3
0x1400187d4  mov     rcx, [rdi+10h]; Object
0x1400187d8  call    cs:__imp_ObfDereferenceObject
0x1400187df  nop     dword ptr [rax+rax+00h]
0x1400187e4  mov     [rdi+10h], r15
0x1400187e8  lea     rdi, [rdi+28h]
0x1400187ec  inc     esi
0x1400187ee  cmp     esi, [rbx+18h]
0x1400187f1  jb      short loc_1400187D4
0x1400187f3  mov     rsi, [rsp+58h+arg_10]
0x1400187f8  lock xadd [rbx], r14d
0x1400187fd  cmp     r14d, 1
0x140018801  jnz     short loc_14001883E
0x140018803  test    byte ptr cs:xmmword_1400875E0+1, 40h
0x14001880a  jnz     loc_1400189B1
0x140018810  cmp     [rbx+0B1h], r15b
0x140018817  jnz     loc_1400189CF
0x14001881d  cmp     [rbx+0B2h], r15b
0x140018824  jnz     loc_1400188BB
0x14001882a  mov     edx, 50646641h; Tag
0x14001882f  mov     rcx, rbx; P
0x140018832  call    cs:__imp_ExFreePoolWithTag
0x140018839  nop     dword ptr [rax+rax+00h]
0x14001883e  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x140018845  mov     rcx, rbp; Irp
0x140018848  call    cs:__imp_IofCompleteRequest
0x14001884f  nop     dword ptr [rax+rax+00h]
0x140018854  mov     rbx, [rsp+58h+arg_0]
0x140018859  mov     r14, [rsp+58h+arg_18]
0x14001885e  add     rsp, 40h
0x140018862  pop     r15
0x140018864  pop     rdi
0x140018865  pop     rbp
0x140018866  retn
0x140018868  lea     rcx, [rbx+60h]; PKTIMER
0x14001886c  call    cs:__imp_KeCancelTimer
0x140018873  nop     dword ptr [rax+rax+00h]
0x140018878  test    al, al
0x14001887a  jz      loc_140018795
0x140018880  lock dec dword ptr [rbx]
0x140018883  mov     [rbx+0A0h], r15d
0x14001888a  jmp     loc_140018795
0x14001888f  lea     rcx, [rsp+58h+Irql]; Irql
0x140018894  mov     [rsp+58h+Irql], r15b
0x140018899  call    cs:__imp_IoAcquireCancelSpinLock
0x1400188a0  nop     dword ptr [rax+rax+00h]
0x1400188a5  movzx   ecx, [rsp+58h+Irql]; Irql
0x1400188aa  call    cs:__imp_IoReleaseCancelSpinLock
0x1400188b1  nop     dword ptr [rax+rax+00h]
0x1400188b6  jmp     loc_140018779
0x1400188bb  mov     rcx, [rbx+0A8h]; Object
0x1400188c2  call    cs:__imp_ObfDereferenceObject
0x1400188c9  nop     dword ptr [rax+rax+00h]
0x1400188ce  mov     eax, [rbx+0A4h]
0x1400188d4  mov     [rbx+0A8h], r15
0x1400188db  test    eax, eax
0x1400188dd  jnz     loc_14001882A
0x1400188e3  xor     edx, edx
0x1400188e5  mov     rcx, rbx
0x1400188e8  call    AfdCachedPollDerefFileObjects
0x1400188ed  jmp     loc_14001882A
0x1400188f2  test    dil, dil
0x1400188f5  jz      short loc_1400188FD
0x1400188f7  cmp     byte ptr [rbp+45h], 1
0x1400188fb  ja      short loc_140018913
0x1400188fd  mov     rax, gs:188h
0x140018906  cmp     [rbp+98h], rax
0x14001890d  jz      loc_1400187A9
0x140018913  movsx   r8d, byte ptr [rbp+46h]
0x140018918  lea     rax, AfdSanPollApcRundownRoutine
0x14001891f  mov     rdx, [rbp+98h]
0x140018926  lea     r9, AfdSanPollApcKernelRoutine
0x14001892d  mov     [rsp+58h+var_20], r15
0x140018932  lea     rcx, [rbx+20h]
0x140018936  mov     [rsp+58h+var_28], r15b
0x14001893b  mov     [rsp+58h+var_30], r14
0x140018940  mov     [rsp+58h+var_38], rax
0x140018945  call    cs:__imp_KeInitializeApc
0x14001894c  nop     dword ptr [rax+rax+00h]
0x140018951  movsx   r9d, cs:AfdPriorityBoost
0x140018959  lea     rcx, [rbx+20h]
0x14001895d  mov     r8, rbp
0x140018960  mov     rdx, rbx
0x140018963  call    cs:__imp_KeInsertQueueApc
0x14001896a  nop     dword ptr [rax+rax+00h]
0x14001896f  test    al, al
0x140018971  jnz     loc_140018854
0x140018977  mov     rcx, [rbx+8]; Object
0x14001897b  call    cs:__imp_ObfDereferenceObject
0x140018982  nop     dword ptr [rax+rax+00h]
0x140018987  mov     [rbx+0B1h], r15b
0x14001898e  jmp     loc_1400187A9
0x140018993  mov     edx, 13h
0x140018998  lea     r8, WPP_800cc04c3f0a310f2669f157ebd45fd5_Traceguids
0x14001899f  mov     ecx, 40Eh
0x1400189a4  mov     r9, rbx
0x1400189a7  call    WPP_SF_q
0x1400189ac  jmp     loc_1400187C4
0x1400189b1  mov     edx, 14h
0x1400189b6  lea     r8, WPP_800cc04c3f0a310f2669f157ebd45fd5_Traceguids
0x1400189bd  mov     ecx, 40Eh
0x1400189c2  mov     r9, rbx
0x1400189c5  call    WPP_SF_q
0x1400189ca  jmp     loc_140018810
0x1400189cf  mov     rcx, [rbx+8]; Object
0x1400189d3  call    cs:__imp_ObfDereferenceObject
0x1400189da  nop     dword ptr [rax+rax+00h]
0x1400189df  jmp     loc_14001881D
```
