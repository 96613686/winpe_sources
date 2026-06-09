# AfdUnload

- ea: `0x14004a870`
- end: `0x14004ac4c`
- name: `AfdUnload`
- size: `988`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140015ae0`
- `0x14003f144`
- `0x14003f274`
- `0x140042a94`
- `0x1400496dc`
- `0x140049b40`
- `0x14004a870`
- `0x14004b690`
- `0x1400502f4`
- `0x1400527a4`
- `0x14005e1e4`
- `0x14005e3f8`
- `0x1400673e0`
- `0x1400677a8`
- `0x14006df84`
- `0x14006e0f0`
- `0x140092408`
- `0x140092440`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14004a914`
- `ntoskrnl!KeInitializeEvent` at `0x14004a914`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004a970`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004a970`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004aa67`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004aa67`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004aa54`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004aa54`
- `ntoskrnl!IoDeleteDevice` at `0x14004abc3`
- `ntoskrnl!IoDeleteDevice` at `0x14004abc3`
- `ntoskrnl!EtwUnregister` at `0x14004abff`
- `ntoskrnl!EtwUnregister` at `0x14004abff`
- `ntoskrnl!ExUnregisterCallback` at `0x14004a99b`
- `ntoskrnl!ExUnregisterCallback` at `0x14004a99b`
- `ntoskrnl!ZwClose` at `0x14004a8f5`
- `ntoskrnl!ZwClose` at `0x14004a8f5`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004a933`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004a933`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14004a8e2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14004a8e2`
- `ntoskrnl!ObfDereferenceObject` at `0x14004a9ae`
- `ntoskrnl!ObfDereferenceObject` at `0x14004a9ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a9e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004aa7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a9e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004aa7f`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x14004abec`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x14004abec`
- `NETIO!NetioNrtStop` at `0x14004abcf`
- `NETIO!NetioNrtStop` at `0x14004abcf`
- `NETIO!NetioTimerWorkItemShutdown` at `0x14004aa99`
- `NETIO!NetioTimerWorkItemShutdown` at `0x14004aa99`

## pseudocode

```c
__int64 AfdUnload()
{
  int IsEnabledDeviceUsageNoInline; // eax
  _QWORD *v1; // rcx
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
    AfdDereferenceCompartment(AfdDefaultCompartment);
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
    v1 = (_QWORD *)AfdTransportInfoListHead;
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
    v1[1] = v1;
    *v1 = v1;
    AfdDereferenceTransport(v1);
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
0x14004a870  mov     [rsp+arg_0], rbx
0x14004a875  push    rdi
0x14004a876  sub     rsp, 60h
0x14004a87a  xorps   xmm0, xmm0
0x14004a87d  xor     eax, eax
0x14004a87f  movups  xmmword ptr [rsp+68h+Event.Header], xmm0
0x14004a884  mov     [rsp+68h+Event.Header.WaitListHead.Blink], rax
0x14004a889  mov     dil, 10h
0x14004a88c  test    byte ptr cs:xmmword_1400875E0+0Ah, dil
0x14004a893  jz      short loc_14004A8A9
0x14004a895  lea     edx, [rax+0Ch]
0x14004a898  mov     ecx, 514h
0x14004a89d  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x14004a8a4  call    WPP_SF_
0x14004a8a9  mov     eax, cs:Feature_4431_4260__private_featureState
0x14004a8af  test    dil, al
0x14004a8b2  jz      short loc_14004A8B9
0x14004a8b4  and     eax, 1
0x14004a8b7  jmp     short loc_14004A8BE
0x14004a8b9  call    Feature_4431_4260__private_IsEnabledDeviceUsageNoInline
0x14004a8be  xor     ebx, ebx
0x14004a8c0  test    eax, eax
0x14004a8c2  jz      short loc_14004A8C9
0x14004a8c4  call    AfdDnskStopProviderModule
0x14004a8c9  call    AfdWskStopProviderModule
0x14004a8ce  cmp     cs:AfdParametersNotifyHandle, rbx
0x14004a8d5  jz      loc_14004A97C
0x14004a8db  mov     rcx, cs:AfdGlobalData; Resource
0x14004a8e2  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14004a8e9  nop     dword ptr [rax+rax+00h]
0x14004a8ee  mov     rcx, cs:AfdParametersNotifyHandle; Handle
0x14004a8f5  call    cs:__imp_ZwClose
0x14004a8fc  nop     dword ptr [rax+rax+00h]
0x14004a901  xor     r8d, r8d; State
0x14004a904  mov     cs:AfdParametersNotifyHandle, rbx
0x14004a90b  lea     rcx, [rsp+68h+Event]; Event
0x14004a910  lea     edx, [r8+1]; Type
0x14004a914  call    cs:__imp_KeInitializeEvent
0x14004a91b  nop     dword ptr [rax+rax+00h]
0x14004a920  mov     rcx, cs:AfdGlobalData; Resource
0x14004a927  lea     rax, [rsp+68h+Event]
0x14004a92c  mov     cs:AfdParametersUnloadEvent, rax
0x14004a933  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14004a93a  nop     dword ptr [rax+rax+00h]
0x14004a93f  test    byte ptr cs:xmmword_1400875E0+0Ah, dil
0x14004a946  jz      short loc_14004A95E
0x14004a948  mov     edx, 0Dh
0x14004a94d  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x14004a954  mov     ecx, 514h
0x14004a959  call    WPP_SF_
0x14004a95e  xor     r9d, r9d; Alertable
0x14004a961  mov     [rsp+68h+Timeout], rbx; Timeout
0x14004a966  xor     r8d, r8d; WaitMode
0x14004a969  lea     rcx, [rsp+68h+Event]; Object
0x14004a96e  xor     edx, edx; WaitReason
0x14004a970  call    cs:__imp_KeWaitForSingleObject
0x14004a977  nop     dword ptr [rax+rax+00h]
0x14004a97c  call    AfdPodDeinit
0x14004a981  call    AfdStopTimerWheel
0x14004a986  call    AfdTlStopClientModule
0x14004a98b  cmp     cs:AfdTdxCallbackObject, rbx
0x14004a992  jz      short loc_14004A9BA
0x14004a994  mov     rcx, cs:AfdTdxCallbackRegistration; CallbackRegistration
0x14004a99b  call    cs:__imp_ExUnregisterCallback
0x14004a9a2  nop     dword ptr [rax+rax+00h]
0x14004a9a7  mov     rcx, cs:AfdTdxCallbackObject; Object
0x14004a9ae  call    cs:__imp_ObfDereferenceObject
0x14004a9b5  nop     dword ptr [rax+rax+00h]
0x14004a9ba  mov     rcx, cs:AfdDefaultCompartment; P
0x14004a9c1  test    rcx, rcx
0x14004a9c4  jz      short loc_14004A9D2
0x14004a9c6  call    AfdDereferenceCompartment
0x14004a9cb  mov     cs:AfdDefaultCompartment, rbx
0x14004a9d2  mov     rcx, cs:AfdAdminSecurityDescriptor; P
0x14004a9d9  test    rcx, rcx
0x14004a9dc  jz      short loc_14004A9F3
0x14004a9de  xor     edx, edx; Tag
0x14004a9e0  call    cs:__imp_ExFreePoolWithTag
0x14004a9e7  nop     dword ptr [rax+rax+00h]
0x14004a9ec  mov     cs:AfdAdminSecurityDescriptor, rbx
0x14004a9f3  call    AfdTdiStop
0x14004a9f8  call    AfdEtwUnRegisterLog
0x14004a9fd  lea     rdi, AfdTransportInfoListHead
0x14004aa04  mov     rcx, cs:AfdTransportInfoListHead
0x14004aa0b  cmp     rcx, rdi
0x14004aa0e  jz      short loc_14004AA3F
0x14004aa10  cmp     [rcx+8], rdi
0x14004aa14  jnz     short loc_14004AA38
0x14004aa16  mov     rax, [rcx]
0x14004aa19  cmp     [rax+8], rcx
0x14004aa1d  jnz     short loc_14004AA38
0x14004aa1f  mov     cs:AfdTransportInfoListHead, rax
0x14004aa26  mov     [rax+8], rdi
0x14004aa2a  mov     [rcx+8], rcx
0x14004aa2e  mov     [rcx], rcx
0x14004aa31  call    AfdDereferenceTransport
0x14004aa36  jmp     short loc_14004AA04
0x14004aa38  mov     ecx, 3
0x14004aa3d  int     29h; Win8: RtlFailFast(ecx)
0x14004aa3f  call    AfdTerminateGroup
0x14004aa44  mov     rcx, cs:AfdGlobalData
0x14004aa4b  test    rcx, rcx
0x14004aa4e  jz      short loc_14004AA92
0x14004aa50  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14004aa54  call    cs:__imp_ExDeleteNPagedLookasideList
0x14004aa5b  nop     dword ptr [rax+rax+00h]
0x14004aa60  mov     rcx, cs:AfdGlobalData; Resource
0x14004aa67  call    cs:__imp_ExDeleteResourceLite
0x14004aa6e  nop     dword ptr [rax+rax+00h]
0x14004aa73  mov     rcx, cs:AfdGlobalData; P
0x14004aa7a  mov     edx, 72646641h; Tag
0x14004aa7f  call    cs:__imp_ExFreePoolWithTag
0x14004aa86  nop     dword ptr [rax+rax+00h]
0x14004aa8b  mov     cs:AfdGlobalData, rbx
0x14004aa92  lea     rcx, AfdTrimLookasidesWorkItem
0x14004aa99  call    cs:__imp_NetioTimerWorkItemShutdown
0x14004aaa0  nop     dword ptr [rax+rax+00h]
0x14004aaa5  mov     rcx, cs:PplConnectionPool; P
0x14004aaac  test    rcx, rcx
0x14004aaaf  jz      short loc_14004AAC2
0x14004aab1  mov     edx, 43646641h; Tag
0x14004aab6  call    PplDestroyLookasideList
0x14004aabb  mov     cs:PplConnectionPool, rbx
0x14004aac2  mov     rcx, cs:PplEndpointPool; P
0x14004aac9  mov     edi, 45646641h
0x14004aace  test    rcx, rcx
0x14004aad1  jz      short loc_14004AAE1
0x14004aad3  mov     edx, edi; Tag
0x14004aad5  call    PplDestroyLookasideList
0x14004aada  mov     cs:PplEndpointPool, rbx
0x14004aae1  mov     rcx, cs:PplTditlEndpointPool; P
0x14004aae8  test    rcx, rcx
0x14004aaeb  jz      short loc_14004AAFB
0x14004aaed  mov     edx, edi; Tag
0x14004aaef  call    PplDestroyLookasideList
0x14004aaf4  mov     cs:PplTditlEndpointPool, rbx
0x14004aafb  mov     rcx, cs:WskProPplSocket; P
0x14004ab02  test    rcx, rcx
0x14004ab05  jz      short loc_14004AB18
0x14004ab07  mov     edx, 734B5357h; Tag
0x14004ab0c  call    PplDestroyLookasideList
0x14004ab11  mov     cs:WskProPplSocket, rbx
0x14004ab18  mov     rcx, cs:PplAddressPool; P
0x14004ab1f  test    rcx, rcx
0x14004ab22  jz      short loc_14004AB35
0x14004ab24  mov     edx, 52646641h; Tag
0x14004ab29  call    PplDestroyLookasideList
0x14004ab2e  mov     cs:PplAddressPool, rbx
0x14004ab35  mov     rcx, cs:AfdPplBufferTagPool; P
0x14004ab3c  mov     edi, 42646641h
0x14004ab41  test    rcx, rcx
0x14004ab44  jz      short loc_14004AB54
0x14004ab46  mov     edx, edi; Tag
0x14004ab48  call    PplDestroyLookasideList
0x14004ab4d  mov     cs:AfdPplBufferTagPool, rbx
0x14004ab54  mov     rcx, cs:AfdPplHugeBufferPool; P
0x14004ab5b  test    rcx, rcx
0x14004ab5e  jz      short loc_14004AB6E
0x14004ab60  mov     edx, edi; Tag
0x14004ab62  call    PplDestroyLookasideList
0x14004ab67  mov     cs:AfdPplHugeBufferPool, rbx
0x14004ab6e  mov     rcx, cs:AfdPplLargeBufferPool; P
0x14004ab75  test    rcx, rcx
0x14004ab78  jz      short loc_14004AB88
0x14004ab7a  mov     edx, edi; Tag
0x14004ab7c  call    PplDestroyLookasideList
0x14004ab81  mov     cs:AfdPplLargeBufferPool, rbx
0x14004ab88  mov     rcx, cs:AfdPplMediumBufferPool; P
0x14004ab8f  test    rcx, rcx
0x14004ab92  jz      short loc_14004ABA2
0x14004ab94  mov     edx, edi; Tag
0x14004ab96  call    PplDestroyLookasideList
0x14004ab9b  mov     cs:AfdPplMediumBufferPool, rbx
0x14004aba2  mov     rcx, cs:AfdPplSmallBufferPool; P
0x14004aba9  test    rcx, rcx
0x14004abac  jz      short loc_14004ABBC
0x14004abae  mov     edx, edi; Tag
0x14004abb0  call    PplDestroyLookasideList
0x14004abb5  mov     cs:AfdPplSmallBufferPool, rbx
0x14004abbc  mov     rcx, cs:AfdDeviceObject; DeviceObject
0x14004abc3  call    cs:__imp_IoDeleteDevice
0x14004abca  nop     dword ptr [rax+rax+00h]
0x14004abcf  call    cs:__imp_NetioNrtStop
0x14004abd6  nop     dword ptr [rax+rax+00h]
0x14004abdb  call    AfdTdiDeInit
0x14004abe0  call    AfdPcwCleanup
0x14004abe5  lea     rcx, qword_140087750
0x14004abec  call    cs:__imp_NetioDeregisterTriageDumpDataCallback
0x14004abf3  nop     dword ptr [rax+rax+00h]
0x14004abf8  mov     rcx, cs:FastWppRegHandle; RegHandle
0x14004abff  call    cs:__imp_EtwUnregister
0x14004ac06  nop     dword ptr [rax+rax+00h]
0x14004ac0b  mov     [rsp+68h+CallbackContext], rbx; CallbackContext
0x14004ac10  xor     r9d, r9d; MatchAnyKeyword
0x14004ac13  mov     [rsp+68h+FilterData], rbx; FilterData
0x14004ac18  xor     r8d, r8d; Level
0x14004ac1b  xor     edx, edx; ControlCode
0x14004ac1d  mov     [rsp+68h+Timeout], rbx; MatchAllKeyword
0x14004ac22  xor     ecx, ecx; SourceId
0x14004ac24  mov     cs:FastWppRegHandle, rbx
0x14004ac2b  call    FastWppCallback
0x14004ac30  mov     cs:FastWppInitState, ebx
0x14004ac36  call    TraceLoggingUnregister_EtwUnregister
0x14004ac3b  call    wil_UninitializeFeatureStaging
0x14004ac40  mov     rbx, [rsp+68h+arg_0]
0x14004ac45  add     rsp, 60h
0x14004ac49  pop     rdi
0x14004ac4a  retn
```
