# AfdCancelTPackets

- ea: `0x1400550a0`
- end: `0x14005539e`
- name: `AfdCancelTPackets`
- size: `766`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14001dd20`
- `0x14002dc3c`
- `0x140042270`
- `0x1400436b8`
- `0x140043ef8`
- `0x1400550a0`
- `0x1400559d4`
- `0x140093008`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140055164`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140055174`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400551f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005529c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005532a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005536d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140055164`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140055174`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400551f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005529c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005532a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005536d`
- `ntoskrnl!KeLowerIrql` at `0x140055183`
- `ntoskrnl!KeLowerIrql` at `0x1400552bc`
- `ntoskrnl!KeLowerIrql` at `0x140055380`
- `ntoskrnl!KeLowerIrql` at `0x140055183`
- `ntoskrnl!KeLowerIrql` at `0x1400552bc`
- `ntoskrnl!KeLowerIrql` at `0x140055380`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005512c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055234`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055338`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005534b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005512c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055234`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055338`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005534b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400550e2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400550fd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400550e2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400550fd`
- `ntoskrnl!IofCompleteRequest` at `0x1400552fa`
- `ntoskrnl!IofCompleteRequest` at `0x1400552fa`

## pseudocode

```c
void __fastcall AfdCancelTPackets(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v4; // rsi
  __int64 v5; // r14
  __int64 *v6; // rbx
  __int64 *v7; // rcx
  __int64 **v8; // rax
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
    v6 = (__int64 *)(a2 + 168);
    if ( *(_QWORD *)(a2 + 168) )
    {
      IoReleaseCancelSpinLock(2u);
      v7 = (__int64 *)*v6;
      if ( *(__int64 **)(*v6 + 8) != v6 || (v8 = *(__int64 ***)(a2 + 176), *v8 != v6) )
        __fastfail(3u);
      *v8 = v7;
      v7[1] = (__int64)v8;
      *v6 = 0;
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&v18);
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      KeLowerIrql(*(_BYTE *)(a2 + 69));
      AfdAbortTPackets(a2, 3221225760LL);
      if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
        WPP_SF_qq(1042, 50, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v5, a2);
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
    AfdAbortTPackets(a2, 3221225760LL);
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
      WPP_SF_q(1042, 51, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, a2);
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
0x1400550a0  push    rbp
0x1400550a2  push    rbx
0x1400550a3  push    rsi
0x1400550a4  push    rdi
0x1400550a5  push    r14
0x1400550a7  push    r15
0x1400550a9  mov     rbp, rsp
0x1400550ac  sub     rsp, 68h
0x1400550b0  mov     r15, [rdx+0B8h]
0x1400550b7  xor     eax, eax
0x1400550b9  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400550bd  xorps   xmm0, xmm0
0x1400550c0  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400550c4  mov     qword ptr [rbp+var_20.OldIrql], rax
0x1400550c8  mov     rdi, rdx
0x1400550cb  xorps   xmm1, xmm1
0x1400550ce  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400550d2  movups  xmmword ptr [rbp+var_20.LockQueue.Next], xmm1
0x1400550d6  mov     rax, [r15+30h]
0x1400550da  mov     rsi, [rax+18h]
0x1400550de  lea     rcx, [rsi+38h]; SpinLock
0x1400550e2  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400550e9  nop     dword ptr [rax+rax+00h]
0x1400550ee  mov     r14, [rdi+18h]
0x1400550f2  lea     rdx, [rbp+var_20]; LockHandle
0x1400550f6  lea     rcx, AfdQueuedTransmitFileSpinLock; SpinLock
0x1400550fd  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140055104  nop     dword ptr [rax+rax+00h]
0x140055109  mov     eax, [rdi+88h]
0x14005510f  bt      eax, 8
0x140055113  jb      loc_1400551F0
0x140055119  lea     rbx, [rdi+0A8h]
0x140055120  cmp     qword ptr [rbx], 0
0x140055124  jz      loc_1400551F0
0x14005512a  mov     cl, 2; Irql
0x14005512c  call    cs:__imp_IoReleaseCancelSpinLock
0x140055133  nop     dword ptr [rax+rax+00h]
0x140055138  mov     rcx, [rbx]
0x14005513b  cmp     [rcx+8], rbx
0x14005513f  jnz     loc_1400551E9
0x140055145  mov     rax, [rbx+8]
0x140055149  cmp     [rax], rbx
0x14005514c  jnz     loc_1400551E9
0x140055152  mov     [rax], rcx
0x140055155  mov     [rcx+8], rax
0x140055159  lea     rcx, [rbp+var_20]; LockHandle
0x14005515d  mov     qword ptr [rbx], 0
0x140055164  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005516b  nop     dword ptr [rax+rax+00h]
0x140055170  lea     rcx, [rbp+LockHandle]; LockHandle
0x140055174  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005517b  nop     dword ptr [rax+rax+00h]
0x140055180  mov     cl, [rdi+45h]; NewIrql
0x140055183  call    cs:__imp_KeLowerIrql
0x14005518a  nop     dword ptr [rax+rax+00h]
0x14005518f  mov     edx, 0C0000120h
0x140055194  mov     rcx, rdi
0x140055197  call    AfdAbortTPackets
0x14005519c  test    byte ptr cs:xmmword_1400875E0+2, 4
0x1400551a3  jz      short loc_1400551C3
0x1400551a5  mov     edx, 32h ; '2'
0x1400551aa  mov     [rsp+68h+var_48], rdi
0x1400551af  mov     ecx, 412h
0x1400551b4  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x1400551bb  mov     r9, r14
0x1400551be  call    WPP_SF_qq
0x1400551c3  or      eax, 0FFFFFFFFh
0x1400551c6  lock xadd [rdi+84h], eax
0x1400551ce  cmp     eax, 1
0x1400551d1  jnz     short loc_1400551DB
0x1400551d3  mov     rcx, rdi; Irp
0x1400551d6  call    AfdCompleteTPackets
0x1400551db  add     rsp, 68h
0x1400551df  pop     r15
0x1400551e1  pop     r14
0x1400551e3  pop     rdi
0x1400551e4  pop     rsi
0x1400551e5  pop     rbx
0x1400551e6  pop     rbp
0x1400551e7  retn
0x1400551e9  mov     ecx, 3
0x1400551ee  int     29h; Win8: RtlFailFast(ecx)
0x1400551f0  mov     bl, [rdi+45h]
0x1400551f3  lea     rcx, [rbp+var_20]; LockHandle
0x1400551f7  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400551fe  nop     dword ptr [rax+rax+00h]
0x140055203  mov     eax, [rdi+88h]
0x140055209  test    al, 20h
0x14005520b  jnz     loc_140055349
0x140055211  mov     rcx, rdi
0x140055214  call    AfdGetTPacketsReference
0x140055219  test    al, al
0x14005521b  jnz     loc_140055349
0x140055221  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140055225  jnz     loc_140055326
0x14005522b  mov     r14, [rdi+0B0h]
0x140055232  mov     cl, 2; Irql
0x140055234  call    cs:__imp_IoReleaseCancelSpinLock
0x14005523b  nop     dword ptr [rax+rax+00h]
0x140055240  mov     rdx, [rsi+168h]
0x140055247  cmp     rdx, rdi
0x14005524a  jnz     short loc_140055259
0x14005524c  mov     qword ptr [rsi+168h], 0
0x140055257  jmp     short loc_140055282
0x140055259  mov     rax, [rdx+78h]
0x14005525d  sub     rax, 78h ; 'x'
0x140055261  cmp     rax, rdi
0x140055264  jz      short loc_14005527A
0x140055266  mov     rax, [rdx+78h]
0x14005526a  mov     rcx, [rax]
0x14005526d  lea     rdx, [rax-78h]
0x140055271  sub     rcx, 78h ; 'x'
0x140055275  cmp     rcx, rdi
0x140055278  jnz     short loc_140055266
0x14005527a  mov     qword ptr [rdx+78h], 0
0x140055282  mov     qword ptr [rdi+18h], 0
0x14005528a  mov     rsi, [r15+20h]
0x14005528e  mov     rcx, rsi
0x140055291  call    AfdCheckAndReferenceConnection
0x140055296  lea     rcx, [rbp+LockHandle]; LockHandle
0x14005529a  mov     bl, al
0x14005529c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400552a3  nop     dword ptr [rax+rax+00h]
0x1400552a8  test    bl, bl
0x1400552aa  jz      short loc_1400552B4
0x1400552ac  mov     rcx, rsi
0x1400552af  call    AfdAbortConnection
0x1400552b4  mov     cl, [rdi+45h]; NewIrql
0x1400552b7  cmp     cl, 2
0x1400552ba  jz      short loc_1400552C8
0x1400552bc  call    cs:__imp_KeLowerIrql
0x1400552c3  nop     dword ptr [rax+rax+00h]
0x1400552c8  test    byte ptr cs:xmmword_1400875E0+2, 4
0x1400552cf  jz      short loc_1400552EA
0x1400552d1  mov     edx, 33h ; '3'
0x1400552d6  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x1400552dd  mov     ecx, 412h
0x1400552e2  mov     r9, rdi
0x1400552e5  call    WPP_SF_q
0x1400552ea  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x1400552f0  mov     rcx, rdi; Irp
0x1400552f3  mov     dword ptr [rdi+30h], 0C0000120h
0x1400552fa  call    cs:__imp_IofCompleteRequest
0x140055301  nop     dword ptr [rax+rax+00h]
0x140055306  cmp     cs:AfdMaxActiveTransmitFileCount, 0
0x14005530d  jbe     loc_1400551DB
0x140055313  test    r14, r14
0x140055316  jnz     loc_1400551DB
0x14005531c  call    AfdStartNextQueuedTransmit
0x140055321  jmp     loc_1400551DB
0x140055326  lea     rcx, [rbp+LockHandle]; LockHandle
0x14005532a  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140055331  nop     dword ptr [rax+rax+00h]
0x140055336  mov     cl, bl; Irql
0x140055338  call    cs:__imp_IoReleaseCancelSpinLock
0x14005533f  nop     dword ptr [rax+rax+00h]
0x140055344  jmp     loc_1400551DB
0x140055349  mov     cl, 2; Irql
0x14005534b  call    cs:__imp_IoReleaseCancelSpinLock
0x140055352  nop     dword ptr [rax+rax+00h]
0x140055357  mov     eax, [rdi+88h]
0x14005535d  test    al, 20h
0x14005535f  jz      short loc_140055369
0x140055361  lock add dword ptr [rdi+88h], 0FFFFFFE0h
0x140055369  lea     rcx, [rbp+LockHandle]; LockHandle
0x14005536d  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140055374  nop     dword ptr [rax+rax+00h]
0x140055379  cmp     bl, 2
0x14005537c  jz      short loc_14005538C
0x14005537e  mov     cl, bl; NewIrql
0x140055380  call    cs:__imp_KeLowerIrql
0x140055387  nop     dword ptr [rax+rax+00h]
0x14005538c  mov     edx, 0C0000120h
0x140055391  mov     rcx, rdi
0x140055394  call    AfdAbortTPackets
0x140055399  jmp     loc_1400551C3
```
