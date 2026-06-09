# BthUsb_ScoWriteTransferCallback(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140009a10`
- end: `0x140009a8a`
- name: `?BthUsb_ScoWriteTransferCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `122`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400058bc`
- `0x140009a10`
- `0x14000d708`
- `0x14000d85c`

## string_xrefs

- `0x140009a41`: `onecore\drivers\wdm\bluetooth\drivers\bthusb\scousbwrite.cpp`
- `0x140009a5f`: `onecore\drivers\wdm\bluetooth\drivers\bthusb\scousbwrite.cpp`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoWriteTransferCallback(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        struct _SCO_USB_TRANSFER_CTX *a3)
{
  struct _DEVICE_EXTENSION *DevExt; // rsi
  _REF_OBJ *p_RefObj; // rbx
  _SCO_USB_CHANNEL *Chx; // rbp

  DevExt = a3->DevExt;
  p_RefObj = &a3->RefObj;
  Chx = a3->Chx;
  _InterlockedIncrement((volatile signed __int32 *)&a3->RefObj);
  if ( a3->RefObj.DebugInfo )
    RefObj_AddTrackingBlock(
      p_RefObj,
      941,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousbwrite.cpp",
      BthUsb_ScoWriteTransferCallback);
  BthUsb_ScoUrbComplete(DevExt, &Chx->WritePipeObj, a3);
  RefObj_ReleaseEx(
    p_RefObj,
    BthUsb_ScoWriteTransferCallback,
    943,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousbwrite.cpp");
  return 3221225494LL;
}

```

## disassembly

```asm
0x140009a10  push    rbx
0x140009a12  push    rbp
0x140009a13  push    rsi
0x140009a14  push    rdi
0x140009a15  sub     rsp, 28h
0x140009a19  mov     rsi, [r8+38h]
0x140009a1d  lea     rbx, [r8+8]
0x140009a21  mov     rbp, [r8+90h]
0x140009a28  mov     rdi, r8
0x140009a2b  lock inc dword ptr [rbx]
0x140009a2e  cmp     qword ptr [rbx+10h], 0
0x140009a33  jz      short loc_140009A50
0x140009a35  lea     r9, ?BthUsb_ScoWriteTransferCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; BthUsb_ScoWriteTransferCallback(_DEVICE_OBJECT *,_IRP *,void *)
0x140009a3c  mov     edx, 3ADh
0x140009a41  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009a48  mov     rcx, rbx
0x140009a4b  call    RefObj_AddTrackingBlock
0x140009a50  lea     rdx, [rbp+40h]; struct _SCO_USB_PIPE_OBJ *
0x140009a54  mov     r8, rdi; struct _SCO_USB_TRANSFER_CTX *
0x140009a57  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x140009a5a  call    ?BthUsb_ScoUrbComplete@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_PIPE_OBJ@@PEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoUrbComplete(_DEVICE_EXTENSION *,_SCO_USB_PIPE_OBJ *,_SCO_USB_TRANSFER_CTX *)
0x140009a5f  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009a66  mov     r8d, 3AFh
0x140009a6c  lea     rdx, ?BthUsb_ScoWriteTransferCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; BthUsb_ScoWriteTransferCallback(_DEVICE_OBJECT *,_IRP *,void *)
0x140009a73  mov     rcx, rbx
0x140009a76  call    RefObj_ReleaseEx
0x140009a7b  mov     eax, 0C0000016h
0x140009a80  add     rsp, 28h
0x140009a84  pop     rdi
0x140009a85  pop     rsi
0x140009a86  pop     rbp
0x140009a87  pop     rbx
0x140009a88  retn
```
