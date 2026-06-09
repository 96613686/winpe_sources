# USBSTOR_AllocBcStream

- ea: `0x1400115ac`
- end: `0x14001168e`
- name: `USBSTOR_AllocBcStream`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x1400115ac`
- `0x140011bf4`
- `0x140013064`
- `0x1400135a8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001166f`
- `ntoskrnl!IofCompleteRequest` at `0x14001166f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001161e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001161e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001165b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001165b`

## pseudocode

```c
__int64 __fastcall USBSTOR_AllocBcStream(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int BcStream; // ebx
  __int64 v6; // rcx
  __int64 v7; // rsi
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !CurrentStackLocation )
    return 3221225473LL;
  if ( CurrentStackLocation->MinorFunction == 4 )
  {
    BcStream = -1073741808;
    if ( (unsigned __int8)USBSTOR_IsAvioEnabledDevice(*(_QWORD *)(a1 + 64)) )
    {
      v7 = v6 + 368;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 656), &LockHandle);
      BcStream = PortAvioAllocateBcStream((PVOID)(v7 + 256));
      if ( BcStream >= 0 )
        BcStream = UsbQueueAllocateStream(v7, 0);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
  }
  else
  {
    BcStream = -1073741790;
  }
  a2->IoStatus.Status = BcStream;
  IofCompleteRequest(a2, 0);
  return (unsigned int)BcStream;
}

```

## disassembly

```asm
0x1400115ac  mov     [rsp+arg_8], rbx
0x1400115b1  mov     [rsp+arg_10], rsi
0x1400115b6  push    rdi
0x1400115b7  sub     rsp, 40h
0x1400115bb  xor     eax, eax
0x1400115bd  xorps   xmm0, xmm0
0x1400115c0  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x1400115c5  mov     rdi, rdx
0x1400115c8  mov     rax, [rdx+0B8h]
0x1400115cf  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x1400115d4  test    rax, rax
0x1400115d7  jnz     short loc_1400115E3
0x1400115d9  mov     eax, 0C0000001h
0x1400115de  jmp     loc_14001167D
0x1400115e3  cmp     byte ptr [rax+1], 4
0x1400115e7  jz      short loc_1400115F0
0x1400115e9  mov     ebx, 0C0000022h
0x1400115ee  jmp     short loc_140011667
0x1400115f0  mov     rcx, [rcx+40h]
0x1400115f4  mov     ebx, 0C0000010h
0x1400115f9  call    USBSTOR_IsAvioEnabledDevice
0x1400115fe  test    al, al
0x140011600  jz      short loc_140011667
0x140011602  lea     rsi, [rcx+170h]
0x140011609  mov     [rsp+48h+arg_0], 0
0x140011612  add     rcx, 290h; SpinLock
0x140011619  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14001161e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140011625  nop     dword ptr [rax+rax+00h]
0x14001162a  lea     rcx, [rsi+100h]; Signature
0x140011631  mov     r8, rdi
0x140011634  lea     r9, [rsp+48h+arg_0]
0x140011639  mov     rdx, rsi
0x14001163c  call    PortAvioAllocateBcStream
0x140011641  mov     ebx, eax
0x140011643  test    eax, eax
0x140011645  js      short loc_140011656
0x140011647  mov     rdx, [rsp+48h+arg_0]
0x14001164c  mov     rcx, rsi
0x14001164f  call    UsbQueueAllocateStream
0x140011654  mov     ebx, eax
0x140011656  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14001165b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011662  nop     dword ptr [rax+rax+00h]
0x140011667  xor     edx, edx; PriorityBoost
0x140011669  mov     [rdi+30h], ebx
0x14001166c  mov     rcx, rdi; Irp
0x14001166f  call    cs:__imp_IofCompleteRequest
0x140011676  nop     dword ptr [rax+rax+00h]
0x14001167b  mov     eax, ebx
0x14001167d  mov     rbx, [rsp+48h+arg_8]
0x140011682  mov     rsi, [rsp+48h+arg_10]
0x140011687  add     rsp, 40h
0x14001168b  pop     rdi
0x14001168c  retn
```
