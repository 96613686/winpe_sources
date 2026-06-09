# USBDInternal_BuildAndSendQueryInterfaceSynchronously

- ea: `0x14000c550`
- end: `0x14000c6ae`
- name: `USBDInternal_BuildAndSendQueryInterfaceSynchronously`
- size: `350`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000cd68`

## callees

- `0x14000c550`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000c694`
- `ntoskrnl!IoFreeIrp` at `0x14000c694`
- `ntoskrnl!KeInitializeEvent` at `0x14000c580`
- `ntoskrnl!KeInitializeEvent` at `0x14000c580`
- `ntoskrnl!IofCallDriver` at `0x14000c657`
- `ntoskrnl!IofCallDriver` at `0x14000c657`
- `ntoskrnl!IoAllocateIrp` at `0x14000c591`
- `ntoskrnl!IoAllocateIrp` at `0x14000c591`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000c622`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000c622`
- `ntoskrnl!DbgPrintEx` at `0x14000c5bc`
- `ntoskrnl!DbgPrintEx` at `0x14000c5bc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c682`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c682`

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
  unsigned int Status; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v12; // rax
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
      v12 = v9->Tail.Overlay.CurrentStackLocation;
      v12[-1].CompletionRoutine = USBD_SyncCompletionRoutine;
      v12[-1].Context = &Event;
      v12[-1].Control = -32;
    }
    v9->IoStatus.Status = -1073741637;
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
      DbgPrintEx(0x4Du, 0, "Failed to allocate Query Interface Irp for Target Device Ojbect 0x%p\n", a2);
    return (unsigned int)-1073741670;
  }
  return Status;
}

```

## disassembly

```asm
0x14000c550  push    rbx
0x14000c552  push    rbp
0x14000c553  push    rsi
0x14000c554  push    rdi
0x14000c555  push    r14
0x14000c557  sub     rsp, 60h
0x14000c55b  mov     rbp, r8
0x14000c55e  mov     rdi, rdx
0x14000c561  mov     r14, rcx
0x14000c564  xorps   xmm0, xmm0
0x14000c567  xor     eax, eax
0x14000c569  lea     rcx, [rsp+88h+Event]; Event
0x14000c56e  xor     r8d, r8d; State
0x14000c571  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000c576  xor     edx, edx; Type
0x14000c578  mov     rsi, r9
0x14000c57b  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14000c580  call    cs:__imp_KeInitializeEvent
0x14000c587  nop     dword ptr [rax+rax+00h]
0x14000c58c  mov     cl, [rdi+4Ch]; StackSize
0x14000c58f  xor     edx, edx; ChargeQuota
0x14000c591  call    cs:__imp_IoAllocateIrp
0x14000c598  nop     dword ptr [rax+rax+00h]
0x14000c59d  mov     rbx, rax
0x14000c5a0  test    rax, rax
0x14000c5a3  jnz     short loc_14000C5D2
0x14000c5a5  cmp     cs:g_EnableDbgPrints, al
0x14000c5ab  jz      short loc_14000C5C8
0x14000c5ad  mov     r9, rdi
0x14000c5b0  lea     r8, aFailedToAlloca; "Failed to allocate Query Interface Irp "...
0x14000c5b7  xor     edx, edx; Level
0x14000c5b9  lea     ecx, [rax+4Dh]; ComponentId
0x14000c5bc  call    cs:__imp_DbgPrintEx
0x14000c5c3  nop     dword ptr [rax+rax+00h]
0x14000c5c8  mov     edi, 0C000009Ah
0x14000c5cd  jmp     loc_14000C6A0
0x14000c5d2  mov     rcx, [rax+0B8h]
0x14000c5d9  lea     r9, [rsp+88h+Event]; Context
0x14000c5de  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x14000c5e3  mov     rdx, rbx; Irp
0x14000c5e6  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x14000c5eb  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000c5f0  mov     [rcx-30h], rsi
0x14000c5f4  mov     word ptr [rcx-48h], 81Bh
0x14000c5fa  mov     qword ptr [rcx-28h], 0
0x14000c602  mov     [rcx-40h], rbp
0x14000c606  movzx   eax, word ptr [rsi]
0x14000c609  mov     [rcx-38h], ax
0x14000c60d  movzx   eax, word ptr [rsi+2]
0x14000c611  lea     rsi, USBD_SyncCompletionRoutine
0x14000c618  mov     [rcx-36h], ax
0x14000c61c  mov     r8, rsi; CompletionRoutine
0x14000c61f  mov     rcx, r14; DeviceObject
0x14000c622  call    cs:__imp_IoSetCompletionRoutineEx
0x14000c629  nop     dword ptr [rax+rax+00h]
0x14000c62e  test    eax, eax
0x14000c630  jns     short loc_14000C64A
0x14000c632  mov     rax, [rbx+0B8h]
0x14000c639  lea     rcx, [rsp+88h+Event]
0x14000c63e  mov     [rax-10h], rsi
0x14000c642  mov     [rax-8], rcx
0x14000c646  mov     byte ptr [rax-45h], 0E0h
0x14000c64a  mov     rdx, rbx; Irp
0x14000c64d  mov     dword ptr [rbx+30h], 0C00000BBh
0x14000c654  mov     rcx, rdi; DeviceObject
0x14000c657  call    cs:__imp_IofCallDriver
0x14000c65e  nop     dword ptr [rax+rax+00h]
0x14000c663  mov     edi, eax
0x14000c665  cmp     eax, 103h
0x14000c66a  jnz     short loc_14000C691
0x14000c66c  xor     r9d, r9d; Alertable
0x14000c66f  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x14000c678  xor     r8d, r8d; WaitMode
0x14000c67b  lea     rcx, [rsp+88h+Event]; Object
0x14000c680  xor     edx, edx; WaitReason
0x14000c682  call    cs:__imp_KeWaitForSingleObject
0x14000c689  nop     dword ptr [rax+rax+00h]
0x14000c68e  mov     edi, [rbx+30h]
0x14000c691  mov     rcx, rbx; Irp
0x14000c694  call    cs:__imp_IoFreeIrp
0x14000c69b  nop     dword ptr [rax+rax+00h]
0x14000c6a0  mov     eax, edi
0x14000c6a2  add     rsp, 60h
0x14000c6a6  pop     r14
0x14000c6a8  pop     rdi
0x14000c6a9  pop     rsi
0x14000c6aa  pop     rbp
0x14000c6ab  pop     rbx
0x14000c6ac  retn
```
