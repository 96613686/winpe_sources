# WdmlibIoCreateDeviceSecure

- ea: `0x18002b090`
- end: `0x18002b17f`
- name: `WdmlibIoCreateDeviceSecure`
- size: `239`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015fa4`

## callees

- `0x18001bb30`
- `0x18002b090`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18002b0ce`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18002b111`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18002b0ce`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18002b111`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002b0bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002b100`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002b0bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002b100`

## string_xrefs

- `0x18002b0ac`: `IoCreateDeviceSecure`
- `0x18002b0f4`: `IoValidateDeviceIoControlAccess`

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
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  if ( !WdmlibInitialized )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"IoCreateDeviceSecure");
    PfnIoCreateDeviceSecure = (__int64)MmGetSystemRoutineAddress(&DestinationString);
    if ( !PfnIoCreateDeviceSecure )
      PfnIoCreateDeviceSecure = (__int64)IoDevObjCreateDeviceSecure;
    RtlInitUnicodeString(&DestinationString, L"IoValidateDeviceIoControlAccess");
    MmGetSystemRoutineAddress(&DestinationString);
    WdmlibInitialized = 1;
  }
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, __int64, PUNICODE_STRING, __int64, int, char, const UNICODE_STRING *, GUID *, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           96,
           DeviceName,
           42633,
           256,
           1,
           &SDDL_DEVOBJ_SYS_ALL_ADM_ALL,
           &VEMGR_CLASS_GUID,
           DeviceObject);
}

```

## disassembly

```asm
0x18002b090  mov     [rsp+arg_0], rbx
0x18002b095  push    rdi
0x18002b096  sub     rsp, 60h
0x18002b09a  cmp     cs:WdmlibInitialized, 0
0x18002b0a1  mov     rbx, r8
0x18002b0a4  mov     rdi, rcx
0x18002b0a7  jnz     short loc_18002B124
0x18002b0a9  xorps   xmm0, xmm0
0x18002b0ac  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x18002b0b3  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18002b0b8  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18002b0bd  call    cs:__imp_RtlInitUnicodeString
0x18002b0c4  nop     dword ptr [rax+rax+00h]
0x18002b0c9  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x18002b0ce  call    cs:__imp_MmGetSystemRoutineAddress
0x18002b0d5  nop     dword ptr [rax+rax+00h]
0x18002b0da  mov     cs:PfnIoCreateDeviceSecure, rax
0x18002b0e1  test    rax, rax
0x18002b0e4  jnz     short loc_18002B0F4
0x18002b0e6  lea     rax, IoDevObjCreateDeviceSecure
0x18002b0ed  mov     cs:PfnIoCreateDeviceSecure, rax
0x18002b0f4  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x18002b0fb  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18002b100  call    cs:__imp_RtlInitUnicodeString
0x18002b107  nop     dword ptr [rax+rax+00h]
0x18002b10c  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x18002b111  call    cs:__imp_MmGetSystemRoutineAddress
0x18002b118  nop     dword ptr [rax+rax+00h]
0x18002b11d  mov     cs:WdmlibInitialized, 1
0x18002b124  mov     rcx, [rsp+68h+DeviceObject]
0x18002b12c  mov     r9d, 0A689h
0x18002b132  mov     rax, cs:PfnIoCreateDeviceSecure
0x18002b139  mov     r8, rbx
0x18002b13c  mov     [rsp+68h+var_28], rcx
0x18002b141  mov     edx, 60h ; '`'
0x18002b146  lea     rcx, ?VEMGR_CLASS_GUID@@3U_GUID@@B; _GUID const VEMGR_CLASS_GUID
0x18002b14d  mov     [rsp+68h+var_30], rcx
0x18002b152  lea     rcx, SDDL_DEVOBJ_SYS_ALL_ADM_ALL
0x18002b159  mov     [rsp+68h+var_38], rcx
0x18002b15e  mov     rcx, rdi
0x18002b161  mov     [rsp+68h+var_40], 1
0x18002b166  mov     [rsp+68h+var_48], 100h
0x18002b16e  call    _guard_dispatch_icall
0x18002b173  mov     rbx, [rsp+68h+arg_0]
0x18002b178  add     rsp, 60h
0x18002b17c  pop     rdi
0x18002b17d  retn
```
