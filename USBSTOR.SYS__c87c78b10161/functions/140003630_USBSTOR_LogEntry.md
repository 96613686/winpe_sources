# USBSTOR_LogEntry

- ea: `0x140003630`
- end: `0x1400036e1`
- name: `USBSTOR_LogEntry`
- size: `177`
- prototype: ``
- caller_count: `88`
- callee_count: `1`
- tags: ``

## callers

- `0x140001008`
- `0x140001950`
- `0x140001de0`
- `0x1400023b0`
- `0x140002a70`
- `0x140002fd0`
- `0x140003e10`
- `0x140004910`
- `0x140004ed0`
- `0x140006040`
- `0x140006ff0`
- `0x140007900`
- `0x1400084c0`
- `0x1400090e0`
- `0x1400094b0`
- `0x140009860`
- `0x140009cb0`
- `0x140009f90`
- `0x14000a3f4`
- `0x14000a500`
- `0x14000b0bc`
- `0x14000c120`
- `0x14000c830`
- `0x14000c96c`
- `0x14000cd00`
- `0x14000ced4`
- `0x14000d1f0`
- `0x14000d7e4`
- `0x14000d8cc`
- `0x14000dd1c`
- `0x14000df00`
- `0x14000dfac`
- `0x14000e060`
- `0x14000e190`
- `0x14000e7b4`
- `0x14000e8bc`
- `0x14000ea94`
- `0x14000ec40`
- `0x14000f280`
- `0x14000f320`
- `0x14000f640`
- `0x14000fafc`
- `0x14000fc80`
- `0x14000fd74`
- `0x1400103a4`
- `0x140010960`
- `0x1400109e0`
- `0x140010ad0`
- `0x140010b50`
- `0x1400116a0`

## callees

- `0x140003630`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003668`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003668`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400036be`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400036be`

## pseudocode

```c
void __fastcall USBSTOR_LogEntry(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = a1;
    *(_QWORD *)(qword_14001A190 + 8) = a2;
    *(_QWORD *)(qword_14001A190 + 16) = a3;
    *(_QWORD *)(qword_14001A190 + 24) = a4;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v8 = qword_14001A198 - 32;
    else
      v8 = qword_14001A190 - 32;
    qword_14001A190 = v8;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
}

```

## disassembly

```asm
0x140003630  push    rbx
0x140003632  push    rbp
0x140003633  push    rsi
0x140003634  push    rdi
0x140003635  sub     rsp, 48h
0x140003639  xor     eax, eax
0x14000363b  xorps   xmm0, xmm0
0x14000363e  cmp     cs:P, rax
0x140003645  mov     rdi, r9
0x140003648  mov     rsi, r8
0x14000364b  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x140003650  mov     rbp, rdx
0x140003653  mov     ebx, ecx
0x140003655  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14000365a  jz      short loc_1400036CA
0x14000365c  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140003661  lea     rcx, SpinLock; SpinLock
0x140003668  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000366f  nop     dword ptr [rax+rax+00h]
0x140003674  mov     rax, cs:qword_14001A190
0x14000367b  mov     [rax], ebx
0x14000367d  mov     rax, cs:qword_14001A190
0x140003684  mov     [rax+8], rbp
0x140003688  mov     rax, cs:qword_14001A190
0x14000368f  mov     [rax+10h], rsi
0x140003693  mov     rax, cs:qword_14001A190
0x14000369a  mov     [rax+18h], rdi
0x14000369e  mov     rax, cs:qword_14001A190
0x1400036a5  cmp     rax, cs:P
0x1400036ac  jbe     short loc_1400036D4
0x1400036ae  sub     rax, 20h ; ' '
0x1400036b2  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x1400036b7  mov     cs:qword_14001A190, rax
0x1400036be  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400036c5  nop     dword ptr [rax+rax+00h]
0x1400036ca  add     rsp, 48h
0x1400036ce  pop     rdi
0x1400036cf  pop     rsi
0x1400036d0  pop     rbp
0x1400036d1  pop     rbx
0x1400036d2  retn
0x1400036d4  mov     rax, cs:qword_14001A198
0x1400036db  add     rax, 0FFFFFFFFFFFFFFE0h
0x1400036df  jmp     short loc_1400036B2
```
