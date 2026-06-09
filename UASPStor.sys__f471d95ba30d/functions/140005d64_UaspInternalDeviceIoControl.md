# UaspInternalDeviceIoControl

- ea: `0x140005d64`
- end: `0x140005eaa`
- name: `UaspInternalDeviceIoControl`
- size: `326`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, __int64, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002320`
- `0x140006dc8`

## callees

- `0x140005d64`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140005e90`
- `ntoskrnl!IoFreeIrp` at `0x140005e90`
- `ntoskrnl!KeInitializeEvent` at `0x140005d94`
- `ntoskrnl!KeInitializeEvent` at `0x140005d94`
- `ntoskrnl!IofCallDriver` at `0x140005e14`
- `ntoskrnl!IofCallDriver` at `0x140005e14`
- `ntoskrnl!IoCancelIrp` at `0x140005e55`
- `ntoskrnl!IoCancelIrp` at `0x140005e55`
- `ntoskrnl!IoAllocateIrp` at `0x140005da5`
- `ntoskrnl!IoAllocateIrp` at `0x140005da5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005e3f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005e77`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005e3f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005e77`

## pseudocode

```c
__int64 __fastcall UaspInternalDeviceIoControl(
        PDEVICE_OBJECT DeviceObject,
        DWORD a2,
        struct _IRP *a3,
        ULONG a4,
        void *a5,
        ULONG a6)
{
  PIRP Irp; // rax
  IRP *v11; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  IRP *v14; // rdx
  struct _IO_STACK_LOCATION *v15; // rax
  unsigned int Status; // edi
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Irp = IoAllocateIrp(DeviceObject->StackSize, 0);
  v11 = Irp;
  if ( !Irp )
    return 3221225626LL;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v14 = Irp;
  CurrentStackLocation[-1].Parameters.Read.Length = a6;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = a2;
  CurrentStackLocation[-1].Parameters.Create.Options = a4;
  Irp->UserBuffer = a5;
  v15 = Irp->Tail.Overlay.CurrentStackLocation;
  v11->AssociatedIrp.MasterIrp = a3;
  v15[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)USBD_SyncCompletionRoutine;
  v15[-1].Context = &Event;
  v15[-1].Control = -32;
  Status = IofCallDriver(DeviceObject, v14);
  if ( Status == 259 )
  {
    if ( KeWaitForSingleObject(&Event, Executive, 0, 0, 0) == 258 )
    {
      IoCancelIrp(v11);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = -1073741643;
    }
    else
    {
      Status = v11->IoStatus.Status;
    }
  }
  IoFreeIrp(v11);
  return Status;
}

```

## disassembly

```asm
0x140005d64  push    rbx
0x140005d66  push    rbp
0x140005d67  push    rsi
0x140005d68  push    rdi
0x140005d69  push    r14
0x140005d6b  sub     rsp, 50h
0x140005d6f  mov     rbp, r8
0x140005d72  mov     r14d, edx
0x140005d75  mov     rdi, rcx
0x140005d78  xorps   xmm0, xmm0
0x140005d7b  xor     eax, eax
0x140005d7d  lea     rcx, [rsp+78h+Event]; Event
0x140005d82  xor     r8d, r8d; State
0x140005d85  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x140005d8a  xor     edx, edx; Type
0x140005d8c  mov     esi, r9d
0x140005d8f  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x140005d94  call    cs:__imp_KeInitializeEvent
0x140005d9b  nop     dword ptr [rax+rax+00h]
0x140005da0  mov     cl, [rdi+4Ch]; StackSize
0x140005da3  xor     edx, edx; ChargeQuota
0x140005da5  call    cs:__imp_IoAllocateIrp
0x140005dac  nop     dword ptr [rax+rax+00h]
0x140005db1  mov     rbx, rax
0x140005db4  test    rax, rax
0x140005db7  jnz     short loc_140005DC3
0x140005db9  mov     eax, 0C000009Ah
0x140005dbe  jmp     loc_140005E9E
0x140005dc3  mov     rcx, [rax+0B8h]
0x140005dca  mov     rdx, rbx; Irp
0x140005dcd  mov     eax, [rsp+78h+arg_28]
0x140005dd4  mov     [rcx-40h], eax
0x140005dd7  mov     rax, [rsp+78h+arg_20]
0x140005ddf  mov     byte ptr [rcx-48h], 0Fh
0x140005de3  mov     [rcx-30h], r14d
0x140005de7  mov     [rcx-38h], esi
0x140005dea  lea     rcx, USBD_SyncCompletionRoutine
0x140005df1  mov     [rbx+70h], rax
0x140005df5  mov     rax, [rbx+0B8h]
0x140005dfc  mov     [rbx+18h], rbp
0x140005e00  mov     [rax-10h], rcx
0x140005e04  lea     rcx, [rsp+78h+Event]
0x140005e09  mov     [rax-8], rcx
0x140005e0d  mov     rcx, rdi; DeviceObject
0x140005e10  mov     byte ptr [rax-45h], 0E0h
0x140005e14  call    cs:__imp_IofCallDriver
0x140005e1b  nop     dword ptr [rax+rax+00h]
0x140005e20  mov     edi, eax
0x140005e22  cmp     eax, 103h
0x140005e27  jnz     short loc_140005E8D
0x140005e29  xor     r9d, r9d; Alertable
0x140005e2c  mov     [rsp+78h+Timeout], 0; Timeout
0x140005e35  xor     r8d, r8d; WaitMode
0x140005e38  lea     rcx, [rsp+78h+Event]; Object
0x140005e3d  xor     edx, edx; WaitReason
0x140005e3f  call    cs:__imp_KeWaitForSingleObject
0x140005e46  nop     dword ptr [rax+rax+00h]
0x140005e4b  cmp     eax, 102h
0x140005e50  jnz     short loc_140005E8A
0x140005e52  mov     rcx, rbx; Irp
0x140005e55  call    cs:__imp_IoCancelIrp
0x140005e5c  nop     dword ptr [rax+rax+00h]
0x140005e61  xor     r9d, r9d; Alertable
0x140005e64  mov     [rsp+78h+Timeout], 0; Timeout
0x140005e6d  xor     r8d, r8d; WaitMode
0x140005e70  lea     rcx, [rsp+78h+Event]; Object
0x140005e75  xor     edx, edx; WaitReason
0x140005e77  call    cs:__imp_KeWaitForSingleObject
0x140005e7e  nop     dword ptr [rax+rax+00h]
0x140005e83  mov     edi, 0C00000B5h
0x140005e88  jmp     short loc_140005E8D
0x140005e8a  mov     edi, [rbx+30h]
0x140005e8d  mov     rcx, rbx; Irp
0x140005e90  call    cs:__imp_IoFreeIrp
0x140005e97  nop     dword ptr [rax+rax+00h]
0x140005e9c  mov     eax, edi
0x140005e9e  add     rsp, 50h
0x140005ea2  pop     r14
0x140005ea4  pop     rdi
0x140005ea5  pop     rsi
0x140005ea6  pop     rbp
0x140005ea7  pop     rbx
0x140005ea8  retn
```
