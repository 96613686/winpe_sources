# BthUsb_ScoReleaseUsbBusInterface(_DEVICE_EXTENSION *)

- ea: `0x140019ea0`
- end: `0x140019f25`
- name: `?BthUsb_ScoReleaseUsbBusInterface@@_Y2PAGE@@AXPEAU_DEVICE_EXTENSION@@@Z`
- size: `133`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400030e0`
- `0x140005180`

## callees

- `0x14000175c`
- `0x14000de00`
- `0x14000e1c0`
- `0x140019ea0`

## pseudocode

```c
void __fastcall BthUsb_ScoReleaseUsbBusInterface(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3)
{
  bool v4; // dl

  v4 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v4,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    32,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
  a1->Sco.UsbBusInterface.InterfaceDereference(a1->Sco.UsbBusInterface.BusContext);
  memset(&a1->Sco.UsbBusInterface, 0, sizeof(a1->Sco.UsbBusInterface));
}

```

## disassembly

```asm
0x140019ea0  mov     [rsp+arg_0], rbx
0x140019ea5  push    rdi
0x140019ea6  sub     rsp, 40h
0x140019eaa  mov     rdi, rcx
0x140019ead  mov     rcx, cs:WPP_GLOBAL_Control
0x140019eb4  mov     eax, [rcx+2Ch]
0x140019eb7  test    al, 8
0x140019eb9  jz      short loc_140019EC5
0x140019ebb  cmp     byte ptr [rcx+29h], 4
0x140019ebf  jb      short loc_140019EC5
0x140019ec1  mov     dl, 1
0x140019ec3  jmp     short loc_140019EC7
0x140019ec5  xor     dl, dl
0x140019ec7  mov     r9, [rcx+40h]
0x140019ecb  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140019ed2  mov     rcx, [rcx+18h]
0x140019ed6  mov     [rsp+48h+var_10], rax
0x140019edb  mov     [rsp+48h+var_18], 20h ; ' '
0x140019ee2  mov     [rsp+48h+var_20], 4
0x140019eea  mov     [rsp+48h+var_28], 4
0x140019eef  call    WPP_RECORDER_AND_TRACE_SF_
0x140019ef4  mov     rax, [rdi+108h]
0x140019efb  lea     rbx, [rdi+0F0h]
0x140019f02  mov     rcx, [rbx+8]
0x140019f06  call    _guard_dispatch_icall
0x140019f0b  xor     edx, edx; Val
0x140019f0d  mov     rcx, rbx; void *
0x140019f10  lea     r8d, [rdx+40h]; Size
0x140019f14  call    memset
0x140019f19  mov     rbx, [rsp+48h+arg_0]
0x140019f1e  add     rsp, 40h
0x140019f22  pop     rdi
0x140019f23  retn
```
