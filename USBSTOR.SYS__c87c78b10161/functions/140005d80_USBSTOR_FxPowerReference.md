# USBSTOR_FxPowerReference

- ea: `0x140005d80`
- end: `0x140005e42`
- name: `USBSTOR_FxPowerReference`
- size: `194`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004910`
- `0x140004ed0`
- `0x140006ff0`
- `0x14000f39c`
- `0x140011900`

## callees

- `0x140005d80`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x140005dcd`
- `ntoskrnl!PoFxIdleComponent` at `0x140005dcd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140005dff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140005dff`
- `ntoskrnl!PoFxActivateComponent` at `0x140005db8`
- `ntoskrnl!PoFxActivateComponent` at `0x140005db8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005e2a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005e2a`

## pseudocode

```c
void __fastcall USBSTOR_FxPowerReference(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v3 = *(_QWORD *)(a1 + 1968);
  if ( v3 && (*(_DWORD *)(a2 + 12) & 0x100800) == 0 )
  {
    if ( a3 )
    {
      PoFxActivateComponent(v3, 0, 0);
      *(_DWORD *)(a2 + 12) |= 0x2000000u;
    }
    else
    {
      PoFxIdleComponent(v3, 0, 0);
      *(_DWORD *)(a2 + 12) &= ~0x2000000u;
    }
    v6 = *(unsigned __int8 *)(a2 + 72);
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock(&qword_14001A1C8, &LockHandle);
    v7 = 32LL * v6;
    if ( a3 )
      ++*(_DWORD *)((char *)qword_14001A1B8 + v7);
    else
      --*(_DWORD *)((char *)qword_14001A1B8 + v7);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
}

```

## disassembly

```asm
0x140005d80  mov     [rsp+arg_0], rbx
0x140005d85  push    rdi
0x140005d86  sub     rsp, 40h
0x140005d8a  mov     rcx, [rcx+7B0h]
0x140005d91  movzx   edi, r8b
0x140005d95  mov     rbx, rdx
0x140005d98  test    rcx, rcx
0x140005d9b  jz      loc_140005E36
0x140005da1  test    dword ptr [rdx+0Ch], 100800h
0x140005da8  jnz     loc_140005E36
0x140005dae  xor     r8d, r8d
0x140005db1  xor     edx, edx
0x140005db3  test    dil, dil
0x140005db6  jz      short loc_140005DCD
0x140005db8  call    cs:__imp_PoFxActivateComponent
0x140005dbf  nop     dword ptr [rax+rax+00h]
0x140005dc4  or      dword ptr [rbx+0Ch], 2000000h
0x140005dcb  jmp     short loc_140005DE0
0x140005dcd  call    cs:__imp_PoFxIdleComponent
0x140005dd4  nop     dword ptr [rax+rax+00h]
0x140005dd9  and     dword ptr [rbx+0Ch], 0FDFFFFFFh
0x140005de0  movzx   ebx, byte ptr [rbx+48h]
0x140005de4  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140005de9  xorps   xmm0, xmm0
0x140005dec  lea     rcx, qword_14001A1C8; SpinLock
0x140005df3  xor     eax, eax
0x140005df5  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140005dfa  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140005dff  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140005e06  nop     dword ptr [rax+rax+00h]
0x140005e0b  mov     rax, cs:qword_14001A1B8
0x140005e12  mov     ecx, ebx
0x140005e14  shl     rcx, 5
0x140005e18  test    dil, dil
0x140005e1b  jz      short loc_140005E22
0x140005e1d  inc     dword ptr [rcx+rax]
0x140005e20  jmp     short loc_140005E25
0x140005e22  dec     dword ptr [rcx+rax]
0x140005e25  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140005e2a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140005e31  nop     dword ptr [rax+rax+00h]
0x140005e36  mov     rbx, [rsp+48h+arg_0]
0x140005e3b  add     rsp, 40h
0x140005e3f  pop     rdi
0x140005e40  retn
```
