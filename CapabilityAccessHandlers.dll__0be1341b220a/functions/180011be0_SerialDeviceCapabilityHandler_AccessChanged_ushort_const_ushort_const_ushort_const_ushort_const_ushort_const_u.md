# SerialDeviceCapabilityHandler::AccessChanged(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180011be0`
- end: `0x180011bfd`
- name: `?AccessChanged@SerialDeviceCapabilityHandler@@UEAAJPEBG0000K@Z`
- size: `29`
- prototype: `__int64 __fastcall(SerialDeviceCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012bbc`

## pseudocode

```c
__int64 __fastcall SerialDeviceCapabilityHandler::AccessChanged(
        SerialDeviceCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  DeviceHelperAccessCheckRevokeInterfaceHandles((__int64)&GUID_DEVINTERFACE_COMPORT, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x180011be0  sub     rsp, 28h
0x180011be4  mov     rdx, r8
0x180011be7  lea     rcx, GUID_DEVINTERFACE_COMPORT
0x180011bee  mov     r8, r9
0x180011bf1  call    DeviceHelperAccessCheckRevokeInterfaceHandles
0x180011bf6  xor     eax, eax
0x180011bf8  add     rsp, 28h
0x180011bfc  retn
```
