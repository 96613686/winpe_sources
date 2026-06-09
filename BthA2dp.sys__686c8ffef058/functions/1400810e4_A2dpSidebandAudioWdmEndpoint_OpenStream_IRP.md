# A2dpSidebandAudioWdmEndpoint::OpenStream(_IRP *)

- ea: `0x1400810e4`
- end: `0x140081b99`
- name: `?OpenStream@A2dpSidebandAudioWdmEndpoint@@AEAAJPEAU_IRP@@@Z`
- size: `2741`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140080730`

## callees

- `0x140003530`
- `0x140006380`
- `0x140006410`
- `0x140006a88`
- `0x14000e690`
- `0x14000f570`
- `0x14000fffc`
- `0x14001f8bc`
- `0x14001f93c`
- `0x14001f9ac`
- `0x1400202e8`
- `0x14002d8e8`
- `0x140030c98`
- `0x140036b48`
- `0x140037364`
- `0x140037648`
- `0x140037778`
- `0x14005c870`
- `0x14005ce00`
- `0x1400810e4`
- `0x140081ba0`
- `0x1400826f8`
- `0x140085c3c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14008118d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008118d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14008119c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14008119c`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::OpenStream(A2dpSidebandAudioWdmEndpoint *this, struct _IRP *a2)
{
  struct _IRP *v2; // r14
  char v4; // di
  int *v5; // r12
  __int64 v6; // r8
  int v7; // edx
  int v8; // edx
  int v9; // r8d
  __int64 v10; // r15
  __int64 v11; // rdx
  __int64 v12; // rsi
  __int64 v13; // r8
  int v14; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  PDEVICE_OBJECT v16; // rcx
  unsigned int InboundQuota; // ecx
  __m128i si128; // xmm0
  int v19; // edx
  int v20; // r8d
  unsigned __int64 v21; // rdx
  __int64 v22; // rbx
  LARGE_INTEGER *p_DefaultTimeout; // r14
  unsigned int HighPart; // eax
  __int64 v25; // rcx
  PDEVICE_OBJECT v26; // rcx
  int v27; // edx
  int v28; // r8d
  __int64 v29; // r14
  int v30; // edx
  int v31; // r8d
  PVOID DeviceExtension; // r9
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  void *L2capMediaChannelHandle; // rax
  int v35; // edx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  int v43; // r14d
  __int64 v44; // rbx
  PDEVICE_OBJECT v45; // rcx
  utl::_RefCountBase *v46; // rcx
  int v47; // [rsp+20h] [rbp-69h]
  int v48; // [rsp+28h] [rbp-61h]
  int v49; // [rsp+30h] [rbp-59h]
  __int16 v50; // [rsp+30h] [rbp-59h]
  __int16 v51; // [rsp+30h] [rbp-59h]
  __int16 v52; // [rsp+30h] [rbp-59h]
  int v53; // [rsp+38h] [rbp-51h]
  char v54; // [rsp+40h] [rbp-49h]
  unsigned __int64 v55; // [rsp+60h] [rbp-29h] BYREF
  __int64 v56; // [rsp+68h] [rbp-21h]
  __int64 v57; // [rsp+70h] [rbp-19h] BYREF
  utl::_RefCountBase *v58; // [rsp+78h] [rbp-11h]
  __int64 v59; // [rsp+80h] [rbp-9h] BYREF
  utl::_RefCountBase *v60; // [rsp+88h] [rbp-1h]
  __m128i v61; // [rsp+90h] [rbp+7h] BYREF
  __int64 v62; // [rsp+A0h] [rbp+17h]
  int v64; // [rsp+100h] [rbp+77h] BYREF
  char *v65; // [rsp+108h] [rbp+7Fh] BYREF

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      68,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)this + 744));
  v65 = (char *)this + 744;
  v5 = (int *)((char *)this + 800);
  if ( (unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline() && *v5 == 3 )
    *v5 = 0;
  v7 = *v5;
  if ( *v5 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = v4;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v6,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        19,
        69,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        *v5,
        this);
    }
LABEL_161:
    __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v65);
    return 3221225860LL;
  }
  utl::weak_ptr<BtaMpmContext>::lock((char *)this + 616, &v57, v6);
  if ( !v57 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = v4;
      LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        v9,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        18,
        70,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        132);
    }
    goto LABEL_159;
  }
  v10 = *(_QWORD *)(v57 + 488);
  v56 = v10;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(v10 + 3560))(50434, 1346650433);
  v14 = -1073741670;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = v4;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v13,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        18,
        71,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids);
    }
    goto LABEL_110;
  }
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x18 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_149;
    v50 = 72;
LABEL_148:
    LOBYTE(v11) = v4;
    WPP_RECORDER_AND_TRACE_SF_d(
      v16->AttachedDevice,
      v11,
      v13,
      v16->DeviceExtension,
      2,
      18,
      v50,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      13);
LABEL_149:
    (*(void (__fastcall **)(__int64, __int64, __int64))(v10 + 3568))(v12, v11, v13);
    if ( v58 )
      utl::_RefCountBase::_DecStrong(v58);
    __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v65);
    return 3221225485LL;
  }
  InboundQuota = CurrentStackLocation->Parameters.CreatePipe.Parameters->InboundQuota;
  if ( InboundQuota > 0xFF )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_149;
    v50 = 73;
    goto LABEL_148;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(_BYTE *)(v12 + 254) = InboundQuota;
  v62 = -1;
  v61 = si128;
  if ( InboundQuota )
  {
    if ( !(unsigned __int8)utl::vector<_AVDTP_AUDIO_INTERFACE_PARAMETER,utl::allocator<_AVDTP_AUDIO_INTERFACE_PARAMETER>>::_Resize<,0>(
                             &v61,
                             InboundQuota) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v4 = 0;
      }
      if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = v4;
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v19,
          v20,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          18,
          74,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          154);
      }
LABEL_109:
      utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(&v61);
      (*(void (__fastcall **)(__int64))(v10 + 3568))(v12);
LABEL_110:
      if ( v58 )
        utl::_RefCountBase::_DecStrong(v58);
      __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v65);
      return (unsigned int)v14;
    }
    v21 = CurrentStackLocation->Parameters.Create.Options - 24LL;
    v22 = v61.m128i_i64[0];
    p_DefaultTimeout = &CurrentStackLocation->Parameters.CreatePipe.Parameters->DefaultTimeout;
    while ( 1 )
    {
      v55 = v21;
      if ( v22 == v61.m128i_i64[1] )
        break;
      if ( v21 < 0x18 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v4 = 0;
        }
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_63;
        v51 = 75;
LABEL_62:
        LOBYTE(v21) = v4;
        WPP_RECORDER_AND_TRACE_SF_d(
          v26->AttachedDevice,
          v21,
          v20,
          v26->DeviceExtension,
          2,
          18,
          v51,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          13);
        goto LABEL_63;
      }
      *(_DWORD *)v22 = (unsigned __int16)p_DefaultTimeout->LowPart;
      if ( p_DefaultTimeout[2].LowPart > 0xFFFF )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v4 = 0;
        }
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_63;
        v51 = 76;
        goto LABEL_62;
      }
      *(_WORD *)(v22 + 4) = p_DefaultTimeout[2].LowPart;
      if ( p_DefaultTimeout[2].HighPart > 0xFFu )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v4 = 0;
        }
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v51 = 77;
          goto LABEL_62;
        }
LABEL_63:
        utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(&v61);
        goto LABEL_149;
      }
      *(_BYTE *)(v22 + 6) = BYTE4(p_DefaultTimeout[2].QuadPart);
      HighPart = p_DefaultTimeout[2].HighPart;
      if ( HighPart )
      {
        memmove((void *)(v22 + 7), &p_DefaultTimeout[3], HighPart);
        v21 = v55;
      }
      v25 = (unsigned int)p_DefaultTimeout[2].HighPart;
      v21 += -24 - v25;
      p_DefaultTimeout = (LARGE_INTEGER *)((char *)p_DefaultTimeout + v25 + 24);
      v22 += 262;
    }
    *(_QWORD *)(v12 + 255) = v61.m128i_i64[0];
  }
  else
  {
    *(_QWORD *)(v12 + 255) = 0;
  }
  A2dpRole::GetCurrentSelectedCodec(*(_QWORD *)(v10 + 8), &v59);
  v29 = v59;
  if ( !v59 || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59) != 1 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v27) = v4;
      LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v27,
        v28,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        18,
        78,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        132);
    }
    if ( v60 )
      utl::_RefCountBase::_DecStrong(v60);
    utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(&v61);
    (*(void (__fastcall **)(__int64))(v10 + 3568))(v12);
LABEL_159:
    if ( v58 )
      utl::_RefCountBase::_DecStrong(v58);
    goto LABEL_161;
  }
  v64 = 132;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v29 + 64LL))(v29, v12 + 122, &v64);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_107;
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v54 = v14;
    v52 = 79;
LABEL_106:
    LOBYTE(v30) = v4;
    WPP_RECORDER_AND_TRACE_SF_d(
      (_DWORD)AttachedDevice,
      v30,
      v31,
      (_DWORD)DeviceExtension,
      2,
      18,
      v52,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      v54);
LABEL_107:
    if ( v60 )
      utl::_RefCountBase::_DecStrong(v60);
    goto LABEL_109;
  }
  *(_WORD *)(v12 + 120) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 120LL))(v29);
  L2capMediaChannelHandle = A2DP_Device::GetL2capMediaChannelHandle((A2DP_Device *)v10);
  *(_QWORD *)(v12 + 112) = L2capMediaChannelHandle;
  LOBYTE(v35) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v35 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_dqq(
      WPP_GLOBAL_Control->AttachedDevice,
      v35,
      v36,
      WPP_GLOBAL_Control->DeviceExtension,
      v47,
      v48,
      v49,
      v53,
      v37,
      (char)L2capMediaChannelHandle,
      (char)this);
  v14 = A2dpUtilities::SendBrbSynchronously(*(PDEVICE_OBJECT *)(v10 + 376), (struct _BRB *)v12, v36, v37);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_107;
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v54 = v14;
    v52 = 81;
    goto LABEL_106;
  }
  v39 = utl::make_unique<SiopStoreMap,,0>(&v55);
  utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::operator=<SiopStoreMap,utl::default_delete<SiopStoreMap>,0>(
    (char *)this + 672,
    v39);
  utl::unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>::~unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>(&v55);
  if ( *((_QWORD *)this + 84) )
  {
    v43 = 0;
    v44 = v12 + 266;
    if ( *(_BYTE *)(v12 + 265) )
    {
      do
      {
        A2dpSidebandAudioWdmEndpoint::StoreAudioInterfaceParameter(
          this,
          *((struct SiopStore **)this + 84),
          (struct _AVDTP_AUDIO_INTERFACE_PARAMETER *)v44);
        ++v43;
        v44 += *(unsigned __int8 *)(v44 + 6) + 7LL;
      }
      while ( v43 < *(unsigned __int8 *)(v12 + 265) );
      v10 = v56;
    }
  }
  else
  {
    v45 = WPP_GLOBAL_Control;
    LOBYTE(v40) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v41) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v40 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v40,
        (_BYTE)v41,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        19,
        82,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        (char)this);
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v45, v40, v41, v42);
  }
  A2dpSidebandAudioWdmEndpoint::SetAvdtpOffloadHandle(this, *(_WORD *)(v12 + 263));
  v46 = v60;
  *v5 = 1;
  if ( v46 )
    utl::_RefCountBase::_DecStrong(v46);
  utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(&v61);
  (*(void (__fastcall **)(__int64))(v10 + 3568))(v12);
  if ( v58 )
    utl::_RefCountBase::_DecStrong(v58);
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v65);
  return 0;
}

```

## disassembly

```asm
0x1400810e4  mov     [rsp-8+arg_8], rbx
0x1400810e9  mov     [rsp-8+arg_0], rcx
0x1400810ee  push    rbp
0x1400810ef  push    rsi
0x1400810f0  push    rdi
0x1400810f1  push    r12
0x1400810f3  push    r13
0x1400810f5  push    r14
0x1400810f7  push    r15
0x1400810f9  lea     rbp, [rsp-27h]
0x1400810fe  sub     rsp, 0B0h
0x140081105  mov     r14, rdx
0x140081108  mov     r13, rcx
0x14008110b  mov     rcx, cs:WPP_GLOBAL_Control
0x140081112  lea     rsi, WPP_GLOBAL_Control
0x140081119  mov     edi, 1
0x14008111e  cmp     rcx, rsi
0x140081121  jz      short loc_140081137
0x140081123  test    dword ptr [rcx+2Ch], 40000h
0x14008112a  jz      short loc_140081137
0x14008112c  cmp     byte ptr [rcx+29h], 4
0x140081130  jb      short loc_140081137
0x140081132  mov     dl, dil
0x140081135  jmp     short loc_140081139
0x140081137  xor     dl, dl
0x140081139  lea     r15, WPP_RECORDER_INITIALIZED
0x140081140  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140081147  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14008114e  setnz   r8b
0x140081152  test    dl, dl
0x140081154  jnz     short loc_14008115B
0x140081156  test    r8b, r8b
0x140081159  jz      short loc_140081186
0x14008115b  mov     [rsp+0E0h+var_A0], r13
0x140081160  mov     [rsp+0E0h+var_A8], r9
0x140081165  mov     r9, [rcx+40h]
0x140081169  mov     rcx, [rcx+18h]
0x14008116d  mov     [rsp+0E0h+var_B0], 44h ; 'D'
0x140081174  mov     [rsp+0E0h+var_B8], 13h
0x14008117c  mov     [rsp+0E0h+var_C0], 4
0x140081181  call    WPP_RECORDER_AND_TRACE_SF_q
0x140081186  lea     rbx, [r13+2E8h]
0x14008118d  call    cs:__imp_KeEnterCriticalRegion
0x140081194  nop     dword ptr [rax+rax+00h]
0x140081199  mov     rcx, rbx; FastMutex
0x14008119c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400811a3  nop     dword ptr [rax+rax+00h]
0x1400811a8  mov     [rbp+57h+arg_18], rbx
0x1400811ac  lea     r12, [r13+320h]
0x1400811b3  call    Feature_60759990__private_IsEnabledDeviceUsageNoInline
0x1400811b8  test    eax, eax
0x1400811ba  jz      short loc_1400811CB
0x1400811bc  cmp     dword ptr [r12], 3
0x1400811c1  jnz     short loc_1400811CB
0x1400811c3  mov     dword ptr [r12], 0
0x1400811cb  mov     edx, [r12]
0x1400811cf  test    edx, edx
0x1400811d1  jz      short loc_140081248
0x1400811d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400811da  cmp     rcx, rsi
0x1400811dd  jz      short loc_1400811EE
0x1400811df  test    dword ptr [rcx+2Ch], 40000h
0x1400811e6  jz      short loc_1400811EE
0x1400811e8  cmp     byte ptr [rcx+29h], 2
0x1400811ec  jnb     short loc_1400811F1
0x1400811ee  xor     dil, dil
0x1400811f1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400811f8  setnz   r8b
0x1400811fc  test    dil, dil
0x1400811ff  jnz     short loc_14008120A
0x140081201  test    r8b, r8b
0x140081204  jz      loc_140081B6F
0x14008120a  mov     r9, [rcx+40h]
0x14008120e  lea     r11, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140081215  mov     rcx, [rcx+18h]
0x140081219  mov     [rsp+0E0h+var_98], r13
0x14008121e  mov     dword ptr [rsp+0E0h+var_A0], edx
0x140081222  mov     dl, dil
0x140081225  mov     [rsp+0E0h+var_A8], r11
0x14008122a  mov     [rsp+0E0h+var_B0], 45h ; 'E'
0x140081231  mov     [rsp+0E0h+var_B8], 13h
0x140081239  mov     [rsp+0E0h+var_C0], 2
0x14008123e  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x140081243  jmp     loc_140081B6F
0x140081248  lea     rcx, [r13+268h]
0x14008124f  lea     rdx, [rbp+57h+var_70]
0x140081253  call    ?lock@?$weak_ptr@VBtaMpmContext@@@utl@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@2@XZ; utl::weak_ptr<BtaMpmContext>::lock(void)
0x140081258  mov     r15, [rbp+57h+var_70]
0x14008125c  test    r15, r15
0x14008125f  jz      loc_140081AEF
0x140081265  mov     r15, [r15+1E8h]
0x14008126c  mov     edx, 50444141h
0x140081271  mov     ecx, 0C502h
0x140081276  mov     [rbp+57h+var_78], r15
0x14008127a  mov     rax, [r15+0DE8h]
0x140081281  call    _guard_dispatch_icall
0x140081286  mov     rsi, rax
0x140081289  mov     ebx, 0C000009Ah
0x14008128e  test    rax, rax
0x140081291  jnz     short loc_14008130D
0x140081293  mov     rcx, cs:WPP_GLOBAL_Control
0x14008129a  lea     r14, WPP_GLOBAL_Control
0x1400812a1  cmp     rcx, r14
0x1400812a4  jz      short loc_1400812B5
0x1400812a6  test    dword ptr [rcx+2Ch], 20000h
0x1400812ad  jz      short loc_1400812B5
0x1400812af  cmp     byte ptr [rcx+29h], 2
0x1400812b3  jnb     short loc_1400812B8
0x1400812b5  xor     dil, dil
0x1400812b8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400812bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400812c6  setnz   r8b
0x1400812ca  test    dil, dil
0x1400812cd  jnz     short loc_1400812D8
0x1400812cf  test    r8b, r8b
0x1400812d2  jz      loc_14008183C
0x1400812d8  mov     r9, [rcx+40h]
0x1400812dc  lea     r11, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x1400812e3  mov     rcx, [rcx+18h]
0x1400812e7  mov     dl, dil
0x1400812ea  mov     [rsp+0E0h+var_A8], r11
0x1400812ef  mov     [rsp+0E0h+var_B0], 47h ; 'G'
0x1400812f6  mov     [rsp+0E0h+var_B8], 12h
0x1400812fe  mov     [rsp+0E0h+var_C0], 2
0x140081303  call    WPP_RECORDER_AND_TRACE_SF_
0x140081308  jmp     loc_14008183C
0x14008130d  mov     r14, [r14+0B8h]
0x140081314  cmp     dword ptr [r14+10h], 18h
0x140081319  jnb     short loc_140081380
0x14008131b  mov     rcx, cs:WPP_GLOBAL_Control
0x140081322  lea     r14, WPP_GLOBAL_Control
0x140081329  cmp     rcx, r14
0x14008132c  jz      short loc_14008133D
0x14008132e  test    dword ptr [rcx+2Ch], 20000h
0x140081335  jz      short loc_14008133D
0x140081337  cmp     byte ptr [rcx+29h], 2
0x14008133b  jnb     short loc_140081340
0x14008133d  xor     dil, dil
0x140081340  lea     rax, WPP_RECORDER_INITIALIZED
0x140081347  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008134e  setnz   r8b
0x140081352  test    dil, dil
0x140081355  jnz     short loc_140081360
0x140081357  test    r8b, r8b
0x14008135a  jz      loc_140081ABF
0x140081360  mov     dword ptr [rsp+0E0h+var_A0], 0C000000Dh
0x140081368  lea     r11, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14008136f  mov     [rsp+0E0h+var_A8], r11
0x140081374  mov     [rsp+0E0h+var_B0], 48h ; 'H'
0x14008137b  jmp     loc_140081AA2
0x140081380  mov     rax, [r14+20h]
0x140081384  mov     ecx, [rax+10h]
0x140081387  cmp     ecx, 0FFh
0x14008138d  ja      loc_140081A46
0x140081393  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14008139b  mov     [rsi+0FEh], cl
0x1400813a1  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x1400813a9  movdqu  [rbp+57h+var_50], xmm0
0x1400813ae  test    ecx, ecx
0x1400813b0  jz      loc_140081639
0x1400813b6  mov     edx, ecx
0x1400813b8  lea     rcx, [rbp+57h+var_50]
0x1400813bc  call    ??$_Resize@$$V$0A@@?$vector@U_AVDTP_AUDIO_INTERFACE_PARAMETER@@V?$allocator@U_AVDTP_AUDIO_INTERFACE_PARAMETER@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<_AVDTP_AUDIO_INTERFACE_PARAMETER,utl::allocator<_AVDTP_AUDIO_INTERFACE_PARAMETER>>::_Resize<,0>(unsigned __int64)
0x1400813c1  test    al, al
0x1400813c3  jnz     short loc_140081443
0x1400813c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400813cc  lea     r14, WPP_GLOBAL_Control
0x1400813d3  cmp     rcx, r14
0x1400813d6  jz      short loc_1400813E7
0x1400813d8  test    dword ptr [rcx+2Ch], 20000h
0x1400813df  jz      short loc_1400813E7
0x1400813e1  cmp     byte ptr [rcx+29h], 2
0x1400813e5  jnb     short loc_1400813EA
0x1400813e7  xor     dil, dil
0x1400813ea  lea     rax, WPP_RECORDER_INITIALIZED
0x1400813f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400813f8  setnz   r8b
0x1400813fc  test    dil, dil
0x1400813ff  jnz     short loc_14008140A
0x140081401  test    r8b, r8b
0x140081404  jz      loc_140081824
0x14008140a  mov     r9, [rcx+40h]
0x14008140e  lea     r11, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140081415  mov     rcx, [rcx+18h]
0x140081419  mov     dl, dil
0x14008141c  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x140081420  mov     [rsp+0E0h+var_A8], r11
0x140081425  mov     [rsp+0E0h+var_B0], 4Ah ; 'J'
0x14008142c  mov     [rsp+0E0h+var_B8], 12h
0x140081434  mov     [rsp+0E0h+var_C0], 2
0x140081439  call    WPP_RECORDER_AND_TRACE_SF_d
0x14008143e  jmp     loc_140081824
0x140081443  mov     edx, [r14+10h]
0x140081447  mov     r14, [r14+20h]
0x14008144b  sub     rdx, 18h
0x14008144f  mov     rbx, qword ptr [rbp+57h+var_50]
0x140081453  add     r14, 18h
0x140081457  mov     [rbp+57h+var_80], rdx
0x14008145b  cmp     rbx, qword ptr [rbp+57h+var_50+8]
0x14008145f  jz      loc_14008162C
0x140081465  cmp     rdx, 18h
0x140081469  jb      loc_1400815C7
0x14008146f  mov     eax, [r14]
0x140081472  movzx   ecx, ax
0x140081475  mov     [rbx], ecx
0x140081477  cmp     dword ptr [r14+10h], 0FFFFh
0x14008147f  ja      loc_140081566
0x140081485  movzx   eax, word ptr [r14+10h]
0x14008148a  mov     [rbx+4], ax
0x14008148e  cmp     dword ptr [r14+14h], 0FFh
0x140081496  ja      short loc_1400814DF
0x140081498  mov     al, [r14+14h]
0x14008149c  mov     [rbx+6], al
0x14008149f  mov     eax, [r14+14h]
0x1400814a3  test    eax, eax
0x1400814a5  jz      short loc_1400814BB
0x1400814a7  mov     r8d, eax; Size
0x1400814aa  lea     rdx, [r14+18h]; Src
0x1400814ae  lea     rcx, [rbx+7]; void *
0x1400814b2  call    memmove
0x1400814b7  mov     rdx, [rbp+57h+var_80]
0x1400814bb  mov     ecx, [r14+14h]
0x1400814bf  mov     rax, 0FFFFFFFFFFFFFFE8h
0x1400814c6  sub     rax, rcx
0x1400814c9  add     r14, 18h
0x1400814cd  add     rdx, rax
0x1400814d0  add     r14, rcx
0x1400814d3  add     rbx, 106h
0x1400814da  jmp     loc_140081457
0x1400814df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400814e6  lea     r14, WPP_GLOBAL_Control
0x1400814ed  cmp     rcx, r14
0x1400814f0  jz      short loc_140081501
0x1400814f2  test    dword ptr [rcx+2Ch], 20000h
0x1400814f9  jz      short loc_140081501
0x1400814fb  cmp     byte ptr [rcx+29h], 2
0x1400814ff  jnb     short loc_140081504
0x140081501  xor     dil, dil
0x140081504  lea     rax, WPP_RECORDER_INITIALIZED
0x14008150b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140081512  setnz   r8b
0x140081516  test    dil, dil
0x140081519  jnz     short loc_140081520
0x14008151b  test    r8b, r8b
0x14008151e  jz      short loc_140081558
0x140081520  mov     dword ptr [rsp+0E0h+var_A0], 0C000000Dh
0x140081528  lea     r11, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14008152f  mov     [rsp+0E0h+var_A8], r11
0x140081534  mov     [rsp+0E0h+var_B0], 4Dh ; 'M'
0x14008153b  mov     r9, [rcx+40h]
0x14008153f  mov     dl, dil
0x140081542  mov     rcx, [rcx+18h]
0x140081546  mov     [rsp+0E0h+var_B8], 12h
0x14008154e  mov     [rsp+0E0h+var_C0], 2
0x140081553  call    WPP_RECORDER_AND_TRACE_SF_d
0x140081558  lea     rcx, [rbp+57h+var_50]
0x14008155c  call    ?_Uninit@?$vector@PEAUFrameListEntry@@V?$allocator@PEAUFrameListEntry@@@utl@@@utl@@AEAAXXZ; utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(void)
0x140081561  jmp     loc_140081ABF
0x140081566  mov     rcx, cs:WPP_GLOBAL_Control
0x14008156d  lea     r14, WPP_GLOBAL_Control
0x140081574  cmp     rcx, r14
0x140081577  jz      short loc_140081588
0x140081579  test    dword ptr [rcx+2Ch], 20000h
0x140081580  jz      short loc_140081588
0x140081582  cmp     byte ptr [rcx+29h], 2
0x140081586  jnb     short loc_14008158B
0x140081588  xor     dil, dil
0x14008158b  lea     rax, WPP_RECORDER_INITIALIZED
0x140081592  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140081599  setnz   r8b
0x14008159d  test    dil, dil
0x1400815a0  jnz     short loc_1400815A7
0x1400815a2  test    r8b, r8b
0x1400815a5  jz      short loc_140081558
0x1400815a7  mov     dword ptr [rsp+0E0h+var_A0], 0C000000Dh
0x1400815af  lea     r11, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x1400815b6  mov     [rsp+0E0h+var_A8], r11
0x1400815bb  mov     [rsp+0E0h+var_B0], 4Ch ; 'L'
0x1400815c2  jmp     loc_14008153B
0x1400815c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400815ce  lea     r14, WPP_GLOBAL_Control
0x1400815d5  cmp     rcx, r14
0x1400815d8  jz      short loc_1400815E9
0x1400815da  test    dword ptr [rcx+2Ch], 20000h
0x1400815e1  jz      short loc_1400815E9
0x1400815e3  cmp     byte ptr [rcx+29h], 2
0x1400815e7  jnb     short loc_1400815EC
0x1400815e9  xor     dil, dil
0x1400815ec  lea     rax, WPP_RECORDER_INITIALIZED
0x1400815f3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400815fa  setnz   r8b
0x1400815fe  test    dil, dil
0x140081601  jnz     short loc_14008160C
0x140081603  test    r8b, r8b
0x140081606  jz      loc_140081558
0x14008160c  mov     dword ptr [rsp+0E0h+var_A0], 0C000000Dh
0x140081614  lea     r11, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14008161b  mov     [rsp+0E0h+var_A8], r11
0x140081620  mov     [rsp+0E0h+var_B0], 4Bh ; 'K'
0x140081627  jmp     loc_14008153B
  ... truncated ...
```
