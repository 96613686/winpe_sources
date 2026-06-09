# DriverEntry

- ea: `0x14004abb4`
- end: `0x14004b579`
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
- `0x14003f124`
- `0x140042a74`
- `0x140045ac0`
- `0x140047d2c`
- `0x14004963c`
- `0x1400499d8`
- `0x140049aa0`
- `0x140049cc4`
- `0x14004a004`
- `0x14004a660`
- `0x14004abb4`
- `0x14004b580`
- `0x14004b5f0`
- `0x14004eddc`
- `0x140050254`
- `0x140050814`
- `0x140052704`
- `0x140052760`
- `0x14005df98`
- `0x14005e044`
- `0x14005e1ec`
- `0x14005e258`
- `0x140067098`
- `0x140067240`
- `0x140067608`
- `0x1400678ec`
- `0x14006dde4`
- `0x14006de34`
- `0x14006df50`
- `0x14006e04c`
- `0x14009235c`
- `0x140092408`
- `0x140092440`
- `0x1400931d0`
- `0x1400932cc`
- `0x140095078`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14004ad82`
- `ntoskrnl!KeInitializeEvent` at `0x14004ad82`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004b3ab`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004b3ab`
- `ntoskrnl!ExInitializeResourceLite` at `0x14004addb`
- `ntoskrnl!ExInitializeResourceLite` at `0x14004addb`
- `ntoskrnl!MmIsVerifierEnabled` at `0x14004ac14`
- `ntoskrnl!MmIsVerifierEnabled` at `0x14004ac14`
- `ntoskrnl!IoCreateDevice` at `0x14004acd4`
- `ntoskrnl!IoCreateDevice` at `0x14004acd4`
- `ntoskrnl!IoAllocateWorkItem` at `0x14004ad37`
- `ntoskrnl!IoAllocateWorkItem` at `0x14004ad37`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004aef7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004aef7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004b398`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004b398`
- `ntoskrnl!IoFreeWorkItem` at `0x14004b4cc`
- `ntoskrnl!IoFreeWorkItem` at `0x14004b4cc`
- `ntoskrnl!IoDeleteDevice` at `0x14004b4eb`
- `ntoskrnl!IoDeleteDevice` at `0x14004b4eb`
- `ntoskrnl!EtwUnregister` at `0x14004b51b`
- `ntoskrnl!EtwUnregister` at `0x14004b51b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ac9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ac9f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004ac87`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004ac87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b375`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b3c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b375`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b3c3`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004b230`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004b230`
- `NETIO!NmrRegisterProvider` at `0x14004b2c3`
- `NETIO!NmrRegisterProvider` at `0x14004b308`
- `NETIO!NmrRegisterProvider` at `0x14004b2c3`
- `NETIO!NmrRegisterProvider` at `0x14004b308`
- `NETIO!NetioNrtStop` at `0x14004b4fe`
- `NETIO!NetioNrtStop` at `0x14004b4fe`
- `NETIO!NetioTimerWorkItemShutdown` at `0x14004b3e2`
- `NETIO!NetioTimerWorkItemShutdown` at `0x14004b3e2`
- `NETIO!NetioTimerWorkItemStart` at `0x14004b1a9`
- `NETIO!NetioTimerWorkItemStart` at `0x14004b1a9`
- `NETIO!NetioTimerWorkItemInitialize` at `0x14004b184`
- `NETIO!NetioTimerWorkItemInitialize` at `0x14004b184`
- `NETIO!NetioNrtStart` at `0x14004ad1a`
- `NETIO!NetioNrtStart` at `0x14004ad1a`
- `NETIO!NetioSetTriageBlock` at `0x14004ac42`
- `NETIO!NetioSetTriageBlock` at `0x14004ac42`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14004ac74`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14004ac74`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  int v4; // esi
  char v5; // bp
  NTSTATUS v6; // eax
  NTSTATUS SecurityDescriptor; // edi
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
    v6 = IoCreateDevice(DriverObject, 0, &DestinationString, 0x11u, 0x20000u, 0, (PDEVICE_OBJECT *)&AfdDeviceObject);
    SecurityDescriptor = v6;
    if ( v6 < 0 )
    {
      if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
        WPP_SF_d(532, 10, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids, (unsigned int)v6);
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
      PoolPriority = (struct _ERESOURCE *)AfdAllocatePoolPriority(64, (int)AfdAlignmentTableSize + 256, 1919182401, 32);
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
      DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&AfdDispatchDeviceControl;
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
0x14004abb4  mov     rax, rsp
0x14004abb7  mov     [rax+8], rbx
0x14004abbb  mov     [rax+10h], rbp
0x14004abbf  push    rsi
0x14004abc0  push    rdi
0x14004abc1  push    r13
0x14004abc3  push    r14
0x14004abc5  push    r15
0x14004abc7  sub     rsp, 60h
0x14004abcb  xorps   xmm0, xmm0
0x14004abce  xor     r14d, r14d
0x14004abd1  movups  xmmword ptr [rax-38h], xmm0
0x14004abd5  mov     [rax+18h], r14d
0x14004abd9  mov     rbx, rcx
0x14004abdc  call    wil_InitializeFeatureStaging
0x14004abe1  test    eax, eax
0x14004abe3  js      loc_14004B55F
0x14004abe9  mov     esi, 0C0000001h
0x14004abee  mov     bpl, r14b
0x14004abf1  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14004abf6  call    FastWppInit
0x14004abfb  mov     rax, 0FFFFFFFF4D2FA200h
0x14004ac05  lea     rcx, [rsp+88h+VerifierFlags]; VerifierFlags
0x14004ac0d  mov     qword ptr cs:AfdHungCloseRequestTimeout, rax
0x14004ac14  call    cs:__imp_MmIsVerifierEnabled
0x14004ac1b  nop     dword ptr [rax+rax+00h]
0x14004ac20  test    eax, eax
0x14004ac22  js      short loc_14004AC36
0x14004ac24  mov     rax, qword ptr cs:AfdHungCloseRequestTimeout
0x14004ac2b  shl     rax, 2
0x14004ac2f  mov     qword ptr cs:AfdHungCloseRequestTimeout, rax
0x14004ac36  lea     rdx, AfdGlobalTriageBlock
0x14004ac3d  mov     ecx, 2
0x14004ac42  call    cs:__imp_NetioSetTriageBlock
0x14004ac49  nop     dword ptr [rax+rax+00h]
0x14004ac4e  lea     rax, aAfd; "AFD"
0x14004ac55  mov     edx, 1
0x14004ac5a  lea     r9, AfdGlobalTriageBlock
0x14004ac61  mov     qword ptr [rsp+88h+DeviceCharacteristics], rax
0x14004ac66  lea     r8, AfdPopulateTriageDumpData
0x14004ac6d  lea     rcx, qword_140087750
0x14004ac74  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x14004ac7b  nop     dword ptr [rax+rax+00h]
0x14004ac80  lea     rcx, AfdTdiSpinlock; SpinLock
0x14004ac87  call    cs:__imp_KeInitializeSpinLock
0x14004ac8e  nop     dword ptr [rax+rax+00h]
0x14004ac93  lea     rdx, aDeviceAfd; "\\Device\\Afd"
0x14004ac9a  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14004ac9f  call    cs:__imp_RtlInitUnicodeString
0x14004aca6  nop     dword ptr [rax+rax+00h]
0x14004acab  lea     rax, AfdDeviceObject
0x14004acb2  mov     r9d, 11h; DeviceType
0x14004acb8  mov     [rsp+88h+DeviceObject], rax; DeviceObject
0x14004acbd  lea     r8, [rsp+88h+DestinationString]; DeviceName
0x14004acc2  mov     [rsp+88h+Exclusive], r14b; Exclusive
0x14004acc7  xor     edx, edx; DeviceExtensionSize
0x14004acc9  mov     rcx, rbx; DriverObject
0x14004accc  mov     [rsp+88h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x14004acd4  call    cs:__imp_IoCreateDevice
0x14004acdb  nop     dword ptr [rax+rax+00h]
0x14004ace0  mov     edi, eax
0x14004ace2  mov     r15d, 42646641h
0x14004ace8  test    eax, eax
0x14004acea  jns     short loc_14004AD17
0x14004acec  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x14004acf3  jz      loc_14004B31E
0x14004acf9  mov     edx, 0Ah
0x14004acfe  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x14004ad05  mov     ecx, 214h
0x14004ad0a  mov     r9d, eax
0x14004ad0d  call    WPP_SF_d
0x14004ad12  jmp     loc_14004B31E
0x14004ad17  mov     rcx, rbx
0x14004ad1a  call    cs:__imp_NetioNrtStart
0x14004ad21  nop     dword ptr [rax+rax+00h]
0x14004ad26  mov     edi, eax
0x14004ad28  test    eax, eax
0x14004ad2a  js      loc_14004B31E
0x14004ad30  mov     rcx, cs:AfdDeviceObject; DeviceObject
0x14004ad37  call    cs:__imp_IoAllocateWorkItem
0x14004ad3e  nop     dword ptr [rax+rax+00h]
0x14004ad43  mov     cs:AfdWorkQueueItem, rax
0x14004ad4a  test    rax, rax
0x14004ad4d  jnz     short loc_14004AD76
0x14004ad4f  test    byte ptr cs:xmmword_1400875E0+2, 10h
0x14004ad56  jz      short loc_14004AD6C
0x14004ad58  lea     edx, [rax+0Bh]
0x14004ad5b  mov     ecx, 414h
0x14004ad60  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x14004ad67  call    WPP_SF_
0x14004ad6c  mov     edi, 0C000009Ah
0x14004ad71  jmp     loc_14004B31E
0x14004ad76  xor     r8d, r8d; State
0x14004ad79  lea     rcx, AfdContextWaitEvent; Event
0x14004ad80  xor     edx, edx; Type
0x14004ad82  call    cs:__imp_KeInitializeEvent
0x14004ad89  nop     dword ptr [rax+rax+00h]
0x14004ad8e  call    AfdCreateSecurityDescriptor
0x14004ad93  mov     edi, eax
0x14004ad95  test    eax, eax
0x14004ad97  js      loc_14004B31E
0x14004ad9d  call    AfdInitializeData
0x14004ada2  mov     rcx, rbx
0x14004ada5  call    AfdReadRegistry
0x14004adaa  mov     eax, cs:AfdAlignmentTableSize
0x14004adb0  mov     ecx, 40h ; '@'
0x14004adb5  add     eax, 100h
0x14004adba  mov     r8d, 72646641h
0x14004adc0  movsxd  rdx, eax
0x14004adc3  lea     r9d, [rcx-20h]
0x14004adc7  call    AfdAllocatePoolPriority
0x14004adcc  mov     cs:AfdGlobalData, rax
0x14004add3  test    rax, rax
0x14004add6  jz      short loc_14004AD6C
0x14004add8  mov     rcx, rax; Resource
0x14004addb  call    cs:__imp_ExInitializeResourceLite
0x14004ade2  nop     dword ptr [rax+rax+00h]
0x14004ade7  call    AfdInitializeBufferManager
0x14004adec  mov     r8b, cs:AfdTdiStackSize
0x14004adf3  mov     edx, cs:AfdStandardAddressLength
0x14004adf9  mov     ecx, cs:AfdHugeBufferSize; Length
0x14004adff  call    AfdCalculateBufferSize
0x14004ae04  mov     r8b, cs:AfdTdiStackSize
0x14004ae0b  mov     edx, cs:AfdStandardAddressLength
0x14004ae11  mov     ecx, cs:AfdLargeBufferSize; Length
0x14004ae17  mov     eax, eax
0x14004ae19  mov     cs:AfdPplHugeBufferSize, rax
0x14004ae20  call    AfdCalculateBufferSize
0x14004ae25  mov     eax, eax
0x14004ae27  cmp     rax, cs:AfdPplHugeBufferSize
0x14004ae2e  mov     cs:AfdPplLargeBufferSize, rax
0x14004ae35  jnz     short loc_14004AE43
0x14004ae37  mov     eax, cs:AfdHugeBufferSize
0x14004ae3d  mov     cs:AfdLargeBufferSize, eax
0x14004ae43  mov     r8b, cs:AfdTdiStackSize
0x14004ae4a  mov     edx, cs:AfdStandardAddressLength
0x14004ae50  mov     ecx, cs:AfdMediumBufferSize; Length
0x14004ae56  call    AfdCalculateBufferSize
0x14004ae5b  mov     eax, eax
0x14004ae5d  cmp     rax, cs:AfdPplLargeBufferSize
0x14004ae64  mov     cs:AfdPplMediumBufferSize, rax
0x14004ae6b  jnz     short loc_14004AE79
0x14004ae6d  mov     eax, cs:AfdLargeBufferSize
0x14004ae73  mov     cs:AfdMediumBufferSize, eax
0x14004ae79  mov     r8b, cs:AfdTdiStackSize
0x14004ae80  mov     edx, cs:AfdStandardAddressLength
0x14004ae86  mov     ecx, cs:AfdSmallBufferSize; Length
0x14004ae8c  call    AfdCalculateBufferSize
0x14004ae91  mov     eax, eax
0x14004ae93  cmp     rax, cs:AfdPplMediumBufferSize
0x14004ae9a  mov     cs:AfdPplSmallBufferSize, rax
0x14004aea1  jnz     short loc_14004AEAF
0x14004aea3  mov     eax, cs:AfdMediumBufferSize
0x14004aea9  mov     cs:AfdSmallBufferSize, eax
0x14004aeaf  mov     eax, cs:AfdDefaultTpInfoElementCount
0x14004aeb5  lea     r8, AfdFreeTpInfo; Free
0x14004aebc  mov     word ptr [rsp+88h+DeviceObject], r14w; Depth
0x14004aec2  lea     rdx, AfdAllocateTpInfo; Allocate
0x14004aec9  mov     dword ptr [rsp+88h+Exclusive], 46646641h; Tag
0x14004aed1  mov     r9d, 200h; Flags
0x14004aed7  lea     ecx, [rax+rax*2]
0x14004aeda  lea     eax, ds:10Fh[rcx*8]
0x14004aee1  mov     rcx, cs:AfdGlobalData
0x14004aee8  and     eax, 0FFFFFFF0h
0x14004aeeb  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14004aeef  add     eax, 60h ; '`'
0x14004aef2  mov     qword ptr [rsp+88h+DeviceCharacteristics], rax; int
0x14004aef7  call    cs:__imp_ExInitializeNPagedLookasideList
0x14004aefe  nop     dword ptr [rax+rax+00h]
0x14004af03  mov     [rsp+88h+var_48], r15d; ULONG
0x14004af08  lea     rdx, AfdFreeBufferTag; int
0x14004af0f  mov     r13d, 400h
0x14004af15  lea     rcx, AfdAllocateBufferTag; int
0x14004af1c  mov     [rsp+88h+var_50], r13w; __int16
0x14004af22  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004af27  mov     qword ptr [rsp+88h+Exclusive], 68h ; 'h'; SIZE_T
0x14004af30  call    PplCreateLookasideList
0x14004af35  mov     cs:AfdPplBufferTagPool, rax
0x14004af3c  test    rax, rax
0x14004af3f  jz      loc_14004AD6C
0x14004af45  mov     rax, cs:AfdPplHugeBufferSize
0x14004af4c  lea     rdi, AfdFreeBuffer
0x14004af53  mov     [rsp+88h+var_48], r15d; ULONG
0x14004af58  lea     rcx, AfdAllocateBuffer; int
0x14004af5f  mov     [rsp+88h+var_50], r13w; __int16
0x14004af65  mov     rdx, rdi; int
0x14004af68  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004af6d  mov     qword ptr [rsp+88h+Exclusive], rax; SIZE_T
0x14004af72  call    PplCreateLookasideList
0x14004af77  mov     cs:AfdPplHugeBufferPool, rax
0x14004af7e  test    rax, rax
0x14004af81  jz      loc_14004AD6C
0x14004af87  mov     rax, cs:AfdPplLargeBufferSize
0x14004af8e  lea     rcx, AfdAllocateBuffer; int
0x14004af95  mov     [rsp+88h+var_48], r15d; ULONG
0x14004af9a  mov     rdx, rdi; int
0x14004af9d  mov     [rsp+88h+var_50], r13w; __int16
0x14004afa3  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004afa8  mov     qword ptr [rsp+88h+Exclusive], rax; SIZE_T
0x14004afad  call    PplCreateLookasideList
0x14004afb2  mov     cs:AfdPplLargeBufferPool, rax
0x14004afb9  test    rax, rax
0x14004afbc  jz      loc_14004AD6C
0x14004afc2  mov     rax, cs:AfdPplMediumBufferSize
0x14004afc9  lea     rcx, AfdAllocateBuffer; int
0x14004afd0  mov     [rsp+88h+var_48], r15d; ULONG
0x14004afd5  mov     rdx, rdi; int
0x14004afd8  mov     [rsp+88h+var_50], r13w; __int16
0x14004afde  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004afe3  mov     qword ptr [rsp+88h+Exclusive], rax; SIZE_T
0x14004afe8  call    PplCreateLookasideList
0x14004afed  mov     cs:AfdPplMediumBufferPool, rax
0x14004aff4  test    rax, rax
0x14004aff7  jz      loc_14004AD6C
0x14004affd  mov     rax, cs:AfdPplSmallBufferSize
0x14004b004  lea     rcx, AfdAllocateBuffer; int
0x14004b00b  mov     [rsp+88h+var_48], r15d; ULONG
0x14004b010  mov     rdx, rdi; int
0x14004b013  mov     [rsp+88h+var_50], r13w; __int16
0x14004b019  mov     dword ptr [rsp+88h+DeviceObject], r15d; ULONG
0x14004b01e  mov     qword ptr [rsp+88h+Exclusive], rax; SIZE_T
0x14004b023  call    PplCreateLookasideList
0x14004b028  mov     cs:AfdPplSmallBufferPool, rax
0x14004b02f  test    rax, rax
0x14004b032  jz      loc_14004AD6C
0x14004b038  mov     [rsp+88h+var_48], 43646641h; ULONG
0x14004b040  xor     edx, edx; int
0x14004b042  mov     [rsp+88h+var_50], r14w; __int16
0x14004b048  xor     ecx, ecx; int
0x14004b04a  mov     dword ptr [rsp+88h+DeviceObject], 43646641h; ULONG
0x14004b052  mov     qword ptr [rsp+88h+Exclusive], 100h; SIZE_T
0x14004b05b  call    PplCreateLookasideList
0x14004b060  mov     cs:PplConnectionPool, rax
0x14004b067  test    rax, rax
0x14004b06a  jz      loc_14004AD6C
0x14004b070  mov     [rsp+88h+var_48], 45646641h; ULONG
0x14004b078  xor     edx, edx; int
0x14004b07a  mov     [rsp+88h+var_50], r14w; __int16
0x14004b080  xor     ecx, ecx; int
0x14004b082  mov     dword ptr [rsp+88h+DeviceObject], 45646641h; ULONG
0x14004b08a  mov     qword ptr [rsp+88h+Exclusive], 1F0h; SIZE_T
0x14004b093  call    PplCreateLookasideList
0x14004b098  mov     cs:PplEndpointPool, rax
0x14004b09f  test    rax, rax
0x14004b0a2  jz      loc_14004AD6C
0x14004b0a8  mov     [rsp+88h+var_48], 45646641h; ULONG
0x14004b0b0  xor     edx, edx; int
0x14004b0b2  mov     [rsp+88h+var_50], r14w; __int16
0x14004b0b8  xor     ecx, ecx; int
0x14004b0ba  mov     dword ptr [rsp+88h+DeviceObject], 45646641h; ULONG
0x14004b0c2  mov     qword ptr [rsp+88h+Exclusive], 210h; SIZE_T
0x14004b0cb  call    PplCreateLookasideList
0x14004b0d0  mov     cs:PplTditlEndpointPool, rax
0x14004b0d7  test    rax, rax
0x14004b0da  jz      loc_14004AD6C
0x14004b0e0  mov     [rsp+88h+var_48], 734B5357h; ULONG
0x14004b0e8  xor     edx, edx; int
0x14004b0ea  mov     [rsp+88h+var_50], r14w; __int16
0x14004b0f0  xor     ecx, ecx; int
0x14004b0f2  mov     dword ptr [rsp+88h+DeviceObject], 734B5357h; ULONG
0x14004b0fa  mov     qword ptr [rsp+88h+Exclusive], 0C8h; SIZE_T
0x14004b103  call    PplCreateLookasideList
0x14004b108  mov     cs:WskProPplSocket, rax
0x14004b10f  test    rax, rax
0x14004b112  jz      loc_14004AD6C
0x14004b118  mov     ecx, cs:AfdStandardAddressLength
0x14004b11e  lea     rdx, AfdFreeRemoteAddress; int
0x14004b125  mov     [rsp+88h+var_48], 52646641h; ULONG
0x14004b12d  mov     [rsp+88h+var_50], r14w; __int16
0x14004b133  mov     dword ptr [rsp+88h+DeviceObject], 52646641h; ULONG
0x14004b13b  mov     qword ptr [rsp+88h+Exclusive], rcx; SIZE_T
0x14004b140  lea     rcx, AfdAllocateRemoteAddress; int
0x14004b147  call    PplCreateLookasideList
0x14004b14c  mov     cs:PplAddressPool, rax
0x14004b153  test    rax, rax
0x14004b156  jz      loc_14004AD6C
0x14004b15c  mov     rax, cs:AfdDeviceObject
0x14004b163  lea     rdx, AfdTrimLookasides
0x14004b16a  mov     qword ptr [rsp+88h+Exclusive], rax
0x14004b16f  lea     rcx, AfdTrimLookasidesWorkItem
0x14004b176  mov     r9d, 1
0x14004b17c  mov     qword ptr [rsp+88h+DeviceCharacteristics], r14
0x14004b181  xor     r8d, r8d
0x14004b184  call    cs:__imp_NetioTimerWorkItemInitialize
0x14004b18b  nop     dword ptr [rax+rax+00h]
0x14004b190  mov     edi, eax
0x14004b192  test    eax, eax
0x14004b194  js      loc_14004B31E
0x14004b19a  mov     edx, 0EA60h
0x14004b19f  lea     rcx, AfdTrimLookasidesWorkItem
0x14004b1a6  mov     bpl, 1
0x14004b1a9  call    cs:__imp_NetioTimerWorkItemStart
0x14004b1b0  nop     dword ptr [rax+rax+00h]
0x14004b1b5  call    AfdInitializeGroup
0x14004b1ba  test    al, al
0x14004b1bc  jz      loc_14004AD6C
0x14004b1c2  lea     rax, AfdDispatch
0x14004b1c9  mov     ecx, 1Ch
0x14004b1ce  lea     rdi, [rbx+70h]
0x14004b1d2  rep stosq
  ... truncated ...
```
