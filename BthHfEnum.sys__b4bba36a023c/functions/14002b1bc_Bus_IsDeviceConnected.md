# Bus_IsDeviceConnected

- ea: `0x14002b1bc`
- end: `0x14002b224`
- name: `Bus_IsDeviceConnected`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140007768`
- `0x140009004`
- `0x14000e87c`
- `0x14000ecc4`
- `0x14002b22c`

## callees

- `0x14001ae00`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002b206`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b206`

## pseudocode

```c
_BOOL8 __fastcall Bus_IsDeviceConnected(__int64 a1)
{
  __int64 v1; // rax
  union _LARGE_INTEGER Timeout; // [rsp+48h] [rbp+10h] BYREF

  v1 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  Timeout.QuadPart = 0;
  return KeWaitForSingleObject((PVOID)(v1 + 216), Executive, 0, 0, &Timeout) == 258;
}

```

## disassembly

```asm
0x14002b1bc  sub     rsp, 38h
0x14002b1c0  mov     rax, cs:WdfFunctions_01015
0x14002b1c7  mov     rdx, rcx
0x14002b1ca  mov     r8, cs:off_1400220B0
0x14002b1d1  mov     rcx, cs:WdfDriverGlobals
0x14002b1d8  mov     rax, [rax+650h]
0x14002b1df  call    _guard_dispatch_icall
0x14002b1e4  xor     r9d, r9d; Alertable
0x14002b1e7  mov     qword ptr [rsp+38h+arg_8], 0
0x14002b1f0  xor     r8d, r8d; WaitMode
0x14002b1f3  xor     edx, edx; WaitReason
0x14002b1f5  lea     rcx, [rax+0D8h]; Object
0x14002b1fc  lea     rax, [rsp+38h+arg_8]
0x14002b201  mov     [rsp+38h+Timeout], rax; Timeout
0x14002b206  call    cs:__imp_KeWaitForSingleObject
0x14002b20d  nop     dword ptr [rax+rax+00h]
0x14002b212  xor     ecx, ecx
0x14002b214  cmp     eax, 102h
0x14002b219  setz    cl
0x14002b21c  mov     eax, ecx
0x14002b21e  add     rsp, 38h
0x14002b222  retn
```
