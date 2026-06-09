# DriverEntry

- ea: `0x14004ac54`
- end: `0x14004b619`
- name: `DriverEntry`
- size: `2501`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140095010`

## callees

- `0x140003670`
- `0x1400129d0`
- `0x14003f144`
- `0x140042a94`
- `0x140045b48`
- `0x140047dac`
- `0x1400496dc`
- `0x140049a78`
- `0x140049b40`
- `0x140049d64`
- `0x14004a0a4`
- `0x14004a700`
- `0x14004ac54`
- `0x14004b620`
- `0x14004b690`
- `0x14004ee7c`
- `0x1400502f4`
- `0x1400508b4`
- `0x1400527a4`
- `0x140052800`
- `0x14005e138`
- `0x14005e1e4`
- `0x14005e38c`
- `0x14005e3f8`
- `0x140067238`
- `0x1400673e0`
- `0x1400677a8`
- `0x140067a8c`
- `0x14006df84`
- `0x14006dfd4`
- `0x14006e0f0`
- `0x14006e1ec`
- `0x14009235c`
- `0x140092408`
- `0x140092440`
- `0x1400931d0`
- `0x1400932cc`
- `0x140095078`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14004ae22`
- `ntoskrnl!KeInitializeEvent` at `0x14004ae22`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004b44b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004b44b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14004ae7b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14004ae7b`
- `ntoskrnl!MmIsVerifierEnabled` at `0x14004acb4`
- `ntoskrnl!MmIsVerifierEnabled` at `0x14004acb4`
- `ntoskrnl!IoCreateDevice` at `0x14004ad74`
- `ntoskrnl!IoCreateDevice` at `0x14004ad74`
- `ntoskrnl!IoAllocateWorkItem` at `0x14004add7`
- `ntoskrnl!IoAllocateWorkItem` at `0x14004add7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004af97`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004af97`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004b438`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004b438`
- `ntoskrnl!IoFreeWorkItem` at `0x14004b56c`
- `ntoskrnl!IoFreeWorkItem` at `0x14004b56c`
- `ntoskrnl!IoDeleteDevice` at `0x14004b58b`
- `ntoskrnl!IoDeleteDevice` at `0x14004b58b`
- `ntoskrnl!EtwUnregister` at `0x14004b5bb`
- `ntoskrnl!EtwUnregister` at `0x14004b5bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ad3f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ad3f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004ad27`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004ad27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b415`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b463`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b415`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b463`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004b2d0`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004b2d0`
- `NETIO!NmrRegisterProvider` at `0x14004b363`
- `NETIO!NmrRegisterProvider` at `0x14004b3a8`
- `NETIO!NmrRegisterProvider` at `0x14004b363`
- `NETIO!NmrRegisterProvider` at `0x14004b3a8`
- `NETIO!NetioNrtStop` at `0x14004b59e`
- `NETIO!NetioNrtStop` at `0x14004b59e`
- `NETIO!NetioTimerWorkItemShutdown` at `0x14004b482`
- `NETIO!NetioTimerWorkItemShutdown` at `0x14004b482`
- `NETIO!NetioTimerWorkItemStart` at `0x14004b249`
- `NETIO!NetioTimerWorkItemStart` at `0x14004b249`
- `NETIO!NetioTimerWorkItemInitialize` at `0x14004b224`
- `NETIO!NetioTimerWorkItemInitialize` at `0x14004b224`
- `NETIO!NetioNrtStart` at `0x14004adba`
- `NETIO!NetioNrtStart` at `0x14004adba`
- `NETIO!NetioSetTriageBlock` at `0x14004ace2`
- `NETIO!NetioSetTriageBlock` at `0x14004ace2`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14004ad14`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14004ad14`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  int v4; // esi
  char v5; // bp
  int SecurityDescriptor; // edi
  struct _ERESOURCE *PoolPriority; // rax
  int inited; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  int DeviceCharacteristicsi; // [rsp+20h] [rbp-68h]
  int DeviceCharacteristics; // [rsp+20h] [rbp-68h]
  int DeviceCharacteristicsa; // [rsp+20h] [rbp-68h]
  int DeviceCharacteristicsb; // [rsp+20h] [rbp-68h]
  int DeviceCharacteristicsc; // [rsp+20h] [rbp-68h]
  int DeviceCharacteristicsd; // [rsp+20h] [rbp-68h]
  int DeviceCharacteristicse; // [rsp+20h] [rbp-68h]
  int DeviceCharacteristicsf; // [rsp+20h] [rbp-68h]
  int DeviceCharacteristicsg; // [rsp+20h] [rbp-68h]
  int DeviceCharacteristicsh; // [rsp+20h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-38h] BYREF
  ULONG VerifierFlags; // [rsp+A0h] [rbp+18h] BYREF

  DestinationString = 0;
  VerifierFlags = 0;
  result = wil_InitializeFeatureStaging(DriverObject, RegistryPath);
  if ( result >= 0 )
  {
    v4 = -1073741823;
    v5 = 0;
    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
    FastWppInit();
    AfdHungCloseRequestTimeout.QuadPart = -3000000000LL;
    if ( MmIsVerifierEnabled(&VerifierFlags) >= 0 )
      AfdHungCloseRequestTimeout.QuadPart *= 4LL;
    NetioSetTriageBlock(2, AfdGlobalTriageBlock);
    NetioRegisterTriageDumpDataCallback(qword_140087750, 1, AfdPopulateTriageDumpData, AfdGlobalTriageBlock, "AFD");
    KeInitializeSpinLock(&AfdTdiSpinlock);
    RtlInitUnicodeString(&DestinationString, L"\\Device\\Afd");
    SecurityDescriptor = IoCreateDevice(
                           DriverObject,
                           0,
                           &DestinationString,
                           0x11u,
                           0x20000u,
                           0,
                           (PDEVICE_OBJECT *)&AfdDeviceObject);
    if ( SecurityDescriptor < 0 )
    {
      if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
        WPP_SF_d(532, 10, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
      goto LABEL_48;
    }
    SecurityDescriptor = NetioNrtStart(DriverObject);
    if ( SecurityDescriptor >= 0 )
    {
      AfdWorkQueueItem = IoAllocateWorkItem((PDEVICE_OBJECT)AfdDeviceObject);
      if ( !AfdWorkQueueItem )
      {
        if ( (BYTE2(xmmword_1400875E0) & 0x10) != 0 )
          WPP_SF_(1044, 11, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
LABEL_11:
        SecurityDescriptor = -1073741670;
        goto LABEL_48;
      }
      KeInitializeEvent(&AfdContextWaitEvent, NotificationEvent, 0);
      SecurityDescriptor = AfdCreateSecurityDescriptor();
      if ( SecurityDescriptor < 0 )
        goto LABEL_48;
      AfdInitializeData();
      AfdReadRegistry(DriverObject);
      PoolPriority = (struct _ERESOURCE *)AfdAllocatePoolPriority(64, (int)AfdAlignmentTableSize + 256, 1919182401);
      AfdGlobalData = PoolPriority;
      if ( !PoolPriority )
        goto LABEL_11;
      ExInitializeResourceLite(PoolPriority);
      AfdInitializeBufferManager();
      AfdPplHugeBufferSize = (unsigned int)AfdCalculateBufferSize((unsigned int)AfdHugeBufferSize);
      AfdPplLargeBufferSize = (unsigned int)AfdCalculateBufferSize((unsigned int)AfdLargeBufferSize);
      if ( AfdPplLargeBufferSize == AfdPplHugeBufferSize )
        LODWORD(AfdLargeBufferSize) = AfdHugeBufferSize;
      AfdPplMediumBufferSize = (unsigned int)AfdCalculateBufferSize((unsigned int)AfdMediumBufferSize);
      if ( AfdPplMediumBufferSize == AfdPplLargeBufferSize )
        LODWORD(AfdMediumBufferSize) = AfdLargeBufferSize;
      AfdPplSmallBufferSize = (unsigned int)AfdCalculateBufferSize((unsigned int)AfdSmallBufferSize);
      if ( AfdPplSmallBufferSize == AfdPplMediumBufferSize )
        LODWORD(AfdSmallBufferSize) = AfdMediumBufferSize;
      ExInitializeNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)&AfdGlobalData[1].ActiveCount,
        AfdAllocateTpInfo,
        AfdFreeTpInfo,
        0x200u,
        ((24 * AfdDefaultTpInfoElementCount + 271) & 0xFFFFFFF0) + 96,
        0x46646641u,
        0);
      AfdPplBufferTagPool = (PVOID)PplCreateLookasideList(
                                     (int)AfdAllocateBufferTag,
                                     (int)AfdFreeBufferTag,
                                     DeviceCharacteristicsi,
                                     0x68u,
                                     0x42646641u,
                                     1024,
                                     0x42646641u);
      if ( !AfdPplBufferTagPool )
        goto LABEL_11;
      AfdPplHugeBufferPool = (PVOID)PplCreateLookasideList(
                                      (int)&AfdAllocateBuffer,
                                      (int)AfdFreeBuffer,
                                      DeviceCharacteristics,
                                      AfdPplHugeBufferSize,
                                      0x42646641u,
                                      1024,
                                      0x42646641u);
      if ( !AfdPplHugeBufferPool )
        goto LABEL_11;
      AfdPplLargeBufferPool = (PVOID)PplCreateLookasideList(
                                       (int)&AfdAllocateBuffer,
                                       (int)AfdFreeBuffer,
                                       DeviceCharacteristicsa,
                                       AfdPplLargeBufferSize,
                                       0x42646641u,
                                       1024,
                                       0x42646641u);
      if ( !AfdPplLargeBufferPool )
        goto LABEL_11;
      AfdPplMediumBufferPool = (PVOID)PplCreateLookasideList(
                                        (int)&AfdAllocateBuffer,
                                        (int)AfdFreeBuffer,
                                        DeviceCharacteristicsb,
                                        AfdPplMediumBufferSize,
                                        0x42646641u,
                                        1024,
                                        0x42646641u);
      if ( !AfdPplMediumBufferPool )
        goto LABEL_11;
      AfdPplSmallBufferPool = (PVOID)PplCreateLookasideList(
                                       (int)&AfdAllocateBuffer,
                                       (int)AfdFreeBuffer,
                                       DeviceCharacteristicsc,
                                       AfdPplSmallBufferSize,
                                       0x42646641u,
                                       1024,
                                       0x42646641u);
      if ( !AfdPplSmallBufferPool )
        goto LABEL_11;
      PplConnectionPool = (PVOID)PplCreateLookasideList(
                                   0,
                                   0,
                                   DeviceCharacteristicsd,
                                   0x100u,
                                   0x43646641u,
                                   0,
                                   0x43646641u);
      if ( !PplConnectionPool )
        goto LABEL_11;
      PplEndpointPool = (PVOID)PplCreateLookasideList(0, 0, DeviceCharacteristicse, 0x1F0u, 0x45646641u, 0, 0x45646641u);
      if ( !PplEndpointPool )
        goto LABEL_11;
      PplTditlEndpointPool = (PVOID)PplCreateLookasideList(
                                      0,
                                      0,
                                      DeviceCharacteristicsf,
                                      0x210u,
                                      0x45646641u,
                                      0,
                                      0x45646641u);
      if ( !PplTditlEndpointPool )
        goto LABEL_11;
      WskProPplSocket = (PVOID)PplCreateLookasideList(0, 0, DeviceCharacteristicsg, 0xC8u, 0x734B5357u, 0, 0x734B5357u);
      if ( !WskProPplSocket )
        goto LABEL_11;
      PplAddressPool = (PVOID)PplCreateLookasideList(
                                (int)AfdAllocateRemoteAddress,
                                (int)AfdFreeRemoteAddress,
                                DeviceCharacteristicsh,
                                (unsigned int)AfdStandardAddressLength,
                                0x52646641u,
                                0,
                                0x52646641u);
      if ( !PplAddressPool )
        goto LABEL_11;
      SecurityDescriptor = NetioTimerWorkItemInitialize(
                             AfdTrimLookasidesWorkItem,
                             AfdTrimLookasides,
                             0,
                             1,
                             0,
                             AfdDeviceObject);
      if ( SecurityDescriptor < 0 )
        goto LABEL_48;
      v5 = 1;
      NetioTimerWorkItemStart(AfdTrimLookasidesWorkItem, 60000);
      if ( !(unsigned __int8)AfdInitializeGroup() )
        goto LABEL_11;
      memset64(DriverObject->MajorFunction, (unsigned __int64)&AfdDispatch, 0x1Cu);
      DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)AfdDispatchDeviceControl;
      DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)&AfdWskDispatchInternalDeviceControl;
      DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)&AfdEtwDispatch;
      DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)AfdFastIoDispatch;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)AfdUnload;
      *((_DWORD *)AfdDeviceObject + 12) |= 0x10u;
      *((_BYTE *)AfdDeviceObject + 76) = AfdIrpStackSize;
      IoGetCurrentProcess();
      if ( AfdParametersNotifyHandle )
        AfdReadVolatileParameters(0);
      inited = AfdEtwInitLog();
      v4 = inited;
      if ( inited >= 0 )
      {
        SecurityDescriptor = AfdTdiStart();
        if ( SecurityDescriptor >= 0 )
        {
          SecurityDescriptor = AfdInitTimerWheel();
          if ( SecurityDescriptor >= 0 )
          {
            SecurityDescriptor = AfdTlStartClientModule();
            if ( SecurityDescriptor >= 0 )
            {
              SecurityDescriptor = AfdPodInit(DriverObject);
              if ( SecurityDescriptor >= 0 )
              {
                SecurityDescriptor = AfdWskStartProviderModule();
                if ( SecurityDescriptor >= 0 )
                {
                  SecurityDescriptor = AfdPcwInit();
                  if ( SecurityDescriptor >= 0 )
                  {
                    SecurityDescriptor = NmrRegisterProvider(&ProviderCharacteristics, 0, &qword_1400877A0);
                    if ( SecurityDescriptor >= 0 )
                    {
                      if ( !((Feature_4431_4260__private_featureState & 0x10) != 0
                           ? Feature_4431_4260__private_featureState & 1
                           : Feature_4431_4260__private_IsEnabledDeviceUsageNoInline()) )
                        return SecurityDescriptor;
                      NmrProviderHandle = 0;
                      SecurityDescriptor = NmrRegisterProvider(&AfdDnskProviderNotify, 0, &NmrProviderHandle);
                      if ( SecurityDescriptor >= 0 )
                        return SecurityDescriptor;
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        SecurityDescriptor = inited;
      }
    }
LABEL_48:
    if ( (Feature_4431_4260__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_4431_4260__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_4431_4260__private_IsEnabledDeviceUsageNoInline();
    if ( IsEnabledDeviceUsageNoInline )
      AfdDnskStopProviderModule();
    AfdDeregisterNsiProvider();
    AfdWskStopProviderModule();
    AfdPodDeinit();
    AfdTlStopClientModule();
    AfdTdiStop();
    if ( v4 >= 0 )
      AfdEtwUnRegisterLog();
    AfdStopTimerWheel();
    AfdTerminateGroup();
    if ( AfdAdminSecurityDescriptor )
    {
      ExFreePoolWithTag(AfdAdminSecurityDescriptor, 0);
      AfdAdminSecurityDescriptor = 0;
    }
    if ( AfdGlobalData )
    {
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&AfdGlobalData[1].ActiveCount);
      ExDeleteResourceLite(AfdGlobalData);
      ExFreePoolWithTag(AfdGlobalData, 0x72646641u);
      AfdGlobalData = 0;
    }
    if ( v5 )
      NetioTimerWorkItemShutdown(AfdTrimLookasidesWorkItem);
    if ( PplConnectionPool )
      PplDestroyLookasideList(PplConnectionPool, 0x43646641u);
    if ( PplEndpointPool )
      PplDestroyLookasideList(PplEndpointPool, 0x45646641u);
    if ( PplTditlEndpointPool )
      PplDestroyLookasideList(PplTditlEndpointPool, 0x45646641u);
    if ( WskProPplSocket )
      PplDestroyLookasideList(WskProPplSocket, 0x734B5357u);
    if ( PplAddressPool )
      PplDestroyLookasideList(PplAddressPool, 0x52646641u);
    if ( AfdPplBufferTagPool )
      PplDestroyLookasideList(AfdPplBufferTagPool, 0x42646641u);
    if ( AfdPplHugeBufferPool )
      PplDestroyLookasideList(AfdPplHugeBufferPool, 0x42646641u);
    if ( AfdPplLargeBufferPool )
      PplDestroyLookasideList(AfdPplLargeBufferPool, 0x42646641u);
    if ( AfdPplMediumBufferPool )
      PplDestroyLookasideList(AfdPplMediumBufferPool, 0x42646641u);
    if ( AfdPplSmallBufferPool )
      PplDestroyLookasideList(AfdPplSmallBufferPool, 0x42646641u);
    if ( AfdWorkQueueItem )
    {
      IoFreeWorkItem(AfdWorkQueueItem);
      AfdWorkQueueItem = 0;
    }
    if ( AfdDeviceObject )
    {
      IoDeleteDevice((PDEVICE_OBJECT)AfdDeviceObject);
      AfdDeviceObject = 0;
    }
    NetioNrtStop();
    AfdTdiDeInit();
    AfdPcwCleanup();
    EtwUnregister(FastWppRegHandle);
    FastWppRegHandle = 0;
    FastWppCallback(0, 0, 0, 0, 0, 0, 0);
    FastWppInitState = 0;
    TraceLoggingUnregister_EtwUnregister();
    wil_UninitializeFeatureStaging();
    return SecurityDescriptor;
  }
  return result;
}

```

## disassembly

```asm
0x14004ac54  mov     rax, rsp
0x14004ac57  mov     [rax+8], rbx
0x14004ac5b  mov     [rax+10h], rbp
0x14004ac5f  push    rsi
0x14004ac60  push    rdi
0x14004ac61  push    r13
0x14004ac63  push    r14
0x14004ac65  push    r15
0x14004ac67  sub     rsp, 60h
0x14004ac6b  xorps   xmm0, xmm0
0x14004ac6e  xor     r14d, r14d
0x14004ac71  movups  xmmword ptr [rax-38h], xmm0
0x14004ac75  mov     [rax+18h], r14d
0x14004ac79  mov     rbx, rcx
0x14004ac7c  call    wil_InitializeFeatureStaging
0x14004ac81  test    eax, eax
0x14004ac83  js      loc_14004B5FF
0x14004ac89  mov     esi, 0C0000001h
0x14004ac8e  mov     bpl, r14b
0x14004ac91  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14004ac96  call    FastWppInit
0x14004ac9b  mov     rax, 0FFFFFFFF4D2FA200h
0x14004aca5  lea     rcx, [rsp+88h+VerifierFlags]; VerifierFlags
0x14004acad  mov     qword ptr cs:AfdHungCloseRequestTimeout, rax
0x14004acb4  call    cs:__imp_MmIsVerifierEnabled
0x14004acbb  nop     dword ptr [rax+rax+00h]
0x14004acc0  test    eax, eax
0x14004acc2  js      short loc_14004ACD6
0x14004acc4  mov     rax, qword ptr cs:AfdHungCloseRequestTimeout
0x14004accb  shl     rax, 2
0x14004accf  mov     qword ptr cs:AfdHungCloseRequestTimeout, rax
0x14004acd6  lea     rdx, AfdGlobalTriageBlock
0x14004acdd  mov     ecx, 2
0x14004ace2  call    cs:__imp_NetioSetTriageBlock
0x14004ace9  nop     dword ptr [rax+rax+00h]
0x14004acee  lea     rax, aAfd; "AFD"
0x14004acf5  mov     edx, 1
0x14004acfa  lea     r9, AfdGlobalTriageBlock
0x14004ad01  mov     qword ptr [rsp+88h+DeviceCharacteristics], rax
0x14004ad06  lea     r8, AfdPopulateTriageDumpData
0x14004ad0d  lea     rcx, qword_140087750
0x14004ad14  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x14004ad1b  nop     dword ptr [rax+rax+00h]
0x14004ad20  lea     rcx, AfdTdiSpinlock; SpinLock
0x14004ad27  call    cs:__imp_KeInitializeSpinLock
0x14004ad2e  nop     dword ptr [rax+rax+00h]
0x14004ad33  lea     rdx, aDeviceAfd; "\\Device\\Afd"
0x14004ad3a  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14004ad3f  call    cs:__imp_RtlInitUnicodeString
0x14004ad46  nop     dword ptr [rax+rax+00h]
0x14004ad4b  lea     rax, AfdDeviceObject
0x14004ad52  mov     r9d, 11h; DeviceType
0x14004ad58  mov     [rsp+88h+DeviceObject], rax; DeviceObject
0x14004ad5d  lea     r8, [rsp+88h+DestinationString]; DeviceName
0x14004ad62  mov     [rsp+88h+Exclusive], r14b; Exclusive
0x14004ad67  xor     edx, edx; DeviceExtensionSize
0x14004ad69  mov     rcx, rbx; DriverObject
0x14004ad6c  mov     [rsp+88h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x14004ad74  call    cs:__imp_IoCreateDevice
0x14004ad7b  nop     dword ptr [rax+rax+00h]
0x14004ad80  mov     edi, eax
0x14004ad82  mov     r15d, 42646641h
0x14004ad88  test    eax, eax
0x14004ad8a  jns     short loc_14004ADB7
0x14004ad8c  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x14004ad93  jz      loc_14004B3BE
0x14004ad99  mov     edx, 0Ah
0x14004ad9e  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x14004ada5  mov     ecx, 214h
0x14004adaa  mov     r9d, eax
0x14004adad  call    WPP_SF_d
0x14004adb2  jmp     loc_14004B3BE
0x14004adb7  mov     rcx, rbx
0x14004adba  call    cs:__imp_NetioNrtStart
0x14004adc1  nop     dword ptr [rax+rax+00h]
0x14004adc6  mov     edi, eax
0x14004adc8  test    eax, eax
0x14004adca  js      loc_14004B3BE
0x14004add0  mov     rcx, cs:AfdDeviceObject; DeviceObject
0x14004add7  call    cs:__imp_IoAllocateWorkItem
0x14004adde  nop     dword ptr [rax+rax+00h]
0x14004ade3  mov     cs:AfdWorkQueueItem, rax
0x14004adea  test    rax, rax
0x14004aded  jnz     short loc_14004AE16
0x14004adef  test    byte ptr cs:xmmword_1400875E0+2, 10h
0x14004adf6  jz      short loc_14004AE0C
0x14004adf8  lea     edx, [rax+0Bh]
0x14004adfb  mov     ecx, 414h
0x14004ae00  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x14004ae07  call    WPP_SF_
0x14004ae0c  mov     edi, 0C000009Ah
0x14004ae11  jmp     loc_14004B3BE
0x14004ae16  xor     r8d, r8d; State
0x14004ae19  lea     rcx, AfdContextWaitEvent; Event
0x14004ae20  xor     edx, edx; Type
0x14004ae22  call    cs:__imp_KeInitializeEvent
0x14004ae29  nop     dword ptr [rax+rax+00h]
0x14004ae2e  call    AfdCreateSecurityDescriptor
0x14004ae33  mov     edi, eax
0x14004ae35  test    eax, eax
0x14004ae37  js      loc_14004B3BE
0x14004ae3d  call    AfdInitializeData
0x14004ae42  mov     rcx, rbx
0x14004ae45  call    AfdReadRegistry
0x14004ae4a  mov     eax, cs:AfdAlignmentTableSize
0x14004ae50  mov     ecx, 40h ; '@'
0x14004ae55  add     eax, 100h
0x14004ae5a  mov     r8d, 72646641h
0x14004ae60  movsxd  rdx, eax
0x14004ae63  lea     r9d, [rcx-20h]
0x14004ae67  call    AfdAllocatePoolPriority
0x14004ae6c  mov     cs:AfdGlobalData, rax
0x14004ae73  test    rax, rax
0x14004ae76  jz      short loc_14004AE0C
0x14004ae78  mov     rcx, rax; Resource
0x14004ae7b  call    cs:__imp_ExInitializeResourceLite
0x14004ae82  nop     dword ptr [rax+rax+00h]
0x14004ae87  call    AfdInitializeBufferManager
0x14004ae8c  mov     r8b, cs:AfdTdiStackSize
0x14004ae93  mov     edx, cs:AfdStandardAddressLength
0x14004ae99  mov     ecx, cs:AfdHugeBufferSize; Length
0x14004ae9f  call    AfdCalculateBufferSize
0x14004aea4  mov     r8b, cs:AfdTdiStackSize
0x14004aeab  mov     edx, cs:AfdStandardAddressLength
0x14004aeb1  mov     ecx, cs:AfdLargeBufferSize; Length
0x14004aeb7  mov     eax, eax
0x14004aeb9  mov     cs:AfdPplHugeBufferSize, rax
0x14004aec0  call    AfdCalculateBufferSize
0x14004aec5  mov     eax, eax
0x14004aec7  cmp     rax, cs:AfdPplHugeBufferSize
0x14004aece  mov     cs:AfdPplLargeBufferSize, rax
0x14004aed5  jnz     short loc_14004AEE3
0x14004aed7  mov     eax, cs:AfdHugeBufferSize
0x14004aedd  mov     cs:AfdLargeBufferSize, eax
0x14004aee3  mov     r8b, cs:AfdTdiStackSize
0x14004aeea  mov     edx, cs:AfdStandardAddressLength
0x14004aef0  mov     ecx, cs:AfdMediumBufferSize; Length
0x14004aef6  call    AfdCalculateBufferSize
0x14004aefb  mov     eax, eax
0x14004aefd  cmp     rax, cs:AfdPplLargeBufferSize
0x14004af04  mov     cs:AfdPplMediumBufferSize, rax
0x14004af0b  jnz     short loc_14004AF19
0x14004af0d  mov     eax, cs:AfdLargeBufferSize
0x14004af13  mov     cs:AfdMediumBufferSize, eax
0x14004af19  mov     r8b, cs:AfdTdiStackSize
0x14004af20  mov     edx, cs:AfdStandardAddressLength
0x14004af26  mov     ecx, cs:AfdSmallBufferSize; Length
0x14004af2c  call    AfdCalculateBufferSize
0x14004af31  mov     eax, eax
0x14004af33  cmp     rax, cs:AfdPplMediumBufferSize
0x14004af3a  mov     cs:AfdPplSmallBufferSize, rax
0x14004af41  jnz     short loc_14004AF4F
0x14004af43  mov     eax, cs:AfdMediumBufferSize
0x14004af49  mov     cs:AfdSmallBufferSize, eax
0x14004af4f  mov     eax, cs:AfdDefaultTpInfoElementCount
0x14004af55  lea     r8, AfdFreeTpInfo; Free
0x14004af5c  mov     word ptr [rsp+88h+DeviceObject], r14w; Depth
0x14004af62  lea     rdx, AfdAllocateTpInfo; Allocate
0x14004af69  mov     dword ptr [rsp+88h+Exclusive], 46646641h; Tag
0x14004af71  mov     r9d, 200h; Flags
0x14004af77  lea     ecx, [rax+rax*2]
0x14004af7a  lea     eax, ds:10Fh[rcx*8]
0x14004af81  mov     rcx, cs:AfdGlobalData
0x14004af88  and     eax, 0FFFFFFF0h
0x14004af8b  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14004af8f  add     eax, 60h ; '`'
0x14004af92  mov     qword ptr [rsp+88h+DeviceCharacteristics], rax; int
0x14004af97  call    cs:__imp_ExInitializeNPagedLookasideList
0x14004af9e  nop     dword ptr [rax+rax+00h]
0x14004afa3  mov     [rsp+88h+var_48], r15d; ULONG
0x14004afa8  lea     rdx, AfdFreeBufferTag; int
0x14004afaf  mov     r13d, 400h
0x14004afb5  lea     rcx, AfdAllocateBufferTag; int
0x14004afbc  mov     [rsp+88h+var_50], r13w; __int16
0x14004afc2  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004afc7  mov     qword ptr [rsp+88h+Exclusive], 68h ; 'h'; SIZE_T
0x14004afd0  call    PplCreateLookasideList
0x14004afd5  mov     cs:AfdPplBufferTagPool, rax
0x14004afdc  test    rax, rax
0x14004afdf  jz      loc_14004AE0C
0x14004afe5  mov     rax, cs:AfdPplHugeBufferSize
0x14004afec  lea     rdi, AfdFreeBuffer
0x14004aff3  mov     [rsp+88h+var_48], r15d; ULONG
0x14004aff8  lea     rcx, AfdAllocateBuffer; int
0x14004afff  mov     [rsp+88h+var_50], r13w; __int16
0x14004b005  mov     rdx, rdi; int
0x14004b008  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004b00d  mov     qword ptr [rsp+88h+Exclusive], rax; SIZE_T
0x14004b012  call    PplCreateLookasideList
0x14004b017  mov     cs:AfdPplHugeBufferPool, rax
0x14004b01e  test    rax, rax
0x14004b021  jz      loc_14004AE0C
0x14004b027  mov     rax, cs:AfdPplLargeBufferSize
0x14004b02e  lea     rcx, AfdAllocateBuffer; int
0x14004b035  mov     [rsp+88h+var_48], r15d; ULONG
0x14004b03a  mov     rdx, rdi; int
0x14004b03d  mov     [rsp+88h+var_50], r13w; __int16
0x14004b043  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004b048  mov     qword ptr [rsp+88h+Exclusive], rax; SIZE_T
0x14004b04d  call    PplCreateLookasideList
0x14004b052  mov     cs:AfdPplLargeBufferPool, rax
0x14004b059  test    rax, rax
0x14004b05c  jz      loc_14004AE0C
0x14004b062  mov     rax, cs:AfdPplMediumBufferSize
0x14004b069  lea     rcx, AfdAllocateBuffer; int
0x14004b070  mov     [rsp+88h+var_48], r15d; ULONG
0x14004b075  mov     rdx, rdi; int
0x14004b078  mov     [rsp+88h+var_50], r13w; __int16
0x14004b07e  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004b083  mov     qword ptr [rsp+88h+Exclusive], rax; SIZE_T
0x14004b088  call    PplCreateLookasideList
0x14004b08d  mov     cs:AfdPplMediumBufferPool, rax
0x14004b094  test    rax, rax
0x14004b097  jz      loc_14004AE0C
0x14004b09d  mov     rax, cs:AfdPplSmallBufferSize
0x14004b0a4  lea     rcx, AfdAllocateBuffer; int
0x14004b0ab  mov     [rsp+88h+var_48], r15d; ULONG
0x14004b0b0  mov     rdx, rdi; int
0x14004b0b3  mov     [rsp+88h+var_50], r13w; __int16
0x14004b0b9  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004b0be  mov     qword ptr [rsp+88h+Exclusive], rax; SIZE_T
0x14004b0c3  call    PplCreateLookasideList
0x14004b0c8  mov     cs:AfdPplSmallBufferPool, rax
0x14004b0cf  test    rax, rax
0x14004b0d2  jz      loc_14004AE0C
0x14004b0d8  mov     [rsp+88h+var_48], 43646641h; ULONG
0x14004b0e0  xor     edx, edx; int
0x14004b0e2  mov     [rsp+88h+var_50], r14w; __int16
0x14004b0e8  xor     ecx, ecx; int
0x14004b0ea  mov     dword ptr [rsp+88h+DeviceObject], 43646641h; ULONG
0x14004b0f2  mov     qword ptr [rsp+88h+Exclusive], 100h; SIZE_T
0x14004b0fb  call    PplCreateLookasideList
0x14004b100  mov     cs:PplConnectionPool, rax
0x14004b107  test    rax, rax
0x14004b10a  jz      loc_14004AE0C
0x14004b110  mov     [rsp+88h+var_48], 45646641h; ULONG
0x14004b118  xor     edx, edx; int
0x14004b11a  mov     [rsp+88h+var_50], r14w; __int16
0x14004b120  xor     ecx, ecx; int
0x14004b122  mov     dword ptr [rsp+88h+DeviceObject], 45646641h; ULONG
0x14004b12a  mov     qword ptr [rsp+88h+Exclusive], 1F0h; SIZE_T
0x14004b133  call    PplCreateLookasideList
0x14004b138  mov     cs:PplEndpointPool, rax
0x14004b13f  test    rax, rax
0x14004b142  jz      loc_14004AE0C
0x14004b148  mov     [rsp+88h+var_48], 45646641h; ULONG
0x14004b150  xor     edx, edx; int
0x14004b152  mov     [rsp+88h+var_50], r14w; __int16
0x14004b158  xor     ecx, ecx; int
0x14004b15a  mov     dword ptr [rsp+88h+DeviceObject], 45646641h; ULONG
0x14004b162  mov     qword ptr [rsp+88h+Exclusive], 210h; SIZE_T
0x14004b16b  call    PplCreateLookasideList
0x14004b170  mov     cs:PplTditlEndpointPool, rax
0x14004b177  test    rax, rax
0x14004b17a  jz      loc_14004AE0C
0x14004b180  mov     [rsp+88h+var_48], 734B5357h; ULONG
0x14004b188  xor     edx, edx; int
0x14004b18a  mov     [rsp+88h+var_50], r14w; __int16
0x14004b190  xor     ecx, ecx; int
0x14004b192  mov     dword ptr [rsp+88h+DeviceObject], 734B5357h; ULONG
0x14004b19a  mov     qword ptr [rsp+88h+Exclusive], 0C8h; SIZE_T
0x14004b1a3  call    PplCreateLookasideList
0x14004b1a8  mov     cs:WskProPplSocket, rax
0x14004b1af  test    rax, rax
0x14004b1b2  jz      loc_14004AE0C
0x14004b1b8  mov     ecx, cs:AfdStandardAddressLength
0x14004b1be  lea     rdx, AfdFreeRemoteAddress; int
0x14004b1c5  mov     [rsp+88h+var_48], 52646641h; ULONG
0x14004b1cd  mov     [rsp+88h+var_50], r14w; __int16
0x14004b1d3  mov     dword ptr [rsp+88h+DeviceObject], 52646641h; ULONG
0x14004b1db  mov     qword ptr [rsp+88h+Exclusive], rcx; SIZE_T
0x14004b1e0  lea     rcx, AfdAllocateRemoteAddress; int
0x14004b1e7  call    PplCreateLookasideList
0x14004b1ec  mov     cs:PplAddressPool, rax
0x14004b1f3  test    rax, rax
0x14004b1f6  jz      loc_14004AE0C
0x14004b1fc  mov     rax, cs:AfdDeviceObject
0x14004b203  lea     rdx, AfdTrimLookasides
0x14004b20a  mov     qword ptr [rsp+88h+Exclusive], rax
0x14004b20f  lea     rcx, AfdTrimLookasidesWorkItem
0x14004b216  mov     r9d, 1
0x14004b21c  mov     qword ptr [rsp+88h+DeviceCharacteristics], r14
0x14004b221  xor     r8d, r8d
0x14004b224  call    cs:__imp_NetioTimerWorkItemInitialize
0x14004b22b  nop     dword ptr [rax+rax+00h]
0x14004b230  mov     edi, eax
0x14004b232  test    eax, eax
0x14004b234  js      loc_14004B3BE
0x14004b23a  mov     edx, 0EA60h
0x14004b23f  lea     rcx, AfdTrimLookasidesWorkItem
0x14004b246  mov     bpl, 1
0x14004b249  call    cs:__imp_NetioTimerWorkItemStart
0x14004b250  nop     dword ptr [rax+rax+00h]
0x14004b255  call    AfdInitializeGroup
0x14004b25a  test    al, al
0x14004b25c  jz      loc_14004AE0C
0x14004b262  lea     rax, AfdDispatch
0x14004b269  mov     ecx, 1Ch
0x14004b26e  lea     rdi, [rbx+70h]
0x14004b272  rep stosq
  ... truncated ...
```
