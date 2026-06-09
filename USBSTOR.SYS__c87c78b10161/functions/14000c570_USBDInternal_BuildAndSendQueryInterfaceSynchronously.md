# USBDInternal_BuildAndSendQueryInterfaceSynchronously

- ea: `0x14000c570`
- end: `0x14000c6d5`
- name: `USBDInternal_BuildAndSendQueryInterfaceSynchronously`
- size: `357`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fee8`

## callees

- `0x14000c570`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000c681`
- `ntoskrnl!IoFreeIrp` at `0x14000c681`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000c64c`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000c64c`
- `ntoskrnl!IofCallDriver` at `0x14000c669`
- `ntoskrnl!IofCallDriver` at `0x14000c669`
- `ntoskrnl!KeInitializeEvent` at `0x14000c5a0`
- `ntoskrnl!KeInitializeEvent` at `0x14000c5a0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c6c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c6c4`
- `ntoskrnl!IoAllocateIrp` at `0x14000c5b2`
- `ntoskrnl!IoAllocateIrp` at `0x14000c5b2`
- `ntoskrnl!DbgPrintEx` at `0x14000c5df`
- `ntoskrnl!DbgPrintEx` at `0x14000c5df`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildAndSendQueryInterfaceSynchronously(
        PDEVICE_OBJECT DeviceObject,
        PDEVICE_OBJECT a2,
        ULONG_PTR a3,
        USHORT *a4)
{
  PIRP Irp; // rax
  IRP *v9; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned int Status; // edi
  struct _IO_STACK_LOCATION *v13; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Irp = IoAllocateIrp(a2->StackSize, 0);
  v9 = Irp;
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)a4;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 2075;
    CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = a3;
    CurrentStackLocation[-1].Parameters.QueryInterface.Size = *a4;
    CurrentStackLocation[-1].Parameters.QueryInterface.Version = a4[1];
    if ( IoSetCompletionRoutineEx(DeviceObject, Irp, USBD_SyncCompletionRoutine, &Event, 1u, 1u, 1u) < 0 )
    {
      v13 = v9->Tail.Overlay.CurrentStackLocation;
      v13[-1].CompletionRoutine = USBD_SyncCompletionRoutine;
      v13[-1].Context = &Event;
      v13[-1].Control = -32;
    }
    v9->IoStatus.Status = -1073741637;
    Status = IofCallDriver(a2, v9);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v9->IoStatus.Status;
    }
    IoFreeIrp(v9);
    return Status;
  }
  else
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Failed to allocate Query Interface Irp for Target Device Ojbect 0x%p\n", a2);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14000c570  push    rbx
0x14000c572  push    rbp
0x14000c573  push    rsi
0x14000c574  push    rdi
0x14000c575  push    r14
0x14000c577  sub     rsp, 60h
0x14000c57b  mov     rbp, r8
0x14000c57e  mov     rdi, rdx
0x14000c581  mov     r14, rcx
0x14000c584  xorps   xmm0, xmm0
0x14000c587  xor     eax, eax
0x14000c589  lea     rcx, [rsp+88h+Event]; Event
0x14000c58e  xor     r8d, r8d; State
0x14000c591  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000c596  xor     edx, edx; Type
0x14000c598  mov     rsi, r9
0x14000c59b  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14000c5a0  call    cs:__imp_KeInitializeEvent
0x14000c5a7  nop     dword ptr [rax+rax+00h]
0x14000c5ac  movzx   ecx, byte ptr [rdi+4Ch]; StackSize
0x14000c5b0  xor     edx, edx; ChargeQuota
0x14000c5b2  call    cs:__imp_IoAllocateIrp
0x14000c5b9  nop     dword ptr [rax+rax+00h]
0x14000c5be  mov     rbx, rax
0x14000c5c1  test    rax, rax
0x14000c5c4  jnz     short loc_14000C5FC
0x14000c5c6  cmp     cs:g_EnableDbgPrints, al
0x14000c5cc  jz      short loc_14000C5EB
0x14000c5ce  mov     r9, rdi
0x14000c5d1  lea     r8, aFailedToAlloca; "Failed to allocate Query Interface Irp "...
0x14000c5d8  xor     edx, edx; Level
0x14000c5da  mov     ecx, 4Dh ; 'M'; ComponentId
0x14000c5df  call    cs:__imp_DbgPrintEx
0x14000c5e6  nop     dword ptr [rax+rax+00h]
0x14000c5eb  mov     eax, 0C000009Ah
0x14000c5f0  add     rsp, 60h
0x14000c5f4  pop     r14
0x14000c5f6  pop     rdi
0x14000c5f7  pop     rsi
0x14000c5f8  pop     rbp
0x14000c5f9  pop     rbx
0x14000c5fa  retn
0x14000c5fc  mov     rcx, [rax+0B8h]
0x14000c603  lea     r9, [rsp+88h+Event]; Context
0x14000c608  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x14000c60d  mov     rdx, rbx; Irp
0x14000c610  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x14000c615  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000c61a  mov     [rcx-30h], rsi
0x14000c61e  mov     word ptr [rcx-48h], 81Bh
0x14000c624  mov     qword ptr [rcx-28h], 0
0x14000c62c  mov     [rcx-40h], rbp
0x14000c630  movzx   eax, word ptr [rsi]
0x14000c633  mov     [rcx-38h], ax
0x14000c637  movzx   eax, word ptr [rsi+2]
0x14000c63b  lea     rsi, USBD_SyncCompletionRoutine
0x14000c642  mov     [rcx-36h], ax
0x14000c646  mov     r8, rsi; CompletionRoutine
0x14000c649  mov     rcx, r14; DeviceObject
0x14000c64c  call    cs:__imp_IoSetCompletionRoutineEx
0x14000c653  nop     dword ptr [rax+rax+00h]
0x14000c658  test    eax, eax
0x14000c65a  js      short loc_14000C694
0x14000c65c  mov     rdx, rbx; Irp
0x14000c65f  mov     dword ptr [rbx+30h], 0C00000BBh
0x14000c666  mov     rcx, rdi; DeviceObject
0x14000c669  call    cs:__imp_IofCallDriver
0x14000c670  nop     dword ptr [rax+rax+00h]
0x14000c675  mov     edi, eax
0x14000c677  cmp     eax, 103h
0x14000c67c  jz      short loc_14000C6AE
0x14000c67e  mov     rcx, rbx; Irp
0x14000c681  call    cs:__imp_IoFreeIrp
0x14000c688  nop     dword ptr [rax+rax+00h]
0x14000c68d  mov     eax, edi
0x14000c68f  jmp     loc_14000C5F0
0x14000c694  mov     rax, [rbx+0B8h]
0x14000c69b  lea     rcx, [rsp+88h+Event]
0x14000c6a0  mov     [rax-10h], rsi
0x14000c6a4  mov     [rax-8], rcx
0x14000c6a8  mov     byte ptr [rax-45h], 0E0h
0x14000c6ac  jmp     short loc_14000C65C
0x14000c6ae  xor     r9d, r9d; Alertable
0x14000c6b1  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x14000c6ba  xor     r8d, r8d; WaitMode
0x14000c6bd  lea     rcx, [rsp+88h+Event]; Object
0x14000c6c2  xor     edx, edx; WaitReason
0x14000c6c4  call    cs:__imp_KeWaitForSingleObject
0x14000c6cb  nop     dword ptr [rax+rax+00h]
0x14000c6d0  mov     edi, [rbx+30h]
0x14000c6d3  jmp     short loc_14000C67E
```
