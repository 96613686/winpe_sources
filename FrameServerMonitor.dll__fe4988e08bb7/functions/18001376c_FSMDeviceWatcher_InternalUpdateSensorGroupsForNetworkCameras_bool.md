# FSMDeviceWatcher::InternalUpdateSensorGroupsForNetworkCameras(bool *)

- ea: `0x18001376c`
- end: `0x180014138`
- name: `?InternalUpdateSensorGroupsForNetworkCameras@FSMDeviceWatcher@@IEAAJPEA_N@Z`
- size: `2508`
- prototype: `__int64 __fastcall(FSMDeviceWatcher *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800127f0`
- `0x180015180`

## callees

- `0x180002346`
- `0x180002668`
- `0x180003294`
- `0x180004f78`
- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a68`
- `0x180006a98`
- `0x180006ae8`
- `0x180006ffc`
- `0x18000723c`
- `0x18000cadc`
- `0x18000d088`
- `0x18000d1e0`
- `0x18000d208`
- `0x18000d4f8`
- `0x18000d62c`
- `0x18000e148`
- `0x18000e25c`
- `0x18000e5c0`
- `0x180013274`
- `0x18001376c`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorGroupIdManager` at `0x180013dc2`
- `MFSENSORGROUP!MFCreateSensorGroupIdManager` at `0x180013dc2`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x18001388b`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x18001388b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001398f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001398f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d25`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013d1b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013d74`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013d1b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013d74`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013985`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013985`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a7c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a7c`

## string_xrefs

- `0x180013884`: `LocalService`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::InternalUpdateSensorGroupsForNetworkCameras(__int64 **this, bool *a2)
{
  int updated; // esi
  _DWORD *v4; // rbx
  __int64 v5; // rcx
  unsigned __int64 v6; // r15
  __int64 v7; // rbx
  bool v8; // cf
  unsigned __int64 v9; // rbx
  char *v10; // rax
  char *v11; // rdi
  signed int LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  signed int v17; // eax
  unsigned __int64 v18; // r12
  __int64 *v19; // rbx
  __int64 v20; // rcx
  LPVOID v21; // rsi
  __int64 (__fastcall **v22)(LPVOID, GUID *, __int64 **); // rax
  __int64 (__fastcall *v23)(LPVOID, GUID *, __int64 **); // r14
  unsigned __int16 *v24; // rcx
  __int64 v25; // rsi
  __int64 v26; // rax
  __int64 (__fastcall *v27)(__int64, GUID *, unsigned __int16 **); // r14
  unsigned __int64 v28; // rcx
  unsigned __int16 *v29; // rsi
  __int64 (__fastcall **v30)(unsigned __int16 *, GUID *, unsigned __int64); // rax
  __int64 (__fastcall *v31)(unsigned __int16 *, GUID *, unsigned __int64 *); // r14
  unsigned __int64 v32; // r15
  __int64 (__fastcall *v33)(unsigned __int64, unsigned __int64); // r14
  unsigned __int64 v34; // rsi
  unsigned __int16 *v35; // r15
  unsigned __int64 v36; // rsi
  __int64 (__fastcall *v37)(unsigned __int16 *, GUID *, unsigned __int64); // r14
  __int64 v38; // rdx
  signed int v39; // eax
  __int64 v40; // rdx
  char *v41; // r12
  unsigned __int64 i; // r14
  __int64 *v43; // rdi
  const unsigned __int16 *v44; // rcx
  unsigned int v45; // r11d
  unsigned int v46; // r11d
  char *v47; // rsi
  const struct std::nothrow_t *unique; // rax
  unsigned __int16 *v49; // rbx
  __int64 v50; // rdx
  int v51; // ecx
  int v52; // ecx
  LPVOID ppv; // [rsp+30h] [rbp-39h] BYREF
  HANDLE hToken; // [rsp+38h] [rbp-31h] BYREF
  char *v55; // [rsp+40h] [rbp-29h]
  struct IMFSensorGroupIdManager *v56; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v57; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v58; // [rsp+58h] [rbp-11h] BYREF
  __int64 v59; // [rsp+60h] [rbp-9h] BYREF
  int v60; // [rsp+68h] [rbp-1h]
  __int64 v61; // [rsp+6Ch] [rbp+3h]
  __int64 *v62; // [rsp+D0h] [rbp+67h] BYREF
  bool *v63; // [rsp+D8h] [rbp+6Fh]
  unsigned __int16 *v64; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int64 v65; // [rsp+E8h] [rbp+7Fh] BYREF

  v63 = a2;
  updated = 0;
  v55 = 0;
  hToken = 0;
  v56 = 0;
  v59 = 0;
  v61 = 0;
  v60 = 0;
  v4 = this + 17;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 181, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, v5, *v4);
  v6 = *(_QWORD *)v4;
  v58 = v6;
  if ( !v6 )
    goto LABEL_17;
  v7 = 48 * v6;
  if ( !is_mul_ok(v6, 0x30u) )
    v7 = -1;
  v8 = __CFADD__(v7, 8);
  v9 = v7 + 8;
  if ( v8 )
    v9 = -1;
  v10 = (char *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
  {
    v55 = 0;
LABEL_120:
    updated = -2147024882;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v52);
    goto LABEL_122;
  }
  memset_0(v10, 0, v9);
  *(_QWORD *)v11 = v6;
  v55 = v11 + 8;
  `vector constructor iterator'(v11 + 8, 0x30u, v6, (void *(*)(void *))FSNetworkCameraInfo::FSNetworkCameraInfo);
  if ( v11 == (char *)-8LL )
    goto LABEL_120;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hToken,
    0);
  if ( !LogonUserW(L"LocalService", L"NT AUTHORITY", 0, 5u, 0, &hToken) )
  {
    LastError = GetLastError();
    updated = LastError;
    if ( LastError > 0 )
      updated = (unsigned __int16)LastError | 0x80070000;
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    {
      v13 = 183;
LABEL_15:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v13,
        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        this,
        updated);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 184, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v17 = GetLastError();
    updated = v17;
    if ( v17 > 0 )
      updated = (unsigned __int16)v17 | 0x80070000;
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    {
      v13 = 185;
      goto LABEL_15;
    }
LABEL_16:
    if ( updated < 0 )
      goto LABEL_122;
LABEL_17:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    {
      v14 = 210;
LABEL_19:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v14,
        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        this,
        updated);
    }
    goto LABEL_20;
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 186, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  v18 = 0;
  v19 = this[15];
  while ( v19 != (__int64 *)(this + 15) )
  {
    v64 = 0;
    v65 = 0;
    ppv = 0;
    v62 = 0;
    if ( v18 >= v6 )
    {
      updated = -1072875845;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v38 = 187;
LABEL_67:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v38,
          &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
          this,
          updated);
      }
LABEL_68:
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v62);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppv);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v65);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v64);
LABEL_74:
      if ( hToken )
        RevertToSelf();
      goto LABEL_16;
    }
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        188,
        (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        (_DWORD)this,
        v19[2]);
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&ppv);
    updated = CoCreateInstance(
                &CLSID_FrameServerNetworkCameraSource,
                0,
                1u,
                &GUID_00000000_0000_0000_c000_000000000046,
                &ppv);
    if ( updated < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v38 = 189;
        goto LABEL_67;
      }
      goto LABEL_68;
    }
    v20 = (__int64)v62;
    v21 = ppv;
    v22 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 **))ppv;
    v62 = 0;
    v23 = *v22;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    updated = v23(v21, &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67, &v62);
    if ( updated < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v38 = 190;
        goto LABEL_67;
      }
      goto LABEL_68;
    }
    updated = (*(__int64 (__fastcall **)(__int64 *, const IID *, __int64))(*v62 + 200))(
                v62,
                &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
                v19[2]);
    if ( updated < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v38 = 191;
        goto LABEL_67;
      }
      goto LABEL_68;
    }
    v24 = v64;
    v25 = (__int64)v62;
    v26 = *v62;
    v64 = 0;
    v27 = *(__int64 (__fastcall **)(__int64, GUID *, unsigned __int16 **))(v26 + 264);
    if ( v24 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v24 + 16LL))(v24);
    updated = v27(v25, &GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66, &v64);
    if ( updated < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v38 = 192;
        goto LABEL_67;
      }
      goto LABEL_68;
    }
    v28 = v65;
    v29 = v64;
    v30 = *(__int64 (__fastcall ***)(unsigned __int16 *, GUID *, unsigned __int64))v64;
    v65 = 0;
    v31 = (__int64 (__fastcall *)(unsigned __int16 *, GUID *, unsigned __int64 *))*v30;
    if ( v28 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v28 + 16LL))(v28);
    updated = v31(v29, &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8, &v65);
    if ( updated < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v38 = 193;
        goto LABEL_67;
      }
      goto LABEL_68;
    }
    v32 = v65;
    v33 = *(__int64 (__fastcall **)(unsigned __int64, unsigned __int64))(*(_QWORD *)v65 + 104LL);
    v57 = (unsigned __int64)&v55[48 * v18];
    v34 = v57 + 40;
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(v57 + 40);
    updated = v33(v32, v34);
    if ( updated < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v38 = 194;
        goto LABEL_67;
      }
      goto LABEL_68;
    }
    v35 = v64;
    v36 = v57;
    v37 = **(__int64 (__fastcall ***)(unsigned __int16 *, GUID *, unsigned __int64))v64;
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(v57 + 32);
    updated = v37(v35, &GUID_00000000_0000_0000_c000_000000000046, v36 + 32);
    if ( updated < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v38 = 195;
        goto LABEL_67;
      }
      goto LABEL_68;
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      v57,
      v19[2],
      (v19[3] - v19[2]) >> 1);
    ++v18;
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v62);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppv);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v65);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v64);
    v19 = (__int64 *)*v19;
    v6 = v58;
  }
  if ( !RevertToSelf() )
  {
    v39 = GetLastError();
    updated = v39;
    if ( v39 > 0 )
      updated = (unsigned __int16)v39 | 0x80070000;
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        196,
        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        this,
        updated);
    goto LABEL_74;
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 197, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hToken,
    0);
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v56);
  updated = MFCreateSensorGroupIdManager(&v56);
  if ( updated < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v40 = 198;
      goto LABEL_81;
    }
    goto LABEL_122;
  }
  v41 = v55;
  for ( i = 0; ; ++i )
  {
    if ( i >= v6 )
      goto LABEL_16;
    LODWORD(v62) = 0;
    v43 = (__int64 *)&v41[48 * i];
    updated = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v43[5] + 168LL))(
                v43[5],
                MF_FSM_CLIENT_ACTIVATED_MEDIASOURCE,
                1);
    if ( updated < 0 )
      break;
    if ( (*(int (__fastcall **)(__int64, const IID *, __int64 **))(*(_QWORD *)v43[5] + 32LL))(
           v43[5],
           &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
           &v62) < 0 )
    {
      v44 = (const unsigned __int16 *)*v43;
      v64 = 0;
      v65 = 0;
      v57 = 0;
      ppv = 0;
      updated = StringCchLengthW(v44, 0x7FFFFFFFu, (unsigned __int64 *)&ppv);
      if ( updated < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_107;
        v50 = 200;
        goto LABEL_114;
      }
      updated = StringCchLengthW(L"Unknown Network Camera (", v45, &v65);
      if ( updated < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_107;
        v50 = 201;
        goto LABEL_114;
      }
      updated = StringCchLengthW(L")", v46, &v57);
      if ( updated < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_107;
        v50 = 202;
LABEL_114:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v50,
          &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
          this,
          updated);
        goto LABEL_107;
      }
      v47 = (char *)ppv + v65 + v57;
      unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(
                                                &v58,
                                                (unsigned __int64)(v47 + 1));
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v64, unique);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v58);
      v49 = v64;
      if ( !v64 )
      {
        updated = -2147024882;
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            203,
            &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
            this,
            v51);
        goto LABEL_107;
      }
      updated = StringCchPrintfW(v64, (unsigned __int64)(v47 + 1), L"%s%s%s", L"Unknown Network Camera (", *v43, L")");
      if ( updated < 0 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v50 = 204;
          goto LABEL_114;
        }
LABEL_107:
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v64);
        goto LABEL_122;
      }
      updated = (*(__int64 (__fastcall **)(__int64, const IID *, unsigned __int16 *))(*(_QWORD *)v43[5] + 200LL))(
                  v43[5],
                  &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
                  v49);
      if ( updated < 0 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v50 = 205;
          goto LABEL_114;
        }
        goto LABEL_107;
      }
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
        WPP_SF_qDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          206,
          (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
          (_DWORD)this,
          230,
          (__int64)v49);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v64);
    }
    updated = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v43[5] + 168LL))(
                v43[5],
                MF_DEVSOURCE_ATTRIBUTE_USE_DSHOWBRIDGE,
                1);
    if ( updated < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v40 = 207;
        goto LABEL_81;
      }
      goto LABEL_122;
    }
    updated = FSMDeviceWatcher::InternalUpdateSensorGroupsForNetworkCameras(
                (FSMDeviceWatcher *)this,
                v56,
                (const struct FSNetworkCameraInfo *)&v41[48 * i]);
    if ( updated < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
        WPP_SF_qDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          208,
          (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
          (_DWORD)this,
          updated,
          *v43);
      updated = 0;
    }
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v40 = 199;
LABEL_81:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, updated);
  }
LABEL_122:
  if ( v63 )
    *v63 = 1;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
  {
    v14 = 209;
    goto LABEL_19;
  }
LABEL_20:
  CTUnkArray<IMFSensorGroup>::~CTUnkArray<IMFSensorGroup>(&v59);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v56);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  if ( v55 )
    wistd::default_delete<FSNetworkCameraInfo [0]>::operator()<FSNetworkCameraInfo>(v15, v55);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001376c  mov     [rsp-8+arg_8], rdx
0x180013771  push    rbp
0x180013772  push    rbx
0x180013773  push    rsi
0x180013774  push    rdi
0x180013775  push    r12
0x180013777  push    r13
0x180013779  push    r14
0x18001377b  push    r15
0x18001377d  lea     rbp, [rsp-1Fh]
0x180013782  sub     rsp, 88h
0x180013789  xor     esi, esi
0x18001378b  mov     r13, rcx
0x18001378e  mov     [rbp+57h+var_80], rsi
0x180013792  mov     [rbp+57h+hToken], rsi
0x180013796  mov     [rbp+57h+var_78], rsi
0x18001379a  mov     [rbp+57h+var_60], rsi
0x18001379e  mov     [rbp+57h+var_54], rsi
0x1800137a2  mov     [rbp+57h+var_58], esi
0x1800137a5  lea     rbx, [rcx+88h]
0x1800137ac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800137b1  cmp     al, 8
0x1800137b3  jb      short loc_1800137DD
0x1800137b5  mov     eax, [rbx]
0x1800137b7  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800137be  mov     r9, rcx
0x1800137c1  mov     [rsp+0C0h+dwLogonProvider], eax
0x1800137c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137cc  mov     edx, 0B5h
0x1800137d1  mov     rcx, [rcx+0D8h]
0x1800137d8  call    WPP_SF_qD
0x1800137dd  mov     r15, [rbx]
0x1800137e0  mov     [rbp+57h+var_68], r15
0x1800137e4  test    r15, r15
0x1800137e7  jz      loc_1800138E5
0x1800137ed  mov     esi, 30h ; '0'
0x1800137f2  mov     eax, esi
0x1800137f4  mul     r15
0x1800137f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800137fe  mov     rbx, rax
0x180013801  lea     rax, [rsi-31h]
0x180013805  cmovb   rbx, rax
0x180013809  add     rbx, 8
0x18001380d  cmovb   rbx, rax
0x180013811  mov     rcx, rbx; unsigned __int64
0x180013814  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013819  mov     rdi, rax
0x18001381c  test    rax, rax
0x18001381f  jz      loc_1800140DA
0x180013825  mov     r8, rbx; Size
0x180013828  xor     edx, edx; Val
0x18001382a  mov     rcx, rax; void *
0x18001382d  call    memset_0
0x180013832  mov     [rdi], r15
0x180013835  lea     r9, ??0FSNetworkCameraInfo@@QEAA@XZ; void *(*)(void *)
0x18001383c  add     rdi, 8
0x180013840  mov     r8, r15; unsigned __int64
0x180013843  mov     rcx, rdi; void *
0x180013846  mov     [rbp+57h+var_80], rdi
0x18001384a  mov     edx, esi; unsigned __int64
0x18001384c  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180013851  test    rdi, rdi
0x180013854  jz      loc_1800140E2
0x18001385a  xor     edx, edx
0x18001385c  lea     rcx, [rbp+57h+hToken]
0x180013860  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180013865  lea     rax, [rbp+57h+hToken]
0x180013869  xor     r8d, r8d; lpszPassword
0x18001386c  mov     [rsp+0C0h+phToken], rax; phToken
0x180013871  lea     r9d, [rsi-2Bh]; dwLogonType
0x180013875  lea     rdx, szDomain; "NT AUTHORITY"
0x18001387c  mov     [rsp+0C0h+dwLogonProvider], 0; dwLogonProvider
0x180013884  lea     rcx, szUsername; "LocalService"
0x18001388b  call    cs:__imp_LogonUserW
0x180013891  test    eax, eax
0x180013893  jnz     loc_180013956
0x180013899  call    cs:__imp_GetLastError
0x18001389f  mov     esi, eax
0x1800138a1  test    eax, eax
0x1800138a3  jle     short loc_1800138AE
0x1800138a5  movzx   esi, ax
0x1800138a8  or      esi, 80070000h
0x1800138ae  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800138b3  cmp     al, 1
0x1800138b5  jb      short loc_1800138DD
0x1800138b7  mov     edx, 0B7h
0x1800138bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138c3  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800138ca  mov     r9, r13
0x1800138cd  mov     [rsp+0C0h+dwLogonProvider], esi
0x1800138d1  mov     rcx, [rcx+0D8h]
0x1800138d8  call    WPP_SF_qD
0x1800138dd  test    esi, esi
0x1800138df  js      loc_180014115
0x1800138e5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800138ea  cmp     al, 8
0x1800138ec  jb      short loc_180013914
0x1800138ee  mov     edx, 0D2h
0x1800138f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138fa  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180013901  mov     r9, r13
0x180013904  mov     [rsp+0C0h+dwLogonProvider], esi
0x180013908  mov     rcx, [rcx+0D8h]
0x18001390f  call    WPP_SF_qD
0x180013914  lea     rcx, [rbp+57h+var_60]
0x180013918  call    ??1?$CTUnkArray@UIMFSensorGroup@@@@QEAA@XZ; CTUnkArray<IMFSensorGroup>::~CTUnkArray<IMFSensorGroup>(void)
0x18001391d  lea     rcx, [rbp+57h+var_78]
0x180013921  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180013926  lea     rcx, [rbp+57h+hToken]
0x18001392a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001392f  mov     rax, [rbp+57h+var_80]
0x180013933  test    rax, rax
0x180013936  jz      short loc_180013940
0x180013938  mov     rdx, rax
0x18001393b  call    ??$?RUFSNetworkCameraInfo@@@?$default_delete@$$BY0A@UFSNetworkCameraInfo@@@wistd@@QEBAXPEAUFSNetworkCameraInfo@@@Z; wistd::default_delete<FSNetworkCameraInfo [0]>::operator()<FSNetworkCameraInfo>(FSNetworkCameraInfo *)
0x180013940  mov     eax, esi
0x180013942  add     rsp, 88h
0x180013949  pop     r15
0x18001394b  pop     r14
0x18001394d  pop     r13
0x18001394f  pop     r12
0x180013951  pop     rdi
0x180013952  pop     rsi
0x180013953  pop     rbx
0x180013954  pop     rbp
0x180013955  retn
0x180013956  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001395b  cmp     al, 8
0x18001395d  jb      short loc_180013981
0x18001395f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013966  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x18001396d  mov     edx, 0B8h
0x180013972  mov     r9, r13
0x180013975  mov     rcx, [rcx+0D8h]
0x18001397c  call    WPP_SF_q
0x180013981  mov     rcx, [rbp+57h+hToken]; hToken
0x180013985  call    cs:__imp_ImpersonateLoggedOnUser
0x18001398b  test    eax, eax
0x18001398d  jnz     short loc_1800139BB
0x18001398f  call    cs:__imp_GetLastError
0x180013995  mov     esi, eax
0x180013997  test    eax, eax
0x180013999  jle     short loc_1800139A4
0x18001399b  movzx   esi, ax
0x18001399e  or      esi, 80070000h
0x1800139a4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800139a9  cmp     al, 1
0x1800139ab  jb      loc_1800138DD
0x1800139b1  mov     edx, 0B9h
0x1800139b6  jmp     loc_1800138BC
0x1800139bb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800139c0  cmp     al, 8
0x1800139c2  jb      short loc_1800139E6
0x1800139c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139cb  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800139d2  mov     edx, 0BAh
0x1800139d7  mov     r9, r13
0x1800139da  mov     rcx, [rcx+0D8h]
0x1800139e1  call    WPP_SF_q
0x1800139e6  lea     rdi, [r13+78h]
0x1800139ea  xor     r12d, r12d
0x1800139ed  mov     rbx, [rdi]
0x1800139f0  cmp     rbx, rdi
0x1800139f3  jz      loc_180013D1B
0x1800139f9  mov     [rbp+57h+arg_10], 0
0x180013a01  mov     [rbp+57h+arg_18], 0
0x180013a09  mov     [rbp+57h+ppv], 0
0x180013a11  mov     [rbp+57h+arg_0], 0
0x180013a19  cmp     r12, r15
0x180013a1c  jnb     loc_180013CC4
0x180013a22  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180013a27  cmp     al, 8
0x180013a29  jb      short loc_180013A56
0x180013a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a32  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180013a39  mov     rax, [rbx+10h]
0x180013a3d  mov     edx, 0BCh
0x180013a42  mov     r9, r13
0x180013a45  mov     qword ptr [rsp+0C0h+dwLogonProvider], rax
0x180013a4a  mov     rcx, [rcx+0D8h]
0x180013a51  call    WPP_SF_qS
0x180013a56  lea     rcx, [rbp+57h+ppv]
0x180013a5a  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180013a5f  xor     edx, edx; pUnkOuter
0x180013a61  lea     rax, [rbp+57h+ppv]
0x180013a65  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180013a6c  mov     qword ptr [rsp+0C0h+dwLogonProvider], rax; ppv
0x180013a71  lea     rcx, CLSID_FrameServerNetworkCameraSource; rclsid
0x180013a78  lea     r8d, [rdx+1]; dwClsContext
0x180013a7c  call    cs:__imp_CoCreateInstance
0x180013a82  mov     esi, eax
0x180013a84  test    eax, eax
0x180013a86  js      loc_180013CB4
0x180013a8c  mov     rcx, [rbp+57h+arg_0]
0x180013a90  mov     rsi, [rbp+57h+ppv]
0x180013a94  mov     rax, [rsi]
0x180013a97  mov     [rbp+57h+arg_0], 0
0x180013a9f  mov     r14, [rax]
0x180013aa2  test    rcx, rcx
0x180013aa5  jz      short loc_180013AB3
0x180013aa7  mov     rdx, [rcx]
0x180013aaa  mov     rax, [rdx+10h]
0x180013aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ab3  lea     r8, [rbp+57h+arg_0]
0x180013ab7  mov     rcx, rsi
0x180013aba  lea     rdx, _GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67
0x180013ac1  mov     rax, r14
0x180013ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ac9  mov     esi, eax
0x180013acb  test    eax, eax
0x180013acd  js      loc_180013CA4
0x180013ad3  mov     rcx, [rbp+57h+arg_0]
0x180013ad7  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x180013ade  mov     r8, [rbx+10h]
0x180013ae2  mov     rax, [rcx]
0x180013ae5  mov     rax, [rax+0C8h]
0x180013aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013af1  mov     esi, eax
0x180013af3  test    eax, eax
0x180013af5  js      loc_180013C94
0x180013afb  mov     rcx, [rbp+57h+arg_10]
0x180013aff  mov     rsi, [rbp+57h+arg_0]
0x180013b03  mov     rax, [rsi]
0x180013b06  mov     [rbp+57h+arg_10], 0
0x180013b0e  mov     r14, [rax+108h]
0x180013b15  test    rcx, rcx
0x180013b18  jz      short loc_180013B26
0x180013b1a  mov     rdx, [rcx]
0x180013b1d  mov     rax, [rdx+10h]
0x180013b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b26  lea     r8, [rbp+57h+arg_10]
0x180013b2a  mov     rcx, rsi
0x180013b2d  lea     rdx, _GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66
0x180013b34  mov     rax, r14
0x180013b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b3c  mov     esi, eax
0x180013b3e  test    eax, eax
0x180013b40  js      loc_180013C84
0x180013b46  mov     rcx, [rbp+57h+arg_18]
0x180013b4a  mov     rsi, [rbp+57h+arg_10]
0x180013b4e  mov     rax, [rsi]
0x180013b51  mov     [rbp+57h+arg_18], 0
0x180013b59  mov     r14, [rax]
0x180013b5c  test    rcx, rcx
0x180013b5f  jz      short loc_180013B6D
0x180013b61  mov     rdx, [rcx]
0x180013b64  mov     rax, [rdx+10h]
0x180013b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b6d  lea     r8, [rbp+57h+arg_18]
0x180013b71  mov     rcx, rsi
0x180013b74  lea     rdx, _GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8
0x180013b7b  mov     rax, r14
0x180013b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b83  mov     esi, eax
0x180013b85  test    eax, eax
0x180013b87  js      loc_180013C74
0x180013b8d  mov     r15, [rbp+57h+arg_18]
0x180013b91  lea     rdx, [r12+r12*2]
0x180013b95  shl     rdx, 4
0x180013b99  mov     rax, [r15]
0x180013b9c  mov     r14, [rax+68h]
0x180013ba0  mov     rax, [rbp+57h+var_80]
0x180013ba4  add     rax, rdx
0x180013ba7  mov     [rbp+57h+var_70], rax
0x180013bab  lea     rsi, [rax+28h]
0x180013baf  mov     rcx, rsi
0x180013bb2  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180013bb7  mov     rdx, rsi
0x180013bba  mov     rcx, r15
0x180013bbd  mov     rax, r14
0x180013bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bc5  mov     esi, eax
0x180013bc7  test    eax, eax
0x180013bc9  js      loc_180013C60
0x180013bcf  mov     r15, [rbp+57h+arg_10]
0x180013bd3  mov     rsi, [rbp+57h+var_70]
0x180013bd7  mov     rax, [r15]
0x180013bda  lea     rcx, [rsi+20h]
0x180013bde  mov     r14, [rax]
0x180013be1  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180013be6  lea     r8, [rsi+20h]
0x180013bea  mov     rcx, r15
0x180013bed  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180013bf4  mov     rax, r14
0x180013bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bfc  mov     esi, eax
0x180013bfe  test    eax, eax
0x180013c00  js      short loc_180013C4C
0x180013c02  mov     rdx, [rbx+10h]
0x180013c06  mov     r8, [rbx+18h]
0x180013c0a  mov     rcx, [rbp+57h+var_70]
0x180013c0e  sub     r8, rdx
0x180013c11  sar     r8, 1
0x180013c14  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180013c19  lea     rcx, [rbp+57h+arg_0]
0x180013c1d  inc     r12
0x180013c20  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180013c25  lea     rcx, [rbp+57h+ppv]
0x180013c29  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180013c2e  lea     rcx, [rbp+57h+arg_18]
  ... truncated ...
```
