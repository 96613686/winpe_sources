# AfdSanCancelAccept

- ea: `0x140059650`
- end: `0x14005988c`
- name: `AfdSanCancelAccept`
- size: `572`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000f390`
- `0x140059650`
- `0x140072c80`
- `0x140093008`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005973d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140059863`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005973d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140059863`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005974c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140059792`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140059872`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005974c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140059792`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140059872`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140059687`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140059687`
- `ntoskrnl!IofCompleteRequest` at `0x1400597b6`
- `ntoskrnl!IofCompleteRequest` at `0x140059849`
- `ntoskrnl!IofCompleteRequest` at `0x1400597b6`
- `ntoskrnl!IofCompleteRequest` at `0x140059849`
- `ntoskrnl!ObfDereferenceObject` at `0x140059825`
- `ntoskrnl!ObfDereferenceObject` at `0x140059825`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005977f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005977f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005980e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005980e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400597d0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400597d0`

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
0x140059650  push    rbx
0x140059652  push    rbp
0x140059653  push    rsi
0x140059654  push    rdi
0x140059655  push    r14
0x140059657  push    r15
0x140059659  sub     rsp, 58h
0x14005965d  xor     eax, eax
0x14005965f  xorps   xmm0, xmm0
0x140059662  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x140059667  mov     rsi, rdx
0x14005966a  mov     rax, [rdx+0B8h]
0x140059671  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x140059676  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14005967b  mov     r15, [rax+20h]
0x14005967f  mov     rdi, [r15+18h]
0x140059683  lea     rcx, [rdi+38h]; SpinLock
0x140059687  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005968e  nop     dword ptr [rax+rax+00h]
0x140059693  lea     rax, [rsi+0A8h]
0x14005969a  mov     rcx, [rax]
0x14005969d  test    rcx, rcx
0x1400596a0  jz      loc_14005985E
0x1400596a6  cmp     [rcx+8], rax
0x1400596aa  jnz     loc_140059857
0x1400596b0  mov     rdx, [rax+8]
0x1400596b4  cmp     [rdx], rax
0x1400596b7  jnz     loc_140059857
0x1400596bd  mov     [rdx], rcx
0x1400596c0  xor     ebp, ebp
0x1400596c2  mov     [rcx+8], rdx
0x1400596c6  test    byte ptr cs:xmmword_1400875E0+2, 8
0x1400596cd  jz      short loc_1400596EB
0x1400596cf  lea     edx, [rbp+35h]
0x1400596d2  mov     [rsp+88h+var_68], rsi
0x1400596d7  mov     ecx, 413h
0x1400596dc  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x1400596e3  mov     r9, rdi
0x1400596e6  call    WPP_SF_qq
0x1400596eb  test    dword ptr [rdi+8], 800h
0x1400596f2  jnz     short loc_140059738
0x1400596f4  mov     byte ptr [rdi+0A1h], 1
0x1400596fb  lea     rcx, [rdi+80h]
0x140059702  mov     rax, [rcx]
0x140059705  cmp     rax, rcx
0x140059708  jz      short loc_140059738
0x14005970a  cmp     [rax+8], rcx
0x14005970e  jnz     loc_140059857
0x140059714  mov     rdx, [rax]
0x140059717  cmp     [rdx+8], rax
0x14005971b  jnz     loc_140059857
0x140059721  mov     [rcx], rdx
0x140059724  mov     [rdx+8], rcx
0x140059728  mov     [rax+8], rbp
0x14005972c  mov     rbp, rax
0x14005972f  mov     qword ptr [rax], 0
0x140059736  jmp     short loc_140059702
0x140059738  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14005973d  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140059744  nop     dword ptr [rax+rax+00h]
0x140059749  mov     cl, [rsi+45h]; Irql
0x14005974c  call    cs:__imp_IoReleaseCancelSpinLock
0x140059753  nop     dword ptr [rax+rax+00h]
0x140059758  jmp     short loc_1400597C2
0x14005975a  lea     rbx, [rbp-0A8h]
0x140059761  xor     eax, eax
0x140059763  mov     rbp, [rbp+8]
0x140059767  xchg    rax, [rbx+68h]
0x14005976b  test    rax, rax
0x14005976e  jnz     short loc_14005979E
0x140059770  lea     rcx, [rsp+88h+Irql]; Irql
0x140059778  mov     [rsp+88h+Irql], al
0x14005977f  call    cs:__imp_IoAcquireCancelSpinLock
0x140059786  nop     dword ptr [rax+rax+00h]
0x14005978b  mov     cl, [rsp+88h+Irql]; Irql
0x140059792  call    cs:__imp_IoReleaseCancelSpinLock
0x140059799  nop     dword ptr [rax+rax+00h]
0x14005979e  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x1400597a4  mov     rcx, rbx; Irp
0x1400597a7  mov     dword ptr [rbx+30h], 0C0000120h
0x1400597ae  mov     qword ptr [rbx+38h], 0
0x1400597b6  call    cs:__imp_IofCompleteRequest
0x1400597bd  nop     dword ptr [rax+rax+00h]
0x1400597c2  test    rbp, rbp
0x1400597c5  jnz     short loc_14005975A
0x1400597c7  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x1400597cc  lea     rcx, [rdi+38h]; SpinLock
0x1400597d0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400597d7  nop     dword ptr [rax+rax+00h]
0x1400597dc  test    dword ptr [rdi+8], 800h
0x1400597e3  jnz     short loc_140059809
0x1400597e5  mov     rcx, [rdi+60h]
0x1400597e9  call    AfdDereferenceEndpoint
0x1400597ee  xor     edx, edx; Val
0x1400597f0  lea     r8d, [rbp+48h]; Size
0x1400597f4  lea     rcx, [rdi+60h]; void *
0x1400597f8  call    memset
0x1400597fd  mov     word ptr [rdi], 0AFD0h
0x140059802  mov     byte ptr [rdi+2], 1
0x140059806  mov     [rdi+8], ebp
0x140059809  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14005980e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140059815  nop     dword ptr [rax+rax+00h]
0x14005981a  xor     eax, eax
0x14005981c  mov     rcx, r15; Object
0x14005981f  xchg    eax, [rdi+170h]
0x140059825  call    cs:__imp_ObfDereferenceObject
0x14005982c  nop     dword ptr [rax+rax+00h]
0x140059831  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140059837  mov     rcx, rsi; Irp
0x14005983a  mov     dword ptr [rsi+30h], 0C0000120h
0x140059841  mov     qword ptr [rsi+38h], 0
0x140059849  call    cs:__imp_IofCompleteRequest
0x140059850  nop     dword ptr [rax+rax+00h]
0x140059855  jmp     short loc_14005987E
0x140059857  mov     ecx, 3
0x14005985c  int     29h; Win8: RtlFailFast(ecx)
0x14005985e  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x140059863  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005986a  nop     dword ptr [rax+rax+00h]
0x14005986f  mov     cl, [rsi+45h]; Irql
0x140059872  call    cs:__imp_IoReleaseCancelSpinLock
0x140059879  nop     dword ptr [rax+rax+00h]
0x14005987e  add     rsp, 58h
0x140059882  pop     r15
0x140059884  pop     r14
0x140059886  pop     rdi
0x140059887  pop     rsi
0x140059888  pop     rbp
0x140059889  pop     rbx
0x14005988a  retn
```
