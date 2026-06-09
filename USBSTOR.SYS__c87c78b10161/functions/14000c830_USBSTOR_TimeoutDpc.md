# USBSTOR_TimeoutDpc

- ea: `0x14000c830`
- end: `0x14000c965`
- name: `USBSTOR_TimeoutDpc`
- size: `309`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003630`
- `0x14000c830`
- `0x14000ca68`
- `0x140010664`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000c863`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000c863`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000c897`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000c897`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000c8cf`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000c8cf`

## pseudocode

```c
void __fastcall USBSTOR_TimeoutDpc(
        struct _KDPC *Dpc,
        _QWORD *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 v4; // rbx
  char v6; // di
  int v7; // eax
  int v8; // eax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  v4 = DeferredContext[8];
  memset(&LockHandle, 0, sizeof(LockHandle));
  v6 = 0;
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 144), &LockHandle);
  v7 = *(_DWORD *)(v4 + 128);
  if ( (v7 & 8) == 0 )
  {
    if ( (v7 & 2) != 0 )
    {
      v8 = v7 | 8;
      v6 = 1;
LABEL_6:
      *(_DWORD *)(v4 + 128) = v8;
      goto LABEL_7;
    }
    if ( (v7 & 0x20) != 0 )
    {
      v8 = v7 | 0x40;
      goto LABEL_6;
    }
  }
LABEL_7:
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  if ( v6 && IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 1832), USBSTOR_ResetDeviceWorkItem, File, 1u, 0x20u) >= 0 )
  {
    USBSTOR_LogEntry(1380796756, DeferredContext, 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 171, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    USBSTOR_QueueWorkItem(
      DeferredContext,
      *(PLIST_ENTRY *)(v4 + 368),
      (PIO_WORKITEM_ROUTINE_EX)USBSTOR_ResetDeviceWorkItem,
      0,
      *(_BYTE *)(v4 + 1876) == 0);
  }
}

```

## disassembly

```asm
0x14000c830  mov     r11, rsp
0x14000c833  mov     [r11+8], rbx
0x14000c837  mov     [r11+10h], rsi
0x14000c83b  push    rdi
0x14000c83c  sub     rsp, 50h
0x14000c840  mov     rbx, [rdx+40h]
0x14000c844  xorps   xmm0, xmm0
0x14000c847  mov     rsi, rdx
0x14000c84a  xor     eax, eax
0x14000c84c  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14000c851  lea     rdx, [r11-28h]; LockHandle
0x14000c855  mov     [r11-18h], rax
0x14000c859  lea     rcx, [rbx+90h]; SpinLock
0x14000c860  xor     dil, dil
0x14000c863  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000c86a  nop     dword ptr [rax+rax+00h]
0x14000c86f  mov     eax, [rbx+80h]
0x14000c875  test    al, 8
0x14000c877  jnz     short loc_14000C892
0x14000c879  test    al, 2
0x14000c87b  jz      short loc_14000C885
0x14000c87d  or      eax, 8
0x14000c880  mov     dil, 1
0x14000c883  jmp     short loc_14000C88C
0x14000c885  test    al, 20h
0x14000c887  jz      short loc_14000C892
0x14000c889  or      eax, 40h
0x14000c88c  mov     [rbx+80h], eax
0x14000c892  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14000c897  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000c89e  nop     dword ptr [rax+rax+00h]
0x14000c8a3  test    dil, dil
0x14000c8a6  jz      loc_14000C954
0x14000c8ac  lea     rcx, [rbx+728h]; RemoveLock
0x14000c8b3  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x14000c8bb  mov     r9d, 1; Line
0x14000c8c1  lea     r8, File; File
0x14000c8c8  lea     rdx, USBSTOR_ResetDeviceWorkItem; Tag
0x14000c8cf  call    cs:__imp_IoAcquireRemoveLockEx
0x14000c8d6  nop     dword ptr [rax+rax+00h]
0x14000c8db  test    eax, eax
0x14000c8dd  js      short loc_14000C954
0x14000c8df  xor     r9d, r9d
0x14000c8e2  xor     r8d, r8d
0x14000c8e5  mov     rdx, rsi
0x14000c8e8  mov     ecx, 524D4954h
0x14000c8ed  call    USBSTOR_LogEntry
0x14000c8f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c8f9  lea     rax, WPP_GLOBAL_Control
0x14000c900  cmp     rcx, rax
0x14000c903  jz      short loc_14000C927
0x14000c905  mov     eax, [rcx+2Ch]
0x14000c908  test    al, 1
0x14000c90a  jz      short loc_14000C927
0x14000c90c  cmp     byte ptr [rcx+29h], 5
0x14000c910  jb      short loc_14000C927
0x14000c912  mov     rcx, [rcx+18h]
0x14000c916  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000c91d  mov     edx, 0ABh
0x14000c922  call    WPP_SF_
0x14000c927  cmp     byte ptr [rbx+754h], 0
0x14000c92e  lea     r8, USBSTOR_ResetDeviceWorkItem; WorkerRoutine
0x14000c935  mov     rdx, [rbx+170h]; Entry
0x14000c93c  mov     rcx, rsi; Object
0x14000c93f  setz    al
0x14000c942  mov     [rsp+58h+var_30], al; char
0x14000c946  mov     qword ptr [rsp+58h+RemlockSize], 0; Context
0x14000c94f  call    USBSTOR_QueueWorkItem
0x14000c954  mov     rbx, [rsp+58h+arg_0]
0x14000c959  mov     rsi, [rsp+58h+arg_8]
0x14000c95e  add     rsp, 50h
0x14000c962  pop     rdi
0x14000c963  retn
```
