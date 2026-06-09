# UxStartEnvironmentModule

- ea: `0x1400dfbe0`
- end: `0x1400e03c7`
- name: `UxStartEnvironmentModule`
- size: `2023`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14008fdfc`
- `0x1400a2f40`
- `0x1400d6da4`
- `0x1400de424`
- `0x1400de47c`
- `0x1400de4d4`
- `0x1400de52c`
- `0x1400de584`
- `0x1400de5dc`
- `0x1400de634`
- `0x1400de68c`
- `0x1400de6e4`
- `0x1400de73c`
- `0x1400de794`
- `0x1400de7ec`
- `0x1400de844`
- `0x1400deb24`
- `0x1400deb80`
- `0x1400dfbe0`
- `0x1400e0420`
- `0x140103f10`
- `0x14010479c`
- `0x140167810`
- `0x140167c40`
- `0x1401c3f58`
- `0x1401da5a4`
- `0x1401df078`

## import_xrefs

- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400dffb0`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400dffb0`
- `ntoskrnl!RtlGetVersion` at `0x1400e0051`
- `ntoskrnl!RtlGetVersion` at `0x1400e0051`
- `ntoskrnl!ZwOpenKey` at `0x1400e00c6`
- `ntoskrnl!ZwOpenKey` at `0x1400e00c6`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400dffc2`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400dffc2`
- `ntoskrnl!ZwClose` at `0x1400e0373`
- `ntoskrnl!ZwClose` at `0x1400e0373`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e038e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e038e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400e007a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400e007a`
- `HAL!KeQueryPerformanceCounter` at `0x1400e0329`
- `HAL!KeQueryPerformanceCounter` at `0x1400e0329`

## string_xrefs

- `0x1400dfc2f`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters`
- `0x1400e00f3`: `CompactMode`
- `0x1400e02e9`: `AllowNonprivilegedCaptureCred`

## pseudocode

```c
__int64 UxStartEnvironmentModule()
{
  void *QuadPart; // rdi
  int PhysicalMemorySize; // ebx
  void *v2; // rcx
  __int64 v3; // r8
  char LongLongParameter; // al
  _BYTE v6[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v8; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v10[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  _BYTE VersionInformation[284]; // [rsp+A0h] [rbp-60h] BYREF

  memset(VersionInformation, 0, sizeof(VersionInformation));
  v10[0] = 8913030;
  KeyHandle = 0;
  v8 = 0;
  v10[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters";
  QuadPart = 0;
  PerformanceFrequency.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  v6[0] = 0;
  PhysicalMemorySize = wil_InitializeFeatureStaging();
  if ( PhysicalMemorySize >= 0 )
  {
    UxFeatureStagingInitialized = 1;
    UxKirDtHttpFastForwardHttp11Client = (unsigned int)Feature_DtHttpFastForwardHttp11Client__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirBrHttpQuerySocketTtl = (unsigned int)Feature_HttpQueryTcpTtlRedux__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirDtHttp2IsbLimit = (unsigned int)Feature_DtHttpIsbLimitHttp2__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpBugFix25Q1 = (unsigned int)Feature_HttpBugFix25Q1__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirAddDisableAiaFlag = (unsigned int)Feature_Servicing_AddDisableAiaFlag__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirRefactorIoctls = (unsigned int)Feature_RefactorIoctls__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirMsQuic_2_5 = (unsigned int)Feature_MsQuic_2_5__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpBugFix26Q1 = (unsigned int)Feature_HttpBugFix26Q1__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpReadingTrailersFromUm = 1;
    UxKirWritingAndReadingUm = 1;
    UxKirWritingAndReadingUmCertList = 1;
    UxKirHKERangeRequestH2StatusCode = (unsigned int)Feature_HttpsysHKERangeRequestH2StatusCode__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpTlsHandshakePerfCounter = (unsigned int)Feature_HttpTlsHandshakePerfCounter__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirNewUma = (unsigned int)Feature_NewUMAHttpSys__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpBugFix26Q2 = (unsigned int)Feature_HttpBugFix26Q2__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirQuicParseLengthCheck = 1;
    UxKirHttpBugFix2605 = (unsigned int)Feature_HttpBugFix2605__private_IsEnabledDeviceUsageNoInline() != 0;
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1049, 10, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids, (unsigned __int8)UxKirHttpBugFix25Q1);
    if ( UxKirDtHttp2IsbLimit && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 11, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirDtHttpFastForwardHttp11Client && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 12, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirHttpBugFix25Q1 && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 13, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirBrHttpQuerySocketTtl && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 14, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirAddDisableAiaFlag && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 15, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirMsQuic_2_5 && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 16, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirHKERangeRequestH2StatusCode && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 17, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirRefactorIoctls && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 18, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirHttpBugFix26Q1 && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 19, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirHttpReadingTrailersFromUm && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 20, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirWritingAndReadingUm && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 21, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirWritingAndReadingUmCertList && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 22, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirHttpTlsHandshakePerfCounter && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 23, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirNewUma && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 24, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirHttpBugFix26Q2 && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 25, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirQuicParseLengthCheck && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 26, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    if ( UxKirHttpBugFix2605 && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 27, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids);
    UxNumberOfProcessors = 0;
    UxMaximumNumberOfProcessors = KeQueryMaximumProcessorCountEx(0xFFFFu);
    UxNumberOfNodes = KeQueryHighestNodeNumber() + 1;
    PhysicalMemorySize = UxGetPhysicalMemorySize(&UxTotalPhysicalMemMB);
    if ( PhysicalMemorySize >= 0 )
    {
      PhysicalMemorySize = UxOpenNamedEvent(L"\\KernelObjects\\LowNonPagedPoolCondition");
      if ( PhysicalMemorySize >= 0 )
      {
        PhysicalMemorySize = UxOpenNamedEvent(L"\\KernelObjects\\HighNonPagedPoolCondition");
        if ( PhysicalMemorySize >= 0 )
        {
          PhysicalMemorySize = UxOpenNamedEvent(L"\\KernelObjects\\LowMemoryCondition");
          if ( PhysicalMemorySize >= 0 )
          {
            *(_DWORD *)VersionInformation = 284;
            PhysicalMemorySize = RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation);
            if ( PhysicalMemorySize >= 0 )
            {
              UxServerSystem = (unsigned __int8)(VersionInformation[282] - 2) <= 1u;
              UxSystemProcess = IoGetCurrentProcess();
              HttpCmnInitializeStaticHttpCharsTable();
              ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = (PUNICODE_STRING)v10;
              ObjectAttributes.RootDirectory = 0;
              ObjectAttributes.Attributes = 576;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              PhysicalMemorySize = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
              if ( PhysicalMemorySize >= 0 )
              {
                v2 = KeyHandle;
              }
              else
              {
                v2 = 0;
                PhysicalMemorySize = 0;
                KeyHandle = 0;
              }
              UxReadBooleanSetting(v2, L"CompactMode", 0, &UxCompactMode);
              if ( UxKirHttpBugFix25Q1 )
                UxReadBooleanSetting(KeyHandle, L"EnableIrqlEnforcement", 0, &UxEnableIrqlEnforcement);
              UxReadBooleanSetting(KeyHandle, L"SendEndpointInfoToAsc", 0, &UxSendEndpointInfoToASC);
              UxReadBooleanSetting(KeyHandle, L"TlsUseStaticServerHello", 0, &UxTlsUseStaticServerHello);
              UxReadBoundedULongSetting(
                (_DWORD)KeyHandle,
                (unsigned int)L"AscThrottleLimit",
                0,
                0,
                0x7FFFFFFF,
                0,
                (__int64)&UxAscThrottleLimit);
              LOBYTE(v3) = 1;
              UxReadBooleanSetting(KeyHandle, L"EnableSslLargeBuffer", v3, &UxSslLargeBufferEnabled);
              UxReadBoundedULongSetting(
                (_DWORD)KeyHandle,
                (unsigned int)L"RssStatusCheckControl",
                1,
                0,
                2,
                0,
                (__int64)&UxRssEnabledCheckControl);
              UxReadBooleanSetting(KeyHandle, L"EnableHttp3", 0, &UxHttp3ServerEnabled);
              UxReadBooleanSetting(KeyHandle, L"EnableHttp3Push", 0, &UxHttp3PushEnabled);
              UxReadBooleanSetting(KeyHandle, L"EnableExtendedEvents", 0, &UxExtendedEventsEnabled);
              UxReadBoundedULongSetting(
                (_DWORD)KeyHandle,
                (unsigned int)L"ExtendedEventsFrequency",
                3600,
                15,
                0x7FFFFFFF,
                0,
                (__int64)&v8);
              UxExtendedEventsFrequency = 10000000LL * v8;
              UxReadBooleanSetting(KeyHandle, L"EnableAltSvc", 0, &UxAltSvcEnabled);
              if ( UxTelAssertInitialized )
                UxReadBooleanSetting(KeyHandle, L"EnableTelAsserts", 0, &UxTelAssertsEnabled);
              else
                UxTelAssertsEnabled = 0;
              UlReadGenericParameter(KeyHandle);
              QuadPart = (void *)PerformanceFrequency.QuadPart;
              if ( PerformanceFrequency.QuadPart && *(_DWORD *)(PerformanceFrequency.QuadPart + 4) == 7 )
              {
                UxHttp3AlpnRegValue = (PVOID)PerformanceFrequency.QuadPart;
                QuadPart = 0;
              }
              UxReadBooleanSetting(KeyHandle, L"AllowNonprivilegedCaptureCred", 0, &UxAllowNonprivilegedCaptureCred);
              LongLongParameter = UlReadLongLongParameter(KeyHandle, L"DebugFlags", 0);
              PerformanceFrequency.QuadPart = 0;
              UxDebugCheckRefcount = LongLongParameter & 1;
              UxDebugDisableLookaside = (LongLongParameter & 2) != 0;
              KeQueryPerformanceCounter(&PerformanceFrequency);
              UxPerformanceCounterPeriod = PerformanceFrequency.QuadPart;
              UxReadBooleanSetting(KeyHandle, L"DisableMultipleLanes", 0, v6);
              if ( v6[0] )
                UxNumberOfNodes = 1;
            }
          }
        }
      }
    }
  }
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( QuadPart )
    ExFreePoolWithTag(QuadPart, 0);
  if ( PhysicalMemorySize < 0 )
    UxStopEnvironmentModule();
  return (unsigned int)PhysicalMemorySize;
}

```

## disassembly

```asm
0x1400dfbe0  push    rbp
0x1400dfbe2  push    rbx
0x1400dfbe3  push    rsi
0x1400dfbe4  push    rdi
0x1400dfbe5  push    r12
0x1400dfbe7  push    r14
0x1400dfbe9  push    r15
0x1400dfbeb  lea     rbp, [rsp-0D0h]
0x1400dfbf3  sub     rsp, 1D0h
0x1400dfbfa  mov     rax, cs:__security_cookie
0x1400dfc01  xor     rax, rsp
0x1400dfc04  mov     [rbp+100h+var_40], rax
0x1400dfc0b  xor     edx, edx; Val
0x1400dfc0d  lea     rcx, [rbp+100h+VersionInformation]; void *
0x1400dfc11  mov     r8d, 11Ch; Size
0x1400dfc17  call    memset
0x1400dfc1c  xor     esi, esi
0x1400dfc1e  mov     [rsp+200h+var_1A0], 880086h
0x1400dfc27  xorps   xmm0, xmm0
0x1400dfc2a  mov     [rsp+200h+KeyHandle], rsi
0x1400dfc2f  lea     rax, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400dfc36  mov     [rsp+200h+var_1B0], esi
0x1400dfc3a  mov     [rsp+200h+var_198], rax
0x1400dfc3f  mov     edi, esi
0x1400dfc41  movups  xmmword ptr [rbp+100h+ObjectAttributes.ObjectName], xmm0
0x1400dfc45  xor     eax, eax
0x1400dfc47  mov     qword ptr [rsp+200h+PerformanceFrequency], rsi
0x1400dfc4c  movups  xmmword ptr [rsp+200h+ObjectAttributes.Length], xmm0
0x1400dfc51  mov     [rsp+200h+var_1C0], sil
0x1400dfc56  movups  xmmword ptr [rbp+100h+ObjectAttributes+1Ch], xmm0
0x1400dfc5a  call    wil_InitializeFeatureStaging
0x1400dfc5f  mov     ebx, eax
0x1400dfc61  test    eax, eax
0x1400dfc63  js      loc_1400E0369
0x1400dfc69  lea     r12d, [rsi+1]
0x1400dfc6d  mov     cs:UxFeatureStagingInitialized, r12b
0x1400dfc74  call    Feature_DtHttpFastForwardHttp11Client__private_IsEnabledDeviceUsageNoInline
0x1400dfc79  test    eax, eax
0x1400dfc7b  setnz   cs:UxKirDtHttpFastForwardHttp11Client
0x1400dfc82  call    Feature_HttpQueryTcpTtlRedux__private_IsEnabledDeviceUsageNoInline
0x1400dfc87  test    eax, eax
0x1400dfc89  setnz   cs:UxKirBrHttpQuerySocketTtl
0x1400dfc90  call    Feature_DtHttpIsbLimitHttp2__private_IsEnabledDeviceUsageNoInline
0x1400dfc95  test    eax, eax
0x1400dfc97  setnz   cs:UxKirDtHttp2IsbLimit
0x1400dfc9e  call    Feature_HttpBugFix25Q1__private_IsEnabledDeviceUsageNoInline
0x1400dfca3  test    eax, eax
0x1400dfca5  setnz   cs:UxKirHttpBugFix25Q1
0x1400dfcac  call    Feature_Servicing_AddDisableAiaFlag__private_IsEnabledDeviceUsageNoInline
0x1400dfcb1  test    eax, eax
0x1400dfcb3  setnz   cs:UxKirAddDisableAiaFlag
0x1400dfcba  call    Feature_RefactorIoctls__private_IsEnabledDeviceUsageNoInline
0x1400dfcbf  test    eax, eax
0x1400dfcc1  setnz   cs:UxKirRefactorIoctls
0x1400dfcc8  call    Feature_MsQuic_2_5__private_IsEnabledDeviceUsageNoInline
0x1400dfccd  test    eax, eax
0x1400dfccf  setnz   cs:UxKirMsQuic_2_5
0x1400dfcd6  call    Feature_HttpBugFix26Q1__private_IsEnabledDeviceUsageNoInline
0x1400dfcdb  test    eax, eax
0x1400dfcdd  setnz   cs:UxKirHttpBugFix26Q1
0x1400dfce4  mov     cs:UxKirHttpReadingTrailersFromUm, r12b
0x1400dfceb  mov     cs:UxKirWritingAndReadingUm, r12b
0x1400dfcf2  mov     cs:UxKirWritingAndReadingUmCertList, r12b
0x1400dfcf9  call    Feature_HttpsysHKERangeRequestH2StatusCode__private_IsEnabledDeviceUsageNoInline
0x1400dfcfe  test    eax, eax
0x1400dfd00  setnz   cs:UxKirHKERangeRequestH2StatusCode
0x1400dfd07  call    Feature_HttpTlsHandshakePerfCounter__private_IsEnabledDeviceUsageNoInline
0x1400dfd0c  test    eax, eax
0x1400dfd0e  setnz   cs:UxKirHttpTlsHandshakePerfCounter
0x1400dfd15  call    Feature_NewUMAHttpSys__private_IsEnabledDeviceUsageNoInline
0x1400dfd1a  test    eax, eax
0x1400dfd1c  setnz   cs:UxKirNewUma
0x1400dfd23  call    Feature_HttpBugFix26Q2__private_IsEnabledDeviceUsageNoInline
0x1400dfd28  test    eax, eax
0x1400dfd2a  setnz   cs:UxKirHttpBugFix26Q2
0x1400dfd31  mov     cs:UxKirQuicParseLengthCheck, r12b
0x1400dfd38  call    Feature_HttpBugFix2605__private_IsEnabledDeviceUsageNoInline
0x1400dfd3d  test    eax, eax
0x1400dfd3f  setnz   cs:UxKirHttpBugFix2605
0x1400dfd46  lea     r14d, [rsi+2]
0x1400dfd4a  mov     ebx, 419h
0x1400dfd4f  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfd56  lea     r15, WPP_8e1ba98d90cc3fed8729b1cab26b305e_Traceguids
0x1400dfd5d  jz      short loc_1400DFD74
0x1400dfd5f  movzx   r9d, cs:UxKirHttpBugFix25Q1
0x1400dfd67  lea     edx, [rsi+0Ah]
0x1400dfd6a  mov     ecx, ebx
0x1400dfd6c  mov     r8, r15
0x1400dfd6f  call    WPP_SF_d
0x1400dfd74  cmp     cs:UxKirDtHttp2IsbLimit, sil
0x1400dfd7b  jz      short loc_1400DFD95
0x1400dfd7d  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfd84  jz      short loc_1400DFD95
0x1400dfd86  mov     edx, 0Bh
0x1400dfd8b  mov     ecx, ebx
0x1400dfd8d  mov     r8, r15
0x1400dfd90  call    WPP_SF_
0x1400dfd95  cmp     cs:UxKirDtHttpFastForwardHttp11Client, sil
0x1400dfd9c  jz      short loc_1400DFDB6
0x1400dfd9e  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfda5  jz      short loc_1400DFDB6
0x1400dfda7  mov     edx, 0Ch
0x1400dfdac  mov     ecx, ebx
0x1400dfdae  mov     r8, r15
0x1400dfdb1  call    WPP_SF_
0x1400dfdb6  cmp     cs:UxKirHttpBugFix25Q1, sil
0x1400dfdbd  jz      short loc_1400DFDD7
0x1400dfdbf  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfdc6  jz      short loc_1400DFDD7
0x1400dfdc8  mov     edx, 0Dh
0x1400dfdcd  mov     ecx, ebx
0x1400dfdcf  mov     r8, r15
0x1400dfdd2  call    WPP_SF_
0x1400dfdd7  cmp     cs:UxKirBrHttpQuerySocketTtl, sil
0x1400dfdde  jz      short loc_1400DFDF8
0x1400dfde0  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfde7  jz      short loc_1400DFDF8
0x1400dfde9  mov     edx, 0Eh
0x1400dfdee  mov     ecx, ebx
0x1400dfdf0  mov     r8, r15
0x1400dfdf3  call    WPP_SF_
0x1400dfdf8  cmp     cs:UxKirAddDisableAiaFlag, sil
0x1400dfdff  jz      short loc_1400DFE19
0x1400dfe01  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe08  jz      short loc_1400DFE19
0x1400dfe0a  mov     edx, 0Fh
0x1400dfe0f  mov     ecx, ebx
0x1400dfe11  mov     r8, r15
0x1400dfe14  call    WPP_SF_
0x1400dfe19  cmp     cs:UxKirMsQuic_2_5, sil
0x1400dfe20  jz      short loc_1400DFE3A
0x1400dfe22  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe29  jz      short loc_1400DFE3A
0x1400dfe2b  mov     edx, 10h
0x1400dfe30  mov     ecx, ebx
0x1400dfe32  mov     r8, r15
0x1400dfe35  call    WPP_SF_
0x1400dfe3a  cmp     cs:UxKirHKERangeRequestH2StatusCode, sil
0x1400dfe41  jz      short loc_1400DFE5B
0x1400dfe43  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe4a  jz      short loc_1400DFE5B
0x1400dfe4c  mov     edx, 11h
0x1400dfe51  mov     ecx, ebx
0x1400dfe53  mov     r8, r15
0x1400dfe56  call    WPP_SF_
0x1400dfe5b  cmp     cs:UxKirRefactorIoctls, sil
0x1400dfe62  jz      short loc_1400DFE7C
0x1400dfe64  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe6b  jz      short loc_1400DFE7C
0x1400dfe6d  mov     edx, 12h
0x1400dfe72  mov     ecx, ebx
0x1400dfe74  mov     r8, r15
0x1400dfe77  call    WPP_SF_
0x1400dfe7c  cmp     cs:UxKirHttpBugFix26Q1, sil
0x1400dfe83  jz      short loc_1400DFE9D
0x1400dfe85  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe8c  jz      short loc_1400DFE9D
0x1400dfe8e  mov     edx, 13h
0x1400dfe93  mov     ecx, ebx
0x1400dfe95  mov     r8, r15
0x1400dfe98  call    WPP_SF_
0x1400dfe9d  cmp     cs:UxKirHttpReadingTrailersFromUm, sil
0x1400dfea4  jz      short loc_1400DFEBE
0x1400dfea6  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfead  jz      short loc_1400DFEBE
0x1400dfeaf  mov     edx, 14h
0x1400dfeb4  mov     ecx, ebx
0x1400dfeb6  mov     r8, r15
0x1400dfeb9  call    WPP_SF_
0x1400dfebe  cmp     cs:UxKirWritingAndReadingUm, sil
0x1400dfec5  jz      short loc_1400DFEDF
0x1400dfec7  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfece  jz      short loc_1400DFEDF
0x1400dfed0  mov     edx, 15h
0x1400dfed5  mov     ecx, ebx
0x1400dfed7  mov     r8, r15
0x1400dfeda  call    WPP_SF_
0x1400dfedf  cmp     cs:UxKirWritingAndReadingUmCertList, sil
0x1400dfee6  jz      short loc_1400DFF00
0x1400dfee8  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfeef  jz      short loc_1400DFF00
0x1400dfef1  mov     edx, 16h
0x1400dfef6  mov     ecx, ebx
0x1400dfef8  mov     r8, r15
0x1400dfefb  call    WPP_SF_
0x1400dff00  cmp     cs:UxKirHttpTlsHandshakePerfCounter, sil
0x1400dff07  jz      short loc_1400DFF21
0x1400dff09  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dff10  jz      short loc_1400DFF21
0x1400dff12  mov     edx, 17h
0x1400dff17  mov     ecx, ebx
0x1400dff19  mov     r8, r15
0x1400dff1c  call    WPP_SF_
0x1400dff21  cmp     cs:UxKirNewUma, sil
0x1400dff28  jz      short loc_1400DFF42
0x1400dff2a  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dff31  jz      short loc_1400DFF42
0x1400dff33  mov     edx, 18h
0x1400dff38  mov     ecx, ebx
0x1400dff3a  mov     r8, r15
0x1400dff3d  call    WPP_SF_
0x1400dff42  cmp     cs:UxKirHttpBugFix26Q2, sil
0x1400dff49  jz      short loc_1400DFF63
0x1400dff4b  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dff52  jz      short loc_1400DFF63
0x1400dff54  mov     edx, 19h
0x1400dff59  mov     ecx, ebx
0x1400dff5b  mov     r8, r15
0x1400dff5e  call    WPP_SF_
0x1400dff63  cmp     cs:UxKirQuicParseLengthCheck, sil
0x1400dff6a  jz      short loc_1400DFF84
0x1400dff6c  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dff73  jz      short loc_1400DFF84
0x1400dff75  mov     edx, 1Ah
0x1400dff7a  mov     ecx, ebx
0x1400dff7c  mov     r8, r15
0x1400dff7f  call    WPP_SF_
0x1400dff84  cmp     cs:UxKirHttpBugFix2605, sil
0x1400dff8b  jz      short loc_1400DFFA5
0x1400dff8d  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dff94  jz      short loc_1400DFFA5
0x1400dff96  mov     edx, 1Bh
0x1400dff9b  mov     ecx, ebx
0x1400dff9d  mov     r8, r15
0x1400dffa0  call    WPP_SF_
0x1400dffa5  mov     ecx, 0FFFFh; GroupNumber
0x1400dffaa  mov     cs:UxNumberOfProcessors, esi
0x1400dffb0  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400dffb7  nop     dword ptr [rax+rax+00h]
0x1400dffbc  mov     cs:UxMaximumNumberOfProcessors, eax
0x1400dffc2  call    cs:__imp_KeQueryHighestNodeNumber
0x1400dffc9  nop     dword ptr [rax+rax+00h]
0x1400dffce  add     ax, r12w
0x1400dffd2  lea     rcx, UxTotalPhysicalMemMB
0x1400dffd9  mov     cs:UxNumberOfNodes, ax
0x1400dffe0  call    UxGetPhysicalMemorySize
0x1400dffe5  mov     ebx, eax
0x1400dffe7  test    eax, eax
0x1400dffe9  js      loc_1400E0369
0x1400dffef  lea     rdx, UxLowNonPagedPoolEvent
0x1400dfff6  lea     rcx, aKernelobjectsL_0; "\\KernelObjects\\LowNonPagedPoolConditi"...
0x1400dfffd  call    UxOpenNamedEvent
0x1400e0002  mov     ebx, eax
0x1400e0004  test    eax, eax
0x1400e0006  js      loc_1400E0369
0x1400e000c  lea     rdx, UxHighNonPagedPoolEvent
0x1400e0013  lea     rcx, aKernelobjectsH; "\\KernelObjects\\HighNonPagedPoolCondit"...
0x1400e001a  call    UxOpenNamedEvent
0x1400e001f  mov     ebx, eax
0x1400e0021  test    eax, eax
0x1400e0023  js      loc_1400E0369
0x1400e0029  lea     rdx, UxLowMemoryEvent
0x1400e0030  lea     rcx, aKernelobjectsL; "\\KernelObjects\\LowMemoryCondition"
0x1400e0037  call    UxOpenNamedEvent
0x1400e003c  mov     ebx, eax
0x1400e003e  test    eax, eax
0x1400e0040  js      loc_1400E0369
0x1400e0046  lea     rcx, [rbp+100h+VersionInformation]; lpVersionInformation
0x1400e004a  mov     [rbp+100h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1400e0051  call    cs:__imp_RtlGetVersion
0x1400e0058  nop     dword ptr [rax+rax+00h]
0x1400e005d  mov     ebx, eax
0x1400e005f  test    eax, eax
0x1400e0061  js      loc_1400E0369
0x1400e0067  mov     al, [rbp+100h+var_46]
0x1400e006d  sub     al, r14b
0x1400e0070  cmp     al, r12b
0x1400e0073  setbe   cs:UxServerSystem
0x1400e007a  call    cs:__imp_IoGetCurrentProcess
0x1400e0081  nop     dword ptr [rax+rax+00h]
0x1400e0086  mov     cs:UxSystemProcess, rax
0x1400e008d  call    HttpCmnInitializeStaticHttpCharsTable
0x1400e0092  lea     rax, [rsp+200h+var_1A0]
0x1400e0097  mov     [rsp+200h+ObjectAttributes.Length], 30h ; '0'
0x1400e009f  xorps   xmm0, xmm0
0x1400e00a2  mov     [rbp+100h+ObjectAttributes.ObjectName], rax
0x1400e00a6  lea     r8, [rsp+200h+ObjectAttributes]; ObjectAttributes
0x1400e00ab  mov     [rsp+200h+ObjectAttributes.RootDirectory], rsi
0x1400e00b0  mov     edx, 20019h; DesiredAccess
0x1400e00b5  mov     [rbp+100h+ObjectAttributes.Attributes], 240h
0x1400e00bc  lea     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x1400e00c1  movdqu  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e00c6  call    cs:__imp_ZwOpenKey
0x1400e00cd  nop     dword ptr [rax+rax+00h]
0x1400e00d2  mov     ebx, eax
0x1400e00d4  test    eax, eax
0x1400e00d6  jns     short loc_1400E00E4
0x1400e00d8  mov     rcx, rsi
0x1400e00db  mov     ebx, esi
0x1400e00dd  mov     [rsp+200h+KeyHandle], rcx
0x1400e00e2  jmp     short loc_1400E00E9
0x1400e00e4  mov     rcx, [rsp+200h+KeyHandle]
0x1400e00e9  lea     r9, UxCompactMode
0x1400e00f0  xor     r8d, r8d
0x1400e00f3  lea     rdx, aCompactmode; "CompactMode"
0x1400e00fa  call    UxReadBooleanSetting
0x1400e00ff  cmp     cs:UxKirHttpBugFix25Q1, sil
0x1400e0106  jz      short loc_1400E0123
0x1400e0108  mov     rcx, [rsp+200h+KeyHandle]
0x1400e010d  lea     r9, UxEnableIrqlEnforcement
  ... truncated ...
```
