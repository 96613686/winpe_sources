# USBSTOR_CancelIo

- ea: `0x140011900`
- end: `0x140011a59`
- name: `USBSTOR_CancelIo`
- size: `345`
- prototype: `DRIVER_CANCEL`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x140003b90`
- `0x140005d80`
- `0x140010664`
- `0x140011900`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140011a2b`
- `ntoskrnl!IofCompleteRequest` at `0x140011a2b`
- `ntoskrnl!KeRemoveEntryDeviceQueue` at `0x140011989`
- `ntoskrnl!KeRemoveEntryDeviceQueue` at `0x140011989`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011919`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400119a0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011a41`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011919`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400119a0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011a41`

## pseudocode

```c
void __fastcall USBSTOR_CancelIo(struct _DEVICE_OBJECT *DeviceObject, struct _IRP *Irp)
{
  BOOLEAN v4; // al
  KIRQL CancelIrql; // cl
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PIO_SECURITY_CONTEXT SecurityContext; // rdx
  PUNICODE_STRING FileName; // rbx

  if ( DeviceObject->CurrentIrp == Irp )
  {
    IoReleaseCancelSpinLock(Irp->CancelIrql);
    USBSTOR_LogEntry(827212099, DeviceObject, Irp, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
  }
  else
  {
    v4 = KeRemoveEntryDeviceQueue(&DeviceObject->DeviceQueue, &Irp->Tail.Overlay.DeviceQueueEntry);
    CancelIrql = Irp->CancelIrql;
    if ( v4 )
    {
      IoReleaseCancelSpinLock(CancelIrql);
      USBSTOR_LogEntry(843989315, DeviceObject, Irp, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
      Irp->IoStatus.Status = -1073741536;
      Irp->IoStatus.Information = 0;
      SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
      BYTE3(SecurityContext->SecurityQos) = 2;
      FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
      USBSTOR_FxPowerReference(*(_QWORD *)(*(_QWORD *)&FileName[1].Length + 64LL), SecurityContext, 0);
      IofCompleteRequest(Irp, 0);
      UsbStorPumpNextRequest(FileName);
    }
    else
    {
      IoReleaseCancelSpinLock(CancelIrql);
    }
  }
}

```

## disassembly

```asm
0x140011900  mov     [rsp+arg_0], rbx
0x140011905  push    rdi
0x140011906  sub     rsp, 20h
0x14001190a  mov     rdi, rdx
0x14001190d  mov     rbx, rcx
0x140011910  cmp     [rcx+20h], rdx
0x140011914  jnz     short loc_14001197E
0x140011916  mov     cl, [rdx+45h]; Irql
0x140011919  call    cs:__imp_IoReleaseCancelSpinLock
0x140011920  nop     dword ptr [rax+rax+00h]
0x140011925  xor     r9d, r9d
0x140011928  mov     r8, rdi
0x14001192b  mov     rdx, rbx
0x14001192e  mov     ecx, 314E4143h
0x140011933  call    USBSTOR_LogEntry
0x140011938  mov     rcx, cs:WPP_GLOBAL_Control
0x14001193f  lea     rax, WPP_GLOBAL_Control
0x140011946  cmp     rcx, rax
0x140011949  jz      loc_140011A4D
0x14001194f  mov     eax, [rcx+2Ch]
0x140011952  test    al, 1
0x140011954  jz      loc_140011A4D
0x14001195a  cmp     byte ptr [rcx+29h], 2
0x14001195e  jb      loc_140011A4D
0x140011964  mov     rcx, [rcx+18h]
0x140011968  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14001196f  mov     edx, 4Ch ; 'L'
0x140011974  call    WPP_SF_
0x140011979  jmp     loc_140011A4D
0x14001197e  add     rdx, 78h ; 'x'; DeviceQueueEntry
0x140011982  add     rcx, 0A0h; DeviceQueue
0x140011989  call    cs:__imp_KeRemoveEntryDeviceQueue
0x140011990  nop     dword ptr [rax+rax+00h]
0x140011995  mov     cl, [rdi+45h]; Irql
0x140011998  test    al, al
0x14001199a  jz      loc_140011A41
0x1400119a0  call    cs:__imp_IoReleaseCancelSpinLock
0x1400119a7  nop     dword ptr [rax+rax+00h]
0x1400119ac  xor     r9d, r9d
0x1400119af  mov     r8, rdi
0x1400119b2  mov     rdx, rbx
0x1400119b5  mov     ecx, 324E4143h
0x1400119ba  call    USBSTOR_LogEntry
0x1400119bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400119c6  lea     rax, WPP_GLOBAL_Control
0x1400119cd  cmp     rcx, rax
0x1400119d0  jz      short loc_1400119F4
0x1400119d2  mov     eax, [rcx+2Ch]
0x1400119d5  test    al, 1
0x1400119d7  jz      short loc_1400119F4
0x1400119d9  cmp     byte ptr [rcx+29h], 2
0x1400119dd  jb      short loc_1400119F4
0x1400119df  mov     rcx, [rcx+18h]
0x1400119e3  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400119ea  mov     edx, 4Dh ; 'M'
0x1400119ef  call    WPP_SF_
0x1400119f4  mov     rax, [rdi+0B8h]
0x1400119fb  xor     r8d, r8d
0x1400119fe  mov     dword ptr [rdi+30h], 0C0000120h
0x140011a05  mov     qword ptr [rdi+38h], 0
0x140011a0d  mov     rdx, [rax+8]
0x140011a11  mov     byte ptr [rdx+3], 2
0x140011a15  mov     rbx, [rax+10h]
0x140011a19  mov     rcx, [rbx+10h]
0x140011a1d  mov     rcx, [rcx+40h]
0x140011a21  call    USBSTOR_FxPowerReference
0x140011a26  xor     edx, edx; PriorityBoost
0x140011a28  mov     rcx, rdi; Irp
0x140011a2b  call    cs:__imp_IofCompleteRequest
0x140011a32  nop     dword ptr [rax+rax+00h]
0x140011a37  mov     rcx, rbx
0x140011a3a  call    UsbStorPumpNextRequest
0x140011a3f  jmp     short loc_140011A4D
0x140011a41  call    cs:__imp_IoReleaseCancelSpinLock
0x140011a48  nop     dword ptr [rax+rax+00h]
0x140011a4d  mov     rbx, [rsp+28h+arg_0]
0x140011a52  add     rsp, 20h
0x140011a56  pop     rdi
0x140011a57  retn
```
