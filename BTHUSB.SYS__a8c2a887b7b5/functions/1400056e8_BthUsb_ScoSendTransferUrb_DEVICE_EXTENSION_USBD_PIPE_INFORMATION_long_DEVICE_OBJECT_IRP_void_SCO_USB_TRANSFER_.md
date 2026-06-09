# BthUsb_ScoSendTransferUrb(_DEVICE_EXTENSION *,_USBD_PIPE_INFORMATION *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),_SCO_USB_TRANSFER_CTX *)

- ea: `0x1400056e8`
- end: `0x1400057a6`
- name: `?BthUsb_ScoSendTransferUrb@@YAJPEAU_DEVICE_EXTENSION@@PEAU_USBD_PIPE_INFORMATION@@P6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@ZPEAU_SCO_USB_TRANSFER_CTX@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _USBD_PIPE_INFORMATION *, int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *), struct _SCO_USB_TRANSFER_CTX *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008520`
- `0x140009d90`

## callees

- `0x1400017d4`
- `0x1400056e8`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000573a`
- `ntoskrnl!IofCallDriver` at `0x14000573a`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoSendTransferUrb(
        struct _DEVICE_EXTENSION *a1,
        struct _USBD_PIPE_INFORMATION *a2,
        int (__fastcall *a3)(_DEVICE_OBJECT *, _IRP *, void *),
        struct _SCO_USB_TRANSFER_CTX *a4)
{
  _IRP *Irp; // rdx
  struct _DEVICE_OBJECT *TopOfStack; // r11
  _URB *Urb; // r10
  _IO_STACK_LOCATION *v7; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  NTSTATUS v9; // eax
  int v10; // edx

  Irp = a4->Irp;
  TopOfStack = a1->TopOfStack;
  Urb = a4->Urb;
  Irp->Tail.Overlay.CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)a1;
  v7 = --Irp->Tail.Overlay.CurrentStackLocation;
  --Irp->CurrentLocation;
  v7[-1].Parameters.WMI.ProviderId = (unsigned __int64)Urb;
  v7[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
  v7[-1].MajorFunction = 15;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = a3;
  CurrentStackLocation[-1].Context = a4;
  CurrentStackLocation[-1].Control = -32;
  v9 = IofCallDriver(TopOfStack, Irp);
  if ( v9 != 259 )
  {
    LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      1,
      10,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
      v9);
  }
  return 259;
}

```

## disassembly

```asm
0x1400056e8  sub     rsp, 58h
0x1400056ec  mov     rdx, [r9+40h]; Irp
0x1400056f0  mov     r11, [rcx+28h]
0x1400056f4  mov     r10, [r9+48h]
0x1400056f8  mov     rax, [rdx+0B8h]
0x1400056ff  mov     [rax-40h], rcx
0x140005703  mov     rcx, r11; DeviceObject
0x140005706  add     qword ptr [rdx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000570e  mov     rax, [rdx+0B8h]
0x140005715  dec     byte ptr [rdx+43h]
0x140005718  mov     [rax-40h], r10
0x14000571c  mov     dword ptr [rax-30h], 220003h
0x140005723  mov     byte ptr [rax-48h], 0Fh
0x140005727  mov     rax, [rdx+0B8h]
0x14000572e  mov     [rax-10h], r8
0x140005732  mov     [rax-8], r9
0x140005736  mov     byte ptr [rax-45h], 0E0h
0x14000573a  call    cs:__imp_IofCallDriver
0x140005741  nop     dword ptr [rax+rax+00h]
0x140005746  cmp     eax, 103h
0x14000574b  jz      short loc_14000579B
0x14000574d  mov     r8, cs:WPP_GLOBAL_Control
0x140005754  mov     ecx, [r8+2Ch]
0x140005758  test    cl, 1
0x14000575b  jz      short loc_140005768
0x14000575d  cmp     byte ptr [r8+29h], 2
0x140005762  jb      short loc_140005768
0x140005764  mov     dl, 1
0x140005766  jmp     short loc_14000576A
0x140005768  xor     dl, dl
0x14000576a  mov     r9, [r8+40h]
0x14000576e  lea     rcx, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x140005775  mov     [rsp+58h+var_18], eax
0x140005779  mov     [rsp+58h+var_20], rcx
0x14000577e  mov     rcx, [r8+18h]
0x140005782  mov     [rsp+58h+var_28], 0Ah
0x140005789  mov     [rsp+58h+var_30], 1
0x140005791  mov     [rsp+58h+var_38], 2
0x140005796  call    WPP_RECORDER_AND_TRACE_SF_D
0x14000579b  mov     eax, 103h
0x1400057a0  add     rsp, 58h
0x1400057a4  retn
```
