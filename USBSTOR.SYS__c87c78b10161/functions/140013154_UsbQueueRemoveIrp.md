# UsbQueueRemoveIrp

- ea: `0x140013154`
- end: `0x140013229`
- name: `UsbQueueRemoveIrp`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140012f90`

## callees

- `0x14000f9f0`
- `0x1400105e8`
- `0x140010664`
- `0x140013154`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400131b9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400131b9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400131d8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400131d8`

## pseudocode

```c
char __fastcall UsbQueueRemoveIrp(__int64 a1, __int64 a2)
{
  char v4; // bl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 288), &LockHandle);
  v4 = UsbRemoveIrp(a1, a2);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x140013154  mov     [rsp+arg_0], rbx
0x140013159  mov     [rsp+arg_8], rsi
0x14001315e  push    rdi
0x14001315f  sub     rsp, 40h
0x140013163  xorps   xmm0, xmm0
0x140013166  xor     eax, eax
0x140013168  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14001316d  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140013172  mov     rdi, rdx
0x140013175  mov     rbx, rcx
0x140013178  mov     rcx, cs:WPP_GLOBAL_Control
0x14001317f  lea     rsi, WPP_GLOBAL_Control
0x140013186  cmp     rcx, rsi
0x140013189  jz      short loc_1400131AD
0x14001318b  mov     eax, [rcx+2Ch]
0x14001318e  test    al, 20h
0x140013190  jz      short loc_1400131AD
0x140013192  cmp     byte ptr [rcx+29h], 4
0x140013196  jb      short loc_1400131AD
0x140013198  mov     rcx, [rcx+18h]
0x14001319c  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x1400131a3  mov     edx, 1Bh
0x1400131a8  call    WPP_SF_
0x1400131ad  lea     rcx, [rbx+120h]; SpinLock
0x1400131b4  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x1400131b9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400131c0  nop     dword ptr [rax+rax+00h]
0x1400131c5  mov     rdx, rdi
0x1400131c8  mov     rcx, rbx
0x1400131cb  call    UsbRemoveIrp
0x1400131d0  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x1400131d5  movzx   ebx, al
0x1400131d8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400131df  nop     dword ptr [rax+rax+00h]
0x1400131e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400131eb  cmp     rcx, rsi
0x1400131ee  jz      short loc_140013216
0x1400131f0  mov     edx, [rcx+2Ch]
0x1400131f3  test    dl, 20h
0x1400131f6  jz      short loc_140013216
0x1400131f8  cmp     byte ptr [rcx+29h], 4
0x1400131fc  jb      short loc_140013216
0x1400131fe  mov     rcx, [rcx+18h]
0x140013202  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x140013209  mov     r9d, ebx
0x14001320c  mov     edx, 1Ch
0x140013211  call    WPP_SF_d
0x140013216  mov     rsi, [rsp+48h+arg_8]
0x14001321b  mov     al, bl
0x14001321d  mov     rbx, [rsp+48h+arg_0]
0x140013222  add     rsp, 40h
0x140013226  pop     rdi
0x140013227  retn
```
