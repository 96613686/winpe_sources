# BampRegisterKernelExtension

- ea: `0x14000b360`
- end: `0x14000b407`
- name: `BampRegisterKernelExtension`
- size: `167`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140016078`

## import_xrefs

- `ntoskrnl!ExRegisterExtension` at `0x14000b3f5`
- `ntoskrnl!ExRegisterExtension` at `0x14000b3f5`

## pseudocode

```c
__int64 __fastcall BampRegisterKernelExtension(__int64 a1)
{
  _DWORD v2[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 *v3; // [rsp+28h] [rbp-20h]
  __int64 *v4; // [rsp+30h] [rbp-18h]
  __int64 v5; // [rsp+38h] [rbp-10h]

  v2[0] = 65541;
  BampKernelCalloutTable = (__int64)BampCreateProcessCallback;
  v2[1] = 393216;
  qword_140007668 = (__int64)BampSetThrottleStateCallback;
  qword_140007670 = (__int64)BampGetThrottleStateCallback;
  qword_140007680 = (__int64)BampGetUserSettingsHandle;
  qword_140007678 = (__int64)BampSetUserSettings;
  qword_140007688 = (__int64)BampProcessesWindowStateUpdate;
  v3 = &BampKernelCalloutTable;
  v4 = &BampKernelInterface;
  v5 = BamDriverObject;
  return ExRegisterExtension(a1, 65537, v2);
}

```

## disassembly

```asm
0x14000b360  mov     r11, rsp
0x14000b363  sub     rsp, 48h
0x14000b367  mov     [rsp+48h+var_28], 10005h
0x14000b36f  lea     rax, BampCreateProcessCallback
0x14000b376  mov     cs:BampKernelCalloutTable, rax
0x14000b37d  lea     r8, [r11-28h]
0x14000b381  mov     [rsp+48h+var_24], 60000h
0x14000b389  lea     rax, BampSetThrottleStateCallback
0x14000b390  mov     cs:qword_140007668, rax
0x14000b397  mov     edx, 10001h
0x14000b39c  lea     rax, BampGetThrottleStateCallback
0x14000b3a3  mov     cs:qword_140007670, rax
0x14000b3aa  lea     rax, BampGetUserSettingsHandle
0x14000b3b1  mov     cs:qword_140007680, rax
0x14000b3b8  lea     rax, BampSetUserSettings
0x14000b3bf  mov     cs:qword_140007678, rax
0x14000b3c6  lea     rax, BampProcessesWindowStateUpdate
0x14000b3cd  mov     cs:qword_140007688, rax
0x14000b3d4  lea     rax, BampKernelCalloutTable
0x14000b3db  mov     [r11-20h], rax
0x14000b3df  lea     rax, BampKernelInterface
0x14000b3e6  mov     [r11-18h], rax
0x14000b3ea  mov     rax, cs:BamDriverObject
0x14000b3f1  mov     [r11-10h], rax
0x14000b3f5  call    cs:__imp_ExRegisterExtension
0x14000b3fc  nop     dword ptr [rax+rax+00h]
0x14000b401  add     rsp, 48h
0x14000b405  retn
```
