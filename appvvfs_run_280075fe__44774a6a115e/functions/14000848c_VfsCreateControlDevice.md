# VfsCreateControlDevice

- ea: `0x14000848c`
- end: `0x14000857c`
- name: `VfsCreateControlDevice`
- size: `240`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, installer_update`

## callers

- `0x140008100`

## callees

- `0x14000848c`
- `0x140024690`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x140008508`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140008508`
- `ntoskrnl!IoDeleteDevice` at `0x140008522`
- `ntoskrnl!IoDeleteDevice` at `0x140008522`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400084bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400084d4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400084bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400084d4`

## pseudocode

```c
NTSTATUS __fastcall VfsCreateControlDevice(PDRIVER_OBJECT DriverObject)
{
  ULONG v2; // edx
  ULONG v3; // r9d
  NTSTATUS result; // eax
  NTSTATUS v5; // edi
  ULONG v6; // [rsp+20h] [rbp-58h]
  BOOLEAN v7; // [rsp+28h] [rbp-50h]
  const UNICODE_STRING *v8; // [rsp+30h] [rbp-48h]
  const GUID *v9; // [rsp+38h] [rbp-40h]
  struct _UNICODE_STRING DeviceName; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-18h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+88h] [rbp+10h] BYREF

  DeviceObject = 0;
  DeviceName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DeviceName, L"\\Device\\AppvVfs");
  RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\AppvVfs");
  result = WdmlibIoCreateDeviceSecure(DriverObject, v2, &DeviceName, v3, v6, v7, v8, v9, &DeviceObject);
  if ( result >= 0 )
  {
    v5 = IoCreateSymbolicLink(&DestinationString, &DeviceName);
    if ( v5 < 0 )
      IoDeleteDevice(DeviceObject);
    ::DeviceObject = DeviceObject;
    DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&VfsDispatchControl;
    DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&VfsDispatchControl;
    DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&VfsDispatchControl;
    DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)&VfsDispatchControl;
    DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&VfsDispatchDeviceIoControl;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000848c  mov     rax, rsp
0x14000848f  mov     [rax+8], rbx
0x140008493  push    rdi
0x140008494  sub     rsp, 70h
0x140008498  mov     rbx, rcx
0x14000849b  mov     qword ptr [rax+10h], 0
0x1400084a3  xorps   xmm0, xmm0
0x1400084a6  lea     rcx, [rax-28h]; DestinationString
0x1400084aa  xorps   xmm1, xmm1
0x1400084ad  lea     rdx, SourceString; "\\Device\\AppvVfs"
0x1400084b4  movups  xmmword ptr [rax-28h], xmm0
0x1400084b8  movups  xmmword ptr [rax-18h], xmm1
0x1400084bc  call    cs:__imp_RtlInitUnicodeString
0x1400084c3  nop     dword ptr [rax+rax+00h]
0x1400084c8  lea     rdx, aDosdevicesAppv; "\\DosDevices\\AppvVfs"
0x1400084cf  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1400084d4  call    cs:__imp_RtlInitUnicodeString
0x1400084db  nop     dword ptr [rax+rax+00h]
0x1400084e0  lea     rax, [rsp+78h+arg_8]
0x1400084e8  mov     rcx, rbx; DriverObject
0x1400084eb  lea     r8, [rsp+78h+DeviceName]; DeviceName
0x1400084f0  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x1400084f5  call    WdmlibIoCreateDeviceSecure
0x1400084fa  test    eax, eax
0x1400084fc  js      short loc_14000856D
0x1400084fe  lea     rdx, [rsp+78h+DeviceName]; DeviceName
0x140008503  lea     rcx, [rsp+78h+DestinationString]; SymbolicLinkName
0x140008508  call    cs:__imp_IoCreateSymbolicLink
0x14000850f  nop     dword ptr [rax+rax+00h]
0x140008514  mov     edi, eax
0x140008516  test    eax, eax
0x140008518  jns     short loc_14000852E
0x14000851a  mov     rcx, [rsp+78h+arg_8]; DeviceObject
0x140008522  call    cs:__imp_IoDeleteDevice
0x140008529  nop     dword ptr [rax+rax+00h]
0x14000852e  mov     rcx, [rsp+78h+arg_8]
0x140008536  lea     rax, VfsDispatchControl
0x14000853d  mov     cs:DeviceObject, rcx
0x140008544  mov     [rbx+70h], rax
0x140008548  mov     [rbx+80h], rax
0x14000854f  mov     [rbx+100h], rax
0x140008556  mov     [rbx+0F0h], rax
0x14000855d  lea     rax, VfsDispatchDeviceIoControl
0x140008564  mov     [rbx+0E0h], rax
0x14000856b  mov     eax, edi
0x14000856d  mov     rbx, [rsp+78h+arg_0]
0x140008575  add     rsp, 70h
0x140008579  pop     rdi
0x14000857a  retn
```
