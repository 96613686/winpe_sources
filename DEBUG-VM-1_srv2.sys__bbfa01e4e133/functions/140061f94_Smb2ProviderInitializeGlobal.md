# Smb2ProviderInitializeGlobal

- ea: `0x140061f94`
- end: `0x140062b4e`
- name: `Smb2ProviderInitializeGlobal`
- size: `3002`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14005f538`

## callees

- `0x140001008`
- `0x14001a5e8`
- `0x14001c768`
- `0x14001f384`
- `0x14001f4d4`
- `0x14001f934`
- `0x14001ffec`
- `0x14002019c`
- `0x1400224b8`
- `0x1400253b4`
- `0x140038490`
- `0x140059250`
- `0x140059d54`
- `0x140059fec`
- `0x14005a204`
- `0x140061bcc`
- `0x140061f94`
- `0x140077c0c`
- `0x140094fec`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14006204d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006214e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006204d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006214e`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006200b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006201e`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006200b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006201e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006210f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140062137`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006210f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140062137`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140062542`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140062542`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140062625`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140062625`
- `srvnet!SrvLibGetBinary` at `0x140062257`
- `srvnet!SrvLibGetBinary` at `0x140062257`
- `srvnet!SrvLibCreateCredentialHandle` at `0x140062167`
- `srvnet!SrvLibCreateCredentialHandle` at `0x140062167`
- `srvnet!SmbCryptoKeyedHashInitialize` at `0x1400622c3`
- `srvnet!SmbCryptoKeyedHashInitialize` at `0x1400622c3`
- `srvnet!SrvLibS4U2SelfInitialize` at `0x140062393`
- `srvnet!SrvLibS4U2SelfInitialize` at `0x140062393`
- `srvnet!SrvLibGetDWord` at `0x1400623e0`
- `srvnet!SrvLibGetDWord` at `0x140062414`
- `srvnet!SrvLibGetDWord` at `0x140062482`
- `srvnet!SrvLibGetDWord` at `0x1400624b5`
- `srvnet!SrvLibGetDWord` at `0x1400624de`
- `srvnet!SrvLibGetDWord` at `0x14006251b`
- `srvnet!SrvLibGetDWord` at `0x140062644`
- `srvnet!SrvLibGetDWord` at `0x1400626d4`
- `srvnet!SrvLibGetDWord` at `0x14006275b`
- `srvnet!SrvLibGetDWord` at `0x1400623e0`
- `srvnet!SrvLibGetDWord` at `0x140062414`
- `srvnet!SrvLibGetDWord` at `0x140062482`
- `srvnet!SrvLibGetDWord` at `0x1400624b5`
- `srvnet!SrvLibGetDWord` at `0x1400624de`
- `srvnet!SrvLibGetDWord` at `0x14006251b`
- `srvnet!SrvLibGetDWord` at `0x140062644`
- `srvnet!SrvLibGetDWord` at `0x1400626d4`
- `srvnet!SrvLibGetDWord` at `0x14006275b`
- `srvnet!SmbCryptoReadCipherSuiteOrderPolicySetting` at `0x140062563`
- `srvnet!SmbCryptoReadCipherSuiteOrderPolicySetting` at `0x1400625c7`
- `srvnet!SmbCryptoReadCipherSuiteOrderPolicySetting` at `0x140062563`
- `srvnet!SmbCryptoReadCipherSuiteOrderPolicySetting` at `0x1400625c7`
- `srvnet!SmbCryptoReadSigningAlgorithmOrderPolicySetting` at `0x140062674`
- `srvnet!SmbCryptoReadSigningAlgorithmOrderPolicySetting` at `0x140062674`
- `srvnet!SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting` at `0x140062700`
- `srvnet!SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting` at `0x140062700`
- `srvnet!SrvLibKeyExists` at `0x1400627df`
- `srvnet!SrvLibKeyExists` at `0x1400627df`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x14006281d`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x14006281d`
- `ksecdd!BCryptGenRandom` at `0x140062274`
- `ksecdd!BCryptGenRandom` at `0x140062274`

## string_xrefs

- `0x140062233`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x1400623d9`: `MaxThreadsPerNumaNode`
- `0x1400624d7`: `MaxReadWriteSizeForWSK`
- `0x14006255c`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`
- `0x14006263d`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`
- `0x14006266d`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`
- `0x1400626cd`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`
- `0x140062754`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`
- `0x14006274d`: `HonorCompressionAlgorithmSuiteOrder`
- `0x1400627d8`: `\Registry\Machine\System\CurrentControlSet\Services\ResumeKeyFilter`

## pseudocode

```c
__int64 Smb2ProviderInitializeGlobal()
{
  NTSTATUS SigningHashObjectLookasideList; // ebx
  int v1; // eax
  int v2; // eax
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  int v5; // eax
  int v6; // eax
  int v7; // ecx
  int CipherSuiteOrderPolicySetting; // eax
  unsigned int v9; // ebx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  unsigned int SigningAlgorithmOrderPolicySetting; // eax
  unsigned int CompressionAlgorithmSuiteOrderPolicySetting; // eax
  __int64 v15; // r8
  char v16; // r8
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  char v19; // [rsp+54h] [rbp-ACh] BYREF
  char v20; // [rsp+55h] [rbp-ABh] BYREF
  char v21; // [rsp+56h] [rbp-AAh] BYREF
  char v22; // [rsp+57h] [rbp-A9h] BYREF
  char v23; // [rsp+58h] [rbp-A8h] BYREF
  char v24; // [rsp+59h] [rbp-A7h] BYREF
  char v25; // [rsp+5Ah] [rbp-A6h] BYREF
  char v26; // [rsp+5Bh] [rbp-A5h] BYREF
  char v27; // [rsp+5Ch] [rbp-A4h] BYREF
  char v28; // [rsp+5Dh] [rbp-A3h] BYREF
  bool v29; // [rsp+5Eh] [rbp-A2h] BYREF
  char v30; // [rsp+5Fh] [rbp-A1h] BYREF
  char v31; // [rsp+60h] [rbp-A0h] BYREF
  char v32; // [rsp+61h] [rbp-9Fh] BYREF
  char v33; // [rsp+62h] [rbp-9Eh] BYREF
  int v34; // [rsp+64h] [rbp-9Ch] BYREF
  int v35; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+6Ch] [rbp-94h] BYREF
  int v37; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+74h] [rbp-8Ch] BYREF
  int v39; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+7Ch] [rbp-84h] BYREF
  int v41; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v43[32]; // [rsp+A0h] [rbp-60h] BYREF
  char *v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+C8h] [rbp-38h]
  char *v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h]
  int *v48; // [rsp+E0h] [rbp-20h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  char *v50; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]
  char *v52; // [rsp+100h] [rbp+0h]
  __int64 v53; // [rsp+108h] [rbp+8h]
  char *v54; // [rsp+110h] [rbp+10h]
  __int64 v55; // [rsp+118h] [rbp+18h]
  char *v56; // [rsp+120h] [rbp+20h]
  __int64 v57; // [rsp+128h] [rbp+28h]
  char *v58; // [rsp+130h] [rbp+30h]
  __int64 v59; // [rsp+138h] [rbp+38h]
  char *v60; // [rsp+140h] [rbp+40h]
  __int64 v61; // [rsp+148h] [rbp+48h]
  char *v62; // [rsp+150h] [rbp+50h]
  __int64 v63; // [rsp+158h] [rbp+58h]
  char *v64; // [rsp+160h] [rbp+60h]
  __int64 v65; // [rsp+168h] [rbp+68h]
  bool *v66; // [rsp+170h] [rbp+70h]
  __int64 v67; // [rsp+178h] [rbp+78h]
  char *v68; // [rsp+180h] [rbp+80h]
  __int64 v69; // [rsp+188h] [rbp+88h]
  int *v70; // [rsp+190h] [rbp+90h]
  __int64 v71; // [rsp+198h] [rbp+98h]
  char *v72; // [rsp+1A0h] [rbp+A0h]
  __int64 v73; // [rsp+1A8h] [rbp+A8h]
  int *v74; // [rsp+1B0h] [rbp+B0h]
  __int64 v75; // [rsp+1B8h] [rbp+B8h]
  char *v76; // [rsp+1C0h] [rbp+C0h]
  __int64 v77; // [rsp+1C8h] [rbp+C8h]
  int *v78; // [rsp+1D0h] [rbp+D0h]
  __int64 v79; // [rsp+1D8h] [rbp+D8h]
  int *v80; // [rsp+1E0h] [rbp+E0h]
  __int64 v81; // [rsp+1E8h] [rbp+E8h]
  int *v82; // [rsp+1F0h] [rbp+F0h]
  __int64 v83; // [rsp+1F8h] [rbp+F8h]
  int *v84; // [rsp+200h] [rbp+100h]
  __int64 v85; // [rsp+208h] [rbp+108h]
  char *v86; // [rsp+210h] [rbp+110h]
  __int64 v87; // [rsp+218h] [rbp+118h]
  int *v88; // [rsp+220h] [rbp+120h]
  __int64 v89; // [rsp+228h] [rbp+128h]

  DestinationString = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids);
  }
  ExInitializeResourceLite(&Smb2NameLock);
  ExInitializeResourceLite(&Smb2ExtensibleCredHandleLock);
  Smb2CipherSuiteOrderLock = 0;
  Smb2RequireWindowsHelloForBusinessExceptionListLock = 0;
  Smb2XsInitialized = 0;
  RtlInitUnicodeString(&Smb2XsProtocolName, L"ncalrpc");
  Smb2InitProgress |= 8u;
  Smb2InitializeOplockPackage();
  Smb2InitProgress |= 0x10u;
  Smb2DurableHandleInitialize();
  Smb2InitProgress |= 0x20u;
  Smb2InitializeScavenger();
  Smb2InitProgress |= 1u;
  Smb2InitializeSnapShotScavenger();
  Smb2InitProgress |= 2u;
  SigningHashObjectLookasideList = Smb2InitializeLowMemLeaseBufferCache();
  if ( SigningHashObjectLookasideList < 0 )
    goto LABEL_101;
  Smb2InitProgress |= 4u;
  SigningHashObjectLookasideList = RfsHashTableCreate(
                                     (unsigned int)&Smb2ClientHashTable,
                                     128,
                                     0x7FFFFFFF,
                                     48,
                                     1,
                                     (__int64)Srv2ReferenceConnection,
                                     (__int64)&Smb2ClientEqualKey,
                                     0);
  if ( SigningHashObjectLookasideList < 0 )
    goto LABEL_101;
  qword_14004BEB8 = (__int64)&Smb2ClientPendingList;
  Smb2ClientPendingList = (__int64)&Smb2ClientPendingList;
  KeInitializeSpinLock(&Smb2ClientPendingListLock);
  qword_14004BD98 = (__int64)&Smb2ObjectContextList;
  Smb2ObjectContextList = (__int64)&Smb2ObjectContextList;
  KeInitializeSpinLock(&Smb2ObjectContextListLock);
  RtlInitUnicodeString(&DestinationString, L"Negotiate");
  SigningHashObjectLookasideList = SrvLibCreateCredentialHandle(&DestinationString, 0, &Smb2ExtensibleCredentialHandle);
  if ( SigningHashObjectLookasideList < 0 )
    goto LABEL_101;
  Smb2InitProgress |= 0x40u;
  v1 = RfsHashTableCreate(
         (unsigned int)&Smb2AppInstanceFileTableForNonCA,
         128,
         -1,
         848,
         0,
         (__int64)Smb2ReferenceFile,
         (__int64)Smb2AppInstanceFileEqualKey,
         (__int64)Smb2AppInstanceFileMatchEntry);
  if ( !Smb2AppInstanceFileTableForNonCA )
    goto LABEL_100;
  if ( v1 < 0 )
    goto LABEL_100;
  v2 = RfsHashTableCreate(
         (unsigned int)&Smb2AppInstanceFileTableForCA,
         128,
         -1,
         848,
         0,
         (__int64)Smb2ReferenceFile,
         (__int64)Smb2AppInstanceFileEqualKey,
         0);
  if ( !Smb2AppInstanceFileTableForCA || v2 < 0 )
    goto LABEL_100;
  v34 = 16;
  Smb2Guid = 0;
  SrvLibGetBinary(
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    L"Guid",
    &Smb2Guid,
    &v34);
  SigningHashObjectLookasideList = BCryptGenRandom(0, &Smb2SaltBuffer, 0x20u, 2u);
  if ( SigningHashObjectLookasideList < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_101;
    }
    v4 = 14;
    goto LABEL_17;
  }
  SigningHashObjectLookasideList = SmbCryptoKeyedHashInitialize();
  if ( SigningHashObjectLookasideList < 0 )
    goto LABEL_101;
  byte_140058001 |= 1u;
  SigningHashObjectLookasideList = Smb2CreateSigningHashObjectLookasideList();
  if ( SigningHashObjectLookasideList < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_101;
    }
    v4 = 15;
LABEL_17:
    WPP_SF_d(
      v3->AttachedDevice,
      v4,
      &WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids,
      (unsigned int)SigningHashObjectLookasideList);
    goto LABEL_101;
  }
  byte_140058001 |= 2u;
  SigningHashObjectLookasideList = Smb2InitVolumeIDCache();
  if ( SigningHashObjectLookasideList < 0 )
  {
LABEL_101:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        &WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids,
        (unsigned int)SigningHashObjectLookasideList);
    }
    Smb2ProviderCleanupGlobal();
    return (unsigned int)SigningHashObjectLookasideList;
  }
  byte_140058001 |= 4u;
  v5 = RfsHashTableCreate(
         (unsigned int)&Smb2NetnameTable,
         32,
         -1,
         0,
         1,
         (__int64)Smb2ReferenceNetname,
         (__int64)&Smb2NetnameEqualKey,
         0);
  if ( !Smb2NetnameTable || v5 < 0 )
  {
LABEL_100:
    SigningHashObjectLookasideList = -1073741670;
    goto LABEL_101;
  }
  v6 = SrvLibS4U2SelfInitialize("Smb2Srv", "Smb2Srv", &Smb2S4U2SelfContext);
  if ( v6 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids, (unsigned int)v6);
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"MaxThreadsPerNumaNode",
              &v18) >= 0
    && (unsigned int)(v18 - 1) <= 0xFFFE )
  {
    Srv2MaxThreadsPerNumaNode = v18;
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"smb2creditsmax",
              &v18) >= 0
    && v18 )
  {
    Smb2AuthenticatedConnectionMaxMidWindowSize = v18;
  }
  else
  {
    v7 = 2048;
    if ( (unsigned __int8)(byte_1400583AA - 2) <= 1u )
      v7 = 0x2000;
    Smb2AuthenticatedConnectionMaxMidWindowSize = v7;
  }
  Smb2AsyncCredits = (unsigned __int8)(byte_1400583AA - 2) <= 1u ? 512 : 64;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"asynchronouscredits",
              &v18) >= 0
    && v18 )
  {
    Smb2AsyncCredits = v18;
  }
  Smb2ABELevel = 0;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"ABELevel",
              &v18) >= 0 )
    Smb2ABELevel = v18;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"MaxReadWriteSizeForWSK",
              &v18) >= 0
    && (unsigned int)(v18 - 1) <= 0x7FFFFF )
  {
    Smb2MaxLargeMtuReadWriteSize = v18;
  }
  Smb2OplockBreakTimeoutInSec = 35;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"OplockBreakTimeout",
              &v18) >= 0
    && v18 )
  {
    Smb2OplockBreakTimeoutInSec = v18;
  }
  ExAcquirePushLockExclusiveEx(&Smb2CipherSuiteOrderLock, 0);
  CipherSuiteOrderPolicySetting = SmbCryptoReadCipherSuiteOrderPolicySetting(
                                    L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
                                    &Smb2CipherOrder,
                                    &Smb2CipherOrderCeLength);
  v9 = CipherSuiteOrderPolicySetting;
  if ( CipherSuiteOrderPolicySetting < 0 )
  {
    if ( CipherSuiteOrderPolicySetting == -1073741772 )
    {
      v12 = SmbCryptoReadCipherSuiteOrderPolicySetting(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              &Smb2CipherOrder,
              &Smb2CipherOrderCeLength);
      v9 = v12;
      if ( v12 < 0 )
      {
        if ( v12 == -1073739509 && byte_14004C339 < 0 )
          McTemplateK0z_EtwWriteTransfer();
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v11 = 18;
          goto LABEL_69;
        }
      }
    }
    else
    {
      if ( CipherSuiteOrderPolicySetting == -1073739509 && byte_14004C339 < 0 )
        McTemplateK0z_EtwWriteTransfer();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v11 = 17;
LABEL_69:
        WPP_SF_d(v10->AttachedDevice, v11, &WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids, v9);
      }
    }
  }
  ExReleasePushLockExclusiveEx(&Smb2CipherSuiteOrderLock, 0);
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"HonorCipherSuiteOrder",
              &v18) >= 0 )
    Smb2HonorCipherOrder = v18 != 0;
  SigningAlgorithmOrderPolicySetting = SmbCryptoReadSigningAlgorithmOrderPolicySetting(
                                         L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
                                         &Smb2SigningAlgOrder,
                                         &Smb2SigningAlgOrderCeLength);
  if ( (int)(SigningAlgorithmOrderPolicySetting + 0x80000000) >= 0
    && SigningAlgorithmOrderPolicySetting != -1073741772
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      &WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids,
      SigningAlgorithmOrderPolicySetting);
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"HonorSigningAlgorithmSuiteOrder",
              &v18) >= 0 )
    Smb2HonorSigningAlgOrder = v18 != 0;
  CompressionAlgorithmSuiteOrderPolicySetting = SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting(
                                                  L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                                                  &Smb2CompressionAlgOrder,
                                                  &Smb2CompressionAlgOrderCeLength);
  if ( ((CompressionAlgorithmSuiteOrderPolicySetting + 0x80000000) & 0x80000000) == 0
    && CompressionAlgorithmSuiteOrderPolicySetting != -1073741772
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      &WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids,
      CompressionAlgorithmSuiteOrderPolicySetting);
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"HonorCompressionAlgorithmSuiteOrder",
              &v18) >= 0 )
    Smb2HonorCompressionAlgOrder = v18 != 0;
  Smb2RefreshRegistryValue();
  SigningHashObjectLookasideList = Smb2DfsInitialize();
  if ( SigningHashObjectLookasideList < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        &WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids,
        (unsigned int)SigningHashObjectLookasideList);
    }
    goto LABEL_101;
  }
  byte_140058001 |= 8u;
  Smb2NamedPipeInitialize();
  byte_140058001 |= 0x10u;
  Smb2IsRkfInstalled = SrvLibKeyExists(L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\ResumeKeyFilter");
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, &WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids);
  }
  LOBYTE(v15) = SrvAdminAllowAnonymousAccess();
  if ( (unsigned int)dword_1400583B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400583B0, 0x400000000000LL, v15) )
  {
    v19 = Smb2Enabled;
    v44 = &v19;
    v29 = Smb2CompressionDisabled == 0;
    v20 = Smb2SigningRequired;
    v46 = &v20;
    v34 = Smb2KeepAliveTimeInMin;
    v48 = &v34;
    v21 = Smb2TreatHostAsStableStorage;
    v50 = &v21;
    v22 = Smb2LeasingEnabled;
    v52 = &v22;
    v23 = Smb2DirLeasingEnabled;
    v54 = &v23;
    v24 = Smb2DirHandleLeasingEnabled;
    v56 = &v24;
    v25 = Smb2MultiChannelEnabled;
    v58 = &v25;
    v26 = Smb2EncryptData;
    v60 = &v26;
    v27 = Smb2NotificationsEnabled;
    v62 = &v27;
    v28 = Smb2EncryptionEnabled;
    v64 = &v28;
    v66 = &v29;
    v30 = Smb2AllowUnencryptedAccess;
    v68 = &v30;
    v70 = &v35;
    v31 = Smb2SofsAsymmetryMode;
    v72 = &v31;
    v36 = Smb2EnableS4U2SelfForClaims;
    v74 = &v36;
    v45 = 1;
    v47 = 1;
    v49 = 4;
    v51 = 1;
    v53 = 1;
    v55 = 1;
    v57 = 1;
    v59 = 1;
    v61 = 1;
    v63 = 1;
    v65 = 1;
    v67 = 1;
    v69 = 1;
    v35 = -1;
    v71 = 4;
    v73 = 1;
    v75 = 4;
    v32 = v16;
    v76 = &v32;
    v37 = Smb2AuthenticatedConnectionMaxMidWindowSize;
    v77 = 1;
    v78 = &v37;
    v38 = Smb2ABELevel;
    v80 = &v38;
    v39 = Smb2MaxLargeMtuReadWriteSize;
    v82 = &v39;
    v40 = Smb2OplockBreakTimeoutInSec;
    v84 = &v40;
    v33 = Smb2IsRkfInstalled;
    v86 = &v33;
    v41 = Smb2SpnValidationPolicy;
    v88 = &v41;
    v79 = 4;
    v81 = 4;
    v83 = 4;
    v85 = 4;
    v87 = 1;
    v89 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_1400583B0, &unk_140042FBE, 0, 0, 25, v43);
  }
  return (unsigned int)SigningHashObjectLookasideList;
}

```

## disassembly

```asm
0x140061f94  push    rbp
0x140061f96  push    rbx
0x140061f97  push    rsi
0x140061f98  push    rdi
0x140061f99  push    r12
0x140061f9b  push    r14
0x140061f9d  push    r15
0x140061f9f  lea     rbp, [rsp-140h]
0x140061fa7  sub     rsp, 240h
0x140061fae  mov     rax, cs:__security_cookie
0x140061fb5  xor     rax, rsp
0x140061fb8  mov     [rbp+170h+var_40], rax
0x140061fbf  xorps   xmm0, xmm0
0x140061fc2  xor     edi, edi
0x140061fc4  movups  xmmword ptr [rbp+170h+DestinationString.Length], xmm0
0x140061fc8  mov     [rsp+270h+var_220], edi
0x140061fcc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140061fd3  lea     r14, WPP_GLOBAL_Control
0x140061fda  lea     r15, WPP_d13fb186aff73b3d149fffcdc1f6e131_Traceguids
0x140061fe1  cmp     rcx, r14
0x140061fe4  jz      short loc_140062004
0x140061fe6  test    dword ptr [rcx+2Ch], 4000h
0x140061fed  jz      short loc_140062004
0x140061fef  cmp     byte ptr [rcx+29h], 2
0x140061ff3  jb      short loc_140062004
0x140061ff5  mov     rcx, [rcx+18h]
0x140061ff9  lea     edx, [rdi+0Dh]
0x140061ffc  mov     r8, r15
0x140061fff  call    WPP_SF_
0x140062004  lea     rcx, Smb2NameLock; Resource
0x14006200b  call    cs:__imp_ExInitializeResourceLite
0x140062012  nop     dword ptr [rax+rax+00h]
0x140062017  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x14006201e  call    cs:__imp_ExInitializeResourceLite
0x140062025  nop     dword ptr [rax+rax+00h]
0x14006202a  lea     rdx, aNcalrpc; "ncalrpc"
0x140062031  mov     cs:Smb2CipherSuiteOrderLock, rdi
0x140062038  lea     rcx, Smb2XsProtocolName; DestinationString
0x14006203f  mov     cs:Smb2RequireWindowsHelloForBusinessExceptionListLock, rdi
0x140062046  mov     cs:Smb2XsInitialized, dil
0x14006204d  call    cs:__imp_RtlInitUnicodeString
0x140062054  nop     dword ptr [rax+rax+00h]
0x140062059  or      cs:Smb2InitProgress, 8
0x140062060  call    Smb2InitializeOplockPackage
0x140062065  or      cs:Smb2InitProgress, 10h
0x14006206c  call    Smb2DurableHandleInitialize
0x140062071  or      cs:Smb2InitProgress, 20h
0x140062078  call    Smb2InitializeScavenger
0x14006207d  mov     esi, 1
0x140062082  or      cs:Smb2InitProgress, sil
0x140062089  call    Smb2InitializeSnapShotScavenger
0x14006208e  or      cs:Smb2InitProgress, 2
0x140062095  call    Smb2InitializeLowMemLeaseBufferCache
0x14006209a  mov     ebx, eax
0x14006209c  test    eax, eax
0x14006209e  js      loc_140062AF6
0x1400620a4  or      cs:Smb2InitProgress, 4
0x1400620ab  lea     rax, Smb2ClientEqualKey
0x1400620b2  mov     [rsp+270h+var_238], rdi
0x1400620b7  lea     r12d, [rsi+7Fh]
0x1400620bb  mov     [rsp+270h+var_240], rax
0x1400620c0  lea     r9d, [rsi+2Fh]
0x1400620c4  lea     rax, Srv2ReferenceConnection
0x1400620cb  mov     r8d, 7FFFFFFFh
0x1400620d1  mov     [rsp+270h+var_248], rax
0x1400620d6  lea     rcx, Smb2ClientHashTable
0x1400620dd  mov     edx, r12d
0x1400620e0  mov     [rsp+270h+var_250], esi
0x1400620e4  call    RfsHashTableCreate
0x1400620e9  mov     ebx, eax
0x1400620eb  test    eax, eax
0x1400620ed  js      loc_140062AF6
0x1400620f3  lea     rax, Smb2ClientPendingList
0x1400620fa  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x140062101  mov     cs:qword_14004BEB8, rax
0x140062108  mov     cs:Smb2ClientPendingList, rax
0x14006210f  call    cs:__imp_KeInitializeSpinLock
0x140062116  nop     dword ptr [rax+rax+00h]
0x14006211b  lea     rax, Smb2ObjectContextList
0x140062122  lea     rcx, Smb2ObjectContextListLock; SpinLock
0x140062129  mov     cs:qword_14004BD98, rax
0x140062130  mov     cs:Smb2ObjectContextList, rax
0x140062137  call    cs:__imp_KeInitializeSpinLock
0x14006213e  nop     dword ptr [rax+rax+00h]
0x140062143  lea     rdx, aNegotiate; "Negotiate"
0x14006214a  lea     rcx, [rbp+170h+DestinationString]; DestinationString
0x14006214e  call    cs:__imp_RtlInitUnicodeString
0x140062155  nop     dword ptr [rax+rax+00h]
0x14006215a  lea     r8, Smb2ExtensibleCredentialHandle
0x140062161  xor     edx, edx
0x140062163  lea     rcx, [rbp+170h+DestinationString]
0x140062167  call    cs:__imp_SrvLibCreateCredentialHandle
0x14006216e  nop     dword ptr [rax+rax+00h]
0x140062173  mov     ebx, eax
0x140062175  test    eax, eax
0x140062177  js      loc_140062AF6
0x14006217d  or      cs:Smb2InitProgress, 40h
0x140062184  lea     rax, Smb2AppInstanceFileMatchEntry
0x14006218b  mov     [rsp+270h+var_238], rax
0x140062190  lea     rcx, Smb2AppInstanceFileTableForNonCA
0x140062197  lea     rax, Smb2AppInstanceFileEqualKey
0x14006219e  mov     ebx, 350h
0x1400621a3  mov     [rsp+270h+var_240], rax
0x1400621a8  mov     r9d, ebx
0x1400621ab  lea     rax, Smb2ReferenceFile
0x1400621b2  or      r8d, 0FFFFFFFFh
0x1400621b6  mov     [rsp+270h+var_248], rax
0x1400621bb  mov     edx, r12d
0x1400621be  mov     [rsp+270h+var_250], edi
0x1400621c2  call    RfsHashTableCreate
0x1400621c7  cmp     cs:Smb2AppInstanceFileTableForNonCA, rdi
0x1400621ce  jz      loc_140062AF1
0x1400621d4  test    eax, eax
0x1400621d6  js      loc_140062AF1
0x1400621dc  mov     [rsp+270h+var_238], rdi
0x1400621e1  lea     rax, Smb2AppInstanceFileEqualKey
0x1400621e8  mov     [rsp+270h+var_240], rax
0x1400621ed  lea     rcx, Smb2AppInstanceFileTableForCA
0x1400621f4  lea     rax, Smb2ReferenceFile
0x1400621fb  mov     r9d, ebx
0x1400621fe  mov     [rsp+270h+var_248], rax
0x140062203  or      r8d, 0FFFFFFFFh
0x140062207  mov     edx, r12d
0x14006220a  mov     [rsp+270h+var_250], edi
0x14006220e  call    RfsHashTableCreate
0x140062213  cmp     cs:Smb2AppInstanceFileTableForCA, rdi
0x14006221a  jz      loc_140062AF1
0x140062220  test    eax, eax
0x140062222  js      loc_140062AF1
0x140062228  xorps   xmm0, xmm0
0x14006222b  mov     [rsp+270h+var_20C], 10h
0x140062233  lea     r12, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x14006223a  mov     rcx, r12
0x14006223d  lea     r9, [rsp+270h+var_20C]
0x140062242  lea     r8, Smb2Guid
0x140062249  lea     rdx, aGuid; "Guid"
0x140062250  movups  cs:Smb2Guid, xmm0
0x140062257  call    cs:__imp_SrvLibGetBinary
0x14006225e  nop     dword ptr [rax+rax+00h]
0x140062263  lea     r9d, [rsi+1]; dwFlags
0x140062267  xor     ecx, ecx; hAlgorithm
0x140062269  lea     r8d, [rsi+1Fh]; cbBuffer
0x14006226d  lea     rdx, Smb2SaltBuffer; pbBuffer
0x140062274  call    cs:__imp_BCryptGenRandom
0x14006227b  nop     dword ptr [rax+rax+00h]
0x140062280  mov     ebx, eax
0x140062282  test    eax, eax
0x140062284  jns     short loc_1400622C3
0x140062286  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006228d  cmp     rcx, r14
0x140062290  jz      loc_140062AF6
0x140062296  mov     eax, [rcx+2Ch]
0x140062299  test    sil, al
0x14006229c  jz      loc_140062AF6
0x1400622a2  cmp     [rcx+29h], sil
0x1400622a6  jb      loc_140062AF6
0x1400622ac  lea     edx, [rsi+0Dh]
0x1400622af  mov     rcx, [rcx+18h]
0x1400622b3  mov     r9d, ebx
0x1400622b6  mov     r8, r15
0x1400622b9  call    WPP_SF_d
0x1400622be  jmp     loc_140062AF6
0x1400622c3  call    cs:__imp_SmbCryptoKeyedHashInitialize
0x1400622ca  nop     dword ptr [rax+rax+00h]
0x1400622cf  mov     ebx, eax
0x1400622d1  test    eax, eax
0x1400622d3  js      loc_140062AF6
0x1400622d9  or      cs:byte_140058001, sil
0x1400622e0  call    Smb2CreateSigningHashObjectLookasideList
0x1400622e5  mov     ebx, eax
0x1400622e7  test    eax, eax
0x1400622e9  jns     short loc_140062318
0x1400622eb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400622f2  cmp     rcx, r14
0x1400622f5  jz      loc_140062AF6
0x1400622fb  mov     eax, [rcx+2Ch]
0x1400622fe  test    sil, al
0x140062301  jz      loc_140062AF6
0x140062307  cmp     [rcx+29h], sil
0x14006230b  jb      loc_140062AF6
0x140062311  mov     edx, 0Fh
0x140062316  jmp     short loc_1400622AF
0x140062318  or      cs:byte_140058001, 2
0x14006231f  call    Smb2InitVolumeIDCache
0x140062324  mov     ebx, eax
0x140062326  test    eax, eax
0x140062328  js      loc_140062AF6
0x14006232e  or      cs:byte_140058001, 4
0x140062335  lea     rax, Smb2NetnameEqualKey
0x14006233c  mov     [rsp+270h+var_238], rdi
0x140062341  lea     rcx, Smb2NetnameTable
0x140062348  mov     [rsp+270h+var_240], rax
0x14006234d  xor     r9d, r9d
0x140062350  lea     rax, Smb2ReferenceNetname
0x140062357  or      r8d, 0FFFFFFFFh
0x14006235b  mov     [rsp+270h+var_248], rax
0x140062360  mov     [rsp+270h+var_250], esi
0x140062364  lea     edx, [r9+20h]
0x140062368  call    RfsHashTableCreate
0x14006236d  cmp     cs:Smb2NetnameTable, rdi
0x140062374  jz      loc_140062AF1
0x14006237a  test    eax, eax
0x14006237c  js      loc_140062AF1
0x140062382  lea     rcx, aSmb2srv; "Smb2Srv"
0x140062389  mov     rdx, rcx
0x14006238c  lea     r8, Smb2S4U2SelfContext
0x140062393  call    cs:__imp_SrvLibS4U2SelfInitialize
0x14006239a  nop     dword ptr [rax+rax+00h]
0x14006239f  test    eax, eax
0x1400623a1  jns     short loc_1400623D1
0x1400623a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400623aa  cmp     rcx, r14
0x1400623ad  jz      short loc_1400623D1
0x1400623af  mov     edx, [rcx+2Ch]
0x1400623b2  test    sil, dl
0x1400623b5  jz      short loc_1400623D1
0x1400623b7  cmp     [rcx+29h], sil
0x1400623bb  jb      short loc_1400623D1
0x1400623bd  mov     rcx, [rcx+18h]
0x1400623c1  mov     edx, 10h
0x1400623c6  mov     r9d, eax
0x1400623c9  mov     r8, r15
0x1400623cc  call    WPP_SF_d
0x1400623d1  lea     r8, [rsp+270h+var_220]
0x1400623d6  mov     rcx, r12
0x1400623d9  lea     rdx, aMaxthreadspern; "MaxThreadsPerNumaNode"
0x1400623e0  call    cs:__imp_SrvLibGetDWord
0x1400623e7  nop     dword ptr [rax+rax+00h]
0x1400623ec  test    eax, eax
0x1400623ee  js      short loc_140062405
0x1400623f0  mov     ecx, [rsp+270h+var_220]
0x1400623f4  lea     eax, [rcx-1]
0x1400623f7  cmp     eax, 0FFFEh
0x1400623fc  ja      short loc_140062405
0x1400623fe  mov     cs:Srv2MaxThreadsPerNumaNode, cx
0x140062405  lea     r8, [rsp+270h+var_220]
0x14006240a  mov     rcx, r12
0x14006240d  lea     rdx, aSmb2creditsmax; "smb2creditsmax"
0x140062414  call    cs:__imp_SrvLibGetDWord
0x14006241b  nop     dword ptr [rax+rax+00h]
0x140062420  test    eax, eax
0x140062422  js      short loc_140062434
0x140062424  mov     eax, [rsp+270h+var_220]
0x140062428  test    eax, eax
0x14006242a  jz      short loc_140062434
0x14006242c  mov     cs:Smb2AuthenticatedConnectionMaxMidWindowSize, eax
0x140062432  jmp     short loc_140062452
0x140062434  mov     al, cs:byte_1400583AA
0x14006243a  mov     ecx, 800h
0x14006243f  sub     al, 2
0x140062441  mov     edx, 2000h
0x140062446  cmp     al, sil
0x140062449  cmovbe  ecx, edx
0x14006244c  mov     cs:Smb2AuthenticatedConnectionMaxMidWindowSize, ecx
0x140062452  mov     al, cs:byte_1400583AA
0x140062458  lea     r8, [rsp+270h+var_220]
0x14006245d  sub     al, 2
0x14006245f  lea     rdx, aAsynchronouscr; "asynchronouscredits"
0x140062466  cmp     al, sil
0x140062469  setbe   al
0x14006246c  neg     al
0x14006246e  sbb     ecx, ecx
0x140062470  and     ecx, 1C0h
0x140062476  add     ecx, 40h ; '@'
0x140062479  mov     cs:Smb2AsyncCredits, ecx
0x14006247f  mov     rcx, r12
0x140062482  call    cs:__imp_SrvLibGetDWord
0x140062489  nop     dword ptr [rax+rax+00h]
0x14006248e  test    eax, eax
0x140062490  js      short loc_1400624A0
0x140062492  mov     eax, [rsp+270h+var_220]
0x140062496  test    eax, eax
0x140062498  jz      short loc_1400624A0
0x14006249a  mov     cs:Smb2AsyncCredits, eax
0x1400624a0  lea     r8, [rsp+270h+var_220]
0x1400624a5  mov     cs:Smb2ABELevel, edi
0x1400624ab  lea     rdx, aAbelevel; "ABELevel"
0x1400624b2  mov     rcx, r12
0x1400624b5  call    cs:__imp_SrvLibGetDWord
0x1400624bc  nop     dword ptr [rax+rax+00h]
0x1400624c1  test    eax, eax
0x1400624c3  js      short loc_1400624CF
0x1400624c5  mov     eax, [rsp+270h+var_220]
0x1400624c9  mov     cs:Smb2ABELevel, eax
0x1400624cf  lea     r8, [rsp+270h+var_220]
0x1400624d4  mov     rcx, r12
0x1400624d7  lea     rdx, aMaxreadwritesi; "MaxReadWriteSizeForWSK"
0x1400624de  call    cs:__imp_SrvLibGetDWord
0x1400624e5  nop     dword ptr [rax+rax+00h]
0x1400624ea  test    eax, eax
0x1400624ec  js      short loc_140062502
0x1400624ee  mov     ecx, [rsp+270h+var_220]
0x1400624f2  lea     eax, [rcx-1]
0x1400624f5  cmp     eax, 7FFFFFh
0x1400624fa  ja      short loc_140062502
0x1400624fc  mov     cs:Smb2MaxLargeMtuReadWriteSize, ecx
0x140062502  lea     r8, [rsp+270h+var_220]
0x140062507  mov     cs:Smb2OplockBreakTimeoutInSec, 23h ; '#'
0x140062511  lea     rdx, aOplockbreaktim; "OplockBreakTimeout"
0x140062518  mov     rcx, r12
  ... truncated ...
```
