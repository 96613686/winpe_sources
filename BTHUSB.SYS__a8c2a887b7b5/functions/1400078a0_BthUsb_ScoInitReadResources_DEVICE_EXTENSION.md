# BthUsb_ScoInitReadResources(_DEVICE_EXTENSION *)

- ea: `0x1400078a0`
- end: `0x14000797a`
- name: `?BthUsb_ScoInitReadResources@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400030e0`

## callees

- `0x14000175c`
- `0x14000509c`
- `0x1400077c4`
- `0x1400078a0`
- `0x14000da68`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoInitReadResources(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3, int a4)
{
  const ScoUsbAltSetting *UsbAltSetting; // rdx
  int v6; // edx
  struct _DEVICE_EXTENSION *v7; // rcx
  int v8; // edi
  int v9; // r8d

  UsbAltSetting = a1->Sco.UsbAltSetting;
  a1->Sco.ReadsEnabled = 0;
  v8 = ResourceQueue_Initialize((int)a1 + 408, UsbAltSetting->AllocReadTransferCtxImpl, a3, a4);
  if ( v8 >= 0 )
  {
    BthUsb_ScoPipeObjInit(
      v7,
      &a1->Sco.ReadPipeObj,
      READ_SCO_PIPE,
      0,
      (int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *))BthUsb_ScoReadUrbSend,
      (int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *))BthUsb_ScoReadUrbDone,
      (unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int))BthUsb_ScoReadAlignFrame,
      (unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int))BthUsb_ScoReadNextFrame);
    return 0;
  }
  else
  {
    LOBYTE(v6) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v9,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      12,
      (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
    BthUsb_ScoFreeReadResources(a1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400078a0  mov     [rsp+arg_0], rbx
0x1400078a5  push    rdi
0x1400078a6  sub     rsp, 40h
0x1400078aa  mov     rdx, [rcx+478h]
0x1400078b1  mov     rbx, rcx
0x1400078b4  mov     byte ptr [rcx+256h], 0
0x1400078bb  add     rcx, 198h
0x1400078c2  mov     [rsp+48h+var_20], rbx
0x1400078c7  mov     rdx, [rdx+28h]
0x1400078cb  call    ResourceQueue_Initialize
0x1400078d0  mov     edi, eax
0x1400078d2  test    eax, eax
0x1400078d4  jns     short loc_140007927
0x1400078d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078dd  mov     eax, [rcx+2Ch]
0x1400078e0  test    al, 8
0x1400078e2  jz      short loc_1400078EE
0x1400078e4  cmp     byte ptr [rcx+29h], 2
0x1400078e8  jb      short loc_1400078EE
0x1400078ea  mov     dl, 1
0x1400078ec  jmp     short loc_1400078F0
0x1400078ee  xor     dl, dl
0x1400078f0  mov     r9, [rcx+40h]
0x1400078f4  lea     rax, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x1400078fb  mov     rcx, [rcx+18h]
0x1400078ff  mov     [rsp+48h+var_10], rax
0x140007904  mov     word ptr [rsp+48h+var_18], 0Ch
0x14000790b  mov     dword ptr [rsp+48h+var_20], 4
0x140007913  mov     byte ptr [rsp+48h+var_28], 2
0x140007918  call    WPP_RECORDER_AND_TRACE_SF_
0x14000791d  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140007920  call    ?BthUsb_ScoFreeReadResources@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoFreeReadResources(_DEVICE_EXTENSION *)
0x140007925  jmp     short loc_14000796C
0x140007927  lea     rax, ?BthUsb_ScoReadNextFrame@@YAKPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@GK@Z; BthUsb_ScoReadNextFrame(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong)
0x14000792e  xor     r9d, r9d; unsigned __int16
0x140007931  mov     [rsp+48h+var_10], rax; unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int)
0x140007936  lea     rdx, [rbx+1F8h]; struct _SCO_USB_PIPE_OBJ *
0x14000793d  lea     rax, ?BthUsb_ScoReadAlignFrame@@YAKPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@GK@Z; BthUsb_ScoReadAlignFrame(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong)
0x140007944  mov     [rsp+48h+var_18], rax; unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int)
0x140007949  lea     rax, ?BthUsb_ScoReadUrbDone@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoReadUrbDone(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *)
0x140007950  mov     [rsp+48h+var_20], rax; int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *)
0x140007955  lea     r8d, [r9+3]; enum _BTH_PIPE_TYPE
0x140007959  lea     rax, ?BthUsb_ScoReadUrbSend@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoReadUrbSend(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *)
0x140007960  mov     [rsp+48h+var_28], rax; int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *)
0x140007965  call    ?BthUsb_ScoPipeObjInit@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_PIPE_OBJ@@W4_BTH_PIPE_TYPE@@GP6AJ0PEAU_SCO_USB_TRANSFER_CTX@@@Z4P6AK03GK@Z5@Z; BthUsb_ScoPipeObjInit(_DEVICE_EXTENSION *,_SCO_USB_PIPE_OBJ *,_BTH_PIPE_TYPE,ushort,long (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *),long (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *),ulong (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong),ulong (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong))
0x14000796a  xor     edi, edi
0x14000796c  mov     rbx, [rsp+48h+arg_0]
0x140007971  mov     eax, edi
0x140007973  add     rsp, 40h
0x140007977  pop     rdi
0x140007978  retn
```
