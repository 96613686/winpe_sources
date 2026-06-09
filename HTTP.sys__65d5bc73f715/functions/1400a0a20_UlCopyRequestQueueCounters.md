# UlCopyRequestQueueCounters

- ea: `0x1400a0a20`
- end: `0x1400a0bb1`
- name: `UlCopyRequestQueueCounters`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14009f338`

## callees

- `0x1400a0a20`
- `0x1401c3008`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a0b23`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a0b23`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a0a78`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a0a78`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a0a99`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a0a99`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a0b53`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a0b53`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a0aa5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a0aa5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a0a63`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a0a63`

## pseudocode

```c
__int64 __fastcall UlCopyRequestQueueCounters(_QWORD *a1, __int64 a2)
{
  int v2; // r15d
  int v3; // r12d
  __int64 v6; // rbx
  unsigned __int16 v7; // bp
  __int64 i; // r13
  __int64 result; // rax
  __int64 v10; // rdi
  __int64 v11; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-68h] BYREF

  v2 = 0;
  v3 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 255, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, a2);
  v6 = 0x7FFFFFFFFFFFFFFFLL;
  KeEnterCriticalRegion();
  v7 = 0;
  for ( i = ExAcquireCacheAwarePushLockSharedEx(a1[35], 0); v7 < (unsigned __int16)UlNumberOfLanes; ++v7 )
  {
    v10 = *(_QWORD *)(a1[36] + 8LL * v7);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v10, &LockHandle);
    v2 += *(_DWORD *)(v10 + 80);
    v11 = *(_QWORD *)(v10 + 48);
    v3 += *(_DWORD *)(v10 + 40);
    if ( v11 != v10 + 48 && *(_QWORD *)(v11 + 72) < v6 )
      v6 = *(_QWORD *)(v11 + 72);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  ExReleaseCacheAwarePushLockSharedEx(i, 0);
  KeLeaveCriticalRegion();
  *(_QWORD *)(a2 + 16) = a1[12];
  *(_QWORD *)(a2 + 24) = a1[13];
  *(_QWORD *)(a2 + 32) = a1[14];
  *(_QWORD *)(a2 + 8) = v6;
  *(_DWORD *)(a2 + 4) = v2;
  *(_DWORD *)(a2 + 56) = v3;
  result = MEMORY[0xFFFFF78000000014];
  *(_QWORD *)(a2 + 40) = MEMORY[0xFFFFF78000000014];
  *(_QWORD *)(a2 + 48) = 10000000;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    return WPP_SF_q(1032, 256, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a2);
  return result;
}

```

## disassembly

```asm
0x1400a0a20  push    rbx
0x1400a0a22  push    rbp
0x1400a0a23  push    rsi
0x1400a0a24  push    rdi
0x1400a0a25  push    r12
0x1400a0a27  push    r13
0x1400a0a29  push    r14
0x1400a0a2b  push    r15
0x1400a0a2d  sub     rsp, 58h
0x1400a0a31  xor     r15d, r15d
0x1400a0a34  xor     r12d, r12d
0x1400a0a37  xor     eax, eax
0x1400a0a39  xorps   xmm0, xmm0
0x1400a0a3c  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x1400a0a41  mov     rsi, rdx
0x1400a0a44  mov     r14, rcx
0x1400a0a47  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x1400a0a4c  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400a0a53  jnz     loc_1400A0B70
0x1400a0a59  mov     rbx, 7FFFFFFFFFFFFFFFh
0x1400a0a63  call    cs:__imp_KeEnterCriticalRegion
0x1400a0a6a  nop     dword ptr [rax+rax+00h]
0x1400a0a6f  mov     rcx, [r14+118h]
0x1400a0a76  xor     edx, edx
0x1400a0a78  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400a0a7f  nop     dword ptr [rax+rax+00h]
0x1400a0a84  xor     ecx, ecx
0x1400a0a86  xor     ebp, ebp
0x1400a0a88  cmp     cx, cs:UlNumberOfLanes
0x1400a0a8f  mov     r13, rax
0x1400a0a92  jb      short loc_1400A0B0D
0x1400a0a94  xor     edx, edx
0x1400a0a96  mov     rcx, r13
0x1400a0a99  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400a0aa0  nop     dword ptr [rax+rax+00h]
0x1400a0aa5  call    cs:__imp_KeLeaveCriticalRegion
0x1400a0aac  nop     dword ptr [rax+rax+00h]
0x1400a0ab1  mov     rax, [r14+60h]
0x1400a0ab5  mov     [rsi+10h], rax
0x1400a0ab9  mov     rax, [r14+68h]
0x1400a0abd  mov     [rsi+18h], rax
0x1400a0ac1  mov     rax, [r14+70h]
0x1400a0ac5  mov     [rsi+20h], rax
0x1400a0ac9  mov     rax, 0FFFFF78000000014h
0x1400a0ad3  mov     [rsi+8], rbx
0x1400a0ad7  mov     [rsi+4], r15d
0x1400a0adb  mov     [rsi+38h], r12d
0x1400a0adf  mov     rax, [rax]
0x1400a0ae2  mov     [rsi+28h], rax
0x1400a0ae6  mov     qword ptr [rsi+30h], 989680h
0x1400a0aee  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400a0af5  jnz     loc_1400A0B93
0x1400a0afb  add     rsp, 58h
0x1400a0aff  pop     r15
0x1400a0b01  pop     r14
0x1400a0b03  pop     r13
0x1400a0b05  pop     r12
0x1400a0b07  pop     rdi
0x1400a0b08  pop     rsi
0x1400a0b09  pop     rbp
0x1400a0b0a  pop     rbx
0x1400a0b0b  retn
0x1400a0b0d  mov     rcx, [r14+120h]
0x1400a0b14  movzx   edx, bp
0x1400a0b17  mov     rdi, [rcx+rdx*8]
0x1400a0b1b  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x1400a0b20  mov     rcx, rdi; SpinLock
0x1400a0b23  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400a0b2a  nop     dword ptr [rax+rax+00h]
0x1400a0b2f  add     r15d, [rdi+50h]
0x1400a0b33  lea     rax, [rdi+30h]
0x1400a0b37  mov     rcx, [rax]
0x1400a0b3a  add     r12d, [rdi+28h]
0x1400a0b3e  cmp     rcx, rax
0x1400a0b41  jz      short loc_1400A0B4E
0x1400a0b43  mov     rax, [rcx+48h]
0x1400a0b47  cmp     rax, rbx
0x1400a0b4a  cmovl   rbx, rax
0x1400a0b4e  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x1400a0b53  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400a0b5a  nop     dword ptr [rax+rax+00h]
0x1400a0b5f  inc     bp
0x1400a0b62  cmp     bp, cs:UlNumberOfLanes
0x1400a0b69  jb      short loc_1400A0B0D
0x1400a0b6b  jmp     loc_1400A0A94
0x1400a0b70  mov     edx, 0FFh
0x1400a0b75  mov     [rsp+98h+var_78], rsi
0x1400a0b7a  mov     ecx, 408h
0x1400a0b7f  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400a0b86  mov     r9, r14
0x1400a0b89  call    WPP_SF_qq
0x1400a0b8e  jmp     loc_1400A0A59
0x1400a0b93  mov     edx, 100h
0x1400a0b98  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400a0b9f  mov     ecx, 408h
0x1400a0ba4  mov     r9, rsi
0x1400a0ba7  call    WPP_SF_q
0x1400a0bac  jmp     loc_1400A0AFB
```
