# USBSTOR_FreeBcStream

- ea: `0x140011b2c`
- end: `0x140011bed`
- name: `USBSTOR_FreeBcStream`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x14000ab48`
- `0x140011b2c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140011bd3`
- `ntoskrnl!IofCompleteRequest` at `0x140011bd3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011b7b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011b7b`
- `ntoskrnl!IoGetSfioStreamIdentifier` at `0x140011b95`
- `ntoskrnl!IoGetSfioStreamIdentifier` at `0x140011b95`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011bbd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011bbd`

## pseudocode

```c
__int64 __fastcall USBSTOR_FreeBcStream(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v5; // edi
  __int64 v6; // rdi
  PVOID SfioStreamIdentifier; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !CurrentStackLocation )
    return 3221225473LL;
  if ( CurrentStackLocation->MinorFunction == 4 )
  {
    v6 = *(_QWORD *)(a1 + 64);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 656), &LockHandle);
    SfioStreamIdentifier = IoGetSfioStreamIdentifier(a2->Tail.Overlay.OriginalFileObject, (PVOID)(v6 + 624));
    if ( SfioStreamIdentifier )
      UsbQueueFreeStream(v6 + 368, a2, SfioStreamIdentifier);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v5 = 0;
  }
  else
  {
    v5 = -1073741790;
  }
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  return v5;
}

```

## disassembly

```asm
0x140011b2c  mov     [rsp+arg_0], rbx
0x140011b31  push    rdi
0x140011b32  sub     rsp, 40h
0x140011b36  xor     eax, eax
0x140011b38  xorps   xmm0, xmm0
0x140011b3b  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140011b40  mov     rbx, rdx
0x140011b43  mov     rax, [rdx+0B8h]
0x140011b4a  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140011b4f  test    rax, rax
0x140011b52  jnz     short loc_140011B5E
0x140011b54  mov     eax, 0C0000001h
0x140011b59  jmp     loc_140011BE1
0x140011b5e  cmp     byte ptr [rax+1], 4
0x140011b62  jz      short loc_140011B6B
0x140011b64  mov     edi, 0C0000022h
0x140011b69  jmp     short loc_140011BCB
0x140011b6b  mov     rdi, [rcx+40h]
0x140011b6f  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140011b74  lea     rcx, [rdi+290h]; SpinLock
0x140011b7b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140011b82  nop     dword ptr [rax+rax+00h]
0x140011b87  mov     rcx, [rbx+0C0h]; FileObject
0x140011b8e  lea     rdx, [rdi+270h]; Signature
0x140011b95  call    cs:__imp_IoGetSfioStreamIdentifier
0x140011b9c  nop     dword ptr [rax+rax+00h]
0x140011ba1  test    rax, rax
0x140011ba4  jz      short loc_140011BB8
0x140011ba6  mov     r8, rax
0x140011ba9  lea     rcx, [rdi+170h]
0x140011bb0  mov     rdx, rbx
0x140011bb3  call    UsbQueueFreeStream
0x140011bb8  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140011bbd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011bc4  nop     dword ptr [rax+rax+00h]
0x140011bc9  xor     edi, edi
0x140011bcb  xor     edx, edx; PriorityBoost
0x140011bcd  mov     [rbx+30h], edi
0x140011bd0  mov     rcx, rbx; Irp
0x140011bd3  call    cs:__imp_IofCompleteRequest
0x140011bda  nop     dword ptr [rax+rax+00h]
0x140011bdf  mov     eax, edi
0x140011be1  mov     rbx, [rsp+48h+arg_0]
0x140011be6  add     rsp, 40h
0x140011bea  pop     rdi
0x140011beb  retn
```
