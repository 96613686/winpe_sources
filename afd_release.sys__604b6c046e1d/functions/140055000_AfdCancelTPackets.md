# AfdCancelTPackets

- ea: `0x140055000`
- end: `0x1400552fe`
- name: `AfdCancelTPackets`
- size: `766`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14001dd20`
- `0x14002dc3c`
- `0x140042250`
- `0x140043698`
- `0x140043ed8`
- `0x140055000`
- `0x140055934`
- `0x140093008`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400550c4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400550d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140055157`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400551fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005528a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400552cd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400550c4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400550d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140055157`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400551fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005528a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400552cd`
- `ntoskrnl!KeLowerIrql` at `0x1400550e3`
- `ntoskrnl!KeLowerIrql` at `0x14005521c`
- `ntoskrnl!KeLowerIrql` at `0x1400552e0`
- `ntoskrnl!KeLowerIrql` at `0x1400550e3`
- `ntoskrnl!KeLowerIrql` at `0x14005521c`
- `ntoskrnl!KeLowerIrql` at `0x1400552e0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005508c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055194`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055298`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400552ab`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005508c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055194`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055298`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400552ab`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140055042`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005505d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140055042`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005505d`
- `ntoskrnl!IofCompleteRequest` at `0x14005525a`
- `ntoskrnl!IofCompleteRequest` at `0x14005525a`

## pseudocode

```c
void __fastcall AfdCancelTPackets(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v4; // rsi
  __int64 v5; // r14
  __int64 v6; // rbx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  KIRQL v9; // bl
  __int64 v10; // r14
  _QWORD *v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rsi
  char v14; // bl
  KIRQL v15; // cl
  CCHAR v16; // dl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE v18; // [rsp+48h] [rbp-20h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&v18, 0, sizeof(v18));
  v4 = *(_QWORD *)(*(_QWORD *)(v2 + 48) + 24LL);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 56), &LockHandle);
  v5 = *(_QWORD *)(a2 + 24);
  KeAcquireInStackQueuedSpinLockAtDpcLevel(&AfdQueuedTransmitFileSpinLock, &v18);
  if ( (*(_DWORD *)(a2 + 136) & 0x100) == 0 )
  {
    v6 = a2 + 168;
    if ( *(_QWORD *)(a2 + 168) )
    {
      IoReleaseCancelSpinLock(2u);
      v7 = *(_QWORD *)v6;
      if ( *(_QWORD *)(*(_QWORD *)v6 + 8LL) != v6 || (v8 = *(_QWORD **)(a2 + 176), *v8 != v6) )
        __fastfail(3u);
      *v8 = v7;
      *(_QWORD *)(v7 + 8) = v8;
      *(_QWORD *)v6 = 0;
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&v18);
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      KeLowerIrql(*(_BYTE *)(a2 + 69));
      AfdAbortTPackets(a2, -1073741536);
      if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
        WPP_SF_qq(1042, 50, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v5, a2);
LABEL_7:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 132), 0xFFFFFFFF) == 1 )
        AfdCompleteTPackets((PIRP)a2);
      return;
    }
  }
  v9 = *(_BYTE *)(a2 + 69);
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&v18);
  if ( (*(_DWORD *)(a2 + 136) & 0x20) != 0 || (unsigned __int8)AfdGetTPacketsReference(a2) )
  {
    IoReleaseCancelSpinLock(2u);
    if ( (*(_DWORD *)(a2 + 136) & 0x20) != 0 )
      _InterlockedAdd((volatile signed __int32 *)(a2 + 136), 0xFFFFFFE0);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    if ( v9 != 2 )
      KeLowerIrql(v9);
    AfdAbortTPackets(a2, -1073741536);
    goto LABEL_7;
  }
  if ( v5 == -1 )
  {
    v10 = *(_QWORD *)(a2 + 176);
    IoReleaseCancelSpinLock(2u);
    v11 = *(_QWORD **)(v4 + 360);
    if ( v11 == (_QWORD *)a2 )
    {
      *(_QWORD *)(v4 + 360) = 0;
    }
    else
    {
      if ( v11[15] - 120LL != a2 )
      {
        do
        {
          v12 = (_QWORD *)v11[15];
          v11 = v12 - 15;
        }
        while ( *v12 - 120LL != a2 );
      }
      v11[15] = 0;
    }
    *(_QWORD *)(a2 + 24) = 0;
    v13 = *(_QWORD *)(v2 + 32);
    v14 = AfdCheckAndReferenceConnection(v13);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    if ( v14 )
      AfdAbortConnection(v13);
    v15 = *(_BYTE *)(a2 + 69);
    if ( v15 != 2 )
      KeLowerIrql(v15);
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_q(1042, 51, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, a2);
    v16 = AfdPriorityBoost;
    *(_DWORD *)(a2 + 48) = -1073741536;
    IofCompleteRequest((PIRP)a2, v16);
    if ( AfdMaxActiveTransmitFileCount && !v10 )
      AfdStartNextQueuedTransmit();
  }
  else
  {
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    IoReleaseCancelSpinLock(v9);
  }
}

```

## disassembly

```asm
0x140055000  push    rbp
0x140055002  push    rbx
0x140055003  push    rsi
0x140055004  push    rdi
0x140055005  push    r14
0x140055007  push    r15
0x140055009  mov     rbp, rsp
0x14005500c  sub     rsp, 68h
0x140055010  mov     r15, [rdx+0B8h]
0x140055017  xor     eax, eax
0x140055019  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14005501d  xorps   xmm0, xmm0
0x140055020  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140055024  mov     qword ptr [rbp+var_20.OldIrql], rax
0x140055028  mov     rdi, rdx
0x14005502b  xorps   xmm1, xmm1
0x14005502e  lea     rdx, [rbp+LockHandle]; LockHandle
0x140055032  movups  xmmword ptr [rbp+var_20.LockQueue.Next], xmm1
0x140055036  mov     rax, [r15+30h]
0x14005503a  mov     rsi, [rax+18h]
0x14005503e  lea     rcx, [rsi+38h]; SpinLock
0x140055042  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140055049  nop     dword ptr [rax+rax+00h]
0x14005504e  mov     r14, [rdi+18h]
0x140055052  lea     rdx, [rbp+var_20]; LockHandle
0x140055056  lea     rcx, AfdQueuedTransmitFileSpinLock; SpinLock
0x14005505d  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140055064  nop     dword ptr [rax+rax+00h]
0x140055069  mov     eax, [rdi+88h]
0x14005506f  bt      eax, 8
0x140055073  jb      loc_140055150
0x140055079  lea     rbx, [rdi+0A8h]
0x140055080  cmp     qword ptr [rbx], 0
0x140055084  jz      loc_140055150
0x14005508a  mov     cl, 2; Irql
0x14005508c  call    cs:__imp_IoReleaseCancelSpinLock
0x140055093  nop     dword ptr [rax+rax+00h]
0x140055098  mov     rcx, [rbx]
0x14005509b  cmp     [rcx+8], rbx
0x14005509f  jnz     loc_140055149
0x1400550a5  mov     rax, [rbx+8]
0x1400550a9  cmp     [rax], rbx
0x1400550ac  jnz     loc_140055149
0x1400550b2  mov     [rax], rcx
0x1400550b5  mov     [rcx+8], rax
0x1400550b9  lea     rcx, [rbp+var_20]; LockHandle
0x1400550bd  mov     qword ptr [rbx], 0
0x1400550c4  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400550cb  nop     dword ptr [rax+rax+00h]
0x1400550d0  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400550d4  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400550db  nop     dword ptr [rax+rax+00h]
0x1400550e0  mov     cl, [rdi+45h]; NewIrql
0x1400550e3  call    cs:__imp_KeLowerIrql
0x1400550ea  nop     dword ptr [rax+rax+00h]
0x1400550ef  mov     edx, 0C0000120h
0x1400550f4  mov     rcx, rdi
0x1400550f7  call    AfdAbortTPackets
0x1400550fc  test    byte ptr cs:xmmword_1400875E0+2, 4
0x140055103  jz      short loc_140055123
0x140055105  mov     edx, 32h ; '2'
0x14005510a  mov     [rsp+68h+var_48], rdi
0x14005510f  mov     ecx, 412h
0x140055114  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x14005511b  mov     r9, r14
0x14005511e  call    WPP_SF_qq
0x140055123  or      eax, 0FFFFFFFFh
0x140055126  lock xadd [rdi+84h], eax
0x14005512e  cmp     eax, 1
0x140055131  jnz     short loc_14005513B
0x140055133  mov     rcx, rdi; Irp
0x140055136  call    AfdCompleteTPackets
0x14005513b  add     rsp, 68h
0x14005513f  pop     r15
0x140055141  pop     r14
0x140055143  pop     rdi
0x140055144  pop     rsi
0x140055145  pop     rbx
0x140055146  pop     rbp
0x140055147  retn
0x140055149  mov     ecx, 3
0x14005514e  int     29h; Win8: RtlFailFast(ecx)
0x140055150  mov     bl, [rdi+45h]
0x140055153  lea     rcx, [rbp+var_20]; LockHandle
0x140055157  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005515e  nop     dword ptr [rax+rax+00h]
0x140055163  mov     eax, [rdi+88h]
0x140055169  test    al, 20h
0x14005516b  jnz     loc_1400552A9
0x140055171  mov     rcx, rdi
0x140055174  call    AfdGetTPacketsReference
0x140055179  test    al, al
0x14005517b  jnz     loc_1400552A9
0x140055181  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140055185  jnz     loc_140055286
0x14005518b  mov     r14, [rdi+0B0h]
0x140055192  mov     cl, 2; Irql
0x140055194  call    cs:__imp_IoReleaseCancelSpinLock
0x14005519b  nop     dword ptr [rax+rax+00h]
0x1400551a0  mov     rdx, [rsi+168h]
0x1400551a7  cmp     rdx, rdi
0x1400551aa  jnz     short loc_1400551B9
0x1400551ac  mov     qword ptr [rsi+168h], 0
0x1400551b7  jmp     short loc_1400551E2
0x1400551b9  mov     rax, [rdx+78h]
0x1400551bd  sub     rax, 78h ; 'x'
0x1400551c1  cmp     rax, rdi
0x1400551c4  jz      short loc_1400551DA
0x1400551c6  mov     rax, [rdx+78h]
0x1400551ca  mov     rcx, [rax]
0x1400551cd  lea     rdx, [rax-78h]
0x1400551d1  sub     rcx, 78h ; 'x'
0x1400551d5  cmp     rcx, rdi
0x1400551d8  jnz     short loc_1400551C6
0x1400551da  mov     qword ptr [rdx+78h], 0
0x1400551e2  mov     qword ptr [rdi+18h], 0
0x1400551ea  mov     rsi, [r15+20h]
0x1400551ee  mov     rcx, rsi
0x1400551f1  call    AfdCheckAndReferenceConnection
0x1400551f6  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400551fa  mov     bl, al
0x1400551fc  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140055203  nop     dword ptr [rax+rax+00h]
0x140055208  test    bl, bl
0x14005520a  jz      short loc_140055214
0x14005520c  mov     rcx, rsi
0x14005520f  call    AfdAbortConnection
0x140055214  mov     cl, [rdi+45h]; NewIrql
0x140055217  cmp     cl, 2
0x14005521a  jz      short loc_140055228
0x14005521c  call    cs:__imp_KeLowerIrql
0x140055223  nop     dword ptr [rax+rax+00h]
0x140055228  test    byte ptr cs:xmmword_1400875E0+2, 4
0x14005522f  jz      short loc_14005524A
0x140055231  mov     edx, 33h ; '3'
0x140055236  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x14005523d  mov     ecx, 412h
0x140055242  mov     r9, rdi
0x140055245  call    WPP_SF_q
0x14005524a  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140055250  mov     rcx, rdi; Irp
0x140055253  mov     dword ptr [rdi+30h], 0C0000120h
0x14005525a  call    cs:__imp_IofCompleteRequest
0x140055261  nop     dword ptr [rax+rax+00h]
0x140055266  cmp     cs:AfdMaxActiveTransmitFileCount, 0
0x14005526d  jbe     loc_14005513B
0x140055273  test    r14, r14
0x140055276  jnz     loc_14005513B
0x14005527c  call    AfdStartNextQueuedTransmit
0x140055281  jmp     loc_14005513B
0x140055286  lea     rcx, [rbp+LockHandle]; LockHandle
0x14005528a  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140055291  nop     dword ptr [rax+rax+00h]
0x140055296  mov     cl, bl; Irql
0x140055298  call    cs:__imp_IoReleaseCancelSpinLock
0x14005529f  nop     dword ptr [rax+rax+00h]
0x1400552a4  jmp     loc_14005513B
0x1400552a9  mov     cl, 2; Irql
0x1400552ab  call    cs:__imp_IoReleaseCancelSpinLock
0x1400552b2  nop     dword ptr [rax+rax+00h]
0x1400552b7  mov     eax, [rdi+88h]
0x1400552bd  test    al, 20h
0x1400552bf  jz      short loc_1400552C9
0x1400552c1  lock add dword ptr [rdi+88h], 0FFFFFFE0h
0x1400552c9  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400552cd  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400552d4  nop     dword ptr [rax+rax+00h]
0x1400552d9  cmp     bl, 2
0x1400552dc  jz      short loc_1400552EC
0x1400552de  mov     cl, bl; NewIrql
0x1400552e0  call    cs:__imp_KeLowerIrql
0x1400552e7  nop     dword ptr [rax+rax+00h]
0x1400552ec  mov     edx, 0C0000120h
0x1400552f1  mov     rcx, rdi
0x1400552f4  call    AfdAbortTPackets
0x1400552f9  jmp     loc_140055123
```
