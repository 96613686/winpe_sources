# UsbQueueFreeze

- ea: `0x14000cba8`
- end: `0x14000cc67`
- name: `UsbQueueFreeze`
- size: `191`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004910`
- `0x140004ed0`
- `0x140020c90`

## callees

- `0x14000cba8`
- `0x140010664`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000cbe3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000cbe3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000cbfb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000cbfb`

## pseudocode

```c
void __fastcall UsbQueueFreeze(__int64 a1)
{
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, (__int64)WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 288), &LockHandle);
  *(_BYTE *)(a1 + 304) = 1;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xBu, (__int64)WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
}

```

## disassembly

```asm
0x14000cba8  mov     [rsp+arg_0], rbx
0x14000cbad  push    rdi
0x14000cbae  sub     rsp, 40h
0x14000cbb2  xorps   xmm0, xmm0
0x14000cbb5  xor     eax, eax
0x14000cbb7  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14000cbbc  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x14000cbc1  mov     rbx, rcx
0x14000cbc4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbcb  lea     rdi, WPP_GLOBAL_Control
0x14000cbd2  cmp     rcx, rdi
0x14000cbd5  jnz     short loc_14000CC1F
0x14000cbd7  lea     rcx, [rbx+120h]; SpinLock
0x14000cbde  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14000cbe3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000cbea  nop     dword ptr [rax+rax+00h]
0x14000cbef  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14000cbf4  mov     byte ptr [rbx+130h], 1
0x14000cbfb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000cc02  nop     dword ptr [rax+rax+00h]
0x14000cc07  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc0e  cmp     rcx, rdi
0x14000cc11  jnz     short loc_14000CC43
0x14000cc13  mov     rbx, [rsp+48h+arg_0]
0x14000cc18  add     rsp, 40h
0x14000cc1c  pop     rdi
0x14000cc1d  retn
0x14000cc1f  mov     eax, [rcx+2Ch]
0x14000cc22  test    al, 20h
0x14000cc24  jz      short loc_14000CBD7
0x14000cc26  cmp     byte ptr [rcx+29h], 4
0x14000cc2a  jb      short loc_14000CBD7
0x14000cc2c  mov     rcx, [rcx+18h]
0x14000cc30  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000cc37  mov     edx, 0Ah
0x14000cc3c  call    WPP_SF_
0x14000cc41  jmp     short loc_14000CBD7
0x14000cc43  mov     eax, [rcx+2Ch]
0x14000cc46  test    al, 20h
0x14000cc48  jz      short loc_14000CC13
0x14000cc4a  cmp     byte ptr [rcx+29h], 4
0x14000cc4e  jb      short loc_14000CC13
0x14000cc50  mov     rcx, [rcx+18h]
0x14000cc54  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000cc5b  mov     edx, 0Bh
0x14000cc60  call    WPP_SF_
0x14000cc65  jmp     short loc_14000CC13
```
