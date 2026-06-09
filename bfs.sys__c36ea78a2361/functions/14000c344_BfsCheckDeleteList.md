# BfsCheckDeleteList

- ea: `0x14000c344`
- end: `0x14000c4a6`
- name: `BfsCheckDeleteList`
- size: `354`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140002620`
- `0x140003770`

## callees

- `0x14000c344`
- `0x14000c7e8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c3e7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c404`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c3e7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c404`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c44a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c46b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c44a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c46b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c37c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c37c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c3ba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c47e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c3ba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c47e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c364`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c364`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c3c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c456`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c48a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c3c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c456`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c48a`

## pseudocode

```c
__int64 __fastcall BfsCheckDeleteList(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 *v5; // rdi
  __int64 *v6; // r8

  v4 = MEMORY[0xFFFFF78000000014];
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&gBfsGlobalFileTable, 0);
  if ( (__int64 *)qword_140019190 == &qword_140019190
    || v4 - *(_QWORD *)(qword_140019190 + 32) <= (unsigned int)gBfsDeleteThreshold )
  {
    ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
  }
  else
  {
    ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
    KeLeaveCriticalRegion();
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&qword_140019168, 0);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&gBfsGlobalFileTable, 0);
    v5 = (__int64 *)qword_140019190;
    while ( 1 )
    {
      v6 = v5;
      if ( v5 == &qword_140019190 || v4 - v5[4] <= (unsigned int)gBfsDeleteThreshold )
        break;
      v5 = (__int64 *)*v5;
      BfsDeleteFileFromGlobalFileTable(a1, a2, v6 + 5);
    }
    ExReleasePushLockExclusiveEx(&gBfsGlobalFileTable, 0);
    KeLeaveCriticalRegion();
    ExReleasePushLockExclusiveEx(&qword_140019168, 0);
  }
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x14000c344  push    rbx
0x14000c346  push    rbp
0x14000c347  push    rsi
0x14000c348  push    rdi
0x14000c349  push    r14
0x14000c34b  push    r15
0x14000c34d  sub     rsp, 28h
0x14000c351  mov     rbx, 0FFFFF78000000014h
0x14000c35b  mov     rsi, rdx
0x14000c35e  mov     rbp, rcx
0x14000c361  mov     rbx, [rbx]
0x14000c364  call    cs:__imp_KeEnterCriticalRegion
0x14000c36b  nop     dword ptr [rax+rax+00h]
0x14000c370  lea     r14, gBfsGlobalFileTable
0x14000c377  xor     edx, edx
0x14000c379  mov     rcx, r14
0x14000c37c  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000c383  nop     dword ptr [rax+rax+00h]
0x14000c388  mov     rax, cs:qword_140019190
0x14000c38f  lea     r15, qword_140019190
0x14000c396  cmp     rax, r15
0x14000c399  jz      loc_14000C479
0x14000c39f  mov     rcx, rbx
0x14000c3a2  sub     rcx, [rax+20h]
0x14000c3a6  mov     eax, cs:gBfsDeleteThreshold
0x14000c3ac  cmp     rcx, rax
0x14000c3af  jle     loc_14000C479
0x14000c3b5  xor     edx, edx
0x14000c3b7  mov     rcx, r14
0x14000c3ba  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c3c1  nop     dword ptr [rax+rax+00h]
0x14000c3c6  call    cs:__imp_KeLeaveCriticalRegion
0x14000c3cd  nop     dword ptr [rax+rax+00h]
0x14000c3d2  call    cs:__imp_KeEnterCriticalRegion
0x14000c3d9  nop     dword ptr [rax+rax+00h]
0x14000c3de  xor     edx, edx
0x14000c3e0  lea     rcx, qword_140019168
0x14000c3e7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c3ee  nop     dword ptr [rax+rax+00h]
0x14000c3f3  call    cs:__imp_KeEnterCriticalRegion
0x14000c3fa  nop     dword ptr [rax+rax+00h]
0x14000c3ff  xor     edx, edx
0x14000c401  mov     rcx, r14
0x14000c404  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c40b  nop     dword ptr [rax+rax+00h]
0x14000c410  mov     rdi, cs:qword_140019190
0x14000c417  jmp     short loc_14000C43D
0x14000c419  mov     eax, cs:gBfsDeleteThreshold
0x14000c41f  mov     rcx, rbx
0x14000c422  sub     rcx, [rdi+20h]
0x14000c426  cmp     rcx, rax
0x14000c429  jle     short loc_14000C445
0x14000c42b  mov     rdi, [rdi]
0x14000c42e  add     r8, 28h ; '('
0x14000c432  mov     rdx, rsi
0x14000c435  mov     rcx, rbp
0x14000c438  call    BfsDeleteFileFromGlobalFileTable
0x14000c43d  mov     r8, rdi
0x14000c440  cmp     rdi, r15
0x14000c443  jnz     short loc_14000C419
0x14000c445  xor     edx, edx
0x14000c447  mov     rcx, r14
0x14000c44a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c451  nop     dword ptr [rax+rax+00h]
0x14000c456  call    cs:__imp_KeLeaveCriticalRegion
0x14000c45d  nop     dword ptr [rax+rax+00h]
0x14000c462  xor     edx, edx
0x14000c464  lea     rcx, qword_140019168
0x14000c46b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c472  nop     dword ptr [rax+rax+00h]
0x14000c477  jmp     short loc_14000C48A
0x14000c479  xor     edx, edx
0x14000c47b  mov     rcx, r14
0x14000c47e  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c485  nop     dword ptr [rax+rax+00h]
0x14000c48a  call    cs:__imp_KeLeaveCriticalRegion
0x14000c491  nop     dword ptr [rax+rax+00h]
0x14000c496  xor     eax, eax
0x14000c498  add     rsp, 28h
0x14000c49c  pop     r15
0x14000c49e  pop     r14
0x14000c4a0  pop     rdi
0x14000c4a1  pop     rsi
0x14000c4a2  pop     rbp
0x14000c4a3  pop     rbx
0x14000c4a4  retn
```
