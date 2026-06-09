# BthUsb_ScoWriteUrbSend(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *)

- ea: `0x140009d90`
- end: `0x140009e4b`
- name: `?BthUsb_ScoWriteUrbSend@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1400056e8`
- `0x140009d90`
- `0x14000a0a4`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoWriteUrbSend(struct _DEVICE_EXTENSION *a1, struct _SCO_USB_TRANSFER_CTX *a2)
{
  struct _SCO_USB_TRANSFER_CTX *v2; // rbx
  struct _USBD_PIPE_INFORMATION *v4; // rdx

  v2 = a2;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qqLqLLLLLL(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    v2->Urb,
    WPP_GLOBAL_Control->DeviceExtension);
  return BthUsb_ScoSendTransferUrb(
           a1,
           v4,
           (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))BthUsb_ScoWriteTransferCallback,
           v2);
}

```

## disassembly

```asm
0x140009d90  mov     [rsp+arg_0], rbx
0x140009d95  push    rdi
0x140009d96  sub     rsp, 90h
0x140009d9d  mov     rbx, rdx
0x140009da0  mov     rdi, rcx
0x140009da3  mov     rcx, cs:WPP_GLOBAL_Control
0x140009daa  mov     eax, [rcx+2Ch]
0x140009dad  test    al, 10h
0x140009daf  jz      short loc_140009DBB
0x140009db1  cmp     byte ptr [rcx+29h], 4
0x140009db5  jb      short loc_140009DBB
0x140009db7  mov     dl, 1
0x140009db9  jmp     short loc_140009DBD
0x140009dbb  xor     dl, dl
0x140009dbd  mov     r9, [rbx+90h]
0x140009dc4  mov     r8, [rbx+48h]
0x140009dc8  mov     eax, [r9+24h]
0x140009dcc  mov     [rsp+98h+var_10], eax
0x140009dd3  mov     eax, [r9+1Ch]
0x140009dd7  mov     [rsp+98h+var_18], eax
0x140009dde  mov     eax, [r9+14h]
0x140009de2  mov     [rsp+98h+var_20], eax
0x140009de6  mov     eax, [r8+80h]
0x140009ded  mov     [rsp+98h+var_28], eax
0x140009df1  mov     eax, [rbx+78h]
0x140009df4  mov     [rsp+98h+var_30], eax
0x140009df8  mov     eax, [r8+24h]
0x140009dfc  mov     [rsp+98h+var_38], eax
0x140009e00  mov     rax, [r8+28h]
0x140009e04  mov     [rsp+98h+var_40], rax
0x140009e09  mov     eax, [rbx+50h]
0x140009e0c  mov     [rsp+98h+var_48], eax
0x140009e10  mov     [rsp+98h+var_50], r9
0x140009e15  mov     r9, [rcx+40h]
0x140009e19  mov     rcx, [rcx+18h]
0x140009e1d  mov     [rsp+98h+var_58], rbx
0x140009e22  call    WPP_RECORDER_AND_TRACE_SF_qqLqLLLLLL
0x140009e27  mov     r9, rbx; struct _SCO_USB_TRANSFER_CTX *
0x140009e2a  lea     r8, ?BthUsb_ScoWriteTransferCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x140009e31  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140009e34  call    ?BthUsb_ScoSendTransferUrb@@YAJPEAU_DEVICE_EXTENSION@@PEAU_USBD_PIPE_INFORMATION@@P6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@ZPEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoSendTransferUrb(_DEVICE_EXTENSION *,_USBD_PIPE_INFORMATION *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),_SCO_USB_TRANSFER_CTX *)
0x140009e39  mov     rbx, [rsp+98h+arg_0]
0x140009e41  add     rsp, 90h
0x140009e48  pop     rdi
0x140009e49  retn
```
