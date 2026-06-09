# SMPDib_HandleAuthenticateResponseIrp(_SMP_INTERFACE *,DEVICE_INFO_BLOCK *,_IRP *,_IRP *,ulong *)

- ea: `0x1401523a0`
- end: `0x140153195`
- name: `?SMPDib_HandleAuthenticateResponseIrp@@YAJPEAU_SMP_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@PEAU_IRP@@2PEAK@Z`
- size: `3573`
- prototype: `int(struct _SMP_INTERFACE *, struct DEVICE_INFO_BLOCK *, struct _IRP *, struct _IRP *, unsigned int *)`
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1401f2dd8`

## callees

- `0x14000113c`
- `0x140003bb0`
- `0x14000425c`
- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x14001dc88`
- `0x14001fddc`
- `0x1400202d8`
- `0x140041f28`
- `0x140070500`
- `0x1400a6b84`
- `0x1400b9d78`
- `0x140150180`
- `0x1401505a4`
- `0x140150984`
- `0x140150b80`
- `0x1401523a0`
- `0x1401559e0`
- `0x140155ab8`
- `0x140155cf8`
- `0x140155d70`
- `0x140155e04`
- `0x140155e30`
- `0x140161a44`
- `0x140161d7c`
- `0x140162008`
- `0x14016235c`
- `0x140165540`
- `0x140165940`
- `0x1401f45a8`
- `0x1401f5fbc`
- `0x1401fef6c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140152508`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140152c48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140152508`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140152c48`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401524fc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140152c3c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401524fc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140152c3c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14015246a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14015246a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140152457`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140152457`
- `ntoskrnl!KeSetTimer` at `0x1401527e7`
- `ntoskrnl!KeSetTimer` at `0x1401527e7`
- `ntoskrnl!RtlCompareMemory` at `0x140152707`
- `ntoskrnl!RtlCompareMemory` at `0x140152707`
- `ntoskrnl!KeDelayExecutionThread` at `0x14015307b`
- `ntoskrnl!KeDelayExecutionThread` at `0x14015307b`
- `ntoskrnl!atoi` at `0x140152dfc`
- `ntoskrnl!atoi` at `0x140152dfc`
- `ntoskrnl!KeCancelTimer` at `0x140152e9f`
- `ntoskrnl!KeCancelTimer` at `0x140152e9f`

## pseudocode

```c
__int64 __fastcall SMPDib_HandleAuthenticateResponseIrp(
        struct _SMP_INTERFACE *a1,
        struct DEVICE_INFO_BLOCK *a2,
        struct _IRP *a3,
        struct _IRP *a4,
        unsigned int *a5)
{
  struct _IRP *v5; // r12
  struct DEVICE_INFO_BLOCK *v6; // r13
  char v8; // si
  __int16 DeviceType; // ax
  _IRP::<unnamed_type_AssociatedIrp> v10; // rbx
  struct SMPDIB_CONTEXT *ContextFromDib; // rax
  int v12; // edx
  int v13; // r8d
  char v14; // r11
  struct SMPDIB_CONTEXT *v15; // r15
  PDEVICE_OBJECT v16; // rcx
  int v17; // r14d
  int v18; // r8d
  __int16 v19; // ax
  __int64 *v20; // rdx
  int v22; // edx
  int v23; // r8d
  PDEVICE_OBJECT v24; // rcx
  __int16 v25; // ax
  int v26; // edx
  int v27; // r8d
  __int16 v28; // ax
  __int128 *v29; // rax
  DEVICE_EXTENSION *DevExt; // rcx
  __int128 v31; // xmm0
  unsigned __int64 v32; // rax
  struct HCI_INTERFACE *Hci; // rcx
  struct _HCI_CONNECTION *ConnectionFromBdAddrEx2; // rax
  __int64 v35; // rdi
  union _LARGE_INTEGER v36; // r8
  int v37; // r9d
  struct _BTH_AUTHENTICATION_CONTEXT *v38; // rcx
  int v39; // eax
  int v40; // edx
  char v41; // r12
  PDEVICE_OBJECT v42; // rcx
  __int64 *v43; // r8
  __int64 *v44; // r8
  int v45; // eax
  __int64 *v46; // r8
  struct _IRP *v47; // rdi
  struct _IRP *v48; // rbx
  __int64 *v49; // r8
  char v50; // di
  __int64 *v51; // r8
  int v52; // edx
  PDEVICE_OBJECT v53; // rcx
  __int64 *v54; // r8
  __int64 *v55; // r8
  unsigned __int8 *v56; // rdx
  unsigned __int8 *v57; // r8
  unsigned __int8 v58; // cl
  int v59; // edx
  int v60; // r8d
  __int16 v61; // ax
  struct _SMP_INTERFACE *v62; // rdi
  unsigned __int8 v63; // al
  unsigned __int64 MdlAddress; // rdx
  DEVICE_EXTENSION *v65; // rax
  int v66; // edx
  __int64 *v67; // r8
  int v68; // edx
  __int64 *v69; // r8
  _MDL *v70; // rax
  struct DEVICE_EXTENSION **p_DevExt; // rbx
  struct DEVICE_EXTENSION *v72; // rcx
  struct _HCI_CONNECTION *v73; // rax
  struct _IRP *v74; // rdi
  __int16 v75; // [rsp+30h] [rbp-D0h]
  __int16 v76; // [rsp+30h] [rbp-D0h]
  __int16 v77; // [rsp+30h] [rbp-D0h]
  __int16 v78; // [rsp+30h] [rbp-D0h]
  char v79; // [rsp+40h] [rbp-C0h]
  char v80; // [rsp+60h] [rbp-A0h]
  bool v81; // [rsp+61h] [rbp-9Fh]
  unsigned __int8 v82; // [rsp+62h] [rbp-9Eh] BYREF
  char v83[5]; // [rsp+63h] [rbp-9Dh] BYREF
  union _LARGE_INTEGER Interval; // [rsp+68h] [rbp-98h] BYREF
  struct _SMP_INTERFACE *v85; // [rsp+70h] [rbp-90h]
  _QWORD v86[2]; // [rsp+78h] [rbp-88h] BYREF
  GUID ActivityId; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v88; // [rsp+98h] [rbp-68h] BYREF
  char *v89; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v90; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v91; // [rsp+B0h] [rbp-50h] BYREF
  struct _IRP *v92; // [rsp+B8h] [rbp-48h]
  struct _BTH_LE_SMP_PDU v93; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 v94[16]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int8 v95[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v96; // [rsp+130h] [rbp+30h] BYREF

  v82 = 0;
  v5 = a3;
  v92 = a3;
  v6 = a2;
  v85 = a1;
  v8 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
  {
    LOBYTE(a3) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      v6->IfrLog,
      5,
      10,
      234,
      (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
  }
  *a5 = 0;
  v10.MasterIrp = (_IRP *)v5->AssociatedIrp;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(&v6->ProtocolsLock);
  ContextFromDib = SmpDib_GetContextFromDib(v6, HciPhyTypeLE);
  v14 = 0;
  v15 = ContextFromDib;
  if ( ContextFromDib )
  {
    if ( !*((_BYTE *)ContextFromDib + 57) )
    {
      if ( !SmpDib_IsStateExpectingAuthenticationResponse(ContextFromDib) )
      {
        v16 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
          || (LOBYTE(v12) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        {
          LOBYTE(v12) = v14;
        }
        v75 = 237;
        goto LABEL_13;
      }
      if ( *(_DWORD *)&v10.MasterIrp[4].Type == 2 )
      {
        if ( *((_DWORD *)v15 + 228) != 2 )
        {
          v24 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
            || (LOBYTE(v12) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          {
            LOBYTE(v12) = v14;
          }
          v76 = 238;
          goto LABEL_41;
        }
        if ( RtlCompareMemory((char *)v15 + 981, &v10.MasterIrp[4].CancelIrql, 0x10u) != 16 )
        {
          v24 = WPP_GLOBAL_Control;
          LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          v76 = 239;
LABEL_41:
          LOBYTE(v13) = 1;
          WPP_RECORDER_AND_TRACE_SF_(
            v24->AttachedDevice,
            v12,
            v13,
            v6->IfrLog,
            2,
            10,
            v76,
            (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
LABEL_42:
          v17 = -1073741811;
          goto LABEL_14;
        }
        v14 = 0;
      }
    }
    if ( *(_DWORD *)&v10.MasterIrp[4].Type == 1
      && (LOBYTE(v10.MasterIrp[4].Reserved2) > 6u || BYTE2(v10.MasterIrp[4].MdlAddress) != v14) )
    {
      LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      v25 = WPP_GLOBAL_Control->DeviceType;
      if ( (_BYTE)v12 || v25 )
      {
        LOBYTE(v13) = v25 != 0;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          v13,
          v6->IfrLog,
          5,
          10,
          240,
          (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
      }
      goto LABEL_42;
    }
    v80 = v14;
    v81 = v14;
    if ( !KeSetTimer((PKTIMER)((char *)v15 + 1784), (LARGE_INTEGER)-300000000LL, (PKDPC)((char *)v15 + 1720)) )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v26) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
        LOBYTE(v26) = 0;
      v28 = WPP_GLOBAL_Control->DeviceType;
      if ( (_BYTE)v26 || v28 )
      {
        LOBYTE(v27) = v28 != 0;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v26,
          v27,
          *(_QWORD *)(*((_QWORD *)v15 + 1) + 2104LL),
          5,
          10,
          12,
          (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
          (char)v15);
      }
      RefObj_AddRefEx(
        (char *)v15 + 16,
        SMPDibContext_TimeoutDPC,
        363,
        "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp");
    }
    *(_OWORD *)v94 = 0;
    v29 = (__int128 *)BthGetActivityID(&ActivityId);
    DevExt = a1->DevExt;
    v31 = *v29;
    Interval.LowPart = (unsigned int)v10.MasterIrp->MdlAddress;
    v32 = (unsigned __int64)v10.MasterIrp->MdlAddress >> 32;
    *(_OWORD *)v94 = v31;
    Hci = DevExt->Hci;
    WORD2(Interval.QuadPart) = v32;
    ConnectionFromBdAddrEx2 = HCI_GetConnectionFromBdAddrEx2(
                                Hci,
                                (struct _BDADDR *)&Interval,
                                6451,
                                "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp",
                                SMPDib_HandleAuthenticateResponseIrp,
                                1,
                                HciPhyTypeLE);
    __0__RefObjReference_UREAD_CONNECTED_RSSI_CONTEXT___0A__M__T0A__M__T0A___QEAA_PEAUREAD_CONNECTED_RSSI_CONTEXT__PEBX_Z(
      &ActivityId,
      ConnectionFromBdAddrEx2,
      SMPDib_HandleAuthenticateResponseIrp);
    v35 = *(_QWORD *)ActivityId.Data4;
    v36.QuadPart = 0;
    if ( *(_QWORD *)ActivityId.Data4 )
    {
      if ( (unsigned int)dword_140197150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140197150, 0x400000000003LL) )
      {
        Interval = (union _LARGE_INTEGER)v10.MasterIrp->MdlAddress;
        v88 = v94;
        v89 = (char *)v15 + 1848;
        v83[0] = *(_BYTE *)(v35 + 96);
        v90 = v35 + 1304;
        v91 = **(_QWORD **)v15 + 720LL;
        v86[0] = 50333696;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
          v91,
          (unsigned int)byte_14018BEDB,
          v36.LowPart,
          v37,
          (__int64)v86,
          (__int64)&v91,
          (__int64)&v90,
          (__int64)v83,
          (__int64)&v89,
          (__int64)&v88,
          (__int64)&Interval);
        v36.QuadPart = 0;
      }
      Interval = v36;
      wil::acquire_kspin_lock(v86, v35 + 80);
      v38 = *(struct _BTH_AUTHENTICATION_CONTEXT **)(v35 + 720);
      if ( v38 && HCI_StopAuthenticationTimer(v38) )
      {
        wil::details::unique_storage<wil::details::resource_policy<_BTH_AUTHENTICATION_CONTEXT *,void (*)(_BTH_AUTHENTICATION_CONTEXT *),&void HCI_DeleteAuthenticationContext(_BTH_AUTHENTICATION_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_BTH_AUTHENTICATION_CONTEXT *,_BTH_AUTHENTICATION_CONTEXT *,0,std::nullptr_t>>::reset(
          &Interval,
          *(_QWORD *)(v35 + 720));
        *(_QWORD *)(v35 + 720) = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v86);
      _Reset___RefObjReference_U_HCI_CONNECTION___07_M__T0A__M__T0A___QEAAXPEAU_HCI_CONNECTION__PEBX_Z(
        &ActivityId,
        0,
        0);
      wil::details::unique_storage<wil::details::resource_policy<_BTH_AUTHENTICATION_CONTEXT *,void (*)(_BTH_AUTHENTICATION_CONTEXT *),&void HCI_DeleteAuthenticationContext(_BTH_AUTHENTICATION_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_BTH_AUTHENTICATION_CONTEXT *,_BTH_AUTHENTICATION_CONTEXT *,0,std::nullptr_t>>::reset(
        &Interval,
        0);
      wil::details::unique_storage<wil::details::resource_policy<_BTH_AUTHENTICATION_CONTEXT *,void (*)(_BTH_AUTHENTICATION_CONTEXT *),&void HCI_DeleteAuthenticationContext(_BTH_AUTHENTICATION_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_BTH_AUTHENTICATION_CONTEXT *,_BTH_AUTHENTICATION_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_BTH_AUTHENTICATION_CONTEXT *,void (*)(_BTH_AUTHENTICATION_CONTEXT *),&void HCI_DeleteAuthenticationContext(_BTH_AUTHENTICATION_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_BTH_AUTHENTICATION_CONTEXT *,_BTH_AUTHENTICATION_CONTEXT *,0,std::nullptr_t>>(&Interval);
    }
    _Reset___RefObjReference_U_HCI_CONNECTION___07_M__T0A__M__T0A___QEAAXPEAU_HCI_CONNECTION__PEBX_Z(&ActivityId, 0, 0);
    v39 = BthEnqueueAuthenticateIrp(a1->DevExt, v5, 0, 0, 0);
    v17 = v39;
    if ( v39 < 0 )
    {
      v41 = 0;
      v42 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v40) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v40) = 0;
      v79 = v39;
      v43 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
      v77 = 241;
LABEL_81:
      LOBYTE(v43) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        v42->AttachedDevice,
        v40,
        (_DWORD)v43,
        v6->IfrLog,
        2,
        10,
        v77,
        (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
        v79);
LABEL_132:
      v50 = v80;
      goto LABEL_133;
    }
    *((_QWORD *)v15 + 133) = v5;
    v41 = 1;
    if ( *((_BYTE *)v15 + 57) )
    {
      if ( v10.MasterIrp[4].Tail.Apc.Type )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
          || (LOBYTE(v40) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        {
          LOBYTE(v40) = 0;
        }
        v44 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        LOBYTE(v44) = 1;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v40,
          (_DWORD)v44,
          *(_QWORD *)(*((_QWORD *)v15 + 1) + 2104LL),
          2,
          10,
          242,
          (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
        v17 = -1073741198;
        if ( *(_DWORD *)&v10.MasterIrp[4].Type != 3 )
          v17 = -1073741117;
LABEL_109:
        v50 = 1;
        v81 = *((_BYTE *)v15 + 1864) == 0;
LABEL_133:
        if ( KeCancelTimer((PKTIMER)((char *)v15 + 1784)) )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
            || (LOBYTE(v59) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
          {
            LOBYTE(v59) = 0;
          }
          v61 = WPP_GLOBAL_Control->DeviceType;
          if ( (_BYTE)v59 || v61 )
          {
            LOBYTE(v60) = v61 != 0;
            WPP_RECORDER_AND_TRACE_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              v59,
              v60,
              *(_QWORD *)(*((_QWORD *)v15 + 1) + 2104LL),
              5,
              10,
              13,
              (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
              (char)v15);
          }
          RefObj_ReleaseEx(
            (char *)v15 + 16,
            SMPDibContext_TimeoutDPC,
            376,
            "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp");
        }
        SMPDIB_SET_STATE(v15, SmpFailed);
        if ( v50 )
          BthReportError_BthAddr(
            v85->DevExt,
            1074069541,
            0xEu,
            0,
            0,
            (unsigned __int16)WORD2(*(_QWORD *)(*((_QWORD *)v15 + 1) + 32LL)),
            *(_DWORD *)(*((_QWORD *)v15 + 1) + 32LL));
        if ( v81 )
        {
          v62 = *(struct _SMP_INTERFACE **)v15;
          v93.OpCode = 5;
          memset(&v93.OpCode + 1, 0, 71);
          v63 = SmpErrorFromNtStatus(v17);
          MdlAddress = (unsigned __int64)v10.MasterIrp->MdlAddress;
          v93.PairingRequest.IOCapability = v63;
          if ( SMPInt_SendPDU(v62, MdlAddress, HciPhyTypeLE, &v93, 8u) >= 0 )
          {
            v65 = v62->DevExt;
            Interval.QuadPart = 0;
            v66 = 125 * v65->Hci->LEDefaultConnectionParameters.ConnectionIntervalMax / 100;
            Interval.QuadPart = -20000 * v66;
            LOBYTE(v66) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
            v67 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
            LOBYTE(v67) = 1;
            WPP_RECORDER_AND_TRACE_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              v66,
              (_DWORD)v67,
              WPP_GLOBAL_Control->DeviceExtension,
              3,
              10,
              28,
              (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
            KeDelayExecutionThread(0, 0, &Interval);
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
              || (LOBYTE(v68) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
            {
              LOBYTE(v68) = 0;
            }
            v69 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
            LOBYTE(v69) = 1;
            WPP_RECORDER_AND_TRACE_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              v68,
              (_DWORD)v69,
              WPP_GLOBAL_Control->DeviceExtension,
              3,
              10,
              29,
              (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
          }
        }
        Interval.LowPart = (unsigned int)v10.MasterIrp->MdlAddress;
        v70 = v10.MasterIrp->MdlAddress;
        p_DevExt = &v85->DevExt;
        v72 = v85->DevExt;
        WORD2(Interval.QuadPart) = WORD2(v70);
        v73 = HCI_GetConnectionFromBdAddrEx2(
                v72->Hci,
                (struct _BDADDR *)&Interval,
                6631,
                "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp",
                0,
                1,
                HciPhyTypeLE);
        v86[0] = v73;
        if ( v73 )
        {
          SmpDib_DisconnectConnection(v73, v15, 0);
          v17 = 0;
        }
        if ( !*((_BYTE *)v15 + 1864) )
          SMPDib_ClearError(v15);
        wil::details::unique_storage<wil::details::resource_policy<_HCI_CONNECTION *,void (*)(_HCI_CONNECTION *),&void ReleaseHciConnection(_HCI_CONNECTION *),wistd::integral_constant<unsigned __int64,0>,_HCI_CONNECTION *,_HCI_CONNECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HCI_CONNECTION *,void (*)(_HCI_CONNECTION *),&void ReleaseHciConnection(_HCI_CONNECTION *),wistd::integral_constant<unsigned __int64,0>,_HCI_CONNECTION *,_HCI_CONNECTION *,0,std::nullptr_t>>(v86);
        if ( v41 )
        {
          v74 = v92;
          if ( (unsigned __int8)IrpList_DequeueIrp(&(*p_DevExt)->AuthenticateList, v92) )
            BthCompleteRequest(*p_DevExt, v74, v17);
          v17 = 259;
        }
        goto LABEL_14;
      }
      v45 = SmpDibSecureConnection::HandleAuthenticationResponse(
              v15,
              (struct _BTH_AUTHENTICATE_RESPONSE *)v10.MasterIrp,
              &v82);
      v17 = v45;
      if ( v45 < 0 )
      {
        v42 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
          || (LOBYTE(v40) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        {
          LOBYTE(v40) = 0;
        }
        v79 = v45;
        v43 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
        v77 = 243;
        goto LABEL_81;
      }
    }
    else
    {
      if ( *((_DWORD *)v15 + 13) != 1 || SmpDib_IsStateTransitionValid(v15, SmpServerPDUPairingConfirmSent) )
      {
        if ( v10.MasterIrp[4].Tail.Apc.Type )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
            || (LOBYTE(v40) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          {
            LOBYTE(v40) = 0;
          }
          v49 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
          LOBYTE(v49) = 1;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v40,
            (_DWORD)v49,
            v6->IfrLog,
            2,
            10,
            245,
            (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
          v17 = -1073741117;
          goto LABEL_109;
        }
        if ( *(_DWORD *)&v10.MasterIrp[4].Type == 1 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
            || (LOBYTE(v40) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
          {
            LOBYTE(v40) = 0;
          }
          v55 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
          LOBYTE(v55) = 1;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v40,
            (_DWORD)v55,
            v6->IfrLog,
            4,
            10,
            246,
            (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
          *(_OWORD *)v95 = 0;
          *(_DWORD *)v95 = atoi((const char *)&v10.MasterIrp[4].AllocationProcessorNumber);
          v56 = (unsigned __int8 *)&v96;
          v57 = v95;
          do
          {
            if ( v57 == --v56 )
              break;
            v58 = *v57;
            *v57++ = *v56;
            *v56 = v58;
          }
          while ( v57 != v56 );
          v17 = SMPDib_CreateAndSendConfirmPdu(v15, v95);
          if ( v17 >= 0 )
            goto LABEL_101;
          v53 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
            || (LOBYTE(v52) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          {
            LOBYTE(v52) = 0;
          }
          v54 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
          v78 = 247;
        }
        else
        {
          if ( *(_DWORD *)&v10.MasterIrp[4].Type != 2 )
            goto LABEL_101;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
            || (LOBYTE(v40) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
          {
            LOBYTE(v40) = 0;
          }
          v51 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
          LOBYTE(v51) = 1;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v40,
            (_DWORD)v51,
            v6->IfrLog,
            4,
            10,
            248,
            (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
          *(_OWORD *)v94 = *(_OWORD *)&v10.MasterIrp[4].CancelIrql;
          v17 = SMPDib_CreateAndSendConfirmPdu(v15, v94);
          if ( v17 >= 0 )
            goto LABEL_101;
          v53 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
            || (LOBYTE(v52) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          {
            LOBYTE(v52) = 0;
          }
          v54 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
          v78 = 249;
        }
        LOBYTE(v54) = 1;
        WPP_RECORDER_AND_TRACE_SF_(
          v53->AttachedDevice,
          v52,
          (_DWORD)v54,
          v6->IfrLog,
          2,
          10,
          v78,
          (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
        goto LABEL_132;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v40) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        LOBYTE(v40) = 0;
      v46 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
      LOBYTE(v46) = 1;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v40,
        (_DWORD)v46,
        v6->IfrLog,
        4,
        10,
        244,
        (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
    }
LABEL_101:
    v17 = 259;
    goto LABEL_102;
  }
  if ( *(_DWORD *)&v10.MasterIrp[4].Type != 2 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v12) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v12) = 0;
    v75 = 235;
LABEL_13:
    LOBYTE(v13) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      v16->AttachedDevice,
      v12,
      v13,
      v6->IfrLog,
      2,
      10,
      v75,
      (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
    v17 = -1073741661;
LABEL_14:
    ExReleaseFastMutexUnsafe(&v6->ProtocolsLock);
    KeLeaveCriticalRegion();
    goto LABEL_15;
  }
  v17 = BthEnqueueAuthenticateIrp(a1->DevExt, v5, 0, 0, 0);
  if ( v17 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v22) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v22) = 0;
    LOBYTE(v23) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v22,
      v23,
      v6->IfrLog,
      2,
      10,
      236,
      (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
      v17);
    goto LABEL_14;
  }
LABEL_102:
  if ( !v82 )
    goto LABEL_14;
  v47 = (struct _IRP *)_InterlockedExchange64((volatile __int64 *)v15 + 9, 0);
  v48 = (struct _IRP *)_InterlockedExchange64((volatile __int64 *)v15 + 133, 0);
  ExReleaseFastMutexUnsafe(&v6->ProtocolsLock);
  KeLeaveCriticalRegion();
  SMPDib_CompleteIrps(v6, v47, v48, v17);
  v17 = 259;
LABEL_15:
  if ( v15 )
    RefObj_ReleaseEx((char *)v15 + 16, v15, 6689, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp");
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v8 = 0;
  v19 = WPP_GLOBAL_Control->DeviceType;
  if ( v8 || v19 )
  {
    v20 = WPP_5d74b44f6a9434f108575b9e923831da_Traceguids;
    LOBYTE(v20) = v8;
    LOBYTE(v18) = v19 != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v20,
      v18,
      v6->IfrLog,
      5,
      10,
      250,
      (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
      v17);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1401523a0  push    rbp
0x1401523a2  push    rbx
0x1401523a3  push    rsi
0x1401523a4  push    rdi
0x1401523a5  push    r12
0x1401523a7  push    r13
0x1401523a9  push    r14
0x1401523ab  push    r15
0x1401523ad  lea     rbp, [rsp-48h]
0x1401523b2  sub     rsp, 148h
0x1401523b9  mov     rax, cs:__security_cookie
0x1401523c0  xor     rax, rsp
0x1401523c3  mov     [rbp+80h+var_50], rax
0x1401523c7  mov     rbx, [rbp+80h+arg_20]
0x1401523ce  xor     r15d, r15d
0x1401523d1  mov     [rsp+180h+var_11E], r15b
0x1401523d6  mov     rdi, r9
0x1401523d9  mov     r12, r8
0x1401523dc  mov     [rbp+80h+var_C8], r8
0x1401523e0  mov     r13, rdx
0x1401523e3  mov     [rsp+180h+var_110], rcx
0x1401523e8  mov     r14, rcx
0x1401523eb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401523f2  lea     esi, [r15+1]
0x1401523f6  test    dword ptr [rcx+2Ch], 200h
0x1401523fd  jz      short loc_140152408
0x1401523ff  cmp     byte ptr [rcx+29h], 5
0x140152403  mov     dl, sil
0x140152406  jnb     short loc_14015240B
0x140152408  mov     dl, r15b
0x14015240b  movzx   eax, word ptr [rcx+48h]
0x14015240f  lea     r9, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x140152416  test    ax, ax
0x140152419  setnz   r8b
0x14015241d  test    dl, dl
0x14015241f  jnz     short loc_140152426
0x140152421  test    ax, ax
0x140152424  jz      short loc_14015244F
0x140152426  mov     rcx, [rcx+18h]
0x14015242a  mov     [rsp+180h+var_148], r9
0x14015242f  mov     r9, [r13+838h]
0x140152436  mov     word ptr [rsp+180h+var_150], 0EAh
0x14015243d  mov     dword ptr [rsp+180h+var_158], 0Ah
0x140152445  mov     byte ptr [rsp+180h+var_160], 5
0x14015244a  call    WPP_RECORDER_AND_TRACE_SF_
0x14015244f  mov     [rbx], r15d
0x140152452  mov     rbx, [r12+18h]
0x140152457  call    cs:__imp_KeEnterCriticalRegion
0x14015245e  nop     dword ptr [rax+rax+00h]
0x140152463  lea     rcx, [r13+380h]; FastMutex
0x14015246a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140152471  nop     dword ptr [rax+rax+00h]
0x140152476  mov     dl, sil; enum _HCI_PHY_TYPE
0x140152479  mov     rcx, r13; struct DEVICE_INFO_BLOCK *
0x14015247c  call    ?SmpDib_GetContextFromDib@@YAPEAUSMPDIB_CONTEXT@@PEAUDEVICE_INFO_BLOCK@@W4_HCI_PHY_TYPE@@@Z; SmpDib_GetContextFromDib(DEVICE_INFO_BLOCK *,_HCI_PHY_TYPE)
0x140152481  xor     r11d, r11d
0x140152484  mov     r15, rax
0x140152487  test    rax, rax
0x14015248a  jnz     loc_140152638
0x140152490  cmp     dword ptr [rbx+340h], 2
0x140152497  jz      loc_1401525BC
0x14015249d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401524a4  test    dword ptr [rcx+2Ch], 200h
0x1401524ab  jz      short loc_1401524B6
0x1401524ad  cmp     byte ptr [rcx+29h], 2
0x1401524b1  mov     dl, sil
0x1401524b4  jnb     short loc_1401524B9
0x1401524b6  mov     dl, r11b
0x1401524b9  lea     r10, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x1401524c0  mov     [rsp+180h+var_148], r10
0x1401524c5  mov     word ptr [rsp+180h+var_150], 0EBh
0x1401524cc  mov     r9, [r13+838h]
0x1401524d3  mov     r8b, sil
0x1401524d6  mov     rcx, [rcx+18h]
0x1401524da  mov     dword ptr [rsp+180h+var_158], 0Ah
0x1401524e2  mov     byte ptr [rsp+180h+var_160], 2
0x1401524e7  call    WPP_RECORDER_AND_TRACE_SF_
0x1401524ec  mov     r14d, 0C00000A3h
0x1401524f2  xor     r12d, r12d
0x1401524f5  lea     rcx, [r13+380h]; FastMutex
0x1401524fc  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140152503  nop     dword ptr [rax+rax+00h]
0x140152508  call    cs:__imp_KeLeaveCriticalRegion
0x14015250f  nop     dword ptr [rax+rax+00h]
0x140152514  test    r15, r15
0x140152517  jz      short loc_140152532
0x140152519  lea     rcx, [r15+10h]
0x14015251d  mov     r8d, 1A21h
0x140152523  lea     r9, aOnecoreDrivers_46; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14015252a  mov     rdx, r15
0x14015252d  call    RefObj_ReleaseEx
0x140152532  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140152539  test    dword ptr [rcx+2Ch], 200h
0x140152540  jz      short loc_140152548
0x140152542  cmp     byte ptr [rcx+29h], 5
0x140152546  jnb     short loc_14015254B
0x140152548  mov     sil, r12b
0x14015254b  movzx   eax, word ptr [rcx+48h]
0x14015254f  test    ax, ax
0x140152552  setnz   r8b
0x140152556  test    sil, sil
0x140152559  jnz     short loc_140152560
0x14015255b  test    ax, ax
0x14015255e  jz      short loc_140152598
0x140152560  mov     r9, [r13+838h]
0x140152567  lea     rdx, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x14015256e  mov     rcx, [rcx+18h]
0x140152572  mov     dword ptr [rsp+180h+var_140], r14d
0x140152577  mov     [rsp+180h+var_148], rdx
0x14015257c  mov     dl, sil
0x14015257f  mov     word ptr [rsp+180h+var_150], 0FAh
0x140152586  mov     dword ptr [rsp+180h+var_158], 0Ah
0x14015258e  mov     byte ptr [rsp+180h+var_160], 5
0x140152593  call    WPP_RECORDER_AND_TRACE_SF_d
0x140152598  mov     eax, r14d
0x14015259b  mov     rcx, [rbp+80h+var_50]
0x14015259f  xor     rcx, rsp; StackCookie
0x1401525a2  call    __security_check_cookie
0x1401525a7  add     rsp, 148h
0x1401525ae  pop     r15
0x1401525b0  pop     r14
0x1401525b2  pop     r13
0x1401525b4  pop     r12
0x1401525b6  pop     rdi
0x1401525b7  pop     rsi
0x1401525b8  pop     rbx
0x1401525b9  pop     rbp
0x1401525ba  retn
0x1401525bc  mov     rcx, [r14]; struct DEVICE_EXTENSION *
0x1401525bf  xor     edi, edi
0x1401525c1  xor     r9d, r9d; unsigned __int8
0x1401525c4  mov     byte ptr [rsp+180h+var_160], dil; char
0x1401525c9  xor     r8d, r8d; struct _KEVENT *
0x1401525cc  mov     rdx, r12; struct _IRP *
0x1401525cf  call    ?BthEnqueueAuthenticateIrp@@YAJPEAUDEVICE_EXTENSION@@PEAU_IRP@@PEAU_KEVENT@@EE@Z; BthEnqueueAuthenticateIrp(DEVICE_EXTENSION *,_IRP *,_KEVENT *,uchar,uchar)
0x1401525d4  mov     r14d, eax
0x1401525d7  test    eax, eax
0x1401525d9  jns     loc_140152C19
0x1401525df  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401525e6  test    dword ptr [rax+2Ch], 200h
0x1401525ed  jz      short loc_1401525F8
0x1401525ef  cmp     byte ptr [rax+29h], 2
0x1401525f3  mov     dl, sil
0x1401525f6  jnb     short loc_1401525FB
0x1401525f8  mov     dl, dil
0x1401525fb  mov     r9, [r13+838h]
0x140152602  lea     r10, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x140152609  mov     rcx, [rax+18h]
0x14015260d  mov     r8b, sil
0x140152610  mov     dword ptr [rsp+180h+var_140], r14d
0x140152615  mov     [rsp+180h+var_148], r10
0x14015261a  mov     word ptr [rsp+180h+var_150], 0ECh
0x140152621  mov     dword ptr [rsp+180h+var_158], 0Ah
0x140152629  mov     byte ptr [rsp+180h+var_160], 2
0x14015262e  call    WPP_RECORDER_AND_TRACE_SF_d
0x140152633  jmp     loc_1401524F2
0x140152638  cmp     [rax+39h], r11b
0x14015263c  jnz     loc_140152751
0x140152642  mov     rcx, r15; struct SMPDIB_CONTEXT *
0x140152645  call    ?SmpDib_IsStateExpectingAuthenticationResponse@@YA_NPEAUSMPDIB_CONTEXT@@@Z; SmpDib_IsStateExpectingAuthenticationResponse(SMPDIB_CONTEXT *)
0x14015264a  test    al, al
0x14015264c  jnz     short loc_140152682
0x14015264e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140152655  test    dword ptr [rcx+2Ch], 200h
0x14015265c  jz      short loc_140152667
0x14015265e  cmp     byte ptr [rcx+29h], 2
0x140152662  mov     dl, sil
0x140152665  jnb     short loc_14015266A
0x140152667  mov     dl, r11b
0x14015266a  lea     r10, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x140152671  mov     [rsp+180h+var_148], r10
0x140152676  mov     word ptr [rsp+180h+var_150], 0EDh
0x14015267d  jmp     loc_1401524CC
0x140152682  cmp     dword ptr [rbx+340h], 2
0x140152689  jnz     loc_140152751
0x14015268f  cmp     dword ptr [r15+390h], 2
0x140152697  jz      short loc_1401526F3
0x140152699  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401526a0  test    dword ptr [rcx+2Ch], 200h
0x1401526a7  jz      short loc_1401526B2
0x1401526a9  cmp     byte ptr [rcx+29h], 2
0x1401526ad  mov     dl, sil
0x1401526b0  jnb     short loc_1401526B5
0x1401526b2  mov     dl, r11b
0x1401526b5  lea     r10, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x1401526bc  mov     [rsp+180h+var_148], r10
0x1401526c1  mov     word ptr [rsp+180h+var_150], 0EEh
0x1401526c8  mov     dword ptr [rsp+180h+var_158], 0Ah
0x1401526d0  mov     r8b, sil
0x1401526d3  mov     byte ptr [rsp+180h+var_160], 2
0x1401526d8  mov     r9, [r13+838h]
0x1401526df  mov     rcx, [rcx+18h]
0x1401526e3  call    WPP_RECORDER_AND_TRACE_SF_
0x1401526e8  mov     r14d, 0C000000Dh
0x1401526ee  jmp     loc_1401524F2
0x1401526f3  lea     rdx, [rbx+385h]; Source2
0x1401526fa  mov     r8d, 10h; Length
0x140152700  lea     rcx, [r15+3D5h]; Source1
0x140152707  call    cs:__imp_RtlCompareMemory
0x14015270e  nop     dword ptr [rax+rax+00h]
0x140152713  cmp     rax, 10h
0x140152717  jz      short loc_14015274E
0x140152719  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140152720  test    dword ptr [rcx+2Ch], 200h
0x140152727  jz      short loc_140152734
0x140152729  cmp     byte ptr [rcx+29h], 2
0x14015272d  jb      short loc_140152734
0x14015272f  mov     dl, sil
0x140152732  jmp     short loc_140152736
0x140152734  xor     dl, dl
0x140152736  lea     r10, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x14015273d  mov     [rsp+180h+var_148], r10
0x140152742  mov     word ptr [rsp+180h+var_150], 0EFh
0x140152749  jmp     loc_1401526C8
0x14015274e  xor     r11d, r11d
0x140152751  cmp     [rbx+340h], esi
0x140152757  jnz     short loc_1401527C8
0x140152759  cmp     byte ptr [rbx+354h], 6
0x140152760  ja      short loc_14015276B
0x140152762  cmp     [rbx+34Ah], r11b
0x140152769  jz      short loc_1401527C8
0x14015276b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140152772  test    dword ptr [rcx+2Ch], 200h
0x140152779  jz      short loc_140152786
0x14015277b  cmp     byte ptr [rcx+29h], 5
0x14015277f  jb      short loc_140152786
0x140152781  mov     dl, sil
0x140152784  jmp     short loc_14015278B
0x140152786  xor     edi, edi
0x140152788  mov     dl, dil
0x14015278b  movzx   eax, word ptr [rcx+48h]
0x14015278f  test    ax, ax
0x140152792  setnz   r8b
0x140152796  test    dl, dl
0x140152798  jnz     short loc_1401527A3
0x14015279a  test    ax, ax
0x14015279d  jz      loc_1401526E8
0x1401527a3  lea     r10, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x1401527aa  mov     [rsp+180h+var_148], r10
0x1401527af  mov     word ptr [rsp+180h+var_150], 0F0h
0x1401527b6  mov     dword ptr [rsp+180h+var_158], 0Ah
0x1401527be  mov     byte ptr [rsp+180h+var_160], 5
0x1401527c3  jmp     loc_1401526D8
0x1401527c8  lea     r8, [r15+6B8h]; Dpc
0x1401527cf  mov     [rsp+180h+var_120], r11b
0x1401527d4  lea     rcx, [r15+6F8h]; Timer
0x1401527db  mov     [rsp+180h+var_11F], r11b
0x1401527e0  mov     rdx, 0FFFFFFFFEE1E5D00h; DueTime
0x1401527e7  call    cs:__imp_KeSetTimer
0x1401527ee  nop     dword ptr [rax+rax+00h]
0x1401527f3  xor     r9d, r9d
0x1401527f6  test    al, al
0x1401527f8  jnz     loc_140152884
0x1401527fe  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140152805  test    dword ptr [rcx+2Ch], 200h
0x14015280c  jz      short loc_140152817
0x14015280e  cmp     byte ptr [rcx+29h], 5
0x140152812  mov     dl, sil
0x140152815  jnb     short loc_14015281A
0x140152817  mov     dl, r9b
0x14015281a  movzx   eax, word ptr [rcx+48h]
0x14015281e  test    ax, ax
0x140152821  setnz   r8b
0x140152825  test    dl, dl
0x140152827  jnz     short loc_14015282E
0x140152829  test    ax, ax
0x14015282c  jz      short loc_140152867
0x14015282e  mov     r9, [r15+8]
0x140152832  lea     r10, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x140152839  mov     rcx, [rcx+18h]
0x14015283d  mov     [rsp+180h+var_140], r15
0x140152842  mov     [rsp+180h+var_148], r10
0x140152847  mov     r9, [r9+838h]
0x14015284e  mov     word ptr [rsp+180h+var_150], 0Ch
0x140152855  mov     dword ptr [rsp+180h+var_158], 0Ah
0x14015285d  mov     byte ptr [rsp+180h+var_160], 5
0x140152862  call    WPP_RECORDER_AND_TRACE_SF_q
0x140152867  lea     rcx, [r15+10h]
0x14015286b  mov     r8d, 16Bh
0x140152871  lea     r9, aOnecoreDrivers_46; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140152878  lea     rdx, ?SMPDibContext_TimeoutDPC@@YAXPEAU_KDPC@@PEAX11@Z; SMPDibContext_TimeoutDPC(_KDPC *,void *,void *,void *)
0x14015287f  call    RefObj_AddRefEx
0x140152884  xorps   xmm0, xmm0
0x140152887  lea     rcx, [rbp+80h+ActivityId]; ActivityId
0x14015288b  mov     rdx, rdi
0x14015288e  movups  xmmword ptr [rbp+80h+var_70], xmm0
0x140152892  call    BthGetActivityID
0x140152897  mov     rcx, [r14]
0x14015289a  lea     rdi, ?SMPDib_HandleAuthenticateResponseIrp@@YAJPEAU_SMP_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@PEAU_IRP@@2PEAK@Z; SMPDib_HandleAuthenticateResponseIrp(_SMP_INTERFACE *,DEVICE_INFO_BLOCK *,_IRP *,_IRP *,ulong *)
0x1401528a1  mov     [rsp+180h+var_150], sil; enum _HCI_PHY_TYPE
0x1401528a6  lea     r9, aOnecoreDrivers_46; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1401528ad  mov     [rsp+180h+var_158], sil; char
0x1401528b2  lea     rdx, [rsp+180h+Interval]; struct _BDADDR *
0x1401528b7  movups  xmm0, xmmword ptr [rax]
0x1401528ba  mov     eax, [rbx+8]
0x1401528bd  mov     r8d, 1933h; int
0x1401528c3  mov     dword ptr [rsp+180h+Interval], eax
0x1401528c7  mov     rax, [rbx+8]
0x1401528cb  shr     rax, 20h
0x1401528cf  movdqu  xmmword ptr [rbp+80h+var_70], xmm0
  ... truncated ...
```
