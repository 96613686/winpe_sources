# BfsCheckDeleteList

- ea: `0x14000c1b4`
- end: `0x14000c316`
- name: `BfsCheckDeleteList`
- size: `354`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140002a30`
- `0x140003640`

## callees

- `0x14000c1b4`
- `0x14000c658`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c257`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c274`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c257`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c274`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c2ba`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c2db`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c2ba`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c2db`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c1ec`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c1ec`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c22a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c2ee`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c22a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c2ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c1d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c242`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c263`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c1d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c242`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c263`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c236`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c2c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c2fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c236`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c2c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c2fa`

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
  if ( (__int64 *)qword_1400191A0 == &qword_1400191A0
    || v4 - *(_QWORD *)(qword_1400191A0 + 32) <= (unsigned int)gBfsDeleteThreshold )
  {
    ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
  }
  else
  {
    ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
    KeLeaveCriticalRegion();
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&qword_140019178, 0);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&gBfsGlobalFileTable, 0);
    v5 = (__int64 *)qword_1400191A0;
    while ( 1 )
    {
      v6 = v5;
      if ( v5 == &qword_1400191A0 || v4 - v5[4] <= (unsigned int)gBfsDeleteThreshold )
        break;
      v5 = (__int64 *)*v5;
      BfsDeleteFileFromGlobalFileTable(a1, a2, (__int64)(v6 + 5));
    }
    ExReleasePushLockExclusiveEx(&gBfsGlobalFileTable, 0);
    KeLeaveCriticalRegion();
    ExReleasePushLockExclusiveEx(&qword_140019178, 0);
  }
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x14000c1b4  push    rbx
0x14000c1b6  push    rbp
0x14000c1b7  push    rsi
0x14000c1b8  push    rdi
0x14000c1b9  push    r14
0x14000c1bb  push    r15
0x14000c1bd  sub     rsp, 28h
0x14000c1c1  mov     rbx, 0FFFFF78000000014h
0x14000c1cb  mov     rsi, rdx
0x14000c1ce  mov     rbp, rcx
0x14000c1d1  mov     rbx, [rbx]
0x14000c1d4  call    cs:__imp_KeEnterCriticalRegion
0x14000c1db  nop     dword ptr [rax+rax+00h]
0x14000c1e0  lea     r14, gBfsGlobalFileTable
0x14000c1e7  xor     edx, edx
0x14000c1e9  mov     rcx, r14
0x14000c1ec  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000c1f3  nop     dword ptr [rax+rax+00h]
0x14000c1f8  mov     rax, cs:qword_1400191A0
0x14000c1ff  lea     r15, qword_1400191A0
0x14000c206  cmp     rax, r15
0x14000c209  jz      loc_14000C2E9
0x14000c20f  mov     rcx, rbx
0x14000c212  sub     rcx, [rax+20h]
0x14000c216  mov     eax, cs:gBfsDeleteThreshold
0x14000c21c  cmp     rcx, rax
0x14000c21f  jle     loc_14000C2E9
0x14000c225  xor     edx, edx
0x14000c227  mov     rcx, r14
0x14000c22a  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c231  nop     dword ptr [rax+rax+00h]
0x14000c236  call    cs:__imp_KeLeaveCriticalRegion
0x14000c23d  nop     dword ptr [rax+rax+00h]
0x14000c242  call    cs:__imp_KeEnterCriticalRegion
0x14000c249  nop     dword ptr [rax+rax+00h]
0x14000c24e  xor     edx, edx
0x14000c250  lea     rcx, qword_140019178
0x14000c257  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c25e  nop     dword ptr [rax+rax+00h]
0x14000c263  call    cs:__imp_KeEnterCriticalRegion
0x14000c26a  nop     dword ptr [rax+rax+00h]
0x14000c26f  xor     edx, edx
0x14000c271  mov     rcx, r14
0x14000c274  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c27b  nop     dword ptr [rax+rax+00h]
0x14000c280  mov     rdi, cs:qword_1400191A0
0x14000c287  jmp     short loc_14000C2AD
0x14000c289  mov     eax, cs:gBfsDeleteThreshold
0x14000c28f  mov     rcx, rbx
0x14000c292  sub     rcx, [rdi+20h]
0x14000c296  cmp     rcx, rax
0x14000c299  jle     short loc_14000C2B5
0x14000c29b  mov     rdi, [rdi]
0x14000c29e  add     r8, 28h ; '('
0x14000c2a2  mov     rdx, rsi
0x14000c2a5  mov     rcx, rbp
0x14000c2a8  call    BfsDeleteFileFromGlobalFileTable
0x14000c2ad  mov     r8, rdi
0x14000c2b0  cmp     rdi, r15
0x14000c2b3  jnz     short loc_14000C289
0x14000c2b5  xor     edx, edx
0x14000c2b7  mov     rcx, r14
0x14000c2ba  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c2c1  nop     dword ptr [rax+rax+00h]
0x14000c2c6  call    cs:__imp_KeLeaveCriticalRegion
0x14000c2cd  nop     dword ptr [rax+rax+00h]
0x14000c2d2  xor     edx, edx
0x14000c2d4  lea     rcx, qword_140019178
0x14000c2db  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c2e2  nop     dword ptr [rax+rax+00h]
0x14000c2e7  jmp     short loc_14000C2FA
0x14000c2e9  xor     edx, edx
0x14000c2eb  mov     rcx, r14
0x14000c2ee  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c2f5  nop     dword ptr [rax+rax+00h]
0x14000c2fa  call    cs:__imp_KeLeaveCriticalRegion
0x14000c301  nop     dword ptr [rax+rax+00h]
0x14000c306  xor     eax, eax
0x14000c308  add     rsp, 28h
0x14000c30c  pop     r15
0x14000c30e  pop     r14
0x14000c310  pop     rdi
0x14000c311  pop     rsi
0x14000c312  pop     rbp
0x14000c313  pop     rbx
0x14000c314  retn
```
