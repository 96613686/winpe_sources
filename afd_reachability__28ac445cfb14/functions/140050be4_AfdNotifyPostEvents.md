# AfdNotifyPostEvents

- ea: `0x140050be4`
- end: `0x140050eb2`
- name: `AfdNotifyPostEvents`
- size: `718`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008210`
- `0x14000a020`
- `0x14000c0d0`
- `0x14000d7f0`
- `0x14000de50`
- `0x14000ea50`
- `0x140012a88`
- `0x140013590`
- `0x140019810`
- `0x14001aabc`
- `0x14001adf0`
- `0x14001af00`
- `0x14001b800`
- `0x14001b938`
- `0x14001d524`
- `0x14002b8b0`
- `0x140037cf0`
- `0x140050eb8`

## callees

- `0x140035ad8`
- `0x140050b88`
- `0x140050be4`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050cab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050d65`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050e42`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050cab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050d65`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050e42`
- `ntoskrnl!IoCancelMiniCompletionPacket` at `0x140050cd0`
- `ntoskrnl!IoCancelMiniCompletionPacket` at `0x140050cd0`
- `ntoskrnl!IoSetIoCompletionEx3` at `0x140050dbd`
- `ntoskrnl!IoSetIoCompletionEx3` at `0x140050dbd`
- `ntoskrnl!ObfReferenceObject` at `0x140050d82`
- `ntoskrnl!ObfReferenceObject` at `0x140050d82`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050ceb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050d38`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050dd8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050e86`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050ceb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050d38`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050dd8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050e86`
- `ntoskrnl!ObfDereferenceObject` at `0x140050d21`
- `ntoskrnl!ObfDereferenceObject` at `0x140050d21`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050cb9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050d73`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050e50`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050cb9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050d73`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050e50`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050cf9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050d46`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050de6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050e94`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050cf9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050d46`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050de6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050e94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050e6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050e6f`

## pseudocode

```c
void __fastcall AfdNotifyPostEvents(__int64 a1, struct _KLOCK_QUEUE_HANDLE *a2, char a3)
{
  __int64 v3; // rbx
  __int16 v7; // r10
  void *v8; // r12
  __int16 v9; // r10
  __int16 v10; // r15
  char v11; // al
  unsigned __int16 v12; // si
  __int16 v13; // si
  __int16 v14; // r11
  unsigned __int16 v15; // ax
  KSPIN_LOCK *v16; // rsi
  KSPIN_LOCK *v17; // rcx
  KSPIN_LOCK *v18; // rcx
  KSPIN_LOCK *v19; // rcx
  __int64 v20; // [rsp+28h] [rbp-70h]
  int v21; // [rsp+38h] [rbp-60h]
  int v22; // [rsp+40h] [rbp-58h]

  v3 = *(_QWORD *)(a1 + 384);
  v7 = *(_WORD *)(v3 + 106);
  if ( (v7 & 2) == 0 )
  {
    v8 = *(void **)(v3 + 64);
    v9 = v7 | 2;
    *(_WORD *)(v3 + 106) = v9;
    if ( (v9 & 1) != 0 )
    {
      v16 = (KSPIN_LOCK *)(a1 + 56);
LABEL_39:
      *(_QWORD *)(a1 + 384) = 0;
      *(_WORD *)(v3 + 106) &= ~2u;
      if ( a3 )
        KeReleaseInStackQueuedSpinLockFromDpcLevel(a2);
      else
        KeReleaseInStackQueuedSpinLock(a2);
      AfdNotifyDestroyContext(v8);
      ExFreePoolWithTag((PVOID)v3, 0x4E646641u);
      if ( a3 )
        KeAcquireInStackQueuedSpinLockAtDpcLevel(v16, a2);
      else
        KeAcquireInStackQueuedSpinLock(v16, a2);
    }
    else
    {
      v10 = v9;
      while ( 1 )
      {
        v11 = *(_BYTE *)(v3 + 98);
        if ( (v11 & 4) != 0 )
        {
          v12 = 128;
        }
        else if ( (v11 & 2) != 0 )
        {
          v12 = 0;
        }
        else
        {
          v13 = AfdNotifyPollEventsToNotifyEvents(*(unsigned __int16 *)(v3 + 100));
          if ( (*(_BYTE *)(v3 + 99) & 8) != 0 )
            v13 = AfdNotifyPollEventsToNotifyEvents((unsigned __int16)(v14 & ~*(_WORD *)(v3 + 102)))
                | *(_WORD *)(v3 + 104) & v13;
          v12 = *(_WORD *)(v3 + 96) & v13;
        }
        *(_WORD *)(v3 + 102) = *(_WORD *)(v3 + 100);
        v15 = *(_WORD *)(v3 + 104);
        if ( v12 == v15 )
          break;
        if ( (v15 & v12) != 0 )
          goto LABEL_37;
        if ( v15 )
        {
          if ( a3 )
            KeReleaseInStackQueuedSpinLockFromDpcLevel(a2);
          else
            KeReleaseInStackQueuedSpinLock(a2);
          v16 = (KSPIN_LOCK *)(a1 + 56);
          if ( (unsigned __int8)IoCancelMiniCompletionPacket(*(_QWORD *)(v3 + 80), v3) )
          {
            ObfDereferenceObject(v8);
            v18 = (KSPIN_LOCK *)(a1 + 56);
            if ( a3 )
              KeAcquireInStackQueuedSpinLockAtDpcLevel(v18, a2);
            else
              KeAcquireInStackQueuedSpinLock(v18, a2);
            *(_WORD *)(v3 + 104) = 0;
          }
          else
          {
            v17 = (KSPIN_LOCK *)(a1 + 56);
            if ( a3 )
              KeAcquireInStackQueuedSpinLockAtDpcLevel(v17, a2);
            else
              KeAcquireInStackQueuedSpinLock(v17, a2);
            if ( *(_WORD *)(v3 + 104) )
            {
              *(_WORD *)(v3 + 106) &= ~2u;
              return;
            }
          }
        }
        else
        {
          *(_WORD *)(v3 + 104) = v12;
          if ( a3 )
            KeReleaseInStackQueuedSpinLockFromDpcLevel(a2);
          else
            KeReleaseInStackQueuedSpinLock(a2);
          ObfReferenceObject(v8);
          LOBYTE(v22) = AfdPriorityBoost;
          LOBYTE(v21) = 0;
          LOBYTE(v20) = 0;
          IoSetIoCompletionEx3(*(_QWORD *)(v3 + 80), *(_QWORD *)(v3 + 88), 0, 0, v12, v20, v3, v21, v22);
          v16 = (KSPIN_LOCK *)(a1 + 56);
          v19 = (KSPIN_LOCK *)(a1 + 56);
          if ( a3 )
            KeAcquireInStackQueuedSpinLockAtDpcLevel(v19, a2);
          else
            KeAcquireInStackQueuedSpinLock(v19, a2);
        }
        v9 = *(_WORD *)(v3 + 106);
        v10 = v9;
        if ( (v9 & 1) != 0 )
          goto LABEL_39;
      }
      if ( (*(_BYTE *)(v3 + 99) & 1) != 0 )
        v9 = v10 | 4;
LABEL_37:
      *(_WORD *)(v3 + 106) = v9 & 0xFFFD;
    }
  }
}

```

## disassembly

```asm
0x140050be4  push    rbx
0x140050be6  push    rbp
0x140050be7  push    rsi
0x140050be8  push    rdi
0x140050be9  push    r12
0x140050beb  push    r13
0x140050bed  push    r14
0x140050bef  push    r15
0x140050bf1  sub     rsp, 58h
0x140050bf5  mov     rbx, [rcx+180h]
0x140050bfc  mov     bpl, r8b
0x140050bff  mov     rdi, rdx
0x140050c02  mov     r14, rcx
0x140050c05  movzx   r10d, word ptr [rbx+6Ah]
0x140050c0a  test    r10b, 2
0x140050c0e  jnz     loc_140050EA0
0x140050c14  mov     r12, [rbx+40h]
0x140050c18  or      r10w, 2
0x140050c1d  xor     r13d, r13d
0x140050c20  mov     [rbx+6Ah], r10w
0x140050c25  test    r10b, 1
0x140050c29  jnz     loc_140050E26
0x140050c2f  movzx   r15d, r10w
0x140050c33  mov     al, [rbx+62h]
0x140050c36  test    al, 4
0x140050c38  jz      short loc_140050C41
0x140050c3a  mov     esi, 80h
0x140050c3f  jmp     short loc_140050C7C
0x140050c41  test    al, 2
0x140050c43  jz      short loc_140050C4A
0x140050c45  mov     esi, r13d
0x140050c48  jmp     short loc_140050C7C
0x140050c4a  movzx   r11d, word ptr [rbx+64h]
0x140050c4f  movzx   ecx, r11w
0x140050c53  call    AfdNotifyPollEventsToNotifyEvents
0x140050c58  test    byte ptr [rbx+63h], 8
0x140050c5c  movzx   esi, ax
0x140050c5f  jz      short loc_140050C78
0x140050c61  movzx   ecx, word ptr [rbx+66h]
0x140050c65  not     cx
0x140050c68  and     cx, r11w
0x140050c6c  call    AfdNotifyPollEventsToNotifyEvents
0x140050c71  and     si, [rbx+68h]
0x140050c75  or      si, ax
0x140050c78  and     si, [rbx+60h]
0x140050c7c  movzx   eax, word ptr [rbx+64h]
0x140050c80  mov     [rbx+66h], ax
0x140050c84  movzx   eax, word ptr [rbx+68h]
0x140050c88  cmp     si, ax
0x140050c8b  jz      loc_140050E07
0x140050c91  test    si, ax
0x140050c94  jnz     loc_140050E16
0x140050c9a  mov     rcx, rdi; LockHandle
0x140050c9d  test    ax, ax
0x140050ca0  jz      loc_140050D5C
0x140050ca6  test    bpl, bpl
0x140050ca9  jz      short loc_140050CB9
0x140050cab  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140050cb2  nop     dword ptr [rax+rax+00h]
0x140050cb7  jmp     short loc_140050CC5
0x140050cb9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140050cc0  nop     dword ptr [rax+rax+00h]
0x140050cc5  mov     rcx, [rbx+50h]
0x140050cc9  lea     rsi, [r14+38h]
0x140050ccd  mov     rdx, rbx
0x140050cd0  call    cs:__imp_IoCancelMiniCompletionPacket
0x140050cd7  nop     dword ptr [rax+rax+00h]
0x140050cdc  test    al, al
0x140050cde  jnz     short loc_140050D1E
0x140050ce0  mov     rdx, rdi; LockHandle
0x140050ce3  mov     rcx, rsi; SpinLock
0x140050ce6  test    bpl, bpl
0x140050ce9  jz      short loc_140050CF9
0x140050ceb  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140050cf2  nop     dword ptr [rax+rax+00h]
0x140050cf7  jmp     short loc_140050D05
0x140050cf9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140050d00  nop     dword ptr [rax+rax+00h]
0x140050d05  cmp     [rbx+68h], r13w
0x140050d0a  jz      loc_140050DF2
0x140050d10  mov     eax, 0FFFDh
0x140050d15  and     [rbx+6Ah], ax
0x140050d19  jmp     loc_140050EA0
0x140050d1e  mov     rcx, r12; Object
0x140050d21  call    cs:__imp_ObfDereferenceObject
0x140050d28  nop     dword ptr [rax+rax+00h]
0x140050d2d  mov     rdx, rdi; LockHandle
0x140050d30  mov     rcx, rsi; SpinLock
0x140050d33  test    bpl, bpl
0x140050d36  jz      short loc_140050D46
0x140050d38  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140050d3f  nop     dword ptr [rax+rax+00h]
0x140050d44  jmp     short loc_140050D52
0x140050d46  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140050d4d  nop     dword ptr [rax+rax+00h]
0x140050d52  mov     [rbx+68h], r13w
0x140050d57  jmp     loc_140050DF2
0x140050d5c  mov     [rbx+68h], si
0x140050d60  test    bpl, bpl
0x140050d63  jz      short loc_140050D73
0x140050d65  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140050d6c  nop     dword ptr [rax+rax+00h]
0x140050d71  jmp     short loc_140050D7F
0x140050d73  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140050d7a  nop     dword ptr [rax+rax+00h]
0x140050d7f  mov     rcx, r12; Object
0x140050d82  call    cs:__imp_ObfReferenceObject
0x140050d89  nop     dword ptr [rax+rax+00h]
0x140050d8e  mov     al, cs:AfdPriorityBoost
0x140050d94  xor     r9d, r9d
0x140050d97  mov     rdx, [rbx+58h]
0x140050d9b  xor     r8d, r8d
0x140050d9e  mov     byte ptr [rsp+98h+var_58], al
0x140050da2  mov     [rsp+98h+var_60], r13b
0x140050da7  mov     [rsp+98h+var_68], rbx
0x140050dac  movzx   ecx, si
0x140050daf  mov     byte ptr [rsp+98h+var_70], r13b
0x140050db4  mov     [rsp+98h+var_78], rcx
0x140050db9  mov     rcx, [rbx+50h]
0x140050dbd  call    cs:__imp_IoSetIoCompletionEx3
0x140050dc4  nop     dword ptr [rax+rax+00h]
0x140050dc9  lea     rsi, [r14+38h]
0x140050dcd  mov     rdx, rdi; LockHandle
0x140050dd0  mov     rcx, rsi; SpinLock
0x140050dd3  test    bpl, bpl
0x140050dd6  jz      short loc_140050DE6
0x140050dd8  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140050ddf  nop     dword ptr [rax+rax+00h]
0x140050de4  jmp     short loc_140050DF2
0x140050de6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140050ded  nop     dword ptr [rax+rax+00h]
0x140050df2  movzx   r10d, word ptr [rbx+6Ah]
0x140050df7  movzx   r15d, r10w
0x140050dfb  test    r10b, 1
0x140050dff  jz      loc_140050C33
0x140050e05  jmp     short loc_140050E2A
0x140050e07  test    byte ptr [rbx+63h], 1
0x140050e0b  jz      short loc_140050E16
0x140050e0d  movzx   r10d, r15w
0x140050e11  or      r10w, 4
0x140050e16  mov     eax, 0FFFDh
0x140050e1b  and     r10w, ax
0x140050e1f  mov     [rbx+6Ah], r10w
0x140050e24  jmp     short loc_140050EA0
0x140050e26  lea     rsi, [rcx+38h]
0x140050e2a  mov     eax, 0FFFDh
0x140050e2f  mov     [r14+180h], r13
0x140050e36  and     [rbx+6Ah], ax
0x140050e3a  mov     rcx, rdi; LockHandle
0x140050e3d  test    bpl, bpl
0x140050e40  jz      short loc_140050E50
0x140050e42  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140050e49  nop     dword ptr [rax+rax+00h]
0x140050e4e  jmp     short loc_140050E5C
0x140050e50  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140050e57  nop     dword ptr [rax+rax+00h]
0x140050e5c  mov     rdx, rbx
0x140050e5f  mov     rcx, r12; Object
0x140050e62  call    AfdNotifyDestroyContext
0x140050e67  mov     edx, 4E646641h; Tag
0x140050e6c  mov     rcx, rbx; P
0x140050e6f  call    cs:__imp_ExFreePoolWithTag
0x140050e76  nop     dword ptr [rax+rax+00h]
0x140050e7b  mov     rdx, rdi; LockHandle
0x140050e7e  mov     rcx, rsi; SpinLock
0x140050e81  test    bpl, bpl
0x140050e84  jz      short loc_140050E94
0x140050e86  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140050e8d  nop     dword ptr [rax+rax+00h]
0x140050e92  jmp     short loc_140050EA0
0x140050e94  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140050e9b  nop     dword ptr [rax+rax+00h]
0x140050ea0  add     rsp, 58h
0x140050ea4  pop     r15
0x140050ea6  pop     r14
0x140050ea8  pop     r13
0x140050eaa  pop     r12
0x140050eac  pop     rdi
0x140050ead  pop     rsi
0x140050eae  pop     rbp
0x140050eaf  pop     rbx
0x140050eb0  retn
```
