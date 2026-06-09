# AfdCompleteClosePendedTPackets

- ea: `0x140055638`
- end: `0x1400557be`
- name: `AfdCompleteClosePendedTPackets`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010db0`

## callees

- `0x140043ef8`
- `0x140047a48`
- `0x140055638`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055754`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140055754`
- `ntoskrnl!IofCompleteRequest` at `0x140055792`
- `ntoskrnl!IofCompleteRequest` at `0x140055792`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140055744`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140055744`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400556ad`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005571c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400556ad`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005571c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005565d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005565d`

## pseudocode

```c
void __fastcall AfdCompleteClosePendedTPackets(__int64 a1)
{
  __int64 v2; // rbx
  _QWORD *v3; // rdx
  _QWORD *v4; // rax
  __int64 v5; // rdi
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF
  KIRQL Irql; // [rsp+50h] [rbp+8h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
  v2 = *(_QWORD *)(a1 + 360);
  if ( v2 )
  {
    while ( *(_QWORD *)(v2 + 24) != -1 )
    {
      v2 = *(_QWORD *)(v2 + 120) - 120LL;
      if ( !v2 )
        goto LABEL_4;
    }
    *(_QWORD *)(v2 + 24) = 0;
    v3 = *(_QWORD **)(a1 + 360);
    if ( v3 == (_QWORD *)v2 )
    {
      *(_QWORD *)(a1 + 360) = 0;
    }
    else
    {
      if ( v3[15] - 120LL != v2 )
      {
        do
        {
          v4 = (_QWORD *)v3[15];
          v3 = v4 - 15;
        }
        while ( *v4 - 120LL != v2 );
      }
      v3[15] = 0;
    }
    AfdRefreshEndpoint(a1);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    _InterlockedExchange((volatile __int32 *)(a1 + 368), 0);
    if ( !_InterlockedExchange64((volatile __int64 *)(v2 + 104), 0) )
    {
      Irql = 0;
      IoAcquireCancelSpinLock(&Irql);
      IoReleaseCancelSpinLock(Irql);
    }
    v5 = *(_QWORD *)(v2 + 176);
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_q(1042, 53, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, v2);
    IofCompleteRequest((PIRP)v2, AfdPriorityBoost);
    if ( AfdMaxActiveTransmitFileCount && !v5 )
      AfdStartNextQueuedTransmit();
  }
  else
  {
LABEL_4:
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_q(1042, 52, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, a1);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
}

```

## disassembly

```asm
0x140055638  mov     [rsp+arg_8], rbx
0x14005563d  push    rdi
0x14005563e  sub     rsp, 40h
0x140055642  mov     rdi, rcx
0x140055645  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14005564a  xorps   xmm0, xmm0
0x14005564d  xor     eax, eax
0x14005564f  add     rcx, 38h ; '8'; SpinLock
0x140055653  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140055658  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14005565d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140055664  nop     dword ptr [rax+rax+00h]
0x140055669  mov     rbx, [rdi+168h]
0x140055670  test    rbx, rbx
0x140055673  jz      short loc_140055686
0x140055675  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x14005567a  jz      short loc_1400556C5
0x14005567c  mov     rbx, [rbx+78h]
0x140055680  sub     rbx, 78h ; 'x'
0x140055684  jnz     short loc_140055675
0x140055686  test    byte ptr cs:xmmword_1400875E0+2, 4
0x14005568d  jz      short loc_1400556A8
0x14005568f  mov     edx, 34h ; '4'
0x140055694  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x14005569b  mov     ecx, 412h
0x1400556a0  mov     r9, rdi
0x1400556a3  call    WPP_SF_q
0x1400556a8  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x1400556ad  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400556b4  nop     dword ptr [rax+rax+00h]
0x1400556b9  mov     rbx, [rsp+48h+arg_8]
0x1400556be  add     rsp, 40h
0x1400556c2  pop     rdi
0x1400556c3  retn
0x1400556c5  mov     qword ptr [rbx+18h], 0
0x1400556cd  mov     rdx, [rdi+168h]
0x1400556d4  cmp     rdx, rbx
0x1400556d7  jnz     short loc_1400556E6
0x1400556d9  mov     qword ptr [rdi+168h], 0
0x1400556e4  jmp     short loc_14005570F
0x1400556e6  mov     rax, [rdx+78h]
0x1400556ea  sub     rax, 78h ; 'x'
0x1400556ee  cmp     rax, rbx
0x1400556f1  jz      short loc_140055707
0x1400556f3  mov     rax, [rdx+78h]
0x1400556f7  mov     rcx, [rax]
0x1400556fa  lea     rdx, [rax-78h]
0x1400556fe  sub     rcx, 78h ; 'x'
0x140055702  cmp     rcx, rbx
0x140055705  jnz     short loc_1400556F3
0x140055707  mov     qword ptr [rdx+78h], 0
0x14005570f  mov     rcx, rdi
0x140055712  call    AfdRefreshEndpoint
0x140055717  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14005571c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140055723  nop     dword ptr [rax+rax+00h]
0x140055728  xor     eax, eax
0x14005572a  xchg    eax, [rdi+170h]
0x140055730  xor     eax, eax
0x140055732  xchg    rax, [rbx+68h]
0x140055736  test    rax, rax
0x140055739  jnz     short loc_140055760
0x14005573b  lea     rcx, [rsp+48h+Irql]; Irql
0x140055740  mov     [rsp+48h+Irql], al
0x140055744  call    cs:__imp_IoAcquireCancelSpinLock
0x14005574b  nop     dword ptr [rax+rax+00h]
0x140055750  mov     cl, [rsp+48h+Irql]; Irql
0x140055754  call    cs:__imp_IoReleaseCancelSpinLock
0x14005575b  nop     dword ptr [rax+rax+00h]
0x140055760  mov     rdi, [rbx+0B0h]
0x140055767  test    byte ptr cs:xmmword_1400875E0+2, 4
0x14005576e  jz      short loc_140055789
0x140055770  mov     edx, 35h ; '5'
0x140055775  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x14005577c  mov     ecx, 412h
0x140055781  mov     r9, rbx
0x140055784  call    WPP_SF_q
0x140055789  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14005578f  mov     rcx, rbx; Irp
0x140055792  call    cs:__imp_IofCompleteRequest
0x140055799  nop     dword ptr [rax+rax+00h]
0x14005579e  cmp     cs:AfdMaxActiveTransmitFileCount, 0
0x1400557a5  jbe     loc_1400556B9
0x1400557ab  test    rdi, rdi
0x1400557ae  jnz     loc_1400556B9
0x1400557b4  call    AfdStartNextQueuedTransmit
0x1400557b9  jmp     loc_1400556B9
```
