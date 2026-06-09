# USBDInternal_BuildandSendIoctlSynchronously

- ea: `0x14000aa00`
- end: `0x14000ab42`
- name: `USBDInternal_BuildandSendIoctlSynchronously`
- size: `322`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a84c`

## callees

- `0x14000aa00`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000ab2a`
- `ntoskrnl!IoFreeIrp` at `0x14000ab2a`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000aabf`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000aabf`
- `ntoskrnl!IofCallDriver` at `0x14000aaed`
- `ntoskrnl!IofCallDriver` at `0x14000aaed`
- `ntoskrnl!KeInitializeEvent` at `0x14000aa2b`
- `ntoskrnl!KeInitializeEvent` at `0x14000aa2b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ab18`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ab18`
- `ntoskrnl!IoAllocateIrp` at `0x14000aa3c`
- `ntoskrnl!IoAllocateIrp` at `0x14000aa3c`
- `ntoskrnl!DbgPrintEx` at `0x14000aa67`
- `ntoskrnl!DbgPrintEx` at `0x14000aa67`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildandSendIoctlSynchronously(
        PDEVICE_OBJECT DeviceObject,
        PDEVICE_OBJECT a2,
        __int64 a3,
        ULONG_PTR a4)
{
  PIRP Irp; // rax
  IRP *v8; // rbx
  unsigned int Status; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v11; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Irp = IoAllocateIrp(a2->StackSize, 0);
  v8 = Irp;
  if ( Irp )
  {
    Irp->AssociatedIrp.MasterIrp = 0;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = a4;
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4788299;
    if ( IoSetCompletionRoutineEx(DeviceObject, v8, USBD_SyncCompletionRoutine, &Event, 1u, 1u, 1u) < 0 )
    {
      v11 = v8->Tail.Overlay.CurrentStackLocation;
      v11[-1].CompletionRoutine = USBD_SyncCompletionRoutine;
      v11[-1].Context = &Event;
      v11[-1].Control = -32;
    }
    Status = IofCallDriver(a2, v8);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v8->IoStatus.Status;
    }
    IoFreeIrp(v8);
  }
  else
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Failed to allocate Irp for Target Device Object 0x%p\n", a2);
    return (unsigned int)-1073741670;
  }
  return Status;
}

```

## disassembly

```asm
0x14000aa00  push    rbx
0x14000aa02  push    rbp
0x14000aa03  push    rsi
0x14000aa04  push    rdi
0x14000aa05  sub     rsp, 68h
0x14000aa09  mov     rdi, rdx
0x14000aa0c  mov     rbp, rcx
0x14000aa0f  xorps   xmm0, xmm0
0x14000aa12  lea     rcx, [rsp+88h+Event]; Event
0x14000aa17  xor     eax, eax
0x14000aa19  xor     edx, edx; Type
0x14000aa1b  xor     r8d, r8d; State
0x14000aa1e  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000aa23  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14000aa28  mov     rsi, r9
0x14000aa2b  call    cs:__imp_KeInitializeEvent
0x14000aa32  nop     dword ptr [rax+rax+00h]
0x14000aa37  mov     cl, [rdi+4Ch]; StackSize
0x14000aa3a  xor     edx, edx; ChargeQuota
0x14000aa3c  call    cs:__imp_IoAllocateIrp
0x14000aa43  nop     dword ptr [rax+rax+00h]
0x14000aa48  mov     rbx, rax
0x14000aa4b  test    rax, rax
0x14000aa4e  jnz     short loc_14000AA7D
0x14000aa50  cmp     cs:g_EnableDbgPrints, al
0x14000aa56  jz      short loc_14000AA73
0x14000aa58  mov     r9, rdi
0x14000aa5b  lea     r8, aFailedToAlloca_0; "Failed to allocate Irp for Target Devic"...
0x14000aa62  xor     edx, edx; Level
0x14000aa64  lea     ecx, [rax+4Dh]; ComponentId
0x14000aa67  call    cs:__imp_DbgPrintEx
0x14000aa6e  nop     dword ptr [rax+rax+00h]
0x14000aa73  mov     edi, 0C000009Ah
0x14000aa78  jmp     loc_14000AB36
0x14000aa7d  mov     qword ptr [rax+18h], 0
0x14000aa85  lea     r9, [rsp+88h+Event]; Context
0x14000aa8a  mov     rax, [rax+0B8h]
0x14000aa91  mov     rdx, rbx; Irp
0x14000aa94  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x14000aa99  mov     rcx, rbp; DeviceObject
0x14000aa9c  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x14000aaa1  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000aaa6  mov     [rax-40h], rsi
0x14000aaaa  lea     rsi, USBD_SyncCompletionRoutine
0x14000aab1  mov     r8, rsi; CompletionRoutine
0x14000aab4  mov     byte ptr [rax-48h], 0Fh
0x14000aab8  mov     dword ptr [rax-30h], 49104Bh
0x14000aabf  call    cs:__imp_IoSetCompletionRoutineEx
0x14000aac6  nop     dword ptr [rax+rax+00h]
0x14000aacb  test    eax, eax
0x14000aacd  jns     short loc_14000AAE7
0x14000aacf  mov     rax, [rbx+0B8h]
0x14000aad6  lea     rcx, [rsp+88h+Event]
0x14000aadb  mov     [rax-10h], rsi
0x14000aadf  mov     [rax-8], rcx
0x14000aae3  mov     byte ptr [rax-45h], 0E0h
0x14000aae7  mov     rdx, rbx; Irp
0x14000aaea  mov     rcx, rdi; DeviceObject
0x14000aaed  call    cs:__imp_IofCallDriver
0x14000aaf4  nop     dword ptr [rax+rax+00h]
0x14000aaf9  mov     edi, eax
0x14000aafb  cmp     eax, 103h
0x14000ab00  jnz     short loc_14000AB27
0x14000ab02  xor     r9d, r9d; Alertable
0x14000ab05  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x14000ab0e  xor     r8d, r8d; WaitMode
0x14000ab11  lea     rcx, [rsp+88h+Event]; Object
0x14000ab16  xor     edx, edx; WaitReason
0x14000ab18  call    cs:__imp_KeWaitForSingleObject
0x14000ab1f  nop     dword ptr [rax+rax+00h]
0x14000ab24  mov     edi, [rbx+30h]
0x14000ab27  mov     rcx, rbx; Irp
0x14000ab2a  call    cs:__imp_IoFreeIrp
0x14000ab31  nop     dword ptr [rax+rax+00h]
0x14000ab36  mov     eax, edi
0x14000ab38  add     rsp, 68h
0x14000ab3c  pop     rdi
0x14000ab3d  pop     rsi
0x14000ab3e  pop     rbp
0x14000ab3f  pop     rbx
0x14000ab40  retn
```
