# HCI_ProcessAclReadBip(HCI_INTERFACE *,_BIP *,_HCI_CONNECTION *)

- ea: `0x14002d5a4`
- end: `0x14002ded8`
- name: `?HCI_ProcessAclReadBip@@YAXPEAUHCI_INTERFACE@@PEAU_BIP@@PEAU_HCI_CONNECTION@@@Z`
- size: `2356`
- prototype: `void __fastcall(struct HCI_INTERFACE *, struct _BIP *, struct _HCI_CONNECTION *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002d1a0`
- `0x140046880`

## callees

- `0x140005b4c`
- `0x140005c04`
- `0x140007084`
- `0x14000bdb8`
- `0x14001fddc`
- `0x140028938`
- `0x14002d5a4`
- `0x14002e040`
- `0x14002e2a0`
- `0x1400325ac`
- `0x1400420b4`
- `0x1400bc4e0`
- `0x1400bd4f0`
- `0x140161d7c`
- `0x140165540`
- `0x140165580`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14002dc44`
- `ntoskrnl!EtwWriteTransfer` at `0x14002dc44`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d9ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d9ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dd2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dd2a`

## string_xrefs

- `0x14002d933`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclread.cpp`
- `0x14002dd46`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclread.cpp`
- `0x14002ddaf`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclread.cpp`
- `0x14002de86`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclread.cpp`

## pseudocode

```c
void __fastcall HCI_ProcessAclReadBip(struct HCI_INTERFACE *a1, struct _BIP *a2, struct _HCI_CONNECTION *a3)
{
  unsigned __int16 *BufferData; // r15
  struct _HCI_CONNECTION *v6; // r13
  void (__fastcall **p_Blink)(char *); // r12
  int v8; // edx
  __int16 v9; // cx
  PDEVICE_OBJECT v10; // rcx
  int v11; // r8d
  char v12; // di
  int v13; // edx
  int v14; // r8d
  _LIST_ENTRY *Flink; // r12
  _LIST_ENTRY *v16; // rax
  unsigned __int16 v17; // r9
  struct L2CAP_INTERFACE *L2cap; // rcx
  int v19; // edx
  void (__fastcall *v20)(char *); // rax
  KSPIN_LOCK *p_FunctionalDeviceObject; // rcx
  KIRQL v22; // al
  int v23; // edx
  int v24; // r8d
  unsigned __int16 v25; // cx
  _BIP **p_CurrentAclRead; // rdx
  _BIP *CurrentAclRead; // r8
  _LIST_ENTRY *v28; // rax
  RECORDER_LOG__ *IfrLog; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  unsigned __int16 *v31; // rax
  void (__fastcall *Context)(char *); // r10
  _BIP **v33; // r12
  int v34; // edx
  int v35; // r8d
  const GUID *v36; // r9
  const GUID *v37; // rdx
  _LIST_ENTRY *v38; // r8
  _LIST_ENTRY *Data4; // rdx
  const GUID *v40; // r8
  RECORDER_LOG__ *v41; // r9
  _DEVICE_OBJECT *v42; // rcx
  struct _BIP *v43; // rax
  unsigned int DataLen; // edx
  struct _BIP *v45; // r12
  int v46; // edx
  int v47; // r8d
  struct _HCI_CONNECTION *ConnectionFromHandle; // r14
  void (__fastcall *CompletionRoutine)(_BIP *); // rax
  ULONG UserDataCount[2]; // [rsp+20h] [rbp-89h]
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-81h]
  unsigned int v52; // [rsp+30h] [rbp-79h]
  __int64 *v53; // [rsp+38h] [rbp-71h]
  struct _BIP *v54; // [rsp+40h] [rbp-69h]
  __int64 v55; // [rsp+48h] [rbp-61h]
  __int64 v56; // [rsp+50h] [rbp-59h]
  char v57; // [rsp+60h] [rbp-49h]
  KIRQL NewIrql; // [rsp+61h] [rbp-48h]
  int v59; // [rsp+64h] [rbp-45h]
  void (__fastcall *v60)(char *); // [rsp+68h] [rbp-41h]
  struct _LIST_ENTRY v61; // [rsp+70h] [rbp-39h] BYREF
  struct _BIP *v62; // [rsp+80h] [rbp-29h]
  struct _BIP *v63; // [rsp+88h] [rbp-21h]
  unsigned __int16 *v64; // [rsp+90h] [rbp-19h]
  unsigned __int16 *v65; // [rsp+98h] [rbp-11h]
  struct _BIP *v66; // [rsp+A0h] [rbp-9h]
  struct _EVENT_DATA_DESCRIPTOR v67; // [rsp+A8h] [rbp-1h] BYREF
  const GUID *v68; // [rsp+B8h] [rbp+Fh]
  __int64 v69; // [rsp+C0h] [rbp+17h]

  BufferData = (unsigned __int16 *)a2->BufferData;
  v61.Blink = &v61;
  v65 = BufferData;
  v61.Flink = &v61;
  v6 = a3;
  p_Blink = 0;
  v8 = 0x4000;
  if ( (*BufferData & 0xC000) == 0x4000 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v8) = 0;
    LOBYTE(a3) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      (_DWORD)a3,
      a1->IfrLog,
      2,
      2,
      34,
      (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
      (char)a2);
    if ( !v6 )
      goto LABEL_40;
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)&v6->ActivePeripheralBroadcastPacketsDropped, 1u) )
      BthReportError_BthAddr(
        a1->DevExt,
        -2147155917,
        0x11u,
        0,
        0,
        (unsigned __int16)WORD2(v6->Dib->DeviceInfo.address),
        v6->Dib->DeviceInfo.address);
LABEL_38:
    RefObj_ReleaseEx(
      &v6->RefObj,
      HCI_GetConnectionOrZombieFromHandleLocked,
      1083,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclread.cpp");
    if ( p_Blink )
      p_Blink[18]((char *)p_Blink);
LABEL_40:
    HCI_TossAndMarkAclReadUnstable(a1, a2, *v65, -1073741670);
    return;
  }
  v9 = *BufferData & 0x3000;
  if ( !a3 )
  {
    if ( v9 == 0x2000 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v8) = 0;
      v54 = a2;
      v53 = WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids;
      LOWORD(v52) = 35;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v8) = 0;
      v54 = a2;
      v53 = WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids;
      LOWORD(v52) = 36;
    }
    LOBYTE(a3) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(v10->AttachedDevice, v8, (_DWORD)a3, a1->IfrLog, 2, 2, v52, (__int64)v53, (char)v54);
    goto LABEL_40;
  }
  if ( v9 == 0x2000 )
  {
    v11 = BufferData[1];
    if ( (unsigned __int16)v11 < 4u )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v8) = 0;
      LOBYTE(v11) = 1;
      WPP_RECORDER_AND_TRACE_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        v11,
        a1->IfrLog,
        2,
        2,
        37,
        (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
        BufferData[1],
        (char)a2);
      goto LABEL_38;
    }
    v12 = 1;
    if ( !HCI_AllocateBips(&a1->DevExt->BtDevice, &v61, DATA_PKT_R, 1u, 0, 0) )
    {
      LOBYTE(v13) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(v14) = 1;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        v14,
        a1->IfrLog,
        2,
        2,
        38,
        (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
        (char)a2);
      goto LABEL_38;
    }
    Flink = v61.Flink;
    if ( v61.Flink->Blink != &v61 || (v16 = v61.Flink->Flink, v61.Flink->Flink->Blink != v61.Flink) )
LABEL_70:
      __fastfail(3u);
    v61.Flink = v61.Flink->Flink;
    v16->Blink = &v61;
    Flink->Blink = Flink;
    Flink->Flink = Flink;
    Flink[3].Blink = (_LIST_ENTRY *)HCI_CompleteAclRdChain;
    p_Blink = (void (__fastcall **)(char *))&Flink[-6].Blink;
    v17 = BufferData[1];
    *(_QWORD *)UserDataCount = &a2->TrackIrpActivity;
    L2cap = a1->L2cap;
    v64 = BufferData + 2;
    if ( !L2CapInt_VerifyIncomingReadPacket(
            L2cap,
            &v6->L2capData,
            (struct _L2CAP_PDU_HEADER *)(BufferData + 2),
            v17 - 4,
            &a2->TrackIrpActivity) )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        v12 = 0;
      LOBYTE(v19) = v12;
      WPP_RECORDER_AND_TRACE_SF_dDq(
        WPP_GLOBAL_Control->AttachedDevice,
        v19,
        (_DWORD)WPP_GLOBAL_Control,
        a1->IfrLog,
        UserDataCount[0],
        (_DWORD)UserData,
        v52,
        (_DWORD)v53,
        BufferData[2],
        BufferData[3],
        (char)a2);
      goto LABEL_38;
    }
    v20 = p_Blink[19];
    v57 = 0;
    *((_QWORD *)v20 + 10) = v6;
  }
  else
  {
    v57 = 1;
    v64 = BufferData + 2;
  }
  p_FunctionalDeviceObject = (KSPIN_LOCK *)&a1->BtDevice[11].FunctionalDeviceObject;
  v62 = 0;
  v63 = 0;
  v66 = 0;
  v59 = 0;
  v22 = KeAcquireSpinLockRaiseToDpc(p_FunctionalDeviceObject);
  v25 = *BufferData;
  NewIrql = v22;
  if ( (v25 & 0x3000) == 0x2000 )
  {
    LOBYTE(v23) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v24) = 1;
    WPP_RECORDER_AND_TRACE_SF_qL(
      WPP_GLOBAL_Control->AttachedDevice,
      v23,
      v24,
      a1->IfrLog,
      4,
      2,
      40,
      (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
      (char)p_Blink,
      BufferData[2]);
    p_CurrentAclRead = &v6->CurrentAclRead;
    CurrentAclRead = v6->CurrentAclRead;
    if ( CurrentAclRead )
    {
      v28 = CurrentAclRead->BipChain.Flink;
      v63 = v6->CurrentAclRead;
      v59 = (int)v28[-2].Flink->Flink;
      *p_CurrentAclRead = 0;
      LOBYTE(p_CurrentAclRead) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      IfrLog = a1->IfrLog;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      LOBYTE(v54) = (_BYTE)CurrentAclRead;
      LOBYTE(CurrentAclRead) = 1;
      WPP_RECORDER_AND_TRACE_SF_q(
        (_DWORD)AttachedDevice,
        (_DWORD)p_CurrentAclRead,
        (_DWORD)CurrentAclRead,
        (_DWORD)IfrLog,
        4,
        2,
        41,
        (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
        (char)v54);
      p_CurrentAclRead = &v6->CurrentAclRead;
    }
    *p_Blink = (void (__fastcall *)(char *))a2->BtDevice;
    *((_DWORD *)p_Blink + 2) = a2->Type;
    *((_DWORD *)p_Blink + 3) = a2->Status;
    v31 = v64;
    *((_OWORD *)p_Blink + 1) = a2->TrackIrpActivity;
    Context = p_Blink[19];
    LODWORD(v31) = *v31 + 4;
    v60 = Context;
    *((_DWORD *)Context + 18) = (_DWORD)v31;
    *p_CurrentAclRead = (_BIP *)p_Blink;
    *((_DWORD *)p_Blink + 12) = a2->DataLen - 4;
    v33 = &v6->CurrentAclRead;
  }
  else
  {
    LOBYTE(v23) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    v33 = &v6->CurrentAclRead;
    LOBYTE(v24) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v23,
      v24,
      a1->IfrLog,
      4,
      2,
      42,
      (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
      (char)v6->CurrentAclRead);
    if ( v6->CurrentAclRead )
    {
      (*v33)->DataLen += a2->DataLen - 4;
      v36 = (const GUID *)*v33;
      Context = (void (__fastcall *)(char *))(*v33)->PacketContexts[1].Context;
      v60 = Context;
      if ( (Microsoft_Windows_BTH_BTHPORTEnableBits & 4) == 0 )
        goto LABEL_68;
      *(_QWORD *)&v67.Size = 16;
      v67.Ptr = (unsigned __int64)&a2->TrackIrpActivity;
      v68 = v36 + 1;
      v69 = 16;
      EtwWriteTransfer(BTHPORT_ETW_PROVIDER_Context, &EVENT_TIE_ACTIVITY_ID, &a2->TrackIrpActivity, v36 + 1, 2u, &v67);
    }
    else
    {
      v60 = 0;
      v63 = a2;
      v59 = *v65;
      LOBYTE(v34) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v35) = 1;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v34,
        v35,
        a1->IfrLog,
        4,
        2,
        43,
        (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
        (char)a2);
    }
    Context = v60;
  }
LABEL_68:
  v37 = (const GUID *)*v33;
  if ( !*v33 )
  {
    v45 = v62;
    goto LABEL_81;
  }
  v38 = *(_LIST_ENTRY **)&v37[5].Data1;
  Data4 = (_LIST_ENTRY *)v37[4].Data4;
  if ( v38->Flink != Data4 )
    goto LABEL_70;
  a2->BipChain.Flink = Data4;
  a2->BipChain.Blink = v38;
  v38->Flink = &a2->BipChain;
  Data4->Blink = &a2->BipChain;
  LOBYTE(Data4) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  v40 = (const GUID *)*v33;
  v41 = a1->IfrLog;
  v42 = WPP_GLOBAL_Control->AttachedDevice;
  LODWORD(v56) = *((_DWORD *)Context + 18);
  LODWORD(v55) = v40[3].Data1;
  LOBYTE(v54) = (_BYTE)v40;
  LOBYTE(v40) = 1;
  WPP_RECORDER_AND_TRACE_SF_qLL(
    (_DWORD)v42,
    (_DWORD)Data4,
    (_DWORD)v40,
    (_DWORD)v41,
    4,
    2,
    44,
    (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
    (char)v54,
    v55,
    v56);
  v43 = *v33;
  DataLen = (*v33)->DataLen;
  if ( *((_DWORD *)v60 + 18) == DataLen )
  {
    v45 = *v33;
  }
  else
  {
    v45 = v62;
    if ( *((_DWORD *)v60 + 18) >= DataLen )
      goto LABEL_81;
    v66 = v43;
  }
  v6->CurrentAclRead = 0;
LABEL_81:
  KeReleaseSpinLock((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject, NewIrql);
  if ( v57 )
    RefObj_ReleaseEx(
      &v6->RefObj,
      HCI_GetConnectionOrZombieFromHandleLocked,
      997,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclread.cpp");
  if ( v63 )
    HCI_TossAndMarkAclReadUnstable(a1, v63, v59, -1073741823);
  if ( v66 )
    HCI_TossAndMarkAclReadUnstable(a1, v66, *(_WORD *)a2->BufferData, -1073741823);
  if ( v45 )
  {
    ConnectionFromHandle = HCI_GetConnectionFromHandleEx(
                             a1,
                             (__int64)v45->BipChain.Flink[-2].Flink->Flink & 0xFFF,
                             1037,
                             "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclread.cpp",
                             HCI_ProcessAclRead);
    if ( ConnectionFromHandle )
    {
      LOBYTE(v46) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v47) = 1;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v46,
        v47,
        a1->IfrLog,
        4,
        2,
        45,
        (__int64)WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids,
        (char)v45);
      DevicePerfCounters::OnBytesRead(
        &ConnectionFromHandle->Dib->PerfCounters,
        (enum DevicePerfCounters::BasebandType)(ConnectionFromHandle->Info.PhyType == HciPhyTypeLE),
        v45->DataLen);
      DevicePerfCounters::OnBytesRead(
        (DevicePerfCounters *)&a1->PerfCounters,
        (enum DevicePerfCounters::BasebandType)(ConnectionFromHandle->Info.PhyType == HciPhyTypeLE),
        v45->DataLen);
      L2CapInt_ProcessReadBip(a1->L2cap, &ConnectionFromHandle->L2capData, v45);
      RefObj_ReleaseEx(
        &ConnectionFromHandle->RefObj,
        HCI_ProcessAclRead,
        1063,
        "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclread.cpp");
    }
    else
    {
      CompletionRoutine = v45->PacketContexts[1].CompletionRoutine;
      v45->Status = -1073741808;
      CompletionRoutine(v45);
    }
  }
}

```

## disassembly

```asm
0x14002d5a4  mov     [rsp-8+arg_18], rbx
0x14002d5a9  push    rbp
0x14002d5aa  push    rsi
0x14002d5ab  push    rdi
0x14002d5ac  push    r12
0x14002d5ae  push    r13
0x14002d5b0  push    r14
0x14002d5b2  push    r15
0x14002d5b4  lea     rbp, [rsp-27h]
0x14002d5b9  sub     rsp, 0D0h
0x14002d5c0  mov     rax, cs:__security_cookie
0x14002d5c7  xor     rax, rsp
0x14002d5ca  mov     [rbp+57h+var_38], rax
0x14002d5ce  mov     r15, [rdx+28h]
0x14002d5d2  lea     rax, [rbp+57h+var_90]
0x14002d5d6  mov     [rbp+57h+var_90.Blink], rax
0x14002d5da  mov     r14, rdx
0x14002d5dd  lea     rax, [rbp+57h+var_90]
0x14002d5e1  mov     [rbp+57h+var_68], r15
0x14002d5e5  mov     [rbp+57h+var_90.Flink], rax
0x14002d5e9  mov     edx, 0C000h
0x14002d5ee  xor     r9d, r9d
0x14002d5f1  mov     rsi, rcx
0x14002d5f4  movzx   ecx, word ptr [r15]
0x14002d5f8  mov     r13, r8
0x14002d5fb  movzx   eax, cx
0x14002d5fe  mov     r12d, r9d
0x14002d601  and     ax, dx
0x14002d604  mov     edx, 4000h
0x14002d609  cmp     ax, dx
0x14002d60c  jnz     loc_14002D6BD
0x14002d612  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d619  lea     edi, [r9+1]
0x14002d61d  lea     ebx, [rdi+1]
0x14002d620  mov     eax, [rcx+2Ch]
0x14002d623  test    bl, al
0x14002d625  jz      short loc_14002D62F
0x14002d627  mov     dl, dil
0x14002d62a  cmp     [rcx+29h], bl
0x14002d62d  jnb     short loc_14002D632
0x14002d62f  mov     dl, r9b
0x14002d632  mov     r9, [rsi+10B0h]
0x14002d639  lea     r15, WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids
0x14002d640  mov     rcx, [rcx+18h]
0x14002d644  mov     r8b, dil
0x14002d647  mov     [rsp+100h+var_C0], r14
0x14002d64c  mov     [rsp+100h+var_C8], r15
0x14002d651  mov     word ptr [rsp+100h+var_D0], 22h ; '"'
0x14002d658  mov     dword ptr [rsp+100h+UserData], ebx
0x14002d65c  mov     byte ptr [rsp+100h+UserDataCount], bl
0x14002d660  call    WPP_RECORDER_AND_TRACE_SF_q
0x14002d665  test    r13, r13
0x14002d668  jz      loc_14002D95B
0x14002d66e  nop
0x14002d66f  lock xadd [r13+534h], edi
0x14002d678  nop
0x14002d679  test    edi, edi
0x14002d67b  jnz     loc_14002D929
0x14002d681  mov     rdx, [r13+30h]
0x14002d685  lea     r8d, [rdi+11h]; unsigned int
0x14002d689  xor     r9d, r9d; void *
0x14002d68c  mov     rax, [rdx+20h]
0x14002d690  shr     rax, 20h
0x14002d694  movzx   ecx, ax
0x14002d697  mov     eax, [rdx+20h]
0x14002d69a  mov     edx, 80050033h; int
0x14002d69f  mov     [rsp+100h+var_D0], eax; unsigned int
0x14002d6a3  mov     dword ptr [rsp+100h+UserData], ecx; unsigned int
0x14002d6a7  mov     rcx, [rsi+4A8h]; struct DEVICE_EXTENSION *
0x14002d6ae  mov     [rsp+100h+UserDataCount], r12d; unsigned int
0x14002d6b3  call    ?BthReportError_BthAddr@@YAXPEAUDEVICE_EXTENSION@@JKPEAXKKK@Z; BthReportError_BthAddr(DEVICE_EXTENSION *,long,ulong,void *,ulong,ulong,ulong)
0x14002d6b8  jmp     loc_14002D929
0x14002d6bd  mov     eax, 3000h
0x14002d6c2  mov     ebx, 2000h
0x14002d6c7  and     cx, ax
0x14002d6ca  test    r13, r13
0x14002d6cd  jnz     loc_14002D76B
0x14002d6d3  cmp     cx, bx
0x14002d6d6  jnz     short loc_14002D730
0x14002d6d8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d6df  lea     edi, [r13+1]
0x14002d6e3  lea     ebx, [rdi+1]
0x14002d6e6  mov     eax, [rcx+2Ch]
0x14002d6e9  test    bl, al
0x14002d6eb  jz      short loc_14002D6F5
0x14002d6ed  mov     dl, dil
0x14002d6f0  cmp     [rcx+29h], bl
0x14002d6f3  jnb     short loc_14002D6F8
0x14002d6f5  mov     dl, r9b
0x14002d6f8  mov     [rsp+100h+var_C0], r14
0x14002d6fd  lea     r15, WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids
0x14002d704  mov     [rsp+100h+var_C8], r15
0x14002d709  mov     word ptr [rsp+100h+var_D0], 23h ; '#'
0x14002d710  mov     r9, [rsi+10B0h]
0x14002d717  mov     r8b, dil
0x14002d71a  mov     rcx, [rcx+18h]
0x14002d71e  mov     dword ptr [rsp+100h+UserData], ebx
0x14002d722  mov     byte ptr [rsp+100h+UserDataCount], bl
0x14002d726  call    WPP_RECORDER_AND_TRACE_SF_q
0x14002d72b  jmp     loc_14002D95B
0x14002d730  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d737  mov     edi, 1
0x14002d73c  mov     eax, [rcx+2Ch]
0x14002d73f  lea     ebx, [rdi+1]
0x14002d742  test    bl, al
0x14002d744  jz      short loc_14002D74E
0x14002d746  mov     dl, dil
0x14002d749  cmp     [rcx+29h], bl
0x14002d74c  jnb     short loc_14002D751
0x14002d74e  mov     dl, r9b
0x14002d751  mov     [rsp+100h+var_C0], r14
0x14002d756  lea     r15, WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids
0x14002d75d  mov     [rsp+100h+var_C8], r15
0x14002d762  mov     word ptr [rsp+100h+var_D0], 24h ; '$'
0x14002d769  jmp     short loc_14002D710
0x14002d76b  mov     eax, 4
0x14002d770  cmp     cx, bx
0x14002d773  jnz     loc_14002D98B
0x14002d779  movzx   r8d, word ptr [r15+2]
0x14002d77e  cmp     r8w, ax
0x14002d782  jnb     short loc_14002D7E2
0x14002d784  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d78b  mov     edi, 1
0x14002d790  mov     eax, [rcx+2Ch]
0x14002d793  lea     ebx, [rdi+1]
0x14002d796  test    bl, al
0x14002d798  jz      short loc_14002D7A2
0x14002d79a  mov     dl, dil
0x14002d79d  cmp     [rcx+29h], bl
0x14002d7a0  jnb     short loc_14002D7A5
0x14002d7a2  mov     dl, r9b
0x14002d7a5  mov     r9, [rsi+10B0h]
0x14002d7ac  lea     r15, WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids
0x14002d7b3  mov     rcx, [rcx+18h]
0x14002d7b7  mov     [rsp+100h+var_B8], r14
0x14002d7bc  mov     dword ptr [rsp+100h+var_C0], r8d
0x14002d7c1  mov     r8b, dil
0x14002d7c4  mov     [rsp+100h+var_C8], r15
0x14002d7c9  mov     word ptr [rsp+100h+var_D0], 25h ; '%'
0x14002d7d0  mov     dword ptr [rsp+100h+UserData], ebx
0x14002d7d4  mov     byte ptr [rsp+100h+UserDataCount], bl
0x14002d7d8  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x14002d7dd  jmp     loc_14002D929
0x14002d7e2  mov     rcx, [rsi+4A8h]; struct _BTDEVICE *
0x14002d7e9  lea     rdx, [rbp+57h+var_90]; struct _LIST_ENTRY *
0x14002d7ed  mov     byte ptr [rsp+100h+UserData], r9b; unsigned __int8
0x14002d7f2  mov     edi, 1
0x14002d7f7  mov     byte ptr [rsp+100h+UserDataCount], r9b; unsigned __int8
0x14002d7fc  mov     r9d, edi; unsigned int
0x14002d7ff  lea     r8d, [rdi+2]; enum _HCI_PKT_TYPE
0x14002d803  call    ?HCI_AllocateBips@@YAEPEAU_BTDEVICE@@PEAU_LIST_ENTRY@@W4_HCI_PKT_TYPE@@KEE@Z; HCI_AllocateBips(_BTDEVICE *,_LIST_ENTRY *,_HCI_PKT_TYPE,ulong,uchar,uchar)
0x14002d808  test    al, al
0x14002d80a  jnz     short loc_14002D861
0x14002d80c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d813  lea     ebx, [rdi+1]
0x14002d816  mov     eax, [rcx+2Ch]
0x14002d819  test    bl, al
0x14002d81b  jz      short loc_14002D827
0x14002d81d  cmp     [rcx+29h], bl
0x14002d820  jb      short loc_14002D827
0x14002d822  mov     dl, dil
0x14002d825  jmp     short loc_14002D829
0x14002d827  xor     dl, dl
0x14002d829  mov     r9, [rsi+10B0h]
0x14002d830  lea     r15, WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids
0x14002d837  mov     rcx, [rcx+18h]
0x14002d83b  mov     r8b, dil
0x14002d83e  mov     [rsp+100h+var_C0], r14
0x14002d843  mov     [rsp+100h+var_C8], r15
0x14002d848  mov     word ptr [rsp+100h+var_D0], 26h ; '&'
0x14002d84f  mov     dword ptr [rsp+100h+UserData], ebx
0x14002d853  mov     byte ptr [rsp+100h+UserDataCount], bl
0x14002d857  call    WPP_RECORDER_AND_TRACE_SF_q
0x14002d85c  jmp     loc_14002D929
0x14002d861  mov     r12, [rbp+57h+var_90.Flink]
0x14002d865  lea     rax, [rbp+57h+var_90]
0x14002d869  cmp     [r12+8], rax
0x14002d86e  jnz     loc_14002DC74
0x14002d874  mov     rax, [r12]
0x14002d878  cmp     [rax+8], r12
0x14002d87c  jnz     loc_14002DC74
0x14002d882  mov     [rbp+57h+var_90.Flink], rax
0x14002d886  lea     rcx, [rbp+57h+var_90]
0x14002d88a  mov     [rax+8], rcx
0x14002d88e  lea     rdx, [r13+0C8h]; struct HCI_L2CAP_DATA *
0x14002d895  mov     [r12+8], r12
0x14002d89a  lea     rax, ?HCI_CompleteAclRdChain@@YAXPEAU_BIP@@@Z; HCI_CompleteAclRdChain(_BIP *)
0x14002d8a1  mov     [r12], r12
0x14002d8a5  lea     rcx, [r14+10h]
0x14002d8a9  mov     [r12+38h], rax
0x14002d8ae  add     r12, 0FFFFFFFFFFFFFFA8h
0x14002d8b2  movzx   r9d, word ptr [r15+2]
0x14002d8b7  lea     rax, [r15+4]
0x14002d8bb  mov     qword ptr [rsp+100h+UserDataCount], rcx; struct _GUID *
0x14002d8c0  sub     r9w, 4; unsigned __int16
0x14002d8c5  mov     rcx, [rsi+4A0h]; struct L2CAP_INTERFACE *
0x14002d8cc  mov     r8, rax; struct _L2CAP_PDU_HEADER *
0x14002d8cf  mov     [rbp+57h+var_70], rax
0x14002d8d3  call    ?L2CapInt_VerifyIncomingReadPacket@@YAEPEAUL2CAP_INTERFACE@@PEAUHCI_L2CAP_DATA@@PEAU_L2CAP_PDU_HEADER@@GPEAU_GUID@@@Z; L2CapInt_VerifyIncomingReadPacket(L2CAP_INTERFACE *,HCI_L2CAP_DATA *,_L2CAP_PDU_HEADER *,ushort,_GUID *)
0x14002d8d8  xor     r9d, r9d
0x14002d8db  test    al, al
0x14002d8dd  jnz     loc_14002D979
0x14002d8e3  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d8ea  lea     ebx, [r9+2]
0x14002d8ee  mov     eax, [r8+2Ch]
0x14002d8f2  test    bl, al
0x14002d8f4  jz      short loc_14002D8FC
0x14002d8f6  cmp     [r8+29h], bl
0x14002d8fa  jnb     short loc_14002D8FF
0x14002d8fc  mov     dil, r9b
0x14002d8ff  movzx   ecx, word ptr [r15+4]
0x14002d904  mov     dl, dil
0x14002d907  movzx   eax, word ptr [r15+6]
0x14002d90c  mov     r9, [rsi+10B0h]
0x14002d913  mov     [rsp+100h+var_B0], r14
0x14002d918  mov     dword ptr [rsp+100h+var_B8], eax
0x14002d91c  mov     dword ptr [rsp+100h+var_C0], ecx
0x14002d920  mov     rcx, [r8+18h]
0x14002d924  call    WPP_RECORDER_AND_TRACE_SF_dDq
0x14002d929  lea     rcx, [r13+8]
0x14002d92d  mov     r8d, 43Bh
0x14002d933  lea     r9, aOnecoreDrivers_52; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002d93a  lea     rdx, ?HCI_GetConnectionOrZombieFromHandleLocked@@YAPEAU_HCI_CONNECTION@@PEAUHCI_INTERFACE@@G@Z; HCI_GetConnectionOrZombieFromHandleLocked(HCI_INTERFACE *,ushort)
0x14002d941  call    RefObj_ReleaseEx
0x14002d946  test    r12, r12
0x14002d949  jz      short loc_14002D95B
0x14002d94b  mov     rax, [r12+90h]
0x14002d953  mov     rcx, r12
0x14002d956  call    _guard_dispatch_icall
0x14002d95b  mov     rax, [rbp+57h+var_68]
0x14002d95f  mov     r9d, 0C000009Ah; int
0x14002d965  mov     rdx, r14; struct _BIP *
0x14002d968  mov     rcx, rsi; struct HCI_INTERFACE *
0x14002d96b  movzx   r8d, word ptr [rax]; unsigned __int16
0x14002d96f  call    ?HCI_TossAndMarkAclReadUnstable@@YAXPEAUHCI_INTERFACE@@PEAU_BIP@@GJ@Z; HCI_TossAndMarkAclReadUnstable(HCI_INTERFACE *,_BIP *,ushort,long)
0x14002d974  jmp     loc_14002DEB0
0x14002d979  mov     rax, [r12+98h]
0x14002d981  mov     [rbp+57h+var_A0], r9b
0x14002d985  mov     [rax+50h], r13
0x14002d989  jmp     short loc_14002D99C
0x14002d98b  mov     edi, 1
0x14002d990  lea     rax, [r15+4]
0x14002d994  mov     [rbp+57h+var_A0], dil
0x14002d998  mov     [rbp+57h+var_70], rax
0x14002d99c  mov     rcx, [rsi+4B0h]
0x14002d9a3  add     rcx, 168h; SpinLock
0x14002d9aa  mov     [rbp+57h+var_80], r9
0x14002d9ae  mov     [rbp+57h+var_78], r9
0x14002d9b2  mov     [rbp+57h+var_60], r9
0x14002d9b6  mov     [rbp+57h+var_9C], r9d
0x14002d9ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002d9c1  nop     dword ptr [rax+rax+00h]
0x14002d9c6  movzx   ecx, word ptr [r15]
0x14002d9ca  mov     [rbp+57h+NewIrql], al
0x14002d9cd  mov     eax, 3000h
0x14002d9d2  and     cx, ax
0x14002d9d5  cmp     cx, bx
0x14002d9d8  jnz     loc_14002DB1A
0x14002d9de  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d9e5  mov     ebx, 2
0x14002d9ea  mov     ecx, [r10+2Ch]
0x14002d9ee  test    bl, cl
0x14002d9f0  jz      short loc_14002D9FE
0x14002d9f2  cmp     byte ptr [r10+29h], 4
0x14002d9f7  jb      short loc_14002D9FE
0x14002d9f9  mov     dl, dil
0x14002d9fc  jmp     short loc_14002DA00
0x14002d9fe  xor     dl, dl
0x14002da00  movzx   eax, word ptr [r15+4]
0x14002da05  mov     r8b, dil
0x14002da08  mov     r9, [rsi+10B0h]
0x14002da0f  lea     r15, WPP_9c446551dbb43bf6e70198402e2ec18e_Traceguids
0x14002da16  mov     rcx, [r10+18h]
0x14002da1a  mov     dword ptr [rsp+100h+var_B8], eax
0x14002da1e  mov     [rsp+100h+var_C0], r12
0x14002da23  mov     [rsp+100h+var_C8], r15
0x14002da28  mov     word ptr [rsp+100h+var_D0], 28h ; '('
0x14002da2f  mov     dword ptr [rsp+100h+UserData], ebx
0x14002da33  mov     byte ptr [rsp+100h+UserDataCount], 4
0x14002da38  call    WPP_RECORDER_AND_TRACE_SF_qL
0x14002da3d  lea     rdx, [r13+1E0h]
0x14002da44  mov     r8, [rdx]
0x14002da47  test    r8, r8
0x14002da4a  jz      short loc_14002DABA
0x14002da4c  mov     rax, [r8+48h]
0x14002da50  mov     [rbp+57h+var_78], r8
0x14002da54  mov     rcx, [rax-20h]
0x14002da58  movzx   eax, word ptr [rcx]
0x14002da5b  mov     [rbp+57h+var_9C], eax
0x14002da5e  mov     qword ptr [rdx], 0
0x14002da65  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002da6c  mov     r10d, 4
0x14002da72  mov     eax, [rcx+2Ch]
0x14002da75  test    bl, al
0x14002da77  jz      short loc_14002DA84
0x14002da79  cmp     [rcx+29h], r10b
0x14002da7d  jb      short loc_14002DA84
0x14002da7f  mov     dl, dil
0x14002da82  jmp     short loc_14002DA86
0x14002da84  xor     dl, dl
  ... truncated ...
```
