# USBSTOR_CheckRequestTimeOut

- ea: `0x140009f90`
- end: `0x14000a084`
- name: `USBSTOR_CheckRequestTimeOut`
- size: `244`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400094b0`
- `0x140009860`
- `0x140009cb0`
- `0x14000f640`
- `0x1400124f0`

## callees

- `0x140003630`
- `0x140004910`
- `0x140009f90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000a071`
- `ntoskrnl!KeSetEvent` at `0x14000a071`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009fc6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009fc6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ff1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a023`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ff1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a023`

## pseudocode

```c
char __fastcall USBSTOR_CheckRequestTimeOut(_QWORD *Object, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v4; // rbx
  __int64 v10; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  v4 = Object[8];
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 144), &LockHandle);
  *(_DWORD *)(v4 + 128) &= ~2u;
  if ( (*(_DWORD *)(v4 + 128) & 8) != 0 )
  {
    USBSTOR_LogEntry(827609667, (__int64)Object, a2, a3);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v10 = *(_QWORD *)(v4 + 1168);
    *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL) = v10;
    *(_QWORD *)(a2 + 56) = 0;
    *(_DWORD *)(a2 + 48) = -1073741643;
    *(_BYTE *)(v10 + 3) = 9;
    USBSTOR_TranslateCDBComplete(Object, a2, v10);
    *a4 = -1073741802;
    KeSetEvent((PRKEVENT)(v4 + 336), 0, 0);
    return 1;
  }
  else
  {
    *(_QWORD *)(v4 + 328) = 0;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x140009f90  push    rbx
0x140009f92  push    rbp
0x140009f93  push    rsi
0x140009f94  push    rdi
0x140009f95  push    r14
0x140009f97  sub     rsp, 40h
0x140009f9b  mov     rbx, [rcx+40h]
0x140009f9f  mov     rsi, rdx
0x140009fa2  mov     rdi, rcx
0x140009fa5  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140009faa  xorps   xmm0, xmm0
0x140009fad  xor     eax, eax
0x140009faf  mov     r14, r9
0x140009fb2  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x140009fb7  lea     rcx, [rbx+90h]; SpinLock
0x140009fbe  mov     rbp, r8
0x140009fc1  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140009fc6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009fcd  nop     dword ptr [rax+rax+00h]
0x140009fd2  and     dword ptr [rbx+80h], 0FFFFFFFDh
0x140009fd9  mov     eax, [rbx+80h]
0x140009fdf  test    al, 8
0x140009fe1  jnz     short loc_14000A00B
0x140009fe3  xor     eax, eax
0x140009fe5  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140009fea  mov     [rbx+148h], rax
0x140009ff1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009ff8  nop     dword ptr [rax+rax+00h]
0x140009ffd  xor     al, al
0x140009fff  add     rsp, 40h
0x14000a003  pop     r14
0x14000a005  pop     rdi
0x14000a006  pop     rsi
0x14000a007  pop     rbp
0x14000a008  pop     rbx
0x14000a009  retn
0x14000a00b  mov     r9, rbp
0x14000a00e  mov     r8, rsi
0x14000a011  mov     rdx, rdi
0x14000a014  mov     ecx, 31545243h
0x14000a019  call    USBSTOR_LogEntry
0x14000a01e  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14000a023  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000a02a  nop     dword ptr [rax+rax+00h]
0x14000a02f  mov     r8, [rbx+490h]
0x14000a036  mov     rdx, rsi
0x14000a039  mov     rax, [rsi+0B8h]
0x14000a040  mov     rcx, rdi; Object
0x14000a043  mov     [rax+8], r8
0x14000a047  xor     eax, eax
0x14000a049  mov     [rsi+38h], rax
0x14000a04d  mov     dword ptr [rsi+30h], 0C00000B5h
0x14000a054  mov     byte ptr [r8+3], 9
0x14000a059  call    USBSTOR_TranslateCDBComplete
0x14000a05e  lea     rcx, [rbx+150h]; Event
0x14000a065  mov     dword ptr [r14], 0C0000016h
0x14000a06c  xor     r8d, r8d; Wait
0x14000a06f  xor     edx, edx; Increment
0x14000a071  call    cs:__imp_KeSetEvent
0x14000a078  nop     dword ptr [rax+rax+00h]
0x14000a07d  mov     al, 1
0x14000a07f  jmp     loc_140009FFF
```
