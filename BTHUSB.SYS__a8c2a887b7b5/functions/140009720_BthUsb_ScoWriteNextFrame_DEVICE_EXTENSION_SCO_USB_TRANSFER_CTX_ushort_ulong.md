# BthUsb_ScoWriteNextFrame(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong)

- ea: `0x140009720`
- end: `0x140009732`
- name: `?BthUsb_ScoWriteNextFrame@@YAKPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@GK@Z`
- size: `18`
- prototype: `unsigned int __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoWriteNextFrame(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_TRANSFER_CTX *a2,
        __int64 a3,
        int a4)
{
  return a4 + a1->Sco.WriteFramesPerReq * a1->Sco.NumChannels;
}

```

## disassembly

```asm
0x140009720  movzx   eax, word ptr [rcx+2ACh]
0x140009727  imul    eax, [rcx+270h]
0x14000972e  add     eax, r9d
0x140009731  retn
```
