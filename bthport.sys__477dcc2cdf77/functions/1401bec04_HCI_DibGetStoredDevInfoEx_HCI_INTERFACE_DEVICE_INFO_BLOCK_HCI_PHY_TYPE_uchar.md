# HCI_DibGetStoredDevInfoEx(HCI_INTERFACE *,DEVICE_INFO_BLOCK *,_HCI_PHY_TYPE,uchar *)

- ea: `0x1401bec04`
- end: `0x1401bf729`
- name: `?HCI_DibGetStoredDevInfoEx@@YAJPEAUHCI_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@W4_HCI_PHY_TYPE@@PEAE@Z`
- size: `2853`
- prototype: `int(struct HCI_INTERFACE *, struct DEVICE_INFO_BLOCK *, enum _HCI_PHY_TYPE, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400515b0`

## callees

- `0x140005690`
- `0x14000f27c`
- `0x14000fab4`
- `0x14005f0c0`
- `0x14015ce68`
- `0x140165540`
- `0x140165640`
- `0x1401bec04`
- `0x1401c18d0`
- `0x1401c1c04`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bf6da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bf6da`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401bf6ce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401bf6ce`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401bec6d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401bec6d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bec57`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bec57`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bed27`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bed82`
- `ntoskrnl!ZwQueryValueKey` at `0x1401beddc`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bee6f`
- `ntoskrnl!ZwQueryValueKey` at `0x1401befa6`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf003`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf062`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf0ba`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf138`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf19e`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf202`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf267`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf3bd`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf441`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf4b1`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf50b`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf587`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf5e5`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf692`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bed27`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bed82`
- `ntoskrnl!ZwQueryValueKey` at `0x1401beddc`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bee6f`
- `ntoskrnl!ZwQueryValueKey` at `0x1401befa6`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf003`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf062`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf0ba`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf138`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf19e`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf202`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf267`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf3bd`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf441`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf4b1`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf50b`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf587`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf5e5`
- `ntoskrnl!ZwQueryValueKey` at `0x1401bf692`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401beea6`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401beeff`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401bef52`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401beea6`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401beeff`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401bef52`
- `ntoskrnl!ZwClose` at `0x1401bf6f0`
- `ntoskrnl!ZwClose` at `0x1401bf6f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401becf2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bed57`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bedb1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bef76`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401befd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf037`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf08f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf10d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf173`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf1d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf238`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf38e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf412`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf482`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf4dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf557`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf5ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf663`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401becf2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bed57`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bedb1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bef76`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401befd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf037`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf08f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf10d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf173`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf1d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf238`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf38e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf412`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf482`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf4dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf557`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf5ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bf663`

## string_xrefs

- `0x1401bf0e5`: `LERemoteConnParamsIntervalMax`
- `0x1401bf167`: `LERemoteConnParamsIntervalMin`

## pseudocode

```c
__int64 __fastcall HCI_DibGetStoredDevInfoEx(
        struct HCI_INTERFACE *a1,
        struct DEVICE_INFO_BLOCK *a2,
        enum _HCI_PHY_TYPE a3,
        unsigned __int8 *a4)
{
  enum _HCI_PHY_TYPE v5; // r12
  struct _FAST_MUTEX *p_ProtocolsLock; // r13
  int v8; // edx
  NTSTATUS DeviceKey; // ebx
  int v10; // r8d
  __int64 v11; // r14
  const wchar_t *v12; // rax
  __int64 v13; // rcx
  __int16 v14; // cx
  HANDLE v15; // rcx
  const wchar_t *v16; // rax
  __int64 v17; // rcx
  __int16 v18; // cx
  const wchar_t *v19; // rax
  __int16 v20; // r14
  char v21; // r12
  char v22; // r13
  unsigned __int16 v23; // r15
  unsigned __int16 v24; // r14
  unsigned __int16 v25; // bx
  unsigned __int16 v26; // r8
  char v27; // al
  _IO_CAPABILITY v28; // eax
  char v29; // al
  void **v30; // rax
  const WCHAR *v31; // rdx
  ULONG ResultLength; // [rsp+54h] [rbp-ACh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE KeyHandle; // [rsp+68h] [rbp-98h] BYREF
  char v37; // [rsp+70h] [rbp-90h]
  HANDLE v38; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+80h] [rbp-80h]
  int v40; // [rsp+84h] [rbp-7Ch]
  int v41; // [rsp+88h] [rbp-78h]
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp-70h] BYREF
  int v43; // [rsp+94h] [rbp-6Ch]
  unsigned int Src; // [rsp+98h] [rbp-68h]
  _QWORD Src_4[32]; // [rsp+9Ch] [rbp-64h] BYREF

  DestinationString = 0;
  KeyHandle = 0;
  v5 = a3;
  ResultLength = 0;
  KeEnterCriticalRegion();
  p_ProtocolsLock = &a2->ProtocolsLock;
  ExAcquireFastMutexUnsafe(&a2->ProtocolsLock);
  DeviceKey = HCI_GetDeviceKey(&a2->DeviceInfo.address, &KeyHandle, 0);
  if ( DeviceKey >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ManufacturerId");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x108u,
           &ResultLength) >= 0
      && v43 == 4
      && LODWORD(Src_4[0]) )
    {
      a2->RadioInfo.mfg = Src_4[0];
    }
    RtlInitUnicodeString(&DestinationString, L"LmpVersion");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x108u,
           &ResultLength) >= 0
      && v43 == 4
      && LODWORD(Src_4[0]) )
    {
      a2->RadioInfo.lmpVersion = Src_4[0];
    }
    RtlInitUnicodeString(&DestinationString, L"LmpSubversion");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x108u,
           &ResultLength) >= 0
      && v43 == 4
      && LODWORD(Src_4[0]) )
    {
      a2->RadioInfo.lmpSubversion = Src_4[0];
    }
    v11 = 0x7FFF;
    v12 = L"Migrated";
    DestinationString = 0;
    v13 = 0x7FFF;
    while ( *v12 )
    {
      ++v12;
      if ( !--v13 )
        goto LABEL_23;
    }
    v14 = 2 * v13;
    DestinationString.Buffer = L"Migrated";
    DestinationString.Length = -2 - v14;
    DestinationString.MaximumLength = -v14;
LABEL_23:
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x108u,
           &ResultLength) >= 0
      && v43 == 4
      && LODWORD(Src_4[0]) )
    {
      v15 = KeyHandle;
      *a4 = 1;
      ZwDeleteValueKey(v15, &DestinationString);
      DestinationString = 0;
      v16 = L"FingerprintTimestamp";
      v17 = 0x7FFF;
      while ( *v16 )
      {
        ++v16;
        if ( !--v17 )
          goto LABEL_31;
      }
      v18 = 2 * v17;
      DestinationString.Buffer = L"FingerprintTimestamp";
      DestinationString.Length = -2 - v18;
      DestinationString.MaximumLength = -v18;
LABEL_31:
      ZwDeleteValueKey(KeyHandle, &DestinationString);
      DestinationString = 0;
      v19 = L"FingerprintVersion";
      while ( *v19 )
      {
        ++v19;
        if ( !--v11 )
          goto LABEL_36;
      }
      v20 = 2 * v11;
      DestinationString.Buffer = L"FingerprintVersion";
      DestinationString.Length = -2 - v20;
      DestinationString.MaximumLength = -v20;
LABEL_36:
      ZwDeleteValueKey(KeyHandle, &DestinationString);
    }
    if ( v5 == HciPhyTypeBR )
    {
      RtlInitUnicodeString(&DestinationString, L"LMPFeatures");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x108u,
             &ResultLength) >= 0
        && v43 == 11
        && Src_4[0] )
      {
        a2->RadioInfo.lmpSupportedFeatures = Src_4[0];
      }
      RtlInitUnicodeString(&DestinationString, L"HostSupportedFeaturesMap");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x108u,
             &ResultLength) >= 0
        && v43 == 11 )
      {
        a2->RemoteHostSupportedFeatures = (_BTH_HOST_SUPPORTED_FEATURES_MAP)Src_4[0];
      }
    }
    RtlInitUnicodeString(&DestinationString, L"LastSeen");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x108u,
           &ResultLength) >= 0
      && v43 == 11 )
    {
      a2->LastSeenTimestamp.QuadPart = Src_4[0];
    }
    RtlInitUnicodeString(&DestinationString, L"LastConnected");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x108u,
           &ResultLength) >= 0
      && v43 == 11 )
    {
      a2->LastConnectedTimestamp.QuadPart = Src_4[0];
    }
    if ( v5 == HciPhyTypeLE )
    {
      LODWORD(v38) = 0;
      v41 = 0;
      v21 = 0;
      v40 = 0;
      v22 = 0;
      v39 = 0;
      v37 = 0;
      RtlInitUnicodeString(&DestinationString, L"LERemoteConnParamsIntervalMax");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x108u,
             &ResultLength) >= 0
        && v43 == 4
        && (v23 = Src_4[0], LODWORD(Src_4[0]) < 0xFFFF) )
      {
        v37 = 1;
      }
      else
      {
        v23 = v39;
      }
      RtlInitUnicodeString(&DestinationString, L"LERemoteConnParamsIntervalMin");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x108u,
             &ResultLength) >= 0
        && v43 == 4
        && (v24 = Src_4[0], LODWORD(Src_4[0]) < 0xFFFF) )
      {
        v22 = 1;
      }
      else
      {
        v24 = v40;
      }
      RtlInitUnicodeString(&DestinationString, L"LERemoteConnParamsLatency");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x108u,
             &ResultLength) >= 0
        && v43 == 4
        && (v25 = Src_4[0], LODWORD(Src_4[0]) < 0xFFFF) )
      {
        v21 = 1;
      }
      else
      {
        v25 = v41;
      }
      RtlInitUnicodeString(&DestinationString, L"LERemoteConnParamsLSTO");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x108u,
             &ResultLength) >= 0
        && v43 == 4
        && (v26 = Src_4[0], LODWORD(Src_4[0]) < 0xFFFF) )
      {
        v27 = 1;
      }
      else
      {
        v26 = (unsigned __int16)v38;
        v27 = 0;
      }
      if ( v21
        && v22
        && v37
        && v27
        && v25 <= 0x1F4u
        && (unsigned __int16)(v24 - 6) <= 0xC7Au
        && (unsigned __int16)(v23 - 6) <= 0xC7Au
        && v24 <= v23
        && (unsigned int)v26 - 10 <= 0xC76 )
      {
        v5 = a3;
        p_ProtocolsLock = &a2->ProtocolsLock;
        if ( 10 * (unsigned int)v26 > ((unsigned int)v25 + 1) * (250 * v23 / 100) )
        {
          WORD2(v38) = v24;
          HIWORD(v38) = v23;
          WORD1(v38) = v25;
          LOWORD(v38) = v26;
          a2->LELastRemoteConnectionParameters.0 = ($F268B82FC2F74C69CBB841C775A245E2)v38;
          if ( !a2->LELastRemoteConnectionParameters._MyHasVal )
            a2->LELastRemoteConnectionParameters._MyHasVal = 1;
        }
      }
      else
      {
        v5 = a3;
        p_ProtocolsLock = &a2->ProtocolsLock;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"FriendlyName");
    DeviceKey = ZwQueryValueKey(
                  KeyHandle,
                  &DestinationString,
                  KeyValuePartialInformation,
                  KeyValueInformation,
                  0x108u,
                  &ResultLength);
    if ( DeviceKey >= 0 && v43 == 3 && Src <= 0xF8 )
    {
      memmove(a2->FriendlyName, Src_4, Src);
      a2->FriendlyName[247] = 0;
    }
    if ( v5 == HciPhyTypeLE )
    {
      RtlInitUnicodeString(&DestinationString, L"LEName");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x108u,
             &ResultLength) >= 0
        && v43 == 3
        && Src <= 0xF8 )
      {
        HCI_DibUpdateLEName(a2, (char *)Src_4, Src);
      }
      RtlInitUnicodeString(&DestinationString, L"LocalEvaldIoCapLE");
      DeviceKey = ZwQueryValueKey(
                    KeyHandle,
                    &DestinationString,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x108u,
                    &ResultLength);
      if ( DeviceKey >= 0 && v43 == 4 )
        goto LABEL_101;
    }
    else if ( v5 )
    {
LABEL_99:
      if ( DeviceKey < 0 || v43 != 4 )
      {
        DeviceKey = 0;
        v28 = IoCaps_Undefined;
        goto LABEL_105;
      }
LABEL_101:
      v28 = Src_4[0];
      if ( LODWORD(Src_4[0]) > 4 )
        v28 = IoCaps_Undefined;
LABEL_105:
      a2->LocalEvaldIoCap = v28;
      if ( v5 == HciPhyTypeLE )
      {
        RtlInitUnicodeString(&DestinationString, L"LEAppearance");
        if ( ZwQueryValueKey(
               KeyHandle,
               &DestinationString,
               KeyValuePartialInformation,
               KeyValueInformation,
               0x108u,
               &ResultLength) >= 0
          && v43 == 4
          && LODWORD(Src_4[0]) < 0xFFFF )
        {
          a2->LEAppearance = Src_4[0];
        }
        RtlInitUnicodeString(&DestinationString, L"LEAddressType");
        DeviceKey = ZwQueryValueKey(
                      KeyHandle,
                      &DestinationString,
                      KeyValuePartialInformation,
                      KeyValueInformation,
                      0x108u,
                      &ResultLength);
        if ( DeviceKey >= 0 && v43 == 4 )
        {
          v29 = Src_4[0];
          if ( LODWORD(Src_4[0]) <= 1 )
          {
            a2->LEOriginalAddressType = Src_4[0];
            if ( v29 == 1 )
              a2->DeviceInfo.flags |= 0x100000u;
          }
        }
        else
        {
          DeviceKey = 0;
        }
      }
      v38 = 0;
      v30 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v38);
      if ( (int)HCI_GetServicesForKey(KeyHandle, a2->Hci, v30, 0) < 0 )
        goto LABEL_125;
      if ( v5 )
      {
        if ( v5 != HciPhyTypeLE )
        {
          DeviceKey = -1073741637;
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
LABEL_125:
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
          goto LABEL_126;
        }
        v31 = L"LEExtendedDeviceInfoFlags";
      }
      else
      {
        v31 = L"BRExtendedDeviceInfoFlags";
      }
      RtlInitUnicodeString(&DestinationString, v31);
      DeviceKey = ZwQueryValueKey(
                    v38,
                    &DestinationString,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x108u,
                    &ResultLength);
      if ( DeviceKey >= 0 && v43 == 11 )
        *(_QWORD *)a2->exDeviceFlags = Src_4[0];
      goto LABEL_125;
    }
    RtlInitUnicodeString(&DestinationString, L"LocalEvaldIoCap");
    DeviceKey = ZwQueryValueKey(
                  KeyHandle,
                  &DestinationString,
                  KeyValuePartialInformation,
                  KeyValueInformation,
                  0x108u,
                  &ResultLength);
    goto LABEL_99;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
    LOBYTE(v8) = 0;
  LOBYTE(v10) = 1;
  WPP_RECORDER_AND_TRACE_SF_d(
    WPP_GLOBAL_Control->AttachedDevice,
    v8,
    v10,
    a2->IfrLog,
    3,
    2,
    121,
    (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
    DeviceKey);
LABEL_126:
  ExReleaseFastMutexUnsafe(p_ProtocolsLock);
  KeLeaveCriticalRegion();
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)DeviceKey;
}

```

## disassembly

```asm
0x1401bec04  mov     [rsp-8+arg_0], rbx
0x1401bec09  push    rbp
0x1401bec0a  push    rsi
0x1401bec0b  push    rdi
0x1401bec0c  push    r12
0x1401bec0e  push    r13
0x1401bec10  push    r14
0x1401bec12  push    r15
0x1401bec14  lea     rbp, [rsp-0B0h]
0x1401bec1c  sub     rsp, 1B0h
0x1401bec23  mov     rax, cs:__security_cookie
0x1401bec2a  xor     rax, rsp
0x1401bec2d  mov     [rbp+0E0h+var_40], rax
0x1401bec34  xorps   xmm0, xmm0
0x1401bec37  mov     [rsp+1E0h+var_190], r8b
0x1401bec3c  xor     r14d, r14d
0x1401bec3f  mov     r15, r9
0x1401bec42  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x1401bec47  mov     [rsp+1E0h+KeyHandle], r14
0x1401bec4c  mov     r12b, r8b
0x1401bec4f  mov     [rsp+1E0h+var_18C], r14d
0x1401bec54  mov     rdi, rdx
0x1401bec57  call    cs:__imp_KeEnterCriticalRegion
0x1401bec5e  nop     dword ptr [rax+rax+00h]
0x1401bec63  lea     r13, [rdi+380h]
0x1401bec6a  mov     rcx, r13; FastMutex
0x1401bec6d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1401bec74  nop     dword ptr [rax+rax+00h]
0x1401bec79  lea     rcx, [rdi+20h]; unsigned __int64 *
0x1401bec7d  xor     r8d, r8d; unsigned __int8
0x1401bec80  lea     rdx, [rsp+1E0h+KeyHandle]; void **
0x1401bec85  call    ?HCI_GetDeviceKey@@YAJPEB_KPEAPEAXE@Z; HCI_GetDeviceKey(unsigned __int64 const *,void * *,uchar)
0x1401bec8a  mov     ebx, eax
0x1401bec8c  test    eax, eax
0x1401bec8e  jns     short loc_1401BECE6
0x1401bec90  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bec97  lea     esi, [r14+2]
0x1401bec9b  mov     ecx, [rax+2Ch]
0x1401bec9e  test    sil, cl
0x1401beca1  jz      short loc_1401BECAB
0x1401beca3  cmp     byte ptr [rax+29h], 3
0x1401beca7  mov     dl, 1
0x1401beca9  jnb     short loc_1401BECAE
0x1401becab  mov     dl, r14b
0x1401becae  mov     r9, [rdi+838h]
0x1401becb5  lea     rcx, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1401becbc  mov     [rsp+1E0h+var_1A0], ebx
0x1401becc0  mov     r8b, 1
0x1401becc3  mov     [rsp+1E0h+var_1A8], rcx
0x1401becc8  mov     rcx, [rax+18h]
0x1401beccc  mov     [rsp+1E0h+var_1B0], 79h ; 'y'
0x1401becd3  mov     dword ptr [rsp+1E0h+ResultLength], esi
0x1401becd7  mov     byte ptr [rsp+1E0h+Length], 3
0x1401becdc  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401bece1  jmp     loc_1401BF6CB
0x1401bece6  lea     rdx, aManufacturerid; "ManufacturerId"
0x1401beced  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1401becf2  call    cs:__imp_RtlInitUnicodeString
0x1401becf9  nop     dword ptr [rax+rax+00h]
0x1401becfe  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401bed03  lea     rax, [rsp+1E0h+var_18C]
0x1401bed08  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x1401bed0d  lea     r9, [rbp+0E0h+KeyValueInformation]; KeyValueInformation
0x1401bed11  mov     esi, 2
0x1401bed16  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401bed1b  mov     ebx, 108h
0x1401bed20  mov     r8d, esi; KeyValueInformationClass
0x1401bed23  mov     [rsp+1E0h+Length], ebx; Length
0x1401bed27  call    cs:__imp_ZwQueryValueKey
0x1401bed2e  nop     dword ptr [rax+rax+00h]
0x1401bed33  test    eax, eax
0x1401bed35  js      short loc_1401BED4B
0x1401bed37  cmp     [rbp+0E0h+var_14C], 4
0x1401bed3b  jnz     short loc_1401BED4B
0x1401bed3d  mov     eax, dword ptr [rbp+0E0h+Src+4]
0x1401bed40  test    eax, eax
0x1401bed42  jz      short loc_1401BED4B
0x1401bed44  mov     [rdi+3DEh], ax
0x1401bed4b  lea     rdx, aLmpversion; "LmpVersion"
0x1401bed52  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1401bed57  call    cs:__imp_RtlInitUnicodeString
0x1401bed5e  nop     dword ptr [rax+rax+00h]
0x1401bed63  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401bed68  lea     rax, [rsp+1E0h+var_18C]
0x1401bed6d  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x1401bed72  lea     r9, [rbp+0E0h+KeyValueInformation]; KeyValueInformation
0x1401bed76  mov     r8d, esi; KeyValueInformationClass
0x1401bed79  mov     [rsp+1E0h+Length], ebx; Length
0x1401bed7d  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401bed82  call    cs:__imp_ZwQueryValueKey
0x1401bed89  nop     dword ptr [rax+rax+00h]
0x1401bed8e  test    eax, eax
0x1401bed90  js      short loc_1401BEDA5
0x1401bed92  cmp     [rbp+0E0h+var_14C], 4
0x1401bed96  jnz     short loc_1401BEDA5
0x1401bed98  mov     eax, dword ptr [rbp+0E0h+Src+4]
0x1401bed9b  test    eax, eax
0x1401bed9d  jz      short loc_1401BEDA5
0x1401bed9f  mov     [rdi+3E2h], al
0x1401beda5  lea     rdx, aLmpsubversion; "LmpSubversion"
0x1401bedac  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1401bedb1  call    cs:__imp_RtlInitUnicodeString
0x1401bedb8  nop     dword ptr [rax+rax+00h]
0x1401bedbd  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401bedc2  lea     rax, [rsp+1E0h+var_18C]
0x1401bedc7  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x1401bedcc  lea     r9, [rbp+0E0h+KeyValueInformation]; KeyValueInformation
0x1401bedd0  mov     r8d, esi; KeyValueInformationClass
0x1401bedd3  mov     [rsp+1E0h+Length], ebx; Length
0x1401bedd7  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401beddc  call    cs:__imp_ZwQueryValueKey
0x1401bede3  nop     dword ptr [rax+rax+00h]
0x1401bede8  test    eax, eax
0x1401bedea  js      short loc_1401BEE00
0x1401bedec  cmp     [rbp+0E0h+var_14C], 4
0x1401bedf0  jnz     short loc_1401BEE00
0x1401bedf2  mov     eax, dword ptr [rbp+0E0h+Src+4]
0x1401bedf5  test    eax, eax
0x1401bedf7  jz      short loc_1401BEE00
0x1401bedf9  mov     [rdi+3E0h], ax
0x1401bee00  xorps   xmm0, xmm0
0x1401bee03  lea     r8, aMigrated; "Migrated"
0x1401bee0a  mov     r14d, 7FFFh
0x1401bee10  mov     rax, r8
0x1401bee13  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x1401bee18  mov     ecx, r14d
0x1401bee1b  xor     edx, edx
0x1401bee1d  mov     ebx, 0FFFEh
0x1401bee22  cmp     [rax], dx
0x1401bee25  jz      short loc_1401BEE32
0x1401bee27  add     rax, rsi
0x1401bee2a  sub     rcx, 1
0x1401bee2e  jnz     short loc_1401BEE1D
0x1401bee30  jmp     short loc_1401BEE4C
0x1401bee32  add     cx, cx
0x1401bee35  mov     [rsp+1E0h+DestinationString.Buffer], r8
0x1401bee3a  mov     eax, ebx
0x1401bee3c  sub     ax, cx
0x1401bee3f  mov     [rsp+1E0h+DestinationString.Length], ax
0x1401bee44  add     ax, si
0x1401bee47  mov     [rsp+1E0h+DestinationString.MaximumLength], ax
0x1401bee4c  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401bee51  lea     rax, [rsp+1E0h+var_18C]
0x1401bee56  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x1401bee5b  lea     r9, [rbp+0E0h+KeyValueInformation]; KeyValueInformation
0x1401bee5f  mov     r8d, esi; KeyValueInformationClass
0x1401bee62  mov     [rsp+1E0h+Length], 108h; Length
0x1401bee6a  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401bee6f  call    cs:__imp_ZwQueryValueKey
0x1401bee76  nop     dword ptr [rax+rax+00h]
0x1401bee7b  xor     ecx, ecx
0x1401bee7d  test    eax, eax
0x1401bee7f  js      loc_1401BEF5E
0x1401bee85  cmp     [rbp+0E0h+var_14C], 4
0x1401bee89  jnz     loc_1401BEF5E
0x1401bee8f  cmp     dword ptr [rbp+0E0h+Src+4], ecx
0x1401bee92  jz      loc_1401BEF5E
0x1401bee98  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401bee9d  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401beea2  mov     byte ptr [r15], 1
0x1401beea6  call    cs:__imp_ZwDeleteValueKey
0x1401beead  nop     dword ptr [rax+rax+00h]
0x1401beeb2  xorps   xmm0, xmm0
0x1401beeb5  lea     rdx, aFingerprinttim; "FingerprintTimestamp"
0x1401beebc  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x1401beec1  mov     rax, rdx
0x1401beec4  mov     rcx, r14
0x1401beec7  xor     r15d, r15d
0x1401beeca  cmp     [rax], r15w
0x1401beece  jz      short loc_1401BEEDB
0x1401beed0  add     rax, rsi
0x1401beed3  sub     rcx, 1
0x1401beed7  jnz     short loc_1401BEECA
0x1401beed9  jmp     short loc_1401BEEF5
0x1401beedb  add     cx, cx
0x1401beede  mov     [rsp+1E0h+DestinationString.Buffer], rdx
0x1401beee3  mov     eax, ebx
0x1401beee5  sub     ax, cx
0x1401beee8  mov     [rsp+1E0h+DestinationString.Length], ax
0x1401beeed  add     ax, si
0x1401beef0  mov     [rsp+1E0h+DestinationString.MaximumLength], ax
0x1401beef5  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401beefa  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401beeff  call    cs:__imp_ZwDeleteValueKey
0x1401bef06  nop     dword ptr [rax+rax+00h]
0x1401bef0b  xorps   xmm0, xmm0
0x1401bef0e  lea     rcx, aFingerprintver; "FingerprintVersion"
0x1401bef15  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x1401bef1a  mov     rax, rcx
0x1401bef1d  cmp     [rax], r15w
0x1401bef21  jz      short loc_1401BEF2E
0x1401bef23  add     rax, rsi
0x1401bef26  sub     r14, 1
0x1401bef2a  jnz     short loc_1401BEF1D
0x1401bef2c  jmp     short loc_1401BEF48
0x1401bef2e  add     r14w, r14w
0x1401bef32  mov     [rsp+1E0h+DestinationString.Buffer], rcx
0x1401bef37  sub     bx, r14w
0x1401bef3b  mov     [rsp+1E0h+DestinationString.Length], bx
0x1401bef40  add     bx, si
0x1401bef43  mov     [rsp+1E0h+DestinationString.MaximumLength], bx
0x1401bef48  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401bef4d  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401bef52  call    cs:__imp_ZwDeleteValueKey
0x1401bef59  nop     dword ptr [rax+rax+00h]
0x1401bef5e  xor     r14d, r14d
0x1401bef61  test    r12b, r12b
0x1401bef64  jnz     loc_1401BF026
0x1401bef6a  lea     rdx, aLmpfeatures; "LMPFeatures"
0x1401bef71  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1401bef76  call    cs:__imp_RtlInitUnicodeString
0x1401bef7d  nop     dword ptr [rax+rax+00h]
0x1401bef82  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401bef87  lea     rax, [rsp+1E0h+var_18C]
0x1401bef8c  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x1401bef91  lea     r9, [rbp+0E0h+KeyValueInformation]; KeyValueInformation
0x1401bef95  mov     ebx, 108h
0x1401bef9a  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401bef9f  mov     r8d, esi; KeyValueInformationClass
0x1401befa2  mov     [rsp+1E0h+Length], ebx; Length
0x1401befa6  call    cs:__imp_ZwQueryValueKey
0x1401befad  nop     dword ptr [rax+rax+00h]
0x1401befb2  test    eax, eax
0x1401befb4  js      short loc_1401BEFCC
0x1401befb6  cmp     [rbp+0E0h+var_14C], 0Bh
0x1401befba  jnz     short loc_1401BEFCC
0x1401befbc  mov     rax, [rbp+0E0h+Src+4]
0x1401befc0  test    rax, rax
0x1401befc3  jz      short loc_1401BEFCC
0x1401befc5  mov     [rdi+3D6h], rax
0x1401befcc  lea     rdx, aHostsupportedf; "HostSupportedFeaturesMap"
0x1401befd3  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1401befd8  call    cs:__imp_RtlInitUnicodeString
0x1401befdf  nop     dword ptr [rax+rax+00h]
0x1401befe4  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401befe9  lea     rax, [rsp+1E0h+var_18C]
0x1401befee  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x1401beff3  lea     r9, [rbp+0E0h+KeyValueInformation]; KeyValueInformation
0x1401beff7  mov     r8d, esi; KeyValueInformationClass
0x1401beffa  mov     [rsp+1E0h+Length], ebx; Length
0x1401beffe  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401bf003  call    cs:__imp_ZwQueryValueKey
0x1401bf00a  nop     dword ptr [rax+rax+00h]
0x1401bf00f  test    eax, eax
0x1401bf011  js      short loc_1401BF02B
0x1401bf013  cmp     [rbp+0E0h+var_14C], 0Bh
0x1401bf017  jnz     short loc_1401BF02B
0x1401bf019  mov     rax, [rbp+0E0h+Src+4]
0x1401bf01d  mov     [rdi+3E3h], rax
0x1401bf024  jmp     short loc_1401BF02B
0x1401bf026  mov     ebx, 108h
0x1401bf02b  lea     rdx, aLastseen; "LastSeen"
0x1401bf032  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1401bf037  call    cs:__imp_RtlInitUnicodeString
0x1401bf03e  nop     dword ptr [rax+rax+00h]
0x1401bf043  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401bf048  lea     rax, [rsp+1E0h+var_18C]
0x1401bf04d  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x1401bf052  lea     r9, [rbp+0E0h+KeyValueInformation]; KeyValueInformation
0x1401bf056  mov     r8d, esi; KeyValueInformationClass
0x1401bf059  mov     [rsp+1E0h+Length], ebx; Length
0x1401bf05d  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401bf062  call    cs:__imp_ZwQueryValueKey
0x1401bf069  nop     dword ptr [rax+rax+00h]
0x1401bf06e  test    eax, eax
0x1401bf070  js      short loc_1401BF083
0x1401bf072  cmp     [rbp+0E0h+var_14C], 0Bh
0x1401bf076  jnz     short loc_1401BF083
0x1401bf078  mov     rax, [rbp+0E0h+Src+4]
0x1401bf07c  mov     [rdi+670h], rax
0x1401bf083  lea     rdx, aLastconnected; "LastConnected"
0x1401bf08a  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1401bf08f  call    cs:__imp_RtlInitUnicodeString
0x1401bf096  nop     dword ptr [rax+rax+00h]
0x1401bf09b  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1401bf0a0  lea     rax, [rsp+1E0h+var_18C]
0x1401bf0a5  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x1401bf0aa  lea     r9, [rbp+0E0h+KeyValueInformation]; KeyValueInformation
0x1401bf0ae  mov     r8d, esi; KeyValueInformationClass
0x1401bf0b1  mov     [rsp+1E0h+Length], ebx; Length
0x1401bf0b5  lea     rdx, [rsp+1E0h+DestinationString]; ValueName
0x1401bf0ba  call    cs:__imp_ZwQueryValueKey
0x1401bf0c1  nop     dword ptr [rax+rax+00h]
0x1401bf0c6  test    eax, eax
0x1401bf0c8  js      short loc_1401BF0DB
0x1401bf0ca  cmp     [rbp+0E0h+var_14C], 0Bh
0x1401bf0ce  jnz     short loc_1401BF0DB
0x1401bf0d0  mov     rax, [rbp+0E0h+Src+4]
0x1401bf0d4  mov     [rdi+678h], rax
0x1401bf0db  cmp     r12b, 1
0x1401bf0df  jnz     loc_1401BF382
0x1401bf0e5  lea     rdx, aLeremoteconnpa_2; "LERemoteConnParamsIntervalMax"
0x1401bf0ec  mov     dword ptr [rsp+1E0h+var_168], r14d
0x1401bf0f1  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1401bf0f6  mov     [rbp+0E0h+var_158], r14d
0x1401bf0fa  mov     r12b, r14b
0x1401bf0fd  mov     [rbp+0E0h+var_15C], r14d
0x1401bf101  mov     r13b, r14b
0x1401bf104  mov     [rbp+0E0h+var_160], r14d
0x1401bf108  mov     [rsp+1E0h+var_170], r14b
  ... truncated ...
```
