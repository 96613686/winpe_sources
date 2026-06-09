# BthUsb_ScoReadTransferCallback(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140008120`
- end: `0x1400081a3`
- name: `?BthUsb_ScoReadTransferCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `131`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400058bc`
- `0x140008120`
- `0x14000d708`
- `0x14000d85c`

## string_xrefs

- `0x140008150`: `onecore\drivers\wdm\bluetooth\drivers\bthusb\scousbread.cpp`
- `0x140008171`: `onecore\drivers\wdm\bluetooth\drivers\bthusb\scousbread.cpp`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoReadTransferCallback(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        struct _SCO_USB_TRANSFER_CTX *a3)
{
  struct _DEVICE_EXTENSION *DevExt; // rsi
  _REF_OBJ *p_RefObj; // rbx

  DevExt = a3->DevExt;
  p_RefObj = &a3->RefObj;
  _InterlockedIncrement((volatile signed __int32 *)&a3->RefObj);
  if ( a3->RefObj.DebugInfo )
    RefObj_AddTrackingBlock(
      p_RefObj,
      816,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousbread.cpp",
      BthUsb_ScoReadTransferCallback);
  BthUsb_ScoUrbComplete(DevExt, &DevExt->Sco.ReadPipeObj, a3);
  RefObj_ReleaseEx(
    p_RefObj,
    BthUsb_ScoReadTransferCallback,
    818,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousbread.cpp");
  return 3221225494LL;
}

```

## disassembly

```asm
0x140008120  mov     [rsp+arg_0], rbx
0x140008125  mov     [rsp+arg_8], rsi
0x14000812a  push    rdi
0x14000812b  sub     rsp, 20h
0x14000812f  mov     rsi, [r8+38h]
0x140008133  lea     rbx, [r8+8]
0x140008137  mov     rdi, r8
0x14000813a  lock inc dword ptr [rbx]
0x14000813d  cmp     qword ptr [rbx+10h], 0
0x140008142  jz      short loc_14000815F
0x140008144  lea     r9, ?BthUsb_ScoReadTransferCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; BthUsb_ScoReadTransferCallback(_DEVICE_OBJECT *,_IRP *,void *)
0x14000814b  mov     edx, 330h
0x140008150  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140008157  mov     rcx, rbx
0x14000815a  call    RefObj_AddTrackingBlock
0x14000815f  lea     rdx, [rsi+1F8h]; struct _SCO_USB_PIPE_OBJ *
0x140008166  mov     r8, rdi; struct _SCO_USB_TRANSFER_CTX *
0x140008169  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000816c  call    ?BthUsb_ScoUrbComplete@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_PIPE_OBJ@@PEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoUrbComplete(_DEVICE_EXTENSION *,_SCO_USB_PIPE_OBJ *,_SCO_USB_TRANSFER_CTX *)
0x140008171  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140008178  mov     r8d, 332h
0x14000817e  lea     rdx, ?BthUsb_ScoReadTransferCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; BthUsb_ScoReadTransferCallback(_DEVICE_OBJECT *,_IRP *,void *)
0x140008185  mov     rcx, rbx
0x140008188  call    RefObj_ReleaseEx
0x14000818d  mov     rbx, [rsp+28h+arg_0]
0x140008192  mov     eax, 0C0000016h
0x140008197  mov     rsi, [rsp+28h+arg_8]
0x14000819c  add     rsp, 20h
0x1400081a0  pop     rdi
0x1400081a1  retn
```
