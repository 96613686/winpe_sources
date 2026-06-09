# UlpFreeConsumer

- ea: `0x140095f50`
- end: `0x140096203`
- name: `UlpFreeConsumer`
- size: `691`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400953bc`
- `0x1400955b8`
- `0x1400b3714`
- `0x1400cf2b8`

## callees

- `0x14000a350`
- `0x1400620f0`
- `0x140092510`
- `0x140095f50`
- `0x14009620c`
- `0x140096328`
- `0x1400af3e0`
- `0x1400b3d20`
- `0x140105a58`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140095fc0`
- `ntoskrnl!ZwClose` at `0x140095fc0`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140096083`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140096083`
- `ntoskrnl!ObfDereferenceObject` at `0x140095fa7`
- `ntoskrnl!ObfDereferenceObject` at `0x140095fd9`
- `ntoskrnl!ObfDereferenceObject` at `0x140095fa7`
- `ntoskrnl!ObfDereferenceObject` at `0x140095fd9`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14009603b`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14009603b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009608f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400960b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009608f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400960b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400961cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400961cc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400960ab`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400960ab`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140096018`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140096018`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140095ff6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140096028`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140095ff6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140096028`

## pseudocode

```c
void __fastcall UlpFreeConsumer(volatile signed __int32 **P)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rcx
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rcx
  char v6; // si
  volatile signed __int32 *v7; // rbx
  char v8; // bl
  volatile signed __int32 *v9; // rcx
  volatile signed __int32 *v10; // rdx
  int v11; // eax
  volatile signed __int32 *v12; // rdx
  int v13; // eax
  volatile signed __int32 *v14; // rdx
  int v15; // eax
  volatile signed __int32 *v16; // rcx

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 49, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, P);
  if ( P[13] )
    UlFreeCapturedProcessIdentity();
  v2 = P[2];
  if ( v2 )
    UlFreePerNode((void *)v2);
  v3 = P[11];
  if ( v3 )
  {
    ObfDereferenceObject((PVOID)v3);
    P[11] = 0;
  }
  v4 = P[10];
  if ( v4 )
  {
    ZwClose((HANDLE)v4);
    P[10] = 0;
  }
  v5 = P[9];
  if ( v5 )
  {
    ObfDereferenceObject((PVOID)v5);
    P[9] = 0;
  }
  if ( P[1] )
  {
    v6 = 0;
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(*((_QWORD *)P[1] + 41) + 4144LL, 0);
    v7 = P[1];
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*((_QWORD *)v7 + 35));
    v8 = *((_BYTE *)P + 128);
    *((_BYTE *)P + 128) = 0;
    if ( *((_BYTE *)P + 144) )
    {
      UlpDetachConsumerFromRequestQueue(P);
      v9 = P[1];
      *((_BYTE *)P + 144) = 0;
      v6 = UlpAttemptRequestQueueCleanup(v9);
    }
    ExReleaseCacheAwarePushLockExclusive(*((_QWORD *)P[1] + 35));
    KeLeaveCriticalRegion();
    ExReleasePushLockExclusiveEx(*((_QWORD *)P[1] + 41) + 4144LL, 0);
    KeLeaveCriticalRegion();
    if ( v8 )
    {
      v10 = (volatile signed __int32 *)(*((_QWORD *)P[1] + 41) + 4208LL);
      v11 = _InterlockedDecrement(v10);
      if ( UxDebugCheckRefcount && v11 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v10, 0xAu, v11);
      if ( !v11 )
        UxPodCheckZombieCleanup(*((_QWORD *)P[1] + 41));
    }
    v12 = P[1];
    v13 = _InterlockedDecrement(v12);
    if ( UxDebugCheckRefcount && v13 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v12, 6u, v13);
    if ( !v13 )
      UlFreeRequestQueue((PSECURITY_DESCRIPTOR *)P[1]);
    if ( v6 )
    {
      v14 = P[1];
      v15 = _InterlockedDecrement(v14);
      if ( UxDebugCheckRefcount && v15 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v14, 1u, v15);
      if ( !v15 )
        UlFreeRequestQueue((PSECURITY_DESCRIPTOR *)P[1]);
    }
    P[1] = 0;
  }
  v16 = P[17];
  if ( v16 )
  {
    UxPodDereferenceSilo(*((PVOID *)v16 + 8), 0x50416C55u, 6u);
    P[17] = 0;
  }
  *((_DWORD *)P + 6) = 1885424757;
  ExFreePoolWithTag(P, 0);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 50, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
}

```

## disassembly

```asm
0x140095f50  push    rbx
0x140095f52  push    rbp
0x140095f53  push    rsi
0x140095f54  push    rdi
0x140095f55  push    r14
0x140095f57  sub     rsp, 20h
0x140095f5b  mov     rdi, rcx
0x140095f5e  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140095f65  jz      short loc_140095F80
0x140095f67  mov     edx, 31h ; '1'
0x140095f6c  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140095f73  mov     ecx, 408h
0x140095f78  mov     r9, rdi
0x140095f7b  call    WPP_SF_q
0x140095f80  lea     rcx, [rdi+68h]
0x140095f84  xor     ebp, ebp
0x140095f86  cmp     [rcx], rbp
0x140095f89  jz      short loc_140095F90
0x140095f8b  call    UlFreeCapturedProcessIdentity
0x140095f90  mov     rcx, [rdi+10h]; void *
0x140095f94  test    rcx, rcx
0x140095f97  jz      short loc_140095F9E
0x140095f99  call    UlFreePerNode
0x140095f9e  mov     rcx, [rdi+58h]; Object
0x140095fa2  test    rcx, rcx
0x140095fa5  jz      short loc_140095FB7
0x140095fa7  call    cs:__imp_ObfDereferenceObject
0x140095fae  nop     dword ptr [rax+rax+00h]
0x140095fb3  mov     [rdi+58h], rbp
0x140095fb7  mov     rcx, [rdi+50h]; Handle
0x140095fbb  test    rcx, rcx
0x140095fbe  jz      short loc_140095FD0
0x140095fc0  call    cs:__imp_ZwClose
0x140095fc7  nop     dword ptr [rax+rax+00h]
0x140095fcc  mov     [rdi+50h], rbp
0x140095fd0  mov     rcx, [rdi+48h]; Object
0x140095fd4  test    rcx, rcx
0x140095fd7  jz      short loc_140095FE9
0x140095fd9  call    cs:__imp_ObfDereferenceObject
0x140095fe0  nop     dword ptr [rax+rax+00h]
0x140095fe5  mov     [rdi+48h], rbp
0x140095fe9  cmp     [rdi+8], rbp
0x140095fed  jz      loc_140096199
0x140095ff3  mov     sil, bpl
0x140095ff6  call    cs:__imp_KeEnterCriticalRegion
0x140095ffd  nop     dword ptr [rax+rax+00h]
0x140096002  mov     rax, [rdi+8]
0x140096006  mov     r14d, 1030h
0x14009600c  xor     edx, edx
0x14009600e  mov     rcx, [rax+148h]
0x140096015  add     rcx, r14
0x140096018  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14009601f  nop     dword ptr [rax+rax+00h]
0x140096024  mov     rbx, [rdi+8]
0x140096028  call    cs:__imp_KeEnterCriticalRegion
0x14009602f  nop     dword ptr [rax+rax+00h]
0x140096034  mov     rcx, [rbx+118h]
0x14009603b  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x140096042  nop     dword ptr [rax+rax+00h]
0x140096047  mov     bl, [rdi+80h]
0x14009604d  mov     [rdi+80h], bpl
0x140096054  cmp     [rdi+90h], bpl
0x14009605b  jz      short loc_140096078
0x14009605d  mov     rcx, rdi
0x140096060  call    UlpDetachConsumerFromRequestQueue
0x140096065  mov     rcx, [rdi+8]
0x140096069  mov     [rdi+90h], bpl
0x140096070  call    UlpAttemptRequestQueueCleanup
0x140096075  mov     sil, al
0x140096078  mov     rcx, [rdi+8]
0x14009607c  mov     rcx, [rcx+118h]
0x140096083  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x14009608a  nop     dword ptr [rax+rax+00h]
0x14009608f  call    cs:__imp_KeLeaveCriticalRegion
0x140096096  nop     dword ptr [rax+rax+00h]
0x14009609b  mov     rcx, [rdi+8]
0x14009609f  xor     edx, edx
0x1400960a1  mov     rcx, [rcx+148h]
0x1400960a8  add     rcx, r14
0x1400960ab  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400960b2  nop     dword ptr [rax+rax+00h]
0x1400960b7  call    cs:__imp_KeLeaveCriticalRegion
0x1400960be  nop     dword ptr [rax+rax+00h]
0x1400960c3  or      r14d, 0FFFFFFFFh
0x1400960c7  test    bl, bl
0x1400960c9  jz      short loc_14009611A
0x1400960cb  mov     rax, [rdi+8]
0x1400960cf  mov     rdx, [rax+148h]
0x1400960d6  mov     eax, r14d
0x1400960d9  add     rdx, 1070h; BugCheckParameter2
0x1400960e0  lock xadd [rdx], eax
0x1400960e4  add     eax, r14d
0x1400960e7  cmp     cs:UxDebugCheckRefcount, bpl
0x1400960ee  jz      short loc_140096106
0x1400960f0  cmp     eax, r14d
0x1400960f3  jg      short loc_140096106
0x1400960f5  movsxd  r9, eax; BugCheckParameter4
0x1400960f8  lea     ecx, [r14+4]; BugCheckParameter1
0x1400960fc  lea     r8d, [r14+0Bh]; BugCheckParameter3
0x140096100  call    UlBugCheckEx
0x140096106  test    eax, eax
0x140096108  jnz     short loc_14009611A
0x14009610a  mov     rcx, [rdi+8]
0x14009610e  mov     rcx, [rcx+148h]
0x140096115  call    UxPodCheckZombieCleanup
0x14009611a  mov     rdx, [rdi+8]; BugCheckParameter2
0x14009611e  mov     eax, r14d
0x140096121  lock xadd [rdx], eax
0x140096125  add     eax, r14d
0x140096128  cmp     cs:UxDebugCheckRefcount, bpl
0x14009612f  jz      short loc_140096148
0x140096131  cmp     eax, r14d
0x140096134  jg      short loc_140096148
0x140096136  mov     ecx, 3; BugCheckParameter1
0x14009613b  movsxd  r9, eax; BugCheckParameter4
0x14009613e  lea     r8d, [rcx+3]; BugCheckParameter3
0x140096142  call    UlBugCheckEx
0x140096148  test    eax, eax
0x14009614a  jnz     short loc_140096155
0x14009614c  mov     rcx, [rdi+8]; P
0x140096150  call    UlFreeRequestQueue
0x140096155  test    sil, sil
0x140096158  jz      short loc_140096195
0x14009615a  mov     rdx, [rdi+8]; BugCheckParameter2
0x14009615e  mov     eax, r14d
0x140096161  lock xadd [rdx], eax
0x140096165  add     eax, r14d
0x140096168  cmp     cs:UxDebugCheckRefcount, bpl
0x14009616f  jz      short loc_140096188
0x140096171  cmp     eax, r14d
0x140096174  jg      short loc_140096188
0x140096176  mov     ecx, 3; BugCheckParameter1
0x14009617b  movsxd  r9, eax; BugCheckParameter4
0x14009617e  lea     r8d, [rcx-2]; BugCheckParameter3
0x140096182  call    UlBugCheckEx
0x140096188  test    eax, eax
0x14009618a  jnz     short loc_140096195
0x14009618c  mov     rcx, [rdi+8]; P
0x140096190  call    UlFreeRequestQueue
0x140096195  mov     [rdi+8], rbp
0x140096199  mov     rcx, [rdi+88h]
0x1400961a0  test    rcx, rcx
0x1400961a3  jz      short loc_1400961C0
0x1400961a5  mov     rcx, [rcx+40h]; Object
0x1400961a9  mov     edx, 50416C55h; Tag
0x1400961ae  mov     r8d, 6; BugCheckParameter3
0x1400961b4  call    UxPodDereferenceSilo
0x1400961b9  mov     [rdi+88h], rbp
0x1400961c0  xor     edx, edx; Tag
0x1400961c2  mov     dword ptr [rdi+18h], 70614C75h
0x1400961c9  mov     rcx, rdi; P
0x1400961cc  call    cs:__imp_ExFreePoolWithTag
0x1400961d3  nop     dword ptr [rax+rax+00h]
0x1400961d8  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400961df  jz      short loc_1400961F7
0x1400961e1  mov     edx, 32h ; '2'
0x1400961e6  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400961ed  mov     ecx, 408h
0x1400961f2  call    WPP_SF_
0x1400961f7  add     rsp, 20h
0x1400961fb  pop     r14
0x1400961fd  pop     rdi
0x1400961fe  pop     rsi
0x1400961ff  pop     rbp
0x140096200  pop     rbx
0x140096201  retn
```
