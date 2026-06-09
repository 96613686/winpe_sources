# EdpPluginCleanup

- ea: `0x14002c090`
- end: `0x14002c1ba`
- name: `EdpPluginCleanup`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting`

## callees

- `0x14002c090`
- `0x14002d130`
- `0x14002e604`

## import_xrefs

- `ntoskrnl!ZwWaitForSingleObject` at `0x14002c105`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14002c105`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002c164`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002c164`
- `ntoskrnl!ZwAlertThread` at `0x14002c0ed`
- `ntoskrnl!ZwAlertThread` at `0x14002c0ed`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002c199`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002c199`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14002c14f`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14002c14f`
- `ntoskrnl!IoDeleteDevice` at `0x14002c0d5`
- `ntoskrnl!IoDeleteDevice` at `0x14002c0d5`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002c0c6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002c0c6`
- `ntoskrnl!ZwClose` at `0x14002c118`
- `ntoskrnl!ZwClose` at `0x14002c130`
- `ntoskrnl!ZwClose` at `0x14002c118`
- `ntoskrnl!ZwClose` at `0x14002c130`

## string_xrefs

- `0x14002c096`: `\??\AppidEDPPlugin`

## pseudocode

```c
__int64 __fastcall EdpPluginCleanup(PDEVICE_OBJECT *a1, __int64 a2)
{
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)&SymbolicLinkName.Length = 2490404;
  SymbolicLinkName.Buffer = L"\\??\\AppidEDPPlugin";
  if ( *a1 )
  {
    if ( *a1 != (PDEVICE_OBJECT)-64LL && LOBYTE((*a1)->DeviceExtension) )
      IoDeleteSymbolicLink(&SymbolicLinkName);
    IoDeleteDevice(*a1);
  }
  if ( qword_1400194D8 )
  {
    ZwAlertThread(qword_1400194D8);
    ZwWaitForSingleObject(qword_1400194D8, 0, 0);
    ZwClose(qword_1400194D8);
  }
  if ( EventHandle )
    ZwClose(EventHandle);
  EdppShuttingDown = 1;
  if ( EdppPurgeWnfEvtHandle )
    ExUnsubscribeWnfStateChange(EdppPurgeWnfEvtHandle, a2);
  ExAcquirePushLockExclusiveEx(&EdppAuditSessionLock, 0);
  if ( EdppAuditEnabled && (int)EdppDoWorkAsSystem(EdppDisableAudit) >= 0 )
    EdppAuditEnabled = 0;
  ExReleasePushLockEx(&EdppAuditSessionLock, 0);
  EdpFreePluginConfig(byte_140019508);
  return 0;
}

```

## disassembly

```asm
0x14002c090  push    rbx
0x14002c092  sub     rsp, 30h
0x14002c096  lea     rax, aAppidedpplugin; "\\??\\AppidEDPPlugin"
0x14002c09d  mov     qword ptr [rsp+38h+SymbolicLinkName.Length], 260024h
0x14002c0a6  mov     [rsp+38h+SymbolicLinkName.Buffer], rax
0x14002c0ab  mov     rbx, rcx
0x14002c0ae  mov     rax, [rcx]
0x14002c0b1  test    rax, rax
0x14002c0b4  jz      short loc_14002C0E1
0x14002c0b6  add     rax, 40h ; '@'
0x14002c0ba  jz      short loc_14002C0D2
0x14002c0bc  cmp     byte ptr [rax], 0
0x14002c0bf  jz      short loc_14002C0D2
0x14002c0c1  lea     rcx, [rsp+38h+SymbolicLinkName]; SymbolicLinkName
0x14002c0c6  call    cs:__imp_IoDeleteSymbolicLink
0x14002c0cd  nop     dword ptr [rax+rax+00h]
0x14002c0d2  mov     rcx, [rbx]; DeviceObject
0x14002c0d5  call    cs:__imp_IoDeleteDevice
0x14002c0dc  nop     dword ptr [rax+rax+00h]
0x14002c0e1  mov     rcx, cs:qword_1400194D8; ThreadHandle
0x14002c0e8  test    rcx, rcx
0x14002c0eb  jz      short loc_14002C124
0x14002c0ed  call    cs:__imp_ZwAlertThread
0x14002c0f4  nop     dword ptr [rax+rax+00h]
0x14002c0f9  mov     rcx, cs:qword_1400194D8; Handle
0x14002c100  xor     r8d, r8d; Timeout
0x14002c103  xor     edx, edx; Alertable
0x14002c105  call    cs:__imp_ZwWaitForSingleObject
0x14002c10c  nop     dword ptr [rax+rax+00h]
0x14002c111  mov     rcx, cs:qword_1400194D8; Handle
0x14002c118  call    cs:__imp_ZwClose
0x14002c11f  nop     dword ptr [rax+rax+00h]
0x14002c124  mov     rcx, cs:EventHandle; Handle
0x14002c12b  test    rcx, rcx
0x14002c12e  jz      short loc_14002C13C
0x14002c130  call    cs:__imp_ZwClose
0x14002c137  nop     dword ptr [rax+rax+00h]
0x14002c13c  mov     rcx, cs:EdppPurgeWnfEvtHandle
0x14002c143  mov     cs:EdppShuttingDown, 1
0x14002c14a  test    rcx, rcx
0x14002c14d  jz      short loc_14002C15B
0x14002c14f  call    cs:__imp_ExUnsubscribeWnfStateChange
0x14002c156  nop     dword ptr [rax+rax+00h]
0x14002c15b  xor     edx, edx
0x14002c15d  lea     rcx, EdppAuditSessionLock
0x14002c164  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002c16b  nop     dword ptr [rax+rax+00h]
0x14002c170  cmp     cs:EdppAuditEnabled, 0
0x14002c177  jz      short loc_14002C190
0x14002c179  lea     rcx, EdppDisableAudit
0x14002c180  call    EdppDoWorkAsSystem
0x14002c185  test    eax, eax
0x14002c187  js      short loc_14002C190
0x14002c189  mov     cs:EdppAuditEnabled, 0
0x14002c190  xor     edx, edx
0x14002c192  lea     rcx, EdppAuditSessionLock
0x14002c199  call    cs:__imp_ExReleasePushLockEx
0x14002c1a0  nop     dword ptr [rax+rax+00h]
0x14002c1a5  lea     rcx, byte_140019508
0x14002c1ac  call    EdpFreePluginConfig
0x14002c1b1  xor     eax, eax
0x14002c1b3  add     rsp, 30h
0x14002c1b7  pop     rbx
0x14002c1b8  retn
```
