# UaspGetBusInterface

- ea: `0x14000678c`
- end: `0x1400068c6`
- name: `UaspGetBusInterface`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400015cc`

## callees

- `0x14000678c`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400068aa`
- `ntoskrnl!IoFreeIrp` at `0x1400068aa`
- `ntoskrnl!KeInitializeEvent` at `0x1400067f1`
- `ntoskrnl!KeInitializeEvent` at `0x1400067f1`
- `ntoskrnl!IofCallDriver` at `0x14000686d`
- `ntoskrnl!IofCallDriver` at `0x14000686d`
- `ntoskrnl!IoAllocateIrp` at `0x1400067c4`
- `ntoskrnl!IoAllocateIrp` at `0x1400067c4`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140006849`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140006849`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006898`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006898`

## pseudocode

```c
__int64 __fastcall UaspGetBusInterface(__int64 a1, struct _DEVICE_OBJECT *a2, struct _DEVICE_OBJECT *a3, void *a4)
{
  PIRP Irp; // rdi
  unsigned int Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  memset(a4, 0, 0x48u);
  Irp = IoAllocateIrp(a2->StackSize, 0);
  if ( Irp )
  {
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)&USB_BUS_INTERFACE_USBDI_GUID;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 2075;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)a4;
    CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
    CurrentStackLocation[-1].Parameters.Create.Options = 65608;
    if ( IoSetCompletionRoutineEx(a2, Irp, USBD_SyncCompletionRoutine, &Event, 1u, 1u, 1u) >= 0 )
    {
      Irp->IoStatus.Status = -1073741637;
      Status = IofCallDriver(a3, Irp);
      if ( Status == 259 )
      {
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        Status = Irp->IoStatus.Status;
      }
    }
    else
    {
      Status = -1073741670;
    }
    IoFreeIrp(Irp);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return Status;
}

```

## disassembly

```asm
0x14000678c  push    rbx
0x14000678e  push    rbp
0x14000678f  push    rsi
0x140006790  push    rdi
0x140006791  push    r14
0x140006793  push    r15
0x140006795  sub     rsp, 68h
0x140006799  xor     eax, eax
0x14000679b  mov     rbx, r8
0x14000679e  mov     rbp, rdx
0x1400067a1  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x1400067a6  xorps   xmm0, xmm0
0x1400067a9  xor     edx, edx; Val
0x1400067ab  mov     rcx, r9; void *
0x1400067ae  mov     rsi, r9
0x1400067b1  lea     r8d, [rax+48h]; Size
0x1400067b5  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x1400067ba  call    memset
0x1400067bf  mov     cl, [rbp+4Ch]; StackSize
0x1400067c2  xor     edx, edx; ChargeQuota
0x1400067c4  call    cs:__imp_IoAllocateIrp
0x1400067cb  nop     dword ptr [rax+rax+00h]
0x1400067d0  mov     rdi, rax
0x1400067d3  test    rax, rax
0x1400067d6  jnz     short loc_1400067E2
0x1400067d8  mov     ebx, 0C000009Ah
0x1400067dd  jmp     loc_1400068B6
0x1400067e2  xor     r8d, r8d; State
0x1400067e5  lea     rcx, [rsp+98h+Event]; Event
0x1400067ea  lea     r14d, [r8+1]
0x1400067ee  mov     edx, r14d; Type
0x1400067f1  call    cs:__imp_KeInitializeEvent
0x1400067f8  nop     dword ptr [rax+rax+00h]
0x1400067fd  mov     rax, [rdi+0B8h]
0x140006804  lea     rcx, USB_BUS_INTERFACE_USBDI_GUID
0x14000680b  mov     [rsp+98h+InvokeOnCancel], r14b; InvokeOnCancel
0x140006810  lea     r9, [rsp+98h+Event]; Context
0x140006815  mov     [rsp+98h+InvokeOnError], r14b; InvokeOnError
0x14000681a  lea     r8, USBD_SyncCompletionRoutine; CompletionRoutine
0x140006821  mov     rdx, rdi; Irp
0x140006824  mov     [rsp+98h+InvokeOnSuccess], r14b; InvokeOnSuccess
0x140006829  mov     [rax-40h], rcx
0x14000682d  mov     rcx, rbp; DeviceObject
0x140006830  mov     word ptr [rax-48h], 81Bh
0x140006836  mov     [rax-30h], rsi
0x14000683a  mov     qword ptr [rax-28h], 0
0x140006842  mov     dword ptr [rax-38h], 10048h
0x140006849  call    cs:__imp_IoSetCompletionRoutineEx
0x140006850  nop     dword ptr [rax+rax+00h]
0x140006855  test    eax, eax
0x140006857  jns     short loc_140006860
0x140006859  mov     ebx, 0C000009Ah
0x14000685e  jmp     short loc_1400068A7
0x140006860  mov     rdx, rdi; Irp
0x140006863  mov     dword ptr [rdi+30h], 0C00000BBh
0x14000686a  mov     rcx, rbx; DeviceObject
0x14000686d  call    cs:__imp_IofCallDriver
0x140006874  nop     dword ptr [rax+rax+00h]
0x140006879  mov     ebx, eax
0x14000687b  cmp     eax, 103h
0x140006880  jnz     short loc_1400068A7
0x140006882  xor     r9d, r9d; Alertable
0x140006885  mov     qword ptr [rsp+98h+InvokeOnSuccess], 0; Timeout
0x14000688e  xor     r8d, r8d; WaitMode
0x140006891  lea     rcx, [rsp+98h+Event]; Object
0x140006896  xor     edx, edx; WaitReason
0x140006898  call    cs:__imp_KeWaitForSingleObject
0x14000689f  nop     dword ptr [rax+rax+00h]
0x1400068a4  mov     ebx, [rdi+30h]
0x1400068a7  mov     rcx, rdi; Irp
0x1400068aa  call    cs:__imp_IoFreeIrp
0x1400068b1  nop     dword ptr [rax+rax+00h]
0x1400068b6  mov     eax, ebx
0x1400068b8  add     rsp, 68h
0x1400068bc  pop     r15
0x1400068be  pop     r14
0x1400068c0  pop     rdi
0x1400068c1  pop     rsi
0x1400068c2  pop     rbp
0x1400068c3  pop     rbx
0x1400068c4  retn
```
