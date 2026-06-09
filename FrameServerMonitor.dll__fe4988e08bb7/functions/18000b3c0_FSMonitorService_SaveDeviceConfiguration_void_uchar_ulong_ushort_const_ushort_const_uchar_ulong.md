# FSMonitorService::SaveDeviceConfiguration(void *,uchar *,ulong,ushort const *,ushort const *,uchar *,ulong)

- ea: `0x18000b3c0`
- end: `0x18000c0f9`
- name: `?SaveDeviceConfiguration@FSMonitorService@@UEAAJPEAXPEAEKPEBG21K@Z`
- size: `3385`
- prototype: `__int64 __fastcall(FSMonitorService *__hidden this, void *, unsigned __int8 *, char, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, char)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180002f90`
- `0x180003274`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x180006cc0`
- `0x180007020`
- `0x180007090`
- `0x18000723c`
- `0x180009c78`
- `0x18000b3c0`
- `0x18000cadc`
- `0x18000d024`
- `0x18000d1e0`
- `0x18000d240`
- `0x18000d330`
- `0x18000d36c`
- `0x18000d9b8`
- `0x18000db04`
- `0x18000dc08`
- `0x18002fa3c`
- `0x18002fa70`
- `0x18002fd78`
- `0x18002fda4`
- `0x180032d24`
- `0x1800372fc`
- `0x180038564`
- `0x18003a99c`
- `0x18003c75c`
- `0x18004bf44`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000be86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000be86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bef8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bef8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7d6`
- `RPCRT4!RpcServerInqBindingHandle` at `0x18000b612`
- `RPCRT4!RpcServerInqBindingHandle` at `0x18000b64d`
- `RPCRT4!RpcServerInqBindingHandle` at `0x18000b612`
- `RPCRT4!RpcServerInqBindingHandle` at `0x18000b64d`
- `RPCRT4!RpcImpersonateClient` at `0x18000b67d`
- `RPCRT4!RpcImpersonateClient` at `0x18000b68b`
- `RPCRT4!RpcImpersonateClient` at `0x18000b67d`
- `RPCRT4!RpcImpersonateClient` at `0x18000b68b`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000be76`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000c026`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000be76`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000c026`
- `RPCRT4!RpcBindingFree` at `0x18000b5fb`
- `RPCRT4!RpcBindingFree` at `0x18000b636`
- `RPCRT4!RpcBindingFree` at `0x18000b5fb`
- `RPCRT4!RpcBindingFree` at `0x18000b636`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b6c7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b77c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b6c7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b77c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000b7cc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000b7cc`

## pseudocode

```c
__int64 __fastcall FSMonitorService::SaveDeviceConfiguration(
        FSMonitorService *this,
        void *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int8 *a7,
        unsigned int a8)
{
  unsigned __int16 *v8; // rax
  char v12; // r12
  __int64 v13; // rdi
  __int64 v14; // rsi
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rcx
  int v17; // eax
  signed int v18; // r14d
  __int64 v19; // rdx
  RPC_BINDING_HANDLE v20; // rbx
  __int64 v21; // rdx
  signed int LastError; // eax
  __int64 v23; // rdx
  const struct std::nothrow_t *unique; // rax
  PSID *v25; // rbx
  signed int v26; // eax
  signed int v27; // eax
  int Configuration; // eax
  unsigned __int64 v29; // r11
  __int64 v30; // rdx
  unsigned __int16 *v31; // rbx
  unsigned __int64 v32; // r11
  int v33; // eax
  __int64 v34; // rdx
  const void *v35; // rax
  unsigned __int8 v36; // r13
  __int64 v37; // r8
  __int64 v38; // r8
  const struct std::nothrow_t *v39; // rdx
  FSString *v40; // rax
  const char *v41; // rdi
  FSString *v42; // rax
  const char *v43; // rbx
  FSString *v44; // rax
  const char *v45; // rax
  FSString *v46; // rcx
  FSString *v47; // rax
  const char *String; // rdi
  FSString *v49; // rax
  const char *v50; // rbx
  FSString *v51; // rax
  const char *v52; // rax
  int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 (__fastcall ***v56)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v57)(_QWORD, GUID *, __int64 *); // rax
  __int64 (__fastcall *v58)(_QWORD, GUID *, __int64 *); // r14
  bool v59; // zf
  __int64 v60; // rdx
  unsigned __int8 v62; // [rsp+60h] [rbp-A0h]
  _DWORD Size[3]; // [rsp+64h] [rbp-9Ch] BYREF
  struct IFSConfigurationKey *v64; // [rsp+70h] [rbp-90h] BYREF
  DWORD TokenInformationLength; // [rsp+78h] [rbp-88h] BYREF
  RPC_BINDING_HANDLE BindingHandle; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v67; // [rsp+88h] [rbp-78h] BYREF
  __int64 v68; // [rsp+90h] [rbp-70h] BYREF
  __int64 v69; // [rsp+98h] [rbp-68h] BYREF
  struct IFSConfiguration *v70; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v71; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v72; // [rsp+B0h] [rbp-50h] BYREF
  LPWSTR StringSid; // [rsp+B8h] [rbp-48h] BYREF
  RPC_BINDING_HANDLE v74; // [rsp+C0h] [rbp-40h] BYREF
  void *Buf1; // [rsp+C8h] [rbp-38h]
  LPVOID TokenInformation; // [rsp+D0h] [rbp-30h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v78; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v79; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v80; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v81[24]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v82[24]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v83[24]; // [rsp+128h] [rbp+28h] BYREF
  _OWORD v84[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v85; // [rsp+160h] [rbp+60h]
  _OWORD v86[2]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v87; // [rsp+188h] [rbp+88h]

  v8 = a6;
  Buf1 = a3;
  Size[0] = a4;
  v72 = a7;
  v85 = 0;
  v87 = 0;
  v12 = 0;
  v67 = a6;
  v13 = 0;
  v80 = 0;
  v14 = 0;
  v79 = 0;
  StringSid = 0;
  v78 = 0;
  BindingHandle = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  v64 = 0;
  *(_QWORD *)&Size[1] = 0;
  v68 = 0;
  v71 = 0;
  memset(v84, 0, sizeof(v84));
  v70 = 0;
  v69 = 0;
  memset(v86, 0, sizeof(v86));
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v15 = L"<null>";
    v16 = L"<null>";
    if ( a6 )
      v16 = a6;
    if ( a5 )
      v15 = a5;
    WPP_SF_qqqDSSqd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (char)a2,
      (char)a3,
      a4,
      (__int64)v15,
      (__int64)v16,
      (char)a7,
      a8);
    v8 = v67;
  }
  if ( !a5 )
  {
    v17 = -2147024809;
    v18 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_164;
    v19 = 56;
LABEL_163:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v17);
    goto LABEL_164;
  }
  if ( !v8 )
  {
    v17 = -2147024809;
    v18 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_164;
    v19 = 57;
    goto LABEL_163;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    if ( !Buf1 || !a4 )
    {
      v17 = -2147024809;
      v18 = -2147024809;
      if ( !g_wppLevels )
        goto LABEL_164;
      v19 = 58;
      goto LABEL_163;
    }
  }
  else if ( !Buf1 || a4 != 32 )
  {
    v17 = -2147024809;
    v18 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_164;
    v19 = 59;
    goto LABEL_163;
  }
  if ( !v72 )
  {
    if ( !a8 )
      goto LABEL_22;
LABEL_26:
    v17 = -2147024809;
    v18 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_164;
    v19 = 60;
    goto LABEL_163;
  }
  if ( !a8 )
    goto LABEL_26;
LABEL_22:
  v17 = FSMonitorService::InternalValidateSaveConfigurationOptions(this, a5, a2);
  v18 = v17;
  if ( v17 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_164;
    v19 = 61;
    goto LABEL_163;
  }
  BindingHandle = 0;
  if ( RpcServerInqBindingHandle(&BindingHandle) )
  {
    v20 = BindingHandle;
    if ( BindingHandle )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&Binding);
      v74 = v20;
      RpcBindingFree(&v74);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&Binding);
    }
    BindingHandle = 0;
    v18 = RpcServerInqBindingHandle(&BindingHandle) | 0x80010000;
    if ( !g_wppLevels )
    {
LABEL_164:
      if ( byte_18005E5A5 )
      {
        v60 = 87;
        goto LABEL_166;
      }
      goto LABEL_167;
    }
    v21 = 62;
LABEL_33:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v18);
    goto LABEL_164;
  }
  if ( RpcImpersonateClient(BindingHandle) )
  {
    v18 = RpcImpersonateClient(BindingHandle) | 0x80010000;
    if ( !g_wppLevels )
      goto LABEL_164;
    v21 = 63;
    goto LABEL_33;
  }
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError > 0 )
      v18 = (unsigned __int16)LastError | 0x80070000;
    if ( (int)(v18 + 0x80000000) >= 0 && v18 != -2147024774 )
    {
      if ( !g_wppLevels )
      {
LABEL_160:
        RpcRevertToSelfEx(BindingHandle);
        goto LABEL_164;
      }
      v23 = 64;
LABEL_44:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v18);
      goto LABEL_160;
    }
  }
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v74, TokenInformationLength);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&TokenInformation, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v74);
  v25 = (PSID *)TokenInformation;
  if ( !TokenInformation )
  {
    v18 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_160;
    v23 = (unsigned int)((_DWORD)TokenInformation + 65);
    goto LABEL_44;
  }
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFBLL,
          TokenUser,
          TokenInformation,
          TokenInformationLength,
          &TokenInformationLength) )
  {
    v26 = GetLastError();
    v18 = v26;
    if ( v26 > 0 )
      v18 = (unsigned __int16)v26 | 0x80070000;
    if ( v18 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_160;
      v23 = 66;
      goto LABEL_44;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(*v25, &StringSid) )
  {
    v27 = GetLastError();
    v18 = v27;
    if ( v27 > 0 )
      v18 = (unsigned __int16)v27 | 0x80070000;
    if ( v18 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_160;
      v23 = 67;
      goto LABEL_44;
    }
  }
  Configuration = StringCchLengthW(a5, 0x7FFFFFFFu, &v80);
  v18 = Configuration;
  if ( Configuration < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_160;
    v30 = 68;
LABEL_159:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v30,
      &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
      this,
      Configuration);
    goto LABEL_160;
  }
  v31 = v67;
  Configuration = StringCchLengthW(v67, v29, &v79);
  v18 = Configuration;
  if ( Configuration < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_160;
    v30 = 69;
    goto LABEL_159;
  }
  Configuration = StringCchLengthW(StringSid, v32, &v78);
  v18 = Configuration;
  if ( Configuration < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_160;
    v30 = 70;
    goto LABEL_159;
  }
  v64 = 0;
  Configuration = FSConfigurationKey::CreateKey(a5, (int)v80 + 1, v31, (int)v79 + 1, StringSid, (int)v78 + 1, &v64);
  v18 = Configuration;
  if ( Configuration < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_160;
    v30 = 71;
    goto LABEL_159;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    v67 = 0;
    v33 = (**(__int64 (__fastcall ***)(struct IFSConfigurationKey *, GUID *, unsigned __int16 **))v64)(
            v64,
            &GUID_d8ebce9c_16ac_4353_8b31_c7afd4fc67c1,
            &v67);
    v18 = v33;
    if ( v33 < 0 )
    {
      if ( g_wppLevels )
      {
        v34 = 72;
LABEL_79:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v33);
        goto LABEL_80;
      }
      goto LABEL_80;
    }
    if ( !(*(unsigned int (__fastcall **)(unsigned __int16 *, void *, _QWORD))(*(_QWORD *)v67 + 96LL))(
            v67,
            Buf1,
            Size[0]) )
    {
      v33 = -2147024809;
      v18 = -2147024809;
      if ( g_wppLevels )
      {
        v34 = 73;
        goto LABEL_79;
      }
LABEL_80:
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v67);
      goto LABEL_160;
    }
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v67);
  }
  else if ( Size[0] != (*(unsigned int (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v64 + 40LL))(v64)
         || (v35 = (const void *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v64 + 32LL))(v64),
             memcmp_0(Buf1, v35, Size[0])) )
  {
    Configuration = -2147024809;
    v18 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_160;
    v30 = 74;
    goto LABEL_159;
  }
  v62 = 0;
  v36 = 0;
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v70);
  if ( (int)FSLoadDeviceConfiguration(v64, &v70) >= 0 )
  {
    if ( v70 )
    {
      Size[0] = 0;
      v14 = ((__int64 (*)(void))MFGetAttributeUINT64)();
      v71 = v14;
      (*(void (__fastcall **)(struct IFSConfiguration *, __int64 *, _OWORD *, __int64, _DWORD *))(*(_QWORD *)v70 + 120LL))(
        v70,
        MF_FRAMESERVER_MANAGED_CAMERA_SELECTED_MEDIA,
        v86,
        40,
        Size);
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
        v36 = (unsigned int)MFGetAttributeUINT32(v70, MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS, v37) != 0;
    }
  }
  if ( v72 )
  {
    Size[0] = 0;
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&Size[1]);
    Configuration = FSConfiguration::CreateConfiguration(v64, (struct IFSConfiguration **)&Size[1]);
    v18 = Configuration;
    if ( Configuration < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_160;
      v30 = 75;
      goto LABEL_159;
    }
    Configuration = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD))(**(_QWORD **)&Size[1] + 288LL))(
                      *(_QWORD *)&Size[1],
                      v72,
                      a8);
    v18 = Configuration;
    if ( Configuration < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_160;
      v30 = 76;
      goto LABEL_159;
    }
    v13 = MFGetAttributeUINT64(*(_QWORD *)&Size[1]);
    v68 = v13;
    (*(void (__fastcall **)(_QWORD, __int64 *, _OWORD *, __int64, _DWORD *))(**(_QWORD **)&Size[1] + 120LL))(
      *(_QWORD *)&Size[1],
      MF_FRAMESERVER_MANAGED_CAMERA_SELECTED_MEDIA,
      v84,
      40,
      Size);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
      v62 = (unsigned int)MFGetAttributeUINT32(
                            *(_QWORD *)&Size[1],
                            MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS,
                            v38) != 0;
  }
  else if ( v14 )
  {
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&Size[1]);
    Configuration = FSConfiguration::CreateConfiguration(v64, (struct IFSConfiguration **)&Size[1]);
    v18 = Configuration;
    if ( Configuration < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_160;
      v30 = 77;
      goto LABEL_159;
    }
    Configuration = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(**(_QWORD **)&Size[1] + 176LL))(
                      *(_QWORD *)&Size[1],
                      MF_FRAMESERVER_MANAGED_CAMERA_MODE,
                      v14);
    v18 = Configuration;
    if ( Configuration < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_160;
      v30 = 78;
      goto LABEL_159;
    }
    Configuration = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _OWORD *, __int64))(**(_QWORD **)&Size[1] + 208LL))(
                      *(_QWORD *)&Size[1],
                      MF_FRAMESERVER_MANAGED_CAMERA_SELECTED_MEDIA,
                      v86,
                      40);
    v18 = Configuration;
    if ( Configuration < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_160;
      v30 = 79;
      goto LABEL_159;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl)
      && v36 )
    {
      Configuration = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(**(_QWORD **)&Size[1] + 168LL))(
                        *(_QWORD *)&Size[1],
                        MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS,
                        v36);
      v18 = Configuration;
      if ( Configuration < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_160;
        v30 = 80;
        goto LABEL_159;
      }
      v62 = v36;
    }
    Configuration = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 **, unsigned int *))(**(_QWORD **)&Size[1] + 280LL))(
                      *(_QWORD *)&Size[1],
                      &v72,
                      &a8);
    v18 = Configuration;
    if ( Configuration < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_160;
      v30 = 81;
      goto LABEL_159;
    }
    v13 = v14;
    v68 = v14;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      v47 = ManagedModeTrace::ManagedModeTrace(
              (ManagedModeTrace *)v81,
              (const struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011 *)v84);
      String = FSString::GetString(v47);
      v49 = ManagedModeTrace::ManagedModeTrace(
              (ManagedModeTrace *)v82,
              (const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *)&v68);
      v50 = FSString::GetString(v49);
      v51 = ManagedModeTrace::ManagedModeTrace(
              (ManagedModeTrace *)v83,
              (const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *)&v71);
      v52 = FSString::GetString(v51);
      WPP_SF_qsssdd(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v52, (__int64)v50, (__int64)String, v36, v62);
      v13 = v68;
      v12 = 7;
      v14 = v71;
    }
    if ( (v12 & 4) != 0 )
    {
      v12 &= ~4u;
      FSString::~FSString((FSString *)v83, v39);
    }
    if ( (v12 & 2) != 0 )
    {
      v12 &= ~2u;
      FSString::~FSString((FSString *)v82, v39);
    }
    if ( (v12 & 1) != 0 )
    {
      v46 = (FSString *)v81;
      goto LABEL_134;
    }
  }
  else
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      v40 = ManagedModeTrace::ManagedModeTrace(
              (ManagedModeTrace *)v83,
              (const struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011 *)v84);
      v41 = FSString::GetString(v40);
      v42 = ManagedModeTrace::ManagedModeTrace(
              (ManagedModeTrace *)v82,
              (const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *)&v68);
      v43 = FSString::GetString(v42);
      v44 = ManagedModeTrace::ManagedModeTrace(
              (ManagedModeTrace *)v81,
              (const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *)&v71);
      v45 = FSString::GetString(v44);
      WPP_SF_qsss(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v45, (__int64)v43, (__int64)v41);
      v13 = v68;
      v12 = 56;
      v14 = v71;
    }
    if ( (v12 & 0x20) != 0 )
    {
      v12 &= ~0x20u;
      FSString::~FSString((FSString *)v81, v39);
    }
    if ( (v12 & 0x10) != 0 )
    {
      v12 &= ~0x10u;
      FSString::~FSString((FSString *)v82, v39);
    }
    if ( (v12 & 8) != 0 )
    {
      v46 = (FSString *)v83;
LABEL_134:
      FSString::~FSString(v46, v39);
    }
  }
  RpcRevertToSelfEx(BindingHandle);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( v72 )
  {
    v53 = FSSaveDeviceConfiguration(v64, v72, a8);
    v18 = v53;
    if ( v53 < 0 )
    {
      if ( g_wppLevels )
      {
        v54 = 85;
        goto LABEL_142;
      }
LABEL_143:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
      goto LABEL_164;
    }
  }
  else
  {
    v53 = FSDeleteDeviceConfiguration(v64);
    v18 = v53;
    if ( v53 < 0 )
    {
      if ( g_wppLevels )
      {
        v54 = 84;
LABEL_142:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v54, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v53);
        goto LABEL_143;
      }
      goto LABEL_143;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    v59 = v13 == v14;
LABEL_153:
    if ( v59 )
      goto LABEL_155;
    goto LABEL_154;
  }
  v55 = v69;
  v56 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 21);
  v57 = *v56;
  v69 = 0;
  v58 = *v57;
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  v17 = v58(v56, &GUID_eb680aff_4b2b_460b_bd38_54b7a359ffeb, &v69);
  v18 = v17;
  if ( v17 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_164;
    v19 = 86;
    goto LABEL_163;
  }
  (*(void (__fastcall **)(__int64, struct IFSConfigurationKey *, _QWORD, _QWORD))(*(_QWORD *)v69 + 64LL))(
    v69,
    v64,
    v62,
    v36);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 72LL))(v69, 512);
  if ( v13 == v14 )
  {
    v59 = v62 == v36;
    goto LABEL_153;
  }
LABEL_154:
  (*(void (__fastcall **)(FSMonitorService *, _QWORD))(*(_QWORD *)this + 184LL))(this, 0);
LABEL_155:
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v60 = 88;
LABEL_166:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v60, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v18);
  }
LABEL_167:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v69);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v70);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&Size[1]);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v64);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&TokenInformation);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&BindingHandle);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18000b3c0  push    rbp
0x18000b3c2  push    rbx
0x18000b3c3  push    rsi
0x18000b3c4  push    rdi
0x18000b3c5  push    r12
0x18000b3c7  push    r13
0x18000b3c9  push    r14
0x18000b3cb  push    r15
0x18000b3cd  lea     rbp, [rsp-0A8h]
0x18000b3d5  sub     rsp, 1A8h
0x18000b3dc  mov     rax, cs:__security_cookie
0x18000b3e3  xor     rax, rsp
0x18000b3e6  mov     [rbp+0E0h+var_50], rax
0x18000b3ed  mov     rax, [rbp+0E0h+arg_28]
0x18000b3f4  xor     r10d, r10d
0x18000b3f7  mov     r13, [rbp+0E0h+arg_20]
0x18000b3fe  mov     ebx, r9d
0x18000b401  mov     [rsp+1E0h+TokenInformationLength], r10d
0x18000b406  xorps   xmm0, xmm0
0x18000b409  xorps   xmm1, xmm1
0x18000b40c  mov     [rbp+0E0h+Buf1], r8
0x18000b410  mov     r9, r8
0x18000b413  mov     dword ptr [rsp+1E0h+Size], ebx
0x18000b417  mov     r8, [rbp+0E0h+arg_30]
0x18000b41e  mov     r15, rcx
0x18000b421  xor     ecx, ecx
0x18000b423  mov     [rbp+0E0h+var_130], r8
0x18000b427  mov     [rbp+0E0h+var_80], rcx
0x18000b42b  mov     r14, rdx
0x18000b42e  mov     [rbp+0E0h+var_58], rcx
0x18000b435  mov     r12d, r10d
0x18000b438  mov     [rbp+0E0h+var_158], rax
0x18000b43c  mov     edi, r10d
0x18000b43f  mov     [rbp+0E0h+var_F0], r10
0x18000b443  mov     esi, r10d
0x18000b446  mov     [rbp+0E0h+var_F8], r10
0x18000b44a  mov     [rbp+0E0h+StringSid], r10
0x18000b44e  mov     [rbp+0E0h+var_100], r10
0x18000b452  mov     [rbp+0E0h+BindingHandle], r10
0x18000b456  mov     [rbp+0E0h+TokenInformation], r10
0x18000b45a  mov     [rsp+1E0h+TokenInformationLength], r10d
0x18000b45f  mov     [rsp+1E0h+var_170], r10
0x18000b464  mov     qword ptr [rsp+1E0h+Size+4], r10
0x18000b469  mov     [rbp+0E0h+var_150], r10
0x18000b46d  mov     [rbp+0E0h+var_138], r10
0x18000b471  movups  [rbp+0E0h+var_A0], xmm0
0x18000b475  mov     [rbp+0E0h+var_140], r10
0x18000b479  movups  [rbp+0E0h+var_90], xmm0
0x18000b47d  mov     [rbp+0E0h+var_148], r10
0x18000b481  movups  [rbp+0E0h+var_78], xmm1
0x18000b485  movups  [rbp+0E0h+var_68], xmm1
0x18000b489  cmp     cs:byte_18005E5A5, 8
0x18000b490  jb      short loc_18000B4EB
0x18000b492  test    rax, rax
0x18000b495  lea     rdx, aNull; "<null>"
0x18000b49c  mov     rcx, rdx
0x18000b49f  cmovnz  rcx, rax
0x18000b4a3  mov     eax, [rbp+0E0h+arg_38]
0x18000b4a9  mov     dword ptr [rsp+1E0h+var_190], eax; char
0x18000b4ad  test    r13, r13
0x18000b4b0  mov     qword ptr [rsp+1E0h+var_198], r8; char
0x18000b4b5  mov     qword ptr [rsp+1E0h+var_1A0], rcx; __int64
0x18000b4ba  cmovnz  rdx, r13
0x18000b4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4c5  mov     qword ptr [rsp+1E0h+var_1A8], rdx; __int64
0x18000b4ca  mov     dword ptr [rsp+1E0h+var_1B0], ebx; char
0x18000b4ce  mov     qword ptr [rsp+1E0h+var_1B8], r9; char
0x18000b4d3  mov     r9, r15
0x18000b4d6  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18000b4dd  mov     [rsp+1E0h+ReturnLength], r14; char
0x18000b4e2  call    WPP_SF_qqqDSSqd
0x18000b4e7  mov     rax, [rbp+0E0h+var_158]
0x18000b4eb  test    r13, r13
0x18000b4ee  jnz     short loc_18000B50E
0x18000b4f0  mov     eax, 80070057h
0x18000b4f5  mov     r14d, eax
0x18000b4f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b4ff  jb      loc_18000C062
0x18000b505  lea     edx, [r13+38h]
0x18000b509  jmp     loc_18000C044
0x18000b50e  test    rax, rax
0x18000b511  jnz     short loc_18000B532
0x18000b513  mov     eax, 80070057h
0x18000b518  mov     r14d, eax
0x18000b51b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b522  jb      loc_18000C062
0x18000b528  mov     edx, 39h ; '9'
0x18000b52d  jmp     loc_18000C044
0x18000b532  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x18000b539  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x18000b53e  xor     ecx, ecx
0x18000b540  test    al, al
0x18000b542  jz      short loc_18000B56D
0x18000b544  cmp     [rbp+0E0h+Buf1], rcx
0x18000b548  jz      short loc_18000B54E
0x18000b54a  test    ebx, ebx
0x18000b54c  jnz     short loc_18000B580
0x18000b54e  mov     eax, 80070057h
0x18000b553  mov     r14d, eax
0x18000b556  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b55d  jb      loc_18000C062
0x18000b563  mov     edx, 3Ah ; ':'
0x18000b568  jmp     loc_18000C044
0x18000b56d  cmp     [rbp+0E0h+Buf1], rcx
0x18000b571  jz      loc_18000C02E
0x18000b577  cmp     ebx, 20h ; ' '
0x18000b57a  jnz     loc_18000C02E
0x18000b580  cmp     [rbp+0E0h+var_130], rcx
0x18000b584  jnz     short loc_18000B5BA
0x18000b586  cmp     [rbp+0E0h+arg_38], ecx
0x18000b58c  jnz     short loc_18000B5C2
0x18000b58e  mov     r8, r14; void *
0x18000b591  mov     rdx, r13; unsigned __int16 *
0x18000b594  mov     rcx, r15; this
0x18000b597  call    ?InternalValidateSaveConfigurationOptions@FSMonitorService@@IEAAJPEBGPEAX@Z; FSMonitorService::InternalValidateSaveConfigurationOptions(ushort const *,void *)
0x18000b59c  mov     r14d, eax
0x18000b59f  test    eax, eax
0x18000b5a1  jns     short loc_18000B5E1
0x18000b5a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b5aa  jb      loc_18000C062
0x18000b5b0  mov     edx, 3Dh ; '='
0x18000b5b5  jmp     loc_18000C044
0x18000b5ba  cmp     [rbp+0E0h+arg_38], ecx
0x18000b5c0  jnz     short loc_18000B58E
0x18000b5c2  mov     eax, 80070057h
0x18000b5c7  mov     r14d, eax
0x18000b5ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b5d1  jb      loc_18000C062
0x18000b5d7  mov     edx, 3Ch ; '<'
0x18000b5dc  jmp     loc_18000C044
0x18000b5e1  mov     rbx, [rbp+0E0h+BindingHandle]
0x18000b5e5  test    rbx, rbx
0x18000b5e8  jz      short loc_18000B60A
0x18000b5ea  lea     rcx, [rbp+0E0h+var_120]; this
0x18000b5ee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000b5f3  lea     rcx, [rbp+0E0h+Binding]; Binding
0x18000b5f7  mov     [rbp+0E0h+Binding], rbx
0x18000b5fb  call    cs:__imp_RpcBindingFree
0x18000b601  lea     rcx, [rbp+0E0h+var_120]; this
0x18000b605  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000b60a  lea     rcx, [rbp+0E0h+BindingHandle]; Binding
0x18000b60e  mov     [rbp+0E0h+BindingHandle], rsi
0x18000b612  call    cs:__imp_RpcServerInqBindingHandle
0x18000b618  test    eax, eax
0x18000b61a  jz      short loc_18000B679
0x18000b61c  mov     rbx, [rbp+0E0h+BindingHandle]
0x18000b620  test    rbx, rbx
0x18000b623  jz      short loc_18000B645
0x18000b625  lea     rcx, [rbp+0E0h+Binding]; this
0x18000b629  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000b62e  lea     rcx, [rbp+0E0h+var_120]; Binding
0x18000b632  mov     [rbp+0E0h+var_120], rbx
0x18000b636  call    cs:__imp_RpcBindingFree
0x18000b63c  lea     rcx, [rbp+0E0h+Binding]; this
0x18000b640  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000b645  lea     rcx, [rbp+0E0h+BindingHandle]; Binding
0x18000b649  mov     [rbp+0E0h+BindingHandle], rsi
0x18000b64d  call    cs:__imp_RpcServerInqBindingHandle
0x18000b653  mov     r14d, eax
0x18000b656  or      r14d, 80010000h
0x18000b65d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b664  jb      loc_18000C062
0x18000b66a  mov     edx, 3Eh ; '>'
0x18000b66f  mov     dword ptr [rsp+1E0h+ReturnLength], r14d
0x18000b674  jmp     loc_18000C048
0x18000b679  mov     rcx, [rbp+0E0h+BindingHandle]; BindingHandle
0x18000b67d  call    cs:__imp_RpcImpersonateClient
0x18000b683  test    eax, eax
0x18000b685  jz      short loc_18000B6AF
0x18000b687  mov     rcx, [rbp+0E0h+BindingHandle]; BindingHandle
0x18000b68b  call    cs:__imp_RpcImpersonateClient
0x18000b691  mov     r14d, eax
0x18000b694  or      r14d, 80010000h
0x18000b69b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b6a2  jb      loc_18000C062
0x18000b6a8  mov     edx, 3Fh ; '?'
0x18000b6ad  jmp     short loc_18000B66F
0x18000b6af  xor     r9d, r9d; TokenInformationLength
0x18000b6b2  lea     rax, [rsp+1E0h+TokenInformationLength]
0x18000b6b7  xor     r8d, r8d; TokenInformation
0x18000b6ba  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x18000b6bf  lea     edx, [r9+1]; TokenInformationClass
0x18000b6c3  lea     rcx, [r9-5]; TokenHandle
0x18000b6c7  call    cs:__imp_GetTokenInformation
0x18000b6cd  test    eax, eax
0x18000b6cf  jnz     short loc_18000B71B
0x18000b6d1  call    cs:__imp_GetLastError
0x18000b6d7  mov     r14d, eax
0x18000b6da  test    eax, eax
0x18000b6dc  jle     short loc_18000B6E9
0x18000b6de  movzx   r14d, ax
0x18000b6e2  or      r14d, 80070000h
0x18000b6e9  mov     ecx, 80000000h
0x18000b6ee  lea     eax, [r14+rcx]
0x18000b6f2  test    ecx, eax
0x18000b6f4  jnz     short loc_18000B71B
0x18000b6f6  cmp     r14d, 8007007Ah
0x18000b6fd  jz      short loc_18000B71B
0x18000b6ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b706  jb      loc_18000C022
0x18000b70c  mov     edx, 40h ; '@'
0x18000b711  mov     dword ptr [rsp+1E0h+ReturnLength], r14d
0x18000b716  jmp     loc_18000C008
0x18000b71b  mov     edx, [rsp+1E0h+TokenInformationLength]
0x18000b71f  lea     rcx, [rbp+0E0h+var_120]
0x18000b723  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18000b728  mov     rdx, rax
0x18000b72b  lea     rcx, [rbp+0E0h+TokenInformation]
0x18000b72f  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18000b734  lea     rcx, [rbp+0E0h+var_120]
0x18000b738  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18000b73d  mov     rbx, [rbp+0E0h+TokenInformation]
0x18000b741  test    rbx, rbx
0x18000b744  jnz     short loc_18000B75E
0x18000b746  mov     r14d, 8007000Eh
0x18000b74c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b753  jb      loc_18000C022
0x18000b759  lea     edx, [rbx+41h]
0x18000b75c  jmp     short loc_18000B711
0x18000b75e  mov     r9d, [rsp+1E0h+TokenInformationLength]; TokenInformationLength
0x18000b763  lea     rax, [rsp+1E0h+TokenInformationLength]
0x18000b768  mov     r8, rbx; TokenInformation
0x18000b76b  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x18000b770  mov     edx, 1; TokenInformationClass
0x18000b775  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18000b77c  call    cs:__imp_GetTokenInformation
0x18000b782  test    eax, eax
0x18000b784  jnz     short loc_18000B7BA
0x18000b786  call    cs:__imp_GetLastError
0x18000b78c  mov     r14d, eax
0x18000b78f  test    eax, eax
0x18000b791  jle     short loc_18000B79E
0x18000b793  movzx   r14d, ax
0x18000b797  or      r14d, 80070000h
0x18000b79e  test    r14d, r14d
0x18000b7a1  jns     short loc_18000B7BA
0x18000b7a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b7aa  jb      loc_18000C022
0x18000b7b0  mov     edx, 42h ; 'B'
0x18000b7b5  jmp     loc_18000B711
0x18000b7ba  xor     edx, edx
0x18000b7bc  lea     rcx, [rbp+0E0h+StringSid]
0x18000b7c0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000b7c5  mov     rcx, [rbx]; Sid
0x18000b7c8  lea     rdx, [rbp+0E0h+StringSid]; StringSid
0x18000b7cc  call    cs:__imp_ConvertSidToStringSidW
0x18000b7d2  test    eax, eax
0x18000b7d4  jnz     short loc_18000B80A
0x18000b7d6  call    cs:__imp_GetLastError
0x18000b7dc  mov     r14d, eax
0x18000b7df  test    eax, eax
0x18000b7e1  jle     short loc_18000B7EE
0x18000b7e3  movzx   r14d, ax
0x18000b7e7  or      r14d, 80070000h
0x18000b7ee  test    r14d, r14d
0x18000b7f1  jns     short loc_18000B80A
0x18000b7f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b7fa  jb      loc_18000C022
0x18000b800  mov     edx, 43h ; 'C'
0x18000b805  jmp     loc_18000B711
0x18000b80a  mov     r11d, 7FFFFFFFh
0x18000b810  lea     r8, [rbp+0E0h+var_F0]; unsigned __int64 *
0x18000b814  mov     edx, r11d; unsigned __int64
0x18000b817  mov     rcx, r13; unsigned __int16 *
0x18000b81a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000b81f  mov     r14d, eax
0x18000b822  test    eax, eax
0x18000b824  jns     short loc_18000B83D
0x18000b826  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b82d  jb      loc_18000C022
0x18000b833  mov     edx, 44h ; 'D'
0x18000b838  jmp     loc_18000C004
0x18000b83d  mov     rbx, [rbp+0E0h+var_158]
0x18000b841  lea     r8, [rbp+0E0h+var_F8]; unsigned __int64 *
0x18000b845  mov     rcx, rbx; unsigned __int16 *
0x18000b848  mov     rdx, r11; unsigned __int64
0x18000b84b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000b850  mov     r14d, eax
0x18000b853  test    eax, eax
0x18000b855  jns     short loc_18000B86E
0x18000b857  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b85e  jb      loc_18000C022
0x18000b864  mov     edx, 45h ; 'E'
0x18000b869  jmp     loc_18000C004
0x18000b86e  mov     rcx, [rbp+0E0h+StringSid]; unsigned __int16 *
0x18000b872  lea     r8, [rbp+0E0h+var_100]; unsigned __int64 *
0x18000b876  mov     rdx, r11; unsigned __int64
0x18000b879  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000b87e  mov     r14d, eax
0x18000b881  test    eax, eax
0x18000b883  jns     short loc_18000B89C
0x18000b885  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b88c  jb      loc_18000C022
0x18000b892  mov     edx, 46h ; 'F'
0x18000b897  jmp     loc_18000C004
0x18000b89c  mov     rcx, [rsp+1E0h+var_170]
0x18000b8a1  mov     [rsp+1E0h+var_170], rsi
0x18000b8a6  test    rcx, rcx
0x18000b8a9  jz      short loc_18000B8B7
0x18000b8ab  mov     rax, [rcx]
  ... truncated ...
```
