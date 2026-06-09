# HidDeviceCapabilityHandler::AccessChanged(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000a1b0`
- end: `0x18000a1cd`
- name: `?AccessChanged@HidDeviceCapabilityHandler@@UEAAJPEBG0000K@Z`
- size: `29`
- prototype: `__int64 __fastcall(HidDeviceCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180012bbc`

## pseudocode

```c
__int64 __fastcall HidDeviceCapabilityHandler::AccessChanged(
        HidDeviceCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  DeviceHelperAccessCheckRevokeInterfaceHandles((__int64)&GUID_DEVINTERFACE_HID, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x18000a1b0  sub     rsp, 28h
0x18000a1b4  mov     rdx, r8
0x18000a1b7  lea     rcx, GUID_DEVINTERFACE_HID
0x18000a1be  mov     r8, r9
0x18000a1c1  call    DeviceHelperAccessCheckRevokeInterfaceHandles
0x18000a1c6  xor     eax, eax
0x18000a1c8  add     rsp, 28h
0x18000a1cc  retn
```
