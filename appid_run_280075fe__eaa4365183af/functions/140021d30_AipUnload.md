# AipUnload

- ea: `0x140021d30`
- end: `0x14002204e`
- name: `AipUnload`
- size: `798`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x14003825c`

## callees

- `0x140001010`
- `0x140001044`
- `0x140006a20`
- `0x140021b50`
- `0x140021d30`
- `0x140022100`
- `0x14002318c`
- `0x1400252dc`
- `0x140025f90`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140022017`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140022017`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140021ff8`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140021ff8`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f94`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021fb6`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f94`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021fb6`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140021f81`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140021f81`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140021f57`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140021f57`
- `ntoskrnl!EtwUnregister` at `0x140021f3b`
- `ntoskrnl!EtwUnregister` at `0x140021fd4`
- `ntoskrnl!EtwUnregister` at `0x140021f3b`
- `ntoskrnl!EtwUnregister` at `0x140021fd4`
- `ntoskrnl!IoDeleteDevice` at `0x140021dca`
- `ntoskrnl!IoDeleteDevice` at `0x140021dca`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140021dac`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140021dac`
- `ntoskrnl!ZwClose` at `0x140021d94`
- `ntoskrnl!ZwClose` at `0x140021d94`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x140021d76`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x140021d76`

## pseudocode

```c
__int64 AipUnload()
{
  PVOID DeviceExtension; // rcx
  int v1; // r8d
  int v2; // r9d
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rcx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  REGHANDLE v9; // rcx
  __int64 result; // rax
  unsigned __int64 v11; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int64 v12; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+40h] [rbp-9h] BYREF
  __int64 v14[4]; // [rsp+50h] [rbp+7h] BYREF
  unsigned __int64 *v15; // [rsp+70h] [rbp+27h]
  __int64 v16; // [rsp+78h] [rbp+2Fh]
  unsigned __int64 *v17; // [rsp+80h] [rbp+37h]
  __int64 v18; // [rsp+88h] [rbp+3Fh]

  *(_QWORD *)&SymbolicLinkName.Length = 1310738;
  SymbolicLinkName.Buffer = L"\\??\\AppID";
  if ( *(_DWORD *)&WPP_MAIN_CB.StackSize )
  {
    PsSetCreateProcessNotifyRoutineEx(AiProcessNotifyRoutine, 1u);
    *(_DWORD *)&WPP_MAIN_CB.StackSize = 0;
  }
  if ( Handle )
    ZwClose(Handle);
  if ( WPP_MAIN_CB.DeviceType )
  {
    IoDeleteSymbolicLink(&SymbolicLinkName);
    WPP_MAIN_CB.DeviceType = 0;
  }
  DeviceExtension = WPP_MAIN_CB.DeviceExtension;
  if ( WPP_MAIN_CB.DeviceExtension )
  {
    IoDeleteDevice((PDEVICE_OBJECT)WPP_MAIN_CB.DeviceExtension);
    WPP_MAIN_CB.DeviceExtension = 0;
  }
  if ( *(_QWORD *)&qword_140019628
    && (unsigned int)dword_140019000 > 4
    && (unsigned __int8)tlgKeywordOn(DeviceExtension, 0x200000000000LL) )
  {
    v16 = 8;
    v11 = (unsigned __int64)AiPerfStats / *(_QWORD *)&qword_140019628;
    v15 = &v11;
    v17 = &v12;
    v12 = *(_QWORD *)&qword_140019628;
    v18 = 8;
    tlgWriteTransfer_EtwWriteTransfer(qword_140019628, (int)&byte_140015DBD, v1, v2, 4u, (__int64)v14);
  }
  if ( *(_QWORD *)&qword_140019638
    && (unsigned int)dword_140019000 > 4
    && (unsigned __int8)tlgKeywordOn(DeviceExtension, 0x200000000000LL) )
  {
    v16 = 8;
    v12 = (unsigned __int64)qword_140019630 / *(_QWORD *)&qword_140019638;
    v15 = &v12;
    v17 = &v11;
    v11 = *(_QWORD *)&qword_140019638;
    v18 = 8;
    tlgWriteTransfer_EtwWriteTransfer(qword_140019638, (int)&byte_140015D6B, v3, v4, 4u, (__int64)v14);
  }
  SrpCleanup();
  AiServiceStopped(0);
  AiFreeLib();
  if ( (unsigned int)dword_140019000 > 4 && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    tlgWriteTransfer_EtwWriteTransfer(v6, (int)&byte_140015D49, v7, v8, 2u, (__int64)v14);
  v9 = RegHandle;
  dword_140019000 = 0;
  RegHandle = 0;
  EtwUnregister(v9);
  if ( byte_140019900 )
  {
    ExEnterCriticalRegionAndAcquireResourceExclusive((PERESOURCE)&WPP_MAIN_CB.Reserved);
    qword_1400198F8 = 0;
    xmmword_1400198E8 = 0;
    AipTrackListCleanup();
    ExReleaseResourceAndLeaveCriticalRegion((PERESOURCE)&WPP_MAIN_CB.Reserved);
    ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.Reserved);
    byte_140019900 = 0;
  }
  if ( LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink) )
  {
    ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
    LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink) = 0;
  }
  if ( WPP_MAIN_CB.Queue.ListEntry.Blink )
  {
    EtwUnregister((REGHANDLE)WPP_MAIN_CB.Queue.ListEntry.Blink);
    WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
  }
  result = WppCleanupKm();
  if ( g_wil_details_featureChangeNotification )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return result;
}

```

## disassembly

```asm
0x140021d30  mov     [rsp-8+arg_0], rdi
0x140021d35  push    rbp
0x140021d36  lea     rbp, [rsp-57h]
0x140021d3b  sub     rsp, 0A0h
0x140021d42  mov     rax, cs:__security_cookie
0x140021d49  xor     rax, rsp
0x140021d4c  mov     [rbp+57h+var_10], rax
0x140021d50  xor     edi, edi
0x140021d52  mov     qword ptr [rbp+57h+SymbolicLinkName.Length], 140012h
0x140021d5a  cmp     dword ptr cs:WPP_MAIN_CB.StackSize, edi
0x140021d60  lea     rax, aAppid; "\\??\\AppID"
0x140021d67  mov     [rbp+57h+SymbolicLinkName.Buffer], rax
0x140021d6b  jz      short loc_140021D88
0x140021d6d  mov     dl, 1; Remove
0x140021d6f  lea     rcx, AiProcessNotifyRoutine; NotifyRoutine
0x140021d76  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx
0x140021d7d  nop     dword ptr [rax+rax+00h]
0x140021d82  mov     dword ptr cs:WPP_MAIN_CB.StackSize, edi
0x140021d88  mov     rcx, cs:Handle; Handle
0x140021d8f  test    rcx, rcx
0x140021d92  jz      short loc_140021DA0
0x140021d94  call    cs:__imp_ZwClose
0x140021d9b  nop     dword ptr [rax+rax+00h]
0x140021da0  cmp     cs:WPP_MAIN_CB.DeviceType, edi
0x140021da6  jz      short loc_140021DBE
0x140021da8  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x140021dac  call    cs:__imp_IoDeleteSymbolicLink
0x140021db3  nop     dword ptr [rax+rax+00h]
0x140021db8  mov     cs:WPP_MAIN_CB.DeviceType, edi
0x140021dbe  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; DeviceObject
0x140021dc5  test    rcx, rcx
0x140021dc8  jz      short loc_140021DDD
0x140021dca  call    cs:__imp_IoDeleteDevice
0x140021dd1  nop     dword ptr [rax+rax+00h]
0x140021dd6  mov     cs:WPP_MAIN_CB.DeviceExtension, rdi
0x140021ddd  cmp     cs:qword_140019628, rdi
0x140021de4  jz      short loc_140021E5C
0x140021de6  mov     eax, cs:dword_140019000
0x140021dec  cmp     eax, 4
0x140021def  jbe     short loc_140021E5C
0x140021df1  mov     rdx, 200000000000h
0x140021dfb  call    _tlgKeywordOn
0x140021e00  test    al, al
0x140021e02  jz      short loc_140021E5C
0x140021e04  mov     rcx, cs:qword_140019628; int
0x140021e0b  xor     edx, edx
0x140021e0d  mov     rax, cs:AiPerfStats
0x140021e14  div     rcx
0x140021e17  lea     rdx, byte_140015DBD; int
0x140021e1e  mov     [rbp+57h+var_28], 8
0x140021e26  mov     [rbp+57h+var_70], rax
0x140021e2a  lea     rax, [rbp+57h+var_70]
0x140021e2e  mov     [rbp+57h+var_30], rax
0x140021e32  lea     rax, [rbp+57h+var_68]
0x140021e36  mov     [rbp+57h+var_20], rax
0x140021e3a  lea     rax, [rbp+57h+var_50]
0x140021e3e  mov     [rsp+0A0h+var_78], rax; __int64
0x140021e43  mov     [rsp+0A0h+var_80], 4; ULONG
0x140021e4b  mov     [rbp+57h+var_68], rcx
0x140021e4f  mov     [rbp+57h+var_18], 8
0x140021e57  call    _tlgWriteTransfer_EtwWriteTransfer
0x140021e5c  cmp     cs:qword_140019638, rdi
0x140021e63  jz      short loc_140021EDB
0x140021e65  mov     eax, cs:dword_140019000
0x140021e6b  cmp     eax, 4
0x140021e6e  jbe     short loc_140021EDB
0x140021e70  mov     rdx, 200000000000h
0x140021e7a  call    _tlgKeywordOn
0x140021e7f  test    al, al
0x140021e81  jz      short loc_140021EDB
0x140021e83  mov     rcx, cs:qword_140019638; int
0x140021e8a  xor     edx, edx
0x140021e8c  mov     rax, cs:qword_140019630
0x140021e93  div     rcx
0x140021e96  lea     rdx, byte_140015D6B; int
0x140021e9d  mov     [rbp+57h+var_28], 8
0x140021ea5  mov     [rbp+57h+var_68], rax
0x140021ea9  lea     rax, [rbp+57h+var_68]
0x140021ead  mov     [rbp+57h+var_30], rax
0x140021eb1  lea     rax, [rbp+57h+var_70]
0x140021eb5  mov     [rbp+57h+var_20], rax
0x140021eb9  lea     rax, [rbp+57h+var_50]
0x140021ebd  mov     [rsp+0A0h+var_78], rax; __int64
0x140021ec2  mov     [rsp+0A0h+var_80], 4; ULONG
0x140021eca  mov     [rbp+57h+var_70], rcx
0x140021ece  mov     [rbp+57h+var_18], 8
0x140021ed6  call    _tlgWriteTransfer_EtwWriteTransfer
0x140021edb  call    SrpCleanup
0x140021ee0  xor     ecx, ecx
0x140021ee2  call    AiServiceStopped
0x140021ee7  call    AiFreeLib
0x140021eec  mov     eax, cs:dword_140019000
0x140021ef2  cmp     eax, 4
0x140021ef5  jbe     short loc_140021F27
0x140021ef7  mov     rdx, 400000000000h
0x140021f01  call    _tlgKeywordOn
0x140021f06  test    al, al
0x140021f08  jz      short loc_140021F27
0x140021f0a  lea     rax, [rbp+57h+var_50]
0x140021f0e  mov     [rsp+0A0h+var_78], rax; __int64
0x140021f13  lea     rdx, byte_140015D49; int
0x140021f1a  mov     [rsp+0A0h+var_80], 2; ULONG
0x140021f22  call    _tlgWriteTransfer_EtwWriteTransfer
0x140021f27  mov     rcx, cs:RegHandle; RegHandle
0x140021f2e  mov     cs:dword_140019000, edi
0x140021f34  mov     cs:RegHandle, rdi
0x140021f3b  call    cs:__imp_EtwUnregister
0x140021f42  nop     dword ptr [rax+rax+00h]
0x140021f47  cmp     cs:byte_140019900, dil
0x140021f4e  jz      short loc_140021FA7
0x140021f50  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x140021f57  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140021f5e  nop     dword ptr [rax+rax+00h]
0x140021f63  xorps   xmm0, xmm0
0x140021f66  mov     cs:qword_1400198F8, rdi
0x140021f6d  movdqu  cs:xmmword_1400198E8, xmm0
0x140021f75  call    AipTrackListCleanup
0x140021f7a  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x140021f81  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140021f88  nop     dword ptr [rax+rax+00h]
0x140021f8d  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x140021f94  call    cs:__imp_ExDeleteResourceLite
0x140021f9b  nop     dword ptr [rax+rax+00h]
0x140021fa0  mov     cs:byte_140019900, dil
0x140021fa7  cmp     dword ptr cs:WPP_MAIN_CB.Queue, edi
0x140021fad  jz      short loc_140021FC8
0x140021faf  lea     rcx, WPP_MAIN_CB.Queue+10h; Resource
0x140021fb6  call    cs:__imp_ExDeleteResourceLite
0x140021fbd  nop     dword ptr [rax+rax+00h]
0x140021fc2  mov     dword ptr cs:WPP_MAIN_CB.Queue, edi
0x140021fc8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8; RegHandle
0x140021fcf  test    rcx, rcx
0x140021fd2  jz      short loc_140021FE7
0x140021fd4  call    cs:__imp_EtwUnregister
0x140021fdb  nop     dword ptr [rax+rax+00h]
0x140021fe0  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rdi
0x140021fe7  call    WppCleanupKm
0x140021fec  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140021ff3  test    rcx, rcx
0x140021ff6  jz      short loc_14002200B
0x140021ff8  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140021fff  nop     dword ptr [rax+rax+00h]
0x140022004  mov     cs:g_wil_details_featureChangeNotification, rdi
0x14002200b  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140022012  test    rcx, rcx
0x140022015  jz      short loc_14002202A
0x140022017  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14002201e  nop     dword ptr [rax+rax+00h]
0x140022023  mov     cs:g_wil_details_featureUsageProvider, rdi
0x14002202a  mov     cs:g_wil_details_isFeatureStagingInitialized, edi
0x140022030  mov     rcx, [rbp+57h+var_10]
0x140022034  xor     rcx, rsp; StackCookie
0x140022037  call    __security_check_cookie
0x14002203c  mov     rdi, [rsp+0A0h+arg_0]
0x140022044  add     rsp, 0A0h
0x14002204b  pop     rbp
0x14002204c  retn
```
