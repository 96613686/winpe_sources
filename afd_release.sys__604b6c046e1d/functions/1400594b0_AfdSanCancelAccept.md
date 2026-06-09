# AfdSanCancelAccept

- ea: `0x1400594b0`
- end: `0x1400596ec`
- name: `AfdSanCancelAccept`
- size: `572`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000f390`
- `0x1400594b0`
- `0x140072b00`
- `0x140093008`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005959d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400596c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005959d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400596c3`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400595ac`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400595f2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400596d2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400595ac`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400595f2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400596d2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400594e7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400594e7`
- `ntoskrnl!IofCompleteRequest` at `0x140059616`
- `ntoskrnl!IofCompleteRequest` at `0x1400596a9`
- `ntoskrnl!IofCompleteRequest` at `0x140059616`
- `ntoskrnl!IofCompleteRequest` at `0x1400596a9`
- `ntoskrnl!ObfDereferenceObject` at `0x140059685`
- `ntoskrnl!ObfDereferenceObject` at `0x140059685`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400595df`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400595df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005966e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005966e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140059630`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140059630`

## pseudocode

```c
void __fastcall AfdSanCancelAccept(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _QWORD *p_NamedPipeType; // r15
  __int64 v5; // rdi
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rax
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rdx
  _QWORD *v9; // rbp
  _QWORD **v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  _QWORD *v13; // rbx
  CCHAR v14; // dl
  CCHAR v15; // dl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-58h] BYREF
  KIRQL Irql; // [rsp+98h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(&LockHandle, 0, sizeof(LockHandle));
  p_NamedPipeType = &CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
  v5 = p_NamedPipeType[3];
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v5 + 56), &LockHandle);
  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( Flink )
  {
    if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Flink->Blink != p_ListEntry
      || (Blink = a2->Tail.Overlay.ListEntry.Blink,
          (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry) )
    {
LABEL_20:
      __fastfail(3u);
    }
    Blink->Flink = Flink;
    v9 = 0;
    Flink->Blink = Blink;
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_qq(1043, 53, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v5, a2);
    if ( (*(_DWORD *)(v5 + 8) & 0x800) == 0 )
    {
      *(_BYTE *)(v5 + 161) = 1;
      v10 = (_QWORD **)(v5 + 128);
      while ( 1 )
      {
        v11 = *v10;
        if ( *v10 == v10 )
          break;
        if ( (_QWORD **)v11[1] != v10 )
          goto LABEL_20;
        v12 = (_QWORD *)*v11;
        if ( *(_QWORD **)(*v11 + 8LL) != v11 )
          goto LABEL_20;
        *v10 = v12;
        v12[1] = v10;
        v11[1] = v9;
        v9 = v11;
        *v11 = 0;
      }
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    IoReleaseCancelSpinLock(a2->CancelIrql);
    while ( v9 )
    {
      v13 = v9 - 21;
      v9 = (_QWORD *)v9[1];
      if ( !_InterlockedExchange64(v13 + 13, 0) )
      {
        Irql = 0;
        IoAcquireCancelSpinLock(&Irql);
        IoReleaseCancelSpinLock(Irql);
      }
      v14 = AfdPriorityBoost;
      *((_DWORD *)v13 + 12) = -1073741536;
      v13[7] = 0;
      IofCompleteRequest((PIRP)v13, v14);
    }
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
    if ( (*(_DWORD *)(v5 + 8) & 0x800) == 0 )
    {
      AfdDereferenceEndpoint(*(_QWORD *)(v5 + 96));
      memset((void *)(v5 + 96), 0, 0x48u);
      *(_WORD *)v5 = -20528;
      *(_BYTE *)(v5 + 2) = 1;
      *(_DWORD *)(v5 + 8) = 0;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    _InterlockedExchange((volatile __int32 *)(v5 + 368), 0);
    ObfDereferenceObject(p_NamedPipeType);
    v15 = AfdPriorityBoost;
    a2->IoStatus.Status = -1073741536;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, v15);
  }
  else
  {
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    IoReleaseCancelSpinLock(a2->CancelIrql);
  }
}

```

## disassembly

```asm
0x1400594b0  push    rbx
0x1400594b2  push    rbp
0x1400594b3  push    rsi
0x1400594b4  push    rdi
0x1400594b5  push    r14
0x1400594b7  push    r15
0x1400594b9  sub     rsp, 58h
0x1400594bd  xor     eax, eax
0x1400594bf  xorps   xmm0, xmm0
0x1400594c2  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x1400594c7  mov     rsi, rdx
0x1400594ca  mov     rax, [rdx+0B8h]
0x1400594d1  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x1400594d6  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x1400594db  mov     r15, [rax+20h]
0x1400594df  mov     rdi, [r15+18h]
0x1400594e3  lea     rcx, [rdi+38h]; SpinLock
0x1400594e7  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400594ee  nop     dword ptr [rax+rax+00h]
0x1400594f3  lea     rax, [rsi+0A8h]
0x1400594fa  mov     rcx, [rax]
0x1400594fd  test    rcx, rcx
0x140059500  jz      loc_1400596BE
0x140059506  cmp     [rcx+8], rax
0x14005950a  jnz     loc_1400596B7
0x140059510  mov     rdx, [rax+8]
0x140059514  cmp     [rdx], rax
0x140059517  jnz     loc_1400596B7
0x14005951d  mov     [rdx], rcx
0x140059520  xor     ebp, ebp
0x140059522  mov     [rcx+8], rdx
0x140059526  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005952d  jz      short loc_14005954B
0x14005952f  lea     edx, [rbp+35h]
0x140059532  mov     [rsp+88h+var_68], rsi
0x140059537  mov     ecx, 413h
0x14005953c  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140059543  mov     r9, rdi
0x140059546  call    WPP_SF_qq
0x14005954b  test    dword ptr [rdi+8], 800h
0x140059552  jnz     short loc_140059598
0x140059554  mov     byte ptr [rdi+0A1h], 1
0x14005955b  lea     rcx, [rdi+80h]
0x140059562  mov     rax, [rcx]
0x140059565  cmp     rax, rcx
0x140059568  jz      short loc_140059598
0x14005956a  cmp     [rax+8], rcx
0x14005956e  jnz     loc_1400596B7
0x140059574  mov     rdx, [rax]
0x140059577  cmp     [rdx+8], rax
0x14005957b  jnz     loc_1400596B7
0x140059581  mov     [rcx], rdx
0x140059584  mov     [rdx+8], rcx
0x140059588  mov     [rax+8], rbp
0x14005958c  mov     rbp, rax
0x14005958f  mov     qword ptr [rax], 0
0x140059596  jmp     short loc_140059562
0x140059598  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14005959d  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400595a4  nop     dword ptr [rax+rax+00h]
0x1400595a9  mov     cl, [rsi+45h]; Irql
0x1400595ac  call    cs:__imp_IoReleaseCancelSpinLock
0x1400595b3  nop     dword ptr [rax+rax+00h]
0x1400595b8  jmp     short loc_140059622
0x1400595ba  lea     rbx, [rbp-0A8h]
0x1400595c1  xor     eax, eax
0x1400595c3  mov     rbp, [rbp+8]
0x1400595c7  xchg    rax, [rbx+68h]
0x1400595cb  test    rax, rax
0x1400595ce  jnz     short loc_1400595FE
0x1400595d0  lea     rcx, [rsp+88h+Irql]; Irql
0x1400595d8  mov     [rsp+88h+Irql], al
0x1400595df  call    cs:__imp_IoAcquireCancelSpinLock
0x1400595e6  nop     dword ptr [rax+rax+00h]
0x1400595eb  mov     cl, [rsp+88h+Irql]; Irql
0x1400595f2  call    cs:__imp_IoReleaseCancelSpinLock
0x1400595f9  nop     dword ptr [rax+rax+00h]
0x1400595fe  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140059604  mov     rcx, rbx; Irp
0x140059607  mov     dword ptr [rbx+30h], 0C0000120h
0x14005960e  mov     qword ptr [rbx+38h], 0
0x140059616  call    cs:__imp_IofCompleteRequest
0x14005961d  nop     dword ptr [rax+rax+00h]
0x140059622  test    rbp, rbp
0x140059625  jnz     short loc_1400595BA
0x140059627  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14005962c  lea     rcx, [rdi+38h]; SpinLock
0x140059630  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140059637  nop     dword ptr [rax+rax+00h]
0x14005963c  test    dword ptr [rdi+8], 800h
0x140059643  jnz     short loc_140059669
0x140059645  mov     rcx, [rdi+60h]
0x140059649  call    AfdDereferenceEndpoint
0x14005964e  xor     edx, edx; Val
0x140059650  lea     r8d, [rbp+48h]; Size
0x140059654  lea     rcx, [rdi+60h]; void *
0x140059658  call    memset
0x14005965d  mov     word ptr [rdi], 0AFD0h
0x140059662  mov     byte ptr [rdi+2], 1
0x140059666  mov     [rdi+8], ebp
0x140059669  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14005966e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140059675  nop     dword ptr [rax+rax+00h]
0x14005967a  xor     eax, eax
0x14005967c  mov     rcx, r15; Object
0x14005967f  xchg    eax, [rdi+170h]
0x140059685  call    cs:__imp_ObfDereferenceObject
0x14005968c  nop     dword ptr [rax+rax+00h]
0x140059691  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140059697  mov     rcx, rsi; Irp
0x14005969a  mov     dword ptr [rsi+30h], 0C0000120h
0x1400596a1  mov     qword ptr [rsi+38h], 0
0x1400596a9  call    cs:__imp_IofCompleteRequest
0x1400596b0  nop     dword ptr [rax+rax+00h]
0x1400596b5  jmp     short loc_1400596DE
0x1400596b7  mov     ecx, 3
0x1400596bc  int     29h; Win8: RtlFailFast(ecx)
0x1400596be  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x1400596c3  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400596ca  nop     dword ptr [rax+rax+00h]
0x1400596cf  mov     cl, [rsi+45h]; Irql
0x1400596d2  call    cs:__imp_IoReleaseCancelSpinLock
0x1400596d9  nop     dword ptr [rax+rax+00h]
0x1400596de  add     rsp, 58h
0x1400596e2  pop     r15
0x1400596e4  pop     r14
0x1400596e6  pop     rdi
0x1400596e7  pop     rsi
0x1400596e8  pop     rbp
0x1400596e9  pop     rbx
0x1400596ea  retn
```
