# AfdCompleteClosePendedTPackets

- ea: `0x140055598`
- end: `0x14005571e`
- name: `AfdCompleteClosePendedTPackets`
- size: `390`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010db0`

## callees

- `0x140043ed8`
- `0x1400479c8`
- `0x140055598`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400556b4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400556b4`
- `ntoskrnl!IofCompleteRequest` at `0x1400556f2`
- `ntoskrnl!IofCompleteRequest` at `0x1400556f2`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400556a4`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400556a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005560d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005567c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005560d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005567c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400555bd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400555bd`

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
      WPP_SF_q(1042, 53, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, v2);
    IofCompleteRequest((PIRP)v2, AfdPriorityBoost);
    if ( AfdMaxActiveTransmitFileCount && !v5 )
      AfdStartNextQueuedTransmit();
  }
  else
  {
LABEL_4:
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_q(1042, 52, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, a1);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
}

```

## disassembly

```asm
0x140055598  mov     [rsp+arg_8], rbx
0x14005559d  push    rdi
0x14005559e  sub     rsp, 40h
0x1400555a2  mov     rdi, rcx
0x1400555a5  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x1400555aa  xorps   xmm0, xmm0
0x1400555ad  xor     eax, eax
0x1400555af  add     rcx, 38h ; '8'; SpinLock
0x1400555b3  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x1400555b8  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x1400555bd  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400555c4  nop     dword ptr [rax+rax+00h]
0x1400555c9  mov     rbx, [rdi+168h]
0x1400555d0  test    rbx, rbx
0x1400555d3  jz      short loc_1400555E6
0x1400555d5  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x1400555da  jz      short loc_140055625
0x1400555dc  mov     rbx, [rbx+78h]
0x1400555e0  sub     rbx, 78h ; 'x'
0x1400555e4  jnz     short loc_1400555D5
0x1400555e6  test    byte ptr cs:xmmword_1400875E0+2, 4
0x1400555ed  jz      short loc_140055608
0x1400555ef  mov     edx, 34h ; '4'
0x1400555f4  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x1400555fb  mov     ecx, 412h
0x140055600  mov     r9, rdi
0x140055603  call    WPP_SF_q
0x140055608  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14005560d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140055614  nop     dword ptr [rax+rax+00h]
0x140055619  mov     rbx, [rsp+48h+arg_8]
0x14005561e  add     rsp, 40h
0x140055622  pop     rdi
0x140055623  retn
0x140055625  mov     qword ptr [rbx+18h], 0
0x14005562d  mov     rdx, [rdi+168h]
0x140055634  cmp     rdx, rbx
0x140055637  jnz     short loc_140055646
0x140055639  mov     qword ptr [rdi+168h], 0
0x140055644  jmp     short loc_14005566F
0x140055646  mov     rax, [rdx+78h]
0x14005564a  sub     rax, 78h ; 'x'
0x14005564e  cmp     rax, rbx
0x140055651  jz      short loc_140055667
0x140055653  mov     rax, [rdx+78h]
0x140055657  mov     rcx, [rax]
0x14005565a  lea     rdx, [rax-78h]
0x14005565e  sub     rcx, 78h ; 'x'
0x140055662  cmp     rcx, rbx
0x140055665  jnz     short loc_140055653
0x140055667  mov     qword ptr [rdx+78h], 0
0x14005566f  mov     rcx, rdi
0x140055672  call    AfdRefreshEndpoint
0x140055677  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14005567c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140055683  nop     dword ptr [rax+rax+00h]
0x140055688  xor     eax, eax
0x14005568a  xchg    eax, [rdi+170h]
0x140055690  xor     eax, eax
0x140055692  xchg    rax, [rbx+68h]
0x140055696  test    rax, rax
0x140055699  jnz     short loc_1400556C0
0x14005569b  lea     rcx, [rsp+48h+Irql]; Irql
0x1400556a0  mov     [rsp+48h+Irql], al
0x1400556a4  call    cs:__imp_IoAcquireCancelSpinLock
0x1400556ab  nop     dword ptr [rax+rax+00h]
0x1400556b0  mov     cl, [rsp+48h+Irql]; Irql
0x1400556b4  call    cs:__imp_IoReleaseCancelSpinLock
0x1400556bb  nop     dword ptr [rax+rax+00h]
0x1400556c0  mov     rdi, [rbx+0B0h]
0x1400556c7  test    byte ptr cs:xmmword_1400875E0+2, 4
0x1400556ce  jz      short loc_1400556E9
0x1400556d0  mov     edx, 35h ; '5'
0x1400556d5  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x1400556dc  mov     ecx, 412h
0x1400556e1  mov     r9, rbx
0x1400556e4  call    WPP_SF_q
0x1400556e9  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x1400556ef  mov     rcx, rbx; Irp
0x1400556f2  call    cs:__imp_IofCompleteRequest
0x1400556f9  nop     dword ptr [rax+rax+00h]
0x1400556fe  cmp     cs:AfdMaxActiveTransmitFileCount, 0
0x140055705  jbe     loc_140055619
0x14005570b  test    rdi, rdi
0x14005570e  jnz     loc_140055619
0x140055714  call    AfdStartNextQueuedTransmit
0x140055719  jmp     loc_140055619
```
