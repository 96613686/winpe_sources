# HCI_SendNextAclWrite(HCI_INTERFACE *)

- ea: `0x140030f20`
- end: `0x14003177b`
- name: `?HCI_SendNextAclWrite@@YAJPEAUHCI_INTERFACE@@@Z`
- size: `2139`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *)`
- caller_count: `5`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400300d4`
- `0x140031ef8`
- `0x14004e1b0`
- `0x14004ede0`
- `0x1400e5900`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005b4c`
- `0x14002e67c`
- `0x14002e7f8`
- `0x14002f9ec`
- `0x1400302e4`
- `0x140030468`
- `0x140030f20`
- `0x140031784`
- `0x140031a70`
- `0x1400320e8`
- `0x1400350f0`
- `0x14003cea4`
- `0x14004f5f0`
- `0x1400b01d0`
- `0x14012ed14`
- `0x140161a44`
- `0x140161d7c`
- `0x140165580`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003120d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140031333`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400314b1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400314cb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003160f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400316e6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003120d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140031333`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400314b1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400314cb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003160f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400316e6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030fe4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140031380`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400313b1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400315cf`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400316b8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030fe4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140031380`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400313b1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400315cf`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400316b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030fc2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031364`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400315b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031696`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030fc2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031364`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400315b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031696`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031226`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003134c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400314e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031625`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400316fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031226`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003134c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400314e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031625`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400316fc`

## string_xrefs

- `0x140031158`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`
- `0x140031643`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`
- `0x14003167c`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`

## pseudocode

```c
__int64 __fastcall HCI_SendNextAclWrite(struct HCI_INTERFACE *a1)
{
  unsigned int v2; // ebx
  char v3; // r14
  char v4; // dl
  __int16 DeviceType; // ax
  KIRQL v6; // si
  int v7; // edx
  unsigned __int8 v8; // r12
  char *v9; // rcx
  __int64 *v10; // rsi
  __int64 v11; // rax
  struct _HCI_CONNECTION *v12; // rsi
  _LIST_ENTRY *p_BestEffortCxnWrQueueEntry; // rax
  struct _GUID **p_CurrentBestEffortAclWrite; // r15
  __int64 *v15; // r8
  __int64 v16; // r13
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  __int64 *v20; // r8
  struct _GUID *v21; // r15
  int v22; // edx
  __int64 *v23; // r8
  unsigned __int64 *p_HciLock; // rcx
  _LARGE_INTEGER v25; // rbx
  unsigned __int64 ForceActiveOnActivityThresholdTicks; // rdx
  int v27; // edx
  int v28; // r8d
  _QWORD *v29; // r15
  __int64 *v30; // rbx
  __int64 v31; // rax
  _BIP *v32; // rax
  int v33; // edx
  int v34; // r8d
  void (*v35)(void); // rax
  KIRQL v36; // r13
  char v37; // r15
  unsigned int v38; // r8d
  int v39; // edx
  int v40; // r8d
  __int16 v41; // ax
  __int64 v43; // [rsp+48h] [rbp-21h]
  __int64 v44; // [rsp+48h] [rbp-21h]
  unsigned __int16 v45[2]; // [rsp+50h] [rbp-19h] BYREF
  struct _CMD_Exit_Park_Mode v46; // [rsp+54h] [rbp-15h] BYREF
  struct _BIP *v47; // [rsp+60h] [rbp-9h]
  _OWORD v48[5]; // [rsp+68h] [rbp-1h] BYREF
  KIRQL NewIrql; // [rsp+D0h] [rbp+67h]
  unsigned __int8 v50; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int8 v51; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int16 v52; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = 0;
  v51 = 0;
  v45[0] = 0;
  v52 = 0;
  v50 = 0;
  v3 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v4 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v4 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v4 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      DeviceType != 0,
      a1->IfrLog,
      5,
      2,
      43,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
      a1);
  NewIrql = KeAcquireSpinLockRaiseToDpc(&a1->HciLock);
  v6 = NewIrql;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject);
  while ( !a1->CurrentAclWriteSegment )
  {
    if ( a1->ControllerState )
      break;
    *(_DWORD *)&v46.HciCmd.Op_Code = 0;
    HIBYTE(v46.Connection_Handle) = 0;
    v2 = HCI_PeekAclWriteCredit(a1, v45, &v52);
    if ( v2 )
      break;
    if ( !HCI_ScheduleWriteQueues(a1, v45[0], v52, &v50) )
    {
      v2 = 0;
      break;
    }
    v8 = v50;
    v9 = (char *)&a1->GuaranteedCxnWriteQueue + (-(__int64)(v50 != 0) & 0xFFFFFFFFFFFFFFF0uLL);
    v10 = *(__int64 **)v9;
    if ( *(char **)(*(_QWORD *)v9 + 8LL) != v9 )
      goto LABEL_74;
    v11 = *v10;
    if ( *(__int64 **)(*v10 + 8) != v10 )
      goto LABEL_74;
    *(_QWORD *)v9 = v11;
    *(_QWORD *)(v11 + 8) = v9;
    if ( v8 )
      v12 = (struct _HCI_CONNECTION *)(v10 - 53);
    else
      v12 = (struct _HCI_CONNECTION *)(v10 - 55);
    p_BestEffortCxnWrQueueEntry = &v12->BestEffortCxnWrQueueEntry;
    if ( v8 )
    {
      p_CurrentBestEffortAclWrite = (struct _GUID **)&v12->CurrentBestEffortAclWrite;
    }
    else
    {
      p_BestEffortCxnWrQueueEntry = &v12->GuaranteedCxnWrQueueEntry;
      p_CurrentBestEffortAclWrite = (struct _GUID **)&v12->CurrentGuaranteedAclWrite;
    }
    p_BestEffortCxnWrQueueEntry->Blink = p_BestEffortCxnWrQueueEntry;
    p_BestEffortCxnWrQueueEntry->Flink = p_BestEffortCxnWrQueueEntry;
    if ( *p_CurrentBestEffortAclWrite )
    {
      v16 = *(_QWORD *)(*p_CurrentBestEffortAclWrite)[9].Data4;
      RefObj_AddRefEx(
        v16 + 72,
        HCI_SendNextAclWrite,
        1448,
        "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
      v48[0] = 0;
      if ( v16 )
      {
        *((_QWORD *)&v48[0] + 1) = v16;
        *(_QWORD *)&v48[0] = HCI_SendNextAclWrite;
      }
      v17 = HCI_CxnReadyForDataTransfer(v12, &v46, &v51);
      v2 = v17;
      if ( v17 == 259 )
      {
        LOBYTE(v18) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        v20 = WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids;
        LOBYTE(v20) = 1;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v18,
          (_DWORD)v20,
          v12->Dib->IfrLog,
          4,
          2,
          45,
          (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
        v21 = *p_CurrentBestEffortAclWrite;
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject);
        KeReleaseSpinLock(&a1->HciLock, NewIrql);
        if ( v51 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v22) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
            LOBYTE(v22) = 0;
          v23 = WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids;
          LOBYTE(v23) = 1;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v22,
            (_DWORD)v23,
            v12->Dib->IfrLog,
            4,
            2,
            46,
            (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
          v2 = HCI_SendCommandEx(a1, &v46.HciCmd, v21 + 1, HCI_CxnEnterActiveModeCallback, v12, 0, 0);
        }
        _Reset___RefObjReference_U_HCI_ACLWR_BIP_CONTEXT___0EI__M__T0A__M__T0A___QEAAXPEAU_HCI_ACLWR_BIP_CONTEXT__PEBX_Z(v48);
        p_HciLock = &a1->HciLock;
        goto LABEL_73;
      }
      if ( v17 )
      {
        LOBYTE(v18) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        LOBYTE(v19) = 1;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v18,
          v19,
          v12->Dib->IfrLog,
          4,
          2,
          47,
          (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject);
        KeReleaseSpinLock(&a1->HciLock, NewIrql);
        _Reset___RefObjReference_U_HCI_ACLWR_BIP_CONTEXT___0EI__M__T0A__M__T0A___QEAAXPEAU_HCI_ACLWR_BIP_CONTEXT__PEBX_Z(v48);
        v6 = KeAcquireSpinLockRaiseToDpc(&a1->HciLock);
        NewIrql = v6;
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject);
        _Reset___RefObjReference_U_HCI_ACLWR_BIP_CONTEXT___0EI__M__T0A__M__T0A___QEAAXPEAU_HCI_ACLWR_BIP_CONTEXT__PEBX_Z(v48);
      }
      else
      {
        PowerCoordinator::DisableIdle((PowerCoordinator *)&a1->DevExt[1].BtDevice.PhysicalDeviceObject);
        KeAcquireSpinLockAtDpcLevel(&v12->StateLock);
        if ( a1->SMMEnabled )
        {
          v25.QuadPart = MEMORY[0xFFFFF78000000320];
          ForceActiveOnActivityThresholdTicks = v12->ForceActiveOnActivityThresholdTicks;
          if ( ForceActiveOnActivityThresholdTicks
            && MEMORY[0xFFFFF78000000320] - v12->LatestLinkActivityTickCount.QuadPart <= ForceActiveOnActivityThresholdTicks )
          {
            HCI_CxnForceActiveModeForDurationLocked(v12, ForceActiveOnActivityThresholdTicks);
          }
          v12->LatestLinkActivityTickCount = v25;
        }
        HCI_AcquireAclWriteCredit(a1, v12);
        v29 = (_QWORD *)(v16 + 56);
        v30 = *(__int64 **)(v16 + 56);
        if ( v30[1] != v16 + 56 || (v31 = *v30, *(__int64 **)(*v30 + 8) != v30) )
LABEL_74:
          __fastfail(3u);
        *v29 = v31;
        *(_QWORD *)(v31 + 8) = v29;
        v30[1] = (__int64)v30;
        *v30 = (__int64)v30;
        v47 = (struct _BIP *)*(v30 - 7);
        *((_BYTE *)v30 + 49) = 1;
        LOBYTE(v27) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        LOBYTE(v28) = 1;
        LODWORD(v43) = *(_DWORD *)(v16 + 40);
        WPP_RECORDER_AND_TRACE_SF_LL(
          WPP_GLOBAL_Control->AttachedDevice,
          v27,
          v28,
          a1->IfrLog,
          4,
          2,
          48,
          (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
          *(_DWORD *)(v16 + 44),
          v43);
        v32 = v47;
        ++*(_DWORD *)(v16 + 44);
        a1->CurrentAclWriteSegment = v32;
        KeReleaseSpinLockFromDpcLevel(&v12->StateLock);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject);
        KeReleaseSpinLock(&a1->HciLock, NewIrql);
        if ( !_bittest16((const signed __int16 *)v47->BufferData, 0xCu) )
        {
          v35 = *(void (**)(void))(*(v30 - 6) + 136);
          if ( v35 )
            v35();
        }
        LOBYTE(v33) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        LOBYTE(v34) = 1;
        LODWORD(v44) = *(_DWORD *)(v16 + 40);
        WPP_RECORDER_AND_TRACE_SF_LL(
          WPP_GLOBAL_Control->AttachedDevice,
          v33,
          v34,
          a1->IfrLog,
          4,
          2,
          49,
          (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
          *(_DWORD *)(v16 + 44),
          v44);
        if ( !*((_BYTE *)v30 + 48) )
          LogEtwHciBip(v47, a1->CommandPacketsAllowed, a1->AclWriteCredits, a1->DevExt->EtwLogSensitiveData);
        HCI_WriteAclBip(a1, v47);
        v2 = 259;
        v36 = KeAcquireSpinLockRaiseToDpc(&a1->HciLock);
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject);
        a1->CurrentAclWriteSegment = 0;
        if ( (_QWORD *)*v29 == v29 )
        {
          v37 = 1;
        }
        else
        {
          HCI_ScheduleAclWrCxn(a1, v12, v8);
          v37 = 0;
        }
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject);
        KeReleaseSpinLock(&a1->HciLock, v36);
        if ( v37 )
          RefObj_AddRefEx(
            &v12->RefObj,
            HCI_SendNextAclWrite,
            1632,
            "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
        _Reset___RefObjReference_U_HCI_ACLWR_BIP_CONTEXT___0EI__M__T0A__M__T0A___QEAAXPEAU_HCI_ACLWR_BIP_CONTEXT__PEBX_Z(v48);
        if ( v37 )
        {
          HCI_TryToCompleteCurrentAclWrite(a1, v12, v38, v8);
          RefObj_ReleaseEx(
            &v12->RefObj,
            HCI_SendNextAclWrite,
            1641,
            "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
        }
        p_HciLock = &a1->HciLock;
LABEL_73:
        NewIrql = KeAcquireSpinLockRaiseToDpc(p_HciLock);
        v6 = NewIrql;
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject);
        _Reset___RefObjReference_U_HCI_ACLWR_BIP_CONTEXT___0EI__M__T0A__M__T0A___QEAAXPEAU_HCI_ACLWR_BIP_CONTEXT__PEBX_Z(v48);
      }
    }
    else
    {
      LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      v15 = WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids;
      LOBYTE(v15) = 1;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        (_DWORD)v15,
        v12->Dib->IfrLog,
        4,
        2,
        44,
        (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
      HCI_AdvanceAclWrQueue(a1, v12, v8 != 0);
      v6 = NewIrql;
    }
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&a1->BtDevice[11].FunctionalDeviceObject);
  KeReleaseSpinLock(&a1->HciLock, v6);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v3 = 0;
  v41 = WPP_GLOBAL_Control->DeviceType;
  if ( v3 || v41 )
  {
    LOBYTE(v39) = v3;
    LOBYTE(v40) = v41 != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v39,
      v40,
      a1->IfrLog,
      5,
      2,
      50,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
      v2);
  }
  return v2;
}

```

## disassembly

```asm
0x140030f20  push    rbp
0x140030f22  push    rbx
0x140030f23  push    rsi
0x140030f24  push    rdi
0x140030f25  push    r12
0x140030f27  push    r13
0x140030f29  push    r14
0x140030f2b  push    r15
0x140030f2d  lea     rbp, [rsp-1Fh]
0x140030f32  sub     rsp, 88h
0x140030f39  xor     r13d, r13d
0x140030f3c  mov     rdi, rcx
0x140030f3f  mov     ebx, r13d
0x140030f42  mov     [rbp+57h+arg_10], r13b
0x140030f46  mov     [rbp+57h+var_70], r13w
0x140030f4b  mov     [rbp+57h+arg_18], r13w
0x140030f50  mov     [rbp+57h+arg_8], r13b
0x140030f54  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030f5b  lea     r14d, [r13+1]
0x140030f5f  mov     eax, [rcx+2Ch]
0x140030f62  test    al, 2
0x140030f64  jz      short loc_140030F6F
0x140030f66  cmp     byte ptr [rcx+29h], 5
0x140030f6a  mov     dl, r14b
0x140030f6d  jnb     short loc_140030F72
0x140030f6f  mov     dl, r13b
0x140030f72  movzx   eax, word ptr [rcx+48h]
0x140030f76  lea     r9, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x140030f7d  test    ax, ax
0x140030f80  setnz   r8b
0x140030f84  test    dl, dl
0x140030f86  jnz     short loc_140030F8D
0x140030f88  test    ax, ax
0x140030f8b  jz      short loc_140030FBB
0x140030f8d  mov     rcx, [rcx+18h]
0x140030f91  mov     [rsp+0C0h+var_80], rdi
0x140030f96  mov     [rsp+0C0h+var_88], r9
0x140030f9b  mov     r9, [rdi+10B0h]
0x140030fa2  mov     word ptr [rsp+0C0h+var_90], 2Bh ; '+'
0x140030fa9  mov     [rsp+0C0h+var_98], 2
0x140030fb1  mov     byte ptr [rsp+0C0h+var_A0], 5
0x140030fb6  call    WPP_RECORDER_AND_TRACE_SF_q
0x140030fbb  lea     rcx, [rdi+7B0h]; SpinLock
0x140030fc2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030fc9  nop     dword ptr [rax+rax+00h]
0x140030fce  mov     rcx, [rdi+4B0h]
0x140030fd5  mov     r15d, 168h
0x140030fdb  add     rcx, r15; SpinLock
0x140030fde  mov     [rbp+57h+NewIrql], al
0x140030fe1  mov     sil, al
0x140030fe4  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140030feb  nop     dword ptr [rax+rax+00h]
0x140030ff0  lea     r12, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x140030ff7  cmp     [rdi+9B0h], r13
0x140030ffe  jnz     loc_1400316DC
0x140031004  cmp     [rdi+20h], r13d
0x140031008  jnz     loc_1400316DC
0x14003100e  xor     eax, eax
0x140031010  lea     r8, [rbp+57h+arg_18]; unsigned __int16 *
0x140031014  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x140031018  mov     dword ptr [rbp+57h+var_6C.HciCmd.Op_Code], eax
0x14003101b  mov     rcx, rdi; struct HCI_INTERFACE *
0x14003101e  mov     byte ptr [rbp+57h+var_6C.Connection_Handle+1], al
0x140031021  call    ?HCI_PeekAclWriteCredit@@YAJPEAUHCI_INTERFACE@@PEAG1@Z; HCI_PeekAclWriteCredit(HCI_INTERFACE *,ushort *,ushort *)
0x140031026  mov     ebx, eax
0x140031028  test    eax, eax
0x14003102a  jnz     loc_1400316DC
0x140031030  movzx   r8d, [rbp+57h+arg_18]; unsigned __int16
0x140031035  lea     r9, [rbp+57h+arg_8]; unsigned __int8 *
0x140031039  movzx   edx, [rbp+57h+var_70]; unsigned __int16
0x14003103d  mov     rcx, rdi; struct HCI_INTERFACE *
0x140031040  call    ?HCI_ScheduleWriteQueues@@YAEPEAUHCI_INTERFACE@@GGPEAE@Z; HCI_ScheduleWriteQueues(HCI_INTERFACE *,ushort,ushort,uchar *)
0x140031045  test    al, al
0x140031047  jz      loc_1400316D9
0x14003104d  mov     r12b, [rbp+57h+arg_8]
0x140031051  mov     cl, r12b
0x140031054  neg     cl
0x140031056  lea     rcx, [rdi+9D0h]
0x14003105d  sbb     rax, rax
0x140031060  and     rax, 0FFFFFFFFFFFFFFF0h
0x140031064  add     rcx, rax
0x140031067  mov     rsi, [rcx]
0x14003106a  cmp     [rsi+8], rcx
0x14003106e  jnz     loc_1400316D2
0x140031074  mov     rax, [rsi]
0x140031077  cmp     [rax+8], rsi
0x14003107b  jnz     loc_1400316D2
0x140031081  mov     [rcx], rax
0x140031084  mov     [rax+8], rcx
0x140031088  test    r12b, r12b
0x14003108b  jz      short loc_140031096
0x14003108d  add     rsi, 0FFFFFFFFFFFFFE58h
0x140031094  jmp     short loc_14003109D
0x140031096  add     rsi, 0FFFFFFFFFFFFFE48h
0x14003109d  lea     rax, [rsi+1A8h]
0x1400310a4  test    r12b, r12b
0x1400310a7  jnz     short loc_1400310E3
0x1400310a9  lea     rax, [rsi+1B8h]
0x1400310b0  lea     r15, [rsi+1A0h]
0x1400310b7  mov     [rax+8], rax
0x1400310bb  mov     [rax], rax
0x1400310be  mov     r13, [r15]
0x1400310c1  test    r13, r13
0x1400310c4  jnz     loc_14003114A
0x1400310ca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400310d1  mov     eax, [rcx+2Ch]
0x1400310d4  test    al, 2
0x1400310d6  jz      short loc_1400310EC
0x1400310d8  cmp     byte ptr [rcx+29h], 4
0x1400310dc  jb      short loc_1400310EC
0x1400310de  mov     dl, r14b
0x1400310e1  jmp     short loc_1400310F2
0x1400310e3  lea     r15, [rsi+198h]
0x1400310ea  jmp     short loc_1400310B7
0x1400310ec  xor     r13d, r13d
0x1400310ef  mov     dl, r13b
0x1400310f2  mov     r9, [rsi+30h]
0x1400310f6  lea     r8, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x1400310fd  mov     rcx, [rcx+18h]
0x140031101  mov     [rsp+0C0h+var_88], r8
0x140031106  mov     r8b, r14b
0x140031109  mov     word ptr [rsp+0C0h+var_90], 2Ch ; ','
0x140031110  mov     r9, [r9+838h]
0x140031117  mov     [rsp+0C0h+var_98], 2
0x14003111f  mov     byte ptr [rsp+0C0h+var_A0], 4
0x140031124  call    WPP_RECORDER_AND_TRACE_SF_
0x140031129  test    r12b, r12b
0x14003112c  mov     rdx, rsi; struct _HCI_CONNECTION *
0x14003112f  mov     rcx, rdi; struct HCI_INTERFACE *
0x140031132  setnz   r8b; bool
0x140031136  call    ?HCI_AdvanceAclWrQueue@@YAXPEAUHCI_INTERFACE@@PEAU_HCI_CONNECTION@@_N@Z; HCI_AdvanceAclWrQueue(HCI_INTERFACE *,_HCI_CONNECTION *,bool)
0x14003113b  mov     sil, [rbp+57h+NewIrql]
0x14003113f  mov     r15d, 168h
0x140031145  jmp     loc_140030FF0
0x14003114a  mov     r13, [r13+98h]
0x140031151  lea     rbx, ?HCI_SendNextAclWrite@@YAJPEAUHCI_INTERFACE@@@Z; HCI_SendNextAclWrite(HCI_INTERFACE *)
0x140031158  lea     r9, aOnecoreDrivers_32; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14003115f  mov     r8d, 5A8h
0x140031165  mov     rdx, rbx
0x140031168  lea     rcx, [r13+48h]
0x14003116c  call    RefObj_AddRefEx
0x140031171  xorps   xmm0, xmm0
0x140031174  movdqu  [rbp+57h+var_58], xmm0
0x140031179  test    r13, r13
0x14003117c  jz      short loc_140031186
0x14003117e  mov     qword ptr [rbp+57h+var_58+8], r13
0x140031182  mov     qword ptr [rbp+57h+var_58], rbx
0x140031186  lea     r8, [rbp+57h+arg_10]; unsigned __int8 *
0x14003118a  mov     rcx, rsi; struct _HCI_CONNECTION *
0x14003118d  lea     rdx, [rbp+57h+var_6C]; struct _CMD_Exit_Park_Mode *
0x140031191  call    ?HCI_CxnReadyForDataTransfer@@YAJPEAU_HCI_CONNECTION@@PEAU_CMD_Exit_Park_Mode@@PEAE@Z; HCI_CxnReadyForDataTransfer(_HCI_CONNECTION *,_CMD_Exit_Park_Mode *,uchar *)
0x140031196  mov     ebx, eax
0x140031198  cmp     eax, 103h
0x14003119d  jnz     loc_1400312C2
0x1400311a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400311aa  mov     eax, [rcx+2Ch]
0x1400311ad  test    al, 2
0x1400311af  jz      short loc_1400311BF
0x1400311b1  cmp     byte ptr [rcx+29h], 4
0x1400311b5  jb      short loc_1400311BF
0x1400311b7  mov     dl, r14b
0x1400311ba  xor     r13d, r13d
0x1400311bd  jmp     short loc_1400311C5
0x1400311bf  xor     r13d, r13d
0x1400311c2  mov     dl, r13b
0x1400311c5  mov     r9, [rsi+30h]
0x1400311c9  lea     r8, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x1400311d0  mov     rcx, [rcx+18h]
0x1400311d4  mov     [rsp+0C0h+var_88], r8
0x1400311d9  mov     r8b, r14b
0x1400311dc  mov     word ptr [rsp+0C0h+var_90], 2Dh ; '-'
0x1400311e3  mov     r9, [r9+838h]
0x1400311ea  mov     [rsp+0C0h+var_98], 2
0x1400311f2  mov     byte ptr [rsp+0C0h+var_A0], 4
0x1400311f7  call    WPP_RECORDER_AND_TRACE_SF_
0x1400311fc  mov     rcx, [rdi+4B0h]
0x140031203  mov     r15, [r15]
0x140031206  add     rcx, 168h; SpinLock
0x14003120d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140031214  nop     dword ptr [rax+rax+00h]
0x140031219  mov     dl, [rbp+57h+NewIrql]; NewIrql
0x14003121c  lea     r12, [rdi+7B0h]
0x140031223  mov     rcx, r12; SpinLock
0x140031226  call    cs:__imp_KeReleaseSpinLock
0x14003122d  nop     dword ptr [rax+rax+00h]
0x140031232  cmp     [rbp+57h+arg_10], r13b
0x140031236  jz      short loc_1400312B1
0x140031238  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003123f  mov     eax, [rcx+2Ch]
0x140031242  test    al, 2
0x140031244  jz      short loc_14003124F
0x140031246  cmp     byte ptr [rcx+29h], 4
0x14003124a  mov     dl, r14b
0x14003124d  jnb     short loc_140031252
0x14003124f  mov     dl, r13b
0x140031252  mov     r9, [rsi+30h]
0x140031256  lea     r8, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14003125d  mov     rcx, [rcx+18h]
0x140031261  mov     [rsp+0C0h+var_88], r8
0x140031266  mov     r8b, r14b
0x140031269  mov     word ptr [rsp+0C0h+var_90], 2Eh ; '.'
0x140031270  mov     r9, [r9+838h]
0x140031277  mov     [rsp+0C0h+var_98], 2
0x14003127f  mov     byte ptr [rsp+0C0h+var_A0], 4
0x140031284  call    WPP_RECORDER_AND_TRACE_SF_
0x140031289  mov     [rsp+0C0h+var_90], r13; void *
0x14003128e  lea     r9, ?HCI_CxnEnterActiveModeCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z; void (*)(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *)
0x140031295  mov     [rsp+0C0h+var_98], r13d; unsigned int
0x14003129a  lea     r8, [r15+10h]; struct _GUID *
0x14003129e  lea     rdx, [rbp+57h+var_6C]; struct _HCI_COMMAND_HEADER *
0x1400312a2  mov     [rsp+0C0h+var_A0], rsi; void *
0x1400312a7  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400312aa  call    ?HCI_SendCommandEx@@YAJPEAUHCI_INTERFACE@@PEAU_HCI_COMMAND_HEADER@@PEAU_GUID@@P6AXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z4K4@Z; HCI_SendCommandEx(HCI_INTERFACE *,_HCI_COMMAND_HEADER *,_GUID *,void (*)(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *),void *,ulong,void *)
0x1400312af  mov     ebx, eax
0x1400312b1  lea     rcx, [rbp+57h+var_58]
0x1400312b5  call    ?Reset@?$RefObjReference@U_HCI_ACLWR_BIP_CONTEXT@@$0EI@$M$$T0A@$M$$T0A@@@QEAAXPEAU_HCI_ACLWR_BIP_CONTEXT@@PEBX@Z
0x1400312ba  mov     rcx, r12
0x1400312bd  jmp     loc_140031696
0x1400312c2  test    eax, eax
0x1400312c4  jz      loc_14003139A
0x1400312ca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400312d1  mov     eax, [rcx+2Ch]
0x1400312d4  test    al, 2
0x1400312d6  jz      short loc_1400312E6
0x1400312d8  cmp     byte ptr [rcx+29h], 4
0x1400312dc  jb      short loc_1400312E6
0x1400312de  mov     dl, r14b
0x1400312e1  xor     r13d, r13d
0x1400312e4  jmp     short loc_1400312EC
0x1400312e6  xor     r13d, r13d
0x1400312e9  mov     dl, r13b
0x1400312ec  mov     r9, [rsi+30h]
0x1400312f0  lea     r12, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x1400312f7  mov     rcx, [rcx+18h]
0x1400312fb  mov     r8b, r14b
0x1400312fe  mov     [rsp+0C0h+var_88], r12
0x140031303  mov     word ptr [rsp+0C0h+var_90], 2Fh ; '/'
0x14003130a  mov     r9, [r9+838h]
0x140031311  mov     [rsp+0C0h+var_98], 2
0x140031319  mov     byte ptr [rsp+0C0h+var_A0], 4
0x14003131e  call    WPP_RECORDER_AND_TRACE_SF_
0x140031323  mov     rcx, [rdi+4B0h]
0x14003132a  mov     r15d, 168h
0x140031330  add     rcx, r15; SpinLock
0x140031333  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14003133a  nop     dword ptr [rax+rax+00h]
0x14003133f  mov     dl, [rbp+57h+NewIrql]; NewIrql
0x140031342  lea     rsi, [rdi+7B0h]
0x140031349  mov     rcx, rsi; SpinLock
0x14003134c  call    cs:__imp_KeReleaseSpinLock
0x140031353  nop     dword ptr [rax+rax+00h]
0x140031358  lea     rcx, [rbp+57h+var_58]
0x14003135c  call    ?Reset@?$RefObjReference@U_HCI_ACLWR_BIP_CONTEXT@@$0EI@$M$$T0A@$M$$T0A@@@QEAAXPEAU_HCI_ACLWR_BIP_CONTEXT@@PEBX@Z
0x140031361  mov     rcx, rsi; SpinLock
0x140031364  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003136b  nop     dword ptr [rax+rax+00h]
0x140031370  mov     rcx, [rdi+4B0h]
0x140031377  mov     sil, al
0x14003137a  add     rcx, r15; SpinLock
0x14003137d  mov     [rbp+57h+NewIrql], al
0x140031380  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140031387  nop     dword ptr [rax+rax+00h]
0x14003138c  lea     rcx, [rbp+57h+var_58]
0x140031390  call    ?Reset@?$RefObjReference@U_HCI_ACLWR_BIP_CONTEXT@@$0EI@$M$$T0A@$M$$T0A@@@QEAAXPEAU_HCI_ACLWR_BIP_CONTEXT@@PEBX@Z
0x140031395  jmp     loc_140030FF7
0x14003139a  mov     rcx, [rdi+4A8h]
0x1400313a1  add     rcx, 300h; this
0x1400313a8  call    ?DisableIdle@PowerCoordinator@@QEAAXXZ; PowerCoordinator::DisableIdle(void)
0x1400313ad  lea     rcx, [rsi+50h]; SpinLock
0x1400313b1  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400313b8  nop     dword ptr [rax+rax+00h]
0x1400313bd  cmp     byte ptr [rdi+0F2Ch], 0
0x1400313c4  jz      short loc_1400313FD
0x1400313c6  mov     rbx, 0FFFFF78000000320h
0x1400313d0  mov     rbx, [rbx]
0x1400313d3  mov     rdx, [rsi+4E0h]; unsigned __int64
0x1400313da  test    rdx, rdx
0x1400313dd  jz      short loc_1400313F6
0x1400313df  mov     rax, rbx
0x1400313e2  sub     rax, [rsi+4C8h]
0x1400313e9  cmp     rax, rdx
0x1400313ec  ja      short loc_1400313F6
0x1400313ee  mov     rcx, rsi; struct _HCI_CONNECTION *
0x1400313f1  call    ?HCI_CxnForceActiveModeForDurationLocked@@YAXPEAU_HCI_CONNECTION@@_K@Z; HCI_CxnForceActiveModeForDurationLocked(_HCI_CONNECTION *,unsigned __int64)
0x1400313f6  mov     [rsi+4C8h], rbx
0x1400313fd  mov     rdx, rsi; struct _HCI_CONNECTION *
0x140031400  mov     rcx, rdi; struct HCI_INTERFACE *
0x140031403  call    ?HCI_AcquireAclWriteCredit@@YAJPEAUHCI_INTERFACE@@PEAU_HCI_CONNECTION@@@Z; HCI_AcquireAclWriteCredit(HCI_INTERFACE *,_HCI_CONNECTION *)
0x140031408  lea     r15, [r13+38h]
0x14003140c  mov     rbx, [r15]
0x14003140f  cmp     [rbx+8], r15
0x140031413  jnz     loc_1400316D2
0x140031419  mov     rax, [rbx]
0x14003141c  cmp     [rax+8], rbx
0x140031420  jnz     loc_1400316D2
0x140031426  mov     [r15], rax
0x140031429  mov     [rax+8], r15
0x14003142d  mov     [rbx+8], rbx
0x140031431  mov     [rbx], rbx
0x140031434  mov     rax, [rbx-38h]
  ... truncated ...
```
