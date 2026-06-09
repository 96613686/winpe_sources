# Avdtp_impl::L2CA_OPEN_CHANNEL_Completion_Initiator_Media(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140018cb0`
- end: `0x140019339`
- name: `?L2CA_OPEN_CHANNEL_Completion_Initiator_Media@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `1673`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400086e0`
- `0x14000e690`
- `0x14000fd00`
- `0x140018cb0`
- `0x140036494`
- `0x14003b244`
- `0x140046044`
- `0x140046390`
- `0x140048550`
- `0x1400502f0`
- `0x1400522bc`
- `0x140055404`
- `0x140055e20`
- `0x14005903c`
- `0x14005c7d0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140018cf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018cf8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018edd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001915c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019221`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400192ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018edd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001915c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019221`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400192ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018e31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018f81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400191f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400192c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018e31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018f81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400191f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400192c5`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::L2CA_OPEN_CHANNEL_Completion_Initiator_Media(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        unsigned int *a3)
{
  __int64 v3; // r15
  __int64 v5; // rdi
  int v6; // edx
  int v7; // r8d
  PIO_SECURITY_CONTEXT SecurityContext; // rsi
  char v9; // bl
  int FullCreateOptions_low; // r8d
  char v11; // r14
  KIRQL v12; // al
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r13
  int v18; // r12d
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rcx
  unsigned int v23; // r15d
  int v24; // edx
  __int64 v25; // rcx
  int v26; // r8d
  KIRQL v27; // al
  __int64 v28; // rbx
  KIRQL v29; // r14
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  int IfrRecorderLog; // eax
  __int64 v34; // r10
  int v35; // edx
  int v36; // r8d
  __int64 v37; // rdx
  int v38; // r15d
  int v39; // edx
  int v40; // r8d
  KIRQL v41; // al
  KIRQL v42; // r15
  __int64 v43; // r8
  KIRQL v44; // bl
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // r9
  unsigned __int64 v47; // r8
  int v49; // [rsp+20h] [rbp-C8h]
  int v50; // [rsp+28h] [rbp-C0h]
  int v51; // [rsp+30h] [rbp-B8h]
  __int64 *v52; // [rsp+38h] [rbp-B0h]
  NTSTATUS Status; // [rsp+40h] [rbp-A8h]
  int SecurityQos_high; // [rsp+48h] [rbp-A0h]
  __int64 v55; // [rsp+50h] [rbp-98h]
  __int64 v56; // [rsp+58h] [rbp-90h]
  int v57; // [rsp+60h] [rbp-88h]
  KIRQL NewIrql; // [rsp+70h] [rbp-78h]
  unsigned __int8 v59; // [rsp+71h] [rbp-77h]
  unsigned int v60; // [rsp+74h] [rbp-74h]
  __int64 v61; // [rsp+78h] [rbp-70h]
  _BYTE v62[32]; // [rsp+80h] [rbp-68h] BYREF

  v3 = a3[2];
  v5 = *(_QWORD *)a3;
  v60 = a3[2];
  v59 = *((_BYTE *)a3 + 13);
  ExFreePoolWithTag(a3, 0x41564430u);
  if ( !a2 )
    return 3221225494LL;
  SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  v9 = 1;
  LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v57 = v3;
    v56 = v5;
    v55 = *(_QWORD *)&SecurityContext[4].DesiredAccess;
    SecurityQos_high = HIDWORD(SecurityContext[1].SecurityQos);
    Status = a2->IoStatus.Status;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_ddqqd(WPP_GLOBAL_Control->AttachedDevice, v6, v7, WPP_GLOBAL_Control->DeviceExtension);
  }
  LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    FullCreateOptions_low = LOWORD(SecurityContext[15].FullCreateOptions);
    LOBYTE(FullCreateOptions_low) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      FullCreateOptions_low,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      255,
      (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
      SecurityContext[15].FullCreateOptions,
      WORD2(SecurityContext[12].SecurityQos));
  }
  v11 = SecurityContext && !a2->IoStatus.Status && !HIDWORD(SecurityContext[1].SecurityQos);
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 1600));
  v17 = *(_QWORD *)(v5 + 1144);
  v18 = *(_DWORD *)(v5 + 144);
  NewIrql = v12;
  v61 = v3;
  if ( v11 )
  {
    Feature_60817472__private_IsEnabledDeviceUsageNoInline(v14, v13, v15, v16);
    v22 = 200 * v3;
    v23 = *(_DWORD *)(200 * v3 + v5 + 232);
    if ( v23 != 2 )
    {
      LOBYTE(v19) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      if ( (_BYTE)v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_DL(
          WPP_GLOBAL_Control->AttachedDevice,
          v19,
          v20,
          WPP_GLOBAL_Control->DeviceExtension,
          v49,
          v50,
          v51,
          (_DWORD)v52,
          v60,
          v23);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 1600), NewIrql);
      if ( v23 != 7 )
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(v25, v23, 2, "The state of SEP is unexpected");
      if ( v17 && v18 != 1 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v9 = 0;
        }
        if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          Status = 49;
          v52 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
          LOBYTE(v24) = v9;
          LOWORD(v51) = 257;
          v50 = 4;
          LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_D(WPP_GLOBAL_Control->AttachedDevice, v24, v26, WPP_GLOBAL_Control->DeviceExtension);
        }
        v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 1600));
        v28 = *(_QWORD *)(v5 + 1144);
        v29 = v27;
        if ( v28 )
          (*(void (__fastcall **)(_QWORD))(v5 + 1168))(*(_QWORD *)(v5 + 1144));
        KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 1600), v29);
        if ( v28 )
        {
          LOBYTE(v30) = 49;
          (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD, int, int, __int64 *, NTSTATUS, int, __int64, __int64, int))(v5 + 1320))(
            v5,
            v28,
            v30,
            LOWORD(SecurityContext[15].FullCreateOptions),
            WORD2(SecurityContext[12].SecurityQos),
            v50,
            v51,
            v52,
            Status,
            SecurityQos_high,
            v55,
            v56,
            v57);
LABEL_74:
          (*(void (__fastcall **)(__int64))(v5 + 1176))(v28);
          return 3221225494LL;
        }
        return 3221225494LL;
      }
LABEL_77:
      Avdtp_impl::Abort_Req((void *)v5, v59);
      return 3221225494LL;
    }
    if ( v17 )
    {
      _InterlockedExchange64((volatile __int64 *)(v22 + v5 + 240), *(_QWORD *)&SecurityContext[4].DesiredAccess);
      *(_OWORD *)(v22 + v5 + 248) = *(_OWORD *)&SecurityContext[15].DesiredAccess;
      *(_OWORD *)(v22 + v5 + 264) = *(_OWORD *)&SecurityContext[16].AccessState;
      *(_OWORD *)(v22 + v5 + 280) = *(_OWORD *)&SecurityContext[17].SecurityQos;
      *(_OWORD *)(v22 + v5 + 296) = *(_OWORD *)&SecurityContext[17].DesiredAccess;
      *(_OWORD *)(v22 + v5 + 312) = *(_OWORD *)&SecurityContext[18].AccessState;
      *(_OWORD *)(v22 + v5 + 328) = *(_OWORD *)&SecurityContext[12].SecurityQos;
      *(_OWORD *)(v22 + v5 + 344) = *(_OWORD *)&SecurityContext[12].DesiredAccess;
      *(_OWORD *)(v22 + v5 + 360) = *(_OWORD *)&SecurityContext[13].AccessState;
      *(_OWORD *)(v22 + v5 + 376) = *(_OWORD *)&SecurityContext[14].SecurityQos;
      *(_OWORD *)(v22 + v5 + 392) = *(_OWORD *)&SecurityContext[14].DesiredAccess;
      if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v22, v19, v20, v21) )
      {
        LOBYTE(v31) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( (_BYTE)v31 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v32) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          IfrRecorderLog = GetIfrRecorderLog(2, v31, v32);
          WPP_RECORDER_AND_TRACE_SF_bth_addrqD(
            *(_QWORD *)(v34 + 24),
            v35,
            v36,
            IfrRecorderLog,
            v49,
            v50,
            258,
            (_DWORD)v52,
            *(_QWORD *)(v5 + 1128),
            *(_QWORD *)&SecurityContext[4].DesiredAccess,
            v60);
        }
      }
    }
    v3 = v61;
    v37 = 4;
  }
  else
  {
    v37 = v18 != 1;
  }
  Avdtp_impl::tagSepInfo::SetState(v5 + 200 * v3 + 216, v37);
  v38 = *(_DWORD *)(v5 + 144);
  KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 1600), NewIrql);
  if ( !v17 || v18 == 1 )
  {
    if ( !v11 || v38 == 7 )
    {
      v44 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 1600));
      Avdtp_impl::CopySepsToLocalInfo(
        (const struct Avdtp_impl::tagSepInfo *)(v5 + 216),
        v45,
        (struct SepInfoCopy *)v62,
        v46);
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 1600), v44);
      Avdtp_impl::AbortOpenMediaChannelsOrDisconnect((Avdtp_impl *)v5, (const struct SepInfoCopy *)v62, v47);
      return 3221225494LL;
    }
    goto LABEL_77;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v9 = 0;
  }
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v39) = v9;
    LOBYTE(v40) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v39,
      v40,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      259,
      (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
      v11);
  }
  v41 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 1600));
  v28 = *(_QWORD *)(v5 + 1144);
  v42 = v41;
  if ( v28 )
    (*(void (__fastcall **)(_QWORD))(v5 + 1168))(*(_QWORD *)(v5 + 1144));
  KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 1600), v42);
  if ( v28 )
  {
    LOBYTE(v43) = v11 == 0 ? 0x29 : 0;
    (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD))(v5 + 1320))(
      v5,
      v28,
      v43,
      LOWORD(SecurityContext[15].FullCreateOptions),
      WORD2(SecurityContext[12].SecurityQos));
    if ( v11 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD))(v5 + 1336))(
        v5,
        v28,
        *(_QWORD *)&SecurityContext[4].DesiredAccess,
        LOWORD(SecurityContext[15].FullCreateOptions),
        WORD2(SecurityContext[12].SecurityQos));
    goto LABEL_74;
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140018cb0  mov     [rsp+arg_0], rbx
0x140018cb5  push    rbp
0x140018cb6  push    rsi
0x140018cb7  push    rdi
0x140018cb8  push    r12
0x140018cba  push    r13
0x140018cbc  push    r14
0x140018cbe  push    r15
0x140018cc0  sub     rsp, 0B0h
0x140018cc7  mov     rax, cs:__security_cookie
0x140018cce  xor     rax, rsp
0x140018cd1  mov     [rsp+0E8h+var_48], rax
0x140018cd9  mov     r15d, [r8+8]
0x140018cdd  mov     rbp, rdx
0x140018ce0  mov     al, [r8+0Dh]
0x140018ce4  mov     edx, 41564430h; Tag
0x140018ce9  mov     rdi, [r8]
0x140018cec  mov     rcx, r8; P
0x140018cef  mov     [rsp+0E8h+var_74], r15d
0x140018cf4  mov     [rsp+0E8h+var_77], al
0x140018cf8  call    cs:__imp_ExFreePoolWithTag
0x140018cff  nop     dword ptr [rax+rax+00h]
0x140018d04  test    rbp, rbp
0x140018d07  jz      loc_140019308
0x140018d0d  mov     rax, [rbp+0B8h]
0x140018d14  mov     rsi, [rax+8]
0x140018d18  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d1f  lea     r14, WPP_GLOBAL_Control
0x140018d26  mov     ebx, 1
0x140018d2b  cmp     rcx, r14
0x140018d2e  jz      short loc_140018D41
0x140018d30  mov     eax, [rcx+2Ch]
0x140018d33  test    al, 8
0x140018d35  jz      short loc_140018D41
0x140018d37  cmp     byte ptr [rcx+29h], 4
0x140018d3b  jb      short loc_140018D41
0x140018d3d  mov     dl, bl
0x140018d3f  jmp     short loc_140018D43
0x140018d41  xor     dl, dl
0x140018d43  lea     r9, WPP_RECORDER_INITIALIZED
0x140018d4a  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140018d51  setnz   r8b
0x140018d55  test    dl, dl
0x140018d57  jnz     short loc_140018D5E
0x140018d59  test    r8b, r8b
0x140018d5c  jz      short loc_140018D93
0x140018d5e  mov     rax, [rsi+70h]
0x140018d62  mov     r9, [rcx+40h]
0x140018d66  mov     rcx, [rcx+18h]
0x140018d6a  mov     [rsp+0E8h+var_88], r15d
0x140018d6f  mov     [rsp+0E8h+var_90], rdi
0x140018d74  mov     [rsp+0E8h+var_98], rax
0x140018d79  mov     eax, [rsi+1Ch]
0x140018d7c  mov     dword ptr [rsp+0E8h+var_A0], eax
0x140018d80  mov     eax, [rbp+30h]
0x140018d83  mov     dword ptr [rsp+0E8h+var_A8], eax
0x140018d87  call    WPP_RECORDER_AND_TRACE_SF_ddqqd
0x140018d8c  lea     r9, WPP_RECORDER_INITIALIZED
0x140018d93  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d9a  cmp     rcx, r14
0x140018d9d  jz      short loc_140018DB0
0x140018d9f  mov     eax, [rcx+2Ch]
0x140018da2  test    al, 8
0x140018da4  jz      short loc_140018DB0
0x140018da6  cmp     byte ptr [rcx+29h], 4
0x140018daa  jb      short loc_140018DB0
0x140018dac  mov     dl, bl
0x140018dae  jmp     short loc_140018DB2
0x140018db0  xor     dl, dl
0x140018db2  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140018db9  lea     r11, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140018dc0  setnz   r10b
0x140018dc4  test    dl, dl
0x140018dc6  jnz     short loc_140018DCD
0x140018dc8  test    r10b, r10b
0x140018dcb  jz      short loc_140018E0E
0x140018dcd  movzx   r8d, word ptr [rsi+17Ch]
0x140018dd5  movzx   eax, word ptr [rsi+124h]
0x140018ddc  mov     r9, [rcx+40h]
0x140018de0  mov     rcx, [rcx+18h]
0x140018de4  mov     dword ptr [rsp+0E8h+var_A0], eax
0x140018de8  mov     dword ptr [rsp+0E8h+var_A8], r8d
0x140018ded  mov     r8b, r10b
0x140018df0  mov     [rsp+0E8h+var_B0], r11
0x140018df5  mov     [rsp+0E8h+var_B8], 0FFh
0x140018dfc  mov     [rsp+0E8h+var_C0], 4
0x140018e04  mov     byte ptr [rsp+0E8h+var_C8], 4
0x140018e09  call    WPP_RECORDER_AND_TRACE_SF_dd
0x140018e0e  test    rsi, rsi
0x140018e11  jz      short loc_140018E24
0x140018e13  cmp     dword ptr [rbp+30h], 0
0x140018e17  jnz     short loc_140018E24
0x140018e19  cmp     dword ptr [rsi+1Ch], 0
0x140018e1d  jnz     short loc_140018E24
0x140018e1f  mov     r14b, bl
0x140018e22  jmp     short loc_140018E27
0x140018e24  xor     r14b, r14b
0x140018e27  lea     rbp, [rdi+640h]
0x140018e2e  mov     rcx, rbp; SpinLock
0x140018e31  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018e38  nop     dword ptr [rax+rax+00h]
0x140018e3d  mov     r13, [rdi+478h]
0x140018e44  mov     r12d, [rdi+90h]
0x140018e4b  mov     [rsp+0E8h+NewIrql], al
0x140018e4f  mov     [rsp+0E8h+var_70], r15
0x140018e54  test    r14b, r14b
0x140018e57  jz      loc_140019130
0x140018e5d  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140018e62  imul    rcx, r15, 0C8h
0x140018e69  mov     r15d, [rcx+rdi+0E8h]
0x140018e71  cmp     r15d, 2
0x140018e75  jz      loc_140018FF3
0x140018e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e82  lea     r14, WPP_GLOBAL_Control
0x140018e89  cmp     rcx, r14
0x140018e8c  jz      short loc_140018E9F
0x140018e8e  mov     eax, [rcx+2Ch]
0x140018e91  test    al, 8
0x140018e93  jz      short loc_140018E9F
0x140018e95  cmp     byte ptr [rcx+29h], 3
0x140018e99  jb      short loc_140018E9F
0x140018e9b  mov     dl, bl
0x140018e9d  jmp     short loc_140018EA1
0x140018e9f  xor     dl, dl
0x140018ea1  lea     rax, WPP_RECORDER_INITIALIZED
0x140018ea8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018eaf  setnz   r8b
0x140018eb3  test    dl, dl
0x140018eb5  jnz     short loc_140018EBC
0x140018eb7  test    r8b, r8b
0x140018eba  jz      short loc_140018ED6
0x140018ebc  mov     r9, [rcx+40h]
0x140018ec0  mov     eax, [rsp+0E8h+var_74]
0x140018ec4  mov     rcx, [rcx+18h]
0x140018ec8  mov     dword ptr [rsp+0E8h+var_A0], r15d
0x140018ecd  mov     dword ptr [rsp+0E8h+var_A8], eax
0x140018ed1  call    WPP_RECORDER_AND_TRACE_SF_DL
0x140018ed6  mov     dl, [rsp+0E8h+NewIrql]; NewIrql
0x140018eda  mov     rcx, rbp; SpinLock
0x140018edd  call    cs:__imp_KeReleaseSpinLock
0x140018ee4  nop     dword ptr [rax+rax+00h]
0x140018ee9  cmp     r15d, 7
0x140018eed  jz      short loc_140018F04
0x140018eef  lea     r9, aTheStateOfSepI; "The state of SEP is unexpected"
0x140018ef6  mov     r8d, 2
0x140018efc  mov     edx, r15d
0x140018eff  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140018f04  test    r13, r13
0x140018f07  jz      loc_1400192B4
0x140018f0d  cmp     r12d, ebx
0x140018f10  jz      loc_1400192B4
0x140018f16  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f1d  cmp     rcx, r14
0x140018f20  jz      short loc_140018F2F
0x140018f22  mov     eax, [rcx+2Ch]
0x140018f25  test    al, 8
0x140018f27  jz      short loc_140018F2F
0x140018f29  cmp     byte ptr [rcx+29h], 4
0x140018f2d  jnb     short loc_140018F31
0x140018f2f  xor     bl, bl
0x140018f31  lea     rax, WPP_RECORDER_INITIALIZED
0x140018f38  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018f3f  setnz   r8b
0x140018f43  test    bl, bl
0x140018f45  jnz     short loc_140018F4C
0x140018f47  test    r8b, r8b
0x140018f4a  jz      short loc_140018F7E
0x140018f4c  mov     dword ptr [rsp+0E8h+var_A8], 31h ; '1'
0x140018f54  lea     r9, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140018f5b  mov     [rsp+0E8h+var_B0], r9
0x140018f60  mov     dl, bl
0x140018f62  mov     r9, [rcx+40h]
0x140018f66  mov     rcx, [rcx+18h]
0x140018f6a  mov     [rsp+0E8h+var_B8], 101h
0x140018f71  mov     [rsp+0E8h+var_C0], 4
0x140018f79  call    WPP_RECORDER_AND_TRACE_SF_D
0x140018f7e  mov     rcx, rbp; SpinLock
0x140018f81  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018f88  nop     dword ptr [rax+rax+00h]
0x140018f8d  mov     rbx, [rdi+478h]
0x140018f94  mov     r14b, al
0x140018f97  test    rbx, rbx
0x140018f9a  jz      short loc_140018FAB
0x140018f9c  mov     rax, [rdi+490h]
0x140018fa3  mov     rcx, rbx
0x140018fa6  call    _guard_dispatch_icall
0x140018fab  mov     dl, r14b; NewIrql
0x140018fae  mov     rcx, rbp; SpinLock
0x140018fb1  call    cs:__imp_KeReleaseSpinLock
0x140018fb8  nop     dword ptr [rax+rax+00h]
0x140018fbd  test    rbx, rbx
0x140018fc0  jz      loc_140019308
0x140018fc6  movzx   edx, word ptr [rsi+124h]
0x140018fcd  mov     r8b, 31h ; '1'
0x140018fd0  movzx   r9d, word ptr [rsi+17Ch]
0x140018fd8  mov     rcx, rdi
0x140018fdb  mov     rax, [rdi+528h]
0x140018fe2  mov     [rsp+0E8h+var_C8], edx
0x140018fe6  mov     rdx, rbx
0x140018fe9  call    _guard_dispatch_icall
0x140018fee  jmp     loc_140019298
0x140018ff3  test    r13, r13
0x140018ff6  jz      loc_140019124
0x140018ffc  mov     rax, [rsi+70h]
0x140019000  xchg    rax, [rcx+rdi+0F0h]
0x140019008  movups  xmm0, xmmword ptr [rsi+178h]
0x14001900f  movups  xmmword ptr [rcx+rdi+0F8h], xmm0
0x140019017  movups  xmm1, xmmword ptr [rsi+188h]
0x14001901e  movups  xmmword ptr [rcx+rdi+108h], xmm1
0x140019026  movups  xmm0, xmmword ptr [rsi+198h]
0x14001902d  movups  xmmword ptr [rcx+rdi+118h], xmm0
0x140019035  movups  xmm1, xmmword ptr [rsi+1A8h]
0x14001903c  movups  xmmword ptr [rcx+rdi+128h], xmm1
0x140019044  movups  xmm0, xmmword ptr [rsi+1B8h]
0x14001904b  movups  xmmword ptr [rcx+rdi+138h], xmm0
0x140019053  movups  xmm0, xmmword ptr [rsi+120h]
0x14001905a  movups  xmmword ptr [rcx+rdi+148h], xmm0
0x140019062  movups  xmm1, xmmword ptr [rsi+130h]
0x140019069  movups  xmmword ptr [rcx+rdi+158h], xmm1
0x140019071  movups  xmm0, xmmword ptr [rsi+140h]
0x140019078  movups  xmmword ptr [rcx+rdi+168h], xmm0
0x140019080  movups  xmm1, xmmword ptr [rsi+150h]
0x140019087  movups  xmmword ptr [rcx+rdi+178h], xmm1
0x14001908f  movups  xmm0, xmmword ptr [rsi+160h]
0x140019096  movups  xmmword ptr [rcx+rdi+188h], xmm0
0x14001909e  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x1400190a3  test    eax, eax
0x1400190a5  jz      short loc_140019124
0x1400190a7  mov     r10, cs:WPP_GLOBAL_Control
0x1400190ae  lea     rax, WPP_GLOBAL_Control
0x1400190b5  cmp     r10, rax
0x1400190b8  jz      short loc_1400190CD
0x1400190ba  mov     eax, [r10+2Ch]
0x1400190be  test    al, 8
0x1400190c0  jz      short loc_1400190CD
0x1400190c2  cmp     byte ptr [r10+29h], 4
0x1400190c7  jb      short loc_1400190CD
0x1400190c9  mov     dl, bl
0x1400190cb  jmp     short loc_1400190CF
0x1400190cd  xor     dl, dl
0x1400190cf  lea     rax, WPP_RECORDER_INITIALIZED
0x1400190d6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400190dd  setnz   r8b
0x1400190e1  test    dl, dl
0x1400190e3  jnz     short loc_1400190EA
0x1400190e5  test    r8b, r8b
0x1400190e8  jz      short loc_140019124
0x1400190ea  mov     ecx, 2
0x1400190ef  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x1400190f4  mov     rcx, [r10+18h]
0x1400190f8  mov     r9, rax
0x1400190fb  mov     eax, [rsp+0E8h+var_74]
0x1400190ff  mov     dword ptr [rsp+0E8h+var_98], eax
0x140019103  mov     rax, [rsi+70h]
0x140019107  mov     [rsp+0E8h+var_A0], rax
0x14001910c  mov     rax, [rdi+468h]
0x140019113  mov     [rsp+0E8h+var_A8], rax
0x140019118  mov     [rsp+0E8h+var_B8], 102h
0x14001911f  call    WPP_RECORDER_AND_TRACE_SF_bth_addrqD
0x140019124  mov     r15, [rsp+0E8h+var_70]
0x140019129  mov     edx, 4
0x14001912e  jmp     short loc_140019138
0x140019130  xor     edx, edx
0x140019132  cmp     r12d, ebx
0x140019135  setnz   dl
0x140019138  imul    rcx, r15, 0C8h
0x14001913f  add     rcx, 0D8h
0x140019146  add     rcx, rdi
0x140019149  call    ?SetState@tagSepInfo@Avdtp_impl@@QEAAXW4TAG_AvdtpSepState@@@Z; Avdtp_impl::tagSepInfo::SetState(TAG_AvdtpSepState)
0x14001914e  mov     dl, [rsp+0E8h+NewIrql]; NewIrql
0x140019152  mov     rcx, rbp; SpinLock
0x140019155  mov     r15d, [rdi+90h]
0x14001915c  call    cs:__imp_KeReleaseSpinLock
0x140019163  nop     dword ptr [rax+rax+00h]
0x140019168  test    r13, r13
0x14001916b  jz      loc_1400192A9
0x140019171  cmp     r12d, ebx
0x140019174  jz      loc_1400192A9
0x14001917a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019181  lea     rax, WPP_GLOBAL_Control
0x140019188  cmp     rcx, rax
0x14001918b  jz      short loc_14001919A
0x14001918d  mov     eax, [rcx+2Ch]
0x140019190  test    al, 8
0x140019192  jz      short loc_14001919A
0x140019194  cmp     byte ptr [rcx+29h], 4
0x140019198  jnb     short loc_14001919C
0x14001919a  xor     bl, bl
0x14001919c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400191a3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400191aa  setnz   r8b
0x1400191ae  test    bl, bl
0x1400191b0  jnz     short loc_1400191B7
0x1400191b2  test    r8b, r8b
0x1400191b5  jz      short loc_1400191EE
0x1400191b7  movzx   eax, r14b
0x1400191bb  lea     r9, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x1400191c2  mov     dword ptr [rsp+0E8h+var_A8], eax
0x1400191c6  mov     dl, bl
0x1400191c8  mov     [rsp+0E8h+var_B0], r9
  ... truncated ...
```
