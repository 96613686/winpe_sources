# BthUsb_ScoAddChannel(_BTDEVICE *,_BTH_SCO_ADD_CHANNEL_ARG *)

- ea: `0x1400030e0`
- end: `0x140004082`
- name: `?BthUsb_ScoAddChannel@@YAJPEAU_BTDEVICE@@PEAU_BTH_SCO_ADD_CHANNEL_ARG@@@Z`
- size: `4002`
- prototype: `__int64 __fastcall(struct _BTDEVICE *, struct _BTH_SCO_ADD_CHANNEL_ARG *)`
- caller_count: `0`
- callee_count: `31`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000115c`
- `0x140001304`
- `0x14000175c`
- `0x1400017d4`
- `0x14000187c`
- `0x140001924`
- `0x1400030e0`
- `0x1400046b4`
- `0x1400047a4`
- `0x140004b3c`
- `0x140004f3c`
- `0x140004fc8`
- `0x140005600`
- `0x1400057ac`
- `0x14000581c`
- `0x140005858`
- `0x140006104`
- `0x140006318`
- `0x14000638c`
- `0x140006580`
- `0x140006638`
- `0x140006700`
- `0x1400067e8`
- `0x140006e80`
- `0x1400077c4`
- `0x1400078a0`
- `0x140009000`
- `0x140009340`
- `0x14000da68`
- `0x14000e1c0`
- `0x140019ea0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000405f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000405f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004053`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004053`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400032f6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400032f6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400032e5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400032e5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003d6e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003d6e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140003c34`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140003c34`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoAddChannel(struct _BTDEVICE *a1, struct _BTH_SCO_ADD_CHANNEL_ARG *a2)
{
  int v4; // edx
  int v5; // r8d
  wil::push_lock *p_ChannelMutex; // rbx
  char v7; // di
  struct _DEVICE_EXTENSION *MiniportContext; // r14
  unsigned __int8 v9; // al
  int v10; // edx
  int v11; // edx
  NTSTATUS UsbBusInterface; // esi
  int v13; // r8d
  int v14; // edx
  int NumChannels; // r8d
  int v16; // r8d
  int v17; // edx
  struct _SCO_USB_CHANNEL *v18; // r13
  unsigned int v19; // esi
  void *DeviceExtension; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  unsigned int MaxUsedBw; // eax
  unsigned int v23; // ecx
  unsigned int v24; // r12d
  unsigned int v25; // edx
  unsigned int v26; // r9d
  int v27; // edx
  int v28; // r8d
  unsigned __int8 v29; // si
  void *v30; // r9
  _DEVICE_OBJECT *v31; // rcx
  struct _USB_INTERFACE_DESCRIPTOR *InterfaceByFrame; // rax
  int v33; // edx
  int v34; // r8d
  int v35; // edx
  int v36; // r8d
  unsigned int v37; // esi
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // esi
  unsigned int v41; // r12d
  _USB_INTERFACE_DESCRIPTOR *MaxInterface; // rax
  __int16 bAlternateSetting; // cx
  _USB_INTERFACE_DESCRIPTOR *RealMaxInterface; // rax
  _USB_DEVICE_DESCRIPTOR *DeviceDescriptor; // rcx
  __int64 *v46; // rcx
  unsigned __int16 v47; // ax
  int v48; // edx
  int v49; // r8d
  int v50; // edx
  int v51; // r8d
  int v52; // edx
  int v53; // r8d
  int v54; // edx
  int v55; // r8d
  int v56; // edx
  int v57; // r8d
  int v58; // edx
  int v59; // r8d
  int v60; // edx
  int v61; // r8d
  int v62; // edx
  int v63; // r8d
  int v64; // edx
  int v65; // r8d
  int v66; // r9d
  char v67; // r15
  int v68; // edx
  int v69; // r8d
  int v70; // edx
  int v71; // r8d
  char v72; // r12
  int v73; // edx
  int v74; // r8d
  int v75; // edx
  int v76; // r8d
  char v77; // r15
  char v78; // r12
  int v79; // edx
  int v80; // r8d
  char v81; // al
  int v82; // r9d
  _USB_INTERFACE_DESCRIPTOR *v83; // rax
  __int16 v84; // cx
  _USB_INTERFACE_DESCRIPTOR *v85; // rax
  _USB_DEVICE_DESCRIPTOR *v86; // rcx
  int RemlockSize; // [rsp+20h] [rbp-110h]
  int RemlockSizea; // [rsp+20h] [rbp-110h]
  int RemlockSizeb; // [rsp+20h] [rbp-110h]
  int RemlockSizec; // [rsp+20h] [rbp-110h]
  int RemlockSized; // [rsp+20h] [rbp-110h]
  int RemlockSizee; // [rsp+20h] [rbp-110h]
  int v94; // [rsp+28h] [rbp-108h]
  int v95; // [rsp+28h] [rbp-108h]
  int v96; // [rsp+30h] [rbp-100h]
  int v97; // [rsp+38h] [rbp-F8h]
  int v98; // [rsp+38h] [rbp-F8h]
  unsigned __int64 v99; // [rsp+B0h] [rbp-80h] BYREF
  __int16 v100; // [rsp+B8h] [rbp-78h] BYREF
  __int16 v101; // [rsp+BAh] [rbp-76h] BYREF
  unsigned __int16 idProduct; // [rsp+BCh] [rbp-74h] BYREF
  unsigned int v103; // [rsp+C0h] [rbp-70h] BYREF
  unsigned int v104; // [rsp+C4h] [rbp-6Ch] BYREF
  unsigned int v105; // [rsp+C8h] [rbp-68h] BYREF
  int v106; // [rsp+CCh] [rbp-64h] BYREF
  unsigned __int64 v107; // [rsp+D0h] [rbp-60h] BYREF
  unsigned int v108; // [rsp+D8h] [rbp-58h] BYREF
  unsigned int MaxFrameSize; // [rsp+DCh] [rbp-54h] BYREF
  unsigned int RealMaxFrameSize; // [rsp+E0h] [rbp-50h] BYREF
  struct _USB_INTERFACE_DESCRIPTOR *v111; // [rsp+E8h] [rbp-48h]
  __int64 v112; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v113; // [rsp+F8h] [rbp-38h] BYREF
  struct _SCO_USB_CHANNEL v114; // [rsp+100h] [rbp-30h] BYREF
  unsigned int v115; // [rsp+1F0h] [rbp+C0h] BYREF
  unsigned int v116; // [rsp+1F8h] [rbp+C8h] BYREF
  unsigned __int16 v117; // [rsp+200h] [rbp+D0h] BYREF
  unsigned int v118; // [rsp+208h] [rbp+D8h] BYREF

  memset(&v114, 0, sizeof(v114));
  p_ChannelMutex = 0;
  v7 = 1;
  LOBYTE(v4) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qD(WPP_GLOBAL_Control->AttachedDevice, v4, v5, WPP_GLOBAL_Control->DeviceExtension);
  MiniportContext = (struct _DEVICE_EXTENSION *)a1->MiniportContext;
  v9 = IsAlignDataCapable(a1->MiniportContext);
  if ( *((_BYTE *)a2 + 40) && v9 )
  {
    LOBYTE(v115) = 1;
    *((_DWORD *)a2 + 2) = 62000;
    *((_DWORD *)a2 + 3) = 62000;
  }
  else
  {
    LOBYTE(v115) = 0;
  }
  LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_DDLLLL(WPP_GLOBAL_Control->AttachedDevice, v10, v9, WPP_GLOBAL_Control->DeviceExtension);
  UsbBusInterface = BthUsb_ScoBasicValidation(a1, a2, 0x30u);
  if ( UsbBusInterface < 0 )
    goto LABEL_172;
  if ( *((_DWORD *)a2 + 4) )
  {
    LOBYTE(v11) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v13,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      58,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
LABEL_20:
    UsbBusInterface = -1073741811;
    goto LABEL_172;
  }
  if ( !*((_QWORD *)a2 + 3) )
  {
    LOBYTE(v11) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v13,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      59,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
    goto LABEL_20;
  }
  if ( *((_WORD *)a2 + 2) == 0xFFFF )
  {
    LOBYTE(v11) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v13,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      60,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
    goto LABEL_20;
  }
  p_ChannelMutex = &MiniportContext->Sco.ChannelMutex;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&MiniportContext->Sco.ChannelMutex, 0);
  NumChannels = MiniportContext->Sco.NumChannels;
  LOWORD(NumChannels) = NumChannels + 1;
  v117 = NumChannels;
  LOBYTE(v14) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v14,
    NumChannels,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    61,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    NumChannels);
  v17 = 0;
  while ( 1 )
  {
    v18 = &MiniportContext->Sco.Channel[(unsigned __int16)v17];
    if ( v18->ConnectionHandle == 0xFFFF )
      break;
    LOWORD(v17) = v17 + 1;
    if ( (unsigned __int16)v17 >= 3u )
      goto LABEL_42;
  }
  if ( !v18 )
  {
LABEL_42:
    LOBYTE(v17) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v17,
      v16,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      62,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
    UsbBusInterface = -1073741211;
    goto LABEL_172;
  }
  v118 = *((_DWORD *)a2 + 2);
  v116 = *((_DWORD *)a2 + 3);
  UsbBusInterface = BthUsb_ScoValidateChnInfo(MiniportContext, &v118, &v116);
  if ( UsbBusInterface < 0 )
    goto LABEL_172;
  LOBYTE(v11) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  v19 = v116;
  DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
  AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
  v99 = __PAIR64__(v116, v118);
  WPP_RECORDER_AND_TRACE_SF_LL(
    (_DWORD)AttachedDevice,
    v11,
    v13,
    (_DWORD)DeviceExtension,
    RemlockSize,
    4,
    63,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    v118,
    v116);
  MaxUsedBw = BthUsb_ScoGetMaxUsedBw(MiniportContext);
  v23 = MaxUsedBw;
  v24 = MaxUsedBw;
  if ( MaxUsedBw < (unsigned int)v99 )
    v23 = v99;
  if ( v23 < v19 )
    v23 = v19;
  v25 = v23 / 0x3E8;
  v26 = v23 / 0x3E8 * v117 + 1;
  v118 = v26;
  LOBYTE(v25) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_LLLL(
    WPP_GLOBAL_Control->AttachedDevice,
    v25,
    v99,
    WPP_GLOBAL_Control->DeviceExtension,
    RemlockSizea,
    v94,
    64,
    v97,
    MaxUsedBw,
    v99,
    v19,
    v26);
  if ( (_BYTE)v115 )
    v29 = v24 != 0;
  else
    v29 = v24 == 1;
  LOBYTE(v27) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  v30 = WPP_GLOBAL_Control->DeviceExtension;
  v31 = WPP_GLOBAL_Control->AttachedDevice;
  v115 = v29;
  WPP_RECORDER_AND_TRACE_SF_lL((_DWORD)v31, v27, v28, (_DWORD)v30, RemlockSizeb, v95, v96, v98, v29, v24);
  v116 = 0;
  InterfaceByFrame = BthUsb_ScoFindInterfaceByFrame(MiniportContext, v118, &v116);
  v111 = InterfaceByFrame;
  if ( InterfaceByFrame && !v29 )
  {
    LOBYTE(v115) = 0;
    LOBYTE(v33) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v33,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      67,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      InterfaceByFrame->bAlternateSetting);
    LOBYTE(v35) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    v37 = v116;
    LOBYTE(v36) = 1;
    WPP_RECORDER_AND_TRACE_SF_L(
      WPP_GLOBAL_Control->AttachedDevice,
      v35,
      v36,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      68,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      v116);
    if ( (unsigned int)dword_140013000 > 4
      && (qword_140013010 & 0x400000000000LL) != 0
      && (qword_140013018 & 0x400000000000LL) == qword_140013018 )
    {
      v103 = v37;
      v40 = HIDWORD(v99);
      v105 = v24;
      v41 = v99;
      LOBYTE(v116) = v111->bAlternateSetting;
      v104 = v118;
      LOWORD(v118) = v117;
      HIDWORD(v107) = *((_DWORD *)a2 + 3);
      v108 = *((_DWORD *)a2 + 2);
      MaxFrameSize = MiniportContext->Sco.MaxFrameSize;
      MaxInterface = MiniportContext->Sco.MaxInterface;
      v106 = HIDWORD(v99);
      LODWORD(v107) = v99;
      v112 = (__int64)MiniportContext;
      bAlternateSetting = MaxInterface->bAlternateSetting;
      RealMaxFrameSize = MiniportContext->Sco.RealMaxFrameSize;
      RealMaxInterface = MiniportContext->Sco.RealMaxInterface;
      v100 = bAlternateSetting;
      v101 = RealMaxInterface->bAlternateSetting;
      DeviceDescriptor = MiniportContext->DeviceDescriptor;
      idProduct = DeviceDescriptor->idProduct;
      WORD2(v99) = DeviceDescriptor->idVendor;
      LOWORD(v99) = DeviceDescriptor->bcdUSB;
      v113 = 33556480;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        (_DWORD)DeviceDescriptor,
        (unsigned int)byte_140010D8B,
        v38,
        v39,
        (__int64)&v113,
        (__int64)&v112,
        (__int64)&v99,
        (__int64)&v99 + 4,
        (__int64)&idProduct,
        (__int64)&v101,
        (__int64)&RealMaxFrameSize,
        (__int64)&v100,
        (__int64)&MaxFrameSize,
        (__int64)&v108,
        (__int64)&v107 + 4,
        (__int64)&v107,
        (__int64)&v106,
        (__int64)&v105,
        (__int64)&v118,
        (__int64)&v104,
        (__int64)&v116,
        (__int64)&v103);
    }
    else
    {
      v40 = HIDWORD(v99);
      v41 = v99;
    }
    v46 = qword_140010000;
    if ( v111->bAlternateSetting != 6 )
      v46 = qword_140010050;
    MiniportContext->Sco.UsbAltSetting = (const ScoUsbAltSetting *)v46;
    memset(&v114, 0, sizeof(v114));
    v114.Callback = (int (__fastcall *)(void *, _BTH_SCO_MP_INDICATION_CODE, _BTH_SCO_MP_INDICATION_PARAMETERS *))*((_QWORD *)a2 + 3);
    v114.CallbackContext = (void *)*((_QWORD *)a2 + 4);
    v47 = *((_WORD *)a2 + 2) & 0xFFF;
    v114.TxBandwidth = v41;
    v114.ConnectionHandle = v47;
    v114.RxBandwidth = v40;
    BthUsb_ScoComputeChannelInfo(MiniportContext, &v114, v117);
    LOBYTE(v48) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v48,
      v49,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      69,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      (char)&v114);
    LOBYTE(v50) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v50,
      v51,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      70,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      v114.ConnectionHandle);
    LOBYTE(v52) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v52,
      v53,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      71,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      v114.Flags);
    LOBYTE(v54) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v55) = 1;
    WPP_RECORDER_AND_TRACE_SF_L(
      WPP_GLOBAL_Control->AttachedDevice,
      v54,
      v55,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      72,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      v114.WriteDataSizePerReq);
    LOBYTE(v56) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_LLL(
      WPP_GLOBAL_Control->AttachedDevice,
      v56,
      v57,
      WPP_GLOBAL_Control->DeviceExtension,
      RemlockSizec,
      4,
      73,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      v114.TxBandwidth,
      v114.TxPacketSize,
      v114.TxFragmentSize);
    LOBYTE(v58) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_LLL(
      WPP_GLOBAL_Control->AttachedDevice,
      v58,
      v59,
      WPP_GLOBAL_Control->DeviceExtension,
      RemlockSized,
      4,
      74,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      v114.RxBandwidth,
      v114.RxPacketSize,
      v114.RxFragmentSize);
    LOBYTE(v60) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v60,
      v61,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      75,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
    if ( MiniportContext->Sco.NumChannels )
    {
      v77 = 0;
    }
    else
    {
      LOBYTE(v62) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v62,
        v63,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        76,
        (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
      UsbBusInterface = BthUsb_ScoGetUsbBusInterface(MiniportContext);
      if ( UsbBusInterface < 0 )
      {
        LOBYTE(v64) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v64,
          v65,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          77,
          (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        goto LABEL_172;
      }
      v67 = 0;
      UsbBusInterface = ResourceQueue_Initialize(
                          (int)MiniportContext + 312,
                          MiniportContext->Sco.UsbAltSetting->AllocWriteTransferCtxImpl,
                          v65,
                          v66,
                          RemlockSizee,
                          (__int64)MiniportContext);
      if ( UsbBusInterface < 0 )
      {
        LOBYTE(v68) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v68,
          v69,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          12,
          (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
        BthUsb_ScoFreeWriteResources(MiniportContext);
        LOBYTE(v70) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v70,
          v71,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          78,
          (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        goto LABEL_157;
      }
      v72 = 1;
      UsbBusInterface = BthUsb_ScoInitReadResources(MiniportContext);
      if ( UsbBusInterface < 0 )
      {
        LOBYTE(v73) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v73,
          v74,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          79,
          (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        goto LABEL_155;
      }
      UsbBusInterface = IoAcquireRemoveLockEx(
                          &MiniportContext->RemoveLock,
                          BthUsb_ScoAddChannel,
                          "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousb.cpp",
                          0x8F9u,
                          0x20u);
      if ( UsbBusInterface < 0 )
      {
        LOBYTE(v75) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v75,
          v76,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          80,
          (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
LABEL_153:
        BthUsb_ScoFreeReadResources(MiniportContext);
LABEL_155:
        BthUsb_ScoFreeWriteResources(MiniportContext);
        goto LABEL_156;
      }
      v77 = 1;
    }
    BthUsb_ScoStopUsbTraffic(MiniportContext);
    v78 = (char)v111;
    UsbBusInterface = BthUsb_ScoSelectInterface(MiniportContext, v111);
    if ( UsbBusInterface >= 0 )
    {
      *v18 = v114;
      MiniportContext->Sco.NumChannels = v117;
      BthUsb_ScoUpdateChannelsInfo(MiniportContext);
      BthUsb_ScoUpdateWriteResources(MiniportContext);
      BthUsb_ScoStartUsbTraffic(MiniportContext);
      UsbBusInterface = 0;
      goto LABEL_172;
    }
    LOBYTE(v79) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v79,
      v80,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      81,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      v78);
    v81 = v77;
    LOBYTE(v115) = v77;
    v72 = v77;
    v67 = 1;
    if ( !v81 )
    {
LABEL_156:
      if ( !v72 )
      {
LABEL_158:
        if ( v67 )
          BthUsb_ScoStartUsbTraffic(MiniportContext);
        if ( (_BYTE)v115 )
          IoReleaseRemoveLockEx(&MiniportContext->RemoveLock, BthUsb_ScoAddChannel, 0x20u);
        goto LABEL_172;
      }
LABEL_157:
      BthUsb_ScoReleaseUsbBusInterface(MiniportContext);
      goto LABEL_158;
    }
    goto LABEL_153;
  }
  LOBYTE(v33) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v33,
    v34,
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    4,
    66,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
  if ( (unsigned int)dword_140013000 > 2 )
  {
    v11 = qword_140013018;
    if ( (qword_140013010 & 0x400000000000LL) != 0 && (qword_140013018 & 0x400000000000LL) == qword_140013018 )
    {
      RealMaxFrameSize = v115;
      MaxFrameSize = v118;
      LOWORD(v115) = v117;
      v106 = *((_DWORD *)a2 + 3);
      v105 = *((_DWORD *)a2 + 2);
      v104 = MiniportContext->Sco.MaxFrameSize;
      v83 = MiniportContext->Sco.MaxInterface;
      v108 = v24;
      v107 = v99;
      v84 = v83->bAlternateSetting;
      v103 = MiniportContext->Sco.RealMaxFrameSize;
      v85 = MiniportContext->Sco.RealMaxInterface;
      LOWORD(v116) = v84;
      v113 = (__int64)MiniportContext;
      v117 = v85->bAlternateSetting;
      v86 = MiniportContext->DeviceDescriptor;
      LOWORD(v118) = v86->idProduct;
      LOWORD(v99) = v86->idVendor;
      WORD2(v99) = v86->bcdUSB;
      v112 = 33556480;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v86,
        (unsigned int)&unk_140010F40,
        v13,
        v82,
        (__int64)&v112,
        (__int64)&v113,
        (__int64)&v99 + 4,
        (__int64)&v99,
        (__int64)&v118,
        (__int64)&v117,
        (__int64)&v103,
        (__int64)&v116,
        (__int64)&v104,
        (__int64)&v105,
        (__int64)&v106,
        (__int64)&v107,
        (__int64)&v107 + 4,
        (__int64)&v108,
        (__int64)&v115,
        (__int64)&MaxFrameSize,
        (__int64)&RealMaxFrameSize);
    }
  }
  UsbBusInterface = -1073741670;
LABEL_172:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v7 = 0;
  LOBYTE(v11) = v7;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v11,
    v13,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    82,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    UsbBusInterface);
  if ( p_ChannelMutex )
  {
    ExReleasePushLockExclusiveEx(p_ChannelMutex, 0);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)UsbBusInterface;
}

```

## disassembly

```asm
0x1400030e0  push    rbp
0x1400030e2  push    rbx
0x1400030e3  push    rsi
0x1400030e4  push    rdi
0x1400030e5  push    r12
0x1400030e7  push    r13
0x1400030e9  push    r14
0x1400030eb  push    r15
0x1400030ed  lea     rbp, [rsp-78h]
0x1400030f2  sub     rsp, 1A8h
0x1400030f9  mov     r15, rdx
0x1400030fc  mov     rsi, rcx
0x1400030ff  xor     edx, edx; Val
0x140003101  lea     rcx, [rbp+0B0h+var_E0]; void *
0x140003105  mov     r8d, 98h; Size
0x14000310b  call    memset
0x140003110  xor     ebx, ebx
0x140003112  mov     rcx, cs:WPP_GLOBAL_Control
0x140003119  lea     edi, [rbx+1]
0x14000311c  mov     eax, [rcx+2Ch]
0x14000311f  test    al, 8
0x140003121  jz      short loc_14000312E
0x140003123  cmp     byte ptr [rcx+29h], 4
0x140003127  jb      short loc_14000312E
0x140003129  mov     dl, dil
0x14000312c  jmp     short loc_140003130
0x14000312e  xor     dl, dl
0x140003130  movzx   eax, word ptr [r15+4]
0x140003135  mov     r9, [rcx+40h]
0x140003139  mov     rcx, [rcx+18h]
0x14000313d  mov     dword ptr [rsp+1E0h+var_198], eax
0x140003141  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140003148  mov     [rsp+1E0h+var_1A0], rsi
0x14000314d  mov     [rsp+1E0h+var_1A8], rax
0x140003152  mov     word ptr [rsp+1E0h+var_1B0], 38h ; '8'
0x140003159  mov     dword ptr [rsp+1E0h+var_1B8], 4
0x140003161  call    WPP_RECORDER_AND_TRACE_SF_qD
0x140003166  mov     r14, [rsi]
0x140003169  mov     r12d, [r15+8]
0x14000316d  mov     rcx, r14
0x140003170  mov     r13d, [r15+0Ch]
0x140003174  call    IsAlignDataCapable
0x140003179  movzx   r9d, byte ptr [r15+28h]
0x14000317e  movzx   r8d, al
0x140003182  test    r9b, r9b
0x140003185  jz      short loc_1400031A1
0x140003187  test    al, al
0x140003189  jz      short loc_1400031A1
0x14000318b  mov     eax, 0F230h
0x140003190  mov     byte ptr [rbp+0B0h+arg_0], dil
0x140003197  mov     [r15+8], eax
0x14000319b  mov     [r15+0Ch], eax
0x14000319f  jmp     short loc_1400031A7
0x1400031a1  mov     byte ptr [rbp+0B0h+arg_0], bl
0x1400031a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400031ae  mov     eax, [rcx+2Ch]
0x1400031b1  test    al, 8
0x1400031b3  jz      short loc_1400031C0
0x1400031b5  cmp     byte ptr [rcx+29h], 4
0x1400031b9  jb      short loc_1400031C0
0x1400031bb  mov     dl, dil
0x1400031be  jmp     short loc_1400031C2
0x1400031c0  xor     dl, dl
0x1400031c2  mov     eax, [r15+0Ch]
0x1400031c6  mov     dword ptr [rsp+1E0h+var_178], eax
0x1400031ca  mov     eax, [r15+8]
0x1400031ce  mov     dword ptr [rsp+1E0h+var_180], r13d
0x1400031d3  mov     dword ptr [rsp+1E0h+var_188], eax
0x1400031d7  mov     dword ptr [rsp+1E0h+var_190], r12d
0x1400031dc  mov     dword ptr [rsp+1E0h+var_198], r8d
0x1400031e1  mov     dword ptr [rsp+1E0h+var_1A0], r9d
0x1400031e6  mov     r9, [rcx+40h]
0x1400031ea  mov     rcx, [rcx+18h]
0x1400031ee  call    WPP_RECORDER_AND_TRACE_SF_DDLLLL
0x1400031f3  mov     r8d, 30h ; '0'; unsigned int
0x1400031f9  mov     rdx, r15; void *
0x1400031fc  mov     rcx, rsi; struct _BTDEVICE *
0x1400031ff  call    ?BthUsb_ScoBasicValidation@@YAJPEAU_BTDEVICE@@PEAXK@Z; BthUsb_ScoBasicValidation(_BTDEVICE *,void *,ulong)
0x140003204  mov     esi, eax
0x140003206  test    eax, eax
0x140003208  js      loc_140003FFB
0x14000320e  cmp     [r15+10h], ebx
0x140003212  jz      short loc_140003269
0x140003214  mov     rcx, cs:WPP_GLOBAL_Control
0x14000321b  mov     eax, [rcx+2Ch]
0x14000321e  test    al, 8
0x140003220  jz      short loc_14000322D
0x140003222  cmp     byte ptr [rcx+29h], 2
0x140003226  jb      short loc_14000322D
0x140003228  mov     dl, dil
0x14000322b  jmp     short loc_14000322F
0x14000322d  xor     dl, dl
0x14000322f  lea     r15, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140003236  mov     [rsp+1E0h+var_1A8], r15
0x14000323b  mov     word ptr [rsp+1E0h+var_1B0], 3Ah ; ':'
0x140003242  mov     r9, [rcx+40h]
0x140003246  mov     r12d, 4
0x14000324c  mov     rcx, [rcx+18h]
0x140003250  mov     dword ptr [rsp+1E0h+var_1B8], r12d
0x140003255  mov     byte ptr [rsp+1E0h+RemlockSize], 2
0x14000325a  call    WPP_RECORDER_AND_TRACE_SF_
0x14000325f  mov     esi, 0C000000Dh
0x140003264  jmp     loc_140004008
0x140003269  cmp     [r15+18h], rbx
0x14000326d  jnz     short loc_14000329F
0x14000326f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003276  mov     eax, [rcx+2Ch]
0x140003279  test    al, 8
0x14000327b  jz      short loc_140003288
0x14000327d  cmp     byte ptr [rcx+29h], 2
0x140003281  jb      short loc_140003288
0x140003283  mov     dl, dil
0x140003286  jmp     short loc_14000328A
0x140003288  xor     dl, dl
0x14000328a  lea     r15, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140003291  mov     [rsp+1E0h+var_1A8], r15
0x140003296  mov     word ptr [rsp+1E0h+var_1B0], 3Bh ; ';'
0x14000329d  jmp     short loc_140003242
0x14000329f  mov     esi, 0FFFFh
0x1400032a4  cmp     si, [r15+4]
0x1400032a9  jnz     short loc_1400032DE
0x1400032ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032b2  mov     eax, [rcx+2Ch]
0x1400032b5  test    al, 8
0x1400032b7  jz      short loc_1400032C4
0x1400032b9  cmp     byte ptr [rcx+29h], 2
0x1400032bd  jb      short loc_1400032C4
0x1400032bf  mov     dl, dil
0x1400032c2  jmp     short loc_1400032C6
0x1400032c4  xor     dl, dl
0x1400032c6  lea     r15, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400032cd  mov     [rsp+1E0h+var_1A8], r15
0x1400032d2  mov     word ptr [rsp+1E0h+var_1B0], 3Ch ; '<'
0x1400032d9  jmp     loc_140003242
0x1400032de  lea     rbx, [r14+130h]
0x1400032e5  call    cs:__imp_KeEnterCriticalRegion
0x1400032ec  nop     dword ptr [rax+rax+00h]
0x1400032f1  xor     edx, edx
0x1400032f3  mov     rcx, rbx
0x1400032f6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400032fd  nop     dword ptr [rax+rax+00h]
0x140003302  movzx   r8d, word ptr [r14+2ACh]
0x14000330a  add     r8w, di
0x14000330e  mov     [rbp+0B0h+arg_10], r8w
0x140003316  mov     rcx, cs:WPP_GLOBAL_Control
0x14000331d  mov     r12d, 4
0x140003323  mov     eax, [rcx+2Ch]
0x140003326  test    al, 8
0x140003328  jz      short loc_140003335
0x14000332a  cmp     [rcx+29h], r12b
0x14000332e  jb      short loc_140003335
0x140003330  mov     dl, dil
0x140003333  jmp     short loc_140003337
0x140003335  xor     dl, dl
0x140003337  movzx   eax, r8w
0x14000333b  lea     r9, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140003342  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x140003346  mov     [rsp+1E0h+var_1A8], r9
0x14000334b  mov     r9, [rcx+40h]
0x14000334f  mov     rcx, [rcx+18h]
0x140003353  mov     word ptr [rsp+1E0h+var_1B0], 3Dh ; '='
0x14000335a  mov     dword ptr [rsp+1E0h+var_1B8], r12d
0x14000335f  mov     byte ptr [rsp+1E0h+RemlockSize], r12b
0x140003364  call    WPP_RECORDER_AND_TRACE_SF_D
0x140003369  xor     edx, edx
0x14000336b  movzx   eax, dx
0x14000336e  imul    r13, rax, 98h
0x140003375  add     r13, 2B0h
0x14000337c  add     r13, r14
0x14000337f  cmp     [r13+0], si
0x140003384  jz      short loc_140003391
0x140003386  add     dx, di
0x140003389  cmp     dx, 3
0x14000338d  jb      short loc_14000336B
0x14000338f  jmp     short loc_140003396
0x140003391  test    r13, r13
0x140003394  jnz     short loc_1400033E5
0x140003396  mov     rcx, cs:WPP_GLOBAL_Control
0x14000339d  mov     eax, [rcx+2Ch]
0x1400033a0  test    al, 8
0x1400033a2  jz      short loc_1400033AF
0x1400033a4  cmp     byte ptr [rcx+29h], 2
0x1400033a8  jb      short loc_1400033AF
0x1400033aa  mov     dl, dil
0x1400033ad  jmp     short loc_1400033B1
0x1400033af  xor     dl, dl
0x1400033b1  mov     r9, [rcx+40h]
0x1400033b5  lea     r15, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400033bc  mov     rcx, [rcx+18h]
0x1400033c0  mov     [rsp+1E0h+var_1A8], r15
0x1400033c5  mov     word ptr [rsp+1E0h+var_1B0], 3Eh ; '>'
0x1400033cc  mov     dword ptr [rsp+1E0h+var_1B8], r12d
0x1400033d1  mov     byte ptr [rsp+1E0h+RemlockSize], 2
0x1400033d6  call    WPP_RECORDER_AND_TRACE_SF_
0x1400033db  mov     esi, 0C0000265h
0x1400033e0  jmp     loc_140004008
0x1400033e5  mov     eax, [r15+8]
0x1400033e9  lea     r8, [rbp+0B0h+arg_8]; unsigned int *
0x1400033f0  mov     [rbp+0B0h+arg_18], eax
0x1400033f6  lea     rdx, [rbp+0B0h+arg_18]; unsigned int *
0x1400033fd  mov     eax, [r15+0Ch]
0x140003401  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x140003404  mov     [rbp+0B0h+arg_8], eax
0x14000340a  call    ?BthUsb_ScoValidateChnInfo@@YAJPEAU_DEVICE_EXTENSION@@PEAK1@Z; BthUsb_ScoValidateChnInfo(_DEVICE_EXTENSION *,ulong *,ulong *)
0x14000340f  mov     esi, eax
0x140003411  test    eax, eax
0x140003413  js      loc_140004001
0x140003419  mov     rcx, cs:WPP_GLOBAL_Control
0x140003420  mov     eax, [rcx+2Ch]
0x140003423  test    al, 8
0x140003425  jz      short loc_140003432
0x140003427  cmp     [rcx+29h], r12b
0x14000342b  jb      short loc_140003432
0x14000342d  mov     dl, dil
0x140003430  jmp     short loc_140003434
0x140003432  xor     dl, dl
0x140003434  mov     eax, [rbp+0B0h+arg_18]
0x14000343a  mov     esi, [rbp+0B0h+arg_8]
0x140003440  mov     r9, [rcx+40h]
0x140003444  mov     rcx, [rcx+18h]
0x140003448  mov     dword ptr [rsp+1E0h+var_198], esi
0x14000344c  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x140003450  mov     dword ptr [rbp+0B0h+var_130], eax
0x140003453  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x14000345a  mov     [rsp+1E0h+var_1A8], rax
0x14000345f  mov     word ptr [rsp+1E0h+var_1B0], 3Fh ; '?'
0x140003466  mov     dword ptr [rsp+1E0h+var_1B8], r12d
0x14000346b  mov     dword ptr [rbp+0B0h+var_130+4], esi
0x14000346e  call    WPP_RECORDER_AND_TRACE_SF_LL
0x140003473  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x140003476  call    ?BthUsb_ScoGetMaxUsedBw@@YAKPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoGetMaxUsedBw(_DEVICE_EXTENSION *)
0x14000347b  mov     r8d, dword ptr [rbp+0B0h+var_130]
0x14000347f  mov     ecx, eax
0x140003481  movzx   r9d, [rbp+0B0h+arg_10]
0x140003489  cmp     eax, r8d
0x14000348c  mov     r12d, eax
0x14000348f  mov     eax, 10624DD3h
0x140003494  cmovb   ecx, r8d
0x140003498  cmp     ecx, esi
0x14000349a  cmovb   ecx, esi
0x14000349d  mul     ecx
0x14000349f  shr     edx, 6
0x1400034a2  imul    r9d, edx
0x1400034a6  inc     r9d
0x1400034a9  mov     [rbp+0B0h+arg_18], r9d
0x1400034b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034b7  mov     eax, [rcx+2Ch]
0x1400034ba  test    al, 8
0x1400034bc  jz      short loc_1400034C9
0x1400034be  cmp     byte ptr [rcx+29h], 4
0x1400034c2  jb      short loc_1400034C9
0x1400034c4  mov     dl, dil
0x1400034c7  jmp     short loc_1400034CB
0x1400034c9  xor     dl, dl
0x1400034cb  mov     dword ptr [rsp+1E0h+var_188], r9d
0x1400034d0  mov     r9, [rcx+40h]
0x1400034d4  mov     rcx, [rcx+18h]
0x1400034d8  mov     dword ptr [rsp+1E0h+var_190], esi
0x1400034dc  mov     dword ptr [rsp+1E0h+var_198], r8d
0x1400034e1  mov     dword ptr [rsp+1E0h+var_1A0], r12d
0x1400034e6  mov     word ptr [rsp+1E0h+var_1B0], 40h ; '@'
0x1400034ed  call    WPP_RECORDER_AND_TRACE_SF_LLLL
0x1400034f2  cmp     byte ptr [rbp+0B0h+arg_0], 0
0x1400034f9  jz      short loc_140003504
0x1400034fb  test    r12d, r12d
0x1400034fe  setnz   sil
0x140003502  jmp     short loc_14000350F
0x140003504  xor     al, al
0x140003506  cmp     r12d, edi
0x140003509  movzx   esi, al
0x14000350c  cmovz   esi, edi
0x14000350f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003516  mov     eax, [rcx+2Ch]
0x140003519  test    al, 8
0x14000351b  jz      short loc_140003528
0x14000351d  cmp     byte ptr [rcx+29h], 4
0x140003521  jb      short loc_140003528
0x140003523  mov     dl, dil
0x140003526  jmp     short loc_14000352A
0x140003528  xor     dl, dl
0x14000352a  mov     r9, [rcx+40h]
0x14000352e  mov     rcx, [rcx+18h]
0x140003532  movzx   eax, sil
0x140003536  mov     dword ptr [rsp+1E0h+var_198], r12d
0x14000353b  mov     [rbp+0B0h+arg_0], eax
0x140003541  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x140003545  call    WPP_RECORDER_AND_TRACE_SF_lL
0x14000354a  mov     edx, [rbp+0B0h+arg_18]; unsigned int
0x140003550  lea     r8, [rbp+0B0h+arg_8]; unsigned int *
0x140003557  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x14000355a  mov     [rbp+0B0h+arg_8], 0
0x140003564  call    ?BthUsb_ScoFindInterfaceByFrame@@YAPEAU_USB_INTERFACE_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@KPEAK@Z; BthUsb_ScoFindInterfaceByFrame(_DEVICE_EXTENSION *,ulong,ulong *)
0x140003569  mov     [rbp+0B0h+var_F8], rax
0x14000356d  test    rax, rax
0x140003570  jz      loc_140003E0C
0x140003576  test    sil, sil
0x140003579  jnz     loc_140003E0C
0x14000357f  mov     byte ptr [rbp+0B0h+arg_0], sil
0x140003586  mov     r8, cs:WPP_GLOBAL_Control
0x14000358d  mov     ecx, [r8+2Ch]
  ... truncated ...
```
