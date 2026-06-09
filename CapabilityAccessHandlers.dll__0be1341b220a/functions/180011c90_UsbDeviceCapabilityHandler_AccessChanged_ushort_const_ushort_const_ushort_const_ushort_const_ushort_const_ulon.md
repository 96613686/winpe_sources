# UsbDeviceCapabilityHandler::AccessChanged(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180011c90`
- end: `0x180011cad`
- name: `?AccessChanged@UsbDeviceCapabilityHandler@@UEAAJPEBG0000K@Z`
- size: `29`
- prototype: `__int64 __fastcall(UsbDeviceCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180012bbc`

## pseudocode

```c
__int64 __fastcall UsbDeviceCapabilityHandler::AccessChanged(
        UsbDeviceCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  DeviceHelperAccessCheckRevokeInterfaceHandles((__int64)&GUID_DEVINTERFACE_USB_DEVICE, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x180011c90  sub     rsp, 28h
0x180011c94  mov     rdx, r8
0x180011c97  lea     rcx, GUID_DEVINTERFACE_USB_DEVICE
0x180011c9e  mov     r8, r9
0x180011ca1  call    DeviceHelperAccessCheckRevokeInterfaceHandles
0x180011ca6  xor     eax, eax
0x180011ca8  add     rsp, 28h
0x180011cac  retn
```
