# SrpCleanup

- ea: `0x14002318c`
- end: `0x1400232c2`
- name: `SrpCleanup`
- size: `310`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting, installer_update`

## callers

- `0x140021d30`
- `0x1400387a4`

## callees

- `0x14002318c`
- `0x140024044`
- `0x140024218`
- `0x140036e80`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140023278`
- `ntoskrnl!ObfDereferenceObject` at `0x140023278`
- `ntoskrnl!ExUnregisterCallback` at `0x140023255`
- `ntoskrnl!ExUnregisterCallback` at `0x140023255`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400231c1`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400231d4`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400231c1`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400231d4`
- `ntoskrnl!EtwUnregister` at `0x14002329b`
- `ntoskrnl!EtwUnregister` at `0x14002329b`
- `ntoskrnl!IoDeleteDevice` at `0x140023232`
- `ntoskrnl!IoDeleteDevice` at `0x140023232`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140023210`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140023210`

## pseudocode

```c
void SrpCleanup()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+20h] [rbp-18h] BYREF

  SymbolicLinkName.Buffer = L"\\??\\SrpDevice";
  *(_QWORD *)&SymbolicLinkName.Length = 1835034;
  if ( byte_1400193F0 )
  {
    ReplacePolicyRef(0);
    SrpPolicyTransactionRollback(v1, v0);
    ExDeleteResourceLite(&Resource);
    ExDeleteResourceLite(&stru_140019300);
    byte_1400193F0 = 0;
  }
  AipForEachPlugin(AipCleanupPluginsCallback, 0);
  if ( g_Srp )
  {
    if ( dword_1400196F0 )
    {
      IoDeleteSymbolicLink(&SymbolicLinkName);
      dword_1400196F0 = 0;
    }
    if ( DeviceObject )
    {
      IoDeleteDevice(DeviceObject);
      DeviceObject = 0;
    }
    if ( CallbackRegistration )
    {
      ExUnregisterCallback(CallbackRegistration);
      CallbackRegistration = 0;
    }
    if ( CallbackObject )
    {
      ObfDereferenceObject(CallbackObject);
      CallbackObject = 0;
    }
    if ( qword_1400196F8 )
    {
      EtwUnregister(qword_1400196F8);
      qword_1400196F8 = 0;
    }
    g_Srp = 0;
  }
}

```

## disassembly

```asm
0x14002318c  sub     rsp, 38h
0x140023190  cmp     cs:byte_1400193F0, 0
0x140023197  lea     rax, aSrpdevice; "\\??\\SrpDevice"
0x14002319e  mov     [rsp+38h+SymbolicLinkName.Buffer], rax
0x1400231a3  mov     qword ptr [rsp+38h+SymbolicLinkName.Length], 1C001Ah
0x1400231ac  jz      short loc_1400231E7
0x1400231ae  xor     ecx, ecx
0x1400231b0  call    ReplacePolicyRef
0x1400231b5  call    SrpPolicyTransactionRollback
0x1400231ba  lea     rcx, Resource; Resource
0x1400231c1  call    cs:__imp_ExDeleteResourceLite
0x1400231c8  nop     dword ptr [rax+rax+00h]
0x1400231cd  lea     rcx, stru_140019300; Resource
0x1400231d4  call    cs:__imp_ExDeleteResourceLite
0x1400231db  nop     dword ptr [rax+rax+00h]
0x1400231e0  mov     cs:byte_1400193F0, 0
0x1400231e7  xor     edx, edx
0x1400231e9  lea     rcx, AipCleanupPluginsCallback
0x1400231f0  call    AipForEachPlugin
0x1400231f5  cmp     cs:g_Srp, 0
0x1400231fc  jz      loc_1400232BC
0x140023202  cmp     cs:dword_1400196F0, 0
0x140023209  jz      short loc_140023226
0x14002320b  lea     rcx, [rsp+38h+SymbolicLinkName]; SymbolicLinkName
0x140023210  call    cs:__imp_IoDeleteSymbolicLink
0x140023217  nop     dword ptr [rax+rax+00h]
0x14002321c  mov     cs:dword_1400196F0, 0
0x140023226  mov     rcx, cs:DeviceObject; DeviceObject
0x14002322d  test    rcx, rcx
0x140023230  jz      short loc_140023249
0x140023232  call    cs:__imp_IoDeleteDevice
0x140023239  nop     dword ptr [rax+rax+00h]
0x14002323e  mov     cs:DeviceObject, 0
0x140023249  mov     rcx, cs:CallbackRegistration; CallbackRegistration
0x140023250  test    rcx, rcx
0x140023253  jz      short loc_14002326C
0x140023255  call    cs:__imp_ExUnregisterCallback
0x14002325c  nop     dword ptr [rax+rax+00h]
0x140023261  mov     cs:CallbackRegistration, 0
0x14002326c  mov     rcx, cs:CallbackObject; Object
0x140023273  test    rcx, rcx
0x140023276  jz      short loc_14002328F
0x140023278  call    cs:__imp_ObfDereferenceObject
0x14002327f  nop     dword ptr [rax+rax+00h]
0x140023284  mov     cs:CallbackObject, 0
0x14002328f  mov     rcx, cs:qword_1400196F8; RegHandle
0x140023296  test    rcx, rcx
0x140023299  jz      short loc_1400232B2
0x14002329b  call    cs:__imp_EtwUnregister
0x1400232a2  nop     dword ptr [rax+rax+00h]
0x1400232a7  mov     cs:qword_1400196F8, 0
0x1400232b2  mov     cs:g_Srp, 0
0x1400232bc  add     rsp, 38h
0x1400232c0  retn
```
