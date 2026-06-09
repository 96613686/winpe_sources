# BthUsb_ScoReadNextFrame(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong)

- ea: `0x140007d90`
- end: `0x140007d9e`
- name: `?BthUsb_ScoReadNextFrame@@YAKPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@GK@Z`
- size: `14`
- prototype: `unsigned int __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoReadNextFrame(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_TRANSFER_CTX *a2,
        __int64 a3,
        int a4)
{
  return a4 + a1->Sco.UsbAltSetting->READ_FRAMES_X_REQ;
}

```

## disassembly

```asm
0x140007d90  mov     rax, [rcx+478h]
0x140007d97  mov     eax, [rax+48h]
0x140007d9a  add     eax, r9d
0x140007d9d  retn
```
