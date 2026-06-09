# AfdUnload

- ea: `0x14004a7d0`
- end: `0x14004abac`
- name: `AfdUnload`
- size: `988`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140015ae0`
- `0x14003f124`
- `0x14003f254`
- `0x140042a74`
- `0x14004963c`
- `0x140049aa0`
- `0x14004a7d0`
- `0x14004b5f0`
- `0x140050254`
- `0x140052704`
- `0x14005e044`
- `0x14005e258`
- `0x140067240`
- `0x140067608`
- `0x14006dde4`
- `0x14006df50`
- `0x140092408`
- `0x140092440`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14004a874`
- `ntoskrnl!KeInitializeEvent` at `0x14004a874`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004a8d0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004a8d0`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004a9c7`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004a9c7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004a9b4`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004a9b4`
- `ntoskrnl!IoDeleteDevice` at `0x14004ab23`
- `ntoskrnl!IoDeleteDevice` at `0x14004ab23`
- `ntoskrnl!EtwUnregister` at `0x14004ab5f`
- `ntoskrnl!EtwUnregister` at `0x14004ab5f`
- `ntoskrnl!ExUnregisterCallback` at `0x14004a8fb`
- `ntoskrnl!ExUnregisterCallback` at `0x14004a8fb`
- `ntoskrnl!ZwClose` at `0x14004a855`
- `ntoskrnl!ZwClose` at `0x14004a855`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004a893`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004a893`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14004a842`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14004a842`
- `ntoskrnl!ObfDereferenceObject` at `0x14004a90e`
- `ntoskrnl!ObfDereferenceObject` at `0x14004a90e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a940`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a9df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a940`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a9df`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x14004ab4c`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x14004ab4c`
- `NETIO!NetioNrtStop` at `0x14004ab2f`
- `NETIO!NetioNrtStop` at `0x14004ab2f`
- `NETIO!NetioTimerWorkItemShutdown` at `0x14004a9f9`
- `NETIO!NetioTimerWorkItemShutdown` at `0x14004a9f9`

## pseudocode

```c
__int64 AfdUnload()
{
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v1; // rcx
  __int64 v2; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( (BYTE10(xmmword_1400875E0) & 0x10) != 0 )
    WPP_SF_(1300, 12, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
  if ( (Feature_4431_4260__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_4431_4260__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_4431_4260__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
    AfdDnskStopProviderModule();
  AfdWskStopProviderModule();
  if ( AfdParametersNotifyHandle )
  {
    ExEnterCriticalRegionAndAcquireResourceExclusive(AfdGlobalData);
    ZwClose(AfdParametersNotifyHandle);
    AfdParametersNotifyHandle = 0;
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    AfdParametersUnloadEvent = &Event;
    ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
    if ( (BYTE10(xmmword_1400875E0) & 0x10) != 0 )
      WPP_SF_(1300, 13, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
  AfdPodDeinit();
  AfdStopTimerWheel();
  AfdTlStopClientModule();
  if ( AfdTdxCallbackObject )
  {
    ExUnregisterCallback(AfdTdxCallbackRegistration);
    ObfDereferenceObject(AfdTdxCallbackObject);
  }
  if ( AfdDefaultCompartment )
  {
    AfdDereferenceCompartment((volatile signed __int32 *)AfdDefaultCompartment);
    AfdDefaultCompartment = 0;
  }
  if ( AfdAdminSecurityDescriptor )
  {
    ExFreePoolWithTag(AfdAdminSecurityDescriptor, 0);
    AfdAdminSecurityDescriptor = 0;
  }
  AfdTdiStop();
  AfdEtwUnRegisterLog();
  while ( 1 )
  {
    v1 = AfdTransportInfoListHead;
    if ( (__int64 *)AfdTransportInfoListHead == &AfdTransportInfoListHead )
      break;
    if ( *(__int64 **)(AfdTransportInfoListHead + 8) != &AfdTransportInfoListHead
      || (v2 = *(_QWORD *)AfdTransportInfoListHead,
          *(_QWORD *)(*(_QWORD *)AfdTransportInfoListHead + 8LL) != AfdTransportInfoListHead) )
    {
      __fastfail(3u);
    }
    AfdTransportInfoListHead = *(_QWORD *)AfdTransportInfoListHead;
    *(_QWORD *)(v2 + 8) = &AfdTransportInfoListHead;
    *(_QWORD *)(v1 + 8) = v1;
    *(_QWORD *)v1 = v1;
    AfdDereferenceTransport((volatile signed __int64 *)v1);
  }
  AfdTerminateGroup();
  if ( AfdGlobalData )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&AfdGlobalData[1].ActiveCount);
    ExDeleteResourceLite(AfdGlobalData);
    ExFreePoolWithTag(AfdGlobalData, 0x72646641u);
    AfdGlobalData = 0;
  }
  NetioTimerWorkItemShutdown(AfdTrimLookasidesWorkItem);
  if ( PplConnectionPool )
  {
    PplDestroyLookasideList(PplConnectionPool, 0x43646641u);
    PplConnectionPool = 0;
  }
  if ( PplEndpointPool )
  {
    PplDestroyLookasideList(PplEndpointPool, 0x45646641u);
    PplEndpointPool = 0;
  }
  if ( PplTditlEndpointPool )
  {
    PplDestroyLookasideList(PplTditlEndpointPool, 0x45646641u);
    PplTditlEndpointPool = 0;
  }
  if ( WskProPplSocket )
  {
    PplDestroyLookasideList(WskProPplSocket, 0x734B5357u);
    WskProPplSocket = 0;
  }
  if ( PplAddressPool )
  {
    PplDestroyLookasideList(PplAddressPool, 0x52646641u);
    PplAddressPool = 0;
  }
  if ( AfdPplBufferTagPool )
  {
    PplDestroyLookasideList(AfdPplBufferTagPool, 0x42646641u);
    AfdPplBufferTagPool = 0;
  }
  if ( AfdPplHugeBufferPool )
  {
    PplDestroyLookasideList(AfdPplHugeBufferPool, 0x42646641u);
    AfdPplHugeBufferPool = 0;
  }
  if ( AfdPplLargeBufferPool )
  {
    PplDestroyLookasideList(AfdPplLargeBufferPool, 0x42646641u);
    AfdPplLargeBufferPool = 0;
  }
  if ( AfdPplMediumBufferPool )
  {
    PplDestroyLookasideList(AfdPplMediumBufferPool, 0x42646641u);
    AfdPplMediumBufferPool = 0;
  }
  if ( AfdPplSmallBufferPool )
  {
    PplDestroyLookasideList(AfdPplSmallBufferPool, 0x42646641u);
    AfdPplSmallBufferPool = 0;
  }
  IoDeleteDevice((PDEVICE_OBJECT)AfdDeviceObject);
  NetioNrtStop();
  AfdTdiDeInit();
  AfdPcwCleanup();
  NetioDeregisterTriageDumpDataCallback(qword_140087750);
  EtwUnregister(FastWppRegHandle);
  FastWppRegHandle = 0;
  FastWppCallback(0, 0, 0, 0, 0, 0, 0);
  FastWppInitState = 0;
  TraceLoggingUnregister_EtwUnregister();
  return wil_UninitializeFeatureStaging();
}

```

## disassembly

```asm
0x14004a7d0  mov     [rsp+arg_0], rbx
0x14004a7d5  push    rdi
0x14004a7d6  sub     rsp, 60h
0x14004a7da  xorps   xmm0, xmm0
0x14004a7dd  xor     eax, eax
0x14004a7df  movups  xmmword ptr [rsp+68h+Event.Header], xmm0
0x14004a7e4  mov     [rsp+68h+Event.Header.WaitListHead.Blink], rax
0x14004a7e9  mov     dil, 10h
0x14004a7ec  test    byte ptr cs:xmmword_1400875E0+0Ah, dil
0x14004a7f3  jz      short loc_14004A809
0x14004a7f5  lea     edx, [rax+0Ch]
0x14004a7f8  mov     ecx, 514h
0x14004a7fd  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x14004a804  call    WPP_SF_
0x14004a809  mov     eax, cs:Feature_4431_4260__private_featureState
0x14004a80f  test    dil, al
0x14004a812  jz      short loc_14004A819
0x14004a814  and     eax, 1
0x14004a817  jmp     short loc_14004A81E
0x14004a819  call    Feature_4431_4260__private_IsEnabledDeviceUsageNoInline
0x14004a81e  xor     ebx, ebx
0x14004a820  test    eax, eax
0x14004a822  jz      short loc_14004A829
0x14004a824  call    AfdDnskStopProviderModule
0x14004a829  call    AfdWskStopProviderModule
0x14004a82e  cmp     cs:AfdParametersNotifyHandle, rbx
0x14004a835  jz      loc_14004A8DC
0x14004a83b  mov     rcx, cs:AfdGlobalData; Resource
0x14004a842  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14004a849  nop     dword ptr [rax+rax+00h]
0x14004a84e  mov     rcx, cs:AfdParametersNotifyHandle; Handle
0x14004a855  call    cs:__imp_ZwClose
0x14004a85c  nop     dword ptr [rax+rax+00h]
0x14004a861  xor     r8d, r8d; State
0x14004a864  mov     cs:AfdParametersNotifyHandle, rbx
0x14004a86b  lea     rcx, [rsp+68h+Event]; Event
0x14004a870  lea     edx, [r8+1]; Type
0x14004a874  call    cs:__imp_KeInitializeEvent
0x14004a87b  nop     dword ptr [rax+rax+00h]
0x14004a880  mov     rcx, cs:AfdGlobalData; Resource
0x14004a887  lea     rax, [rsp+68h+Event]
0x14004a88c  mov     cs:AfdParametersUnloadEvent, rax
0x14004a893  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14004a89a  nop     dword ptr [rax+rax+00h]
0x14004a89f  test    byte ptr cs:xmmword_1400875E0+0Ah, dil
0x14004a8a6  jz      short loc_14004A8BE
0x14004a8a8  mov     edx, 0Dh
0x14004a8ad  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x14004a8b4  mov     ecx, 514h
0x14004a8b9  call    WPP_SF_
0x14004a8be  xor     r9d, r9d; Alertable
0x14004a8c1  mov     [rsp+68h+Timeout], rbx; Timeout
0x14004a8c6  xor     r8d, r8d; WaitMode
0x14004a8c9  lea     rcx, [rsp+68h+Event]; Object
0x14004a8ce  xor     edx, edx; WaitReason
0x14004a8d0  call    cs:__imp_KeWaitForSingleObject
0x14004a8d7  nop     dword ptr [rax+rax+00h]
0x14004a8dc  call    AfdPodDeinit
0x14004a8e1  call    AfdStopTimerWheel
0x14004a8e6  call    AfdTlStopClientModule
0x14004a8eb  cmp     cs:AfdTdxCallbackObject, rbx
0x14004a8f2  jz      short loc_14004A91A
0x14004a8f4  mov     rcx, cs:AfdTdxCallbackRegistration; CallbackRegistration
0x14004a8fb  call    cs:__imp_ExUnregisterCallback
0x14004a902  nop     dword ptr [rax+rax+00h]
0x14004a907  mov     rcx, cs:AfdTdxCallbackObject; Object
0x14004a90e  call    cs:__imp_ObfDereferenceObject
0x14004a915  nop     dword ptr [rax+rax+00h]
0x14004a91a  mov     rcx, cs:AfdDefaultCompartment; P
0x14004a921  test    rcx, rcx
0x14004a924  jz      short loc_14004A932
0x14004a926  call    AfdDereferenceCompartment
0x14004a92b  mov     cs:AfdDefaultCompartment, rbx
0x14004a932  mov     rcx, cs:AfdAdminSecurityDescriptor; P
0x14004a939  test    rcx, rcx
0x14004a93c  jz      short loc_14004A953
0x14004a93e  xor     edx, edx; Tag
0x14004a940  call    cs:__imp_ExFreePoolWithTag
0x14004a947  nop     dword ptr [rax+rax+00h]
0x14004a94c  mov     cs:AfdAdminSecurityDescriptor, rbx
0x14004a953  call    AfdTdiStop
0x14004a958  call    AfdEtwUnRegisterLog
0x14004a95d  lea     rdi, AfdTransportInfoListHead
0x14004a964  mov     rcx, cs:AfdTransportInfoListHead
0x14004a96b  cmp     rcx, rdi
0x14004a96e  jz      short loc_14004A99F
0x14004a970  cmp     [rcx+8], rdi
0x14004a974  jnz     short loc_14004A998
0x14004a976  mov     rax, [rcx]
0x14004a979  cmp     [rax+8], rcx
0x14004a97d  jnz     short loc_14004A998
0x14004a97f  mov     cs:AfdTransportInfoListHead, rax
0x14004a986  mov     [rax+8], rdi
0x14004a98a  mov     [rcx+8], rcx
0x14004a98e  mov     [rcx], rcx
0x14004a991  call    AfdDereferenceTransport
0x14004a996  jmp     short loc_14004A964
0x14004a998  mov     ecx, 3
0x14004a99d  int     29h; Win8: RtlFailFast(ecx)
0x14004a99f  call    AfdTerminateGroup
0x14004a9a4  mov     rcx, cs:AfdGlobalData
0x14004a9ab  test    rcx, rcx
0x14004a9ae  jz      short loc_14004A9F2
0x14004a9b0  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14004a9b4  call    cs:__imp_ExDeleteNPagedLookasideList
0x14004a9bb  nop     dword ptr [rax+rax+00h]
0x14004a9c0  mov     rcx, cs:AfdGlobalData; Resource
0x14004a9c7  call    cs:__imp_ExDeleteResourceLite
0x14004a9ce  nop     dword ptr [rax+rax+00h]
0x14004a9d3  mov     rcx, cs:AfdGlobalData; P
0x14004a9da  mov     edx, 72646641h; Tag
0x14004a9df  call    cs:__imp_ExFreePoolWithTag
0x14004a9e6  nop     dword ptr [rax+rax+00h]
0x14004a9eb  mov     cs:AfdGlobalData, rbx
0x14004a9f2  lea     rcx, AfdTrimLookasidesWorkItem
0x14004a9f9  call    cs:__imp_NetioTimerWorkItemShutdown
0x14004aa00  nop     dword ptr [rax+rax+00h]
0x14004aa05  mov     rcx, cs:PplConnectionPool; P
0x14004aa0c  test    rcx, rcx
0x14004aa0f  jz      short loc_14004AA22
0x14004aa11  mov     edx, 43646641h; Tag
0x14004aa16  call    PplDestroyLookasideList
0x14004aa1b  mov     cs:PplConnectionPool, rbx
0x14004aa22  mov     rcx, cs:PplEndpointPool; P
0x14004aa29  mov     edi, 45646641h
0x14004aa2e  test    rcx, rcx
0x14004aa31  jz      short loc_14004AA41
0x14004aa33  mov     edx, edi; Tag
0x14004aa35  call    PplDestroyLookasideList
0x14004aa3a  mov     cs:PplEndpointPool, rbx
0x14004aa41  mov     rcx, cs:PplTditlEndpointPool; P
0x14004aa48  test    rcx, rcx
0x14004aa4b  jz      short loc_14004AA5B
0x14004aa4d  mov     edx, edi; Tag
0x14004aa4f  call    PplDestroyLookasideList
0x14004aa54  mov     cs:PplTditlEndpointPool, rbx
0x14004aa5b  mov     rcx, cs:WskProPplSocket; P
0x14004aa62  test    rcx, rcx
0x14004aa65  jz      short loc_14004AA78
0x14004aa67  mov     edx, 734B5357h; Tag
0x14004aa6c  call    PplDestroyLookasideList
0x14004aa71  mov     cs:WskProPplSocket, rbx
0x14004aa78  mov     rcx, cs:PplAddressPool; P
0x14004aa7f  test    rcx, rcx
0x14004aa82  jz      short loc_14004AA95
0x14004aa84  mov     edx, 52646641h; Tag
0x14004aa89  call    PplDestroyLookasideList
0x14004aa8e  mov     cs:PplAddressPool, rbx
0x14004aa95  mov     rcx, cs:AfdPplBufferTagPool; P
0x14004aa9c  mov     edi, 42646641h
0x14004aaa1  test    rcx, rcx
0x14004aaa4  jz      short loc_14004AAB4
0x14004aaa6  mov     edx, edi; Tag
0x14004aaa8  call    PplDestroyLookasideList
0x14004aaad  mov     cs:AfdPplBufferTagPool, rbx
0x14004aab4  mov     rcx, cs:AfdPplHugeBufferPool; P
0x14004aabb  test    rcx, rcx
0x14004aabe  jz      short loc_14004AACE
0x14004aac0  mov     edx, edi; Tag
0x14004aac2  call    PplDestroyLookasideList
0x14004aac7  mov     cs:AfdPplHugeBufferPool, rbx
0x14004aace  mov     rcx, cs:AfdPplLargeBufferPool; P
0x14004aad5  test    rcx, rcx
0x14004aad8  jz      short loc_14004AAE8
0x14004aada  mov     edx, edi; Tag
0x14004aadc  call    PplDestroyLookasideList
0x14004aae1  mov     cs:AfdPplLargeBufferPool, rbx
0x14004aae8  mov     rcx, cs:AfdPplMediumBufferPool; P
0x14004aaef  test    rcx, rcx
0x14004aaf2  jz      short loc_14004AB02
0x14004aaf4  mov     edx, edi; Tag
0x14004aaf6  call    PplDestroyLookasideList
0x14004aafb  mov     cs:AfdPplMediumBufferPool, rbx
0x14004ab02  mov     rcx, cs:AfdPplSmallBufferPool; P
0x14004ab09  test    rcx, rcx
0x14004ab0c  jz      short loc_14004AB1C
0x14004ab0e  mov     edx, edi; Tag
0x14004ab10  call    PplDestroyLookasideList
0x14004ab15  mov     cs:AfdPplSmallBufferPool, rbx
0x14004ab1c  mov     rcx, cs:AfdDeviceObject; DeviceObject
0x14004ab23  call    cs:__imp_IoDeleteDevice
0x14004ab2a  nop     dword ptr [rax+rax+00h]
0x14004ab2f  call    cs:__imp_NetioNrtStop
0x14004ab36  nop     dword ptr [rax+rax+00h]
0x14004ab3b  call    AfdTdiDeInit
0x14004ab40  call    AfdPcwCleanup
0x14004ab45  lea     rcx, qword_140087750
0x14004ab4c  call    cs:__imp_NetioDeregisterTriageDumpDataCallback
0x14004ab53  nop     dword ptr [rax+rax+00h]
0x14004ab58  mov     rcx, cs:FastWppRegHandle; RegHandle
0x14004ab5f  call    cs:__imp_EtwUnregister
0x14004ab66  nop     dword ptr [rax+rax+00h]
0x14004ab6b  mov     [rsp+68h+CallbackContext], rbx; CallbackContext
0x14004ab70  xor     r9d, r9d; MatchAnyKeyword
0x14004ab73  mov     [rsp+68h+FilterData], rbx; FilterData
0x14004ab78  xor     r8d, r8d; Level
0x14004ab7b  xor     edx, edx; ControlCode
0x14004ab7d  mov     [rsp+68h+Timeout], rbx; MatchAllKeyword
0x14004ab82  xor     ecx, ecx; SourceId
0x14004ab84  mov     cs:FastWppRegHandle, rbx
0x14004ab8b  call    FastWppCallback
0x14004ab90  mov     cs:FastWppInitState, ebx
0x14004ab96  call    TraceLoggingUnregister_EtwUnregister
0x14004ab9b  call    wil_UninitializeFeatureStaging
0x14004aba0  mov     rbx, [rsp+68h+arg_0]
0x14004aba5  add     rsp, 60h
0x14004aba9  pop     rdi
0x14004abaa  retn
```
