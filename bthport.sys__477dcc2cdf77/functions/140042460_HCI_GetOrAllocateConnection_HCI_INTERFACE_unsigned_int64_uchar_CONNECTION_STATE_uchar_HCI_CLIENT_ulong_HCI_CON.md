# HCI_GetOrAllocateConnection(HCI_INTERFACE *,unsigned __int64 *,uchar *,_CONNECTION_STATE,uchar *,HCI_CLIENT *,ulong,_HCI_CONNECTION * *,_HCI_CXN_ACTION *,_GUID *)

- ea: `0x140042460`
- end: `0x14004379d`
- name: `?HCI_GetOrAllocateConnection@@YAJPEAUHCI_INTERFACE@@PEA_KPEAEW4_CONNECTION_STATE@@2PEAUHCI_CLIENT@@KPEAPEAU_HCI_CONNECTION@@PEAW4_HCI_CXN_ACTION@@PEAU_GUID@@@Z`
- size: `4925`
- prototype: `__int64 __usercall@<rax>(struct HCI_INTERFACE *@<rcx>, unsigned __int64 *@<rdx>, unsigned __int8 *@<r8>, enum _CONNECTION_STATE@<r9d>, unsigned __int8 *, struct HCI_CLIENT *, unsigned int, struct _HCI_CONNECTION **, enum _HCI_CXN_ACTION *, struct _GUID *)`
- caller_count: `3`
- callee_count: `36`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140039cc0`
- `0x140043a60`
- `0x140110cd0`

## callees

- `0x14000113c`
- `0x1400014a4`
- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x140005c04`
- `0x140006f50`
- `0x140006ff0`
- `0x14000764c`
- `0x14000bdb8`
- `0x140013820`
- `0x14001c148`
- `0x14001fddc`
- `0x140036b54`
- `0x14003a1ec`
- `0x14003d664`
- `0x14003fe84`
- `0x140040834`
- `0x140041e7c`
- `0x140042460`
- `0x140049914`
- `0x140049a48`
- `0x140049b2c`
- `0x14004b924`
- `0x14004c6d8`
- `0x14004caec`
- `0x14004ce74`
- `0x14004cfb8`
- `0x14004d154`
- `0x1400535e8`
- `0x140065b9c`
- `0x14015ce38`
- `0x140161a44`
- `0x140161d7c`
- `0x140165540`
- `0x140165940`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140042bf6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140042bf6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140042781`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140042781`
- `ntoskrnl!KeInitializeDpc` at `0x140042752`
- `ntoskrnl!KeInitializeDpc` at `0x140042752`
- `ntoskrnl!KeInitializeTimerEx` at `0x140042735`
- `ntoskrnl!KeInitializeTimerEx` at `0x140042735`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400436a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400436a9`
- `ntoskrnl!ExAllocatePool2` at `0x140042708`
- `ntoskrnl!ExAllocatePool2` at `0x140042708`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140042a19`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140042dcb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140042a19`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140042dcb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400429eb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140042dae`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400429eb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140042dae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004258a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004258a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140043691`
- `ntoskrnl!KeReleaseSpinLock` at `0x140043691`

## pseudocode

```c
__int64 __fastcall HCI_GetOrAllocateConnection(
        struct HCI_INTERFACE *a1,
        unsigned __int64 *a2,
        unsigned __int8 *a3,
        enum _CONNECTION_STATE a4,
        unsigned __int8 *a5,
        struct HCI_CLIENT *a6,
        unsigned int a7,
        struct _HCI_CONNECTION **a8,
        enum _HCI_CXN_ACTION *a9,
        struct _GUID *a10)
{
  char v11; // di
  __int16 DeviceType; // ax
  unsigned int v13; // r12d
  unsigned int CxnFlags; // esi
  unsigned int v15; // esi
  _LIST_ENTRY *p_HciCxnPending; // r12
  struct _HCI_CONNECTION *ConnectionLocked; // rsi
  DEVICE_INFO_BLOCK *Dib; // rcx
  char LEOriginalAddressType; // al
  char v20; // cl
  unsigned __int64 *p_address; // rdx
  unsigned __int8 *v22; // r8
  char v23; // al
  int v24; // r14d
  struct HCI_INTERFACE *v25; // rbx
  struct DEVICE_INFO_BLOCK *v26; // r13
  unsigned __int8 v27; // bl
  int v28; // edx
  unsigned int v29; // eax
  _HCI_CONNECTION *Pool2; // rax
  struct _HCI_CONNECTION *v31; // rsi
  NTSTATUS v32; // eax
  int v33; // r8d
  int v34; // edx
  HciState ControllerState; // r8d
  enum _HCI_PHY_TYPE v36; // si
  _LIST_ENTRY *v37; // r12
  enum _CONNECTION_STATE v38; // esi
  int v39; // edx
  int v40; // r8d
  _LIST_ENTRY **p_Blink; // rdx
  _LIST_ENTRY *v42; // rcx
  _LIST_ENTRY *v43; // rax
  int v44; // ecx
  struct _HCI_CONNECTION *v45; // r14
  int v46; // edx
  _LIST_ENTRY *v47; // rcx
  _LIST_ENTRY *v48; // rax
  struct _HCI_CONNECTION *v49; // r12
  int v50; // esi
  enum _HCI_CXN_ACTION *v51; // r8
  struct _HCI_CONNECTION *v52; // rsi
  struct HCI_CLIENT *i; // rax
  _HCI_CONNECTION *v54; // r12
  int v55; // edx
  _LIST_ENTRY *v56; // r8
  enum _HCI_CXN_ACTION *v57; // r8
  struct DEVICE_INFO_BLOCK *v58; // r8
  char v59; // r11
  __int16 v60; // ax
  int v61; // r8d
  _LIST_ENTRY *p_ListEntry; // rax
  _LIST_ENTRY *Flink; // rdx
  _LIST_ENTRY *Blink; // rcx
  _LIST_ENTRY *v65; // rdx
  int State; // ecx
  int v67; // ecx
  int v68; // ecx
  int v69; // ecx
  int v70; // ecx
  int v71; // ecx
  int v72; // ecx
  int v73; // r8d
  _HCI_PHY_TYPE PhyType; // al
  _MITM_PROTECTION_TYPE MitmProtectionType; // eax
  PDEVICE_OBJECT v76; // rcx
  enum _HCI_PHY_TYPE v77; // r9
  bool IsDebugAllowed; // al
  int v79; // edx
  int v80; // r8d
  int v81; // ecx
  int v82; // r8d
  int v83; // r9d
  DEVICE_EXTENSION *DevExt; // rax
  int v85; // edx
  int v86; // r8d
  _HCI_PHY_TYPE v87; // cl
  _HCI_AUTHENTICATION_STATE Authentication; // eax
  bool v89; // al
  int v90; // ecx
  int v91; // r8d
  int v92; // r9d
  struct _GUID *v93; // rax
  __int16 v94; // ax
  int v95; // edx
  char MinimumEncryptionKeySizePolicy; // bl
  int v97; // r8d
  int v98; // edx
  int v99; // ecx
  int v100; // r8d
  unsigned int EncryptionKeySize; // r8d
  unsigned int v102; // r9d
  _LIST_ENTRY *v103; // rax
  _LIST_ENTRY *v104; // rcx
  int v105; // r8d
  __int16 v106; // ax
  struct _HCI_CONNECTION *v107; // rdx
  char v108; // r11
  int RemlockSize; // [rsp+20h] [rbp-F0h]
  int RemlockSizea; // [rsp+20h] [rbp-F0h]
  int RemlockSizeb; // [rsp+20h] [rbp-F0h]
  int RemlockSizec; // [rsp+20h] [rbp-F0h]
  int v114; // [rsp+28h] [rbp-E8h]
  int v115; // [rsp+28h] [rbp-E8h]
  int v116; // [rsp+28h] [rbp-E8h]
  int v117; // [rsp+28h] [rbp-E8h]
  int v118; // [rsp+30h] [rbp-E0h]
  __int16 v119; // [rsp+30h] [rbp-E0h]
  int v120; // [rsp+38h] [rbp-D8h]
  char v121; // [rsp+40h] [rbp-D0h]
  char v122; // [rsp+90h] [rbp-80h]
  __int64 p_HciConnectionSessionId; // [rsp+98h] [rbp-78h] BYREF
  char v124; // [rsp+A0h] [rbp-70h] BYREF
  char v125; // [rsp+A1h] [rbp-6Fh]
  KIRQL NewIrql; // [rsp+A2h] [rbp-6Eh]
  enum _HCI_PHY_TYPE v127[4]; // [rsp+A4h] [rbp-6Ch]
  enum _CONNECTION_STATE v128; // [rsp+A8h] [rbp-68h]
  enum _HCI_CXN_ACTION *v129; // [rsp+B0h] [rbp-60h]
  unsigned __int64 *v130; // [rsp+B8h] [rbp-58h]
  struct _GUID *v131; // [rsp+C0h] [rbp-50h] BYREF
  struct _HCI_CONNECTION *v132; // [rsp+C8h] [rbp-48h]
  PVOID P; // [rsp+D0h] [rbp-40h]
  __int64 v134; // [rsp+D8h] [rbp-38h] BYREF
  struct _HCI_CONNECTION **v135; // [rsp+E0h] [rbp-30h]
  _GUID *p_DeviceExtensionSessionId; // [rsp+E8h] [rbp-28h] BYREF
  unsigned __int64 address; // [rsp+F0h] [rbp-20h] BYREF
  unsigned __int8 *v138; // [rsp+F8h] [rbp-18h]
  struct HCI_INTERFACE *v139; // [rsp+100h] [rbp-10h]
  PKSPIN_LOCK SpinLock; // [rsp+108h] [rbp-8h]
  struct _HCI_CONNECTION_INFO v141; // [rsp+110h] [rbp+0h] BYREF

  v135 = a8;
  v129 = a9;
  v131 = a10;
  v128 = a4;
  v138 = a3;
  v130 = a2;
  v139 = a1;
  v11 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
  {
    v13 = a7;
    LOBYTE(a3) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_qDDqDD(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a2, (_DWORD)a3, a1->IfrLog);
  }
  else
  {
    v13 = a7;
  }
  v132 = 0;
  P = 0;
  v122 = 0;
  *v135 = 0;
  *(_DWORD *)a9 = 0;
  if ( a6 )
    CxnFlags = a6->CxnFlags;
  else
    CxnFlags = v13;
  v15 = CxnFlags >> 13;
  LOBYTE(v15) = v15 & 1;
  SpinLock = &a1->HciLock;
  *(_DWORD *)v127 = v15;
  p_HciCxnPending = &a1->HciCxnPending;
  NewIrql = KeAcquireSpinLockRaiseToDpc(&a1->HciLock);
  ConnectionLocked = HCI_FindConnectionLocked(a1, &a1->HciCxnPending, v130, (enum _HCI_PHY_TYPE)v15, 1);
  if ( ConnectionLocked )
  {
    v125 = 1;
  }
  else
  {
    v125 = 0;
    ConnectionLocked = HCI_FindConnectionLocked(a1, &a1->HciCxnList, v130, v127[0], 1);
  }
  address = 0;
  v124 = 0;
  if ( ConnectionLocked )
  {
    address = ConnectionLocked->Dib->DeviceInfo.address;
    Dib = ConnectionLocked->Dib;
    if ( (Dib->DeviceInfo.flags & 0x8000) != 0 )
    {
      LEOriginalAddressType = Dib->LEOriginalAddressType;
      v20 = 0;
      if ( LEOriginalAddressType != -1 )
        v20 = LEOriginalAddressType;
    }
    else
    {
      v20 = -1;
    }
    v124 = v20;
    p_address = &address;
    v22 = (unsigned __int8 *)&v124;
  }
  else
  {
    v22 = v138;
    p_address = v130;
  }
  if ( v128 != MODE_CONNECT_REQUEST || (v23 = 1, ConnectionLocked) )
    v23 = 0;
  v24 = 0;
  v25 = a1;
  v26 = HCI_UpdateOrAllocateDibEx(a1, p_address, v22, 0, 0, a5, v23, 1, v127[0], a10, 0);
  if ( !v26 )
    goto LABEL_26;
  if ( (unsigned int)Feature_53100197__private_IsEnabledDeviceUsageNoInline()
    && !ConnectionLocked
    && (v26->DibFlags._MyVal & 0x100) != 0 )
  {
    ++v26->numCreatedForConnect;
  }
  if ( a6 )
    v29 = a6->CxnFlags | a7;
  else
    v29 = 0;
  LODWORD(p_HciConnectionSessionId) = v29;
  if ( ConnectionLocked )
  {
    v132 = ConnectionLocked;
    if ( v26 != ConnectionLocked->Dib )
      MicrosoftTelemetryAssertTriggeredMsgKM("If connection exists, DIB must be valid");
    v58 = ConnectionLocked->Dib;
    if ( v26 != v58 )
    {
      LOBYTE(v28) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(v58) = 1;
      WPP_RECORDER_AND_TRACE_SF_qi(
        WPP_GLOBAL_Control->AttachedDevice,
        v28,
        (_DWORD)v58,
        v26->IfrLog,
        2,
        2,
        68,
        (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
        (char)v26,
        (char)ConnectionLocked->Dib);
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      LOBYTE(v28) = 1;
      v59 = 0;
    }
    else
    {
      v59 = 0;
      LOBYTE(v28) = 0;
    }
    v60 = WPP_GLOBAL_Control->DeviceType;
    if ( (_BYTE)v28 || v60 )
    {
      LOBYTE(v58) = v60 != 0;
      WPP_RECORDER_AND_TRACE_SF_qLL(
        WPP_GLOBAL_Control->AttachedDevice,
        v28,
        (_DWORD)v58,
        v26->IfrLog,
        5,
        2,
        69,
        (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
        (char)ConnectionLocked,
        *((_WORD *)v130 + 2),
        *(_DWORD *)v130);
      v59 = 0;
    }
    if ( v128 != MODE_CONNECT_REQUEST )
    {
      v61 = (int)v129;
      *(_DWORD *)v129 = 1;
      if ( v125 )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
          LOBYTE(v28) = 0;
        LOBYTE(v61) = 1;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v28,
          v61,
          v26->IfrLog,
          4,
          2,
          70,
          (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
          (char)ConnectionLocked);
        p_ListEntry = &ConnectionLocked->ListEntry;
        Flink = ConnectionLocked->ListEntry.Flink;
        if ( Flink->Blink != &ConnectionLocked->ListEntry )
          goto LABEL_258;
        Blink = ConnectionLocked->ListEntry.Blink;
        if ( Blink->Flink != p_ListEntry )
          goto LABEL_258;
        Blink->Flink = Flink;
        Flink->Blink = Blink;
        v65 = v25->HciCxnList.Blink;
        if ( v65->Flink != &v25->HciCxnList )
          goto LABEL_258;
        p_ListEntry->Flink = &v25->HciCxnList;
        ConnectionLocked->ListEntry.Blink = v65;
        v65->Flink = p_ListEntry;
        v25->HciCxnList.Blink = p_ListEntry;
        KeAcquireSpinLockAtDpcLevel(&ConnectionLocked->StateLock);
        HCI_CxnSetStateLocked(ConnectionLocked, MODE_CONNECT_RESPONSE);
        KeReleaseSpinLockFromDpcLevel(&ConnectionLocked->StateLock);
      }
      else
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
          LOBYTE(v28) = 0;
        LOBYTE(v61) = 1;
        WPP_RECORDER_AND_TRACE_SF_qL(
          WPP_GLOBAL_Control->AttachedDevice,
          v28,
          v61,
          v26->IfrLog,
          4,
          2,
          71,
          (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
          (char)ConnectionLocked,
          ConnectionLocked->Info.State);
      }
      goto LABEL_83;
    }
    State = ConnectionLocked->Info.State;
    if ( State > 7 )
    {
      v68 = State - 8;
      if ( !v68 )
        goto LABEL_83;
      v69 = v68 - 1;
      if ( !v69 )
        goto LABEL_83;
      v70 = v69 - 1;
      if ( v70 )
      {
        v71 = v70 - 1;
        if ( v71 )
        {
          v72 = v71 - 1;
          if ( v72 )
          {
            if ( (unsigned int)(v72 - 1) > 1 )
              goto LABEL_83;
          }
        }
      }
    }
    else
    {
      if ( State == 7 )
        goto LABEL_83;
      if ( State )
      {
        v67 = State - 1;
        if ( v67 )
        {
          if ( (unsigned int)(v67 - 1) >= 2 )
            goto LABEL_83;
        }
      }
    }
    if ( a6 )
    {
      Hci_CxnApplyPolicyRequirementsToClientFlags(ConnectionLocked, a6);
      PhyType = ConnectionLocked->Info.PhyType;
      v59 = 0;
      if ( PhyType )
      {
        if ( PhyType == HciPhyTypeLE
          && ConnectionLocked->Info.Authentication == HCI_AUTHENTICATED
          && (a6->CxnFlags & 0x4400) != 0
          && (ConnectionLocked->Dib->DeviceInfo.flags & 0x40000) == 0 )
        {
          v24 = -1073741808;
          v76 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v28) = 0;
          v119 = 73;
          goto LABEL_139;
        }
      }
      else if ( ConnectionLocked->Info.Authentication == HCI_AUTHENTICATED && (a6->CxnFlags & 0x4400) != 0 )
      {
        MitmProtectionType = ConnectionLocked->Info.MitmProtectionType;
        if ( MitmProtectionType != MITM_PROTECTED )
        {
          if ( MitmProtectionType != MITM_PROTECTION_NOT_POSSIBLE )
          {
            *(_DWORD *)v129 = 2;
            ConnectionLocked->Info.Authentication = HCI_AUTHENTICATION_PENDING;
            goto LABEL_83;
          }
          v24 = -1073741808;
          v76 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            LOBYTE(v28) = 0;
          v119 = 72;
LABEL_139:
          LOBYTE(v73) = 1;
          WPP_RECORDER_AND_TRACE_SF_(
            v76->AttachedDevice,
            v28,
            v73,
            v26->IfrLog,
            2,
            2,
            v119,
            (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
          goto LABEL_27;
        }
      }
    }
    v77 = v127[0];
    if ( v127[0] )
    {
      v73 = p_HciConnectionSessionId;
    }
    else
    {
      if ( (v26->DeviceInfo.flags & 0x20000000) != 0 )
      {
        IsDebugAllowed = HciDebugMode::IsDebugAllowed(&v25->DebugMode);
        v59 = 0;
        if ( !IsDebugAllowed )
        {
          BthReportError_BthAddr(
            v25->DevExt,
            -1073414122,
            5u,
            0,
            0,
            (unsigned __int16)WORD2(v26->DeviceInfo.address),
            v26->DeviceInfo.address);
          LOBYTE(v79) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          LOBYTE(v80) = 1;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v79,
            v80,
            v25->IfrLog,
            2,
            2,
            74,
            (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
          if ( (unsigned int)dword_140197150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140197150, 0x400000000000LL) )
          {
            v131 = (struct _GUID *)v26->DeviceInfo.address;
            p_HciConnectionSessionId = (__int64)&ConnectionLocked->HciConnectionSessionId;
            DevExt = v25->DevExt;
            v134 = 50333696;
            p_DeviceExtensionSessionId = &DevExt->DeviceExtensionSessionId;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
              v81,
              (unsigned int)word_14018A1CA,
              v82,
              v83,
              (__int64)&v134,
              (__int64)&p_DeviceExtensionSessionId,
              (__int64)&p_HciConnectionSessionId,
              (__int64)&v131);
          }
LABEL_159:
          v24 = -1073741436;
          goto LABEL_27;
        }
        v77 = v127[0];
      }
      v73 = p_HciConnectionSessionId;
      if ( v25->SimplePairingMode == 1
        && (p_HciConnectionSessionId & 0x18) != 0
        && (v26->DeviceInfo.flags & 0x18) == 0x18
        && (v26->DeviceInfo.flags & 0x200) == 0
        && !v25->SimplePairingAllowLegacyCombinationLinkKeys )
      {
        BthReportError_BthAddr(
          v25->DevExt,
          -1073414094,
          5u,
          0,
          0,
          (unsigned __int16)WORD2(v26->DeviceInfo.address),
          v26->DeviceInfo.address);
        LOBYTE(v85) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        LOBYTE(v86) = 1;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v85,
          v86,
          v25->IfrLog,
          2,
          2,
          75,
          (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
        v24 = -1073741436;
        goto LABEL_27;
      }
    }
    if ( a6 )
    {
      v87 = ConnectionLocked->Info.PhyType;
      if ( v87 )
      {
        v28 = 0;
        if ( v87 == HciPhyTypeLE )
          v28 = 268468224;
      }
      else
      {
        v28 = 134234112;
      }
      if ( (a6->CxnFlags & 0x800) != 0 && (v28 & ConnectionLocked->Dib->DeviceInfo.flags) != v28 )
      {
        v24 = -1073741808;
        v76 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v28) = 0;
        v119 = 76;
        goto LABEL_139;
      }
    }
    if ( v77 )
    {
      if ( v77 == HciPhyTypeLE )
      {
        if ( (v73 & 0x18) != 0 && v25->DevExt->IsSmpEnabled && (ConnectionLocked->Dib->SmpDevInfo.Flag & 0x21) == 0 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
            LOBYTE(v28) = 0;
          LOBYTE(v73) = 1;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v28,
            v73,
            v26->IfrLog,
            4,
            2,
            77,
            (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
          v24 = -1073741808;
          goto LABEL_27;
        }
        if ( (v26->DeviceInfo.flags & 0x40000000) != 0 )
        {
          v89 = HciDebugMode::IsDebugAllowed(&v25->DebugMode);
          v59 = 0;
          if ( !v89 )
          {
            BthReportError_BthAddr(
              v25->DevExt,
              -1073414122,
              5u,
              0,
              0,
              (unsigned __int16)WORD2(v26->DeviceInfo.address),
              v26->DeviceInfo.address);
            if ( (unsigned int)dword_140197150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140197150, 0x400000000000LL) )
            {
              v134 = v26->DeviceInfo.address;
              p_DeviceExtensionSessionId = &ConnectionLocked->HciConnectionSessionId;
              v93 = (struct _GUID *)v25->DevExt;
              p_HciConnectionSessionId = 50333696;
              v131 = v93 + 45;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
                v90,
                (unsigned int)&dword_14018A154,
                v91,
                v92,
                (__int64)&p_HciConnectionSessionId,
                (__int64)&v131,
                (__int64)&p_DeviceExtensionSessionId,
                (__int64)&v134);
            }
            goto LABEL_159;
          }
        }
        if ( (unsigned int)(ConnectionLocked->Info.EncryptType - 1) > 1
          && v25->IsAutomaticLEEncryptionEnabled
          && (ConnectionLocked->Dib->SmpDevInfo.Flag & 1) != 0 )
        {
          if ( !a6 || a6->Type != TypeL2cap || LOWORD(a6[5].MoveEntry.Blink) != 6 )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
              || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
            {
              LOBYTE(v28) = 0;
            }
            LOBYTE(v73) = 1;
            WPP_RECORDER_AND_TRACE_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              v28,
              v73,
              v26->IfrLog,
              4,
              2,
              79,
              (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
            v50 = p_HciConnectionSessionId;
            *(_DWORD *)v129 = 2;
            if ( a6 && a6->Type == TypeL2cap && LOWORD(a6[5].ConnectionCallback) != 1 )
              v50 |= 0x14u;
            goto LABEL_84;
          }
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
            LOBYTE(v28) = 0;
          v94 = WPP_GLOBAL_Control->DeviceType;
          if ( (_BYTE)v28 || v94 )
          {
            LOBYTE(v73) = v94 != 0;
            WPP_RECORDER_AND_TRACE_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              v28,
              v73,
              v26->IfrLog,
              5,
              2,
              78,
              (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
          }
          goto LABEL_83;
        }
      }
    }
    else if ( (v73 & 0x10) != 0 && (unsigned int)(ConnectionLocked->Info.EncryptType - 1) > 1 )
    {
      Authentication = ConnectionLocked->Info.Authentication;
      v50 = p_HciConnectionSessionId;
      if ( (unsigned int)(Authentication - 1) > 1 )
        *(_DWORD *)v129 = 2;
      goto LABEL_84;
    }
    if ( a6 )
    {
      if ( (unsigned int)(ConnectionLocked->Info.EncryptType - 1) <= 1
        && (a6->PolicyFlags & 2) != 0
        && Hci_CxnIsPolicyTrustedPath(ConnectionLocked) )
      {
        if ( ConnectionLocked->Info.EncryptionKeySize < Hci_CxnGetMinimumEncryptionKeySizePolicy(ConnectionLocked) )
        {
          MinimumEncryptionKeySizePolicy = Hci_CxnGetMinimumEncryptionKeySizePolicy(ConnectionLocked);
          LOBYTE(v95) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
          LOBYTE(v97) = 1;
          WPP_RECORDER_AND_TRACE_SF_qLL(
            WPP_GLOBAL_Control->AttachedDevice,
            v95,
            v97,
            v26->IfrLog,
            3,
            2,
            80,
            (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
            (char)a6,
            MinimumEncryptionKeySizePolicy,
            ConnectionLocked->Info.EncryptionKeySize);
          if ( (Microsoft_Windows_Bluetooth_PolicyEnableBits & 1) != 0 )
            McTemplateK0xuu_EtwWriteTransfer(
              v99,
              v98,
              v100,
              v26->DeviceInfo.address,
              MinimumEncryptionKeySizePolicy,
              ConnectionLocked->Info.EncryptionKeySize);
          v24 = -1073740959;
          goto LABEL_27;
        }
        v59 = 0;
      }
      if ( (unsigned int)(ConnectionLocked->Info.EncryptType - 1) <= 1
        && (a6->CxnFlags & 0x10) != 0
        && (a6->CreqFlags & 2) != 0 )
      {
        EncryptionKeySize = a6->EncryptionKeySize;
        v102 = ConnectionLocked->Info.EncryptionKeySize;
        if ( EncryptionKeySize > v102 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
            LOBYTE(v28) = v59;
          LOBYTE(EncryptionKeySize) = 1;
          WPP_RECORDER_AND_TRACE_SF_qLL(
            WPP_GLOBAL_Control->AttachedDevice,
            v28,
            EncryptionKeySize,
            v26->IfrLog,
            3,
            2,
            81,
            (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
            (char)a6,
            a6->EncryptionKeySize,
            v102);
          v24 = -1073741174;
          goto LABEL_27;
        }
      }
    }
    goto LABEL_83;
  }
  if ( a6 && (v29 & 0x180) != 0 )
  {
LABEL_38:
    v24 = -1073741667;
    goto LABEL_27;
  }
  Pool2 = (_HCI_CONNECTION *)ExAllocatePool2(64, 1352, 1346917442);
  P = Pool2;
  v31 = Pool2;
  if ( !Pool2 )
  {
LABEL_26:
    v24 = -1073741670;
LABEL_27:
    v27 = 0;
LABEL_67:
    if ( (a7 & 0x100) == 0 || !a6 || (v52 = v132) == 0 )
    {
LABEL_245:
      if ( v26 )
        v27 = HCI_DibConnectResult(v26, 0, v127[0], 0xFFFFFFFF, RemlockSize);
      goto LABEL_247;
    }
    wil::acquire_kspin_lock_at_dpc(&v134, &v132->StateLock);
    for ( i = (struct HCI_CLIENT *)v52->L2capData.PendingList.Flink; ; i = (struct HCI_CLIENT *)i->ListEntry.Flink )
    {
      if ( i == (struct HCI_CLIENT *)&v52->L2capData.PendingList )
        goto LABEL_244;
      if ( i == a6 )
        break;
    }
    v103 = a6->ListEntry.Flink;
    if ( (struct HCI_CLIENT *)a6->ListEntry.Flink->Blink == a6 )
    {
      v104 = a6->ListEntry.Blink;
      if ( (struct HCI_CLIENT *)v104->Flink == a6 )
      {
        v104->Flink = v103;
        v103->Blink = v104;
        a6->ListEntry.Blink = &a6->ListEntry;
        a6->ListEntry.Flink = &a6->ListEntry;
LABEL_244:
        __1__unique_storage_U__resource_policy_PEA_K__A6AXPEA_K__E_1_ReleaseSpinLockFromDpcLevel_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEA_KPEA_K_0A___T_details_wil___details_wil__QEAA_XZ(&v134);
        goto LABEL_245;
      }
    }
LABEL_258:
    __fastfail(3u);
  }
  _HCI_CONNECTION::_HCI_CONNECTION(Pool2);
  KeInitializeTimerEx(&v31->EncryptionDisabledTimer, NotificationTimer);
  KeInitializeDpc(&v31->EncryptionDisabledDpc, HCI_CxnEncryptionDisabledTimeoutDPC, 0);
  v32 = IoAcquireRemoveLockEx(
          &v25->DevExt->RemoveLock,
          v31,
          "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciconnection.cpp",
          0x923u,
          0x20u);
  v34 = 0;
  v24 = v32;
  if ( v32 < 0 )
  {
    v122 = 1;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      LOBYTE(v34) = 1;
    LOBYTE(v33) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v34,
      v33,
      v26->IfrLog,
      3,
      2,
      67,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
      v32);
    goto LABEL_27;
  }
  ControllerState = v25->ControllerState;
  v132 = v31;
  if ( (unsigned int)(ControllerState - 2) <= 1 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      LOBYTE(v34) = 1;
    v121 = ControllerState;
    LOBYTE(ControllerState) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v34,
      ControllerState,
      v26->IfrLog,
      2,
      2,
      82,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
      v121);
    IoReleaseRemoveLockEx(&v25->DevExt->RemoveLock, v31, 0x20u);
    v122 = 1;
    goto LABEL_38;
  }
  v36 = v127[0];
  if ( v127[0] == HciPhyTypeLE )
  {
    v37 = (_LIST_ENTRY *)P;
    v38 = v128;
    HCI_CxnInit((struct _HCI_CONNECTION *)P, v25, v26, v128, HciPhyTypeLE, v131);
    LOBYTE(v39) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_qDLil(
      WPP_GLOBAL_Control->AttachedDevice,
      v39,
      v40,
      v26->IfrLog,
      RemlockSizea,
      v115,
      v118,
      v120,
      (char)v37,
      (char)v37[12].Flink,
      1,
      *v130,
      v38 == MODE_CONNECT_REQUEST);
    p_Blink = &v25->HciCxnList.Blink;
    v42 = v25->HciCxnList.Blink;
    if ( v42->Flink != &v25->HciCxnList )
      goto LABEL_258;
    v43 = v37 + 2;
    v37[2].Blink = v42;
    v37[2].Flink = &v25->HciCxnList;
    v42->Flink = v37 + 2;
    v44 = 0;
  }
  else
  {
    if ( v128 == MODE_CONNECT_REQUEST && (ControllerState || v25->CurrentConnectRequest || v25->CurrentNameRequest) )
    {
      v45 = (struct _HCI_CONNECTION *)P;
      HCI_CxnInit((struct _HCI_CONNECTION *)P, v25, v26, MODE_PENDING, v127[0], v131);
      LOBYTE(v46) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      WPP_RECORDER_AND_TRACE_SF_qDLDDqDD(
        WPP_GLOBAL_Control->AttachedDevice,
        v46,
        WORD2(v25->CurrentNameRequest),
        v26->IfrLog,
        RemlockSizeb,
        v116,
        v118,
        v120,
        (char)v45,
        v45->Identifier,
        v36,
        *((_WORD *)v130 + 2),
        *(_DWORD *)v130,
        (char)v25->CurrentConnectRequest,
        BYTE4(v25->CurrentNameRequest),
        v25->CurrentNameRequest);
      memset(&v141, 0, sizeof(v141));
      v141.Initiator = 1;
      HCI_CxnSetInfoLocked(v45, &v141, 0x4000u);
      v47 = p_HciCxnPending->Blink;
      if ( v47->Flink != p_HciCxnPending )
        goto LABEL_258;
      v48 = &v45->ListEntry;
      v122 = 0;
      v45->ListEntry.Flink = p_HciCxnPending;
      v24 = 259;
      v48->Blink = v47;
      v47->Flink = v48;
      p_HciCxnPending->Blink = v48;
      goto LABEL_63;
    }
    v54 = (_HCI_CONNECTION *)P;
    HCI_CxnInit((struct _HCI_CONNECTION *)P, v25, v26, v128, v127[0], v131);
    LOBYTE(v55) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_qDLDDl(
      WPP_GLOBAL_Control->AttachedDevice,
      v55,
      *((unsigned __int16 *)v130 + 2),
      v26->IfrLog,
      RemlockSizec,
      v117,
      v118,
      v120,
      (char)v54,
      v54->Identifier,
      v36,
      *((_WORD *)v130 + 2),
      *(_DWORD *)v130,
      v128 == MODE_CONNECT_REQUEST);
    if ( v128 == MODE_CONNECT_REQUEST )
      v25->CurrentConnectRequest = v54;
    p_Blink = &v25->HciCxnList.Blink;
    v56 = v25->HciCxnList.Blink;
    if ( v56->Flink != &v25->HciCxnList )
      goto LABEL_258;
    v43 = &v54->ListEntry;
    v54->ListEntry.Flink = &v25->HciCxnList;
    v44 = 1;
    v54->ListEntry.Blink = v56;
    v56->Flink = &v54->ListEntry;
  }
  v57 = v129;
  *p_Blink = v43;
  v122 = 0;
  *(_DWORD *)v57 = v44;
  if ( v24 == 259 )
  {
LABEL_63:
    v49 = v132;
    v50 = p_HciConnectionSessionId;
    goto LABEL_64;
  }
LABEL_83:
  v50 = p_HciConnectionSessionId;
LABEL_84:
  v49 = v132;
  RefObj_AddRefEx(
    &v132->RefObj,
    HCI_GetOrAllocateConnection,
    2756,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciconnection.cpp");
  *v135 = v49;
LABEL_64:
  if ( a6 )
  {
    KeAcquireSpinLockAtDpcLevel(&v49->StateLock);
    v51 = v129;
    a6->CxnFlags |= v50;
    v24 = HCI_CxnAddClientLocked(v49, a6, v51, HCI_GetOrAllocateConnection);
    KeReleaseSpinLockFromDpcLevel(&v49->StateLock);
  }
  v27 = 0;
  if ( v24 < 0 )
    goto LABEL_67;
LABEL_247:
  KeReleaseSpinLock(SpinLock, NewIrql);
  if ( v122 )
    ExFreePoolWithTag(P, 0);
  if ( v27 )
    RefObj_ReleaseEx(v26, v26, 2831, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciconnection.cpp");
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v11 = 0;
  v106 = WPP_GLOBAL_Control->DeviceType;
  if ( v11 || v106 )
  {
    v107 = *v135;
    if ( v138 )
      v108 = *v138;
    else
      v108 = -1;
    LOBYTE(v107) = v11;
    LOBYTE(v105) = v106 != 0;
    WPP_RECORDER_AND_TRACE_SF_qDDDDqqLD(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v107,
      v105,
      v139->IfrLog,
      RemlockSize,
      v114,
      v118,
      v120,
      (char)v139,
      *((_WORD *)v130 + 2),
      *(_DWORD *)v130,
      v108,
      v128,
      (char)a6,
      (char)*v135,
      *(_DWORD *)v129,
      v24);
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x140042460  push    rbp
0x140042462  push    rbx
0x140042463  push    rsi
0x140042464  push    rdi
0x140042465  push    r12
0x140042467  push    r13
0x140042469  push    r14
0x14004246b  push    r15
0x14004246d  lea     rbp, [rsp-88h]
0x140042475  sub     rsp, 198h
0x14004247c  mov     rax, cs:__security_cookie
0x140042483  xor     rax, rsp
0x140042486  mov     [rbp+0C0h+var_50], rax
0x14004248a  mov     rax, [rbp+0C0h+arg_38]
0x140042491  mov     r11d, r9d
0x140042494  mov     rsi, [rbp+0C0h+arg_40]
0x14004249b  mov     r10, rdx
0x14004249e  mov     r14, [rbp+0C0h+arg_48]
0x1400424a5  mov     r13, rcx
0x1400424a8  mov     r15, [rbp+0C0h+arg_28]
0x1400424af  mov     rbx, [rbp+0C0h+arg_20]
0x1400424b6  mov     [rbp+0C0h+var_F0], rax
0x1400424ba  mov     [rbp+0C0h+var_120], rsi
0x1400424be  mov     [rbp+0C0h+var_110], r14
0x1400424c2  mov     [rbp+0C0h+var_128], r9d
0x1400424c6  mov     [rbp+0C0h+var_D8], r8
0x1400424ca  mov     [rbp+0C0h+var_118], rdx
0x1400424ce  mov     [rbp+0C0h+var_D0], rcx
0x1400424d2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400424d9  xor     r9d, r9d
0x1400424dc  mov     eax, [rcx+2Ch]
0x1400424df  lea     edi, [r9+1]
0x1400424e3  test    al, 2
0x1400424e5  jz      short loc_1400424F0
0x1400424e7  cmp     byte ptr [rcx+29h], 5
0x1400424eb  mov     dl, dil
0x1400424ee  jnb     short loc_1400424F3
0x1400424f0  mov     dl, r9b
0x1400424f3  movzx   eax, word ptr [rcx+48h]
0x1400424f7  test    ax, ax
0x1400424fa  setnz   r8b
0x1400424fe  test    dl, dl
0x140042500  jnz     short loc_140042507
0x140042502  test    ax, ax
0x140042505  jz      short loc_140042548
0x140042507  movzx   r9d, word ptr [r10+4]
0x14004250c  mov     eax, [r10]
0x14004250f  mov     r12d, [rbp+0C0h+arg_30]
0x140042516  mov     rcx, [rcx+18h]
0x14004251a  mov     dword ptr [rsp+1D0h+var_168], r11d
0x14004251f  mov     [rsp+1D0h+var_170], r12d
0x140042524  mov     [rsp+1D0h+var_178], r15
0x140042529  mov     dword ptr [rsp+1D0h+var_180], eax
0x14004252d  mov     dword ptr [rsp+1D0h+var_188], r9d
0x140042532  mov     r9, [r13+10B0h]
0x140042539  mov     qword ptr [rsp+1D0h+var_190], r13
0x14004253e  call    WPP_RECORDER_AND_TRACE_SF_qDDqDD
0x140042543  xor     r9d, r9d
0x140042546  jmp     short loc_14004254F
0x140042548  mov     r12d, [rbp+0C0h+arg_30]
0x14004254f  mov     rax, [rbp+0C0h+var_F0]
0x140042553  mov     [rbp+0C0h+var_108], r9
0x140042557  mov     [rbp+0C0h+P], r9
0x14004255b  mov     [rbp+0C0h+var_140], r9b
0x14004255f  mov     [rax], r9
0x140042562  mov     [rsi], r9d
0x140042565  test    r15, r15
0x140042568  jz      short loc_140042570
0x14004256a  mov     esi, [r15+4Ch]
0x14004256e  jmp     short loc_140042573
0x140042570  mov     esi, r12d
0x140042573  lea     rax, [r13+7B0h]
0x14004257a  shr     esi, 0Dh
0x14004257d  and     sil, dil
0x140042580  mov     [rbp+0C0h+SpinLock], rax
0x140042584  mov     rcx, rax; SpinLock
0x140042587  mov     dword ptr [rbp+0C0h+var_12C], esi
0x14004258a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140042591  nop     dword ptr [rax+rax+00h]
0x140042596  mov     r8, [rbp+0C0h+var_118]; unsigned __int64 *
0x14004259a  lea     r12, [r13+7D8h]
0x1400425a1  mov     rdx, r12; struct _LIST_ENTRY *
0x1400425a4  mov     [rbp+0C0h+NewIrql], al
0x1400425a7  mov     r9b, sil; enum _HCI_PHY_TYPE
0x1400425aa  mov     byte ptr [rsp+1D0h+RemlockSize], dil; bool
0x1400425af  mov     rcx, r13; struct HCI_INTERFACE *
0x1400425b2  call    ?HCI_FindConnectionLocked@@YAPEAU_HCI_CONNECTION@@PEAUHCI_INTERFACE@@PEAU_LIST_ENTRY@@PEB_KW4_HCI_PHY_TYPE@@_N@Z; HCI_FindConnectionLocked(HCI_INTERFACE *,_LIST_ENTRY *,unsigned __int64 const *,_HCI_PHY_TYPE,bool)
0x1400425b7  xor     r9d, r9d
0x1400425ba  mov     rsi, rax
0x1400425bd  test    rax, rax
0x1400425c0  jnz     short loc_1400425EA
0x1400425c2  mov     r8, [rbp+0C0h+var_118]; unsigned __int64 *
0x1400425c6  lea     rdx, [r13+7B8h]; struct _LIST_ENTRY *
0x1400425cd  mov     [rbp+0C0h+var_12F], r9b
0x1400425d1  mov     rcx, r13; struct HCI_INTERFACE *
0x1400425d4  mov     r9b, [rbp+0C0h+var_12C]; enum _HCI_PHY_TYPE
0x1400425d8  mov     byte ptr [rsp+1D0h+RemlockSize], dil; bool
0x1400425dd  call    ?HCI_FindConnectionLocked@@YAPEAU_HCI_CONNECTION@@PEAUHCI_INTERFACE@@PEAU_LIST_ENTRY@@PEB_KW4_HCI_PHY_TYPE@@_N@Z; HCI_FindConnectionLocked(HCI_INTERFACE *,_LIST_ENTRY *,unsigned __int64 const *,_HCI_PHY_TYPE,bool)
0x1400425e2  mov     rsi, rax
0x1400425e5  xor     r9d, r9d
0x1400425e8  jmp     short loc_1400425EE
0x1400425ea  mov     [rbp+0C0h+var_12F], dil
0x1400425ee  mov     [rbp+0C0h+var_E0], r9
0x1400425f2  mov     edx, 0FFh
0x1400425f7  mov     [rbp+0C0h+var_130], r9b
0x1400425fb  test    rsi, rsi
0x1400425fe  jz      short loc_140042639
0x140042600  mov     rax, [rsi+30h]
0x140042604  mov     rcx, [rax+20h]
0x140042608  mov     [rbp+0C0h+var_E0], rcx
0x14004260c  mov     rcx, [rsi+30h]
0x140042610  test    dword ptr [rcx+18h], 8000h
0x140042617  jz      short loc_14004262A
0x140042619  movzx   eax, byte ptr [rcx+5B0h]
0x140042620  mov     ecx, r9d
0x140042623  cmp     al, dl
0x140042625  cmovnz  ecx, eax
0x140042628  jmp     short loc_14004262C
0x14004262a  mov     cl, dl
0x14004262c  mov     [rbp+0C0h+var_130], cl
0x14004262f  lea     rdx, [rbp+0C0h+var_E0]
0x140042633  lea     r8, [rbp+0C0h+var_130]
0x140042637  jmp     short loc_140042641
0x140042639  mov     r8, [rbp+0C0h+var_D8]; unsigned __int8 *
0x14004263d  mov     rdx, [rbp+0C0h+var_118]; unsigned __int64 *
0x140042641  cmp     [rbp+0C0h+var_128], 6
0x140042645  jnz     short loc_14004264F
0x140042647  mov     al, dil
0x14004264a  test    rsi, rsi
0x14004264d  jz      short loc_140042652
0x14004264f  mov     al, r9b
0x140042652  mov     ecx, dword ptr [rbp+0C0h+var_12C]
0x140042655  mov     [rsp+1D0h+var_180], r9b; unsigned __int8
0x14004265a  xor     r9d, r9d; unsigned int (*)(struct HCI_INTERFACE *, struct DEVICE_INFO_BLOCK *, enum _HCI_PHY_TYPE, void *, enum LinkedDibAction *)
0x14004265d  mov     [rsp+1D0h+var_188], r14; struct _GUID *
0x140042662  xor     r14d, r14d
0x140042665  mov     [rsp+1D0h+var_190], cl; enum _HCI_PHY_TYPE
0x140042669  mov     [rsp+1D0h+var_198], dil; char
0x14004266e  mov     [rsp+1D0h+var_1A0], al; char
0x140042672  mov     [rsp+1D0h+var_1A8], rbx; unsigned __int8 *
0x140042677  mov     rbx, r13
0x14004267a  mov     rcx, rbx; struct HCI_INTERFACE *
0x14004267d  mov     qword ptr [rsp+1D0h+RemlockSize], r14; void *
0x140042682  call    ?HCI_UpdateOrAllocateDibEx@@YAPEAUDEVICE_INFO_BLOCK@@PEAUHCI_INTERFACE@@PEA_KPEBEP6AK0PEAU1@W4_HCI_PHY_TYPE@@PEAXPEAW4LinkedDibAction@@@Z5PEAEEE4PEAU_GUID@@E@Z; HCI_UpdateOrAllocateDibEx(HCI_INTERFACE *,unsigned __int64 *,uchar const *,ulong (*)(HCI_INTERFACE *,DEVICE_INFO_BLOCK *,_HCI_PHY_TYPE,void *,LinkedDibAction *),void *,uchar *,uchar,uchar,_HCI_PHY_TYPE,_GUID *,uchar)
0x140042687  mov     r13, rax
0x14004268a  test    rax, rax
0x14004268d  jnz     short loc_1400426A0
0x14004268f  mov     r14d, 0C000009Ah
0x140042695  xor     r12d, r12d
0x140042698  mov     bl, r12b
0x14004269b  jmp     loc_140042A34
0x1400426a0  call    Feature_53100197__private_IsEnabledDeviceUsageNoInline
0x1400426a5  test    eax, eax
0x1400426a7  jz      short loc_1400426C4
0x1400426a9  test    rsi, rsi
0x1400426ac  jnz     short loc_1400426C4
0x1400426ae  mov     rax, [r13+368h]
0x1400426b5  nop
0x1400426b6  bt      rax, 8
0x1400426bb  jnb     short loc_1400426C4
0x1400426bd  add     [r13+0AA8h], edi
0x1400426c4  test    r15, r15
0x1400426c7  jz      short loc_1400426D5
0x1400426c9  mov     eax, [rbp+0C0h+arg_30]
0x1400426cf  or      eax, [r15+4Ch]
0x1400426d3  jmp     short loc_1400426D8
0x1400426d5  mov     eax, r14d
0x1400426d8  mov     dword ptr [rbp+0C0h+var_138], eax
0x1400426db  test    rsi, rsi
0x1400426de  jnz     loc_140042C0B
0x1400426e4  test    r15, r15
0x1400426e7  jz      short loc_1400426F8
0x1400426e9  test    eax, 180h
0x1400426ee  jz      short loc_1400426F8
0x1400426f0  mov     r14d, 0C000009Dh
0x1400426f6  jmp     short loc_140042695
0x1400426f8  mov     edx, 548h
0x1400426fd  mov     ecx, 40h ; '@'
0x140042702  mov     r8d, 50485442h
0x140042708  call    cs:__imp_ExAllocatePool2
0x14004270f  nop     dword ptr [rax+rax+00h]
0x140042714  mov     [rbp+0C0h+P], rax
0x140042718  mov     rsi, rax
0x14004271b  test    rax, rax
0x14004271e  jz      loc_14004268F
0x140042724  mov     rcx, rax; this
0x140042727  call    ??0_HCI_CONNECTION@@QEAA@XZ; _HCI_CONNECTION::_HCI_CONNECTION(void)
0x14004272c  lea     rcx, [rsi+390h]; Timer
0x140042733  xor     edx, edx; Type
0x140042735  call    cs:__imp_KeInitializeTimerEx
0x14004273c  nop     dword ptr [rax+rax+00h]
0x140042741  lea     rcx, [rsi+3D0h]; Dpc
0x140042748  xor     r8d, r8d; DeferredContext
0x14004274b  lea     rdx, ?HCI_CxnEncryptionDisabledTimeoutDPC@@YAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x140042752  call    cs:__imp_KeInitializeDpc
0x140042759  nop     dword ptr [rax+rax+00h]
0x14004275e  mov     rcx, [rbx+4A8h]
0x140042765  lea     r8, aOnecoreDrivers_26; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14004276c  add     rcx, 38h ; '8'; RemoveLock
0x140042770  mov     [rsp+1D0h+RemlockSize], 20h ; ' '; RemlockSize
0x140042778  mov     r9d, 923h; Line
0x14004277e  mov     rdx, rsi; Tag
0x140042781  call    cs:__imp_IoAcquireRemoveLockEx
0x140042788  nop     dword ptr [rax+rax+00h]
0x14004278d  xor     edx, edx
0x14004278f  mov     r14d, eax
0x140042792  test    eax, eax
0x140042794  jns     short loc_1400427EF
0x140042796  mov     [rbp+0C0h+var_140], dil
0x14004279a  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400427a1  mov     ecx, [rax+2Ch]
0x1400427a4  test    cl, 2
0x1400427a7  jz      short loc_1400427B2
0x1400427a9  cmp     byte ptr [rax+29h], 3
0x1400427ad  jb      short loc_1400427B2
0x1400427af  mov     dl, dil
0x1400427b2  mov     r9, [r13+838h]
0x1400427b9  lea     r12, WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids
0x1400427c0  mov     rcx, [rax+18h]
0x1400427c4  mov     r8b, dil
0x1400427c7  mov     dword ptr [rsp+1D0h+var_190], r14d
0x1400427cc  mov     qword ptr [rsp+1D0h+var_198], r12
0x1400427d1  mov     word ptr [rsp+1D0h+var_1A0], 43h ; 'C'
0x1400427d8  mov     dword ptr [rsp+1D0h+var_1A8], 2
0x1400427e0  mov     byte ptr [rsp+1D0h+RemlockSize], 3
0x1400427e5  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400427ea  jmp     loc_140042695
0x1400427ef  mov     r8d, [rbx+20h]
0x1400427f3  mov     [rbp+0C0h+var_108], rsi
0x1400427f7  lea     eax, [r8-2]
0x1400427fb  cmp     eax, edi
0x1400427fd  jbe     loc_140042B93
0x140042803  mov     esi, dword ptr [rbp+0C0h+var_12C]
0x140042806  cmp     sil, dil
0x140042809  jnz     loc_1400428BA
0x14004280f  mov     rax, [rbp+0C0h+var_110]
0x140042813  mov     r8, r13; struct DEVICE_INFO_BLOCK *
0x140042816  mov     r12, [rbp+0C0h+P]
0x14004281a  mov     rdx, rbx; struct HCI_INTERFACE *
0x14004281d  mov     esi, [rbp+0C0h+var_128]
0x140042820  mov     rcx, r12; struct _HCI_CONNECTION *
0x140042823  mov     [rsp+1D0h+var_1A8], rax; struct _GUID *
0x140042828  mov     r9d, esi; enum _CONNECTION_STATE
0x14004282b  mov     byte ptr [rsp+1D0h+RemlockSize], dil; enum _HCI_PHY_TYPE
0x140042830  call    ?HCI_CxnInit@@YAXPEAU_HCI_CONNECTION@@PEAUHCI_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@W4_CONNECTION_STATE@@W4_HCI_PHY_TYPE@@PEAU_GUID@@@Z; HCI_CxnInit(_HCI_CONNECTION *,HCI_INTERFACE *,DEVICE_INFO_BLOCK *,_CONNECTION_STATE,_HCI_PHY_TYPE,_GUID *)
0x140042835  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004283c  mov     eax, [rcx+2Ch]
0x14004283f  test    al, 2
0x140042841  jz      short loc_14004284E
0x140042843  cmp     byte ptr [rcx+29h], 4
0x140042847  jb      short loc_14004284E
0x140042849  mov     dl, dil
0x14004284c  jmp     short loc_140042850
0x14004284e  xor     dl, dl
0x140042850  mov     r9, [r13+838h]
0x140042857  xor     eax, eax
0x140042859  mov     rcx, [rcx+18h]
0x14004285d  cmp     esi, 6
0x140042860  setz    al
0x140042863  mov     [rsp+1D0h+var_170], eax
0x140042867  mov     rax, [rbp+0C0h+var_118]
0x14004286b  mov     rax, [rax]
0x14004286e  mov     [rsp+1D0h+var_178], rax
0x140042873  mov     eax, [r12+0C0h]
0x14004287b  mov     dword ptr [rsp+1D0h+var_180], edi
0x14004287f  mov     dword ptr [rsp+1D0h+var_188], eax
0x140042883  mov     qword ptr [rsp+1D0h+var_190], r12
0x140042888  call    WPP_RECORDER_AND_TRACE_SF_qDLil
0x14004288d  lea     r8, [rbx+7B8h]
0x140042894  lea     rdx, [r8+8]
0x140042898  mov     rcx, [rdx]
0x14004289b  cmp     [rcx], r8
0x14004289e  jnz     loc_140043719
0x1400428a4  lea     rax, [r12+20h]
0x1400428a9  mov     [rax+8], rcx
0x1400428ad  mov     [rax], r8
0x1400428b0  mov     [rcx], rax
0x1400428b3  xor     ecx, ecx
0x1400428b5  jmp     loc_140042B47
0x1400428ba  mov     ecx, [rbp+0C0h+var_128]
0x1400428bd  cmp     ecx, 6
0x1400428c0  jnz     loc_140042A88
0x1400428c6  test    r8d, r8d
0x1400428c9  jnz     short loc_1400428E1
0x1400428cb  cmp     [rbx+800h], rdx
0x1400428d2  jnz     short loc_1400428E1
0x1400428d4  cmp     [rbx+808h], rdx
0x1400428db  jz      loc_140042A88
0x1400428e1  mov     rax, [rbp+0C0h+var_110]
0x1400428e5  mov     r9d, 5; enum _CONNECTION_STATE
0x1400428eb  mov     r14, [rbp+0C0h+P]
0x1400428ef  mov     r8, r13; struct DEVICE_INFO_BLOCK *
0x1400428f2  mov     [rsp+1D0h+var_1A8], rax; struct _GUID *
0x1400428f7  mov     rcx, r14; struct _HCI_CONNECTION *
0x1400428fa  mov     rdx, rbx; struct HCI_INTERFACE *
0x1400428fd  mov     byte ptr [rsp+1D0h+RemlockSize], sil; unsigned __int8
0x140042902  call    ?HCI_CxnInit@@YAXPEAU_HCI_CONNECTION@@PEAUHCI_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@W4_CONNECTION_STATE@@W4_HCI_PHY_TYPE@@PEAU_GUID@@@Z; HCI_CxnInit(_HCI_CONNECTION *,HCI_INTERFACE *,DEVICE_INFO_BLOCK *,_CONNECTION_STATE,_HCI_PHY_TYPE,_GUID *)
0x140042907  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004290e  mov     eax, [rcx+2Ch]
0x140042911  test    al, 2
  ... truncated ...
```
