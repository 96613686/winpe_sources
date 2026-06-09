# WdmlibInit

- ea: `0x14000d198`
- end: `0x14000d21d`
- name: `WdmlibInit`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d224`

## callees

- `0x14000d198`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000d1b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d1f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d1b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d1f3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d1c1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d204`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d1c1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d204`

## string_xrefs

- `0x14000d19f`: `IoCreateDeviceSecure`
- `0x14000d1e7`: `IoValidateDeviceIoControlAccess`

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
0x14000d198  sub     rsp, 38h
0x14000d19c  xorps   xmm0, xmm0
0x14000d19f  lea     rdx, SourceString; "IoCreateDeviceSecure"
0x14000d1a6  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14000d1ab  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14000d1b0  call    cs:__imp_RtlInitUnicodeString
0x14000d1b7  nop     dword ptr [rax+rax+00h]
0x14000d1bc  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x14000d1c1  call    cs:__imp_MmGetSystemRoutineAddress
0x14000d1c8  nop     dword ptr [rax+rax+00h]
0x14000d1cd  mov     cs:PfnIoCreateDeviceSecure, rax
0x14000d1d4  test    rax, rax
0x14000d1d7  jnz     short loc_14000D1E7
0x14000d1d9  lea     rax, IoDevObjCreateDeviceSecure
0x14000d1e0  mov     cs:PfnIoCreateDeviceSecure, rax
0x14000d1e7  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x14000d1ee  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14000d1f3  call    cs:__imp_RtlInitUnicodeString
0x14000d1fa  nop     dword ptr [rax+rax+00h]
0x14000d1ff  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x14000d204  call    cs:__imp_MmGetSystemRoutineAddress
0x14000d20b  nop     dword ptr [rax+rax+00h]
0x14000d210  mov     cs:WdmlibInitialized, 1
0x14000d217  add     rsp, 38h
0x14000d21b  retn
```
