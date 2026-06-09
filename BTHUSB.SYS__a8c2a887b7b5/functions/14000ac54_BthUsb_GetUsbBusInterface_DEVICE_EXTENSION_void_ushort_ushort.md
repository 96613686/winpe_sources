# BthUsb_GetUsbBusInterface(_DEVICE_EXTENSION *,void *,ushort,ushort)

- ea: `0x14000ac54`
- end: `0x14000ae4d`
- name: `?BthUsb_GetUsbBusInterface@@YAJPEAU_DEVICE_EXTENSION@@PEAXGG@Z`
- size: `505`
- prototype: `int(struct _DEVICE_EXTENSION *, void *, unsigned __int16, unsigned __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004fc8`
- `0x140019b00`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x14000ac54`
- `0x14000bbd4`
- `0x14000e1c0`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x14000acd8`
- `ntoskrnl!IoAllocateIrp` at `0x14000acd8`
- `ntoskrnl!IoFreeIrp` at `0x14000adea`
- `ntoskrnl!IoFreeIrp` at `0x14000adea`
- `ntoskrnl!IofCallDriver` at `0x14000adad`
- `ntoskrnl!IofCallDriver` at `0x14000adad`
- `ntoskrnl!KeInitializeEvent` at `0x14000ad47`
- `ntoskrnl!KeInitializeEvent` at `0x14000ad47`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000add8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000add8`

## pseudocode

```c
__int64 __fastcall BthUsb_GetUsbBusInterface(
        struct _DEVICE_EXTENSION *a1,
        void *a2,
        unsigned __int16 a3,
        unsigned __int16 a4)
{
  int v8; // edx
  int v9; // r8d
  char v10; // bl
  int v11; // edx
  PIRP Irp; // rsi
  int v13; // r8d
  int v14; // edx
  int v15; // r8d
  unsigned int Status; // edi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v18; // rax
  struct _KEVENT Event; // [rsp+60h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  memset(a2, 0, a3);
  v10 = 1;
  LOBYTE(v8) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qqdd(WPP_GLOBAL_Control->AttachedDevice, v8, v9, WPP_GLOBAL_Control->DeviceExtension);
  Irp = IoAllocateIrp(a1->TopOfStack->StackSize, 0);
  if ( Irp )
  {
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)&USB_BUS_INTERFACE_USBDI_GUID;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 2075;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (__int64)a2;
    CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
    CurrentStackLocation[-1].Parameters.QueryInterface.Size = a3;
    CurrentStackLocation[-1].Parameters.QueryInterface.Version = a4;
    v18 = Irp->Tail.Overlay.CurrentStackLocation;
    v18[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))BthUsb_SyncCompletionRoutine;
    v18[-1].Context = &Event;
    v18[-1].Control = -32;
    Irp->IoStatus.Status = -1073741637;
    Status = IofCallDriver(a1->TopOfStack, Irp);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = Irp->IoStatus.Status;
    }
    IoFreeIrp(Irp);
  }
  else
  {
    LOBYTE(v11) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v13,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      2,
      79,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
    Status = -1073741670;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v10 = 0;
  LOBYTE(v14) = v10;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v14,
    v15,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    80,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    Status);
  return Status;
}

```

## disassembly

```asm
0x14000ac54  push    rbx
0x14000ac56  push    rbp
0x14000ac57  push    rsi
0x14000ac58  push    rdi
0x14000ac59  push    r13
0x14000ac5b  push    r14
0x14000ac5d  push    r15
0x14000ac5f  sub     rsp, 80h
0x14000ac66  mov     rbp, rdx
0x14000ac69  movzx   edi, r8w
0x14000ac6d  mov     r14, rcx
0x14000ac70  movzx   r15d, r9w
0x14000ac74  xorps   xmm0, xmm0
0x14000ac77  xor     eax, eax
0x14000ac79  mov     r8d, edi; Size
0x14000ac7c  mov     [rsp+0B8h+Event.Header.WaitListHead.Blink], rax
0x14000ac81  mov     rcx, rbp; void *
0x14000ac84  xor     edx, edx; Val
0x14000ac86  movups  xmmword ptr [rsp+0B8h+Event.Header.___u0], xmm0
0x14000ac8b  call    memset
0x14000ac90  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ac97  mov     ebx, 1
0x14000ac9c  mov     eax, [rcx+2Ch]
0x14000ac9f  test    al, 2
0x14000aca1  jz      short loc_14000ACAD
0x14000aca3  cmp     byte ptr [rcx+29h], 4
0x14000aca7  jb      short loc_14000ACAD
0x14000aca9  mov     dl, bl
0x14000acab  jmp     short loc_14000ACAF
0x14000acad  xor     dl, dl
0x14000acaf  mov     r9, [rcx+40h]
0x14000acb3  mov     rcx, [rcx+18h]
0x14000acb7  mov     [rsp+0B8h+var_60], r15d
0x14000acbc  mov     [rsp+0B8h+var_68], edi
0x14000acc0  mov     [rsp+0B8h+var_70], rbp
0x14000acc5  mov     [rsp+0B8h+var_78], r14
0x14000acca  call    WPP_RECORDER_AND_TRACE_SF_qqdd
0x14000accf  mov     rcx, [r14+28h]
0x14000acd3  xor     edx, edx; ChargeQuota
0x14000acd5  mov     cl, [rcx+4Ch]; StackSize
0x14000acd8  call    cs:__imp_IoAllocateIrp
0x14000acdf  nop     dword ptr [rax+rax+00h]
0x14000ace4  lea     r13, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14000aceb  mov     rsi, rax
0x14000acee  test    rax, rax
0x14000acf1  jnz     short loc_14000AD3D
0x14000acf3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000acfa  mov     eax, [rcx+2Ch]
0x14000acfd  test    al, 2
0x14000acff  jz      short loc_14000AD0B
0x14000ad01  cmp     byte ptr [rcx+29h], 2
0x14000ad05  jb      short loc_14000AD0B
0x14000ad07  mov     dl, bl
0x14000ad09  jmp     short loc_14000AD0D
0x14000ad0b  xor     dl, dl
0x14000ad0d  mov     r9, [rcx+40h]
0x14000ad11  mov     rcx, [rcx+18h]
0x14000ad15  mov     [rsp+0B8h+var_80], r13
0x14000ad1a  mov     [rsp+0B8h+var_88], 4Fh ; 'O'
0x14000ad21  mov     [rsp+0B8h+var_90], 2
0x14000ad29  mov     byte ptr [rsp+0B8h+Timeout], 2
0x14000ad2e  call    WPP_RECORDER_AND_TRACE_SF_
0x14000ad33  mov     edi, 0C000009Ah
0x14000ad38  jmp     loc_14000ADF6
0x14000ad3d  xor     r8d, r8d; State
0x14000ad40  lea     rcx, [rsp+0B8h+Event]; Event
0x14000ad45  mov     edx, ebx; Type
0x14000ad47  call    cs:__imp_KeInitializeEvent
0x14000ad4e  nop     dword ptr [rax+rax+00h]
0x14000ad53  mov     rax, [rsi+0B8h]
0x14000ad5a  lea     rcx, USB_BUS_INTERFACE_USBDI_GUID
0x14000ad61  mov     rdx, rsi; Irp
0x14000ad64  mov     [rax-40h], rcx
0x14000ad68  lea     rcx, ?BthUsb_SyncCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; BthUsb_SyncCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14000ad6f  mov     word ptr [rax-48h], 81Bh
0x14000ad75  mov     [rax-30h], rbp
0x14000ad79  mov     qword ptr [rax-28h], 0
0x14000ad81  mov     [rax-38h], di
0x14000ad85  mov     [rax-36h], r15w
0x14000ad8a  mov     rax, [rsi+0B8h]
0x14000ad91  mov     [rax-10h], rcx
0x14000ad95  lea     rcx, [rsp+0B8h+Event]
0x14000ad9a  mov     [rax-8], rcx
0x14000ad9e  mov     byte ptr [rax-45h], 0E0h
0x14000ada2  mov     dword ptr [rsi+30h], 0C00000BBh
0x14000ada9  mov     rcx, [r14+28h]; DeviceObject
0x14000adad  call    cs:__imp_IofCallDriver
0x14000adb4  nop     dword ptr [rax+rax+00h]
0x14000adb9  mov     edi, eax
0x14000adbb  cmp     eax, 103h
0x14000adc0  jnz     short loc_14000ADE7
0x14000adc2  xor     r9d, r9d; Alertable
0x14000adc5  mov     [rsp+0B8h+Timeout], 0; Timeout
0x14000adce  xor     r8d, r8d; WaitMode
0x14000add1  lea     rcx, [rsp+0B8h+Event]; Object
0x14000add6  xor     edx, edx; WaitReason
0x14000add8  call    cs:__imp_KeWaitForSingleObject
0x14000addf  nop     dword ptr [rax+rax+00h]
0x14000ade4  mov     edi, [rsi+30h]
0x14000ade7  mov     rcx, rsi; Irp
0x14000adea  call    cs:__imp_IoFreeIrp
0x14000adf1  nop     dword ptr [rax+rax+00h]
0x14000adf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000adfd  mov     eax, [rcx+2Ch]
0x14000ae00  test    al, 2
0x14000ae02  jz      short loc_14000AE0A
0x14000ae04  cmp     byte ptr [rcx+29h], 4
0x14000ae08  jnb     short loc_14000AE0C
0x14000ae0a  xor     bl, bl
0x14000ae0c  mov     r9, [rcx+40h]
0x14000ae10  mov     dl, bl
0x14000ae12  mov     rcx, [rcx+18h]
0x14000ae16  mov     dword ptr [rsp+0B8h+var_78], edi
0x14000ae1a  mov     [rsp+0B8h+var_80], r13
0x14000ae1f  mov     [rsp+0B8h+var_88], 50h ; 'P'
0x14000ae26  mov     [rsp+0B8h+var_90], 2
0x14000ae2e  mov     byte ptr [rsp+0B8h+Timeout], 4
0x14000ae33  call    WPP_RECORDER_AND_TRACE_SF_D
0x14000ae38  mov     eax, edi
0x14000ae3a  add     rsp, 80h
0x14000ae41  pop     r15
0x14000ae43  pop     r14
0x14000ae45  pop     r13
0x14000ae47  pop     rdi
0x14000ae48  pop     rsi
0x14000ae49  pop     rbp
0x14000ae4a  pop     rbx
0x14000ae4b  retn
```
