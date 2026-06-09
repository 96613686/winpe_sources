# Avdtp_impl::DetachUpperLayerAndShutDown(void)

- ea: `0x14004891c`
- end: `0x140048fd1`
- name: `?DetachUpperLayerAndShutDown@Avdtp_impl@@AEAAJXZ`
- size: `1717`
- prototype: `__int64 __fastcall(Avdtp_impl *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140052220`

## callees

- `0x140003530`
- `0x14000e690`
- `0x14000f300`
- `0x14000f570`
- `0x14000f600`
- `0x140012a5c`
- `0x14001c948`
- `0x14002d890`
- `0x140036494`
- `0x14003b244`
- `0x140046b04`
- `0x140048550`
- `0x14004891c`
- `0x140050a78`
- `0x140055344`
- `0x14005c7d0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140048cc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048fa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048cc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048fa1`
- `ntoskrnl!IoCancelIrp` at `0x140048c95`
- `ntoskrnl!IoCancelIrp` at `0x140048c95`
- `ntoskrnl!IoFreeIrp` at `0x140048cb1`
- `ntoskrnl!IoFreeIrp` at `0x140048cb1`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x140048f1d`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x140048f1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048ac6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048c81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048cf8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048ac6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048c81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048cf8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048a7b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048afa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048cdb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048a7b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048afa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048cdb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048db9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048db9`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::DetachUpperLayerAndShutDown(Avdtp_impl *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  char v9; // di
  int IfrRecorderLog; // eax
  __int64 v11; // r10
  int v12; // edx
  int v13; // r8d
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // esi
  __int64 v19; // rsi
  KIRQL v20; // r14
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // rdx
  KSPIN_LOCK *v23; // rbp
  KIRQL v24; // al
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  volatile signed __int32 **v29; // r15
  volatile signed __int32 *v30; // rsi
  __int64 v31; // rax
  IRP *v32; // r12
  int v33; // edx
  int v34; // r8d
  signed __int32 v35; // eax
  signed __int32 v36; // ecx
  int v37; // edx
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
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  PDEVICE_OBJECT v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // r8
  int v58; // eax
  __int64 v59; // r10
  int v60; // edx
  int v61; // r8d
  __int64 v62; // rdx
  __int64 v63; // r8
  int v64; // eax
  __int64 v65; // r10
  int v66; // edx
  int v67; // r8d
  KIRQL NewIrql; // [rsp+50h] [rbp-78h]
  _OWORD v69[2]; // [rsp+58h] [rbp-70h] BYREF

  v9 = 1;
  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      IfrRecorderLog = GetIfrRecorderLog(0, v5, v7);
      WPP_RECORDER_AND_TRACE_SF_bth_addrq(*(_QWORD *)(v11 + 24), v12, v13, IfrRecorderLog);
    }
  }
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v6, v5, v7, v8) )
  {
    v15 = Avdtp_impl::AcquireRemoveLock((__int64)this, 8);
    v18 = v15;
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v9 = 0;
      }
      if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = v9;
        LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v16,
          v17,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          18,
          82,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          v15);
      }
      return v18;
    }
  }
  else if ( (int)Avdtp_impl::AcquireRemoveLock(this) < 0 )
  {
    return 3221225473LL;
  }
  v19 = 0;
  memset(v69, 0, sizeof(v69));
  v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 200);
  Avdtp_impl::SetAvdtpState_NoLock(this, 7);
  v22 = *((_QWORD *)this + 143);
  if ( v22 )
  {
    v19 = *((_QWORD *)this + 143);
    *((_QWORD *)this + 143) = 0;
  }
  Avdtp_impl::CopySepsToLocalInfo((Avdtp_impl *)((char *)this + 216), v22, (struct SepInfoCopy *)v69, v21);
  KeReleaseSpinLock((PKSPIN_LOCK)this + 200, v20);
  if ( v19 )
    (*((void (__fastcall **)(__int64))this + 147))(v19);
  Avdtp_impl::Stop(this, 1);
  v23 = (KSPIN_LOCK *)((char *)this + 1776);
  v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 222);
  *((_DWORD *)this + 446) = 1;
  v29 = (volatile signed __int32 **)((char *)this + 1760);
  while ( 1 )
  {
    v30 = *v29;
    NewIrql = v24;
    if ( *v29 == (volatile signed __int32 *)v29 )
      break;
    if ( *((volatile signed __int32 ***)v30 + 1) != v29
      || (v31 = *(_QWORD *)v30, *(volatile signed __int32 **)(*(_QWORD *)v30 + 8LL) != v30) )
    {
      __fastfail(3u);
    }
    *v29 = (volatile signed __int32 *)v31;
    v32 = 0;
    *(_QWORD *)(v31 + 8) = v29;
    if ( *((_BYTE *)v30 + 28) )
    {
      if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v26, v25, v27, v28) )
      {
        LOBYTE(v33) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( (_BYTE)v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v34) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qi(
            WPP_GLOBAL_Control->AttachedDevice,
            v33,
            v34,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            4,
            83,
            (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
            *((_QWORD *)v30 + 2),
            (char)this);
        }
      }
      else
      {
        LOBYTE(v33) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( (_BYTE)v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v34) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            v33,
            v34,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            4,
            84,
            (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
            *((_QWORD *)v30 + 2));
        }
      }
    }
    else
    {
      v35 = *((_DWORD *)v30 + 6);
      while ( v35 > 0 )
      {
        v36 = v35;
        v37 = v35 + 1;
        v35 = _InterlockedCompareExchange(v30 + 6, v35 + 1, v35);
        if ( v36 == v35 )
        {
          if ( v37 > 0 )
            v32 = (IRP *)*((_QWORD *)v30 + 2);
          break;
        }
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)this + 222, NewIrql);
    if ( v32 )
    {
      IoCancelIrp(v32);
      if ( _InterlockedExchangeAdd(v30 + 6, 0xFFFFFFFF) == 1 )
      {
        IoFreeIrp(v32);
        ExFreePoolWithTag((PVOID)v30, 0x41564454u);
      }
    }
    v23 = (KSPIN_LOCK *)((char *)this + 1776);
    v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 222);
  }
  KeReleaseSpinLock(v23, v24);
  Avdtp_impl::InterfaceDereference(this, Avdtp_impl::impl_Create);
  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v39, v38, v40, v41) )
  {
    LOBYTE(v42) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v42 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v43) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v44 = GetIfrRecorderLog(0, v42, v43);
      WPP_RECORDER_AND_TRACE_SF_q(
        *(_QWORD *)(v45 + 24),
        v46,
        v47,
        v44,
        4,
        4,
        85,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        (char)this);
    }
  }
  KeWaitForSingleObject((char *)this + 176, Executive, 0, 0, 0);
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v49, v48, v50, v51) )
  {
    v55 = WPP_GLOBAL_Control;
    LOBYTE(v52) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v53) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v52 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v52,
        v53,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        86,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        (char)this);
  }
  else
  {
    v55 = WPP_GLOBAL_Control;
    LOBYTE(v52) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v53) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v52 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v52,
        v53,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        87,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
  }
  if ( *((_QWORD *)this + 224) )
  {
    if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v55, v52, v53, v54) )
    {
      LOBYTE(v56) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v56 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v57) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v58 = GetIfrRecorderLog(0, v56, v57);
        WPP_RECORDER_AND_TRACE_SF_q(
          *(_QWORD *)(v59 + 24),
          v60,
          v61,
          v58,
          4,
          4,
          88,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          (char)this);
      }
    }
    IoReleaseRemoveLockAndWaitEx(*((PIO_REMOVE_LOCK *)this + 224), (PVOID)0x41564454, 0x20u);
  }
  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v55, v52, v53, v54) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v9 = 0;
    }
    if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v63) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v64 = GetIfrRecorderLog(0, v62, v63);
      LOBYTE(v66) = v9;
      WPP_RECORDER_AND_TRACE_SF_q(
        *(_QWORD *)(v65 + 24),
        v66,
        v67,
        v64,
        4,
        4,
        89,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        (char)this);
    }
  }
  ExFreePoolWithTag(this, 0x41564454u);
  return 0;
}

```

## disassembly

```asm
0x14004891c  push    rbx
0x14004891e  push    rbp
0x14004891f  push    rsi
0x140048920  push    rdi
0x140048921  push    r12
0x140048923  push    r13
0x140048925  push    r14
0x140048927  push    r15
0x140048929  sub     rsp, 88h
0x140048930  mov     rax, cs:__security_cookie
0x140048937  xor     rax, rsp
0x14004893a  mov     [rsp+0C8h+var_50], rax
0x14004893f  mov     rbx, rcx
0x140048942  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140048947  lea     r12, WPP_GLOBAL_Control
0x14004894e  mov     edi, 1
0x140048953  lea     rbp, WPP_RECORDER_INITIALIZED
0x14004895a  test    eax, eax
0x14004895c  jz      short loc_1400489BF
0x14004895e  mov     r10, cs:WPP_GLOBAL_Control
0x140048965  cmp     r10, r12
0x140048968  jz      short loc_14004897E
0x14004896a  mov     eax, [r10+2Ch]
0x14004896e  test    al, 8
0x140048970  jz      short loc_14004897E
0x140048972  cmp     byte ptr [r10+29h], 4
0x140048977  jb      short loc_14004897E
0x140048979  mov     dl, dil
0x14004897c  jmp     short loc_140048980
0x14004897e  xor     dl, dl
0x140048980  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140048987  setnz   r8b
0x14004898b  test    dl, dl
0x14004898d  jnz     short loc_140048994
0x14004898f  test    r8b, r8b
0x140048992  jz      short loc_1400489BF
0x140048994  xor     ecx, ecx
0x140048996  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14004899b  mov     rcx, [r10+18h]
0x14004899f  mov     r9, rax
0x1400489a2  mov     rax, [rbx+460h]
0x1400489a9  mov     [rsp+0C8h+var_80], rbx
0x1400489ae  mov     [rsp+0C8h+var_88], rax
0x1400489b3  mov     [rsp+0C8h+var_98], 51h ; 'Q'
0x1400489ba  call    WPP_RECORDER_AND_TRACE_SF_bth_addrq
0x1400489bf  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400489c4  mov     rcx, rbx; this
0x1400489c7  test    eax, eax
0x1400489c9  jnz     short loc_1400489E2
0x1400489cb  call    ?AcquireRemoveLock@Avdtp_impl@@QEAAJXZ; Avdtp_impl::AcquireRemoveLock(void)
0x1400489d0  test    eax, eax
0x1400489d2  jns     loc_140048A62
0x1400489d8  mov     eax, 0C0000001h
0x1400489dd  jmp     loc_140048FAF
0x1400489e2  mov     edx, 8
0x1400489e7  call    ?AcquireRemoveLock@Avdtp_impl@@QEAAJW4RemoveLockClient@1@@Z; Avdtp_impl::AcquireRemoveLock(Avdtp_impl::RemoveLockClient)
0x1400489ec  mov     esi, eax
0x1400489ee  test    eax, eax
0x1400489f0  jns     short loc_140048A62
0x1400489f2  mov     r10, cs:WPP_GLOBAL_Control
0x1400489f9  cmp     r10, r12
0x1400489fc  jz      short loc_140048A0F
0x1400489fe  test    dword ptr [r10+2Ch], 20000h
0x140048a06  jz      short loc_140048A0F
0x140048a08  cmp     byte ptr [r10+29h], 2
0x140048a0d  jnb     short loc_140048A12
0x140048a0f  xor     dil, dil
0x140048a12  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140048a19  setnz   r8b
0x140048a1d  test    dil, dil
0x140048a20  jnz     short loc_140048A27
0x140048a22  test    r8b, r8b
0x140048a25  jz      short loc_140048A5B
0x140048a27  mov     r9, [r10+40h]
0x140048a2b  lea     r13, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140048a32  mov     rcx, [r10+18h]
0x140048a36  mov     dl, dil
0x140048a39  mov     dword ptr [rsp+0C8h+var_88], esi
0x140048a3d  mov     [rsp+0C8h+var_90], r13
0x140048a42  mov     [rsp+0C8h+var_98], 52h ; 'R'
0x140048a49  mov     [rsp+0C8h+var_A0], 12h
0x140048a51  mov     byte ptr [rsp+0C8h+Timeout], 2
0x140048a56  call    WPP_RECORDER_AND_TRACE_SF_d
0x140048a5b  mov     eax, esi
0x140048a5d  jmp     loc_140048FAF
0x140048a62  xorps   xmm0, xmm0
0x140048a65  lea     rbp, [rbx+640h]
0x140048a6c  mov     rcx, rbp; SpinLock
0x140048a6f  xor     esi, esi
0x140048a71  movups  [rsp+0C8h+var_70], xmm0
0x140048a76  movups  [rsp+0C8h+var_60], xmm0
0x140048a7b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140048a82  nop     dword ptr [rax+rax+00h]
0x140048a87  lea     edx, [rsi+7]
0x140048a8a  mov     rcx, rbx
0x140048a8d  mov     r14b, al
0x140048a90  call    ?SetAvdtpState_NoLock@Avdtp_impl@@AEAA?AW4TAG_AvdtpState@@W42@@Z; Avdtp_impl::SetAvdtpState_NoLock(TAG_AvdtpState)
0x140048a95  mov     rdx, [rbx+478h]; unsigned __int64
0x140048a9c  test    rdx, rdx
0x140048a9f  jz      short loc_140048AAF
0x140048aa1  mov     rsi, rdx
0x140048aa4  mov     qword ptr [rbx+478h], 0
0x140048aaf  lea     rcx, [rbx+0D8h]; struct Avdtp_impl::tagSepInfo *
0x140048ab6  lea     r8, [rsp+0C8h+var_70]; struct SepInfoCopy *
0x140048abb  call    ?CopySepsToLocalInfo@Avdtp_impl@@CAXPEBUtagSepInfo@1@_KPEAUSepInfoCopy@@1@Z; Avdtp_impl::CopySepsToLocalInfo(Avdtp_impl::tagSepInfo const *,unsigned __int64,SepInfoCopy *,unsigned __int64)
0x140048ac0  mov     dl, r14b; NewIrql
0x140048ac3  mov     rcx, rbp; SpinLock
0x140048ac6  call    cs:__imp_KeReleaseSpinLock
0x140048acd  nop     dword ptr [rax+rax+00h]
0x140048ad2  test    rsi, rsi
0x140048ad5  jz      short loc_140048AE6
0x140048ad7  mov     rax, [rbx+498h]
0x140048ade  mov     rcx, rsi
0x140048ae1  call    _guard_dispatch_icall
0x140048ae6  mov     edx, edi; int
0x140048ae8  mov     rcx, rbx; this
0x140048aeb  call    ?Stop@Avdtp_impl@@CAXPEAXH@Z; Avdtp_impl::Stop(void *,int)
0x140048af0  lea     rbp, [rbx+6F0h]
0x140048af7  mov     rcx, rbp; SpinLock
0x140048afa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140048b01  nop     dword ptr [rax+rax+00h]
0x140048b06  mov     [rbx+6F8h], edi
0x140048b0c  lea     r15, [rbx+6E0h]
0x140048b13  lea     r13, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140048b1a  mov     rsi, [r15]
0x140048b1d  mov     r14d, 18h
0x140048b23  mov     [rsp+0C8h+NewIrql], al
0x140048b27  cmp     rsi, r15
0x140048b2a  jz      loc_140048CF3
0x140048b30  cmp     [rsi+8], r15
0x140048b34  jnz     loc_140048CEC
0x140048b3a  mov     rax, [rsi]
0x140048b3d  cmp     [rax+8], rsi
0x140048b41  jnz     loc_140048CEC
0x140048b47  mov     [r15], rax
0x140048b4a  xor     r12d, r12d
0x140048b4d  mov     [rax+8], r15
0x140048b51  cmp     [rsi+1Ch], r12b
0x140048b55  jz      loc_140048C56
0x140048b5b  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140048b60  test    eax, eax
0x140048b62  jnz     short loc_140048BDE
0x140048b64  mov     rcx, cs:WPP_GLOBAL_Control
0x140048b6b  lea     rax, WPP_GLOBAL_Control
0x140048b72  cmp     rcx, rax
0x140048b75  jz      short loc_140048B89
0x140048b77  mov     eax, [rcx+2Ch]
0x140048b7a  test    al, 8
0x140048b7c  jz      short loc_140048B89
0x140048b7e  cmp     byte ptr [rcx+29h], 4
0x140048b82  jb      short loc_140048B89
0x140048b84  mov     dl, dil
0x140048b87  jmp     short loc_140048B8B
0x140048b89  xor     dl, dl
0x140048b8b  lea     rax, WPP_RECORDER_INITIALIZED
0x140048b92  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140048b99  setnz   r8b
0x140048b9d  test    dl, dl
0x140048b9f  jnz     short loc_140048BAA
0x140048ba1  test    r8b, r8b
0x140048ba4  jz      loc_140048C73
0x140048baa  mov     rax, [rsi+10h]
0x140048bae  mov     r9, [rcx+40h]
0x140048bb2  mov     rcx, [rcx+18h]
0x140048bb6  mov     [rsp+0C8h+var_88], rax
0x140048bbb  mov     [rsp+0C8h+var_90], r13
0x140048bc0  mov     [rsp+0C8h+var_98], 54h ; 'T'
0x140048bc7  mov     [rsp+0C8h+var_A0], 4
0x140048bcf  mov     byte ptr [rsp+0C8h+Timeout], 4
0x140048bd4  call    WPP_RECORDER_AND_TRACE_SF_q
0x140048bd9  jmp     loc_140048C73
0x140048bde  mov     rcx, cs:WPP_GLOBAL_Control
0x140048be5  lea     rax, WPP_GLOBAL_Control
0x140048bec  cmp     rcx, rax
0x140048bef  jz      short loc_140048C03
0x140048bf1  mov     eax, [rcx+2Ch]
0x140048bf4  test    al, 8
0x140048bf6  jz      short loc_140048C03
0x140048bf8  cmp     byte ptr [rcx+29h], 4
0x140048bfc  jb      short loc_140048C03
0x140048bfe  mov     dl, dil
0x140048c01  jmp     short loc_140048C05
0x140048c03  xor     dl, dl
0x140048c05  lea     rax, WPP_RECORDER_INITIALIZED
0x140048c0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140048c13  setnz   r8b
0x140048c17  test    dl, dl
0x140048c19  jnz     short loc_140048C20
0x140048c1b  test    r8b, r8b
0x140048c1e  jz      short loc_140048C73
0x140048c20  mov     rax, [rsi+10h]
0x140048c24  mov     r9, [rcx+40h]
0x140048c28  mov     rcx, [rcx+18h]
0x140048c2c  mov     [rsp+0C8h+var_80], rbx
0x140048c31  mov     [rsp+0C8h+var_88], rax
0x140048c36  mov     [rsp+0C8h+var_90], r13
0x140048c3b  mov     [rsp+0C8h+var_98], 53h ; 'S'
0x140048c42  mov     [rsp+0C8h+var_A0], 4
0x140048c4a  mov     byte ptr [rsp+0C8h+Timeout], 4
0x140048c4f  call    WPP_RECORDER_AND_TRACE_SF_qi
0x140048c54  jmp     short loc_140048C73
0x140048c56  mov     eax, [rsi+18h]
0x140048c59  test    eax, eax
0x140048c5b  jle     short loc_140048C73
0x140048c5d  mov     ecx, eax
0x140048c5f  lea     edx, [rax+1]
0x140048c62  lock cmpxchg [rsi+18h], edx
0x140048c67  cmp     ecx, eax
0x140048c69  jnz     short loc_140048C59
0x140048c6b  test    edx, edx
0x140048c6d  jle     short loc_140048C73
0x140048c6f  mov     r12, [rsi+10h]
0x140048c73  mov     dl, [rsp+0C8h+NewIrql]; NewIrql
0x140048c77  lea     rcx, [rbx+6F0h]; SpinLock
0x140048c7e  mov     rbp, rsi
0x140048c81  call    cs:__imp_KeReleaseSpinLock
0x140048c88  nop     dword ptr [rax+rax+00h]
0x140048c8d  test    r12, r12
0x140048c90  jz      short loc_140048CD1
0x140048c92  mov     rcx, r12; Irp
0x140048c95  call    cs:__imp_IoCancelIrp
0x140048c9c  nop     dword ptr [rax+rax+00h]
0x140048ca1  or      eax, 0FFFFFFFFh
0x140048ca4  lock xadd [r14+rbp], eax
0x140048caa  cmp     eax, edi
0x140048cac  jnz     short loc_140048CD1
0x140048cae  mov     rcx, r12; Irp
0x140048cb1  call    cs:__imp_IoFreeIrp
0x140048cb8  nop     dword ptr [rax+rax+00h]
0x140048cbd  mov     edx, 41564454h; Tag
0x140048cc2  mov     rcx, rsi; P
0x140048cc5  call    cs:__imp_ExFreePoolWithTag
0x140048ccc  nop     dword ptr [rax+rax+00h]
0x140048cd1  lea     rbp, [rbx+6F0h]
0x140048cd8  mov     rcx, rbp; SpinLock
0x140048cdb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140048ce2  nop     dword ptr [rax+rax+00h]
0x140048ce7  jmp     loc_140048B1A
0x140048cec  mov     ecx, 3
0x140048cf1  int     29h; Win8: RtlFailFast(ecx)
0x140048cf3  mov     dl, al; NewIrql
0x140048cf5  mov     rcx, rbp; SpinLock
0x140048cf8  call    cs:__imp_KeReleaseSpinLock
0x140048cff  nop     dword ptr [rax+rax+00h]
0x140048d04  lea     rdx, ?impl_Create@Avdtp_impl@@SAPEAXPEAU_DEVICE_OBJECT@@0PEAU_IO_REMOVE_LOCK@@GPEAX_KPEBUAVDTPCallbackTable@@3PEAUtagAVDTPFunctionTable@@@Z; void *
0x140048d0b  mov     rcx, rbx; this
0x140048d0e  call    ?InterfaceDereference@Avdtp_impl@@AEAAXPEAX@Z; Avdtp_impl::InterfaceDereference(void *)
0x140048d13  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140048d18  test    eax, eax
0x140048d1a  jz      short loc_140048D93
0x140048d1c  mov     r10, cs:WPP_GLOBAL_Control
0x140048d23  lea     r12, WPP_GLOBAL_Control
0x140048d2a  cmp     r10, r12
0x140048d2d  jz      short loc_140048D43
0x140048d2f  mov     eax, [r10+2Ch]
0x140048d33  test    al, 8
0x140048d35  jz      short loc_140048D43
0x140048d37  cmp     byte ptr [r10+29h], 4
0x140048d3c  jb      short loc_140048D43
0x140048d3e  mov     dl, dil
0x140048d41  jmp     short loc_140048D45
0x140048d43  xor     dl, dl
0x140048d45  lea     rsi, WPP_RECORDER_INITIALIZED
0x140048d4c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140048d53  setnz   r8b
0x140048d57  test    dl, dl
0x140048d59  jnz     short loc_140048D60
0x140048d5b  test    r8b, r8b
0x140048d5e  jz      short loc_140048DA1
0x140048d60  xor     ecx, ecx
0x140048d62  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x140048d67  mov     rcx, [r10+18h]
0x140048d6b  mov     r9, rax
0x140048d6e  mov     [rsp+0C8h+var_88], rbx
0x140048d73  mov     [rsp+0C8h+var_90], r13
0x140048d78  mov     [rsp+0C8h+var_98], 55h ; 'U'
0x140048d7f  mov     [rsp+0C8h+var_A0], 4
0x140048d87  mov     byte ptr [rsp+0C8h+Timeout], 4
0x140048d8c  call    WPP_RECORDER_AND_TRACE_SF_q
0x140048d91  jmp     short loc_140048DA1
0x140048d93  lea     r12, WPP_GLOBAL_Control
0x140048d9a  lea     rsi, WPP_RECORDER_INITIALIZED
0x140048da1  lea     rcx, [rbx+0B0h]; Object
0x140048da8  mov     [rsp+0C8h+Timeout], 0; Timeout
0x140048db1  xor     r9d, r9d; Alertable
0x140048db4  xor     r8d, r8d; WaitMode
0x140048db7  xor     edx, edx; WaitReason
0x140048db9  call    cs:__imp_KeWaitForSingleObject
0x140048dc0  nop     dword ptr [rax+rax+00h]
0x140048dc5  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140048dca  test    eax, eax
0x140048dcc  jnz     short loc_140048E2E
0x140048dce  mov     rcx, cs:WPP_GLOBAL_Control
0x140048dd5  cmp     rcx, r12
0x140048dd8  jz      short loc_140048DEC
0x140048dda  mov     eax, [rcx+2Ch]
0x140048ddd  test    al, 8
0x140048ddf  jz      short loc_140048DEC
0x140048de1  cmp     byte ptr [rcx+29h], 4
0x140048de5  jb      short loc_140048DEC
  ... truncated ...
```
