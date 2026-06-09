# A2dpSidebandAudioWdmEndpoint::GetAvdtpConfiguration(void)

- ea: `0x14007ea6c`
- end: `0x14007f814`
- name: `?GetAvdtpConfiguration@A2dpSidebandAudioWdmEndpoint@@IEAAJXZ`
- size: `3496`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *this, __int16, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x14007f930`

## callees

- `0x140003530`
- `0x140006410`
- `0x14000e690`
- `0x14000f570`
- `0x140010628`
- `0x14001f93c`
- `0x14001f9ac`
- `0x1400205f4`
- `0x14002092c`
- `0x14002e8c8`
- `0x1400374f4`
- `0x140037558`
- `0x1400375d0`
- `0x1400379f4`
- `0x140037ac0`
- `0x140037df8`
- `0x14005c7d0`
- `0x14005c870`
- `0x14005ce00`
- `0x140079db0`
- `0x14007e7b4`
- `0x14007ea6c`
- `0x14008105c`
- `0x1400826f8`
- `0x140085c3c`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14007f6d5`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14007f6d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007f6a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007f6a5`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::GetAvdtpConfiguration(
        A2dpSidebandAudioWdmEndpoint *this,
        __int16 a2,
        __int64 a3)
{
  A2dpSidebandAudioWdmEndpoint *v3; // r13
  unsigned __int8 v4; // r12
  char v5; // si
  int v6; // edx
  int v7; // r8d
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // r14
  __int64 *v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  unsigned __int8 *v13; // rdi
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rax
  int v17; // r15d
  unsigned __int8 v19; // r14
  int v20; // edx
  int v21; // r8d
  struct _AVDTP_CATEGORY_HEADER *v22; // r15
  __int64 v23; // rdx
  unsigned __int8 *v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // r13d
  __int64 v28; // rcx
  int v29; // edx
  int AudioInterfaceParametersFromSiopStore; // edi
  int v31; // r8d
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // eax
  int v35; // edx
  __int64 v36; // r8
  __int64 v37; // r9
  char v38; // di
  __int64 v39; // r8
  __int64 v40; // rax
  unsigned int v41; // eax
  __int64 *v42; // rax
  __int64 v43; // rdi
  int v44; // edx
  int v45; // r8d
  unsigned __int16 v46; // dx
  int v47; // r8d
  __int64 v48; // rax
  struct _AVDTP_CATEGORY_HEADER *v49; // rdi
  int i; // r12d
  __int64 v51; // rbx
  int v52; // edx
  int v53; // ebx
  int v54; // r8d
  char v55; // al
  const struct _AVDTP_CATEGORY_HEADER *v56; // rdx
  int v57; // edx
  int v58; // r8d
  int v59; // edi
  __int64 v60; // r14
  int v61; // eax
  int v62; // edx
  int v63; // r8d
  __int64 v64; // rdi
  int v65; // ebx
  __int64 v66; // rcx
  const WCHAR *AudioControllerInterfacePath; // rax
  int v68; // eax
  int v69; // edx
  int v70; // r8d
  int v71; // ebx
  int v72; // [rsp+28h] [rbp-D8h]
  __int16 v73; // [rsp+30h] [rbp-D0h]
  int v74; // [rsp+38h] [rbp-C8h]
  unsigned __int8 v75; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v76; // [rsp+60h] [rbp-A0h]
  __int64 v77; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 *v78; // [rsp+70h] [rbp-90h] BYREF
  __int64 v79; // [rsp+78h] [rbp-88h]
  __int64 v80; // [rsp+80h] [rbp-80h] BYREF
  __int64 v81; // [rsp+88h] [rbp-78h] BYREF
  struct _AVDTP_CATEGORY_HEADER *v82; // [rsp+90h] [rbp-70h] BYREF
  __int64 v83; // [rsp+98h] [rbp-68h] BYREF
  utl::_RefCountBase *v84; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v86; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v87[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v88; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v89; // [rsp+E0h] [rbp-20h]
  __int128 v90; // [rsp+F0h] [rbp-10h] BYREF
  int v91; // [rsp+100h] [rbp+0h]

  v3 = this;
  *(_QWORD *)&DestinationString.Length = this;
  v4 = 0;
  v5 = 1;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
    || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(a2) = 0;
  }
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      52,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  utl::weak_ptr<BtaMpmContext>::lock((char *)v3 + 616, &v83, a3);
  if ( (unsigned __int8)utl::operator==<A2dpSidebandAudioWdmDevice>(&v83) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v5 = 0;
    }
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v5 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v73 = 53;
LABEL_16:
    LOBYTE(v6) = v5;
    WPP_RECORDER_AND_TRACE_SF_d(
      v8->AttachedDevice,
      v6,
      v7,
      v8->DeviceExtension,
      2,
      18,
      v73,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      132);
LABEL_46:
    if ( v84 )
      utl::_RefCountBase::_DecStrong(v84);
    return 3221225860LL;
  }
  v9 = *(_QWORD *)(v83 + 488);
  v79 = v9;
  if ( !v9 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v5 = 0;
    }
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v5 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v73 = 54;
    goto LABEL_16;
  }
  v10 = (__int64 *)*((_QWORD *)v3 + 3);
  v91 = 1;
  v90 = SIDEBANDAUDIO_PARAMS_SET_A2DP;
  v86 = 0;
  v11 = 0;
  v12 = *v10;
  v13 = 0;
  v77 = 0;
  v78 = 0;
  if ( (*(int (__fastcall **)(__int64 *, __int128 *, __int64 *))(v12 + 16))(v10, &v90, &v86) >= 0 )
  {
    v16 = utl::make_unique<unsigned char [0],0>(&v80, v86);
    utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::operator=(&v78, v16);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v80);
    v13 = v78;
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64, unsigned __int8 *, _QWORD))(**((_QWORD **)v3 + 3) + 8LL))(
            *((_QWORD *)v3 + 3),
            &v90,
            v86,
            v78,
            0);
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v5 = 0;
      }
      if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = v5;
        LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v14,
          v15,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          18,
          55,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          v17);
      }
      utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v78);
      utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v77);
      if ( v84 )
        utl::_RefCountBase::_DecStrong(v84);
      return (unsigned int)v17;
    }
  }
  if ( v9 == -3528 )
  {
    v19 = v9 - 56 + 2;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < v19 )
    {
      v5 = 0;
    }
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = v5;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        v15,
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        18,
        56,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        132);
    }
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v78);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v77);
    goto LABEL_46;
  }
  v82 = (struct _AVDTP_CATEGORY_HEADER *)(*(__int64 (__fastcall **)(__int64, __int64))(v9 + 3560))(50433, 1346650433);
  v22 = v82;
  if ( !v82 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v5 = 0;
    }
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v20) = v5;
      LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v20,
        v21,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        18,
        57,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids);
    }
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v78);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v77);
    if ( v84 )
      utl::_RefCountBase::_DecStrong(v84);
    return 3221225626LL;
  }
  utl::vector<utl::shared_ptr<A2dpAudioCodec>,utl::allocator<utl::shared_ptr<A2dpAudioCodec>>>::vector<utl::shared_ptr<A2dpAudioCodec>,utl::allocator<utl::shared_ptr<A2dpAudioCodec>>>(&v88);
  v23 = v86;
  v24 = v13;
  if ( v86 )
  {
    do
    {
      v25 = v24[1];
      ++v4;
      v24 += v25 + 2;
      v23 += -2 - v25;
    }
    while ( v23 );
    if ( v4 )
    {
      v26 = utl::make_unique<_AVDTP_CODEC_CAPABILITY [0],0>(&v80, v4, v24);
      utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::operator=(&v77, v26);
      utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v80);
      v11 = v77;
      v27 = 0;
      do
      {
        memmove((void *)(v11 + 132LL * (unsigned int)v27++), v13, v13[1] + 2LL);
        v13 += v13[1] + 2;
      }
      while ( v27 < v4 );
      v22 = v82;
      v3 = *(A2dpSidebandAudioWdmEndpoint **)&DestinationString.Length;
    }
  }
  *((_BYTE *)v22 + 112) = v4;
  *(_QWORD *)((char *)v22 + 113) = v11;
  utl::vector<utl::shared_ptr<A2dpAudioCodec>,utl::allocator<utl::shared_ptr<A2dpAudioCodec>>>::vector<utl::shared_ptr<A2dpAudioCodec>,utl::allocator<utl::shared_ptr<A2dpAudioCodec>>>(v87);
  AudioInterfaceParametersFromSiopStore = A2dpSidebandAudioWdmEndpoint::GetAudioInterfaceParametersFromSiopStore(
                                            v28,
                                            *((_QWORD *)v3 + 83),
                                            v87);
  if ( AudioInterfaceParametersFromSiopStore < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v5 = 0;
    }
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v29) = v5;
      LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v29,
        v31,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        18,
        58,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        AudioInterfaceParametersFromSiopStore);
    }
LABEL_74:
    utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(v87);
    utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(&v88);
    (*(void (__fastcall **)(struct _AVDTP_CATEGORY_HEADER *))(v79 + 3568))(v22);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v78);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v77);
    if ( v84 )
      utl::_RefCountBase::_DecStrong(v84);
    return (unsigned int)AudioInterfaceParametersFromSiopStore;
  }
  v32 = v87[1] - v87[0];
  *(_QWORD *)((char *)v22 + 122) = v87[0];
  v33 = 0x3E88CB3C9484E2BLL * (v32 >> 1);
  *((_BYTE *)v22 + 121) = v33;
  *(_QWORD *)&DestinationString.Length = v33;
  v34 = A2dpUtilities::SendBrbSynchronously(*(PDEVICE_OBJECT *)(v79 + 376), (struct _BRB *)v22);
  v37 = 0;
  AudioInterfaceParametersFromSiopStore = v34;
  if ( v34 < 0 )
  {
    if ( v34 != -1073741670 && v34 != -1073741789 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v5 = 0;
      }
      if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v35) = v5;
        LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          v35,
          v36,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          19,
          60,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          v34,
          (char)v3);
      }
      goto LABEL_74;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
      || (LOBYTE(v35) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
    {
      LOBYTE(v35) = 0;
    }
    LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v35 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        (_WORD)v35,
        v36,
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        19,
        59,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        (char)v3);
  }
  v38 = *((_BYTE *)v22 + 139);
  v75 = *((_BYTE *)v22 + 130);
  (*(void (__fastcall **)(struct _AVDTP_CATEGORY_HEADER *, __int64, __int64, __int64))(v79 + 3584))(
    v22,
    50433,
    v36,
    v37);
  *((_BYTE *)v22 + 121) = DestinationString.Length;
  *(_QWORD *)((char *)v22 + 122) = v87[0];
  *((_BYTE *)v22 + 139) = v38;
  *((_BYTE *)v22 + 112) = v4;
  *(_QWORD *)((char *)v22 + 113) = v11;
  *((_BYTE *)v22 + 130) = v75;
  v81 = 0;
  if ( v75 )
  {
    v40 = utl::make_unique<_AVDTP_CODEC_CAPABILITY [0],0>(&DestinationString, v75, v39);
    utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::operator=(&v81, v40);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&DestinationString);
    *(_QWORD *)((char *)v22 + 131) = v81;
  }
  v41 = *((unsigned __int8 *)v22 + 139);
  v80 = 0;
  if ( (_BYTE)v41 )
  {
    v42 = (__int64 *)utl::make_unique<_AVDTP_AUDIO_INTERFACE_PARAMETER [0],0>(&DestinationString, v41);
    v80 = *v42;
    v43 = v80;
    *v42 = 0;
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&DestinationString);
    *(_QWORD *)((char *)v22 + 140) = v43;
  }
  AudioInterfaceParametersFromSiopStore = A2dpUtilities::SendBrbSynchronously(
                                            *(PDEVICE_OBJECT *)(v79 + 376),
                                            (struct _BRB *)v22);
  if ( AudioInterfaceParametersFromSiopStore < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v5 = 0;
    }
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v44) = v5;
      LOBYTE(v45) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v44,
        v45,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        18,
        61,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        AudioInterfaceParametersFromSiopStore);
    }
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v80);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v81);
    goto LABEL_74;
  }
  if ( !*((_BYTE *)v22 + 130) )
    goto LABEL_135;
  v46 = 0;
  v47 = 0;
  do
  {
    v48 = (unsigned int)v47++;
    v46 += *(unsigned __int8 *)(132 * v48 + *(_QWORD *)((char *)v22 + 131) + 1) + 2;
  }
  while ( v47 < *((unsigned __int8 *)v22 + 130) );
  if ( v46 )
  {
    *(_QWORD *)&DestinationString.Length = v46;
    utl::make_unique<unsigned char [0],0>(&v82, v46);
    v49 = v82;
    for ( i = 0; i < *((unsigned __int8 *)v22 + 130); ++i )
    {
      v51 = 132LL * i;
      memmove(
        v49,
        (const void *)(v51 + *(_QWORD *)((char *)v22 + 131)),
        *(unsigned __int8 *)(v51 + *(_QWORD *)((char *)v22 + 131) + 1) + 2LL);
      v76 = *(_BYTE *)(v51 + *(_QWORD *)((char *)v22 + 131) + 1);
      v53 = A2dpRole::AddSidebandCodec(*(A2dpRole **)(v79 + 8), v49);
      if ( v53 < 0 )
      {
        v55 = *((_BYTE *)v49 + 3);
        if ( !v55 )
          goto LABEL_123;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
          || (LOBYTE(v52) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        {
          LOBYTE(v52) = 0;
        }
        if ( (_BYTE)v52 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v54) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_Ddq(
            WPP_GLOBAL_Control->AttachedDevice,
            v52,
            v54,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            v72,
            62,
            v74,
            v55,
            v53,
            (char)v3);
        }
      }
      v56 = v49;
      v49 = (struct _AVDTP_CATEGORY_HEADER *)((char *)v49 + v76 + 2);
      A2dpSidebandAudioWdmEndpoint::LogControllerReportedAvdtpCategory(v3, v56);
    }
    v53 = (***((__int64 (__fastcall ****)(_QWORD, __int128 *, _QWORD, struct _AVDTP_CATEGORY_HEADER *))v3 + 3))(
            *((_QWORD *)v3 + 3),
            &v90,
            *(_QWORD *)&DestinationString.Length,
            v82);
    if ( v53 >= 0 )
    {
      utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v82);
      goto LABEL_147;
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v5 = 0;
    }
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v57) = v5;
      LOBYTE(v58) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v57,
        v58,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        18,
        63,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        v53);
    }
LABEL_123:
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v82);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v80);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v81);
    utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(v87);
    utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(&v88);
    (*(void (__fastcall **)(struct _AVDTP_CATEGORY_HEADER *))(v79 + 3568))(v22);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v78);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v77);
    if ( v84 )
      utl::_RefCountBase::_DecStrong(v84);
    return (unsigned int)v53;
  }
  else
  {
LABEL_135:
    v59 = 0;
    if ( v4 )
    {
      do
      {
        v60 = v11 + 132LL * (unsigned int)v59;
        v61 = A2dpRole::AddSidebandCodec(
                *(A2dpRole **)(*((_QWORD *)v3 + 79) + 8LL),
                (struct _CATEGORY_CODEC_HEADER *)v60);
        if ( v61 < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
            || (LOBYTE(v62) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
          {
            LOBYTE(v62) = 0;
          }
          if ( (_BYTE)v62 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v63) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_Ddq(
              WPP_GLOBAL_Control->AttachedDevice,
              v62,
              v63,
              WPP_GLOBAL_Control->DeviceExtension,
              3,
              v72,
              64,
              v74,
              *(_BYTE *)(v60 + 3),
              v61,
              (char)v3);
          }
        }
        else
        {
          A2dpSidebandAudioWdmEndpoint::LogControllerReportedAvdtpCategory(
            v3,
            (const struct _AVDTP_CATEGORY_HEADER *)v60);
        }
        ++v59;
      }
      while ( v59 < v4 );
      v22 = v82;
    }
LABEL_147:
    v64 = v88;
    v65 = v89;
    if ( v88 != v89 )
    {
      v66 = *((_QWORD *)v3 + 79);
      DestinationString = 0;
      AudioControllerInterfacePath = A2dpRole::GetAudioControllerInterfacePath(*(A2dpRole **)(v66 + 8));
      RtlInitUnicodeString(&DestinationString, AudioControllerInterfacePath);
      v68 = IoSetDeviceInterfacePropertyData(
              &DestinationString,
              DEVPKEY_Bluetooth_LocalControllerSupportedCodecs,
              0,
              0,
              4099,
              v65 - (int)v64,
              v64);
      if ( v68 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
          || (LOBYTE(v69) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
        {
          LOBYTE(v69) = 0;
        }
        if ( (_BYTE)v69 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v70) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_dq(
            WPP_GLOBAL_Control->AttachedDevice,
            v69,
            v70,
            WPP_GLOBAL_Control->DeviceExtension,
            3,
            19,
            65,
            (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
            v68,
            (char)v3);
        }
      }
    }
    v71 = 0;
    if ( *((_BYTE *)v22 + 139) )
    {
      do
        A2dpSidebandAudioWdmEndpoint::StoreAudioInterfaceParameter(
          v3,
          *((struct SiopStore **)v3 + 3),
          (struct _AVDTP_AUDIO_INTERFACE_PARAMETER *)(*(_QWORD *)((char *)v22 + 140) + 262LL * v71++));
      while ( v71 < *((unsigned __int8 *)v22 + 139) );
    }
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v80);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v81);
    utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(v87);
    utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Uninit(&v88);
    (*(void (__fastcall **)(struct _AVDTP_CATEGORY_HEADER *))(v79 + 3568))(v22);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v78);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v77);
    if ( v84 )
      utl::_RefCountBase::_DecStrong(v84);
    return 0;
  }
}

```

## disassembly

```asm
0x14007ea6c  push    rbp
0x14007ea6e  push    rbx
0x14007ea6f  push    rsi
0x14007ea70  push    rdi
0x14007ea71  push    r12
0x14007ea73  push    r13
0x14007ea75  push    r14
0x14007ea77  push    r15
0x14007ea79  lea     rbp, [rsp-18h]
0x14007ea7e  sub     rsp, 118h
0x14007ea85  mov     rax, cs:__security_cookie
0x14007ea8c  xor     rax, rsp
0x14007ea8f  mov     [rbp+50h+var_48], rax
0x14007ea93  mov     r13, rcx
0x14007ea96  mov     qword ptr [rbp+50h+DestinationString.Length], rcx
0x14007ea9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eaa1  lea     r15, WPP_GLOBAL_Control
0x14007eaa8  xor     r12d, r12d
0x14007eaab  lea     esi, [r12+1]
0x14007eab0  cmp     rcx, r15
0x14007eab3  jz      short loc_14007EAC7
0x14007eab5  test    dword ptr [rcx+2Ch], 40000h
0x14007eabc  jz      short loc_14007EAC7
0x14007eabe  cmp     byte ptr [rcx+29h], 4
0x14007eac2  mov     dl, sil
0x14007eac5  jnb     short loc_14007EACA
0x14007eac7  mov     dl, r12b
0x14007eaca  lea     rbx, WPP_RECORDER_INITIALIZED
0x14007ead1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14007ead8  lea     rdi, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14007eadf  setnz   r8b
0x14007eae3  test    dl, dl
0x14007eae5  jnz     short loc_14007EAEC
0x14007eae7  test    r8b, r8b
0x14007eaea  jz      short loc_14007EB17
0x14007eaec  mov     r9, [rcx+40h]
0x14007eaf0  mov     rcx, [rcx+18h]
0x14007eaf4  mov     [rsp+150h+var_110], r13
0x14007eaf9  mov     [rsp+150h+var_118], rdi
0x14007eafe  mov     word ptr [rsp+150h+var_120], 34h ; '4'
0x14007eb05  mov     [rsp+150h+var_128], 13h
0x14007eb0d  mov     byte ptr [rsp+150h+var_130], 4
0x14007eb12  call    WPP_RECORDER_AND_TRACE_SF_q
0x14007eb17  lea     rcx, [r13+268h]
0x14007eb1e  lea     rdx, [rbp+50h+var_B8]
0x14007eb22  call    ?lock@?$weak_ptr@VBtaMpmContext@@@utl@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@2@XZ; utl::weak_ptr<BtaMpmContext>::lock(void)
0x14007eb27  lea     rcx, [rbp+50h+var_B8]
0x14007eb2b  call    ??$?8VA2dpSidebandAudioWdmDevice@@@utl@@YA_NAEBV?$shared_ptr@VA2dpSidebandAudioWdmDevice@@@0@$$T@Z; utl::operator==<A2dpSidebandAudioWdmDevice>(utl::shared_ptr<A2dpSidebandAudioWdmDevice> const &,std::nullptr_t)
0x14007eb30  test    al, al
0x14007eb32  jz      short loc_14007EBA7
0x14007eb34  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eb3b  mov     r14d, 2
0x14007eb41  cmp     rcx, r15
0x14007eb44  jz      short loc_14007EB55
0x14007eb46  test    dword ptr [rcx+2Ch], 20000h
0x14007eb4d  jz      short loc_14007EB55
0x14007eb4f  cmp     [rcx+29h], r14b
0x14007eb53  jnb     short loc_14007EB58
0x14007eb55  mov     sil, r12b
0x14007eb58  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14007eb5f  setnz   r8b
0x14007eb63  test    sil, sil
0x14007eb66  jnz     short loc_14007EB71
0x14007eb68  test    r8b, r8b
0x14007eb6b  jz      loc_14007EDF0
0x14007eb71  mov     dword ptr [rsp+150h+var_110], 0C0000184h
0x14007eb79  mov     [rsp+150h+var_118], rdi
0x14007eb7e  mov     word ptr [rsp+150h+var_120], 35h ; '5'
0x14007eb85  mov     r9, [rcx+40h]
0x14007eb89  mov     dl, sil
0x14007eb8c  mov     rcx, [rcx+18h]
0x14007eb90  mov     [rsp+150h+var_128], 12h
0x14007eb98  mov     byte ptr [rsp+150h+var_130], r14b
0x14007eb9d  call    WPP_RECORDER_AND_TRACE_SF_d
0x14007eba2  jmp     loc_14007EDF0
0x14007eba7  mov     rax, [rbp+50h+var_B8]
0x14007ebab  mov     r14, [rax+1E8h]
0x14007ebb2  mov     [rsp+150h+var_D8], r14
0x14007ebb7  test    r14, r14
0x14007ebba  jnz     short loc_14007EC12
0x14007ebbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ebc3  mov     r14d, 2
0x14007ebc9  cmp     rcx, r15
0x14007ebcc  jz      short loc_14007EBDD
0x14007ebce  test    dword ptr [rcx+2Ch], 20000h
0x14007ebd5  jz      short loc_14007EBDD
0x14007ebd7  cmp     [rcx+29h], r14b
0x14007ebdb  jnb     short loc_14007EBE0
0x14007ebdd  mov     sil, r12b
0x14007ebe0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14007ebe7  setnz   r8b
0x14007ebeb  test    sil, sil
0x14007ebee  jnz     short loc_14007EBF9
0x14007ebf0  test    r8b, r8b
0x14007ebf3  jz      loc_14007EDF0
0x14007ebf9  mov     dword ptr [rsp+150h+var_110], 0C0000184h
0x14007ec01  mov     [rsp+150h+var_118], rdi
0x14007ec06  mov     word ptr [rsp+150h+var_120], 36h ; '6'
0x14007ec0d  jmp     loc_14007EB85
0x14007ec12  movups  xmm0, cs:SIDEBANDAUDIO_PARAMS_SET_A2DP
0x14007ec19  mov     rcx, [r13+18h]
0x14007ec1d  lea     r8, [rbp+50h+var_98]
0x14007ec21  mov     [rbp+50h+var_50], esi
0x14007ec24  lea     rdx, [rbp+50h+var_60]
0x14007ec28  movdqu  [rbp+50h+var_60], xmm0
0x14007ec2d  mov     [rbp+50h+var_98], r12
0x14007ec31  mov     rbx, r12
0x14007ec34  mov     rax, [rcx]
0x14007ec37  mov     rdi, r12
0x14007ec3a  mov     [rsp+150h+var_E8], rbx
0x14007ec3f  mov     [rsp+150h+var_E0], r12
0x14007ec44  mov     rax, [rax+10h]
0x14007ec48  call    _guard_dispatch_icall
0x14007ec4d  test    eax, eax
0x14007ec4f  js      loc_14007ED56
0x14007ec55  mov     rdx, [rbp+50h+var_98]
0x14007ec59  lea     rcx, [rbp+50h+var_D0]
0x14007ec5d  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x14007ec62  mov     rdx, rax
0x14007ec65  lea     rcx, [rsp+150h+var_E0]
0x14007ec6a  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::operator=(utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &&)
0x14007ec6f  lea     rcx, [rbp+50h+var_D0]
0x14007ec73  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x14007ec78  mov     rcx, [r13+18h]
0x14007ec7c  lea     rdx, [rbp+50h+var_60]
0x14007ec80  mov     rdi, [rsp+150h+var_E0]
0x14007ec85  mov     r8, [rbp+50h+var_98]
0x14007ec89  mov     r9, rdi
0x14007ec8c  mov     [rsp+150h+var_130], r12
0x14007ec91  mov     rax, [rcx]
0x14007ec94  mov     rax, [rax+8]
0x14007ec98  call    _guard_dispatch_icall
0x14007ec9d  mov     r15d, eax
0x14007eca0  test    eax, eax
0x14007eca2  jns     loc_14007ED4F
0x14007eca8  mov     r10, cs:WPP_GLOBAL_Control
0x14007ecaf  lea     rax, WPP_GLOBAL_Control
0x14007ecb6  mov     r14d, 2
0x14007ecbc  cmp     r10, rax
0x14007ecbf  jz      short loc_14007ECD1
0x14007ecc1  test    dword ptr [r10+2Ch], 20000h
0x14007ecc9  jz      short loc_14007ECD1
0x14007eccb  cmp     [r10+29h], r14b
0x14007eccf  jnb     short loc_14007ECD4
0x14007ecd1  mov     sil, r12b
0x14007ecd4  lea     rax, WPP_RECORDER_INITIALIZED
0x14007ecdb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ece2  setnz   r8b
0x14007ece6  test    sil, sil
0x14007ece9  jnz     short loc_14007ECF0
0x14007eceb  test    r8b, r8b
0x14007ecee  jz      short loc_14007ED25
0x14007ecf0  mov     rcx, [r10+18h]
0x14007ecf4  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14007ecfb  mov     dword ptr [rsp+150h+var_110], r15d
0x14007ed00  mov     dl, sil
0x14007ed03  mov     [rsp+150h+var_118], r9
0x14007ed08  mov     r9, [r10+40h]
0x14007ed0c  mov     word ptr [rsp+150h+var_120], 37h ; '7'
0x14007ed13  mov     [rsp+150h+var_128], 12h
0x14007ed1b  mov     byte ptr [rsp+150h+var_130], r14b
0x14007ed20  call    WPP_RECORDER_AND_TRACE_SF_d
0x14007ed25  lea     rcx, [rsp+150h+var_E0]
0x14007ed2a  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x14007ed2f  lea     rcx, [rsp+150h+var_E8]
0x14007ed34  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x14007ed39  mov     rcx, [rbp+50h+var_B0]; this
0x14007ed3d  test    rcx, rcx
0x14007ed40  jz      short loc_14007ED47
0x14007ed42  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14007ed47  mov     eax, r15d
0x14007ed4a  jmp     loc_14007F7F3
0x14007ed4f  lea     r15, WPP_GLOBAL_Control
0x14007ed56  lea     rax, [r14+0DC8h]
0x14007ed5d  test    rax, rax
0x14007ed60  jnz     loc_14007EE08
0x14007ed66  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ed6d  lea     r14d, [rax+2]
0x14007ed71  cmp     rcx, r15
0x14007ed74  jz      short loc_14007ED85
0x14007ed76  test    dword ptr [rcx+2Ch], 20000h
0x14007ed7d  jz      short loc_14007ED85
0x14007ed7f  cmp     [rcx+29h], r14b
0x14007ed83  jnb     short loc_14007ED88
0x14007ed85  mov     sil, r12b
0x14007ed88  lea     rax, WPP_RECORDER_INITIALIZED
0x14007ed8f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ed96  setnz   r8b
0x14007ed9a  test    sil, sil
0x14007ed9d  jnz     short loc_14007EDA4
0x14007ed9f  test    r8b, r8b
0x14007eda2  jz      short loc_14007EDDC
0x14007eda4  mov     dword ptr [rsp+150h+var_110], 0C0000184h
0x14007edac  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14007edb3  mov     [rsp+150h+var_118], r9
0x14007edb8  mov     dl, sil
0x14007edbb  mov     r9, [rcx+40h]
0x14007edbf  mov     rcx, [rcx+18h]
0x14007edc3  mov     word ptr [rsp+150h+var_120], 38h ; '8'
0x14007edca  mov     [rsp+150h+var_128], 12h
0x14007edd2  mov     byte ptr [rsp+150h+var_130], r14b
0x14007edd7  call    WPP_RECORDER_AND_TRACE_SF_d
0x14007eddc  lea     rcx, [rsp+150h+var_E0]
0x14007ede1  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x14007ede6  lea     rcx, [rsp+150h+var_E8]
0x14007edeb  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x14007edf0  mov     rcx, [rbp+50h+var_B0]; this
0x14007edf4  test    rcx, rcx
0x14007edf7  jz      short loc_14007EDFE
0x14007edf9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14007edfe  mov     eax, 0C0000184h
0x14007ee03  jmp     loc_14007F7F3
0x14007ee08  mov     rax, [rax+20h]
0x14007ee0c  mov     edx, 50444141h
0x14007ee11  mov     ecx, 0C501h
0x14007ee16  call    _guard_dispatch_icall
0x14007ee1b  mov     [rbp+50h+var_C0], rax
0x14007ee1f  mov     r15, rax
0x14007ee22  test    rax, rax
0x14007ee25  jnz     loc_14007EECC
0x14007ee2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ee32  lea     r14d, [rax+2]
0x14007ee36  lea     rax, WPP_GLOBAL_Control
0x14007ee3d  cmp     rcx, rax
0x14007ee40  jz      short loc_14007EE51
0x14007ee42  test    dword ptr [rcx+2Ch], 20000h
0x14007ee49  jz      short loc_14007EE51
0x14007ee4b  cmp     [rcx+29h], r14b
0x14007ee4f  jnb     short loc_14007EE54
0x14007ee51  mov     sil, r12b
0x14007ee54  lea     rax, WPP_RECORDER_INITIALIZED
0x14007ee5b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ee62  setnz   r8b
0x14007ee66  test    sil, sil
0x14007ee69  jnz     short loc_14007EE70
0x14007ee6b  test    r8b, r8b
0x14007ee6e  jz      short loc_14007EEA0
0x14007ee70  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14007ee77  mov     dl, sil
0x14007ee7a  mov     [rsp+150h+var_118], r9
0x14007ee7f  mov     r9, [rcx+40h]
0x14007ee83  mov     rcx, [rcx+18h]
0x14007ee87  mov     word ptr [rsp+150h+var_120], 39h ; '9'
0x14007ee8e  mov     [rsp+150h+var_128], 12h
0x14007ee96  mov     byte ptr [rsp+150h+var_130], r14b
0x14007ee9b  call    WPP_RECORDER_AND_TRACE_SF_
0x14007eea0  lea     rcx, [rsp+150h+var_E0]
0x14007eea5  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x14007eeaa  lea     rcx, [rsp+150h+var_E8]
0x14007eeaf  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x14007eeb4  mov     rcx, [rbp+50h+var_B0]; this
0x14007eeb8  test    rcx, rcx
0x14007eebb  jz      short loc_14007EEC2
0x14007eebd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14007eec2  mov     eax, 0C000009Ah
0x14007eec7  jmp     loc_14007F7F3
0x14007eecc  lea     rcx, [rbp+50h+var_78]
0x14007eed0  call    ??0?$vector@V?$shared_ptr@VA2dpAudioCodec@@@utl@@V?$allocator@V?$shared_ptr@VA2dpAudioCodec@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<A2dpAudioCodec>,utl::allocator<utl::shared_ptr<A2dpAudioCodec>>>::vector<utl::shared_ptr<A2dpAudioCodec>,utl::allocator<utl::shared_ptr<A2dpAudioCodec>>>(void)
0x14007eed5  mov     rdx, [rbp+50h+var_98]
0x14007eed9  mov     r8, rdi
0x14007eedc  mov     r14d, 2
0x14007eee2  test    rdx, rdx
0x14007eee5  jz      loc_14007EF7C
0x14007eeeb  movzx   ecx, byte ptr [r8+1]
0x14007eef0  lea     r8, [r8+2]
0x14007eef4  mov     rax, 0FFFFFFFFFFFFFFFEh
0x14007eefb  add     r12b, sil
0x14007eefe  sub     rax, rcx
0x14007ef01  lea     r8, [r8+rcx]
0x14007ef05  add     rdx, rax
0x14007ef08  jnz     short loc_14007EEEB
0x14007ef0a  test    r12b, r12b
0x14007ef0d  jz      short loc_14007EF7C
0x14007ef0f  movzx   edx, r12b
0x14007ef13  lea     rcx, [rbp+50h+var_D0]
0x14007ef17  call    ??$make_unique@$$BY0A@U_AVDTP_CODEC_CAPABILITY@@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@U_AVDTP_CODEC_CAPABILITY@@U?$default_delete@$$BY0A@U_AVDTP_CODEC_CAPABILITY@@@utl@@@0@_K@Z; utl::make_unique<_AVDTP_CODEC_CAPABILITY [0],0>(unsigned __int64)
0x14007ef1c  mov     rdx, rax
0x14007ef1f  lea     rcx, [rsp+150h+var_E8]
0x14007ef24  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::operator=(utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &&)
0x14007ef29  lea     rcx, [rbp+50h+var_D0]
0x14007ef2d  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x14007ef32  mov     rbx, [rsp+150h+var_E8]
0x14007ef37  xor     ecx, ecx
0x14007ef39  test    r12b, r12b
0x14007ef3c  jz      short loc_14007EF7C
0x14007ef3e  mov     r13d, ecx
0x14007ef41  movzx   r15d, r12b
0x14007ef45  movzx   r8d, byte ptr [rdi+1]
0x14007ef4a  mov     rdx, rdi; Src
0x14007ef4d  mov     eax, r13d
0x14007ef50  add     r8, r14; Size
0x14007ef53  imul    rcx, rax, 84h
0x14007ef5a  add     rcx, rbx; void *
0x14007ef5d  call    memmove
0x14007ef62  movzx   eax, byte ptr [rdi+1]
0x14007ef66  add     r13d, esi
0x14007ef69  add     rdi, r14
0x14007ef6c  add     rdi, rax
0x14007ef6f  cmp     r13d, r15d
0x14007ef72  jl      short loc_14007EF45
  ... truncated ...
```
