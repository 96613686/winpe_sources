# SMPDib_ProcessSMPPdu(_SMP_INTERFACE *,DEVICE_INFO_BLOCK *,_SMP_RECEIVED_EVENT_QUEUE_ENTRY *)

- ea: `0x140153c50`
- end: `0x140154943`
- name: `?SMPDib_ProcessSMPPdu@@YAXPEAU_SMP_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@PEAU_SMP_RECEIVED_EVENT_QUEUE_ENTRY@@@Z`
- size: `3315`
- prototype: `void __fastcall(struct _SMP_INTERFACE *, struct DEVICE_INFO_BLOCK *, struct _SMP_RECEIVED_EVENT_QUEUE_ENTRY *)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1401f4030`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005b4c`
- `0x140005c04`
- `0x14001b794`
- `0x140041f28`
- `0x140047e80`
- `0x140060e50`
- `0x14014fd90`
- `0x1401505a4`
- `0x140150984`
- `0x140150b80`
- `0x140153c50`
- `0x1401559e0`
- `0x140155ab8`
- `0x140155d70`
- `0x140155e04`
- `0x140155fe4`
- `0x140161a44`
- `0x140161d7c`
- `0x140165580`
- `0x140165940`
- `0x1401b9928`
- `0x1401f45a8`
- `0x1401f50d0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140154800`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140154904`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140154800`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140154904`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401547f4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401548f8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401547f4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401548f8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140153caf`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140153caf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140153c95`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140153c95`
- `ntoskrnl!KeSetTimer` at `0x140154459`
- `ntoskrnl!KeSetTimer` at `0x140154459`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401545d2`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401545d2`
- `ntoskrnl!KeCancelTimer` at `0x14015463d`
- `ntoskrnl!KeCancelTimer` at `0x14015463d`

## pseudocode

```c
void __fastcall SMPDib_ProcessSMPPdu(
        struct _SMP_INTERFACE *a1,
        struct DEVICE_INFO_BLOCK *a2,
        struct _SMP_RECEIVED_EVENT_QUEUE_ENTRY *a3)
{
  unsigned __int64 address; // rax
  int v4; // esi
  unsigned __int8 v8; // r13
  int v9; // edx
  struct SMPDIB_CONTEXT *v10; // rdi
  int v11; // r8d
  union _LARGE_INTEGER v12; // r14
  char v13; // r15
  char v14; // r14
  union _LARGE_INTEGER v15; // r11
  unsigned __int8 *v16; // rdx
  int v17; // r10d
  int v18; // r9d
  unsigned int v19; // r8d
  PDEVICE_OBJECT v20; // rcx
  int v21; // r8d
  int v22; // r10d
  __int64 v23; // r11
  enum _SMP_STATE v24; // edx
  bool v25; // zf
  int v26; // eax
  int v27; // edx
  int v28; // r8d
  int v29; // r10d
  __int64 v30; // r11
  __int64 v31; // r11
  int v32; // eax
  int v33; // r10d
  __int64 v34; // r11
  int v35; // r10d
  __int64 v36; // r11
  int v37; // edx
  int v38; // r8d
  int v39; // r10d
  __int64 v40; // r11
  int v41; // edx
  int v42; // r8d
  __int16 DeviceType; // ax
  enum _HCI_PHY_TYPE v44; // r8
  struct _SMP_INTERFACE *v45; // r14
  unsigned __int64 v46; // rbx
  int v47; // r8d
  DEVICE_EXTENSION *DevExt; // rax
  int v49; // edx
  int v50; // edx
  int v51; // r8d
  int v52; // edx
  int v53; // r8d
  __int16 v54; // ax
  DEVICE_EXTENSION *v55; // rcx
  struct HCI_INTERFACE *Hci; // rcx
  struct _HCI_CONNECTION *ConnectionFromBdAddrEx2; // rax
  int v58; // edx
  int v59; // r8d
  struct _HCI_CONNECTION *v60; // rbx
  struct _IRP *v61; // r14
  struct _IRP *v62; // r15
  int v63; // edx
  int v64; // r8d
  __int64 v65; // rbx
  enum _HCI_PHY_TYPE v66; // [rsp+38h] [rbp-89h]
  __int64 v67; // [rsp+50h] [rbp-71h]
  char v68; // [rsp+50h] [rbp-71h]
  __int64 v69; // [rsp+58h] [rbp-69h]
  struct SMPDIB_CONTEXT *ContextFromDib; // [rsp+68h] [rbp-59h] BYREF
  unsigned __int64 v71; // [rsp+70h] [rbp-51h]
  PFAST_MUTEX FastMutex; // [rsp+78h] [rbp-49h] BYREF
  __int64 v73; // [rsp+80h] [rbp-41h]
  struct _BTH_LE_SMP_PDU v74; // [rsp+88h] [rbp-39h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+138h] [rbp+77h] BYREF
  __int16 v78; // [rsp+140h] [rbp+7Fh] BYREF

  Interval.QuadPart = (__int64)a3;
  address = a2->DeviceInfo.address;
  v4 = 0;
  v78 = 0;
  v71 = address;
  v8 = 8;
  KeEnterCriticalRegion();
  FastMutex = &a2->ProtocolsLock;
  ExAcquireFastMutexUnsafe(&a2->ProtocolsLock);
  ContextFromDib = SmpDib_GetContextFromDib(a2, (enum _HCI_PHY_TYPE)*((_BYTE *)a3 + 32));
  v10 = ContextFromDib;
  if ( !ContextFromDib )
  {
    v4 = SMPDibContext_Create(a1, a2, (enum _HCI_PHY_TYPE)*((_BYTE *)a3 + 32), &ContextFromDib);
    if ( v4 < 0 )
    {
      LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(v11) = 1;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        a2->IfrLog,
        2,
        10,
        195,
        (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
      v10 = ContextFromDib;
      v12 = Interval;
      goto LABEL_149;
    }
    v10 = ContextFromDib;
  }
  v13 = 0;
  v14 = 0;
  LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LODWORD(v69) = **((unsigned __int8 **)a3 + 5);
  LODWORD(v67) = *((unsigned __int8 *)a3 + 32);
  WPP_RECORDER_AND_TRACE_SF_iLL(WPP_GLOBAL_Control->AttachedDevice, v9, v69, WPP_GLOBAL_Control->DeviceExtension);
  v15 = Interval;
  v16 = *(unsigned __int8 **)(Interval.QuadPart + 40);
  v17 = 10;
  v18 = 12;
  v19 = *v16;
  if ( v19 <= 7 )
  {
    switch ( v19 )
    {
      case 7u:
        goto LABEL_21;
      case 1u:
        v32 = *((_DWORD *)v10 + 13);
        if ( !v32 || v32 == 1 && !SmpDib_IsStateTransitionValid(v10, SmpServerPDUPairingRequestReceived) )
        {
          LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          v69 = *(_QWORD *)(v15.QuadPart + 24);
          LODWORD(v67) = 1;
          WPP_RECORDER_AND_TRACE_SF_LLi(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v16, v19, a2->IfrLog);
          LOBYTE(v78) = 1;
          v4 = -1073741436;
          v13 = 1;
          v8 = 7;
          goto LABEL_54;
        }
        break;
      case 2u:
        if ( !SmpDib_IsStateTransitionValid(v10, SmpClientPDUPairingResponseReceived) )
        {
          v20 = WPP_GLOBAL_Control;
          LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          v69 = *(_QWORD *)(v31 + 24);
          LODWORD(v67) = 2;
          goto LABEL_47;
        }
        break;
      case 3u:
        v29 = *((_DWORD *)v10 + 13);
        if ( !v29 )
        {
          if ( !SmpDib_IsStateTransitionValid(
                  v10,
                  (enum _SMP_STATE)(*((_BYTE *)v10 + 57) != 0
                                  ? SmpClientSCConfirmReceived
                                  : SmpClientPDUPairingConfirmReceived)) )
            goto LABEL_67;
          v18 = v29 + 12;
        }
        if ( v29 != 1 )
        {
          if ( v29 )
            goto LABEL_53;
          v24 = *((_BYTE *)v10 + 57) != 0 ? SmpClientSCConfirmReceived : SmpClientPDUPairingConfirmReceived;
          goto LABEL_52;
        }
        if ( SmpDib_IsStateTransitionValid(v10, (enum _SMP_STATE)(v18 + (*((_BYTE *)v10 + 57) != 0 ? 0x15 : 0))) )
        {
          v24 = *((_BYTE *)v10 + 57) != 0 ? SmpServerSCConfirmReceived : SmpServerPDUPairingConfirmReceived;
          goto LABEL_52;
        }
LABEL_67:
        v20 = WPP_GLOBAL_Control;
        LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v69 = *(_QWORD *)(v30 + 24);
        LODWORD(v67) = 3;
        goto LABEL_47;
      case 4u:
        v22 = *((_DWORD *)v10 + 13);
        if ( !v22
          && !SmpDib_IsStateTransitionValid(
                v10,
                (enum _SMP_STATE)(*((_BYTE *)v10 + 57) != 0
                                ? SmpClientSCRandomReceived
                                : SmpClientPDUPairingRandomReceived)) )
        {
LABEL_42:
          v20 = WPP_GLOBAL_Control;
          LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          v69 = *(_QWORD *)(v23 + 24);
          LODWORD(v67) = 4;
          goto LABEL_47;
        }
        if ( v22 == 1 )
        {
          if ( !SmpDib_IsStateTransitionValid(
                  v10,
                  (enum _SMP_STATE)(*((_BYTE *)v10 + 57) != 0
                                  ? SmpServerSCRandomReceived
                                  : SmpServerPDUPairingRandomReceived)) )
            goto LABEL_42;
          v24 = *((_BYTE *)v10 + 57) != 0 ? SmpServerSCRandomReceived : SmpServerPDUPairingRandomReceived;
        }
        else
        {
          if ( v22 )
            goto LABEL_53;
          v24 = *((_BYTE *)v10 + 57) != 0 ? SmpClientSCRandomReceived : SmpClientPDUPairingRandomReceived;
        }
        goto LABEL_52;
      case 5u:
        LOBYTE(v78) = 1;
        v21 = v16[8];
        if ( v21 == 1 || v16[8] == 2 || v16[8] == 3 || v16[8] == 4 )
        {
          v4 = -1073741117;
        }
        else if ( v16[8] == 5 )
        {
          v4 = -1073741637;
        }
        else
        {
          v4 = -1073741436;
        }
        LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        v68 = v21;
        LOBYTE(v21) = 1;
        WPP_RECORDER_AND_TRACE_SF_LL(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v16,
          v21,
          a2->IfrLog,
          3,
          10,
          206,
          (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
          v4,
          v68);
LABEL_54:
        if ( v4 >= 0 )
          goto LABEL_56;
        goto LABEL_55;
      case 6u:
        goto LABEL_21;
      default:
LABEL_97:
        LOBYTE(v78) = 1;
        v4 = -1073741436;
        goto LABEL_55;
    }
    v24 = v17;
    goto LABEL_52;
  }
  if ( v19 != 8 && v19 != 9 && v19 != 10 )
  {
    switch ( v19 )
    {
      case 0xBu:
        if ( *((_DWORD *)v10 + 13) == 1 )
        {
          v20 = WPP_GLOBAL_Control;
          LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          v69 = *(_QWORD *)(Interval.QuadPart + 24);
          LODWORD(v67) = 11;
          goto LABEL_47;
        }
        if ( !SmpDib_IsStateTransitionValid(v10, SmpPDUSecurityRequestedReceived) )
        {
          LOBYTE(v37) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
          LOBYTE(v38) = 1;
          WPP_RECORDER_AND_TRACE_SF_qL(
            WPP_GLOBAL_Control->AttachedDevice,
            v37,
            v38,
            a2->IfrLog,
            3,
            v39,
            203,
            (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
            *(_QWORD *)(v40 + 24),
            *((_DWORD *)v10 + 15));
          goto LABEL_54;
        }
        v24 = SmpPDUSecurityRequestedReceived;
        break;
      case 0xCu:
        v35 = *((_DWORD *)v10 + 13);
        if ( !v35 && !SmpDib_IsStateTransitionValid(v10, SmpClientSCPublicKeyReceived) )
          goto LABEL_115;
        if ( v35 != 1 )
        {
          if ( v35 )
            goto LABEL_53;
          v24 = SmpClientSCPublicKeyReceived;
          break;
        }
        if ( !SmpDib_IsStateTransitionValid(v10, SmpServerSCPublicKeyReceived) )
        {
LABEL_115:
          v20 = WPP_GLOBAL_Control;
          LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          v69 = *(_QWORD *)(v36 + 24);
          LODWORD(v67) = 12;
          goto LABEL_47;
        }
        v24 = SmpServerSCPublicKeyReceived;
        break;
      case 0xDu:
        v33 = *((_DWORD *)v10 + 13);
        if ( !v33 && !SmpDib_IsStateTransitionValid(v10, SmpClientSCDHKeyCheckReceived) )
          goto LABEL_102;
        if ( v33 != 1 )
        {
          if ( v33 )
            goto LABEL_53;
          v24 = SmpClientSCDHKeyCheckReceived;
          break;
        }
        if ( !SmpDib_IsStateTransitionValid(v10, SmpServerSCDHKeyCheckReceived) )
        {
LABEL_102:
          v20 = WPP_GLOBAL_Control;
          LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          v69 = *(_QWORD *)(v34 + 24);
          LODWORD(v67) = 13;
          goto LABEL_47;
        }
        v24 = SmpServerSCDHKeyCheckReceived;
        break;
      default:
        goto LABEL_97;
    }
LABEL_52:
    SMPDIB_SET_STATE(v10, v24);
    goto LABEL_53;
  }
LABEL_21:
  if ( *((_DWORD *)v10 + 15) == 16 )
  {
LABEL_53:
    v14 = 1;
    goto LABEL_54;
  }
  v20 = WPP_GLOBAL_Control;
  LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  v69 = *(_QWORD *)(Interval.QuadPart + 24);
  LODWORD(v67) = v19;
LABEL_47:
  WPP_RECORDER_AND_TRACE_SF_LLi(v20->AttachedDevice, (_DWORD)v16, v19, a2->IfrLog);
  LOBYTE(v78) = 1;
  v4 = -1073741436;
  v13 = 1;
  v8 = 7;
LABEL_55:
  SMPDIB_SET_STATE(v10, SmpFailed);
LABEL_56:
  v25 = v14 == 0;
  v12 = Interval;
  if ( !v25 )
  {
    v26 = ((__int64 (__fastcall *)(struct SMPDIB_CONTEXT *, _QWORD, _QWORD, __int16 *))funcs_140153FE0[**(unsigned __int8 **)(Interval.QuadPart + 40)])(
            v10,
            *(_QWORD *)(Interval.QuadPart + 40),
            *(unsigned int *)(Interval.QuadPart + 48),
            &v78);
    v4 = v26;
    if ( v26 >= 0 )
    {
      if ( !v78 && !KeSetTimer((PKTIMER)((char *)v10 + 1784), (LARGE_INTEGER)-300000000LL, (PKDPC)((char *)v10 + 1720)) )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
          || (LOBYTE(v41) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
        {
          LOBYTE(v41) = 0;
        }
        DeviceType = WPP_GLOBAL_Control->DeviceType;
        if ( (_BYTE)v41 || DeviceType )
        {
          LOBYTE(v42) = DeviceType != 0;
          WPP_RECORDER_AND_TRACE_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            v41,
            v42,
            *(_QWORD *)(*((_QWORD *)v10 + 1) + 2104LL),
            5,
            10,
            12,
            (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
            (char)v10);
        }
        RefObj_AddRefEx(
          (char *)v10 + 16,
          SMPDibContext_TimeoutDPC,
          363,
          "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp");
      }
    }
    else
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v27) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v27) = 0;
      LOBYTE(v28) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v27,
        v28,
        a2->IfrLog,
        2,
        10,
        207,
        (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
        v26);
      SMPDIB_SET_STATE(v10, SmpFailed);
      v25 = *((_BYTE *)v10 + 1864) == 0;
      LOBYTE(v78) = 1;
      v13 = v25;
      v8 = SmpErrorFromNtStatus(v4);
    }
  }
  if ( !v13 )
  {
    v46 = v71;
    v45 = a1;
    goto LABEL_158;
  }
LABEL_149:
  v74.OpCode = 5;
  memset(&v74.OpCode + 1, 0, 71);
  v44 = *(_BYTE *)(v12.QuadPart + 32);
  v45 = a1;
  v46 = v71;
  v74.PairingRequest.IOCapability = v8;
  if ( SMPInt_SendPDU(a1, v71, v44, &v74, 8u) >= 0 )
  {
    DevExt = a1->DevExt;
    Interval.QuadPart = 0;
    v49 = 125 * DevExt->Hci->LEDefaultConnectionParameters.ConnectionIntervalMax / 100;
    Interval.QuadPart = -20000 * v49;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v49) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v49) = 0;
    LOBYTE(v47) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v49,
      v47,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      10,
      28,
      (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
    KeDelayExecutionThread(0, 0, &Interval);
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v50) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v50) = 0;
    LOBYTE(v51) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v50,
      v51,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      10,
      29,
      (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
  }
LABEL_158:
  if ( !(_BYTE)v78 )
    goto LABEL_185;
  if ( KeCancelTimer((PKTIMER)((char *)v10 + 1784)) )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v52) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      LOBYTE(v52) = 0;
    v54 = WPP_GLOBAL_Control->DeviceType;
    if ( (_BYTE)v52 || v54 )
    {
      LOBYTE(v53) = v54 != 0;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v52,
        v53,
        *(_QWORD *)(*((_QWORD *)v10 + 1) + 2104LL),
        5,
        10,
        13,
        (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids,
        v10,
        v67,
        v69);
    }
    RefObj_ReleaseEx(
      (char *)v10 + 16,
      SMPDibContext_TimeoutDPC,
      376,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp");
  }
  if ( v4 )
  {
    v55 = v45->DevExt;
    v66 = *((_BYTE *)v10 + 56);
    Interval.LowPart = v46;
    Hci = v55->Hci;
    WORD2(Interval.QuadPart) = WORD2(v46);
    ConnectionFromBdAddrEx2 = HCI_GetConnectionFromBdAddrEx2(
                                Hci,
                                (struct _BDADDR *)&Interval,
                                5593,
                                "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp",
                                SMPDib_ProcessSMPPdu,
                                1,
                                v66);
    v60 = ConnectionFromBdAddrEx2;
    if ( ConnectionFromBdAddrEx2 )
    {
      if ( v4 != -1073741637 || DeviceException_001DisconnectOnPairingNotSupported(ConnectionFromBdAddrEx2) )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
          || (LOBYTE(v58) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        {
          LOBYTE(v58) = 0;
        }
        LOBYTE(v59) = 1;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v58,
          v59,
          *(_QWORD *)(*((_QWORD *)v10 + 1) + 2104LL),
          4,
          10,
          208,
          (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
        *(_WORD *)((char *)&Interval.QuadPart + 5) = *(_WORD *)((char *)&a2 + 5);
        HIBYTE(Interval.QuadPart) = HIBYTE(a2);
        Interval.LowPart = v4;
        BYTE4(Interval.QuadPart) = 1;
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))SmpDib_DisconnectConnection)(
          v60,
          v10,
          (union _LARGE_INTEGER)Interval.QuadPart);
      }
      RefObj_ReleaseEx(
        &v60->RefObj,
        SMPDib_ProcessSMPPdu,
        5609,
        "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp");
    }
  }
  if ( *((_BYTE *)v10 + 1864) )
  {
LABEL_185:
    ExReleaseFastMutexUnsafe(FastMutex);
    KeLeaveCriticalRegion();
    if ( v10 )
      RefObj_ReleaseEx(
        (char *)v10 + 16,
        v10,
        5659,
        "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp");
  }
  else
  {
    v61 = (struct _IRP *)_InterlockedExchange64((volatile __int64 *)v10 + 9, 0);
    v62 = (struct _IRP *)_InterlockedExchange64((volatile __int64 *)v10 + 133, 0);
    SMPDib_ClearError(v10);
    ExReleaseFastMutexUnsafe(FastMutex);
    KeLeaveCriticalRegion();
    if ( *((_QWORD *)v10 + 252) )
    {
      HCI_GetLeDibFromSmpDibContext(&FastMutex, v10);
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 || (LOBYTE(v63) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        LOBYTE(v63) = 0;
      v65 = v73;
      LOBYTE(v64) = 1;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v63,
        v64,
        *(_QWORD *)(v73 + 2104),
        4,
        10,
        209,
        (__int64)WPP_5d74b44f6a9434f108575b9e923831da_Traceguids);
      if ( HCI_RemoveClient(
             *(struct HCI_INTERFACE **)(**(_QWORD **)v10 + 368LL),
             *((struct HCI_L2CAP_DATA **)v10 + 252),
             (unsigned __int64 *)(v65 + 32),
             (struct HCI_CLIENT *)((char *)v10 + 1896),
             0) )
      {
        RefObj_ReleaseEx(
          (char *)v10 + 16,
          SmpDib_HciClientCallback,
          5635,
          "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp");
      }
      _Reset___RefObjReference_UREAD_CONNECTED_RSSI_CONTEXT___0A__M__T0A__M__T0A___QEAAXPEAUREAD_CONNECTED_RSSI_CONTEXT__PEBX_Z(&FastMutex);
    }
    RefObj_ReleaseEx((char *)v10 + 16, v10, 5643, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\smpdib.cpp");
    SMPDib_CompleteIrps(a2, v61, v62, v4);
  }
}

```

## disassembly

```asm
0x140153c50  mov     rax, rsp
0x140153c53  mov     [rax+18h], r8
0x140153c57  mov     [rax+10h], rdx
0x140153c5b  mov     [rax+8], rcx
0x140153c5f  push    rbp
0x140153c60  push    rbx
0x140153c61  push    rsi
0x140153c62  push    rdi
0x140153c63  push    r12
0x140153c65  push    r13
0x140153c67  push    r14
0x140153c69  push    r15
0x140153c6b  lea     rbp, [rax-5Fh]
0x140153c6f  sub     rsp, 0D8h
0x140153c76  mov     rax, [rdx+20h]
0x140153c7a  xor     r12d, r12d
0x140153c7d  mov     esi, r12d
0x140153c80  mov     [rbp+57h+arg_18], r12w
0x140153c85  mov     [rbp+57h+var_A8], rax
0x140153c89  mov     rbx, r8
0x140153c8c  mov     r14, rdx
0x140153c8f  mov     r15, rcx
0x140153c92  mov     r13b, 8
0x140153c95  call    cs:__imp_KeEnterCriticalRegion
0x140153c9c  nop     dword ptr [rax+rax+00h]
0x140153ca1  lea     rax, [r14+380h]
0x140153ca8  mov     rcx, rax; FastMutex
0x140153cab  mov     [rbp+57h+FastMutex], rax
0x140153caf  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140153cb6  nop     dword ptr [rax+rax+00h]
0x140153cbb  mov     dl, [rbx+20h]; enum _HCI_PHY_TYPE
0x140153cbe  mov     rcx, r14; struct DEVICE_INFO_BLOCK *
0x140153cc1  call    ?SmpDib_GetContextFromDib@@YAPEAUSMPDIB_CONTEXT@@PEAUDEVICE_INFO_BLOCK@@W4_HCI_PHY_TYPE@@@Z; SmpDib_GetContextFromDib(DEVICE_INFO_BLOCK *,_HCI_PHY_TYPE)
0x140153cc6  mov     [rbp+57h+var_B0], rax
0x140153cca  mov     rdi, rax
0x140153ccd  test    rax, rax
0x140153cd0  jnz     short loc_140153D4F
0x140153cd2  mov     r8b, [rbx+20h]; enum _HCI_PHY_TYPE
0x140153cd6  lea     r9, [rbp+57h+var_B0]; struct SMPDIB_CONTEXT **
0x140153cda  mov     rdx, r14; struct DEVICE_INFO_BLOCK *
0x140153cdd  mov     rcx, r15; struct _SMP_INTERFACE *
0x140153ce0  call    ?SMPDibContext_Create@@YAJPEAU_SMP_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@W4_HCI_PHY_TYPE@@PEAPEAUSMPDIB_CONTEXT@@@Z; SMPDibContext_Create(_SMP_INTERFACE *,DEVICE_INFO_BLOCK *,_HCI_PHY_TYPE,SMPDIB_CONTEXT * *)
0x140153ce5  mov     esi, eax
0x140153ce7  test    eax, eax
0x140153ce9  jns     short loc_140153D4B
0x140153ceb  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140153cf2  lea     ebx, [rdi+2]
0x140153cf5  mov     r12d, 200h
0x140153cfb  test    [rax+2Ch], r12d
0x140153cff  jz      short loc_140153D0A
0x140153d01  cmp     [rax+29h], bl
0x140153d04  jb      short loc_140153D0A
0x140153d06  mov     dl, 1
0x140153d08  jmp     short loc_140153D0C
0x140153d0a  xor     dl, dl
0x140153d0c  mov     r9, [r14+838h]
0x140153d13  lea     r15, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x140153d1a  mov     rcx, [rax+18h]
0x140153d1e  mov     r8b, 1
0x140153d21  mov     [rsp+110h+var_D8], r15
0x140153d26  mov     word ptr [rsp+110h+var_E0], 0C3h
0x140153d2d  mov     dword ptr [rsp+110h+var_E8], 0Ah
0x140153d35  mov     byte ptr [rsp+110h+var_F0], bl
0x140153d39  call    WPP_RECORDER_AND_TRACE_SF_
0x140153d3e  mov     rdi, [rbp+57h+var_B0]
0x140153d42  mov     r14, qword ptr [rbp+57h+Interval]
0x140153d46  jmp     loc_140154502
0x140153d4b  mov     rdi, [rbp+57h+var_B0]
0x140153d4f  mov     r15b, r12b
0x140153d52  mov     r14b, r12b
0x140153d55  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140153d5c  mov     r12d, 200h
0x140153d62  test    [rcx+2Ch], r12d
0x140153d66  jz      short loc_140153D72
0x140153d68  cmp     byte ptr [rcx+29h], 4
0x140153d6c  jb      short loc_140153D72
0x140153d6e  mov     dl, 1
0x140153d70  jmp     short loc_140153D74
0x140153d72  xor     dl, dl
0x140153d74  mov     rax, [rbx+28h]
0x140153d78  mov     r9, [rcx+40h]
0x140153d7c  mov     rcx, [rcx+18h]
0x140153d80  movzx   r8d, byte ptr [rax]
0x140153d84  movzx   eax, byte ptr [rbx+20h]
0x140153d88  mov     [rsp+50h], r8d
0x140153d8d  mov     dword ptr [rsp+110h+var_C8], eax
0x140153d91  mov     rax, [rbx+18h]
0x140153d95  mov     qword ptr [rsp+110h+var_D0], rax
0x140153d9a  lea     rax, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x140153da1  mov     [rsp+110h+var_D8], rax
0x140153da6  mov     word ptr [rsp+110h+var_E0], 0C4h
0x140153dad  call    WPP_RECORDER_AND_TRACE_SF_iLL
0x140153db2  mov     r11, qword ptr [rbp+57h+Interval]
0x140153db6  mov     ebx, 2
0x140153dbb  mov     rdx, [r11+28h]
0x140153dbf  lea     r10d, [rbx+8]
0x140153dc3  lea     r9d, [rbx+0Ah]
0x140153dc7  movzx   r8d, byte ptr [rdx]
0x140153dcb  cmp     r8d, 7
0x140153dcf  ja      loc_1401541F4
0x140153dd5  jz      short loc_140153E0C
0x140153dd7  mov     ecx, r8d
0x140153dda  sub     ecx, 1
0x140153ddd  jz      loc_14015417A
0x140153de3  sub     ecx, 1
0x140153de6  jz      loc_140154125
0x140153dec  sub     ecx, 1
0x140153def  jz      loc_140154071
0x140153df5  sub     ecx, 1
0x140153df8  jz      loc_140153ED6
0x140153dfe  sub     ecx, 1
0x140153e01  jz      short loc_140153E3B
0x140153e03  cmp     ecx, 1
0x140153e06  jnz     loc_140154229
0x140153e0c  mov     r9d, [rdi+3Ch]
0x140153e10  cmp     r9d, 10h
0x140153e14  jz      loc_140153FA2
0x140153e1a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140153e21  test    [rcx+2Ch], r12d
0x140153e25  jz      loc_14015440C
0x140153e2b  cmp     [rcx+29h], bl
0x140153e2e  jb      loc_14015440C
0x140153e34  mov     dl, 1
0x140153e36  jmp     loc_14015440E
0x140153e3b  mov     byte ptr [rbp+57h+arg_18], 1
0x140153e3f  movzx   r8d, byte ptr [rdx+8]
0x140153e44  mov     ecx, r8d
0x140153e47  sub     ecx, 1
0x140153e4a  jz      short loc_140153E76
0x140153e4c  sub     ecx, 1
0x140153e4f  jz      short loc_140153E76
0x140153e51  sub     ecx, 1
0x140153e54  jz      short loc_140153E76
0x140153e56  sub     ecx, 1
0x140153e59  jz      short loc_140153E76
0x140153e5b  sub     ecx, 1
0x140153e5e  jz      short loc_140153E6F
0x140153e60  sub     ecx, 1
0x140153e63  jz      short loc_140153E68
0x140153e65  sub     ecx, 1
0x140153e68  mov     esi, 0C0000184h
0x140153e6d  jmp     short loc_140153E7B
0x140153e6f  mov     esi, 0C00000BBh
0x140153e74  jmp     short loc_140153E7B
0x140153e76  mov     esi, 0C00002C3h
0x140153e7b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140153e82  test    [rcx+2Ch], r12d
0x140153e86  jz      short loc_140153E92
0x140153e88  cmp     byte ptr [rcx+29h], 3
0x140153e8c  jb      short loc_140153E92
0x140153e8e  mov     dl, 1
0x140153e90  jmp     short loc_140153E94
0x140153e92  xor     dl, dl
0x140153e94  mov     r9, [rbp+57h+arg_8]
0x140153e98  lea     rax, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x140153e9f  mov     rcx, [rcx+18h]
0x140153ea3  mov     dword ptr [rsp+110h+var_C8], r8d
0x140153ea8  mov     r8b, 1
0x140153eab  mov     [rsp+110h+var_D0], esi
0x140153eaf  mov     r9, [r9+838h]
0x140153eb6  mov     [rsp+110h+var_D8], rax
0x140153ebb  mov     word ptr [rsp+110h+var_E0], 0CEh
0x140153ec2  mov     dword ptr [rsp+110h+var_E8], r10d
0x140153ec7  mov     byte ptr [rsp+110h+var_F0], 3
0x140153ecc  call    WPP_RECORDER_AND_TRACE_SF_LL
0x140153ed1  jmp     loc_140153FA5
0x140153ed6  mov     r10d, [rdi+34h]
0x140153eda  test    r10d, r10d
0x140153edd  jnz     short loc_140153EF8
0x140153edf  mov     al, [rdi+39h]
0x140153ee2  mov     rcx, rdi; struct SMPDIB_CONTEXT *
0x140153ee5  neg     al
0x140153ee7  sbb     edx, edx
0x140153ee9  and     edx, 12h
0x140153eec  add     edx, 9; enum _SMP_STATE
0x140153eef  call    ?SmpDib_IsStateTransitionValid@@YA_NPEAUSMPDIB_CONTEXT@@W4_SMP_STATE@@@Z; SmpDib_IsStateTransitionValid(SMPDIB_CONTEXT *,_SMP_STATE)
0x140153ef4  test    al, al
0x140153ef6  jz      short loc_140153F17
0x140153ef8  cmp     r10d, 1
0x140153efc  jnz     short loc_140153F73
0x140153efe  mov     al, [rdi+39h]
0x140153f01  mov     rcx, rdi; struct SMPDIB_CONTEXT *
0x140153f04  neg     al
0x140153f06  sbb     edx, edx
0x140153f08  and     edx, 14h
0x140153f0b  add     edx, 0Eh; enum _SMP_STATE
0x140153f0e  call    ?SmpDib_IsStateTransitionValid@@YA_NPEAUSMPDIB_CONTEXT@@W4_SMP_STATE@@@Z; SmpDib_IsStateTransitionValid(SMPDIB_CONTEXT *,_SMP_STATE)
0x140153f13  test    al, al
0x140153f15  jnz     short loc_140153F7E
0x140153f17  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140153f1e  test    [rcx+2Ch], r12d
0x140153f22  jz      short loc_140153F2D
0x140153f24  cmp     [rcx+29h], bl
0x140153f27  jb      short loc_140153F2D
0x140153f29  mov     dl, 1
0x140153f2b  jmp     short loc_140153F2F
0x140153f2d  xor     dl, dl
0x140153f2f  mov     rax, [r11+18h]
0x140153f33  mov     [rsp+50h], rax
0x140153f38  mov     eax, [rdi+3Ch]
0x140153f3b  mov     dword ptr [rsp+110h+var_C8], 4
0x140153f43  mov     [rsp+110h+var_D0], eax
0x140153f47  mov     word ptr [rsp+110h+var_E0], 0C8h
0x140153f4e  mov     r9, [rbp+57h+arg_8]
0x140153f52  mov     rcx, [rcx+18h]
0x140153f56  mov     r9, [r9+838h]
0x140153f5d  call    WPP_RECORDER_AND_TRACE_SF_LLi
0x140153f62  mov     byte ptr [rbp+57h+arg_18], 1
0x140153f66  mov     esi, 0C0000184h
0x140153f6b  mov     r15b, 1
0x140153f6e  mov     r13b, 7
0x140153f71  jmp     short loc_140153FA9
0x140153f73  test    r10d, r10d
0x140153f76  jz      short loc_140153F8D
0x140153f78  cmp     r10d, 1
0x140153f7c  jnz     short loc_140153FA2
0x140153f7e  mov     al, [rdi+39h]
0x140153f81  neg     al
0x140153f83  sbb     edx, edx
0x140153f85  and     edx, 14h
0x140153f88  add     edx, 0Eh
0x140153f8b  jmp     short loc_140153F9A
0x140153f8d  mov     al, [rdi+39h]
0x140153f90  neg     al
0x140153f92  sbb     edx, edx
0x140153f94  and     edx, 12h
0x140153f97  add     edx, 9; enum _SMP_STATE
0x140153f9a  mov     rcx, rdi; struct SMPDIB_CONTEXT *
0x140153f9d  call    ?SMPDIB_SET_STATE@@YAXPEAUSMPDIB_CONTEXT@@W4_SMP_STATE@@@Z; SMPDIB_SET_STATE(SMPDIB_CONTEXT *,_SMP_STATE)
0x140153fa2  mov     r14b, 1
0x140153fa5  test    esi, esi
0x140153fa7  jns     short loc_140153FB6
0x140153fa9  mov     edx, 15h; enum _SMP_STATE
0x140153fae  mov     rcx, rdi; struct SMPDIB_CONTEXT *
0x140153fb1  call    ?SMPDIB_SET_STATE@@YAXPEAUSMPDIB_CONTEXT@@W4_SMP_STATE@@@Z; SMPDIB_SET_STATE(SMPDIB_CONTEXT *,_SMP_STATE)
0x140153fb6  test    r14b, r14b
0x140153fb9  mov     r14, qword ptr [rbp+57h+Interval]
0x140153fbd  jz      loc_1401544F2
0x140153fc3  mov     rdx, [r14+28h]
0x140153fc7  lea     rcx, funcs_140153FE0
0x140153fce  mov     r8d, [r14+30h]
0x140153fd2  lea     r9, [rbp+57h+arg_18]
0x140153fd6  movzx   eax, byte ptr [rdx]
0x140153fd9  mov     rax, ds:(funcs_140153FE0 - 14016F760h)[rcx+rax*8]
0x140153fdd  mov     rcx, rdi
0x140153fe0  call    _guard_dispatch_icall
0x140153fe5  xor     r9d, r9d
0x140153fe8  mov     esi, eax
0x140153fea  test    eax, eax
0x140153fec  jns     loc_14015442D
0x140153ff2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140153ff9  test    [rcx+2Ch], r12d
0x140153ffd  jz      short loc_140154006
0x140153fff  mov     dl, 1
0x140154001  cmp     [rcx+29h], bl
0x140154004  jnb     short loc_140154009
0x140154006  mov     dl, r9b
0x140154009  mov     rcx, [rcx+18h]
0x14015400d  lea     rax, WPP_5d74b44f6a9434f108575b9e923831da_Traceguids
0x140154014  mov     [rsp+110h+var_D0], esi
0x140154018  mov     r8b, 1
0x14015401b  mov     [rsp+110h+var_D8], rax
0x140154020  mov     rax, [rbp+57h+arg_8]
0x140154024  mov     word ptr [rsp+110h+var_E0], 0CFh
0x14015402b  mov     dword ptr [rsp+110h+var_E8], 0Ah
0x140154033  mov     byte ptr [rsp+110h+var_F0], bl
0x140154037  mov     r9, [rax+838h]
0x14015403e  call    WPP_RECORDER_AND_TRACE_SF_d
0x140154043  mov     edx, 15h; enum _SMP_STATE
0x140154048  mov     rcx, rdi; struct SMPDIB_CONTEXT *
0x14015404b  call    ?SMPDIB_SET_STATE@@YAXPEAUSMPDIB_CONTEXT@@W4_SMP_STATE@@@Z; SMPDIB_SET_STATE(SMPDIB_CONTEXT *,_SMP_STATE)
0x140154050  xor     r9d, r9d
0x140154053  mov     ecx, esi; int
0x140154055  cmp     [rdi+748h], r9b
0x14015405c  mov     byte ptr [rbp+57h+arg_18], 1
0x140154060  setz    r15b
0x140154064  call    ?SmpErrorFromNtStatus@@YAEJ@Z; SmpErrorFromNtStatus(long)
0x140154069  mov     r13b, al
0x14015406c  jmp     loc_1401544F2
0x140154071  mov     r10d, [rdi+34h]
0x140154075  test    r10d, r10d
0x140154078  jnz     short loc_140154097
0x14015407a  mov     al, [rdi+39h]
0x14015407d  mov     rcx, rdi; struct SMPDIB_CONTEXT *
0x140154080  neg     al
0x140154082  sbb     edx, edx
0x140154084  and     edx, 12h
0x140154087  add     edx, 7; enum _SMP_STATE
0x14015408a  call    ?SmpDib_IsStateTransitionValid@@YA_NPEAUSMPDIB_CONTEXT@@W4_SMP_STATE@@@Z; SmpDib_IsStateTransitionValid(SMPDIB_CONTEXT *,_SMP_STATE)
0x14015408f  test    al, al
0x140154091  jz      short loc_1401540B6
0x140154093  lea     r9d, [r10+0Ch]
0x140154097  cmp     r10d, 1
0x14015409b  jnz     short loc_1401540F2
0x14015409d  mov     al, [rdi+39h]
0x1401540a0  mov     rcx, rdi; struct SMPDIB_CONTEXT *
0x1401540a3  neg     al
0x1401540a5  sbb     edx, edx
0x1401540a7  and     edx, 15h
0x1401540aa  add     edx, r9d; enum _SMP_STATE
  ... truncated ...
```
