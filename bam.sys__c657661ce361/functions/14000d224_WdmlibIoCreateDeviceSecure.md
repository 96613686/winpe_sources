# WdmlibIoCreateDeviceSecure

- ea: `0x14000d224`
- end: `0x14000d296`
- name: `WdmlibIoCreateDeviceSecure`
- size: `114`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140016078`

## callees

- `0x140002710`
- `0x14000d198`
- `0x14000d224`

## pseudocode

```c
NTSTATUS __stdcall WdmlibIoCreateDeviceSecure(
        PDRIVER_OBJECT DriverObject,
        ULONG DeviceExtensionSize,
        PUNICODE_STRING DeviceName,
        ULONG DeviceType,
        ULONG DeviceCharacteristics,
        BOOLEAN Exclusive,
        PCUNICODE_STRING DefaultSDDLString,
        LPCGUID DeviceClassGuid,
        PDEVICE_OBJECT *DeviceObject)
{
  if ( !WdmlibInitialized )
    WdmlibInit(DriverObject, DeviceExtensionSize, DeviceName, DeviceType);
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, const UNICODE_STRING *, _QWORD, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           34,
           256,
           0,
           &SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_R,
           0,
           &BamDeviceObject);
}

```

## disassembly

```asm
0x14000d224  mov     [rsp+arg_0], rbx
0x14000d229  push    rdi
0x14000d22a  sub     rsp, 50h
0x14000d22e  cmp     cs:WdmlibInitialized, 0
0x14000d235  mov     rbx, r8
0x14000d238  mov     rdi, rcx
0x14000d23b  jnz     short loc_14000D242
0x14000d23d  call    WdmlibInit
0x14000d242  mov     rax, cs:PfnIoCreateDeviceSecure
0x14000d249  lea     rcx, BamDeviceObject
0x14000d250  mov     [rsp+58h+var_18], rcx
0x14000d255  mov     r9d, 22h ; '"'
0x14000d25b  mov     [rsp+58h+var_20], 0
0x14000d264  lea     rcx, SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_R
0x14000d26b  mov     [rsp+58h+var_28], rcx
0x14000d270  mov     r8, rbx
0x14000d273  mov     [rsp+58h+var_30], 0
0x14000d278  mov     rcx, rdi
0x14000d27b  xor     edx, edx
0x14000d27d  mov     [rsp+58h+var_38], 100h
0x14000d285  call    _guard_dispatch_icall
0x14000d28a  mov     rbx, [rsp+58h+arg_0]
0x14000d28f  add     rsp, 50h
0x14000d293  pop     rdi
0x14000d294  retn
```
