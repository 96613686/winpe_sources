# FSClientContextInfo::InternalInitialize(IDeviceAccessHandler *,IMFAttributes *)

- ea: `0x180077014`
- end: `0x180077dbd`
- name: `?InternalInitialize@FSClientContextInfo@@IEAAJPEAUIDeviceAccessHandler@@PEAUIMFAttributes@@@Z`
- size: `3497`
- prototype: `__int64 __fastcall(FSClientContextInfo *__hidden this, struct IDeviceAccessHandler *, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `36`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180076828`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180007c10`
- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x18000a648`
- `0x1800175bc`
- `0x180017858`
- `0x180017ab8`
- `0x180017f60`
- `0x18001807c`
- `0x180018998`
- `0x180018a14`
- `0x180022da0`
- `0x180024200`
- `0x1800285cc`
- `0x18002a0ec`
- `0x18002a230`
- `0x180030dd0`
- `0x18004d714`
- `0x18004d748`
- `0x18004dae4`
- `0x18004db10`
- `0x180076340`
- `0x1800763f0`
- `0x180076428`
- `0x180076584`
- `0x180077014`
- `0x180078234`
- `0x1800792f8`
- `0x18007b8ac`
- `0x18007bde8`
- `0x18007beb8`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800770c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800770c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007749c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007749c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180077863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180077863`

## string_xrefs

- `0x180077407`: `CountOfFramesToWaitForConfig`
- `0x180077479`: `CountOfFramesToWaitForConfig`

## pseudocode

```c
__int64 __fastcall FSClientContextInfo::InternalInitialize(
        FSClientContextInfo *this,
        struct IDeviceAccessHandler *a2,
        struct IMFAttributes *a3)
{
  int v3; // r14d
  struct IDeviceAccessHandler *v4; // r15
  FSClientContextInfo *v5; // r13
  __int16 v7; // ax
  int v8; // eax
  int v9; // eax
  int v10; // esi
  __int64 v11; // rdx
  FSClientContextInfo *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct IDeviceAccessHandler *, __int64 *, __int64 **); // rbx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rbx
  char v19; // si
  int (__fastcall *v20)(__int64, const IID *, LPCWSTR *, int *); // rdi
  unsigned int v21; // r9d
  __int64 v22; // rax
  __int64 v23; // rax
  const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *v24; // r12
  __int64 v25; // rax
  void *v26; // rcx
  __int64 (__fastcall *v27)(struct IDeviceAccessHandler *, __int64 *, __int64 **); // rbx
  __int64 v28; // rax
  LPCWSTR v29; // rax
  int v30; // ebx
  FSString *v31; // rax
  const char *String; // rax
  LPCWSTR v33; // rbx
  __int64 v34; // rbx
  __int64 v35; // rbx
  __int64 v36; // rbx
  __int128 *v37; // rbx
  bool v38; // zf
  void (__fastcall *v39)(__int64 *, void *, __int128 *, __int64, int *); // rax
  bool v40; // al
  char *v41; // rcx
  __int128 v42; // xmm1
  __int64 v43; // xmm0_8
  __int128 v44; // xmm6
  __int128 v45; // xmm7
  __int64 v46; // rcx
  void *v47; // rax
  void *v48; // rbx
  _QWORD *v49; // rax
  int v50; // ebx
  int v51; // edi
  int v52; // esi
  int v53; // r14d
  int v54; // r15d
  int v55; // r12d
  int v56; // r13d
  __int64 v57; // rax
  __int64 v58; // rax
  int v59; // eax
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 (__fastcall *v63)(struct IDeviceAccessHandler *, LPCWSTR *, __int64 **); // rbx
  int v64; // eax
  _QWORD *v65; // rax
  LPCWSTR v66; // rbx
  int (__fastcall *v67)(LPCWSTR, const IID *, unsigned __int16 **, __int64 *); // rdi
  FSString *v68; // rax
  const char *v69; // rbx
  FSString *v70; // rax
  const char *v71; // rax
  int v72; // r8d
  const char *v73; // rcx
  __int64 v74; // rdx
  LPDWORD pdwType; // [rsp+28h] [rbp-F0h]
  unsigned int *pvData; // [rsp+30h] [rbp-E8h]
  LPDWORD pcbData; // [rsp+38h] [rbp-E0h]
  __int64 v79; // [rsp+98h] [rbp-80h] BYREF
  LPCWSTR pszDeviceInterface; // [rsp+A0h] [rbp-78h] BYREF
  FSClientContextInfo *v81; // [rsp+A8h] [rbp-70h]
  __int64 *v82; // [rsp+B0h] [rbp-68h] BYREF
  BYTE Data[4]; // [rsp+B8h] [rbp-60h] BYREF
  int v84; // [rsp+BCh] [rbp-5Ch]
  int v85; // [rsp+C0h] [rbp-58h] BYREF
  char v86[8]; // [rsp+C8h] [rbp-50h] BYREF
  unsigned int v87; // [rsp+D0h] [rbp-48h] BYREF
  unsigned __int16 *v88; // [rsp+D8h] [rbp-40h] BYREF
  int v89; // [rsp+E0h] [rbp-38h] BYREF
  DWORD v90; // [rsp+E4h] [rbp-34h] BYREF
  int v91; // [rsp+E8h] [rbp-30h]
  int v92; // [rsp+ECh] [rbp-2Ch]
  int v93; // [rsp+F0h] [rbp-28h]
  int v94; // [rsp+F4h] [rbp-24h]
  LPCWSTR v95; // [rsp+F8h] [rbp-20h] BYREF
  char *v96; // [rsp+100h] [rbp-18h]
  struct IDeviceAccessHandler *v97; // [rsp+108h] [rbp-10h]
  _BYTE v98[24]; // [rsp+110h] [rbp-8h] BYREF
  __int128 v99; // [rsp+128h] [rbp+10h] BYREF
  __int128 v100; // [rsp+138h] [rbp+20h]
  __int64 v101; // [rsp+148h] [rbp+30h]
  __int64 v102; // [rsp+160h] [rbp+48h]

  v3 = 0;
  v97 = a2;
  v4 = a2;
  v81 = this;
  v5 = this;
  v84 = 0;
  v89 = 0;
  v95 = 0;
  wil::com_ptr_t<IMFMediaType,wil::err_returncode_policy>::com_ptr_t<IMFMediaType,wil::err_returncode_policy>(&v82, a3);
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 37, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v5);
  v7 = _InterlockedExchangeAdd(&dword_18010EE9C, 1u);
  *((_DWORD *)v5 + 15) &= 0xFFF00000;
  *((_DWORD *)v5 + 15) |= (unsigned __int16)(v7 + 1);
  *((_DWORD *)v5 + 14) = GetCurrentProcessId();
  *((_DWORD *)v5 + 16) = (*(__int64 (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 72LL))(v4);
  v8 = (*(__int64 (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 96LL))(v4);
  *((_DWORD *)v5 + 17) &= ~8u;
  *((_DWORD *)v5 + 17) |= v8 != 0 ? 8 : 0;
  *((_DWORD *)v5 + 17) = *((_DWORD *)v5 + 17) & 0xFFFFFFDF
                       | ((*(unsigned int (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 104LL))(v4) != 0
                        ? 0x20
                        : 0);
  *((_DWORD *)v5 + 17) = *((_DWORD *)v5 + 17) & 0xFFFFFFBF
                       | ((*(unsigned int (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 112LL))(v4) != 0
                        ? 0x40
                        : 0);
  *((_DWORD *)v5 + 17) = *((_DWORD *)v5 + 17) & 0xFFFFFF7F
                       | ((*(unsigned int (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 128LL))(v4) != 0
                        ? 0x80
                        : 0);
  *((_DWORD *)v5 + 17) = *((_DWORD *)v5 + 17) & 0xFFFFFDFF
                       | ((*(unsigned int (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 136LL))(v4) != 0
                        ? 0x200
                        : 0);
  v9 = (*(__int64 (__fastcall **)(struct IDeviceAccessHandler *, __int64, int *))(*(_QWORD *)v4 + 64LL))(
         v4,
         (__int64)v5 + 72,
         &v89);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
    {
LABEL_7:
      v12 = v5;
      goto LABEL_92;
    }
    v11 = 38;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v5, v9);
    goto LABEL_7;
  }
  if ( a3 )
  {
    *((_DWORD *)v5 + 17) = *((_DWORD *)v5 + 17) & 0xFFFFFFFD
                         | ((unsigned int)MFGetAttributeUINT32(a3, &MF_FRAMESERVER_VCAM_CONFIGURATION_APP, 0) != 0
                          ? 2
                          : 0);
    *((_DWORD *)v5 + 17) = *((_DWORD *)v5 + 17) & 0xFFFFFFEF
                         | ((unsigned int)MFGetAttributeUINT32(a3, &MF_FRAMESERVER_BLOCK_SAME_PROCESS_PREEMPTION, 0) != 0
                          ? 0x10
                          : 0);
    *((_DWORD *)v5 + 17) = *((_DWORD *)v5 + 17) & 0xFFFFFBFF
                         | ((unsigned int)MFGetAttributeUINT32(a3, &MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS, 0) != 0
                          ? 0x400
                          : 0);
    *((_DWORD *)v5 + 17) = *((_DWORD *)v5 + 17) & 0xFFFFF7FF
                         | ((unsigned int)MFGetAttributeUINT32(
                                            a3,
                                            &MF_VIRTUALCAMERA_PROVIDE_ASSOCIATED_CAMERA_SOURCES,
                                            0) != 0
                          ? 0x800
                          : 0);
  }
  *((_QWORD *)v5 + 11) = 0;
  if ( (*((_BYTE *)v5 + 68) & 0x80) == 0 )
    *((_DWORD *)v5 + 17) = *((_DWORD *)v5 + 17) & 0xFFFFFF7F
                         | ((*(unsigned int (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 152LL))(v4) != 0
                          ? 0x80
                          : 0);
  *((_DWORD *)v5 + 36) = (*(__int64 (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 144LL))(v4);
  if ( (*(__int64 (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 88LL))(v4) )
  {
    v13 = (*(__int64 (__fastcall **)(struct IDeviceAccessHandler *))(*(_QWORD *)v4 + 88LL))(v4);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             (char *)v5 + 152,
                             v13) )
    {
      v9 = -2147024882;
      v10 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_7;
      v11 = 39;
      goto LABEL_6;
    }
  }
  v14 = *(_QWORD *)v4;
  *(_DWORD *)Data = 0;
  v90 = 4;
  v79 = 0;
  v15 = *(__int64 (__fastcall **)(struct IDeviceAccessHandler *, __int64 *, __int64 **))(v14 + 80);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v82);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v79);
  v16 = v15(v4, &v79, &v82);
  v10 = v16;
  if ( v16 < 0 )
  {
    if ( !g_wppLevels )
    {
LABEL_20:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v79);
      goto LABEL_7;
    }
    v17 = 40;
LABEL_19:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v5, v16);
    goto LABEL_20;
  }
  v18 = v79;
  if ( !v79 )
    goto LABEL_102;
  pszDeviceInterface = 0;
  v85 = 0;
  v19 = 0;
  v20 = *(int (__fastcall **)(__int64, const IID *, LPCWSTR *, int *))(*(_QWORD *)v79 + 104LL);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &pszDeviceInterface,
    0);
  if ( v20(v18, &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK, &pszDeviceInterface, &v85) >= 0 )
  {
    v87 = 0;
    if ( (int)FSGetDeviceInterfaceRegistryEntry2(
                pszDeviceInterface,
                L"CountOfFramesToWaitForConfig",
                Data,
                v21,
                &v87,
                pvData) >= 0 )
    {
      v22 = *(unsigned int *)Data;
      if ( *(_DWORD *)Data )
      {
        *((_QWORD *)v5 + 33) = *(unsigned int *)Data;
        v19 = 1;
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
          WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 27), 41, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v5, v22);
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszDeviceInterface);
  if ( !v19 )
  {
LABEL_102:
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer",
            L"CountOfFramesToWaitForConfig",
            0x10u,
            0,
            Data,
            &v90) )
    {
      v23 = *(unsigned int *)Data;
      if ( *(_DWORD *)Data )
      {
        *((_QWORD *)v5 + 33) = *(unsigned int *)Data;
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
          WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 27), 42, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v5, v23);
      }
    }
  }
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v79);
  v24 = (FSClientContextInfo *)((char *)v5 + 184);
  v79 = 0;
  *((_QWORD *)v5 + 23) = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::start_and_watch_errors(
    &v79,
    &v99);
  wil::com_ptr_t<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>,wil::err_returncode_policy>(&v79);
  v25 = v102;
  v26 = (void *)*((_QWORD *)v5 + 29);
  v96 = (char *)v5 + 232;
  *((_QWORD *)v5 + 29) = v102;
  if ( v25 )
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 352));
  if ( v26 )
    tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>::Release(v26);
  tip2::test_watcher<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_watcher<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v99);
  v79 = 0;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v82);
  v27 = *(__int64 (__fastcall **)(struct IDeviceAccessHandler *, __int64 *, __int64 **))(*(_QWORD *)v4 + 80LL);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v82);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v79);
  v16 = v27(v4, &v79, &v82);
  v10 = v16;
  if ( v16 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_20;
    v17 = 44;
    goto LABEL_19;
  }
  if ( v82 && (*((_DWORD *)v5 + 17) & 0x200) == 0 )
  {
    v28 = *v82;
    pszDeviceInterface = 0;
    v29 = (*(int (__fastcall **)(__int64 *, void *, LPCWSTR *))(v28 + 64))(
            v82,
            &MF_FRAMESERVER_MANAGED_CAMERA_MODE,
            &pszDeviceInterface) >= 0
        ? pszDeviceInterface
        : 0LL;
    v95 = v29;
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                            (char *)v5 + 232,
                            &pszDeviceInterface)
             + 276LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&pszDeviceInterface);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraManagedModePolicy>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CameraManagedModePolicy>::GetImpl'::`2'::impl) )
    {
      v30 = MFGetAttributeUINT32(v82, &MF_FRAMESERVER_MANAGED_CAMERA_MODE_POLICY_ENABLED, 0);
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                              (char *)v5 + 232,
                              &pszDeviceInterface)
               + 277LL) = v30 != 0;
      tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&pszDeviceInterface);
    }
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v3 = 2;
    v84 = 2;
    v31 = ManagedModeTrace::ManagedModeTrace(
            (ManagedModeTrace *)v98,
            (const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *)&v95);
    String = FSString::GetString(v31);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      45,
      (unsigned int)&WPP_9bb944463e3039875071016bf2e24787_Traceguids,
      (_DWORD)v5,
      (__int64)String);
  }
  if ( (v3 & 2) != 0 )
  {
    v3 &= ~2u;
    v84 = v3;
    FSString::~FSString((FSString *)v98);
  }
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v79);
  v33 = v95;
  *(_QWORD *)v24 = v95;
  *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                           (char *)v5 + 232,
                           &v79)
            + 296LL) = v33;
  tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v79);
  v34 = *(_QWORD *)v24 & 4LL;
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                          (char *)v5 + 232,
                          &v79)
           + 278LL) = v34 != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v79);
  v35 = *(_QWORD *)v24 & 2LL;
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                          (char *)v5 + 232,
                          &v79)
           + 279LL) = v35 != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v79);
  v36 = *(_QWORD *)v24 & 1LL;
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                          (char *)v5 + 232,
                          &v79)
           + 280LL) = v36;
  tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v79);
  v37 = (__int128 *)((char *)v5 + 192);
  *((_OWORD *)v5 + 12) = 0;
  *((_OWORD *)v5 + 13) = 0;
  *((_QWORD *)v5 + 28) = 0;
  if ( !v82 || (*(_BYTE *)v24 & 5) == 0 )
  {
LABEL_69:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl)
      && v82 )
    {
      v59 = MFGetAttributeUINT32(v82, &MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS, 0);
      v61 = *((_DWORD *)v5 + 17) & 0xFFFFFBFF | (v59 != 0 ? 0x400 : 0);
      *((_DWORD *)v5 + 17) = v61;
      if ( !v59 )
      {
        v62 = *(_QWORD *)v4;
        pszDeviceInterface = 0;
        v63 = *(__int64 (__fastcall **)(struct IDeviceAccessHandler *, LPCWSTR *, __int64 **))(v62 + 80);
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v82);
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&pszDeviceInterface);
        v64 = v63(v4, &pszDeviceInterface, &v82);
        v10 = v64;
        if ( v64 < 0 )
        {
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              &WPP_9bb944463e3039875071016bf2e24787_Traceguids,
              v5,
              v64);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&pszDeviceInterface);
LABEL_91:
          v12 = v81;
          goto LABEL_92;
        }
        v66 = pszDeviceInterface;
        if ( pszDeviceInterface )
        {
          v88 = 0;
          LODWORD(v79) = 0;
          v67 = *(int (__fastcall **)(LPCWSTR, const IID *, unsigned __int16 **, __int64 *))(*(_QWORD *)pszDeviceInterface
                                                                                           + 104LL);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
            &v88,
            0);
          if ( v67(v66, &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK, &v88, &v79) >= 0
            && !FSIsOEMOptInForWindowsEffects(v88) )
          {
            *(_QWORD *)v24 |= 2uLL;
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v88);
        }
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&pszDeviceInterface);
      }
      if ( (unsigned __int8)byte_18010EC4D < 8u )
      {
LABEL_87:
        if ( (v3 & 0x10) != 0 )
        {
          LOBYTE(v3) = v3 & 0xEF;
          FSString::~FSString((FSString *)v98);
        }
        if ( (v3 & 8) != 0 )
          FSString::~FSString((FSString *)&v99);
        goto LABEL_91;
      }
      WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 27), v61, v60, v5, (*((_DWORD *)v5 + 17) >> 10) & 1);
    }
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v68 = ManagedModeTrace::ManagedModeTrace((ManagedModeTrace *)&v99, (FSClientContextInfo *)((char *)v5 + 192));
      v69 = FSString::GetString(v68);
      LOBYTE(v3) = v3 | 0x18;
      v70 = ManagedModeTrace::ManagedModeTrace((ManagedModeTrace *)v98, v24);
      v71 = FSString::GetString(v70);
      WPP_SF_qss(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v71, (__int64)v69);
    }
    goto LABEL_87;
  }
  v85 = 0;
  v99 = 0;
  v101 = 0;
  v100 = 0;
  v38 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2602>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CameraQI2602>::GetImpl'::`2'::impl) == 0;
  v39 = *(void (__fastcall **)(__int64 *, void *, __int128 *, __int64, int *))(*v82 + 120);
  if ( v38 )
  {
    v39(v82, &MF_FRAMESERVER_MANAGED_CAMERA_SELECTED_MEDIA, &v99, 40, &v85);
  }
  else if ( ((int (__fastcall *)(__int64 *, void *, __int128 *, __int64, int *))v39)(
              v82,
              &MF_FRAMESERVER_MANAGED_CAMERA_SELECTED_MEDIA,
              &v99,
              40,
              &v85) >= 0 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                            (char *)v5 + 232,
                            &v79)
             + 281LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v79);
  }
  v40 = FSIsSelectedMediaInfoValid((const struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011 *)&v99);
  v41 = (char *)v5 + 232;
  if ( !v40 )
  {
    v65 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                      v41,
                      v86);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      *v65 + 304LL,
      0);
    tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(v86);
    *(GUID *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                           (char *)v5 + 232,
                           v86)
            + 320LL) = GUID_00000000_0000_0000_0000_000000000000;
    tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(v86);
    goto LABEL_69;
  }
  v42 = v100;
  *v37 = v99;
  v43 = v101;
  *((_OWORD *)v5 + 13) = v42;
  *((_QWORD *)v5 + 28) = v43;
  v44 = *v37;
  v45 = *((_OWORD *)v5 + 13);
  v46 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                     v41,
                     &v79);
  *(_OWORD *)(v46 + 312) = v44;
  *(_OWORD *)(v46 + 328) = v45;
  *(_QWORD *)(v46 + 344) = v43;
  tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v79);
  v47 = CoTaskMemAlloc(0xA8u);
  v48 = v47;
  if ( !v47 )
  {
    v9 = -2147024882;
    v10 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_7;
    v11 = 46;
    goto LABEL_6;
  }
  memset_0(v47, 0, 0xA8u);
  v49 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                    (char *)v5 + 232,
                    &v79);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    *v49 + 304LL,
    v48);
  tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v79);
  v50 = *((_DWORD *)v5 + 57);
  v51 = *((_DWORD *)v5 + 56);
  v52 = *((_DWORD *)v5 + 55);
  v53 = *((_DWORD *)v5 + 54);
  v54 = *((unsigned __int8 *)v5 + 215);
  v55 = *((unsigned __int8 *)v5 + 214);
  v56 = *((unsigned __int8 *)v5 + 213);
  v87 = *((unsigned __int8 *)v81 + 212);
  v91 = *((unsigned __int8 *)v81 + 211);
  v92 = *((unsigned __int8 *)v81 + 210);
  v93 = *((unsigned __int8 *)v81 + 209);
  v94 = *((unsigned __int8 *)v81 + 208);
  LODWORD(v88) = *((unsigned __int16 *)v81 + 103);
  LODWORD(pszDeviceInterface) = *((unsigned __int16 *)v81 + 102);
  LODWORD(v79) = *((_DWORD *)v81 + 50);
  v57 = tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
          v96,
          v86);
  LODWORD(pcbData) = v94;
  LODWORD(pvData) = (_DWORD)v88;
  LODWORD(pdwType) = (_DWORD)pszDeviceInterface;
  v10 = StringCchPrintfW(
          *(unsigned __int16 **)(*(_QWORD *)v57 + 304LL),
          0x54u,
          L"{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X},%dx%d,%d/%d",
          (unsigned int)v79,
          pdwType,
          pvData,
          pcbData,
          v93,
          v92,
          v91,
          v87,
          v56,
          v55,
          v54,
          v53,
          v52,
          v51,
          v50);
  tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(v86);
  if ( v10 >= 0 )
  {
    LOBYTE(v3) = v84;
    if ( (unsigned __int8)byte_18010EC4D < 8u )
    {
      v5 = v81;
    }
    else
    {
      LOBYTE(v3) = v84 | 4;
      v58 = tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
              v96,
              v86);
      v5 = v81;
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        48,
        (unsigned int)&WPP_9bb944463e3039875071016bf2e24787_Traceguids,
        (_DWORD)v81,
        *(_QWORD *)(*(_QWORD *)v58 + 304LL));
    }
    if ( (v3 & 4) != 0 )
    {
      LOBYTE(v3) = v3 & 0xFB;
      tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(v86);
    }
    v4 = v97;
    v24 = (FSClientContextInfo *)((char *)v5 + 184);
    goto LABEL_69;
  }
  v12 = v81;
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v81, v10);
LABEL_92:
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                           (char *)v12 + 232,
                           v86)
            + 272LL) = v10;
  tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(v86);
  if ( v10 >= 0 )
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v73 = L"<nullptr>";
      v74 = *((_QWORD *)v12 + 33);
      if ( *((_QWORD *)v12 + 19) )
        v73 = (const char *)*((_QWORD *)v12 + 19);
      WPP_SF_qDiSi(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v74,
        v72,
        (_DWORD)v12,
        v10,
        *((_QWORD *)v12 + 7),
        (__int64)v73,
        v74);
    }
  }
  else if ( byte_18010EC4D )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 52, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v12, v10);
  }
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v82);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180077014  mov     rax, rsp
0x180077017  mov     [rax+20h], rbx
0x18007701b  push    rbp
0x18007701c  push    rsi
0x18007701d  push    rdi
0x18007701e  push    r12
0x180077020  push    r13
0x180077022  push    r14
0x180077024  push    r15
0x180077026  lea     rbp, [rax-0C8h]
0x18007702d  sub     rsp, 1A0h
0x180077034  movaps  xmmword ptr [rax-48h], xmm6
0x180077038  movaps  xmmword ptr [rax-58h], xmm7
0x18007703c  movaps  xmmword ptr [rax-68h], xmm8
0x180077041  mov     rax, cs:__security_cookie
0x180077048  xor     rax, rsp
0x18007704b  mov     [rbp+0C0h+var_70], rax
0x18007704f  xor     r14d, r14d
0x180077052  mov     [rbp+0C0h+var_D0], rdx
0x180077056  mov     r15, rdx
0x180077059  mov     [rbp+0C0h+var_130], rcx
0x18007705d  mov     r13, rcx
0x180077060  mov     [rbp+0C0h+var_11C], r14d
0x180077064  mov     rdx, r8
0x180077067  mov     [rbp+0C0h+var_F8], r14d
0x18007706b  lea     rcx, [rbp+0C0h+var_128]
0x18007706f  mov     [rbp+0C0h+var_E0], r14
0x180077073  mov     rbx, r8
0x180077076  call    ??0?$com_ptr_t@UIMFMediaType@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIMFMediaType@@@Z; wil::com_ptr_t<IMFMediaType,wil::err_returncode_policy>::com_ptr_t<IMFMediaType,wil::err_returncode_policy>(IMFMediaType *)
0x18007707b  cmp     cs:byte_18010EC4D, 8
0x180077082  jb      short loc_1800770A5
0x180077084  mov     rcx, cs:WPP_GLOBAL_Control
0x18007708b  lea     edx, [r14+25h]
0x18007708f  mov     r9, r13
0x180077092  lea     r8, WPP_9bb944463e3039875071016bf2e24787_Traceguids
0x180077099  mov     rcx, [rcx+0D8h]
0x1800770a0  call    WPP_SF_q
0x1800770a5  mov     eax, 1
0x1800770aa  lock xadd cs:dword_18010EE9C, eax
0x1800770b2  and     dword ptr [r13+3Ch], 0FFF00000h
0x1800770ba  inc     eax
0x1800770bc  movzx   ecx, ax
0x1800770bf  or      [r13+3Ch], ecx
0x1800770c3  call    cs:__imp_GetCurrentProcessId
0x1800770c9  mov     [r13+38h], eax
0x1800770cd  mov     rcx, r15
0x1800770d0  mov     rax, [r15]
0x1800770d3  mov     rax, [rax+48h]
0x1800770d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800770dc  mov     [r13+40h], eax
0x1800770e0  mov     rcx, r15
0x1800770e3  mov     rax, [r15]
0x1800770e6  mov     rax, [rax+60h]
0x1800770ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800770ef  and     dword ptr [r13+44h], 0FFFFFFF7h
0x1800770f4  mov     rcx, r15
0x1800770f7  neg     eax
0x1800770f9  sbb     eax, eax
0x1800770fb  and     eax, 8
0x1800770fe  or      [r13+44h], eax
0x180077102  mov     rax, [r15]
0x180077105  mov     rax, [rax+68h]
0x180077109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007710e  neg     eax
0x180077110  mov     eax, [r13+44h]
0x180077114  sbb     ecx, ecx
0x180077116  and     eax, 0FFFFFFDFh
0x180077119  and     ecx, 20h
0x18007711c  or      ecx, eax
0x18007711e  mov     [r13+44h], ecx
0x180077122  mov     rcx, r15
0x180077125  mov     rax, [r15]
0x180077128  mov     rax, [rax+70h]
0x18007712c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077131  neg     eax
0x180077133  mov     eax, [r13+44h]
0x180077137  sbb     ecx, ecx
0x180077139  and     eax, 0FFFFFFBFh
0x18007713c  and     ecx, 40h
0x18007713f  or      ecx, eax
0x180077141  mov     [r13+44h], ecx
0x180077145  mov     rcx, r15
0x180077148  mov     rax, [r15]
0x18007714b  mov     rax, [rax+80h]
0x180077152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077157  neg     eax
0x180077159  mov     edi, 80h
0x18007715e  mov     eax, [r13+44h]
0x180077162  mov     r12d, 0FFFFFF7Fh
0x180077168  sbb     ecx, ecx
0x18007716a  and     eax, r12d
0x18007716d  and     ecx, edi
0x18007716f  or      ecx, eax
0x180077171  mov     [r13+44h], ecx
0x180077175  mov     rcx, r15
0x180077178  mov     rax, [r15]
0x18007717b  mov     rax, [rax+88h]
0x180077182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077187  neg     eax
0x180077189  lea     rdx, [r13+48h]
0x18007718d  mov     eax, [r13+44h]
0x180077191  lea     r8, [rbp+0C0h+var_F8]
0x180077195  sbb     ecx, ecx
0x180077197  btr     eax, 9
0x18007719b  and     ecx, 200h
0x1800771a1  or      ecx, eax
0x1800771a3  mov     [r13+44h], ecx
0x1800771a7  mov     rcx, r15
0x1800771aa  mov     rax, [r15]
0x1800771ad  mov     rax, [rax+40h]
0x1800771b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800771b6  mov     esi, eax
0x1800771b8  test    eax, eax
0x1800771ba  jns     short loc_1800771EE
0x1800771bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800771c3  jb      short loc_1800771E6
0x1800771c5  lea     edx, [rdi-5Ah]
0x1800771c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800771cf  lea     r8, WPP_9bb944463e3039875071016bf2e24787_Traceguids
0x1800771d6  mov     r9, r13
0x1800771d9  mov     dword ptr [rsp+1D0h+pdwType], eax
0x1800771dd  mov     rcx, [rcx+10h]
0x1800771e1  call    WPP_SF_qD
0x1800771e6  mov     rbx, r13
0x1800771e9  jmp     loc_180077CD3
0x1800771ee  test    rbx, rbx
0x1800771f1  jz      loc_180077297
0x1800771f7  xor     r8d, r8d
0x1800771fa  lea     rdx, MF_FRAMESERVER_VCAM_CONFIGURATION_APP
0x180077201  mov     rcx, rbx
0x180077204  call    MFGetAttributeUINT32
0x180077209  neg     eax
0x18007720b  lea     rdx, MF_FRAMESERVER_BLOCK_SAME_PROCESS_PREEMPTION
0x180077212  mov     eax, [r13+44h]
0x180077216  sbb     ecx, ecx
0x180077218  and     eax, 0FFFFFFFDh
0x18007721b  and     ecx, 2
0x18007721e  xor     r8d, r8d
0x180077221  or      ecx, eax
0x180077223  mov     [r13+44h], ecx
0x180077227  mov     rcx, rbx
0x18007722a  call    MFGetAttributeUINT32
0x18007722f  neg     eax
0x180077231  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS
0x180077238  mov     eax, [r13+44h]
0x18007723c  sbb     ecx, ecx
0x18007723e  and     eax, 0FFFFFFEFh
0x180077241  and     ecx, 10h
0x180077244  xor     r8d, r8d
0x180077247  or      ecx, eax
0x180077249  mov     [r13+44h], ecx
0x18007724d  mov     rcx, rbx
0x180077250  call    MFGetAttributeUINT32
0x180077255  neg     eax
0x180077257  lea     rdx, MF_VIRTUALCAMERA_PROVIDE_ASSOCIATED_CAMERA_SOURCES
0x18007725e  mov     eax, [r13+44h]
0x180077262  sbb     ecx, ecx
0x180077264  btr     eax, 0Ah
0x180077268  and     ecx, 400h
0x18007726e  xor     r8d, r8d
0x180077271  or      ecx, eax
0x180077273  mov     [r13+44h], ecx
0x180077277  mov     rcx, rbx
0x18007727a  call    MFGetAttributeUINT32
0x18007727f  neg     eax
0x180077281  mov     eax, [r13+44h]
0x180077285  sbb     ecx, ecx
0x180077287  btr     eax, 0Bh
0x18007728b  and     ecx, 800h
0x180077291  or      ecx, eax
0x180077293  mov     [r13+44h], ecx
0x180077297  mov     [r13+58h], r14
0x18007729b  test    [r13+44h], dil
0x18007729f  jnz     short loc_1800772C6
0x1800772a1  mov     rax, [r15]
0x1800772a4  mov     rcx, r15
0x1800772a7  mov     rax, [rax+98h]
0x1800772ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772b3  neg     eax
0x1800772b5  mov     eax, [r13+44h]
0x1800772b9  sbb     ecx, ecx
0x1800772bb  and     eax, r12d
0x1800772be  and     ecx, edi
0x1800772c0  or      ecx, eax
0x1800772c2  mov     [r13+44h], ecx
0x1800772c6  mov     rax, [r15]
0x1800772c9  mov     rcx, r15
0x1800772cc  mov     rax, [rax+90h]
0x1800772d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772d8  mov     [r13+90h], eax
0x1800772df  mov     rcx, r15
0x1800772e2  mov     rax, [r15]
0x1800772e5  mov     rax, [rax+58h]
0x1800772e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772ee  test    rax, rax
0x1800772f1  jz      short loc_180077333
0x1800772f3  mov     rax, [r15]
0x1800772f6  mov     rcx, r15
0x1800772f9  mov     rax, [rax+58h]
0x1800772fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077302  mov     rdx, rax
0x180077305  lea     rcx, [r13+98h]
0x18007730c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180077311  test    al, al
0x180077313  jnz     short loc_180077333
0x180077315  mov     eax, 8007000Eh
0x18007731a  mov     esi, eax
0x18007731c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077323  jb      loc_1800771E6
0x180077329  mov     edx, 27h ; '''
0x18007732e  jmp     loc_1800771C8
0x180077333  mov     rax, [r15]
0x180077336  lea     rcx, [rbp+0C0h+var_128]
0x18007733a  mov     dword ptr [rbp+0C0h+Data], r14d
0x18007733e  mov     [rbp+0C0h+var_F4], 4
0x180077345  mov     [rbp+0C0h+var_140], r14
0x180077349  mov     rbx, [rax+50h]
0x18007734d  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180077352  lea     rcx, [rbp+0C0h+var_140]
0x180077356  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007735b  lea     r8, [rbp+0C0h+var_128]
0x18007735f  mov     rcx, r15
0x180077362  lea     rdx, [rbp+0C0h+var_140]
0x180077366  mov     rax, rbx
0x180077369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007736e  mov     esi, eax
0x180077370  test    eax, eax
0x180077372  jns     short loc_1800773AE
0x180077374  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007737b  jb      short loc_1800773A0
0x18007737d  mov     edx, 28h ; '('
0x180077382  mov     rcx, cs:WPP_GLOBAL_Control
0x180077389  lea     r8, WPP_9bb944463e3039875071016bf2e24787_Traceguids
0x180077390  mov     r9, r13
0x180077393  mov     dword ptr [rsp+1D0h+pdwType], eax
0x180077397  mov     rcx, [rcx+10h]
0x18007739b  call    WPP_SF_qD
0x1800773a0  lea     rcx, [rbp+0C0h+var_140]; void *
0x1800773a4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800773a9  jmp     loc_1800771E6
0x1800773ae  mov     rbx, [rbp+0C0h+var_140]
0x1800773b2  test    rbx, rbx
0x1800773b5  jz      loc_18007746A
0x1800773bb  mov     [rbp+0C0h+pszDeviceInterface], r14
0x1800773bf  lea     rcx, [rbp+0C0h+pszDeviceInterface]
0x1800773c3  mov     [rbp+0C0h+var_118], r14d
0x1800773c7  xor     edx, edx
0x1800773c9  mov     rax, [rbx]
0x1800773cc  xor     sil, sil
0x1800773cf  mov     rdi, [rax+68h]
0x1800773d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800773d8  lea     r9, [rbp+0C0h+var_118]
0x1800773dc  mov     rcx, rbx
0x1800773df  lea     r8, [rbp+0C0h+pszDeviceInterface]
0x1800773e3  mov     rax, rdi
0x1800773e6  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x1800773ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800773f2  test    eax, eax
0x1800773f4  js      short loc_18007745C
0x1800773f6  mov     rcx, [rbp+0C0h+pszDeviceInterface]; pszDeviceInterface
0x1800773fa  lea     rax, [rbp+0C0h+var_108]
0x1800773fe  lea     r8, [rbp+0C0h+Data]; lpData
0x180077402  mov     [rsp+1D0h+pdwType], rax; unsigned int *
0x180077407  lea     rdx, aCountofframest_0; "CountOfFramesToWaitForConfig"
0x18007740e  mov     [rbp+0C0h+var_108], r14d
0x180077412  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x180077417  test    eax, eax
0x180077419  js      short loc_18007745C
0x18007741b  mov     eax, dword ptr [rbp+0C0h+Data]
0x18007741e  test    eax, eax
0x180077420  jz      short loc_18007745C
0x180077422  mov     [r13+108h], rax
0x180077429  mov     sil, 1
0x18007742c  cmp     cs:byte_18010EC4D, 8
0x180077433  jb      short loc_18007745C
0x180077435  mov     rcx, cs:WPP_GLOBAL_Control
0x18007743c  lea     r8, WPP_9bb944463e3039875071016bf2e24787_Traceguids
0x180077443  mov     edx, 29h ; ')'
0x180077448  mov     [rsp+1D0h+pdwType], rax
0x18007744d  mov     r9, r13
0x180077450  mov     rcx, [rcx+0D8h]
0x180077457  call    WPP_SF_qq
0x18007745c  lea     rcx, [rbp+0C0h+pszDeviceInterface]
0x180077460  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180077465  test    sil, sil
0x180077468  jnz     short loc_1800774E4
0x18007746a  lea     rax, [rbp+0C0h+var_F4]
0x18007746e  mov     r9d, 10h; dwFlags
0x180077474  mov     [rsp+1D0h+pcbData], rax; pcbData
0x180077479  lea     r8, aCountofframest_0; "CountOfFramesToWaitForConfig"
0x180077480  lea     rax, [rbp+0C0h+Data]
0x180077484  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18007748b  mov     [rsp+1D0h+pvData], rax; pvData
0x180077490  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x180077497  mov     [rsp+1D0h+pdwType], r14; pdwType
0x18007749c  call    cs:__imp_RegGetValueW
0x1800774a2  test    eax, eax
0x1800774a4  jnz     short loc_1800774E4
0x1800774a6  mov     eax, dword ptr [rbp+0C0h+Data]
0x1800774a9  test    eax, eax
  ... truncated ...
```
