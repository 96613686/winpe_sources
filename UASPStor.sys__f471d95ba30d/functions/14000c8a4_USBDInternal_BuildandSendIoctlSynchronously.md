# USBDInternal_BuildandSendIoctlSynchronously

- ea: `0x14000c8a4`
- end: `0x14000c9e9`
- name: `USBDInternal_BuildandSendIoctlSynchronously`
- size: `325`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d188`

## callees

- `0x14000c8a4`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000c9cf`
- `ntoskrnl!IoFreeIrp` at `0x14000c9cf`
- `ntoskrnl!KeInitializeEvent` at `0x14000c8d4`
- `ntoskrnl!KeInitializeEvent` at `0x14000c8d4`
- `ntoskrnl!IofCallDriver` at `0x14000c992`
- `ntoskrnl!IofCallDriver` at `0x14000c992`
- `ntoskrnl!IoAllocateIrp` at `0x14000c8e5`
- `ntoskrnl!IoAllocateIrp` at `0x14000c8e5`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000c964`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000c964`
- `ntoskrnl!DbgPrintEx` at `0x14000c910`
- `ntoskrnl!DbgPrintEx` at `0x14000c910`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c9bd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c9bd`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildandSendIoctlSynchronously(
        PDEVICE_OBJECT DeviceObject,
        PDEVICE_OBJECT a2,
        struct _IRP *a3,
        ULONG_PTR a4)
{
  PIRP Irp; // rax
  IRP *v9; // rdi
  unsigned int Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v12; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Irp = IoAllocateIrp(a2->StackSize, 0);
  v9 = Irp;
  if ( Irp )
  {
    Irp->AssociatedIrp.MasterIrp = a3;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = a4;
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4788299;
    if ( IoSetCompletionRoutineEx(DeviceObject, v9, USBD_SyncCompletionRoutine, &Event, 1u, 1u, 1u) < 0 )
    {
      v12 = v9->Tail.Overlay.CurrentStackLocation;
      v12[-1].CompletionRoutine = USBD_SyncCompletionRoutine;
      v12[-1].Context = &Event;
      v12[-1].Control = -32;
    }
    Status = IofCallDriver(a2, v9);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v9->IoStatus.Status;
    }
    IoFreeIrp(v9);
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
0x14000c8a4  push    rbx
0x14000c8a6  push    rbp
0x14000c8a7  push    rsi
0x14000c8a8  push    rdi
0x14000c8a9  push    r14
0x14000c8ab  sub     rsp, 60h
0x14000c8af  mov     rbp, r8
0x14000c8b2  mov     rbx, rdx
0x14000c8b5  mov     r14, rcx
0x14000c8b8  xorps   xmm0, xmm0
0x14000c8bb  xor     eax, eax
0x14000c8bd  lea     rcx, [rsp+88h+Event]; Event
0x14000c8c2  xor     r8d, r8d; State
0x14000c8c5  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000c8ca  xor     edx, edx; Type
0x14000c8cc  mov     rsi, r9
0x14000c8cf  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14000c8d4  call    cs:__imp_KeInitializeEvent
0x14000c8db  nop     dword ptr [rax+rax+00h]
0x14000c8e0  mov     cl, [rbx+4Ch]; StackSize
0x14000c8e3  xor     edx, edx; ChargeQuota
0x14000c8e5  call    cs:__imp_IoAllocateIrp
0x14000c8ec  nop     dword ptr [rax+rax+00h]
0x14000c8f1  mov     rdi, rax
0x14000c8f4  test    rax, rax
0x14000c8f7  jnz     short loc_14000C926
0x14000c8f9  cmp     cs:g_EnableDbgPrints, al
0x14000c8ff  jz      short loc_14000C91C
0x14000c901  mov     r9, rbx
0x14000c904  lea     r8, aFailedToAlloca_0; "Failed to allocate Irp for Target Devic"...
0x14000c90b  xor     edx, edx; Level
0x14000c90d  lea     ecx, [rax+4Dh]; ComponentId
0x14000c910  call    cs:__imp_DbgPrintEx
0x14000c917  nop     dword ptr [rax+rax+00h]
0x14000c91c  mov     ebx, 0C000009Ah
0x14000c921  jmp     loc_14000C9DB
0x14000c926  mov     [rax+18h], rbp
0x14000c92a  lea     r9, [rsp+88h+Event]; Context
0x14000c92f  mov     rax, [rax+0B8h]
0x14000c936  mov     rdx, rdi; Irp
0x14000c939  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x14000c93e  mov     rcx, r14; DeviceObject
0x14000c941  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x14000c946  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000c94b  mov     [rax-40h], rsi
0x14000c94f  lea     rsi, USBD_SyncCompletionRoutine
0x14000c956  mov     r8, rsi; CompletionRoutine
0x14000c959  mov     byte ptr [rax-48h], 0Fh
0x14000c95d  mov     dword ptr [rax-30h], 49104Bh
0x14000c964  call    cs:__imp_IoSetCompletionRoutineEx
0x14000c96b  nop     dword ptr [rax+rax+00h]
0x14000c970  test    eax, eax
0x14000c972  jns     short loc_14000C98C
0x14000c974  mov     rax, [rdi+0B8h]
0x14000c97b  lea     rcx, [rsp+88h+Event]
0x14000c980  mov     [rax-10h], rsi
0x14000c984  mov     [rax-8], rcx
0x14000c988  mov     byte ptr [rax-45h], 0E0h
0x14000c98c  mov     rdx, rdi; Irp
0x14000c98f  mov     rcx, rbx; DeviceObject
0x14000c992  call    cs:__imp_IofCallDriver
0x14000c999  nop     dword ptr [rax+rax+00h]
0x14000c99e  mov     ebx, eax
0x14000c9a0  cmp     eax, 103h
0x14000c9a5  jnz     short loc_14000C9CC
0x14000c9a7  xor     r9d, r9d; Alertable
0x14000c9aa  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x14000c9b3  xor     r8d, r8d; WaitMode
0x14000c9b6  lea     rcx, [rsp+88h+Event]; Object
0x14000c9bb  xor     edx, edx; WaitReason
0x14000c9bd  call    cs:__imp_KeWaitForSingleObject
0x14000c9c4  nop     dword ptr [rax+rax+00h]
0x14000c9c9  mov     ebx, [rdi+30h]
0x14000c9cc  mov     rcx, rdi; Irp
0x14000c9cf  call    cs:__imp_IoFreeIrp
0x14000c9d6  nop     dword ptr [rax+rax+00h]
0x14000c9db  mov     eax, ebx
0x14000c9dd  add     rsp, 60h
0x14000c9e1  pop     r14
0x14000c9e3  pop     rdi
0x14000c9e4  pop     rsi
0x14000c9e5  pop     rbp
0x14000c9e6  pop     rbx
0x14000c9e7  retn
```
