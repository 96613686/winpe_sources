# DriverEntry

- ea: `0x14001f078`
- end: `0x14001f588`
- name: `DriverEntry`
- size: `1296`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001f010`

## callees

- `0x140001008`
- `0x140003614`
- `0x140003b0c`
- `0x140003e44`
- `0x140004494`
- `0x140007920`
- `0x14000ab04`
- `0x14000abe0`
- `0x14000b0d0`
- `0x14000b5b4`
- `0x14000bfe8`
- `0x14000cb34`
- `0x14000d2d4`
- `0x140012d2c`
- `0x140013860`
- `0x14001e1a0`
- `0x14001e650`
- `0x14001e6fc`
- `0x14001e884`
- `0x14001f078`
- `0x14001f590`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x14001f134`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14001f134`
- `ntoskrnl!KeInitializeEvent` at `0x14001f21f`
- `ntoskrnl!KeInitializeEvent` at `0x14001f21f`
- `ntoskrnl!IoCreateDevice` at `0x14001f318`
- `ntoskrnl!IoCreateDevice` at `0x14001f318`
- `ntoskrnl!CmRegisterCallbackEx` at `0x14001f390`
- `ntoskrnl!CmRegisterCallbackEx` at `0x14001f390`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f14b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f26b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f339`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f14b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f26b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f339`
- `ntoskrnl!CmUnRegisterCallback` at `0x14001f52a`
- `ntoskrnl!CmUnRegisterCallback` at `0x14001f52a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001f546`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001f546`
- `ntoskrnl!IoDeleteDevice` at `0x14001f4e0`
- `ntoskrnl!IoDeleteDevice` at `0x14001f4e0`
- `ntoskrnl!ZwClose` at `0x14001f4cb`
- `ntoskrnl!ZwClose` at `0x14001f4cb`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001f408`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001f408`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f42e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f448`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f47c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f49f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f42e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f448`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f47c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f49f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f3f5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f3f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f414`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f414`
- `FLTMGR!FltStartFiltering` at `0x14001f3a9`
- `FLTMGR!FltStartFiltering` at `0x14001f3a9`
- `FLTMGR!FltRegisterFilter` at `0x14001f2c2`
- `FLTMGR!FltRegisterFilter` at `0x14001f2c2`
- `FLTMGR!FltUnregisterFilter` at `0x14001f4f8`
- `FLTMGR!FltUnregisterFilter` at `0x14001f4f8`
- `cng!BCryptCloseAlgorithmProvider` at `0x14001f512`
- `cng!BCryptCloseAlgorithmProvider` at `0x14001f512`
- `cng!BCryptOpenAlgorithmProvider` at `0x14001f28b`
- `cng!BCryptOpenAlgorithmProvider` at `0x14001f28b`

## string_xrefs

- `0x14001f140`: `\SystemRoot\System32\config\BFS`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  HANDLE v3; // rsi
  char v4; // r15
  char v5; // r12
  int v6; // eax
  int v7; // r8d
  int v8; // r9d
  int PolicyStorageDescriptor; // ebx
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // ebx
  int IsEnabledDeviceUsageNoInline; // eax
  const FLT_REGISTRATION *v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  PVOID v19; // rcx
  int DeviceCharacteristics; // [rsp+20h] [rbp-69h]
  int v22; // [rsp+40h] [rbp-49h] BYREF
  char v23; // [rsp+44h] [rbp-45h]
  HANDLE Handle; // [rsp+48h] [rbp-41h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-31h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+68h] [rbp-21h] BYREF
  UNICODE_STRING Altitude; // [rsp+78h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+88h] [rbp-1h] BYREF
  int *v30; // [rsp+A8h] [rbp+1Fh]
  __int64 v31; // [rsp+B0h] [rbp+27h]

  Altitude = 0;
  DeviceName = 0;
  DestinationString = 0;
  wil_InitializeFeatureStaging(DriverObject, RegistryPath);
  v3 = 0;
  Handle = 0;
  DeviceObject = 0;
  v4 = 0;
  v5 = 0;
  v23 = 0;
  v6 = BfsVerifyVolumeRootDescriptor();
  PolicyStorageDescriptor = v6;
  if ( v6 >= 0 )
  {
    PolicyStorageDescriptor = BfsCreatePolicyStorageDescriptor(gBfsPolicyStorageDirectoryDescriptor);
    if ( PolicyStorageDescriptor >= 0 )
    {
      PolicyStorageDescriptor = BfsCreatePolicyStorageDescriptor(gBfsPolicyStorageFileDescriptor);
      if ( PolicyStorageDescriptor >= 0 )
      {
        ExInitializeRundownProtection(&gBfsRundownProtection);
        RtlInitUnicodeString(&DestinationString, L"\\SystemRoot\\System32\\config\\BFS");
        PolicyStorageDescriptor = BfsInitializePolicyTable();
        if ( PolicyStorageDescriptor >= 0 )
        {
          PolicyStorageDescriptor = BfsInitializePipeMappingTable();
          if ( PolicyStorageDescriptor >= 0 )
          {
            PolicyStorageDescriptor = BfsOpenPolicyRootDirectory(&DestinationString, &Handle);
            if ( PolicyStorageDescriptor < 0 )
            {
              if ( (unsigned int)dword_140019000 > 3 )
              {
                v22 = PolicyStorageDescriptor;
                v30 = &v22;
                v31 = 4;
                tlgWriteTransfer_EtwWriteTransfer(v11, (int)&byte_140016D91, v12, v13, DeviceCharacteristics, &v29);
              }
              v3 = Handle;
              goto LABEL_29;
            }
            v3 = Handle;
            v14 = BfsVerifyPolicySecurity(Handle);
            gBfsDeleteThreshold = BfsReadDeleteThresholdFromRegistry();
            if ( v14 >= 0 || (PolicyStorageDescriptor = BfsUpdatePolicySecurity(v3), PolicyStorageDescriptor >= 0) )
            {
              PolicyStorageDescriptor = BfsInitializeBootDevice(&gBfsBootDevice);
              if ( PolicyStorageDescriptor >= 0 )
              {
                KeInitializeEvent(&Event, NotificationEvent, 0);
                DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&BfsClose;
                DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&BfsClose;
                DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)BfsDeviceIoControl;
                DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&BfsClose;
                RtlInitUnicodeString(&DeviceName, L"\\Device\\Bfs");
                PolicyStorageDescriptor = BCryptOpenAlgorithmProvider(&gBfsSHA256Handle, L"SHA256", 0, 0);
                if ( PolicyStorageDescriptor >= 0 )
                {
                  IsEnabledDeviceUsageNoInline = Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(v10);
                  v16 = (const FLT_REGISTRATION *)&FilterRegistrationAgentic;
                  if ( !IsEnabledDeviceUsageNoInline )
                    v16 = &FilterRegistration;
                  PolicyStorageDescriptor = FltRegisterFilter(DriverObject, v16, &gBfsFilterHandle);
                  if ( PolicyStorageDescriptor >= 0 )
                  {
                    v4 = 1;
                    if ( !(unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(v10)
                      || (PolicyStorageDescriptor = BfsSetApplicableCapabilitySid(), PolicyStorageDescriptor >= 0) )
                    {
                      PolicyStorageDescriptor = IoCreateDevice(
                                                  DriverObject,
                                                  0,
                                                  &DeviceName,
                                                  0x22u,
                                                  0x100u,
                                                  0,
                                                  &DeviceObject);
                      if ( PolicyStorageDescriptor >= 0 )
                      {
                        RtlInitUnicodeString(&Altitude, L"100010");
                        TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
                        gBfsDeviceObject = DeviceObject;
                        gBfsRootDirectory = v3;
                        PolicyStorageDescriptor = BfsInitializeGlobalFileTable(v18, v17, &gBfsGlobalFileTable);
                        if ( PolicyStorageDescriptor >= 0 )
                        {
                          PolicyStorageDescriptor = CmRegisterCallbackEx(
                                                      (PEX_CALLBACK_FUNCTION)BfsRegistryCallback,
                                                      &Altitude,
                                                      DriverObject,
                                                      0,
                                                      &gBfsRegistryCookie,
                                                      0);
                          if ( PolicyStorageDescriptor >= 0 )
                          {
                            PolicyStorageDescriptor = FltStartFiltering(gBfsFilterHandle);
                            if ( PolicyStorageDescriptor >= 0 )
                              return PolicyStorageDescriptor;
                            v5 = 1;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v22 = PolicyStorageDescriptor;
      goto LABEL_28;
    }
  }
  else
  {
    LODWORD(v10) = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v22 = v6;
LABEL_28:
      v31 = 4;
      v30 = &v22;
      tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v7, v8, DeviceCharacteristics, &v29);
    }
  }
LABEL_29:
  KeEnterCriticalRegion();
  ExWaitForRundownProtectionRelease(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( qword_1400191F8 )
    ExFreePoolWithTag(qword_1400191F8, 0);
  if ( qword_1400191F0 )
    ExFreePoolWithTag(qword_1400191F0, 0);
  if ( qword_1400191D0 )
    ExFreePoolWithTag(qword_1400191D0, 0);
  v19 = qword_1400191C8;
  if ( qword_1400191C8 )
    ExFreePoolWithTag(qword_1400191C8, 0);
  if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(v19)
    && gApplicableCapabilitySid )
  {
    ExFreePoolWithTag(gApplicableCapabilitySid, 0);
  }
  BfsUninitializePipeMappingTable(&gBfsPipeMappingTable);
  BfsUninitializePolicyTable(&gBfsPolicyTable);
  if ( v3 )
    ZwClose(v3);
  if ( DeviceObject )
    IoDeleteDevice(DeviceObject);
  if ( v4 )
    FltUnregisterFilter(gBfsFilterHandle);
  if ( gBfsSHA256Handle )
    BCryptCloseAlgorithmProvider(gBfsSHA256Handle, 0);
  if ( v5 )
    CmUnRegisterCallback(gBfsRegistryCookie);
  if ( gBfsBootDevice.Buffer )
    RtlFreeUnicodeString(&gBfsBootDevice);
  TraceLoggingUnregister_EtwUnregister();
  wil_UninitializeFeatureStaging();
  return PolicyStorageDescriptor;
}

```

## disassembly

```asm
0x14001f078  mov     [rsp-8+arg_8], rbx
0x14001f07d  mov     [rsp-8+arg_10], rsi
0x14001f082  push    rbp
0x14001f083  push    r12
0x14001f085  push    r13
0x14001f087  push    r14
0x14001f089  push    r15
0x14001f08b  lea     rbp, [rsp-37h]
0x14001f090  sub     rsp, 0C0h
0x14001f097  mov     rax, cs:__security_cookie
0x14001f09e  xor     rax, rsp
0x14001f0a1  mov     [rbp+57h+var_28], rax
0x14001f0a5  xorps   xmm0, xmm0
0x14001f0a8  xorps   xmm1, xmm1
0x14001f0ab  xor     r13d, r13d
0x14001f0ae  mov     r14, rcx
0x14001f0b1  movups  xmmword ptr [rbp+57h+Altitude.Length], xmm0
0x14001f0b5  mov     [rbp+57h+var_90], r13
0x14001f0b9  movups  xmmword ptr [rbp+57h+DeviceName.Length], xmm1
0x14001f0bd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001f0c1  call    wil_InitializeFeatureStaging
0x14001f0c6  mov     esi, r13d
0x14001f0c9  mov     [rbp+57h+Handle], r13
0x14001f0cd  mov     [rbp+57h+var_90], r13
0x14001f0d1  mov     r15b, r13b
0x14001f0d4  mov     r12b, r13b
0x14001f0d7  mov     [rbp+57h+var_9C], r13b
0x14001f0db  call    BfsVerifyVolumeRootDescriptor
0x14001f0e0  mov     ebx, eax
0x14001f0e2  test    eax, eax
0x14001f0e4  jns     short loc_14001F0FD
0x14001f0e6  mov     ecx, cs:dword_140019000
0x14001f0ec  cmp     ecx, 3
0x14001f0ef  jbe     loc_14001F3F5
0x14001f0f5  mov     [rbp+57h+var_A0], eax
0x14001f0f8  jmp     loc_14001F3D0
0x14001f0fd  mov     dl, 3
0x14001f0ff  lea     rcx, gBfsPolicyStorageDirectoryDescriptor; SecurityDescriptor
0x14001f106  call    BfsCreatePolicyStorageDescriptor
0x14001f10b  mov     ebx, eax
0x14001f10d  test    eax, eax
0x14001f10f  js      loc_14001F3C2
0x14001f115  xor     edx, edx
0x14001f117  lea     rcx, gBfsPolicyStorageFileDescriptor; SecurityDescriptor
0x14001f11e  call    BfsCreatePolicyStorageDescriptor
0x14001f123  mov     ebx, eax
0x14001f125  test    eax, eax
0x14001f127  js      loc_14001F3C2
0x14001f12d  lea     rcx, gBfsRundownProtection; RunRef
0x14001f134  call    cs:__imp_ExInitializeRundownProtection
0x14001f13b  nop     dword ptr [rax+rax+00h]
0x14001f140  lea     rdx, aSystemrootSyst; "\\SystemRoot\\System32\\config\\BFS"
0x14001f147  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f14b  call    cs:__imp_RtlInitUnicodeString
0x14001f152  nop     dword ptr [rax+rax+00h]
0x14001f157  call    BfsInitializePolicyTable
0x14001f15c  mov     ebx, eax
0x14001f15e  test    eax, eax
0x14001f160  js      loc_14001F3C2
0x14001f166  call    BfsInitializePipeMappingTable
0x14001f16b  mov     ebx, eax
0x14001f16d  test    eax, eax
0x14001f16f  js      loc_14001F3C2
0x14001f175  lea     rdx, [rbp+57h+Handle]
0x14001f179  lea     rcx, [rbp+57h+DestinationString]
0x14001f17d  call    BfsOpenPolicyRootDirectory
0x14001f182  mov     ebx, eax
0x14001f184  test    eax, eax
0x14001f186  jns     short loc_14001F1C4
0x14001f188  mov     eax, cs:dword_140019000
0x14001f18e  cmp     eax, 3
0x14001f191  jbe     short loc_14001F1BB
0x14001f193  lea     rax, [rbp+57h+var_A0]
0x14001f197  mov     [rbp+57h+var_A0], ebx
0x14001f19a  mov     [rbp+57h+var_38], rax
0x14001f19e  lea     rdx, byte_140016D91; int
0x14001f1a5  lea     rax, [rbp+57h+var_58]
0x14001f1a9  mov     [rbp+57h+var_30], 4
0x14001f1b1  mov     qword ptr [rsp+0E0h+Exclusive], rax; PEVENT_DATA_DESCRIPTOR
0x14001f1b6  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001f1bb  mov     rsi, [rbp+57h+Handle]
0x14001f1bf  jmp     loc_14001F3F5
0x14001f1c4  mov     rsi, [rbp+57h+Handle]
0x14001f1c8  lea     rdx, [rbp+57h+var_9C]
0x14001f1cc  mov     rcx, rsi; Handle
0x14001f1cf  call    BfsVerifyPolicySecurity
0x14001f1d4  mov     ebx, eax
0x14001f1d6  call    BfsReadDeleteThresholdFromRegistry
0x14001f1db  mov     cs:gBfsDeleteThreshold, eax
0x14001f1e1  test    ebx, ebx
0x14001f1e3  js      short loc_14001F1EB
0x14001f1e5  cmp     [rbp+57h+var_9C], r13b
0x14001f1e9  jz      short loc_14001F1FD
0x14001f1eb  mov     rcx, rsi; Handle
0x14001f1ee  call    BfsUpdatePolicySecurity
0x14001f1f3  mov     ebx, eax
0x14001f1f5  test    eax, eax
0x14001f1f7  js      loc_14001F3C2
0x14001f1fd  lea     rcx, gBfsBootDevice; LinkTarget
0x14001f204  call    BfsInitializeBootDevice
0x14001f209  mov     ebx, eax
0x14001f20b  test    eax, eax
0x14001f20d  js      loc_14001F3C2
0x14001f213  xor     r8d, r8d; State
0x14001f216  lea     rcx, Event; Event
0x14001f21d  xor     edx, edx; Type
0x14001f21f  call    cs:__imp_KeInitializeEvent
0x14001f226  nop     dword ptr [rax+rax+00h]
0x14001f22b  lea     rax, BfsClose
0x14001f232  mov     [r14+70h], rax
0x14001f236  lea     rdx, aDeviceBfs; "\\Device\\Bfs"
0x14001f23d  lea     rax, BfsClose
0x14001f244  mov     [r14+100h], rax
0x14001f24b  lea     rcx, [rbp+57h+DeviceName]; DestinationString
0x14001f24f  lea     rax, BfsDeviceIoControl
0x14001f256  mov     [r14+0E0h], rax
0x14001f25d  lea     rax, BfsClose
0x14001f264  mov     [r14+80h], rax
0x14001f26b  call    cs:__imp_RtlInitUnicodeString
0x14001f272  nop     dword ptr [rax+rax+00h]
0x14001f277  xor     r9d, r9d; dwFlags
0x14001f27a  lea     rdx, pszAlgId; "SHA256"
0x14001f281  xor     r8d, r8d; pszImplementation
0x14001f284  lea     rcx, gBfsSHA256Handle; phAlgorithm
0x14001f28b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14001f292  nop     dword ptr [rax+rax+00h]
0x14001f297  mov     ebx, eax
0x14001f299  test    eax, eax
0x14001f29b  js      loc_14001F3C2
0x14001f2a1  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14001f2a6  lea     r8, gBfsFilterHandle; RetFilter
0x14001f2ad  mov     rcx, r14; Driver
0x14001f2b0  lea     rdx, FilterRegistrationAgentic
0x14001f2b7  test    eax, eax
0x14001f2b9  jnz     short loc_14001F2C2
0x14001f2bb  lea     rdx, FilterRegistration; Registration
0x14001f2c2  call    cs:__imp_FltRegisterFilter
0x14001f2c9  nop     dword ptr [rax+rax+00h]
0x14001f2ce  mov     ebx, eax
0x14001f2d0  test    eax, eax
0x14001f2d2  js      loc_14001F3C2
0x14001f2d8  mov     r15b, 1
0x14001f2db  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14001f2e0  test    eax, eax
0x14001f2e2  jz      short loc_14001F2F3
0x14001f2e4  call    BfsSetApplicableCapabilitySid
0x14001f2e9  mov     ebx, eax
0x14001f2eb  test    eax, eax
0x14001f2ed  js      loc_14001F3C2
0x14001f2f3  lea     rax, [rbp+57h+var_90]
0x14001f2f7  mov     r9d, 22h ; '"'; DeviceType
0x14001f2fd  mov     [rsp+0E0h+DeviceObject], rax; DeviceObject
0x14001f302  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x14001f306  mov     [rsp+0E0h+Exclusive], r13b; Exclusive
0x14001f30b  xor     edx, edx; DeviceExtensionSize
0x14001f30d  mov     rcx, r14; DriverObject
0x14001f310  mov     [rsp+0E0h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14001f318  call    cs:__imp_IoCreateDevice
0x14001f31f  nop     dword ptr [rax+rax+00h]
0x14001f324  mov     ebx, eax
0x14001f326  test    eax, eax
0x14001f328  js      loc_14001F3C2
0x14001f32e  lea     rdx, a100010; "100010"
0x14001f335  lea     rcx, [rbp+57h+Altitude]; DestinationString
0x14001f339  call    cs:__imp_RtlInitUnicodeString
0x14001f340  nop     dword ptr [rax+rax+00h]
0x14001f345  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14001f34a  mov     rax, [rbp+57h+var_90]
0x14001f34e  lea     r8, gBfsGlobalFileTable
0x14001f355  mov     cs:gBfsDeviceObject, rax
0x14001f35c  mov     cs:gBfsRootDirectory, rsi
0x14001f363  call    BfsInitializeGlobalFileTable
0x14001f368  mov     ebx, eax
0x14001f36a  test    eax, eax
0x14001f36c  js      short loc_14001F3C2
0x14001f36e  lea     rax, gBfsRegistryCookie
0x14001f375  mov     qword ptr [rsp+0E0h+Exclusive], r13; Reserved
0x14001f37a  xor     r9d, r9d; Context
0x14001f37d  mov     qword ptr [rsp+0E0h+DeviceCharacteristics], rax; int
0x14001f382  mov     r8, r14; Driver
0x14001f385  lea     rdx, [rbp+57h+Altitude]; Altitude
0x14001f389  lea     rcx, BfsRegistryCallback; Function
0x14001f390  call    cs:__imp_CmRegisterCallbackEx
0x14001f397  nop     dword ptr [rax+rax+00h]
0x14001f39c  mov     ebx, eax
0x14001f39e  test    eax, eax
0x14001f3a0  js      short loc_14001F3C2
0x14001f3a2  mov     rcx, cs:gBfsFilterHandle; Filter
0x14001f3a9  call    cs:__imp_FltStartFiltering
0x14001f3b0  nop     dword ptr [rax+rax+00h]
0x14001f3b5  mov     ebx, eax
0x14001f3b7  test    eax, eax
0x14001f3b9  jns     loc_14001F55C
0x14001f3bf  mov     r12b, r15b
0x14001f3c2  mov     eax, cs:dword_140019000
0x14001f3c8  cmp     eax, 3
0x14001f3cb  jbe     short loc_14001F3F5
0x14001f3cd  mov     [rbp+57h+var_A0], ebx
0x14001f3d0  lea     rax, [rbp+57h+var_A0]
0x14001f3d4  mov     [rbp+57h+var_30], 4
0x14001f3dc  mov     [rbp+57h+var_38], rax
0x14001f3e0  lea     rdx, byte_140016D91; int
0x14001f3e7  lea     rax, [rbp+57h+var_58]
0x14001f3eb  mov     qword ptr [rsp+0E0h+Exclusive], rax; PEVENT_DATA_DESCRIPTOR
0x14001f3f0  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001f3f5  call    cs:__imp_KeEnterCriticalRegion
0x14001f3fc  nop     dword ptr [rax+rax+00h]
0x14001f401  lea     rcx, gBfsRundownProtection; RunRef
0x14001f408  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14001f40f  nop     dword ptr [rax+rax+00h]
0x14001f414  call    cs:__imp_KeLeaveCriticalRegion
0x14001f41b  nop     dword ptr [rax+rax+00h]
0x14001f420  mov     rcx, cs:qword_1400191F8; P
0x14001f427  test    rcx, rcx
0x14001f42a  jz      short loc_14001F43A
0x14001f42c  xor     edx, edx; Tag
0x14001f42e  call    cs:__imp_ExFreePoolWithTag
0x14001f435  nop     dword ptr [rax+rax+00h]
0x14001f43a  mov     rcx, cs:qword_1400191F0; P
0x14001f441  test    rcx, rcx
0x14001f444  jz      short loc_14001F454
0x14001f446  xor     edx, edx; Tag
0x14001f448  call    cs:__imp_ExFreePoolWithTag
0x14001f44f  nop     dword ptr [rax+rax+00h]
0x14001f454  mov     rcx, cs:qword_1400191D0; P
0x14001f45b  test    rcx, rcx
0x14001f45e  jz      short loc_14001F46E
0x14001f460  xor     edx, edx; Tag
0x14001f462  call    cs:__imp_ExFreePoolWithTag
0x14001f469  nop     dword ptr [rax+rax+00h]
0x14001f46e  mov     rcx, cs:qword_1400191C8; P
0x14001f475  test    rcx, rcx
0x14001f478  jz      short loc_14001F488
0x14001f47a  xor     edx, edx; Tag
0x14001f47c  call    cs:__imp_ExFreePoolWithTag
0x14001f483  nop     dword ptr [rax+rax+00h]
0x14001f488  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14001f48d  test    eax, eax
0x14001f48f  jz      short loc_14001F4AB
0x14001f491  mov     rcx, cs:gApplicableCapabilitySid; P
0x14001f498  test    rcx, rcx
0x14001f49b  jz      short loc_14001F4AB
0x14001f49d  xor     edx, edx; Tag
0x14001f49f  call    cs:__imp_ExFreePoolWithTag
0x14001f4a6  nop     dword ptr [rax+rax+00h]
0x14001f4ab  lea     rcx, gBfsPipeMappingTable
0x14001f4b2  call    BfsUninitializePipeMappingTable
0x14001f4b7  lea     rcx, gBfsPolicyTable
0x14001f4be  call    BfsUninitializePolicyTable
0x14001f4c3  test    rsi, rsi
0x14001f4c6  jz      short loc_14001F4D7
0x14001f4c8  mov     rcx, rsi; Handle
0x14001f4cb  call    cs:__imp_ZwClose
0x14001f4d2  nop     dword ptr [rax+rax+00h]
0x14001f4d7  mov     rcx, [rbp+57h+var_90]; DeviceObject
0x14001f4db  test    rcx, rcx
0x14001f4de  jz      short loc_14001F4EC
0x14001f4e0  call    cs:__imp_IoDeleteDevice
0x14001f4e7  nop     dword ptr [rax+rax+00h]
0x14001f4ec  test    r15b, r15b
0x14001f4ef  jz      short loc_14001F504
0x14001f4f1  mov     rcx, cs:gBfsFilterHandle; Filter
0x14001f4f8  call    cs:__imp_FltUnregisterFilter
0x14001f4ff  nop     dword ptr [rax+rax+00h]
0x14001f504  mov     rcx, cs:gBfsSHA256Handle; hAlgorithm
0x14001f50b  test    rcx, rcx
0x14001f50e  jz      short loc_14001F51E
0x14001f510  xor     edx, edx; dwFlags
0x14001f512  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14001f519  nop     dword ptr [rax+rax+00h]
0x14001f51e  test    r12b, r12b
0x14001f521  jz      short loc_14001F536
0x14001f523  mov     rcx, qword ptr cs:gBfsRegistryCookie; Cookie
0x14001f52a  call    cs:__imp_CmUnRegisterCallback
0x14001f531  nop     dword ptr [rax+rax+00h]
0x14001f536  cmp     cs:gBfsBootDevice.Buffer, r13
0x14001f53d  jz      short loc_14001F552
0x14001f53f  lea     rcx, gBfsBootDevice; UnicodeString
0x14001f546  call    cs:__imp_RtlFreeUnicodeString
0x14001f54d  nop     dword ptr [rax+rax+00h]
0x14001f552  call    TraceLoggingUnregister_EtwUnregister
0x14001f557  call    wil_UninitializeFeatureStaging
0x14001f55c  mov     eax, ebx
0x14001f55e  mov     rcx, [rbp+57h+var_28]
0x14001f562  xor     rcx, rsp; StackCookie
0x14001f565  call    __security_check_cookie
0x14001f56a  lea     r11, [rsp+0E0h+var_20]
0x14001f572  mov     rbx, [r11+38h]
0x14001f576  mov     rsi, [r11+40h]
0x14001f57a  mov     rsp, r11
0x14001f57d  pop     r15
0x14001f57f  pop     r14
0x14001f581  pop     r13
0x14001f583  pop     r12
0x14001f585  pop     rbp
0x14001f586  retn
```
