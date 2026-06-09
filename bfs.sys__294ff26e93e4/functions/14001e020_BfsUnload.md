# BfsUnload

- ea: `0x14001e020`
- end: `0x14001e198`
- name: `BfsUnload`
- size: `376`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140003614`
- `0x140003aec`
- `0x140003afc`
- `0x14000ab04`
- `0x14000bfe8`
- `0x14000d900`
- `0x14001e020`
- `0x14001e6fc`
- `0x14001e884`

## import_xrefs

- `ntoskrnl!CmUnRegisterCallback` at `0x14001e17a`
- `ntoskrnl!CmUnRegisterCallback` at `0x14001e17a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e154`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e154`
- `ntoskrnl!IoDeleteDevice` at `0x14001e073`
- `ntoskrnl!IoDeleteDevice` at `0x14001e073`
- `ntoskrnl!ZwClose` at `0x14001e05b`
- `ntoskrnl!ZwClose` at `0x14001e05b`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001e037`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001e037`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e118`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e118`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e024`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e024`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e043`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e043`
- `FLTMGR!FltUnregisterFilter` at `0x14001e167`
- `FLTMGR!FltUnregisterFilter` at `0x14001e167`
- `cng!BCryptCloseAlgorithmProvider` at `0x14001e08d`
- `cng!BCryptCloseAlgorithmProvider` at `0x14001e08d`

## pseudocode

```c
__int64 BfsUnload()
{
  PVOID v0; // rcx
  __int64 PolicyTable; // rax
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 PipeNameMappingTable; // rax

  KeEnterCriticalRegion();
  ExWaitForRundownProtectionRelease(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( gBfsRootDirectory )
    ZwClose(gBfsRootDirectory);
  if ( gBfsDeviceObject )
    IoDeleteDevice(gBfsDeviceObject);
  if ( gBfsSHA256Handle )
    BCryptCloseAlgorithmProvider(gBfsSHA256Handle, 0);
  if ( qword_1400191F8 )
    ExFreePoolWithTag(qword_1400191F8, 0);
  if ( qword_1400191F0 )
    ExFreePoolWithTag(qword_1400191F0, 0);
  if ( qword_1400191D0 )
    ExFreePoolWithTag(qword_1400191D0, 0);
  v0 = qword_1400191C8;
  if ( qword_1400191C8 )
    ExFreePoolWithTag(qword_1400191C8, 0);
  if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(v0)
    && gApplicableCapabilitySid )
  {
    ExFreePoolWithTag(gApplicableCapabilitySid, 0);
  }
  PolicyTable = BfsGetPolicyTable();
  if ( PolicyTable )
    BfsUninitializePolicyTable(PolicyTable, v2, v3);
  PipeNameMappingTable = BfsGetPipeNameMappingTable();
  if ( PipeNameMappingTable )
    BfsUninitializePipeMappingTable(PipeNameMappingTable);
  BfsUninitializeGlobalFileTable();
  RtlFreeUnicodeString(&gBfsBootDevice);
  FltUnregisterFilter(gBfsFilterHandle);
  CmUnRegisterCallback(gBfsRegistryCookie);
  wil_UninitializeFeatureStaging();
  TraceLoggingUnregister_EtwUnregister();
  return 0;
}

```

## disassembly

```asm
0x14001e020  sub     rsp, 28h
0x14001e024  call    cs:__imp_KeEnterCriticalRegion
0x14001e02b  nop     dword ptr [rax+rax+00h]
0x14001e030  lea     rcx, gBfsRundownProtection; RunRef
0x14001e037  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14001e03e  nop     dword ptr [rax+rax+00h]
0x14001e043  call    cs:__imp_KeLeaveCriticalRegion
0x14001e04a  nop     dword ptr [rax+rax+00h]
0x14001e04f  mov     rcx, cs:gBfsRootDirectory; Handle
0x14001e056  test    rcx, rcx
0x14001e059  jz      short loc_14001E067
0x14001e05b  call    cs:__imp_ZwClose
0x14001e062  nop     dword ptr [rax+rax+00h]
0x14001e067  mov     rcx, cs:gBfsDeviceObject; DeviceObject
0x14001e06e  test    rcx, rcx
0x14001e071  jz      short loc_14001E07F
0x14001e073  call    cs:__imp_IoDeleteDevice
0x14001e07a  nop     dword ptr [rax+rax+00h]
0x14001e07f  mov     rcx, cs:gBfsSHA256Handle; hAlgorithm
0x14001e086  test    rcx, rcx
0x14001e089  jz      short loc_14001E099
0x14001e08b  xor     edx, edx; dwFlags
0x14001e08d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14001e094  nop     dword ptr [rax+rax+00h]
0x14001e099  mov     rcx, cs:qword_1400191F8; P
0x14001e0a0  test    rcx, rcx
0x14001e0a3  jz      short loc_14001E0B3
0x14001e0a5  xor     edx, edx; Tag
0x14001e0a7  call    cs:__imp_ExFreePoolWithTag
0x14001e0ae  nop     dword ptr [rax+rax+00h]
0x14001e0b3  mov     rcx, cs:qword_1400191F0; P
0x14001e0ba  test    rcx, rcx
0x14001e0bd  jz      short loc_14001E0CD
0x14001e0bf  xor     edx, edx; Tag
0x14001e0c1  call    cs:__imp_ExFreePoolWithTag
0x14001e0c8  nop     dword ptr [rax+rax+00h]
0x14001e0cd  mov     rcx, cs:qword_1400191D0; P
0x14001e0d4  test    rcx, rcx
0x14001e0d7  jz      short loc_14001E0E7
0x14001e0d9  xor     edx, edx; Tag
0x14001e0db  call    cs:__imp_ExFreePoolWithTag
0x14001e0e2  nop     dword ptr [rax+rax+00h]
0x14001e0e7  mov     rcx, cs:qword_1400191C8; P
0x14001e0ee  test    rcx, rcx
0x14001e0f1  jz      short loc_14001E101
0x14001e0f3  xor     edx, edx; Tag
0x14001e0f5  call    cs:__imp_ExFreePoolWithTag
0x14001e0fc  nop     dword ptr [rax+rax+00h]
0x14001e101  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14001e106  test    eax, eax
0x14001e108  jz      short loc_14001E124
0x14001e10a  mov     rcx, cs:gApplicableCapabilitySid; P
0x14001e111  test    rcx, rcx
0x14001e114  jz      short loc_14001E124
0x14001e116  xor     edx, edx; Tag
0x14001e118  call    cs:__imp_ExFreePoolWithTag
0x14001e11f  nop     dword ptr [rax+rax+00h]
0x14001e124  call    BfsGetPolicyTable
0x14001e129  test    rax, rax
0x14001e12c  jz      short loc_14001E136
0x14001e12e  mov     rcx, rax
0x14001e131  call    BfsUninitializePolicyTable
0x14001e136  call    BfsGetPipeNameMappingTable
0x14001e13b  test    rax, rax
0x14001e13e  jz      short loc_14001E148
0x14001e140  mov     rcx, rax
0x14001e143  call    BfsUninitializePipeMappingTable
0x14001e148  call    BfsUninitializeGlobalFileTable
0x14001e14d  lea     rcx, gBfsBootDevice; UnicodeString
0x14001e154  call    cs:__imp_RtlFreeUnicodeString
0x14001e15b  nop     dword ptr [rax+rax+00h]
0x14001e160  mov     rcx, cs:gBfsFilterHandle; Filter
0x14001e167  call    cs:__imp_FltUnregisterFilter
0x14001e16e  nop     dword ptr [rax+rax+00h]
0x14001e173  mov     rcx, qword ptr cs:gBfsRegistryCookie; Cookie
0x14001e17a  call    cs:__imp_CmUnRegisterCallback
0x14001e181  nop     dword ptr [rax+rax+00h]
0x14001e186  call    wil_UninitializeFeatureStaging
0x14001e18b  call    TraceLoggingUnregister_EtwUnregister
0x14001e190  xor     eax, eax
0x14001e192  add     rsp, 28h
0x14001e196  retn
```
