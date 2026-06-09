# AfdNotifyPostEvents

- ea: `0x140050c84`
- end: `0x140050f52`
- name: `AfdNotifyPostEvents`
- size: `718`
- prototype: `void __fastcall(__int64, struct _KLOCK_QUEUE_HANDLE *, char)`
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
- `0x140037d10`
- `0x140050f58`

## callees

- `0x140035af8`
- `0x140050c28`
- `0x140050c84`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050d4b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050e05`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050ee2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050d4b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050e05`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140050ee2`
- `ntoskrnl!IoCancelMiniCompletionPacket` at `0x140050d70`
- `ntoskrnl!IoCancelMiniCompletionPacket` at `0x140050d70`
- `ntoskrnl!IoSetIoCompletionEx3` at `0x140050e5d`
- `ntoskrnl!IoSetIoCompletionEx3` at `0x140050e5d`
- `ntoskrnl!ObfReferenceObject` at `0x140050e22`
- `ntoskrnl!ObfReferenceObject` at `0x140050e22`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050d8b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050dd8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050e78`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050f26`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050d8b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050dd8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050e78`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140050f26`
- `ntoskrnl!ObfDereferenceObject` at `0x140050dc1`
- `ntoskrnl!ObfDereferenceObject` at `0x140050dc1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050d59`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050e13`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050ef0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050d59`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050e13`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050ef0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050d99`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050de6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050e86`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050f34`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050d99`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050de6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050e86`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050f34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050f0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050f0f`

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
  int v20; // [rsp+28h] [rbp-70h]
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
      AfdNotifyDestroyContext(v8, v3);
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
0x140050c84  push    rbx
0x140050c86  push    rbp
0x140050c87  push    rsi
0x140050c88  push    rdi
0x140050c89  push    r12
0x140050c8b  push    r13
0x140050c8d  push    r14
0x140050c8f  push    r15
0x140050c91  sub     rsp, 58h
0x140050c95  mov     rbx, [rcx+180h]
0x140050c9c  mov     bpl, r8b
0x140050c9f  mov     rdi, rdx
0x140050ca2  mov     r14, rcx
0x140050ca5  movzx   r10d, word ptr [rbx+6Ah]
0x140050caa  test    r10b, 2
0x140050cae  jnz     loc_140050F40
0x140050cb4  mov     r12, [rbx+40h]
0x140050cb8  or      r10w, 2
0x140050cbd  xor     r13d, r13d
0x140050cc0  mov     [rbx+6Ah], r10w
0x140050cc5  test    r10b, 1
0x140050cc9  jnz     loc_140050EC6
0x140050ccf  movzx   r15d, r10w
0x140050cd3  mov     al, [rbx+62h]
0x140050cd6  test    al, 4
0x140050cd8  jz      short loc_140050CE1
0x140050cda  mov     esi, 80h
0x140050cdf  jmp     short loc_140050D1C
0x140050ce1  test    al, 2
0x140050ce3  jz      short loc_140050CEA
0x140050ce5  mov     esi, r13d
0x140050ce8  jmp     short loc_140050D1C
0x140050cea  movzx   r11d, word ptr [rbx+64h]
0x140050cef  movzx   ecx, r11w
0x140050cf3  call    AfdNotifyPollEventsToNotifyEvents
0x140050cf8  test    byte ptr [rbx+63h], 8
0x140050cfc  movzx   esi, ax
0x140050cff  jz      short loc_140050D18
0x140050d01  movzx   ecx, word ptr [rbx+66h]
0x140050d05  not     cx
0x140050d08  and     cx, r11w
0x140050d0c  call    AfdNotifyPollEventsToNotifyEvents
0x140050d11  and     si, [rbx+68h]
0x140050d15  or      si, ax
0x140050d18  and     si, [rbx+60h]
0x140050d1c  movzx   eax, word ptr [rbx+64h]
0x140050d20  mov     [rbx+66h], ax
0x140050d24  movzx   eax, word ptr [rbx+68h]
0x140050d28  cmp     si, ax
0x140050d2b  jz      loc_140050EA7
0x140050d31  test    si, ax
0x140050d34  jnz     loc_140050EB6
0x140050d3a  mov     rcx, rdi; LockHandle
0x140050d3d  test    ax, ax
0x140050d40  jz      loc_140050DFC
0x140050d46  test    bpl, bpl
0x140050d49  jz      short loc_140050D59
0x140050d4b  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140050d52  nop     dword ptr [rax+rax+00h]
0x140050d57  jmp     short loc_140050D65
0x140050d59  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140050d60  nop     dword ptr [rax+rax+00h]
0x140050d65  mov     rcx, [rbx+50h]
0x140050d69  lea     rsi, [r14+38h]
0x140050d6d  mov     rdx, rbx
0x140050d70  call    cs:__imp_IoCancelMiniCompletionPacket
0x140050d77  nop     dword ptr [rax+rax+00h]
0x140050d7c  test    al, al
0x140050d7e  jnz     short loc_140050DBE
0x140050d80  mov     rdx, rdi; LockHandle
0x140050d83  mov     rcx, rsi; SpinLock
0x140050d86  test    bpl, bpl
0x140050d89  jz      short loc_140050D99
0x140050d8b  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140050d92  nop     dword ptr [rax+rax+00h]
0x140050d97  jmp     short loc_140050DA5
0x140050d99  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140050da0  nop     dword ptr [rax+rax+00h]
0x140050da5  cmp     [rbx+68h], r13w
0x140050daa  jz      loc_140050E92
0x140050db0  mov     eax, 0FFFDh
0x140050db5  and     [rbx+6Ah], ax
0x140050db9  jmp     loc_140050F40
0x140050dbe  mov     rcx, r12; Object
0x140050dc1  call    cs:__imp_ObfDereferenceObject
0x140050dc8  nop     dword ptr [rax+rax+00h]
0x140050dcd  mov     rdx, rdi; LockHandle
0x140050dd0  mov     rcx, rsi; SpinLock
0x140050dd3  test    bpl, bpl
0x140050dd6  jz      short loc_140050DE6
0x140050dd8  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140050ddf  nop     dword ptr [rax+rax+00h]
0x140050de4  jmp     short loc_140050DF2
0x140050de6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140050ded  nop     dword ptr [rax+rax+00h]
0x140050df2  mov     [rbx+68h], r13w
0x140050df7  jmp     loc_140050E92
0x140050dfc  mov     [rbx+68h], si
0x140050e00  test    bpl, bpl
0x140050e03  jz      short loc_140050E13
0x140050e05  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140050e0c  nop     dword ptr [rax+rax+00h]
0x140050e11  jmp     short loc_140050E1F
0x140050e13  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140050e1a  nop     dword ptr [rax+rax+00h]
0x140050e1f  mov     rcx, r12; Object
0x140050e22  call    cs:__imp_ObfReferenceObject
0x140050e29  nop     dword ptr [rax+rax+00h]
0x140050e2e  mov     al, cs:AfdPriorityBoost
0x140050e34  xor     r9d, r9d
0x140050e37  mov     rdx, [rbx+58h]
0x140050e3b  xor     r8d, r8d
0x140050e3e  mov     byte ptr [rsp+98h+var_58], al
0x140050e42  mov     [rsp+98h+var_60], r13b
0x140050e47  mov     [rsp+98h+var_68], rbx
0x140050e4c  movzx   ecx, si
0x140050e4f  mov     [rsp+98h+var_70], r13b
0x140050e54  mov     [rsp+98h+var_78], rcx
0x140050e59  mov     rcx, [rbx+50h]
0x140050e5d  call    cs:__imp_IoSetIoCompletionEx3
0x140050e64  nop     dword ptr [rax+rax+00h]
0x140050e69  lea     rsi, [r14+38h]
0x140050e6d  mov     rdx, rdi; LockHandle
0x140050e70  mov     rcx, rsi; SpinLock
0x140050e73  test    bpl, bpl
0x140050e76  jz      short loc_140050E86
0x140050e78  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140050e7f  nop     dword ptr [rax+rax+00h]
0x140050e84  jmp     short loc_140050E92
0x140050e86  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140050e8d  nop     dword ptr [rax+rax+00h]
0x140050e92  movzx   r10d, word ptr [rbx+6Ah]
0x140050e97  movzx   r15d, r10w
0x140050e9b  test    r10b, 1
0x140050e9f  jz      loc_140050CD3
0x140050ea5  jmp     short loc_140050ECA
0x140050ea7  test    byte ptr [rbx+63h], 1
0x140050eab  jz      short loc_140050EB6
0x140050ead  movzx   r10d, r15w
0x140050eb1  or      r10w, 4
0x140050eb6  mov     eax, 0FFFDh
0x140050ebb  and     r10w, ax
0x140050ebf  mov     [rbx+6Ah], r10w
0x140050ec4  jmp     short loc_140050F40
0x140050ec6  lea     rsi, [rcx+38h]
0x140050eca  mov     eax, 0FFFDh
0x140050ecf  mov     [r14+180h], r13
0x140050ed6  and     [rbx+6Ah], ax
0x140050eda  mov     rcx, rdi; LockHandle
0x140050edd  test    bpl, bpl
0x140050ee0  jz      short loc_140050EF0
0x140050ee2  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140050ee9  nop     dword ptr [rax+rax+00h]
0x140050eee  jmp     short loc_140050EFC
0x140050ef0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140050ef7  nop     dword ptr [rax+rax+00h]
0x140050efc  mov     rdx, rbx
0x140050eff  mov     rcx, r12; Object
0x140050f02  call    AfdNotifyDestroyContext
0x140050f07  mov     edx, 4E646641h; Tag
0x140050f0c  mov     rcx, rbx; P
0x140050f0f  call    cs:__imp_ExFreePoolWithTag
0x140050f16  nop     dword ptr [rax+rax+00h]
0x140050f1b  mov     rdx, rdi; LockHandle
0x140050f1e  mov     rcx, rsi; SpinLock
0x140050f21  test    bpl, bpl
0x140050f24  jz      short loc_140050F34
0x140050f26  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140050f2d  nop     dword ptr [rax+rax+00h]
0x140050f32  jmp     short loc_140050F40
0x140050f34  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140050f3b  nop     dword ptr [rax+rax+00h]
0x140050f40  add     rsp, 58h
0x140050f44  pop     r15
0x140050f46  pop     r14
0x140050f48  pop     r13
0x140050f4a  pop     r12
0x140050f4c  pop     rdi
0x140050f4d  pop     rsi
0x140050f4e  pop     rbp
0x140050f4f  pop     rbx
0x140050f50  retn
```
