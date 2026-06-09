# WdmlibIoCreateDeviceSecure

- ea: `0x140017140`
- end: `0x14001722a`
- name: `WdmlibIoCreateDeviceSecure`
- size: `234`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400083a0`

## callees

- `0x14000a6c0`
- `0x140017140`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001717e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400171c1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001717e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400171c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001716d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400171b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001716d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400171b0`

## string_xrefs

- `0x14001715c`: `IoCreateDeviceSecure`
- `0x1400171a4`: `IoValidateDeviceIoControlAccess`

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
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, PCUNICODE_STRING, _QWORD, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           18,
           256,
           0,
           DefaultSDDLString,
           0,
           DeviceObject);
}

```

## disassembly

```asm
0x140017140  mov     [rsp+arg_0], rbx
0x140017145  push    rdi
0x140017146  sub     rsp, 60h
0x14001714a  cmp     cs:WdmlibInitialized, 0
0x140017151  mov     rbx, r8
0x140017154  mov     rdi, rcx
0x140017157  jnz     short loc_1400171D4
0x140017159  xorps   xmm0, xmm0
0x14001715c  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x140017163  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140017168  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14001716d  call    cs:__imp_RtlInitUnicodeString
0x140017174  nop     dword ptr [rax+rax+00h]
0x140017179  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x14001717e  call    cs:__imp_MmGetSystemRoutineAddress
0x140017185  nop     dword ptr [rax+rax+00h]
0x14001718a  mov     cs:PfnIoCreateDeviceSecure, rax
0x140017191  test    rax, rax
0x140017194  jnz     short loc_1400171A4
0x140017196  lea     rax, IoDevObjCreateDeviceSecure
0x14001719d  mov     cs:PfnIoCreateDeviceSecure, rax
0x1400171a4  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x1400171ab  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400171b0  call    cs:__imp_RtlInitUnicodeString
0x1400171b7  nop     dword ptr [rax+rax+00h]
0x1400171bc  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x1400171c1  call    cs:__imp_MmGetSystemRoutineAddress
0x1400171c8  nop     dword ptr [rax+rax+00h]
0x1400171cd  mov     cs:WdmlibInitialized, 1
0x1400171d4  mov     rcx, [rsp+68h+DeviceObject]
0x1400171dc  mov     r9d, 12h
0x1400171e2  mov     rax, cs:PfnIoCreateDeviceSecure
0x1400171e9  mov     r8, rbx
0x1400171ec  mov     [rsp+68h+var_28], rcx
0x1400171f1  xor     edx, edx
0x1400171f3  mov     rcx, [rsp+68h+DefaultSDDLString]
0x1400171fb  mov     [rsp+68h+var_30], 0
0x140017204  mov     [rsp+68h+var_38], rcx
0x140017209  mov     rcx, rdi
0x14001720c  mov     [rsp+68h+var_40], 0
0x140017211  mov     [rsp+68h+var_48], 100h
0x140017219  call    _guard_dispatch_icall
0x14001721e  mov     rbx, [rsp+68h+arg_0]
0x140017223  add     rsp, 60h
0x140017227  pop     rdi
0x140017228  retn
```
