# WdmlibIoCreateDeviceSecure

- ea: `0x140024690`
- end: `0x14002477c`
- name: `WdmlibIoCreateDeviceSecure`
- size: `236`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000848c`

## callees

- `0x140013b40`
- `0x140024690`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400246ce`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140024711`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400246ce`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140024711`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400246bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024700`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400246bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024700`

## string_xrefs

- `0x1400246ac`: `IoCreateDeviceSecure`
- `0x1400246f4`: `IoValidateDeviceIoControlAccess`

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
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, const UNICODE_STRING *, __int64 *, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           42632,
           256,
           0,
           &SDDL_DEVOBJ_SYS_ALL_ADM_ALL,
           APPV_VFS_CLASS_GUID,
           DeviceObject);
}

```

## disassembly

```asm
0x140024690  mov     [rsp+arg_0], rbx
0x140024695  push    rdi
0x140024696  sub     rsp, 60h
0x14002469a  cmp     cs:WdmlibInitialized, 0
0x1400246a1  mov     rbx, r8
0x1400246a4  mov     rdi, rcx
0x1400246a7  jnz     short loc_140024724
0x1400246a9  xorps   xmm0, xmm0
0x1400246ac  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x1400246b3  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400246b8  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400246bd  call    cs:__imp_RtlInitUnicodeString
0x1400246c4  nop     dword ptr [rax+rax+00h]
0x1400246c9  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x1400246ce  call    cs:__imp_MmGetSystemRoutineAddress
0x1400246d5  nop     dword ptr [rax+rax+00h]
0x1400246da  mov     cs:PfnIoCreateDeviceSecure, rax
0x1400246e1  test    rax, rax
0x1400246e4  jnz     short loc_1400246F4
0x1400246e6  lea     rax, IoDevObjCreateDeviceSecure
0x1400246ed  mov     cs:PfnIoCreateDeviceSecure, rax
0x1400246f4  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x1400246fb  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140024700  call    cs:__imp_RtlInitUnicodeString
0x140024707  nop     dword ptr [rax+rax+00h]
0x14002470c  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x140024711  call    cs:__imp_MmGetSystemRoutineAddress
0x140024718  nop     dword ptr [rax+rax+00h]
0x14002471d  mov     cs:WdmlibInitialized, 1
0x140024724  mov     rcx, [rsp+68h+DeviceObject]
0x14002472c  mov     r9d, 0A688h
0x140024732  mov     rax, cs:PfnIoCreateDeviceSecure
0x140024739  mov     r8, rbx
0x14002473c  mov     [rsp+68h+var_28], rcx
0x140024741  xor     edx, edx
0x140024743  lea     rcx, APPV_VFS_CLASS_GUID
0x14002474a  mov     [rsp+68h+var_30], rcx
0x14002474f  lea     rcx, SDDL_DEVOBJ_SYS_ALL_ADM_ALL
0x140024756  mov     [rsp+68h+var_38], rcx
0x14002475b  mov     rcx, rdi
0x14002475e  mov     [rsp+68h+var_40], 0
0x140024763  mov     [rsp+68h+var_48], 100h
0x14002476b  call    _guard_dispatch_icall
0x140024770  mov     rbx, [rsp+68h+arg_0]
0x140024775  add     rsp, 60h
0x140024779  pop     rdi
0x14002477a  retn
```
