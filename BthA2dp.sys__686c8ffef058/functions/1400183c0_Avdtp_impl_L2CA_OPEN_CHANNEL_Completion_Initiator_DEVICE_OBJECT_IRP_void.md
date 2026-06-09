# Avdtp_impl::L2CA_OPEN_CHANNEL_Completion_Initiator(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1400183c0`
- end: `0x140018caa`
- name: `?L2CA_OPEN_CHANNEL_Completion_Initiator@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `2282`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003530`
- `0x14000e690`
- `0x14000f570`
- `0x14000f6e4`
- `0x140010628`
- `0x140011d60`
- `0x14001232c`
- `0x140012a5c`
- `0x1400183c0`
- `0x14001c8d0`
- `0x14001c948`
- `0x14001ced8`
- `0x14002d890`
- `0x140036494`
- `0x14003b244`
- `0x14004d790`
- `0x140055344`
- `0x140055998`
- `0x140055d20`
- `0x140056900`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140018822`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018c57`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018822`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018c57`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400185a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018806`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018c27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400185a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018806`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018c27`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::L2CA_OPEN_CHANNEL_Completion_Initiator(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        char *a3,
        __int64 a4)
{
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  bool v10; // r12
  _UNKNOWN **v11; // rcx
  char v12; // bl
  int IfrRecorderLog; // eax
  __int64 v14; // r10
  int v15; // edx
  int v16; // r8d
  PIO_SECURITY_CONTEXT SecurityContext; // rsi
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // ebp
  KSPIN_LOCK *v21; // rcx
  bool v22; // r13
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  PDEVICE_OBJECT Timer_high; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // eax
  __int64 v34; // r10
  int v35; // edx
  int v36; // r8d
  KIRQL v37; // dl
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // r8
  int v44; // eax
  __int64 v45; // r10
  int v46; // edx
  int v47; // r8d
  int v48; // eax
  __int64 v49; // r10
  int v50; // edx
  int v51; // r8d
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  int v60; // eax
  __int64 v61; // r10
  int v62; // edx
  int v63; // r8d
  int v64; // r8d
  __int64 *v65; // rdx
  __int64 *v66; // rdx
  int v67; // r8d
  __int64 *v68; // rdx
  __int64 *v69; // rdx
  KIRQL v70; // al
  __int64 v71; // rbx
  KIRQL v72; // si
  int v74; // [rsp+20h] [rbp-78h]
  int v75; // [rsp+28h] [rbp-70h]
  int v76; // [rsp+30h] [rbp-68h]
  int v77; // [rsp+38h] [rbp-60h]
  char v78; // [rsp+A8h] [rbp+10h]
  KIRQL v79; // [rsp+B0h] [rbp+18h]

  IsEnabledDeviceUsageNoInline = Feature_60817472__private_IsEnabledDeviceUsageNoInline(a1, a2, a3, a4);
  v10 = 0;
  v11 = &WPP_RECORDER_INITIALIZED;
  v12 = 1;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      LOBYTE(v7) = 0;
    }
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      IfrRecorderLog = GetIfrRecorderLog(2, v7, v8);
      WPP_RECORDER_AND_TRACE_SF_qi(
        *(_QWORD *)(v14 + 24),
        v15,
        v16,
        IfrRecorderLog,
        4,
        4,
        199,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        (char)a3,
        (char)a2);
    }
  }
  if ( !a2 )
  {
    Avdtp_impl::SetAvdtpState(a3, 1);
    return 3221225494LL;
  }
  SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v11, v7, v8, v9) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v18) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      LOBYTE(v18) = 0;
    }
    if ( (_BYTE)v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_ddqq(
        WPP_GLOBAL_Control->AttachedDevice,
        v18,
        v19,
        WPP_GLOBAL_Control->DeviceExtension,
        v74,
        v75,
        200,
        v77,
        a2->IoStatus.Status,
        HIDWORD(SecurityContext[1].SecurityQos),
        *(_QWORD *)&SecurityContext[4].DesiredAccess,
        (char)a3);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v18) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      LOBYTE(v18) = 0;
    }
    if ( (_BYTE)v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_ddDq(
        WPP_GLOBAL_Control->AttachedDevice,
        v18,
        v19,
        WPP_GLOBAL_Control->DeviceExtension,
        v74,
        v75,
        v76,
        v77,
        a2->IoStatus.Status,
        HIDWORD(SecurityContext[1].SecurityQos),
        (char)SecurityContext[1].AccessState,
        *(_QWORD *)&SecurityContext[4].DesiredAccess);
    }
  }
  if ( !SecurityContext || a2->IoStatus.Status || (v20 = 1, HIDWORD(SecurityContext[1].SecurityQos)) )
    v20 = 0;
  v78 = 0;
  v21 = (KSPIN_LOCK *)(a3 + 1600);
  if ( v20 )
  {
    v22 = 1;
    v79 = KeAcquireSpinLockRaiseToDpc(v21);
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v24, v23, v25, v26) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (Timer_high = (PDEVICE_OBJECT)HIDWORD(WPP_GLOBAL_Control->Timer), ((unsigned __int8)Timer_high & 8) == 0)
        || (LOBYTE(v27) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      {
        LOBYTE(v27) = 0;
      }
      LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qLq(
          WPP_GLOBAL_Control->AttachedDevice,
          v27,
          v29,
          WPP_GLOBAL_Control->DeviceExtension,
          4);
    }
    else
    {
      Timer_high = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || (LOBYTE(v27) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      {
        LOBYTE(v27) = 0;
      }
      LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qL(
          WPP_GLOBAL_Control->AttachedDevice,
          v27,
          v29,
          WPP_GLOBAL_Control->DeviceExtension,
          4);
    }
    v10 = *((_DWORD *)a3 + 36) == 3;
    *((_QWORD *)a3 + 141) = *((_QWORD *)a3 + 140);
    if ( *((_QWORD *)a3 + 143) )
    {
      *((_QWORD *)a3 + 179) = *(_QWORD *)&SecurityContext[4].DesiredAccess;
      *((_OWORD *)a3 + 90) = *(_OWORD *)&SecurityContext[15].DesiredAccess;
      *((_OWORD *)a3 + 91) = *(_OWORD *)&SecurityContext[16].AccessState;
      *((_OWORD *)a3 + 92) = *(_OWORD *)&SecurityContext[17].SecurityQos;
      *((_OWORD *)a3 + 93) = *(_OWORD *)&SecurityContext[17].DesiredAccess;
      *((_OWORD *)a3 + 94) = *(_OWORD *)&SecurityContext[18].AccessState;
      *((_OWORD *)a3 + 95) = *(_OWORD *)&SecurityContext[12].SecurityQos;
      *((_OWORD *)a3 + 96) = *(_OWORD *)&SecurityContext[12].DesiredAccess;
      *((_OWORD *)a3 + 97) = *(_OWORD *)&SecurityContext[13].AccessState;
      *((_OWORD *)a3 + 98) = *(_OWORD *)&SecurityContext[14].SecurityQos;
      *((_OWORD *)a3 + 99) = *(_OWORD *)&SecurityContext[14].DesiredAccess;
      if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(Timer_high, v27, v29, v30) )
      {
        LOBYTE(v31) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( (_BYTE)v31 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v32) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          v33 = GetIfrRecorderLog(1, v31, v32);
          WPP_RECORDER_AND_TRACE_SF_bth_addrq(*(_QWORD *)(v34 + 24), v35, v36, v33);
        }
      }
      Avdtp_impl::SetAvdtpState_NoLock(a3, 5);
    }
    else
    {
      v10 = 1;
      v78 = 1;
    }
    v37 = v79;
  }
  else
  {
    v37 = KeAcquireSpinLockRaiseToDpc(v21);
    v22 = *((_QWORD *)a3 + 179) == 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)a3 + 200, v37);
  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v39, v38, v40, v41) )
  {
    if ( v20 )
      goto LABEL_82;
    if ( !v22 )
    {
      LOBYTE(v42) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v42 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v43) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v48 = GetIfrRecorderLog(1, v42, v43);
        WPP_RECORDER_AND_TRACE_SF_qi(
          *(_QWORD *)(v49 + 24),
          v50,
          v51,
          v48,
          4,
          4,
          206,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          *((_QWORD *)a3 + 179),
          (char)a3);
      }
      goto LABEL_82;
    }
    LOBYTE(v42) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v42 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v43) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v44 = GetIfrRecorderLog(1, v42, v43);
      WPP_RECORDER_AND_TRACE_SF_llq(
        *(_QWORD *)(v45 + 24),
        v46,
        v47,
        v44,
        4,
        4,
        205,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        a2->IoStatus.Status,
        HIDWORD(SecurityContext[1].SecurityQos),
        (char)a3);
    }
    goto LABEL_81;
  }
  if ( !v20 && v22 )
LABEL_81:
    Avdtp_impl::SetStateIfCurrentStateMatches(a3, v42, 4);
LABEL_82:
  Avdtp_impl::AbortAnyRxFragmentedPackets((Avdtp_impl *)a3);
  if ( v10 )
  {
    if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v53, v52, v54, v55) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v12 = 0;
      }
      if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v58) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v60 = GetIfrRecorderLog(2, v56, v58);
        LOBYTE(v62) = v12;
        WPP_RECORDER_AND_TRACE_SF_qi(
          *(_QWORD *)(v61 + 24),
          v62,
          v63,
          v60,
          4,
          4,
          207,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          *(_QWORD *)&SecurityContext[4].DesiredAccess,
          (char)a3);
      }
    }
    else if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v57, v56, v58, v59) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v12 = 0;
      }
      if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v65 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
        LOBYTE(v65) = v12;
        LOBYTE(v64) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v65,
          v64,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          208,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          (char)a3);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v12 = 0;
      }
      if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v66 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
        LOBYTE(v66) = v12;
        LOBYTE(v64) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v66,
          v64,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          209,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
      }
    }
    Avdtp_impl::L2capCloseAtShutdown((Avdtp_impl *)a3, *(void **)&SecurityContext[4].DesiredAccess);
    if ( v78 )
      *((_QWORD *)a3 + 141) = 0;
  }
  else if ( v22 )
  {
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v53, v52, v54, v55) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v12 = 0;
      }
      if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v68 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
        LOBYTE(v68) = v12;
        LOBYTE(v67) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v68,
          v67,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          210,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          v20,
          (char)a3);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v12 = 0;
      }
      if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v69 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
        LOBYTE(v69) = v12;
        LOBYTE(v67) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v69,
          v67,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          211,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          v20);
      }
    }
    v70 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a3 + 200);
    v71 = *((_QWORD *)a3 + 143);
    v72 = v70;
    if ( v71 )
      (*((void (__fastcall **)(_QWORD))a3 + 146))(*((_QWORD *)a3 + 143));
    KeReleaseSpinLock((PKSPIN_LOCK)a3 + 200, v72);
    if ( v71 )
    {
      (*((void (__fastcall **)(char *, __int64, _QWORD))a3 + 150))(a3, v71, v20);
      (*((void (__fastcall **)(__int64))a3 + 147))(v71);
    }
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400183c0  mov     [rsp+arg_0], rbx
0x1400183c5  push    rbp
0x1400183c6  push    rsi
0x1400183c7  push    rdi
0x1400183c8  push    r12
0x1400183ca  push    r13
0x1400183cc  push    r14
0x1400183ce  push    r15
0x1400183d0  sub     rsp, 60h
0x1400183d4  mov     rdi, r8
0x1400183d7  mov     r14, rdx
0x1400183da  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x1400183df  mov     ebp, 4
0x1400183e4  lea     r15, WPP_GLOBAL_Control
0x1400183eb  xor     r12d, r12d
0x1400183ee  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400183f5  lea     rsi, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x1400183fc  mov     r13b, 8
0x1400183ff  lea     ebx, [rbp-3]
0x140018402  test    eax, eax
0x140018404  jz      short loc_14001846F
0x140018406  mov     r10, cs:WPP_GLOBAL_Control
0x14001840d  cmp     r10, r15
0x140018410  jz      short loc_140018423
0x140018412  mov     eax, [r10+2Ch]
0x140018416  test    r13b, al
0x140018419  jz      short loc_140018423
0x14001841b  mov     dl, bl
0x14001841d  cmp     [r10+29h], bpl
0x140018421  jnb     short loc_140018426
0x140018423  mov     dl, r12b
0x140018426  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001842d  setnz   r8b
0x140018431  test    dl, dl
0x140018433  jnz     short loc_14001843A
0x140018435  test    r8b, r8b
0x140018438  jz      short loc_14001846F
0x14001843a  mov     ecx, 2
0x14001843f  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x140018444  mov     rcx, [r10+18h]
0x140018448  mov     r9, rax
0x14001844b  mov     [rsp+98h+var_50], r14
0x140018450  mov     [rsp+98h+var_58], rdi
0x140018455  mov     [rsp+98h+var_60], rsi
0x14001845a  mov     [rsp+98h+var_68], 0C7h
0x140018461  mov     [rsp+98h+var_70], ebp
0x140018465  mov     [rsp+98h+var_78], bpl
0x14001846a  call    WPP_RECORDER_AND_TRACE_SF_qi
0x14001846f  test    r14, r14
0x140018472  jnz     short loc_140018483
0x140018474  mov     edx, ebx
0x140018476  mov     rcx, rdi
0x140018479  call    ?SetAvdtpState@Avdtp_impl@@AEAA?AW4TAG_AvdtpState@@W42@@Z; Avdtp_impl::SetAvdtpState(TAG_AvdtpState)
0x14001847e  jmp     loc_140018C8C
0x140018483  mov     rax, [r14+0B8h]
0x14001848a  mov     rsi, [rax+8]
0x14001848e  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140018493  test    eax, eax
0x140018495  jz      short loc_140018508
0x140018497  mov     rcx, cs:WPP_GLOBAL_Control
0x14001849e  cmp     rcx, r15
0x1400184a1  jz      short loc_1400184B3
0x1400184a3  mov     eax, [rcx+2Ch]
0x1400184a6  test    r13b, al
0x1400184a9  jz      short loc_1400184B3
0x1400184ab  mov     dl, bl
0x1400184ad  cmp     [rcx+29h], bpl
0x1400184b1  jnb     short loc_1400184B6
0x1400184b3  mov     dl, r12b
0x1400184b6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400184bd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400184c4  setnz   r8b
0x1400184c8  test    dl, dl
0x1400184ca  jnz     short loc_1400184D5
0x1400184cc  test    r8b, r8b
0x1400184cf  jz      loc_140018570
0x1400184d5  mov     rax, [rsi+70h]
0x1400184d9  mov     r9, [rcx+40h]
0x1400184dd  mov     rcx, [rcx+18h]
0x1400184e1  mov     [rsp+98h+var_40], rdi
0x1400184e6  mov     [rsp+98h+var_48], rax
0x1400184eb  mov     eax, [rsi+1Ch]
0x1400184ee  mov     dword ptr [rsp+98h+var_50], eax
0x1400184f2  mov     eax, [r14+30h]
0x1400184f6  mov     dword ptr [rsp+98h+var_58], eax
0x1400184fa  mov     [rsp+98h+var_68], 0C8h
0x140018501  call    WPP_RECORDER_AND_TRACE_SF_ddqq
0x140018506  jmp     short loc_140018570
0x140018508  mov     r10, cs:WPP_GLOBAL_Control
0x14001850f  cmp     r10, r15
0x140018512  jz      short loc_140018525
0x140018514  mov     eax, [r10+2Ch]
0x140018518  test    r13b, al
0x14001851b  jz      short loc_140018525
0x14001851d  mov     dl, bl
0x14001851f  cmp     [r10+29h], bpl
0x140018523  jnb     short loc_140018528
0x140018525  mov     dl, r12b
0x140018528  lea     rax, WPP_RECORDER_INITIALIZED
0x14001852f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018536  setnz   r8b
0x14001853a  test    dl, dl
0x14001853c  jnz     short loc_140018543
0x14001853e  test    r8b, r8b
0x140018541  jz      short loc_140018570
0x140018543  mov     rax, [rsi+70h]
0x140018547  movzx   ecx, byte ptr [rsi+20h]
0x14001854b  mov     r9, [r10+40h]
0x14001854f  mov     [rsp+98h+var_40], rax
0x140018554  mov     eax, [rsi+1Ch]
0x140018557  mov     dword ptr [rsp+98h+var_48], ecx
0x14001855b  mov     rcx, [r10+18h]
0x14001855f  mov     dword ptr [rsp+98h+var_50], eax
0x140018563  mov     eax, [r14+30h]
0x140018567  mov     dword ptr [rsp+98h+var_58], eax
0x14001856b  call    WPP_RECORDER_AND_TRACE_SF_ddDq
0x140018570  test    rsi, rsi
0x140018573  jz      short loc_140018583
0x140018575  cmp     [r14+30h], r12d
0x140018579  jnz     short loc_140018583
0x14001857b  mov     ebp, ebx
0x14001857d  cmp     [rsi+1Ch], r12d
0x140018581  jz      short loc_140018586
0x140018583  mov     ebp, r12d
0x140018586  mov     [rsp+98h+arg_8], r12b
0x14001858e  lea     r15, [rdi+640h]
0x140018595  mov     rcx, r15; SpinLock
0x140018598  test    ebp, ebp
0x14001859a  jz      loc_140018806
0x1400185a0  mov     r13b, bl
0x1400185a3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400185aa  nop     dword ptr [rax+rax+00h]
0x1400185af  mov     [rsp+98h+arg_10], al
0x1400185b6  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400185bb  test    eax, eax
0x1400185bd  jz      short loc_14001863C
0x1400185bf  mov     r10, cs:WPP_GLOBAL_Control
0x1400185c6  lea     rax, WPP_GLOBAL_Control
0x1400185cd  cmp     r10, rax
0x1400185d0  jz      short loc_1400185E4
0x1400185d2  mov     ecx, [r10+2Ch]
0x1400185d6  test    cl, 8
0x1400185d9  jz      short loc_1400185E4
0x1400185db  cmp     byte ptr [r10+29h], 4
0x1400185e0  mov     dl, bl
0x1400185e2  jnb     short loc_1400185E7
0x1400185e4  mov     dl, r12b
0x1400185e7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400185ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400185f5  setnz   r8b
0x1400185f9  test    dl, dl
0x1400185fb  jnz     short loc_140018606
0x1400185fd  test    r8b, r8b
0x140018600  jz      loc_1400186AB
0x140018606  mov     eax, [rdi+90h]
0x14001860c  mov     r9, [r10+40h]
0x140018610  mov     rcx, [r10+18h]
0x140018614  mov     [rsp+98h+var_48], rdi
0x140018619  mov     dword ptr [rsp+98h+var_50], eax
0x14001861d  mov     rax, [rdi+478h]
0x140018624  mov     [rsp+98h+var_58], rax
0x140018629  mov     [rsp+98h+var_68], 0CAh
0x140018630  mov     [rsp+98h+var_78], 4
0x140018635  call    WPP_RECORDER_AND_TRACE_SF_qLq
0x14001863a  jmp     short loc_1400186AB
0x14001863c  mov     rcx, cs:WPP_GLOBAL_Control
0x140018643  lea     rax, WPP_GLOBAL_Control
0x14001864a  cmp     rcx, rax
0x14001864d  jz      short loc_14001865E
0x14001864f  mov     eax, [rcx+2Ch]
0x140018652  test    al, 8
0x140018654  jz      short loc_14001865E
0x140018656  cmp     byte ptr [rcx+29h], 4
0x14001865a  mov     dl, bl
0x14001865c  jnb     short loc_140018661
0x14001865e  mov     dl, r12b
0x140018661  lea     rax, WPP_RECORDER_INITIALIZED
0x140018668  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001866f  setnz   r8b
0x140018673  test    dl, dl
0x140018675  jnz     short loc_14001867C
0x140018677  test    r8b, r8b
0x14001867a  jz      short loc_1400186AB
0x14001867c  mov     eax, [rdi+90h]
0x140018682  mov     r9, [rcx+40h]
0x140018686  mov     rcx, [rcx+18h]
0x14001868a  mov     dword ptr [rsp+98h+var_50], eax
0x14001868e  mov     rax, [rdi+478h]
0x140018695  mov     [rsp+98h+var_58], rax
0x14001869a  mov     [rsp+98h+var_68], 0CBh
0x1400186a1  mov     [rsp+98h+var_78], 4
0x1400186a6  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1400186ab  cmp     dword ptr [rdi+90h], 3
0x1400186b2  mov     rax, [rdi+460h]
0x1400186b9  setz    r12b
0x1400186bd  mov     [rdi+468h], rax
0x1400186c4  cmp     qword ptr [rdi+478h], 0
0x1400186cc  jnz     short loc_1400186DD
0x1400186ce  mov     r12b, bl
0x1400186d1  mov     [rsp+98h+arg_8], bl
0x1400186d8  jmp     loc_1400187FD
0x1400186dd  mov     rax, [rsi+70h]
0x1400186e1  mov     [rdi+598h], rax
0x1400186e8  movups  xmm0, xmmword ptr [rsi+178h]
0x1400186ef  movups  xmmword ptr [rdi+5A0h], xmm0
0x1400186f6  movups  xmm1, xmmword ptr [rsi+188h]
0x1400186fd  movups  xmmword ptr [rdi+5B0h], xmm1
0x140018704  movups  xmm0, xmmword ptr [rsi+198h]
0x14001870b  movups  xmmword ptr [rdi+5C0h], xmm0
0x140018712  movups  xmm1, xmmword ptr [rsi+1A8h]
0x140018719  movups  xmmword ptr [rdi+5D0h], xmm1
0x140018720  movups  xmm0, xmmword ptr [rsi+1B8h]
0x140018727  movups  xmmword ptr [rdi+5E0h], xmm0
0x14001872e  movups  xmm0, xmmword ptr [rsi+120h]
0x140018735  movups  xmmword ptr [rdi+5F0h], xmm0
0x14001873c  movups  xmm1, xmmword ptr [rsi+130h]
0x140018743  movups  xmmword ptr [rdi+600h], xmm1
0x14001874a  movups  xmm0, xmmword ptr [rsi+140h]
0x140018751  movups  xmmword ptr [rdi+610h], xmm0
0x140018758  movups  xmm1, xmmword ptr [rsi+150h]
0x14001875f  movups  xmmword ptr [rdi+620h], xmm1
0x140018766  movups  xmm0, xmmword ptr [rsi+160h]
0x14001876d  movups  xmmword ptr [rdi+630h], xmm0
0x140018774  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140018779  test    eax, eax
0x14001877b  jz      short loc_1400187F0
0x14001877d  mov     r10, cs:WPP_GLOBAL_Control
0x140018784  lea     rax, WPP_GLOBAL_Control
0x14001878b  cmp     r10, rax
0x14001878e  jz      short loc_1400187A3
0x140018790  mov     eax, [r10+2Ch]
0x140018794  test    al, 8
0x140018796  jz      short loc_1400187A3
0x140018798  cmp     byte ptr [r10+29h], 4
0x14001879d  jb      short loc_1400187A3
0x14001879f  mov     dl, bl
0x1400187a1  jmp     short loc_1400187A5
0x1400187a3  xor     dl, dl
0x1400187a5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400187ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400187b3  setnz   r8b
0x1400187b7  test    dl, dl
0x1400187b9  jnz     short loc_1400187C0
0x1400187bb  test    r8b, r8b
0x1400187be  jz      short loc_1400187F0
0x1400187c0  mov     rcx, rbx
0x1400187c3  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x1400187c8  mov     rcx, [r10+18h]
0x1400187cc  mov     r9, rax
0x1400187cf  mov     rax, [rsi+70h]
0x1400187d3  mov     [rsp+98h+var_50], rax
0x1400187d8  mov     rax, [rdi+468h]
0x1400187df  mov     [rsp+98h+var_58], rax
0x1400187e4  mov     [rsp+98h+var_68], 0CCh
0x1400187eb  call    WPP_RECORDER_AND_TRACE_SF_bth_addrq
0x1400187f0  mov     edx, 5
0x1400187f5  mov     rcx, rdi
0x1400187f8  call    ?SetAvdtpState_NoLock@Avdtp_impl@@AEAA?AW4TAG_AvdtpState@@W42@@Z; Avdtp_impl::SetAvdtpState_NoLock(TAG_AvdtpState)
0x1400187fd  mov     dl, [rsp+98h+arg_10]
0x140018804  jmp     short loc_14001881F
0x140018806  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001880d  nop     dword ptr [rax+rax+00h]
0x140018812  cmp     [rdi+598h], r12
0x140018819  mov     dl, al; NewIrql
0x14001881b  setz    r13b
0x14001881f  mov     rcx, r15; SpinLock
0x140018822  call    cs:__imp_KeReleaseSpinLock
0x140018829  nop     dword ptr [rax+rax+00h]
0x14001882e  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140018833  test    eax, eax
0x140018835  jz      loc_14001896A
0x14001883b  test    ebp, ebp
0x14001883d  jnz     loc_140018981
0x140018843  test    r13b, r13b
0x140018846  jz      loc_1400188E0
0x14001884c  mov     r10, cs:WPP_GLOBAL_Control
0x140018853  lea     rax, WPP_GLOBAL_Control
0x14001885a  cmp     r10, rax
0x14001885d  jz      short loc_140018872
0x14001885f  mov     eax, [r10+2Ch]
0x140018863  test    al, 8
0x140018865  jz      short loc_140018872
0x140018867  cmp     byte ptr [r10+29h], 4
0x14001886c  jb      short loc_140018872
0x14001886e  mov     dl, bl
0x140018870  jmp     short loc_140018874
0x140018872  xor     dl, dl
0x140018874  lea     rax, WPP_RECORDER_INITIALIZED
0x14001887b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018882  setnz   r8b
0x140018886  test    dl, dl
0x140018888  jnz     short loc_140018893
0x14001888a  test    r8b, r8b
0x14001888d  jz      loc_140018973
0x140018893  mov     rcx, rbx
0x140018896  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14001889b  mov     rcx, [r10+18h]
0x14001889f  mov     r9, rax
0x1400188a2  mov     eax, [rsi+1Ch]
0x1400188a5  mov     [rsp+98h+var_48], rdi
  ... truncated ...
```
