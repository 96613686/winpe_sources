# BthUsb_ScoReadUrbSend(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *)

- ea: `0x140008520`
- end: `0x1400085ad`
- name: `?BthUsb_ScoReadUrbSend@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1400056e8`
- `0x140006700`
- `0x140008520`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoReadUrbSend(struct _DEVICE_EXTENSION *a1, struct _SCO_USB_TRANSFER_CTX *a2)
{
  struct _SCO_USB_TRANSFER_CTX *v2; // rbx
  struct _USBD_PIPE_INFORMATION *v4; // rdx

  v2 = a2;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_LLL(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    v2->Urb,
    WPP_GLOBAL_Control->DeviceExtension);
  return BthUsb_ScoSendTransferUrb(
           a1,
           v4,
           (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))BthUsb_ScoReadTransferCallback,
           v2);
}

```

## disassembly

```asm
0x140008520  mov     [rsp+arg_0], rbx
0x140008525  push    rdi
0x140008526  sub     rsp, 60h
0x14000852a  mov     rbx, rdx
0x14000852d  mov     rdi, rcx
0x140008530  mov     rcx, cs:WPP_GLOBAL_Control
0x140008537  mov     eax, [rcx+2Ch]
0x14000853a  test    al, 8
0x14000853c  jz      short loc_140008548
0x14000853e  cmp     byte ptr [rcx+29h], 4
0x140008542  jb      short loc_140008548
0x140008544  mov     dl, 1
0x140008546  jmp     short loc_14000854A
0x140008548  xor     dl, dl
0x14000854a  mov     eax, [rbx+78h]
0x14000854d  mov     r8, [rbx+48h]
0x140008551  mov     r9, [rcx+40h]
0x140008555  mov     rcx, [rcx+18h]
0x140008559  mov     [rsp+68h+var_18], eax
0x14000855d  mov     eax, [rbx+50h]
0x140008560  mov     [rsp+68h+var_20], eax
0x140008564  mov     eax, [r8+80h]
0x14000856b  mov     [rsp+68h+var_28], eax
0x14000856f  lea     rax, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140008576  mov     [rsp+68h+var_30], rax
0x14000857b  mov     [rsp+68h+var_38], 17h
0x140008582  mov     [rsp+68h+var_40], 4
0x14000858a  call    WPP_RECORDER_AND_TRACE_SF_LLL
0x14000858f  mov     r9, rbx; struct _SCO_USB_TRANSFER_CTX *
0x140008592  lea     r8, ?BthUsb_ScoReadTransferCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x140008599  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14000859c  call    ?BthUsb_ScoSendTransferUrb@@YAJPEAU_DEVICE_EXTENSION@@PEAU_USBD_PIPE_INFORMATION@@P6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@ZPEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoSendTransferUrb(_DEVICE_EXTENSION *,_USBD_PIPE_INFORMATION *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),_SCO_USB_TRANSFER_CTX *)
0x1400085a1  mov     rbx, [rsp+68h+arg_0]
0x1400085a6  add     rsp, 60h
0x1400085aa  pop     rdi
0x1400085ab  retn
```
