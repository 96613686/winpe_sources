# WdmlibInit

- ea: `0x140036e5c`
- end: `0x140036ee1`
- name: `WdmlibInit`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140036ee8`

## callees

- `0x140036e5c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140036e74`
- `ntoskrnl!RtlInitUnicodeString` at `0x140036eb7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140036e74`
- `ntoskrnl!RtlInitUnicodeString` at `0x140036eb7`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140036e85`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140036ec8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140036e85`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140036ec8`

## string_xrefs

- `0x140036e63`: `IoCreateDeviceSecure`
- `0x140036eab`: `IoValidateDeviceIoControlAccess`

## pseudocode

```c
PVOID WdmlibInit()
{
  PVOID result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"IoCreateDeviceSecure");
  PfnIoCreateDeviceSecure = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  if ( !PfnIoCreateDeviceSecure )
    PfnIoCreateDeviceSecure = (__int64)IoDevObjCreateDeviceSecure;
  RtlInitUnicodeString(&DestinationString, L"IoValidateDeviceIoControlAccess");
  result = MmGetSystemRoutineAddress(&DestinationString);
  WdmlibInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x140036e5c  sub     rsp, 38h
0x140036e60  xorps   xmm0, xmm0
0x140036e63  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x140036e6a  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140036e6f  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140036e74  call    cs:__imp_RtlInitUnicodeString
0x140036e7b  nop     dword ptr [rax+rax+00h]
0x140036e80  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140036e85  call    cs:__imp_MmGetSystemRoutineAddress
0x140036e8c  nop     dword ptr [rax+rax+00h]
0x140036e91  mov     cs:PfnIoCreateDeviceSecure, rax
0x140036e98  test    rax, rax
0x140036e9b  jnz     short loc_140036EAB
0x140036e9d  lea     rax, IoDevObjCreateDeviceSecure
0x140036ea4  mov     cs:PfnIoCreateDeviceSecure, rax
0x140036eab  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x140036eb2  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140036eb7  call    cs:__imp_RtlInitUnicodeString
0x140036ebe  nop     dword ptr [rax+rax+00h]
0x140036ec3  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140036ec8  call    cs:__imp_MmGetSystemRoutineAddress
0x140036ecf  nop     dword ptr [rax+rax+00h]
0x140036ed4  mov     cs:WdmlibInitialized, 1
0x140036edb  add     rsp, 38h
0x140036edf  retn
```
