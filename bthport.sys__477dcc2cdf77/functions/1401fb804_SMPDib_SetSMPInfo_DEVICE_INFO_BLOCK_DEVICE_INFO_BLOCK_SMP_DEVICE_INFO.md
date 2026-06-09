# SMPDib_SetSMPInfo(DEVICE_INFO_BLOCK *,DEVICE_INFO_BLOCK *,SMP_DEVICE_INFO *)

- ea: `0x1401fb804`
- end: `0x1401fc794`
- name: `?SMPDib_SetSMPInfo@@YAJPEAUDEVICE_INFO_BLOCK@@0PEAUSMP_DEVICE_INFO@@@Z`
- size: `3984`
- prototype: `__int64 __fastcall(struct DEVICE_INFO_BLOCK *, struct DEVICE_INFO_BLOCK *, struct SMP_DEVICE_INFO *)`
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400515b0`
- `0x14005de64`
- `0x1401f544c`

## callees

- `0x140005608`
- `0x140005690`
- `0x140058f78`
- `0x14005b478`
- `0x1400a95f0`
- `0x14014cb50`
- `0x140155cbc`
- `0x1401563d8`
- `0x140165540`
- `0x140165940`
- `0x1401c1a48`
- `0x1401fa610`
- `0x1401fb804`
- `0x140209110`
- `0x140209168`

## import_xrefs

- `ntoskrnl!ZwDeleteKey` at `0x1401fc20b`
- `ntoskrnl!ZwDeleteKey` at `0x1401fc20b`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401fb9bc`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401fb9bc`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbaa3`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbb33`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbbb9`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbc45`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbcd4`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbd62`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbdee`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbe7e`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbf04`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbf95`
- `ntoskrnl!ZwSetValueKey` at `0x1401fc019`
- `ntoskrnl!ZwSetValueKey` at `0x1401fc0ba`
- `ntoskrnl!ZwSetValueKey` at `0x1401fc146`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbaa3`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbb33`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbbb9`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbc45`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbcd4`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbd62`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbdee`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbe7e`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbf04`
- `ntoskrnl!ZwSetValueKey` at `0x1401fbf95`
- `ntoskrnl!ZwSetValueKey` at `0x1401fc019`
- `ntoskrnl!ZwSetValueKey` at `0x1401fc0ba`
- `ntoskrnl!ZwSetValueKey` at `0x1401fc146`
- `ntoskrnl!ZwClose` at `0x1401fb9cc`
- `ntoskrnl!ZwClose` at `0x1401fc1c4`
- `ntoskrnl!ZwClose` at `0x1401fc21b`
- `ntoskrnl!ZwClose` at `0x1401fb9cc`
- `ntoskrnl!ZwClose` at `0x1401fc1c4`
- `ntoskrnl!ZwClose` at `0x1401fc21b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fba77`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbafe`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbb8a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbc10`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbca8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbd34`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbdc2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbe52`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbed5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbf69`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbfec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fc08e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fc11a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fba77`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbafe`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbb8a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbc10`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbca8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbd34`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbdc2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbe52`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbed5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbf69`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fbfec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fc08e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401fc11a`

## pseudocode

```c
__int64 __fastcall SMPDib_SetSMPInfo(
        struct DEVICE_INFO_BLOCK *a1,
        struct DEVICE_INFO_BLOCK *a2,
        struct SMP_DEVICE_INFO *a3)
{
  struct SMP_DEVICE_INFO *v3; // r12
  int v4; // r15d
  char v6; // di
  __int16 DeviceType; // ax
  int v8; // r8d
  int v9; // edx
  char v10; // r13
  unsigned int Flag; // esi
  int v12; // ecx
  unsigned int v13; // r13d
  char v14; // si
  bool v15; // zf
  char v16; // r11
  __int16 v17; // ax
  __int64 v18; // r14
  int v19; // edx
  _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 *v21; // r8
  NTSTATUS v22; // eax
  PDEVICE_OBJECT v23; // rcx
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  NTSTATUS v28; // eax
  NTSTATUS v29; // eax
  NTSTATUS v30; // eax
  NTSTATUS v31; // eax
  NTSTATUS v32; // eax
  NTSTATUS v33; // eax
  int v34; // eax
  NTSTATUS v35; // eax
  NTSTATUS v36; // eax
  int v37; // edx
  unsigned int v38; // edx
  unsigned int v39; // r8d
  unsigned __int8 *LTK; // rax
  unsigned __int8 *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  unsigned int v44; // edx
  unsigned __int8 *IRK; // rax
  unsigned __int8 *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rcx
  unsigned int v49; // edx
  unsigned __int8 *InboundCSRK; // rax
  unsigned __int8 *v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  unsigned int v54; // r9d
  unsigned __int8 *OutboundCSRK; // rax
  unsigned __int8 *v56; // rdx
  unsigned int v57; // edx
  unsigned int v58; // eax
  int v59; // edx
  int v60; // eax
  int v61; // edx
  unsigned int v62; // eax
  int v63; // eax
  int v64; // edx
  unsigned int v65; // eax
  int v66; // eax
  int v67; // edx
  unsigned int v68; // eax
  int v69; // esi
  unsigned __int8 LEOriginalAddressType; // al
  __int64 *v71; // r8
  bool v72; // r13
  __int16 v73; // ax
  int v74; // r14d
  __int16 v75; // ax
  __int16 v76; // ax
  __int64 *v77; // rdx
  int Data; // [rsp+20h] [rbp-99h]
  ULONG DataSize; // [rsp+28h] [rbp-91h]
  int v81; // [rsp+30h] [rbp-89h]
  __int16 v82; // [rsp+30h] [rbp-89h]
  int v83; // [rsp+38h] [rbp-81h]
  char v84; // [rsp+40h] [rbp-79h]
  char v85; // [rsp+40h] [rbp-79h]
  bool v86; // [rsp+60h] [rbp-59h]
  HANDLE KeyHandle; // [rsp+68h] [rbp-51h] BYREF
  unsigned int EncryptionKeySize; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int64 AddressInformation; // [rsp+88h] [rbp-31h] BYREF
  struct DEVICE_INFO_BLOCK *v91; // [rsp+90h] [rbp-29h]
  WCHAR SourceString[8]; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v93; // [rsp+B0h] [rbp-9h]
  struct _UNICODE_STRING ValueName; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v95; // [rsp+D0h] [rbp+17h]

  v91 = a2;
  v3 = a3;
  v95 = 0;
  KeyHandle = 0;
  v4 = 0;
  EncryptionKeySize = 0;
  AddressInformation = 0;
  *(_OWORD *)SourceString = 0;
  v93 = 0;
  ValueName = 0;
  DestinationString = 0;
  v6 = 1;
  if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
    || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    LOBYTE(a2) = 0;
  }
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
  {
    LOBYTE(a3) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      a1->IfrLog,
      5,
      10,
      126,
      (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
  }
  DS_Init(SourceString, &a1->DeviceInfo.address);
  if ( !v3 )
  {
    LOBYTE(v9) = 0;
    v10 = 0;
    goto LABEL_15;
  }
  Flag = v3->Flag;
  v12 = v3->Flag & 0x400;
  LOBYTE(v9) = v12 != 0;
  v86 = v12 != 0;
  if ( v12 )
    v13 = HIWORD(Flag);
  else
    LOBYTE(v13) = v3->Flag;
  v10 = v13 & 1;
  if ( !v12 )
  {
    v15 = (Flag & 0xFFFEFFFF) == 0;
    v14 = 1;
    if ( !v15 )
    {
LABEL_16:
      v86 = v9;
      goto LABEL_17;
    }
LABEL_15:
    v14 = 0;
    goto LABEL_16;
  }
  v14 = BYTE2(Flag) & 1;
LABEL_17:
  if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
    || (v16 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    v16 = 0;
  }
  v17 = WPP_GLOBAL_Control->DeviceType;
  if ( v16 || v17 )
  {
    v9 = (unsigned __int8)v9;
    v84 = v9;
    LOBYTE(v9) = v16;
    LOBYTE(v8) = v17 != 0;
    WPP_RECORDER_AND_TRACE_SF_llll(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      v8,
      a1->IfrLog,
      Data,
      DataSize,
      v81,
      v83,
      v84,
      v10,
      v14,
      v3 != 0);
  }
  v18 = 16;
  if ( v14 )
  {
    if ( (int)HCI_GetPersonalDevicesKey(a1->Hci, &KeyHandle, 0) >= 0 )
    {
      ZwDeleteValueKey(KeyHandle, (PUNICODE_STRING)&ValueName.Buffer);
      ZwClose(KeyHandle);
      KeyHandle = 0;
    }
    v4 = BthCreateKeySdEnforced(a1->Hci->DevExt->LinkKeysHandle, v95, &KeyHandle);
    if ( v4 < 0 )
    {
      LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
      v85 = v4;
      v82 = 128;
      goto LABEL_32;
    }
    if ( (v3->Flag & 1) != 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"LTK");
      v22 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, v3->LTK, 0x10u);
      v4 = v22;
      if ( v22 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v22;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 129;
LABEL_40:
        AttachedDevice = v23->AttachedDevice;
LABEL_32:
        LOBYTE(v21) = 1;
        WPP_RECORDER_AND_TRACE_SF_d(
          (_DWORD)AttachedDevice,
          v19,
          (_DWORD)v21,
          a1->IfrLog,
          2,
          10,
          v82,
          (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
          v85);
        goto LABEL_119;
      }
      RtlInitUnicodeString(&DestinationString, L"KeyLength");
      EncryptionKeySize = v3->EncryptionKeySize;
      v24 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &EncryptionKeySize, 4u);
      v4 = v24;
      if ( v24 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v24;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 130;
        goto LABEL_40;
      }
      RtlInitUnicodeString(&DestinationString, L"ERand");
      v25 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 0xBu, &v3->Rand, 8u);
      v4 = v25;
      if ( v25 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v25;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 131;
        goto LABEL_40;
      }
      RtlInitUnicodeString(&DestinationString, L"EDIV");
      EncryptionKeySize = v3->EDIV;
      v26 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &EncryptionKeySize, 4u);
      v4 = v26;
      if ( v26 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v26;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 132;
        goto LABEL_40;
      }
    }
    if ( (v3->Flag & 4) != 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"IRK");
      v27 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, v3->IRK, 0x10u);
      v4 = v27;
      if ( v27 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v27;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 133;
        goto LABEL_40;
      }
      AddressInformation = v3->AddressInformation;
      RtlInitUnicodeString(&DestinationString, L"Address");
      v28 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 0xBu, &AddressInformation, 8u);
      v4 = v28;
      if ( v28 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v28;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 134;
        goto LABEL_40;
      }
      EncryptionKeySize = v3->AddressInformationType;
      RtlInitUnicodeString(&DestinationString, L"AddressType");
      v29 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &EncryptionKeySize, 4u);
      v4 = v29;
      if ( v29 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v29;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 135;
        goto LABEL_40;
      }
    }
    if ( (v3->Flag & 0x10) != 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"CSRKInbound");
      v30 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, v3->InboundCSRK, 0x10u);
      v4 = v30;
      if ( v30 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v30;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 136;
        goto LABEL_40;
      }
      RtlInitUnicodeString(&DestinationString, L"InboundSignCounter");
      v31 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 0xBu, &v3->InboundSignCounter, 8u);
      v4 = v31;
      if ( v31 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v31;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 137;
        goto LABEL_40;
      }
    }
    if ( (v3->Flag & 0x100) != 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"CSRK");
      v32 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, v3->OutboundCSRK, 0x10u);
      v4 = v32;
      if ( v32 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v32;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 138;
        goto LABEL_40;
      }
      RtlInitUnicodeString(&DestinationString, L"OutboundSignCounter");
      v33 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &v3->OutboundSignCounter, 4u);
      v4 = v33;
      if ( v33 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v85 = v33;
        v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v82 = 139;
        goto LABEL_40;
      }
    }
    if ( (v3->Flag & 0x80u) == 0 )
    {
      if ( (v3->Flag & 0x40) == 0 )
      {
LABEL_114:
        EncryptionKeySize = v3->AuthReq;
        RtlInitUnicodeString(&DestinationString, L"AuthReq");
        v36 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &EncryptionKeySize, 4u);
        v4 = v36;
        if ( v36 < 0 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
            || (LOBYTE(v37) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          {
            LOBYTE(v37) = 0;
          }
          WPP_RECORDER_AND_TRACE_SF_Sd(
            WPP_GLOBAL_Control->AttachedDevice,
            v37,
            (unsigned int)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
            a1->IfrLog,
            2,
            10,
            141,
            (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
            (__int64)L"AuthReq",
            v36);
        }
        goto LABEL_119;
      }
      v34 = 1;
    }
    else
    {
      v34 = 0;
    }
    EncryptionKeySize = v34;
    RtlInitUnicodeString(&DestinationString, L"CEntralIRKStatus");
    v35 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &EncryptionKeySize, 4u);
    v4 = v35;
    if ( v35 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      v85 = v35;
      v21 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
      v82 = 140;
      goto LABEL_40;
    }
    goto LABEL_114;
  }
LABEL_119:
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( v14 && v4 >= 0 )
    goto LABEL_126;
  if ( !(unsigned int)BthOpenKey(a1->Hci->DevExt->LinkKeysHandle, v95, &KeyHandle) )
  {
    ZwDeleteKey(KeyHandle);
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  memset(&a1->SmpDevInfo, 0, sizeof(a1->SmpDevInfo));
  if ( v4 >= 0 )
  {
LABEL_126:
    if ( v3 )
    {
      v39 = v3->Flag;
      a1->SmpDevInfo.AuthReq = v3->AuthReq;
      a1->SmpDevInfo.IOCapability = v3->IOCapability;
      LTK = a1->SmpDevInfo.LTK;
      if ( (v39 & 1) != 0 )
      {
        v41 = v3->LTK;
        *(_OWORD *)LTK = *(_OWORD *)v3->LTK;
        a1->SmpDevInfo.EncryptionKeySize = v3->EncryptionKeySize;
        a1->SmpDevInfo.EDIV = v3->EDIV;
        a1->SmpDevInfo.Rand = v3->Rand;
        a1->SmpDevInfo.Flag |= v39 & 0x1003;
        v42 = 16;
        do
        {
          *v41++ = 0;
          --v42;
        }
        while ( v42 );
        goto LABEL_135;
      }
    }
    else
    {
      v39 = 0;
      LTK = a1->SmpDevInfo.LTK;
    }
    v43 = 16;
    do
    {
      *LTK++ = 0;
      --v43;
    }
    while ( v43 );
    a1->SmpDevInfo.Flag &= 0xFFFFEFFC;
    a1->SmpDevInfo.EncryptionKeySize = 0;
    a1->SmpDevInfo.EDIV = 0;
    a1->SmpDevInfo.Rand = 0;
LABEL_135:
    v44 = a1->SmpDevInfo.Flag;
    IRK = a1->SmpDevInfo.IRK;
    if ( (v39 & 4) != 0 )
    {
      v46 = v3->IRK;
      *(_OWORD *)IRK = *(_OWORD *)v3->IRK;
      a1->SmpDevInfo.AddressInformation = v3->AddressInformation;
      a1->SmpDevInfo.AddressInformationType = v3->AddressInformationType;
      a1->SmpDevInfo.Flag = v44 | v39 & 0xC;
      v47 = 16;
      do
      {
        *v46++ = 0;
        --v47;
      }
      while ( v47 );
    }
    else
    {
      v48 = 16;
      do
      {
        *IRK++ = 0;
        --v48;
      }
      while ( v48 );
      a1->SmpDevInfo.Flag &= 0xFFFFFFF3;
      a1->SmpDevInfo.AddressInformation = 0;
      a1->SmpDevInfo.AddressInformationType = 0;
    }
    v49 = a1->SmpDevInfo.Flag;
    InboundCSRK = a1->SmpDevInfo.InboundCSRK;
    if ( (v39 & 0x10) != 0 )
    {
      v51 = v3->InboundCSRK;
      *(_OWORD *)InboundCSRK = *(_OWORD *)v3->InboundCSRK;
      a1->SmpDevInfo.InboundSignCounter = v3->InboundSignCounter;
      v52 = 16;
      a1->SmpDevInfo.Flag = v39 & 0x10 | v49;
      do
      {
        *v51++ = 0;
        --v52;
      }
      while ( v52 );
    }
    else
    {
      v53 = 16;
      do
      {
        *InboundCSRK++ = 0;
        --v53;
      }
      while ( v53 );
      a1->SmpDevInfo.Flag &= ~0x10u;
      a1->SmpDevInfo.InboundSignCounter = -1;
    }
    v54 = a1->SmpDevInfo.Flag;
    OutboundCSRK = a1->SmpDevInfo.OutboundCSRK;
    if ( (v39 & 0x100) != 0 )
    {
      v56 = v3->OutboundCSRK;
      *(_OWORD *)OutboundCSRK = *(_OWORD *)v3->OutboundCSRK;
      a1->SmpDevInfo.OutboundSignCounter = v3->OutboundSignCounter;
      a1->SmpDevInfo.Flag = v54 | v39 & 0x100;
      do
      {
        *v56++ = 0;
        --v18;
      }
      while ( v18 );
      v57 = a1->SmpDevInfo.Flag;
    }
    else
    {
      do
      {
        *OutboundCSRK++ = 0;
        --v18;
      }
      while ( v18 );
      v57 = a1->SmpDevInfo.Flag & 0xFFFFFEFF;
      a1->SmpDevInfo.OutboundSignCounter = 0;
    }
    v58 = v57 & 0xFFFFFFBF;
    v59 = v57 | 0x40;
    if ( (v39 & 0x40) == 0 )
      v59 = v58;
    v60 = v59;
    v61 = v59 | 0x200;
    v62 = v60 & 0xFFFFFDFF;
    if ( (v39 & 0x200) == 0 )
      v61 = v62;
    v63 = v61;
    v64 = v61 | 0x800;
    v65 = v63 & 0xFFFFF7FF;
    if ( (v39 & 0x800) == 0 )
      v64 = v65;
    v66 = v64;
    v67 = v64 | 0x2000;
    v68 = v66 & 0xFFFFDFFF;
    if ( (v39 & 0x2000) == 0 )
      v67 = v68;
    v38 = v67 & 0xFFFF7FDF;
    a1->SmpDevInfo.Flag = v38;
  }
  if ( !v14 || v4 < 0 )
    goto LABEL_207;
  if ( v10 )
  {
    v69 = ((!v86 << 17) + 0x8000) | 0x30000;
    if ( (a1->DeviceInfo.flags & 0x8000) == 0 )
      goto LABEL_177;
    LEOriginalAddressType = 0;
    if ( a1->LEOriginalAddressType != 0xFF )
      LEOriginalAddressType = a1->LEOriginalAddressType;
    if ( LEOriginalAddressType == 1 && (a1->DeviceInfo.address & 0xC00000000000LL) == 0x400000000000LL )
    {
      if ( (a1->SmpDevInfo.Flag & 4) == 0 )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
          || (LOBYTE(v38) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
        {
          LOBYTE(v38) = 0;
        }
        v71 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        LOBYTE(v71) = 1;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v38,
          (_DWORD)v71,
          a1->IfrLog,
          3,
          10,
          142,
          (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
      }
    }
    else
    {
LABEL_177:
      if ( (a1->SmpDevInfo.Flag & 0x100C) != 0x100C )
      {
LABEL_179:
        v72 = (v3->Flag & 0x400) != 0 || (HCI_DibGetFlags(a1) & 0x10000000) != 0;
        if ( !SmpDib_IsPairedWithMitmProtection(a1, v72, 0) )
        {
          if ( !v91 || (v3->Flag & 0x1000) == 0 || (HCI_DibGetFlags(v91) & 0x400) == 0 )
            goto LABEL_195;
          LOBYTE(v38) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
          v73 = WPP_GLOBAL_Control->DeviceType;
          if ( (_BYTE)v38 || v73 )
          {
            LOBYTE(v39) = v73 != 0;
            WPP_RECORDER_AND_TRACE_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              v38,
              v39,
              a1->IfrLog,
              5,
              10,
              143,
              (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
          }
        }
        v69 |= 0x40000u;
LABEL_195:
        v74 = v69 | 0x10000000;
        if ( !v72 )
          v74 = v69;
        if ( (v3->Flag & 0x4000) != 0 )
          v74 |= 0x40000000u;
        goto LABEL_200;
      }
    }
    v69 = ((!v86 << 17) + 0x8000) | 0xB0000;
    goto LABEL_179;
  }
  v74 = (!v86 << 17) + 0x8000;
LABEL_200:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v38) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(v38) = 0;
  v75 = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)v38 || v75 )
  {
    LOBYTE(v39) = v75 != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v38,
      v39,
      a1->IfrLog,
      5,
      10,
      144,
      (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
      v74);
  }
  HCI_DibSetFlags(a1, v74, 1u);
  SMPDib_PopulateCompatFlags(a1);
LABEL_207:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v6 = 0;
  v76 = WPP_GLOBAL_Control->DeviceType;
  if ( v6 || v76 )
  {
    v77 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
    LOBYTE(v77) = v6;
    LOBYTE(v39) = v76 != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v77,
      v39,
      a1->IfrLog,
      5,
      10,
      145,
      (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1401fb804  mov     [rsp-8+arg_18], rbx
0x1401fb809  push    rbp
0x1401fb80a  push    rsi
0x1401fb80b  push    rdi
0x1401fb80c  push    r12
0x1401fb80e  push    r13
0x1401fb810  push    r14
0x1401fb812  push    r15
0x1401fb814  lea     rbp, [rsp-27h]
0x1401fb819  sub     rsp, 0E0h
0x1401fb820  mov     rax, cs:__security_cookie
0x1401fb827  xor     rax, rsp
0x1401fb82a  mov     [rbp+57h+var_38], rax
0x1401fb82e  xorps   xmm0, xmm0
0x1401fb831  mov     [rbp+57h+var_80], rdx
0x1401fb835  xor     eax, eax
0x1401fb837  mov     r12, r8
0x1401fb83a  xor     r9d, r9d
0x1401fb83d  mov     [rbp+57h+var_40], rax
0x1401fb841  mov     [rbp+57h+KeyHandle], r9
0x1401fb845  mov     r15d, r9d
0x1401fb848  mov     [rbp+57h+var_A0], r9d
0x1401fb84c  mov     rbx, rcx
0x1401fb84f  mov     [rbp+57h+var_88], r9
0x1401fb853  movups  xmmword ptr [rbp+57h+SourceString], xmm0
0x1401fb857  movups  [rbp+57h+var_60], xmm0
0x1401fb85b  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1401fb85f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1401fb863  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401fb86a  lea     edi, [rax+1]
0x1401fb86d  bt      dword ptr [rcx+2Ch], 9
0x1401fb872  jnb     short loc_1401FB87D
0x1401fb874  cmp     byte ptr [rcx+29h], 5
0x1401fb878  mov     dl, dil
0x1401fb87b  jnb     short loc_1401FB880
0x1401fb87d  mov     dl, r9b
0x1401fb880  movzx   eax, word ptr [rcx+48h]
0x1401fb884  lea     r10, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x1401fb88b  test    ax, ax
0x1401fb88e  setnz   r8b
0x1401fb892  test    dl, dl
0x1401fb894  jnz     short loc_1401FB89B
0x1401fb896  test    ax, ax
0x1401fb899  jz      short loc_1401FB8C4
0x1401fb89b  mov     r9, [rbx+838h]
0x1401fb8a2  mov     rcx, [rcx+18h]
0x1401fb8a6  mov     [rsp+110h+var_D8], r10
0x1401fb8ab  mov     [rsp+110h+var_E0], 7Eh ; '~'
0x1401fb8b2  mov     [rsp+110h+DataSize], 0Ah
0x1401fb8ba  mov     byte ptr [rsp+110h+Data], 5
0x1401fb8bf  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fb8c4  lea     rdx, [rbx+20h]; unsigned __int64 *
0x1401fb8c8  lea     rcx, [rbp+57h+SourceString]; SourceString
0x1401fb8cc  call    ?DS_Init@@YAXPEAU_DEVICE_STRING@@PEB_K@Z; DS_Init(_DEVICE_STRING *,unsigned __int64 const *)
0x1401fb8d1  xor     r9d, r9d
0x1401fb8d4  test    r12, r12
0x1401fb8d7  jnz     short loc_1401FB8E1
0x1401fb8d9  mov     dl, r9b
0x1401fb8dc  mov     r13b, r9b
0x1401fb8df  jmp     short loc_1401FB91D
0x1401fb8e1  mov     esi, [r12]
0x1401fb8e5  mov     ecx, esi
0x1401fb8e7  and     ecx, 400h
0x1401fb8ed  setnz   dl
0x1401fb8f0  mov     [rbp+57h+var_B0], dl
0x1401fb8f3  test    ecx, ecx
0x1401fb8f5  jz      short loc_1401FB900
0x1401fb8f7  mov     r13d, esi
0x1401fb8fa  shr     r13d, 10h
0x1401fb8fe  jmp     short loc_1401FB903
0x1401fb900  mov     r13b, sil
0x1401fb903  and     r13b, dil
0x1401fb906  test    ecx, ecx
0x1401fb908  jz      short loc_1401FB912
0x1401fb90a  shr     esi, 10h
0x1401fb90d  and     sil, dil
0x1401fb910  jmp     short loc_1401FB923
0x1401fb912  test    esi, 0FFFEFFFFh
0x1401fb918  mov     sil, dil
0x1401fb91b  jnz     short loc_1401FB920
0x1401fb91d  mov     sil, r9b
0x1401fb920  mov     [rbp+57h+var_B0], dl
0x1401fb923  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401fb92a  bt      dword ptr [r10+2Ch], 9
0x1401fb930  jnb     short loc_1401FB93C
0x1401fb932  cmp     byte ptr [r10+29h], 5
0x1401fb937  mov     r11b, dil
0x1401fb93a  jnb     short loc_1401FB93F
0x1401fb93c  mov     r11b, r9b
0x1401fb93f  movzx   eax, word ptr [r10+48h]
0x1401fb944  test    ax, ax
0x1401fb947  setnz   r8b
0x1401fb94b  test    r11b, r11b
0x1401fb94e  jnz     short loc_1401FB955
0x1401fb950  test    ax, ax
0x1401fb953  jz      short loc_1401FB98E
0x1401fb955  movzx   edx, dl
0x1401fb958  test    r12, r12
0x1401fb95b  movzx   eax, sil
0x1401fb95f  setnz   r9b
0x1401fb963  movzx   ecx, r13b
0x1401fb967  mov     [rsp+110h+var_B8], r9d
0x1401fb96c  mov     r9, [rbx+838h]
0x1401fb973  mov     [rsp+110h+var_C0], eax
0x1401fb977  mov     [rsp+110h+var_C8], ecx
0x1401fb97b  mov     rcx, [r10+18h]
0x1401fb97f  mov     dword ptr [rsp+110h+var_D0], edx
0x1401fb983  mov     dl, r11b
0x1401fb986  call    WPP_RECORDER_AND_TRACE_SF_llll
0x1401fb98b  xor     r9d, r9d
0x1401fb98e  mov     r14d, 10h
0x1401fb994  test    sil, sil
0x1401fb997  jz      loc_1401FC1BB
0x1401fb99d  mov     rcx, [rbx+378h]; struct HCI_INTERFACE *
0x1401fb9a4  lea     rdx, [rbp+57h+KeyHandle]; void **
0x1401fb9a8  xor     r8d, r8d; unsigned __int8
0x1401fb9ab  call    ?HCI_GetPersonalDevicesKey@@YAJPEAUHCI_INTERFACE@@PEAPEAXE@Z; HCI_GetPersonalDevicesKey(HCI_INTERFACE *,void * *,uchar)
0x1401fb9b0  test    eax, eax
0x1401fb9b2  js      short loc_1401FB9DC
0x1401fb9b4  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401fb9b8  lea     rdx, [rbp+57h+ValueName.Buffer]; ValueName
0x1401fb9bc  call    cs:__imp_ZwDeleteValueKey
0x1401fb9c3  nop     dword ptr [rax+rax+00h]
0x1401fb9c8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1401fb9cc  call    cs:__imp_ZwClose
0x1401fb9d3  nop     dword ptr [rax+rax+00h]
0x1401fb9d8  mov     [rbp+57h+KeyHandle], r15
0x1401fb9dc  mov     rax, [rbx+378h]
0x1401fb9e3  lea     r8, [rbp+57h+KeyHandle]
0x1401fb9e7  mov     rdx, [rbp+57h+var_40]
0x1401fb9eb  mov     rcx, [rax+4A8h]
0x1401fb9f2  mov     rcx, [rcx+0D8h]
0x1401fb9f9  call    BthCreateKeySdEnforced
0x1401fb9fe  mov     r15d, eax
0x1401fba01  test    eax, eax
0x1401fba03  jns     short loc_1401FBA5F
0x1401fba05  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401fba0c  test    dword ptr [rax+2Ch], 200h
0x1401fba13  jz      short loc_1401FBA20
0x1401fba15  cmp     byte ptr [rax+29h], 2
0x1401fba19  jb      short loc_1401FBA20
0x1401fba1b  mov     dl, dil
0x1401fba1e  jmp     short loc_1401FBA22
0x1401fba20  xor     dl, dl
0x1401fba22  mov     rcx, [rax+18h]
0x1401fba26  lea     r8, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x1401fba2d  mov     dword ptr [rsp+110h+var_D0], r15d
0x1401fba32  mov     [rsp+110h+var_D8], r8
0x1401fba37  mov     [rsp+110h+var_E0], 80h
0x1401fba3e  mov     r9, [rbx+838h]
0x1401fba45  mov     r8b, dil
0x1401fba48  mov     [rsp+110h+DataSize], 0Ah
0x1401fba50  mov     byte ptr [rsp+110h+Data], 2
0x1401fba55  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401fba5a  jmp     loc_1401FC1B8
0x1401fba5f  mov     eax, [r12]
0x1401fba63  test    dil, al
0x1401fba66  jz      loc_1401FBC91
0x1401fba6c  lea     rdx, aLtk; "LTK"
0x1401fba73  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401fba77  call    cs:__imp_RtlInitUnicodeString
0x1401fba7e  nop     dword ptr [rax+rax+00h]
0x1401fba83  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401fba87  lea     rax, [r12+4]
0x1401fba8c  mov     [rsp+110h+DataSize], r14d; DataSize
0x1401fba91  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1401fba95  mov     r9d, 3; Type
0x1401fba9b  mov     [rsp+110h+Data], rax; Data
0x1401fbaa0  xor     r8d, r8d; TitleIndex
0x1401fbaa3  call    cs:__imp_ZwSetValueKey
0x1401fbaaa  nop     dword ptr [rax+rax+00h]
0x1401fbaaf  mov     r15d, eax
0x1401fbab2  test    eax, eax
0x1401fbab4  jns     short loc_1401FBAF3
0x1401fbab6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401fbabd  test    dword ptr [rcx+2Ch], 200h
0x1401fbac4  jz      short loc_1401FBAD1
0x1401fbac6  cmp     byte ptr [rcx+29h], 2
0x1401fbaca  jb      short loc_1401FBAD1
0x1401fbacc  mov     dl, dil
0x1401fbacf  jmp     short loc_1401FBAD3
0x1401fbad1  xor     dl, dl
0x1401fbad3  mov     dword ptr [rsp+110h+var_D0], eax
0x1401fbad7  lea     r8, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x1401fbade  mov     [rsp+110h+var_D8], r8
0x1401fbae3  mov     [rsp+110h+var_E0], 81h
0x1401fbaea  mov     rcx, [rcx+18h]
0x1401fbaee  jmp     loc_1401FBA3E
0x1401fbaf3  lea     rdx, aKeylength; "KeyLength"
0x1401fbafa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401fbafe  call    cs:__imp_RtlInitUnicodeString
0x1401fbb05  nop     dword ptr [rax+rax+00h]
0x1401fbb0a  movzx   eax, byte ptr [r12+14h]
0x1401fbb10  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1401fbb14  mov     ecx, 4
0x1401fbb19  mov     [rbp+57h+var_A0], eax
0x1401fbb1c  mov     [rsp+110h+DataSize], ecx; DataSize
0x1401fbb20  lea     rax, [rbp+57h+var_A0]
0x1401fbb24  mov     r9d, ecx; Type
0x1401fbb27  mov     [rsp+110h+Data], rax; Data
0x1401fbb2c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401fbb30  xor     r8d, r8d; TitleIndex
0x1401fbb33  call    cs:__imp_ZwSetValueKey
0x1401fbb3a  nop     dword ptr [rax+rax+00h]
0x1401fbb3f  mov     r15d, eax
0x1401fbb42  test    eax, eax
0x1401fbb44  jns     short loc_1401FBB7F
0x1401fbb46  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401fbb4d  test    dword ptr [rcx+2Ch], 200h
0x1401fbb54  jz      short loc_1401FBB61
0x1401fbb56  cmp     byte ptr [rcx+29h], 2
0x1401fbb5a  jb      short loc_1401FBB61
0x1401fbb5c  mov     dl, dil
0x1401fbb5f  jmp     short loc_1401FBB63
0x1401fbb61  xor     dl, dl
0x1401fbb63  mov     dword ptr [rsp+110h+var_D0], eax
0x1401fbb67  lea     r8, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x1401fbb6e  mov     [rsp+110h+var_D8], r8
0x1401fbb73  mov     [rsp+110h+var_E0], 82h
0x1401fbb7a  jmp     loc_1401FBAEA
0x1401fbb7f  lea     rdx, aErand; "ERand"
0x1401fbb86  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401fbb8a  call    cs:__imp_RtlInitUnicodeString
0x1401fbb91  nop     dword ptr [rax+rax+00h]
0x1401fbb96  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401fbb9a  lea     rax, [r12+18h]
0x1401fbb9f  mov     [rsp+110h+DataSize], 8; DataSize
0x1401fbba7  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1401fbbab  mov     r9d, 0Bh; Type
0x1401fbbb1  mov     [rsp+110h+Data], rax; Data
0x1401fbbb6  xor     r8d, r8d; TitleIndex
0x1401fbbb9  call    cs:__imp_ZwSetValueKey
0x1401fbbc0  nop     dword ptr [rax+rax+00h]
0x1401fbbc5  mov     r15d, eax
0x1401fbbc8  test    eax, eax
0x1401fbbca  jns     short loc_1401FBC05
0x1401fbbcc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401fbbd3  test    dword ptr [rcx+2Ch], 200h
0x1401fbbda  jz      short loc_1401FBBE7
0x1401fbbdc  cmp     byte ptr [rcx+29h], 2
0x1401fbbe0  jb      short loc_1401FBBE7
0x1401fbbe2  mov     dl, dil
0x1401fbbe5  jmp     short loc_1401FBBE9
0x1401fbbe7  xor     dl, dl
0x1401fbbe9  mov     dword ptr [rsp+110h+var_D0], eax
0x1401fbbed  lea     r8, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x1401fbbf4  mov     [rsp+110h+var_D8], r8
0x1401fbbf9  mov     [rsp+110h+var_E0], 83h
0x1401fbc00  jmp     loc_1401FBAEA
0x1401fbc05  lea     rdx, aEdiv; "EDIV"
0x1401fbc0c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401fbc10  call    cs:__imp_RtlInitUnicodeString
0x1401fbc17  nop     dword ptr [rax+rax+00h]
0x1401fbc1c  movzx   eax, word ptr [r12+20h]
0x1401fbc22  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1401fbc26  mov     ecx, 4
0x1401fbc2b  mov     [rbp+57h+var_A0], eax
0x1401fbc2e  mov     [rsp+110h+DataSize], ecx; DataSize
0x1401fbc32  lea     rax, [rbp+57h+var_A0]
0x1401fbc36  mov     r9d, ecx; Type
0x1401fbc39  mov     [rsp+110h+Data], rax; Data
0x1401fbc3e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401fbc42  xor     r8d, r8d; TitleIndex
0x1401fbc45  call    cs:__imp_ZwSetValueKey
0x1401fbc4c  nop     dword ptr [rax+rax+00h]
0x1401fbc51  mov     r15d, eax
0x1401fbc54  test    eax, eax
0x1401fbc56  jns     short loc_1401FBC91
0x1401fbc58  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401fbc5f  test    dword ptr [rcx+2Ch], 200h
0x1401fbc66  jz      short loc_1401FBC73
0x1401fbc68  cmp     byte ptr [rcx+29h], 2
0x1401fbc6c  jb      short loc_1401FBC73
0x1401fbc6e  mov     dl, dil
0x1401fbc71  jmp     short loc_1401FBC75
0x1401fbc73  xor     dl, dl
0x1401fbc75  mov     dword ptr [rsp+110h+var_D0], eax
0x1401fbc79  lea     r8, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x1401fbc80  mov     [rsp+110h+var_D8], r8
0x1401fbc85  mov     [rsp+110h+var_E0], 84h
0x1401fbc8c  jmp     loc_1401FBAEA
0x1401fbc91  mov     eax, [r12]
0x1401fbc95  test    al, 4
0x1401fbc97  jz      loc_1401FBE3A
0x1401fbc9d  lea     rdx, aIrk; "IRK"
0x1401fbca4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401fbca8  call    cs:__imp_RtlInitUnicodeString
0x1401fbcaf  nop     dword ptr [rax+rax+00h]
0x1401fbcb4  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401fbcb8  lea     rax, [r12+22h]
0x1401fbcbd  mov     [rsp+110h+DataSize], r14d; DataSize
0x1401fbcc2  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1401fbcc6  mov     r9d, 3; Type
0x1401fbccc  mov     [rsp+110h+Data], rax; Data
0x1401fbcd1  xor     r8d, r8d; TitleIndex
0x1401fbcd4  call    cs:__imp_ZwSetValueKey
0x1401fbcdb  nop     dword ptr [rax+rax+00h]
0x1401fbce0  mov     r15d, eax
0x1401fbce3  test    eax, eax
0x1401fbce5  jns     short loc_1401FBD20
  ... truncated ...
```
