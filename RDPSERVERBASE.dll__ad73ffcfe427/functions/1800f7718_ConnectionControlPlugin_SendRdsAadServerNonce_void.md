# ConnectionControlPlugin::SendRdsAadServerNonce(void)

- ea: `0x1800f7718`
- end: `0x1800f81f9`
- name: `?SendRdsAadServerNonce@ConnectionControlPlugin@@AEAAJXZ`
- size: `2785`
- prototype: `__int64 __fastcall(ConnectionControlPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f6d14`

## callees

- `0x180001308`
- `0x18000146c`
- `0x18000202c`
- `0x18000ce04`
- `0x18000ce34`
- `0x18000e4ec`
- `0x18002aafc`
- `0x18004f5bc`
- `0x18007e9e0`
- `0x18007f390`
- `0x18007f6f0`
- `0x18007f6fc`
- `0x1800f4edc`
- `0x1800f4f08`
- `0x1800f4f24`
- `0x1800f5068`
- `0x1800f6004`
- `0x1800f7718`
- `0x180159e30`
- `0x18015cee4`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800f77cb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800f81ac`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800f77cb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800f81ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f7c63`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f7d8d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f7c63`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f7d8d`
- `OLEAUT32!__imp_VariantInit` at `0x1800f7bff`
- `OLEAUT32!__imp_VariantInit` at `0x1800f7bff`
- `OLEAUT32!__imp_VariantClear` at `0x1800f7c90`
- `OLEAUT32!__imp_VariantClear` at `0x1800f7e5c`
- `OLEAUT32!__imp_VariantClear` at `0x1800f7c90`
- `OLEAUT32!__imp_VariantClear` at `0x1800f7e5c`

## string_xrefs

- `0x1800f7840`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f78ec`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f7a0f`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f7ae5`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f7cfc`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f7e01`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f7fed`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f80d4`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f8143`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f7d86`: `a4a365df-50f1-4397-bc59-1a1564b8bb9c;termsrv.wvd.microsoft.com`

## pseudocode

```c
__int64 __fastcall ConnectionControlPlugin::SendRdsAadServerNonce(ConnectionControlPlugin *this)
{
  __int64 v2; // rbx
  __int64 **v3; // r12
  struct _GUID v4; // xmm0
  int v5; // r8d
  int v6; // r9d
  int InstanceOfCloudAPHelper; // r14d
  __int64 v8; // rdi
  const char *v9; // rax
  __int16 *v10; // rdx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, struct IRdsAuthorizationCallback **); // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 (__fastcall ***v15)(_QWORD, GUID *, struct IRdsLoggingCallback **); // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // edx
  const unsigned __int16 *v20; // rdi
  int v21; // eax
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  int v30; // r8d
  int v31; // r9d
  void *v32; // rcx
  __int64 *v33; // rbx
  __int64 v34; // rax
  __int64 (__fastcall *v35)(__int64 *, _QWORD, _QWORD, VARIANTARG *, rsize_t *, _BYTE *); // rdi
  int v36; // ebx
  int v37; // r8d
  int v38; // r9d
  int v39; // eax
  int v40; // edi
  char *v41; // rax
  int v42; // r8d
  int v43; // r9d
  void *v44; // rbx
  int v45; // r8d
  int v46; // r9d
  int v47; // ecx
  __int16 *v48; // rdx
  const char *v49; // rax
  unsigned int v51; // [rsp+28h] [rbp-D8h]
  int v52; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v53; // [rsp+58h] [rbp-A8h] BYREF
  const char *v54; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v55[2]; // [rsp+68h] [rbp-98h] BYREF
  const char *v56; // [rsp+70h] [rbp-90h] BYREF
  const char *v57; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v58[8]; // [rsp+80h] [rbp-80h] BYREF
  struct ICloudAPHelper *v59; // [rsp+88h] [rbp-78h] BYREF
  rsize_t SourceSize; // [rsp+90h] [rbp-70h] BYREF
  struct IRdsLoggingCallback *v61; // [rsp+98h] [rbp-68h] BYREF
  int v62; // [rsp+A0h] [rbp-60h] BYREF
  struct IRdsAuthorizationCallback *v63; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-50h] BYREF
  void *Block; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v67; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v69; // [rsp+E8h] [rbp-18h] BYREF
  GUID ActivityId; // [rsp+F8h] [rbp-8h] BYREF

  v2 = 0;
  v67 = 0;
  v64 = 0;
  v66 = 0;
  Block = 0;
  LODWORD(SourceSize) = 0;
  v58[0] = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v64);
  v61 = (ConnectionControlPlugin *)((char *)this + 120);
  CTSCriticalSection::Lock((ConnectionControlPlugin *)((char *)this + 120));
  TCntPtr<IRDPCoreVirtualChannel>::operator=(&v67, *((_QWORD *)this + 11));
  if ( *((_QWORD *)this + 21) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v64);
    v2 = *((_QWORD *)this + 21);
    v64 = v2;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v64);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v61);
  ActivityId = (GUID)*((_OWORD *)this + 11);
  EventActivityIdControl(4u, &ActivityId);
  v3 = (__int64 **)((char *)this + 192);
  if ( !*((_QWORD *)this + 24) )
  {
    v4 = (struct _GUID)*((_OWORD *)this + 11);
    v59 = 0;
    v69 = v4;
    InstanceOfCloudAPHelper = GetInstanceOfCloudAPHelper(&v69, &v59);
    if ( InstanceOfCloudAPHelper < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v56 = "SendRdsAadServerNonce";
        v57 = "Failed to get instance of CloudAPHelper";
        v52 = 566;
        *(_QWORD *)v55 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
        v54 = "Error HResult failed";
        LODWORD(v53) = InstanceOfCloudAPHelper;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)word_1802841AA,
          v5,
          v6,
          (__int64)&v54,
          (__int64)&v53,
          (__int64)v55,
          (__int64)&v52,
          (__int64)&v56,
          (__int64)&v57);
      }
      goto LABEL_11;
    }
    v8 = v67;
    if ( !v67 )
    {
      InstanceOfCloudAPHelper = -2147467261;
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_11:
        TCntPtr<IRdpVCMgr>::SafeRelease(&v59);
        goto LABEL_62;
      }
      LODWORD(v53) = 568;
      *(_QWORD *)v55 = "SendRdsAadServerNonce";
      v9 = "invalid spRDPStack pointer";
      v10 = &word_1802840F6;
LABEL_10:
      v54 = v9;
      v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
      v57 = "Error condition failed";
      v52 = -2147467261;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147467261,
        (_DWORD)v10,
        v5,
        v6,
        (__int64)&v57,
        (__int64)&v52,
        (__int64)&v56,
        (__int64)&v53,
        (__int64)v55,
        (__int64)&v54);
      goto LABEL_11;
    }
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 128LL))(v67) )
    {
      InstanceOfCloudAPHelper = -2147467261;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_11;
      LODWORD(v53) = 569;
      *(_QWORD *)v55 = "SendRdsAadServerNonce";
      v9 = "invalid spRDPStack NetStream pointer";
      v10 = (__int16 *)&unk_180284150;
      goto LABEL_10;
    }
    v63 = 0;
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IRdsAuthorizationCallback **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 128LL))(v8);
    InstanceOfCloudAPHelper = (**v11)(v11, &IID_IRdsAuthorizationCallback, &v63);
    if ( InstanceOfCloudAPHelper < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v53) = 573;
        v54 = "Failed to get instance of RdsAuthorizationCallback";
        *(_QWORD *)v55 = "SendRdsAadServerNonce";
        v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
        v52 = InstanceOfCloudAPHelper;
        v57 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v12,
          (unsigned int)&dword_18028409C,
          v13,
          v14,
          (__int64)&v57,
          (__int64)&v52,
          (__int64)&v56,
          (__int64)&v53,
          (__int64)v55,
          (__int64)&v54);
      }
      goto LABEL_43;
    }
    v61 = 0;
    v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IRdsLoggingCallback **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 128LL))(v8);
    InstanceOfCloudAPHelper = (**v15)(v15, &IID_IRdsLoggingCallback, &v61);
    if ( InstanceOfCloudAPHelper < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v53) = 577;
        v54 = "Failed to get instance of RdsLoggingCallback";
        *(_QWORD *)v55 = "SendRdsAadServerNonce";
        v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
        v52 = InstanceOfCloudAPHelper;
        v57 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v16,
          (unsigned int)word_180283FFA,
          v17,
          v18,
          (__int64)&v57,
          (__int64)&v52,
          (__int64)&v56,
          (__int64)&v53,
          (__int64)v55,
          (__int64)&v54);
      }
      goto LABEL_42;
    }
    v57 = 0;
    v19 = 0;
    v62 = 0;
    v20 = 0;
    if ( v2 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v2 + 32LL))(
              v2,
              L"EnableRdsAadAuthResourceAppIDValidation",
              &v62);
      if ( v21 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v53) = v21;
        v54 = "SendRdsAadServerNonce";
        *(_QWORD *)v55 = "Failed to get CONN_PROPERTY_ENABLE_RDSAADAUTH_RESOURCE_APP_ID_VALIDATION property";
        v56 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&dword_180284054,
          v22,
          v23,
          (__int64)&v56,
          (__int64)v55,
          (__int64)&v53,
          (__int64)&v54);
      }
      v19 = v62;
      if ( v62 )
      {
        VariantInit(&pvarg);
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v2 + 24LL))(
               v2,
               L"AllowedRdsAadAuthResourceAppIDs",
               &pvarg) >= 0
          && pvarg.vt == 8 )
        {
          if ( (unsigned int)CallbackContext > 4 )
          {
            v54 = "Successfully set CONN_PROPERTY_ALLOWED_RDSAADAUTH_RESOURCE_APP_IDS property value";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v24,
              (unsigned int)&word_180283F9E,
              v25,
              v26,
              (__int64)&v54);
          }
          v53 = SysAllocString(pvarg.bstrVal);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v57,
            &v53);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
          v20 = (const unsigned __int16 *)v57;
        }
        else
        {
          if ( (unsigned int)CallbackContext > 3 )
          {
            v54 = "Failed to get CONN_PROPERTY_ALLOWED_RDSAADAUTH_RESOURCE_APP_IDS property value, falling back to CONN_P"
                  "ROPERTY_RDS_AAD_AUTH_RESOURCE_APP_ID_DEFAULT";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v24,
              (unsigned int)&dword_180283FCC,
              v25,
              v26,
              (__int64)&v54);
          }
          v53 = SysAllocString(L"a4a365df-50f1-4397-bc59-1a1564b8bb9c;termsrv.wvd.microsoft.com");
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v57,
            &v53);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
          v20 = (const unsigned __int16 *)v57;
          if ( !v57 )
          {
            InstanceOfCloudAPHelper = -2147024882;
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v53) = 611;
              v54 = "Could not allocate buffer for valid RDS AAD Auth Resource App IDs";
              v52 = -2147024882;
              *(_QWORD *)v55 = "SendRdsAadServerNonce";
              v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
              *(_QWORD *)&v69.Data1 = "Error condition failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                -2147024882,
                (unsigned int)&dword_180283F44,
                v30,
                v31,
                (__int64)&v69,
                (__int64)&v52,
                (__int64)&v56,
                (__int64)&v53,
                (__int64)v55,
                (__int64)&v54);
            }
            VariantClear(&pvarg);
            goto LABEL_41;
          }
        }
        VariantClear(&pvarg);
        v19 = v62;
      }
    }
    InstanceOfCloudAPHelper = GetInstanceOfRdsAadAuthServer(
                                v20,
                                v19,
                                v59,
                                v63,
                                v61,
                                v51,
                                (struct IRdsAadAuthServer **)this + 24);
    if ( InstanceOfCloudAPHelper < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v53) = 625;
        *(_QWORD *)&v69.Data1 = "Failed to get instance of RdsAadAuthServer";
        v52 = InstanceOfCloudAPHelper;
        v54 = "SendRdsAadServerNonce";
        *(_QWORD *)v55 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
        v56 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v27,
          (unsigned int)word_180283EA2,
          v28,
          v29,
          (__int64)&v56,
          (__int64)&v52,
          (__int64)v55,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v69);
      }
LABEL_41:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v57);
LABEL_42:
      TCntPtr<IRdpVCMgr>::SafeRelease(&v61);
LABEL_43:
      TCntPtr<IRdpVCMgr>::SafeRelease(&v63);
      goto LABEL_11;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v57);
    TCntPtr<IRdpVCMgr>::SafeRelease(&v61);
    TCntPtr<IRdpVCMgr>::SafeRelease(&v63);
    TCntPtr<IRdpVCMgr>::SafeRelease(&v59);
  }
  v32 = Block;
  v33 = *v3;
  v34 = **v3;
  *(_QWORD *)&pvarg.vt = 0;
  Block = 0;
  v35 = *(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, VARIANTARG *, rsize_t *, _BYTE *))(v34 + 32);
  pvarg.llVal = (LONGLONG)&Block;
  if ( v32 )
    operator delete(v32);
  v36 = v35(v33, 0, 0, &pvarg, &SourceSize, v58);
  utl::out_ptr_t<utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>,unsigned char *,>::~out_ptr_t<utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>,unsigned char *,>(&pvarg);
  if ( v36 < 0 )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v53) = v36;
      *(_QWORD *)&v69.Data1 = "SendRdsAadServerNonce";
      *(_QWORD *)v55 = "HResult failed but continue";
      v54 = "RDS AAD Server handshake failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)&dword_180283EFC,
        v37,
        v38,
        (__int64)v55,
        (__int64)&v54,
        (__int64)&v53,
        (__int64)&v69);
    }
    v39 = (*(__int64 (__fastcall **)(__int64 *))(**v3 + 56))(*v3);
    InstanceOfCloudAPHelper = ConnectionControlPlugin::LogRdsAadDiagnosticsFailure(this, v36, v39);
    goto LABEL_62;
  }
  v40 = SourceSize;
  v41 = (char *)operator new[]((unsigned int)SourceSize + 9LL);
  v44 = v41;
  if ( v41 )
  {
    *(_WORD *)v41 = 38;
    *((_DWORD *)v41 + 1) = SourceSize;
    memcpy_s(v41 + 8, (unsigned int)SourceSize, Block, (unsigned int)SourceSize);
    *(_QWORD *)&v69.Data1 = (char *)this + 120;
    CTSCriticalSection::Lock((ConnectionControlPlugin *)((char *)this + 120));
    TCntPtr<IRDPCoreVirtualChannel>::operator=(&v66, *((_QWORD *)this + 12));
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v69);
    if ( v66 )
    {
      InstanceOfCloudAPHelper = (*(__int64 (__fastcall **)(__int64, _QWORD, void *, _QWORD))(*(_QWORD *)v66 + 24LL))(
                                  v66,
                                  (unsigned int)(v40 + 9),
                                  v44,
                                  0);
      if ( InstanceOfCloudAPHelper >= 0 )
        goto LABEL_62;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v53) = 658;
        *(_QWORD *)&v69.Data1 = "Failed to send RDS AAD server nonce";
        v48 = &word_180283DEE;
        v52 = InstanceOfCloudAPHelper;
        v54 = "SendRdsAadServerNonce";
        *(_QWORD *)v55 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
        v49 = "Error HResult failed";
        goto LABEL_60;
      }
    }
    else
    {
      v47 = -2147467261;
      InstanceOfCloudAPHelper = -2147467261;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v53) = 655;
        *(_QWORD *)&v69.Data1 = "invalid spChannel pointer";
        v48 = (__int16 *)&dword_180283D94;
        v52 = -2147467261;
        v54 = "SendRdsAadServerNonce";
        *(_QWORD *)v55 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
        v49 = "Error condition failed";
LABEL_60:
        v56 = v49;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v47,
          (_DWORD)v48,
          v45,
          v46,
          (__int64)&v56,
          (__int64)&v52,
          (__int64)v55,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v69);
      }
    }
    operator delete(v44);
    goto LABEL_62;
  }
  InstanceOfCloudAPHelper = -2147024882;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v53) = 644;
    *(_QWORD *)&v69.Data1 = "Allocation of RDS AAD server nonce buffer has failed";
    v52 = -2147024882;
    v54 = "SendRdsAadServerNonce";
    *(_QWORD *)v55 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
    v56 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      -2147024882,
      (unsigned int)&unk_180283E48,
      v42,
      v43,
      (__int64)&v56,
      (__int64)&v52,
      (__int64)v55,
      (__int64)&v53,
      (__int64)&v54,
      (__int64)&v69);
  }
LABEL_62:
  EventActivityIdControl(2u, &ActivityId);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v64);
  utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>(&Block);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v66);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v67);
  return (unsigned int)InstanceOfCloudAPHelper;
}

```

## disassembly

```asm
0x1800f7718  push    rbp
0x1800f771a  push    rbx
0x1800f771b  push    rsi
0x1800f771c  push    rdi
0x1800f771d  push    r12
0x1800f771f  push    r13
0x1800f7721  push    r14
0x1800f7723  push    r15
0x1800f7725  lea     rbp, [rsp-18h]
0x1800f772a  sub     rsp, 118h
0x1800f7731  mov     rax, cs:__security_cookie
0x1800f7738  xor     rax, rsp
0x1800f773b  mov     [rbp+50h+var_48], rax
0x1800f773f  xor     r13d, r13d
0x1800f7742  mov     r15, rcx
0x1800f7745  mov     ebx, r13d
0x1800f7748  mov     [rbp+50h+var_88], r13
0x1800f774c  lea     rcx, [rbp+50h+var_A0]
0x1800f7750  mov     [rbp+50h+var_A0], rbx
0x1800f7754  mov     [rbp+50h+var_90], r13
0x1800f7758  mov     [rbp+50h+Block], r13
0x1800f775c  mov     dword ptr [rbp+50h+SourceSize], r13d
0x1800f7760  mov     [rbp+50h+var_D0], r13b
0x1800f7764  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800f7769  lea     rsi, [r15+78h]
0x1800f776d  mov     rcx, rsi; this
0x1800f7770  mov     [rbp+50h+var_B8], rsi
0x1800f7774  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800f7779  mov     rdx, [r15+58h]
0x1800f777d  lea     rcx, [rbp+50h+var_88]
0x1800f7781  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800f7786  cmp     [r15+0A8h], r13
0x1800f778d  jz      short loc_1800F77AC
0x1800f778f  lea     rcx, [rbp+50h+var_A0]
0x1800f7793  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f7798  mov     rbx, [r15+0A8h]
0x1800f779f  lea     rcx, [rbp+50h+var_A0]
0x1800f77a3  mov     [rbp+50h+var_A0], rbx
0x1800f77a7  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800f77ac  lea     rcx, [rbp+50h+var_B8]; this
0x1800f77b0  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800f77b5  movups  xmm0, xmmword ptr [r15+0B0h]
0x1800f77bd  lea     rdx, [rbp+50h+ActivityId]; ActivityId
0x1800f77c1  mov     ecx, 4; ControlCode
0x1800f77c6  movdqu  xmmword ptr [rbp+50h+ActivityId.Data1], xmm0
0x1800f77cb  call    cs:__imp_EventActivityIdControl
0x1800f77d1  lea     r12, [r15+0C0h]
0x1800f77d8  lea     rdi, aSendrdsaadserv; "SendRdsAadServerNonce"
0x1800f77df  lea     r14, aHresultFailedB; "HResult failed but continue"
0x1800f77e6  cmp     [r12], r13
0x1800f77ea  jnz     loc_1800F7EAF
0x1800f77f0  movups  xmm0, xmmword ptr [r15+0B0h]
0x1800f77f8  lea     rdx, [rbp+50h+var_C8]; struct ICloudAPHelper **
0x1800f77fc  mov     [rbp+50h+var_C8], r13
0x1800f7800  lea     rcx, [rbp+50h+var_68]; struct _GUID *
0x1800f7804  movdqu  xmmword ptr [rbp+50h+var_68.Data1], xmm0
0x1800f7809  call    ?GetInstanceOfCloudAPHelper@@YAJAEBU_GUID@@PEAPEAVICloudAPHelper@@@Z; GetInstanceOfCloudAPHelper(_GUID const &,ICloudAPHelper * *)
0x1800f780e  mov     r14d, eax
0x1800f7811  test    eax, eax
0x1800f7813  jns     loc_1800F78A1
0x1800f7819  mov     ecx, cs:CallbackContext
0x1800f781f  cmp     ecx, 2
0x1800f7822  jbe     loc_1800F7949
0x1800f7828  lea     rax, aFailedToGetIns; "Failed to get instance of CloudAPHelper"
0x1800f782f  mov     [rsp+150h+var_E0], rdi
0x1800f7834  mov     [rsp+150h+var_D8], rax
0x1800f7839  lea     rdx, word_1802841AA
0x1800f7840  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f7847  mov     [rsp+150h+var_100], 236h
0x1800f784f  mov     qword ptr [rsp+150h+var_E8], rax
0x1800f7854  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f785b  mov     [rsp+150h+var_F0], rax
0x1800f7860  lea     rax, [rsp+150h+var_D8]
0x1800f7865  mov     [rsp+150h+var_108], rax
0x1800f786a  lea     rax, [rsp+150h+var_E0]
0x1800f786f  mov     [rsp+150h+var_110], rax
0x1800f7874  lea     rax, [rsp+150h+var_100]
0x1800f7879  mov     [rsp+150h+var_118], rax
0x1800f787e  lea     rax, [rsp+150h+var_E8]
0x1800f7883  mov     [rsp+150h+var_120], rax
0x1800f7888  lea     rax, [rsp+150h+var_F8]
0x1800f788d  mov     qword ptr [rsp+150h+var_128], rax
0x1800f7892  lea     rax, [rsp+150h+var_F0]
0x1800f7897  mov     dword ptr [rsp+150h+var_F8], r14d
0x1800f789c  jmp     loc_1800F793F
0x1800f78a1  mov     rdi, [rbp+50h+var_88]
0x1800f78a5  test    rdi, rdi
0x1800f78a8  jnz     loc_1800F7957
0x1800f78ae  mov     eax, cs:CallbackContext
0x1800f78b4  mov     ecx, 80004003h
0x1800f78b9  mov     r14d, ecx
0x1800f78bc  cmp     eax, 2
0x1800f78bf  jbe     loc_1800F7949
0x1800f78c5  lea     rdx, aSendrdsaadserv; "SendRdsAadServerNonce"
0x1800f78cc  mov     dword ptr [rsp+150h+var_F8], 238h
0x1800f78d4  mov     qword ptr [rsp+150h+var_E8], rdx
0x1800f78d9  lea     rax, aInvalidSprdpst; "invalid spRDPStack pointer"
0x1800f78e0  lea     rdx, word_1802840F6
0x1800f78e7  mov     [rsp+150h+var_F0], rax
0x1800f78ec  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f78f3  mov     [rsp+150h+var_E0], rax
0x1800f78f8  lea     rax, aErrorCondition; "Error condition failed"
0x1800f78ff  mov     [rsp+150h+var_D8], rax
0x1800f7904  lea     rax, [rsp+150h+var_F0]
0x1800f7909  mov     [rsp+150h+var_108], rax
0x1800f790e  lea     rax, [rsp+150h+var_E8]
0x1800f7913  mov     [rsp+150h+var_110], rax
0x1800f7918  lea     rax, [rsp+150h+var_F8]
0x1800f791d  mov     [rsp+150h+var_118], rax
0x1800f7922  lea     rax, [rsp+150h+var_E0]
0x1800f7927  mov     [rsp+150h+var_120], rax
0x1800f792c  lea     rax, [rsp+150h+var_100]
0x1800f7931  mov     qword ptr [rsp+150h+var_128], rax
0x1800f7936  lea     rax, [rsp+150h+var_D8]
0x1800f793b  mov     [rsp+150h+var_100], ecx
0x1800f793f  mov     [rsp+150h+var_130], rax
0x1800f7944  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800f7949  lea     rcx, [rbp+50h+var_C8]
0x1800f794d  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f7952  jmp     loc_1800F81A3
0x1800f7957  mov     rax, [rdi]
0x1800f795a  mov     rcx, rdi
0x1800f795d  mov     rax, [rax+80h]
0x1800f7964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7969  test    rax, rax
0x1800f796c  jnz     short loc_1800F79A8
0x1800f796e  mov     eax, cs:CallbackContext
0x1800f7974  mov     ecx, 80004003h
0x1800f7979  mov     r14d, ecx
0x1800f797c  cmp     eax, 2
0x1800f797f  jbe     short loc_1800F7949
0x1800f7981  lea     rdx, aSendrdsaadserv; "SendRdsAadServerNonce"
0x1800f7988  mov     dword ptr [rsp+150h+var_F8], 239h
0x1800f7990  mov     qword ptr [rsp+150h+var_E8], rdx
0x1800f7995  lea     rax, aInvalidSprdpst_0; "invalid spRDPStack NetStream pointer"
0x1800f799c  lea     rdx, unk_180284150
0x1800f79a3  jmp     loc_1800F78E7
0x1800f79a8  mov     [rbp+50h+var_A8], r13
0x1800f79ac  mov     rcx, rdi
0x1800f79af  mov     rax, [rdi]
0x1800f79b2  mov     rax, [rax+80h]
0x1800f79b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f79be  mov     r9, rax
0x1800f79c1  lea     r8, [rbp+50h+var_A8]
0x1800f79c5  lea     rdx, IID_IRdsAuthorizationCallback
0x1800f79cc  mov     rcx, [rax]
0x1800f79cf  mov     rax, [rcx]
0x1800f79d2  mov     rcx, r9
0x1800f79d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f79da  mov     r14d, eax
0x1800f79dd  test    eax, eax
0x1800f79df  jns     loc_1800F7A7E
0x1800f79e5  mov     eax, cs:CallbackContext
0x1800f79eb  cmp     eax, 2
0x1800f79ee  jbe     loc_1800F7E75
0x1800f79f4  lea     rax, aFailedToGetIns_2; "Failed to get instance of RdsAuthorizat"...
0x1800f79fb  mov     dword ptr [rsp+150h+var_F8], 23Dh
0x1800f7a03  mov     [rsp+150h+var_F0], rax
0x1800f7a08  lea     rdx, aSendrdsaadserv; "SendRdsAadServerNonce"
0x1800f7a0f  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f7a16  mov     qword ptr [rsp+150h+var_E8], rdx
0x1800f7a1b  mov     [rsp+150h+var_E0], rax
0x1800f7a20  lea     rdx, dword_18028409C
0x1800f7a27  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f7a2e  mov     [rsp+150h+var_100], r14d
0x1800f7a33  mov     [rsp+150h+var_D8], rax
0x1800f7a38  lea     rax, [rsp+150h+var_F0]
0x1800f7a3d  mov     [rsp+150h+var_108], rax
0x1800f7a42  lea     rax, [rsp+150h+var_E8]
0x1800f7a47  mov     [rsp+150h+var_110], rax
0x1800f7a4c  lea     rax, [rsp+150h+var_F8]
0x1800f7a51  mov     [rsp+150h+var_118], rax
0x1800f7a56  lea     rax, [rsp+150h+var_E0]
0x1800f7a5b  mov     [rsp+150h+var_120], rax
0x1800f7a60  lea     rax, [rsp+150h+var_100]
0x1800f7a65  mov     qword ptr [rsp+150h+var_128], rax
0x1800f7a6a  lea     rax, [rsp+150h+var_D8]
0x1800f7a6f  mov     [rsp+150h+var_130], rax
0x1800f7a74  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800f7a79  jmp     loc_1800F7E75
0x1800f7a7e  mov     [rbp+50h+var_B8], r13
0x1800f7a82  mov     rcx, rdi
0x1800f7a85  mov     rax, [rdi]
0x1800f7a88  mov     rax, [rax+80h]
0x1800f7a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7a94  mov     r9, rax
0x1800f7a97  lea     r8, [rbp+50h+var_B8]
0x1800f7a9b  lea     rdx, IID_IRdsLoggingCallback
0x1800f7aa2  mov     rcx, [rax]
0x1800f7aa5  mov     rax, [rcx]
0x1800f7aa8  mov     rcx, r9
0x1800f7aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7ab0  mov     r14d, eax
0x1800f7ab3  test    eax, eax
0x1800f7ab5  jns     loc_1800F7B54
0x1800f7abb  mov     eax, cs:CallbackContext
0x1800f7ac1  cmp     eax, 2
0x1800f7ac4  jbe     loc_1800F7E6C
0x1800f7aca  lea     rax, aFailedToGetIns_1; "Failed to get instance of RdsLoggingCal"...
0x1800f7ad1  mov     dword ptr [rsp+150h+var_F8], 241h
0x1800f7ad9  mov     [rsp+150h+var_F0], rax
0x1800f7ade  lea     rdx, aSendrdsaadserv; "SendRdsAadServerNonce"
0x1800f7ae5  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f7aec  mov     qword ptr [rsp+150h+var_E8], rdx
0x1800f7af1  mov     [rsp+150h+var_E0], rax
0x1800f7af6  lea     rdx, word_180283FFA
0x1800f7afd  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f7b04  mov     [rsp+150h+var_100], r14d
0x1800f7b09  mov     [rsp+150h+var_D8], rax
0x1800f7b0e  lea     rax, [rsp+150h+var_F0]
0x1800f7b13  mov     [rsp+150h+var_108], rax
0x1800f7b18  lea     rax, [rsp+150h+var_E8]
0x1800f7b1d  mov     [rsp+150h+var_110], rax
0x1800f7b22  lea     rax, [rsp+150h+var_F8]
0x1800f7b27  mov     [rsp+150h+var_118], rax
0x1800f7b2c  lea     rax, [rsp+150h+var_E0]
0x1800f7b31  mov     [rsp+150h+var_120], rax
0x1800f7b36  lea     rax, [rsp+150h+var_100]
0x1800f7b3b  mov     qword ptr [rsp+150h+var_128], rax
0x1800f7b40  lea     rax, [rsp+150h+var_D8]
0x1800f7b45  mov     [rsp+150h+var_130], rax
0x1800f7b4a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800f7b4f  jmp     loc_1800F7E6C
0x1800f7b54  mov     [rsp+150h+var_D8], r13
0x1800f7b59  mov     edx, r13d
0x1800f7b5c  mov     [rbp+50h+var_B0], edx
0x1800f7b5f  mov     rdi, r13
0x1800f7b62  test    rbx, rbx
0x1800f7b65  jz      loc_1800F7C99
0x1800f7b6b  mov     rax, [rbx]
0x1800f7b6e  lea     r8, [rbp+50h+var_B0]
0x1800f7b72  lea     rdx, aEnablerdsaadau; "EnableRdsAadAuthResourceAppIDValidation"
0x1800f7b79  mov     rcx, rbx
0x1800f7b7c  mov     rax, [rax+20h]
0x1800f7b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7b85  test    eax, eax
0x1800f7b87  jns     short loc_1800F7BF0
0x1800f7b89  mov     ecx, cs:CallbackContext
0x1800f7b8f  cmp     ecx, 3
0x1800f7b92  jbe     short loc_1800F7BF0
0x1800f7b94  mov     dword ptr [rsp+150h+var_F8], eax
0x1800f7b98  lea     rdx, aSendrdsaadserv; "SendRdsAadServerNonce"
0x1800f7b9f  lea     rax, aFailedToGetCon_10; "Failed to get CONN_PROPERTY_ENABLE_RDSA"...
0x1800f7ba6  mov     [rsp+150h+var_F0], rdx
0x1800f7bab  mov     qword ptr [rsp+150h+var_E8], rax
0x1800f7bb0  lea     rdx, dword_180284054
0x1800f7bb7  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800f7bbe  mov     [rsp+150h+var_E0], rax
0x1800f7bc3  lea     rax, [rsp+150h+var_F0]
0x1800f7bc8  mov     [rsp+150h+var_118], rax
0x1800f7bcd  lea     rax, [rsp+150h+var_F8]
0x1800f7bd2  mov     [rsp+150h+var_120], rax
0x1800f7bd7  lea     rax, [rsp+150h+var_E8]
0x1800f7bdc  mov     qword ptr [rsp+150h+var_128], rax; unsigned int
0x1800f7be1  lea     rax, [rsp+150h+var_E0]
0x1800f7be6  mov     [rsp+150h+var_130], rax
0x1800f7beb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800f7bf0  mov     edx, [rbp+50h+var_B0]
0x1800f7bf3  test    edx, edx
0x1800f7bf5  jz      loc_1800F7C99
0x1800f7bfb  lea     rcx, [rbp+50h+pvarg]; pvarg
0x1800f7bff  call    cs:__imp_VariantInit
0x1800f7c05  mov     rax, [rbx]
0x1800f7c08  lea     r8, [rbp+50h+pvarg]
0x1800f7c0c  lea     rdx, aAllowedrdsaada; "AllowedRdsAadAuthResourceAppIDs"
0x1800f7c13  mov     rcx, rbx
0x1800f7c16  mov     rax, [rax+18h]
0x1800f7c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7c1f  test    eax, eax
0x1800f7c21  js      loc_1800F7D59
0x1800f7c27  cmp     word ptr [rbp+50h+pvarg], 8
0x1800f7c2c  jnz     loc_1800F7D59
0x1800f7c32  mov     eax, cs:CallbackContext
0x1800f7c38  cmp     eax, 4
0x1800f7c3b  jbe     short loc_1800F7C5F
0x1800f7c3d  lea     rax, aSuccessfullySe; "Successfully set CONN_PROPERTY_ALLOWED_"...
0x1800f7c44  mov     [rsp+150h+var_F0], rax
0x1800f7c49  lea     rdx, word_180283F9E
0x1800f7c50  lea     rax, [rsp+150h+var_F0]
0x1800f7c55  mov     [rsp+150h+var_130], rax
0x1800f7c5a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800f7c5f  mov     rcx, qword ptr [rbp+50h+pvarg+8]; psz
0x1800f7c63  call    cs:__imp_SysAllocString
0x1800f7c69  lea     rdx, [rsp+150h+var_F8]
0x1800f7c6e  mov     [rsp+150h+var_F8], rax
0x1800f7c73  lea     rcx, [rsp+150h+var_D8]
0x1800f7c78  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800f7c7d  lea     rcx, [rsp+150h+var_F8]
0x1800f7c82  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f7c87  mov     rdi, [rsp+150h+var_D8]
0x1800f7c8c  lea     rcx, [rbp+50h+pvarg]; pvarg
0x1800f7c90  call    cs:__imp_VariantClear
0x1800f7c96  mov     edx, [rbp+50h+var_B0]; int
0x1800f7c99  mov     rax, [rbp+50h+var_B8]
0x1800f7c9d  mov     rcx, rdi; unsigned __int16 *
0x1800f7ca0  mov     r9, [rbp+50h+var_A8]; struct IRdsAuthorizationCallback *
0x1800f7ca4  mov     r8, [rbp+50h+var_C8]; struct ICloudAPHelper *
0x1800f7ca8  mov     [rsp+150h+var_120], r12; struct IRdsAadAuthServer **
0x1800f7cad  mov     [rsp+150h+var_130], rax; struct IRdsLoggingCallback *
0x1800f7cb2  call    ?GetInstanceOfRdsAadAuthServer@@YAJPEBGHPEAVICloudAPHelper@@PEAVIRdsAuthorizationCallback@@PEAVIRdsLoggingCallback@@KPEAPEAVIRdsAadAuthServer@@@Z; GetInstanceOfRdsAadAuthServer(ushort const *,int,ICloudAPHelper *,IRdsAuthorizationCallback *,IRdsLoggingCallback *,ulong,IRdsAadAuthServer * *)
  ... truncated ...
```
