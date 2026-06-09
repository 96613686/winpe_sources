# GetDeviceBoundPasskeyCredentialDetails

- ea: `0x180083e50`
- end: `0x18008492b`
- name: `GetDeviceBoundPasskeyCredentialDetails`
- size: `2779`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180082050`
- `0x180082158`
- `0x18008c250`

## callees

- `0x180015d30`
- `0x1800164c8`
- `0x18001687c`
- `0x180017a88`
- `0x180019074`
- `0x18001df88`
- `0x18001ee7c`
- `0x180020584`
- `0x1800205a4`
- `0x1800205e4`
- `0x180020614`
- `0x180020668`
- `0x18002be64`
- `0x18002c328`
- `0x18003aab8`
- `0x18003c9e4`
- `0x180044e28`
- `0x180046768`
- `0x1800510e8`
- `0x18006b260`
- `0x18006f750`
- `0x18007c8c8`
- `0x18007dba4`
- `0x18007e368`
- `0x180080750`
- `0x180080810`
- `0x1800814f8`
- `0x180081648`
- `0x180081840`
- `0x180082504`
- `0x180083e50`
- `0x1800849f4`
- `0x180087804`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083f8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083fb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008468d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800846a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800846bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083f8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083fb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008468d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800846a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800846bd`
- `ncrypt!NCryptGetProperty` at `0x1800847b3`
- `ncrypt!NCryptGetProperty` at `0x1800847b3`

## string_xrefs

- `0x180084146`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180084207`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008426c`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x1800843ea`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008454f`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180084658`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180084702`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180084904`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180084919`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x1800843cd`: `login.microsoft.com`
- `0x180084532`: `login.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall GetDeviceBoundPasskeyCredentialDetails(__int64 a1, void *a2, unsigned int a3, __int64 a4)
{
  int v4; // eax
  int v5; // ebx
  HLOCAL v6; // rcx
  HLOCAL v7; // rcx
  HLOCAL v8; // rcx
  int v10; // r14d
  __int64 DomainRPID; // rbx
  __int64 v12; // rbx
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  int v17; // ebx
  int v18; // ebx
  __int64 v19; // rax
  const char *v20; // r9
  int v21; // eax
  int v22; // ebx
  int v23; // ebx
  __int64 v24; // rax
  const char *v25; // r9
  int v26; // eax
  wil::details::in1diag3 *v27; // rcx
  __int64 v28; // rdx
  int AccountInformation; // eax
  int v30; // ebx
  int v31; // ebx
  __int64 v32; // rax
  const char *v33; // r9
  HLOCAL v34; // rcx
  HLOCAL v35; // rcx
  bool v36; // zf
  HLOCAL v37; // rcx
  NCRYPT_HANDLE v38; // rbx
  int AccountInformationFromFidoKey; // eax
  char v40; // di
  int v41; // edi
  __int64 v42; // rax
  const char *v43; // r9
  __int64 v44; // r9
  _QWORD *v45; // rcx
  int *pcbResult; // [rsp+20h] [rbp-388h]
  struct _NGC_USER_ID_KEY_INFO **dwFlags; // [rsp+28h] [rbp-380h]
  HLOCAL v48; // [rsp+30h] [rbp-378h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-370h] BYREF
  HLOCAL v50; // [rsp+40h] [rbp-368h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp-360h] BYREF
  int v52; // [rsp+50h] [rbp-358h] BYREF
  HLOCAL *p_hMem; // [rsp+58h] [rbp-350h] BYREF
  struct _NGC_USER_ID_KEY_INFO *v54; // [rsp+60h] [rbp-348h] BYREF
  char v55; // [rsp+68h] [rbp-340h]
  __int64 v56; // [rsp+70h] [rbp-338h] BYREF
  DWORD v57; // [rsp+78h] [rbp-330h] BYREF
  unsigned int v58; // [rsp+80h] [rbp-328h]
  NCRYPT_PROV_HANDLE hProvider; // [rsp+88h] [rbp-320h] BYREF
  __int64 v60; // [rsp+90h] [rbp-318h] BYREF
  BYTE pbOutput[8]; // [rsp+98h] [rbp-310h] BYREF
  CtapCbor::WebAuthNCredentialDetails *v62[2]; // [rsp+A0h] [rbp-308h] BYREF
  CtapCbor::WebAuthNCredentialDetails *v63; // [rsp+B0h] [rbp-2F8h]
  __int64 v64; // [rsp+B8h] [rbp-2F0h]
  __int64 v65; // [rsp+C0h] [rbp-2E8h]
  void *v66; // [rsp+C8h] [rbp-2E0h] BYREF
  __int64 v67; // [rsp+D0h] [rbp-2D8h]
  __int64 v68; // [rsp+D8h] [rbp-2D0h]
  _BYTE v69[8]; // [rsp+E8h] [rbp-2C0h] BYREF
  void *v70; // [rsp+F0h] [rbp-2B8h]
  __int64 v71; // [rsp+F8h] [rbp-2B0h]
  int v72; // [rsp+100h] [rbp-2A8h] BYREF
  __int64 v73; // [rsp+108h] [rbp-2A0h]
  __int128 v74; // [rsp+110h] [rbp-298h]
  int v75; // [rsp+120h] [rbp-288h]
  _QWORD v76[4]; // [rsp+128h] [rbp-280h] BYREF
  _BYTE v77[32]; // [rsp+148h] [rbp-260h] BYREF
  int v78; // [rsp+168h] [rbp-240h]
  __int128 v79; // [rsp+170h] [rbp-238h]
  __int64 v80; // [rsp+180h] [rbp-228h]
  _BYTE v81[32]; // [rsp+188h] [rbp-220h] BYREF
  _BYTE v82[40]; // [rsp+1A8h] [rbp-200h] BYREF
  _BYTE v83[32]; // [rsp+1D0h] [rbp-1D8h] BYREF
  __int128 v84; // [rsp+1F0h] [rbp-1B8h]
  __int64 v85; // [rsp+200h] [rbp-1A8h]
  _BYTE v86[344]; // [rsp+210h] [rbp-198h] BYREF
  int v87; // [rsp+368h] [rbp-40h]
  char v88; // [rsp+36Ch] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v71 = a4;
  v67 = a1;
  v70 = a2;
  v58 = a3;
  v68 = a4;
  wil::impersonate_token(v69, a2);
  *(_OWORD *)v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  hProvider = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &hProvider,
    0);
  v4 = WebAuthNOpenNgcKsp(&hProvider);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1264,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)(unsigned int)v4,
      (int)pcbResult);
  v66 = 0;
  while ( 1 )
  {
    v48 = 0;
    v52 = 0;
    v50 = 0;
    hMem = 0;
    hObject = 0;
    *(_DWORD *)pbOutput = 0;
    p_hMem = &v48;
    v54 = 0;
    v55 = 1;
    v5 = WebAuthNEnumUserIdKeys(hProvider, &dword_18015030C, &v54, &v66);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( v5 == -2146893782 )
      break;
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x127C,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
        (const char *)(unsigned int)v5,
        (int)pcbResult);
    LODWORD(v64) = v64 + 1;
    v10 = WebAuthNGetKeyDomainType(*(_QWORD *)v48);
    v72 = 4;
    v73 = 0;
    v74 = 0;
    v75 = 1;
    std::wstring::wstring(v76);
    std::wstring::wstring(v77);
    v78 = 1;
    v79 = 0;
    v80 = 0;
    std::wstring::wstring(v81);
    std::wstring::wstring(v82);
    std::wstring::wstring(v83);
    v84 = 0;
    v85 = 0;
    switch ( v10 )
    {
      case 1:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
          &hObject,
          0);
        v26 = WebAuthNOpenUserIdKey(hProvider, *((LPCWSTR *)v48 + 4), &hObject);
        v27 = retaddr;
        if ( v26 < 0 )
        {
          v28 = 4746;
          goto LABEL_44;
        }
        p_hMem = &v50;
        v54 = 0;
        v55 = 1;
        v38 = hObject;
        AccountInformationFromFidoKey = I_NgcGetAccountInformationFromFidoKey(hObject);
        if ( AccountInformationFromFidoKey >= 0 )
        {
          v40 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x128F,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
            (const char *)(unsigned int)AccountInformationFromFidoKey,
            (int)pcbResult);
          v40 = 1;
        }
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
        if ( !v40 )
        {
          p_hMem = &hMem;
          v54 = 0;
          v55 = 1;
          v41 = CtapCborDecodeAccountInformation(
                  v52,
                  (_DWORD)v50,
                  (unsigned int)&v54,
                  (unsigned int)&v60,
                  (__int64)&v57,
                  (_DWORD)dwFlags);
          wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
          if ( !v41 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
            {
              v57 = 0;
              NCryptGetProperty(v38, L"NgcFidoThirdPartyPayment", pbOutput, 4u, &v57, 0);
            }
            try
            {
              LODWORD(dwFlags) = *(_DWORD *)pbOutput;
              LODWORD(pcbResult) = 1;
              v42 = EncodeDeviceBoundNgcKeyDetails(v86, hMem, v58, v38);
              CtapCbor::WebAuthNCredentialDetails::operator=(&v72, v42);
              CtapCbor::WebAuthNCredentialDetails::~WebAuthNCredentialDetails((CtapCbor::WebAuthNCredentialDetails *)v86);
              ++HIDWORD(v64);
            }
            catch ( ... )
            {
              wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x12B4,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
                v43);
              break;
            }
            goto LABEL_58;
          }
        }
        break;
      case 2:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
          &hObject,
          0);
        v26 = WebAuthNOpenUserIdKey(hProvider, *((LPCWSTR *)v48 + 4), &hObject);
        v27 = retaddr;
        if ( v26 < 0 )
        {
          v28 = 4800;
LABEL_44:
          wil::details::in1diag3::_Log_Hr(
            v27,
            (void *)v28,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
            (const char *)(unsigned int)v26,
            (int)pcbResult);
          break;
        }
        p_hMem = &v50;
        v54 = 0;
        v55 = 1;
        dwFlags = &v54;
        pcbResult = &v52;
        AccountInformation = I_NgcGetAccountInformation(L"login.microsoft.com", v48, hObject, 2);
        v30 = AccountInformation;
        if ( AccountInformation < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x12C8,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
            (const char *)(unsigned int)AccountInformation,
            (int)&v52);
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
        if ( v30 >= 0 )
        {
          p_hMem = &hMem;
          v54 = 0;
          v55 = 1;
          v31 = CtapCborDecodeAccountInformation(
                  v52,
                  (_DWORD)v50,
                  (unsigned int)&v54,
                  (unsigned int)&v60,
                  (__int64)&v57,
                  (unsigned int)&v54);
          wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
          if ( !v31 )
          {
            try
            {
              LODWORD(dwFlags) = 0;
              LODWORD(pcbResult) = 2;
              v32 = EncodeDeviceBoundNgcKeyDetails(v86, hMem, v58, hObject);
              CtapCbor::WebAuthNCredentialDetails::operator=(&v72, v32);
              CtapCbor::WebAuthNCredentialDetails::~WebAuthNCredentialDetails((CtapCbor::WebAuthNCredentialDetails *)v86);
              ++HIDWORD(v65);
            }
            catch ( ... )
            {
              wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x12E0,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
                v33);
              break;
            }
LABEL_58:
            CtapCbor::WebAuthNCredentialDetails::WebAuthNCredentialDetails(
              (CtapCbor::WebAuthNCredentialDetails *)v86,
              (const struct CtapCbor::WebAuthNCredentialDetails *)&v72);
            v86[336] = 1;
            v87 = v10;
            v88 = 1;
            CredentialAuthenticatorCache::AddCredential(v70, (const struct CredentialInfo *)v86);
            CredentialInfo::~CredentialInfo((CredentialInfo *)v86);
            if ( !v68 )
              goto LABEL_64;
            v44 = -1;
            do
              ++v44;
            while ( *(_WORD *)(v71 + 2 * v44) );
            v45 = v76;
            if ( v76[3] > 7u )
              v45 = (_QWORD *)v76[0];
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v45, v76[2], v71, v44) )
            {
LABEL_64:
              if ( v62[1] == v63 )
              {
                std::vector<CtapCbor::WebAuthNCredentialDetails>::_Emplace_reallocate<CtapCbor::WebAuthNCredentialDetails const &>(
                  v62,
                  v62[1],
                  &v72);
              }
              else
              {
                CtapCbor::WebAuthNCredentialDetails::WebAuthNCredentialDetails(
                  v62[1],
                  (const struct CtapCbor::WebAuthNCredentialDetails *)&v72);
                v62[1] = (CtapCbor::WebAuthNCredentialDetails *)((char *)v62[1] + 272);
              }
            }
          }
        }
        break;
      case 3:
        v56 = 0;
        DomainRPID = I_GetDomainRPID(*((_QWORD *)v48 + 1));
        dwFlags = (struct _NGC_USER_ID_KEY_INFO **)"Couldn't get AAD domain from system";
        LODWORD(pcbResult) = DomainRPID;
        wil::details::in1diag3::Log_HrIfNullMsg<unsigned short *,0>(
          retaddr,
          4844,
          "onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
          2147500035LL);
        if ( !DomainRPID )
          goto LABEL_16;
        v60 = DomainRPID;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v56,
          &v60);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v60);
        v12 = v56;
        if ( (unsigned __int8)IsStringInList(v56, 1, &off_18014C800)
          || (unsigned __int8)IsStringInList(v12, 4, off_18014C810) )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
            &hObject,
            0);
          v13 = WebAuthNOpenUserIdKey(hProvider, *((LPCWSTR *)v48 + 4), &hObject);
          v14 = retaddr;
          if ( v13 < 0 )
          {
            v15 = 4854;
            goto LABEL_21;
          }
          p_hMem = &v50;
          v54 = 0;
          v55 = 1;
          dwFlags = &v54;
          pcbResult = &v52;
          v21 = I_NgcGetAccountInformation(L"login.microsoft.com", v48, hObject, 3);
          v22 = v21;
          if ( v21 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x12FE,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
              (const char *)(unsigned int)v21,
              (int)&v52);
          wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
          if ( v22 < 0 )
            goto LABEL_16;
          p_hMem = &hMem;
          v54 = 0;
          v55 = 1;
          v23 = CtapCborDecodeAccountInformation(
                  v52,
                  (_DWORD)v50,
                  (unsigned int)&v54,
                  (unsigned int)&v60,
                  (__int64)&v57,
                  (unsigned int)&v54);
          wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
          if ( v23 )
            goto LABEL_16;
          try
          {
            LODWORD(dwFlags) = 0;
            LODWORD(pcbResult) = 3;
            v24 = EncodeDeviceBoundNgcKeyDetails(v86, hMem, v58, hObject);
            CtapCbor::WebAuthNCredentialDetails::operator=(&v72, v24);
            CtapCbor::WebAuthNCredentialDetails::~WebAuthNCredentialDetails((CtapCbor::WebAuthNCredentialDetails *)v86);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x1316,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
              v25);
            goto LABEL_16;
          }
        }
        else
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
            &hObject,
            0);
          v13 = WebAuthNOpenUserIdKey(hProvider, *((LPCWSTR *)v48 + 4), &hObject);
          v14 = retaddr;
          if ( v13 < 0 )
          {
            v15 = 4897;
LABEL_21:
            wil::details::in1diag3::_Log_Hr(
              v14,
              (void *)v15,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
              (const char *)(unsigned int)v13,
              (int)pcbResult);
LABEL_16:
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v56);
            break;
          }
          p_hMem = &v50;
          v54 = 0;
          v55 = 1;
          dwFlags = &v54;
          pcbResult = &v52;
          v16 = I_NgcGetAccountInformation(v12, v48, hObject, 3);
          v17 = v16;
          if ( v16 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1329,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
              (const char *)(unsigned int)v16,
              (int)&v52);
          wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
          if ( v17 < 0 )
            goto LABEL_16;
          p_hMem = &hMem;
          v54 = 0;
          v55 = 1;
          v18 = CtapCborDecodeAccountInformation(
                  v52,
                  (_DWORD)v50,
                  (unsigned int)&v54,
                  (unsigned int)&v60,
                  (__int64)&v57,
                  (unsigned int)&v54);
          wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
          if ( v18 )
            goto LABEL_16;
          try
          {
            LODWORD(dwFlags) = 0;
            LODWORD(pcbResult) = 3;
            v19 = EncodeDeviceBoundNgcKeyDetails(v86, hMem, v58, hObject);
            CtapCbor::WebAuthNCredentialDetails::operator=(&v72, v19);
            CtapCbor::WebAuthNCredentialDetails::~WebAuthNCredentialDetails((CtapCbor::WebAuthNCredentialDetails *)v86);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x1341,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
              v20);
            goto LABEL_16;
          }
        }
        LODWORD(v65) = v65 + 1;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v56);
        goto LABEL_58;
      default:
        break;
    }
    CtapCbor::WebAuthNCredentialDetails::~WebAuthNCredentialDetails((CtapCbor::WebAuthNCredentialDetails *)&v72);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    v34 = hMem;
    hMem = 0;
    if ( v34 )
      LocalFree(v34);
    v35 = v50;
    v36 = v50 == 0;
    v50 = 0;
    if ( !v36 )
      LocalFree(v35);
    v37 = v48;
    v48 = 0;
    if ( v37 )
      LocalFree(v37);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  v6 = hMem;
  hMem = 0;
  if ( v6 )
    LocalFree(v6);
  v7 = v50;
  v50 = 0;
  if ( v7 )
    LocalFree(v7);
  v8 = v48;
  v48 = 0;
  if ( v8 )
    LocalFree(v8);
  DeviceBoundPasskeyListResult::DeviceBoundPasskeyListResult(v67, v62);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v66);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
  std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(v62);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v69);
  return v67;
}

```

## disassembly

```asm
0x180083e50  push    rbx
0x180083e52  push    rsi
0x180083e53  push    rdi
0x180083e54  push    r14
0x180083e56  sub     rsp, 388h
0x180083e5d  mov     rax, cs:__security_cookie
0x180083e64  xor     rax, rsp
0x180083e67  mov     [rsp+3A8h+var_38], rax
0x180083e6f  mov     [rsp+3A8h+var_2B0], r9
0x180083e77  mov     [rsp+3A8h+var_2D8], rcx
0x180083e7f  mov     [rsp+3A8h+var_2B8], rdx
0x180083e87  mov     [rsp+3A8h+var_328], r8d
0x180083e8f  mov     [rsp+3A8h+var_2D0], r9
0x180083e97  xor     esi, esi
0x180083e99  lea     rcx, [rsp+3A8h+var_2C0]
0x180083ea1  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x180083ea6  nop
0x180083ea7  xorps   xmm0, xmm0
0x180083eaa  movdqu  xmmword ptr [rsp+3A8h+var_308], xmm0
0x180083eb3  mov     [rsp+3A8h+var_2F8], rsi
0x180083ebb  mov     [rsp+3A8h+var_2F0], rsi
0x180083ec3  mov     [rsp+3A8h+var_2E8], rsi
0x180083ecb  mov     [rsp+3A8h+hProvider], rsi
0x180083ed3  xor     edx, edx
0x180083ed5  lea     rcx, [rsp+3A8h+hProvider]
0x180083edd  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180083ee2  lea     rcx, [rsp+3A8h+hProvider]; unsigned __int64 *
0x180083eea  call    ?WebAuthNOpenNgcKsp@@YAJPEA_K@Z; WebAuthNOpenNgcKsp(unsigned __int64 *)
0x180083eef  mov     rcx, [rsp+3A8h]; this
0x180083ef7  test    eax, eax
0x180083ef9  js      loc_180084901
0x180083eff  mov     [rsp+3A8h+var_2E0], rsi
0x180083f07  mov     [rsp+3A8h+var_378], rsi
0x180083f0c  mov     [rsp+3A8h+var_358], esi
0x180083f10  mov     [rsp+3A8h+var_368], rsi
0x180083f15  mov     [rsp+3A8h+hMem], rsi
0x180083f1a  mov     [rsp+3A8h+hObject], rsi
0x180083f1f  mov     dword ptr [rsp+3A8h+pbOutput], esi
0x180083f26  lea     rax, [rsp+3A8h+var_378]
0x180083f2b  mov     [rsp+3A8h+var_350], rax
0x180083f30  mov     [rsp+3A8h+var_348], rsi
0x180083f35  mov     [rsp+3A8h+var_340], 1
0x180083f3a  lea     r9, [rsp+3A8h+var_2E0]; void **
0x180083f42  lea     r8, [rsp+3A8h+var_348]; struct _NGC_USER_ID_KEY_INFO **
0x180083f47  lea     rdx, dword_18015030C; unsigned __int16 *
0x180083f4e  mov     rcx, [rsp+3A8h+hProvider]; hProvider
0x180083f56  call    ?WebAuthNEnumUserIdKeys@@YAJ_KPEBGPEAPEAU_NGC_USER_ID_KEY_INFO@@PEAPEAX@Z; WebAuthNEnumUserIdKeys(unsigned __int64,ushort const *,_NGC_USER_ID_KEY_INFO * *,void * *)
0x180083f5b  mov     ebx, eax
0x180083f5d  lea     rcx, [rsp+3A8h+var_350]
0x180083f62  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180083f67  cmp     ebx, 8009002Ah
0x180083f6d  jnz     loc_180084031
0x180083f73  lea     rcx, [rsp+3A8h+hObject]
0x180083f78  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180083f7d  nop
0x180083f7e  mov     rcx, [rsp+3A8h+hMem]; hMem
0x180083f83  mov     [rsp+3A8h+hMem], rsi
0x180083f88  test    rcx, rcx
0x180083f8b  jz      short loc_180083F94
0x180083f8d  call    cs:__imp_LocalFree
0x180083f93  nop
0x180083f94  mov     rcx, [rsp+3A8h+var_368]; hMem
0x180083f99  mov     [rsp+3A8h+var_368], rsi
0x180083f9e  test    rcx, rcx
0x180083fa1  jz      short loc_180083FAA
0x180083fa3  call    cs:__imp_LocalFree
0x180083fa9  nop
0x180083faa  mov     rcx, [rsp+3A8h+var_378]; hMem
0x180083faf  mov     [rsp+3A8h+var_378], rsi
0x180083fb4  test    rcx, rcx
0x180083fb7  jz      short loc_180083FBF
0x180083fb9  call    cs:__imp_LocalFree
0x180083fbf  lea     rdx, [rsp+3A8h+var_308]
0x180083fc7  mov     rcx, [rsp+3A8h+var_2D8]
0x180083fcf  call    ??0DeviceBoundPasskeyListResult@@QEAA@$$QEAU0@@Z; DeviceBoundPasskeyListResult::DeviceBoundPasskeyListResult(DeviceBoundPasskeyListResult &&)
0x180083fd4  nop
0x180083fd5  lea     rcx, [rsp+3A8h+var_2E0]
0x180083fdd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?NgcFreeEnumState@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180083fe2  nop
0x180083fe3  lea     rcx, [rsp+3A8h+hProvider]
0x180083feb  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180083ff0  nop
0x180083ff1  lea     rcx, [rsp+3A8h+var_308]
0x180083ff9  call    ?_Tidy@?$vector@UWebAuthNCredentialDetails@CtapCbor@@V?$allocator@UWebAuthNCredentialDetails@CtapCbor@@@std@@@std@@AEAAXXZ; std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(void)
0x180083ffe  nop
0x180083fff  lea     rcx, [rsp+3A8h+var_2C0]
0x180084007  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18008400c  mov     rax, [rsp+3A8h+var_2D8]
0x180084014  mov     rcx, [rsp+3A8h+var_38]
0x18008401c  xor     rcx, rsp; StackCookie
0x18008401f  call    __security_check_cookie
0x180084024  add     rsp, 388h
0x18008402b  pop     r14
0x18008402d  pop     rdi
0x18008402e  pop     rsi
0x18008402f  pop     rbx
0x180084030  retn
0x180084031  mov     rcx, [rsp+3A8h]; this
0x180084039  test    ebx, ebx
0x18008403b  js      loc_180084916
0x180084041  inc     dword ptr [rsp+3A8h+var_2F0]
0x180084048  mov     rcx, [rsp+3A8h+var_378]
0x18008404d  mov     rcx, [rcx]
0x180084050  call    WebAuthNGetKeyDomainType
0x180084055  mov     r14d, eax
0x180084058  mov     [rsp+3A8h+var_2A8], 4
0x180084063  mov     [rsp+3A8h+var_2A0], rsi
0x18008406b  xorps   xmm0, xmm0
0x18008406e  movdqa  [rsp+3A8h+var_298], xmm0
0x180084077  mov     [rsp+3A8h+var_288], 1
0x180084082  lea     rcx, [rsp+3A8h+var_280]
0x18008408a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008408f  lea     rcx, [rsp+3A8h+var_260]
0x180084097  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008409c  mov     [rsp+3A8h+var_240], 1
0x1800840a7  xorps   xmm1, xmm1
0x1800840aa  movdqa  [rsp+3A8h+var_238], xmm1
0x1800840b3  mov     [rsp+3A8h+var_228], rsi
0x1800840bb  lea     rcx, [rsp+3A8h+var_220]
0x1800840c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800840c8  lea     rcx, [rsp+3A8h+var_200]
0x1800840d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800840d5  lea     rcx, [rsp+3A8h+var_1D8]
0x1800840dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800840e2  movdqa  [rsp+3A8h+var_1B8], xmm1
0x1800840eb  mov     [rsp+3A8h+var_1A8], rsi
0x1800840f3  mov     ecx, r14d
0x1800840f6  sub     ecx, 1
0x1800840f9  jz      loc_18008461D
0x1800840ff  sub     ecx, 1
0x180084102  jz      loc_1800844BD
0x180084108  cmp     ecx, 1
0x18008410b  jnz     loc_180084665
0x180084111  mov     [rsp+3A8h+var_338], rsi
0x180084116  mov     rcx, [rsp+3A8h+var_378]
0x18008411b  mov     rcx, [rcx+8]
0x18008411f  call    I_GetDomainRPID
0x180084124  mov     rbx, rax
0x180084127  mov     rcx, [rsp+3A8h]
0x18008412f  lea     rax, aCouldnTGetAadD; "Couldn't get AAD domain from system"
0x180084136  mov     qword ptr [rsp+3A8h+dwFlags], rax
0x18008413b  mov     [rsp+3A8h+pcbResult], rbx; int
0x180084140  mov     r9d, 80004003h
0x180084146  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18008414d  mov     edx, 12ECh
0x180084152  call    ??$Log_HrIfNullMsg@PEAG$0A@@in1diag3@details@wil@@YAPEAGPEAXIPEBDJPEAG1ZZ; wil::details::in1diag3::Log_HrIfNullMsg<ushort *,0>(void *,uint,char const *,long,ushort *,char const *,...)
0x180084157  test    rbx, rbx
0x18008415a  jnz     short loc_18008416B
0x18008415c  lea     rcx, [rsp+3A8h+var_338]
0x180084161  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180084166  jmp     loc_180084665
0x18008416b  mov     [rsp+3A8h+var_318], rbx
0x180084173  lea     rdx, [rsp+3A8h+var_318]
0x18008417b  lea     rcx, [rsp+3A8h+var_338]
0x180084180  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180084185  lea     rcx, [rsp+3A8h+var_318]
0x18008418d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180084192  lea     r8, off_18014C800; "login.microsoft.com"
0x180084199  mov     edx, 1
0x18008419e  mov     rbx, [rsp+3A8h+var_338]
0x1800841a3  mov     rcx, rbx
0x1800841a6  call    _IsStringInList
0x1800841ab  test    al, al
0x1800841ad  jnz     loc_180084358
0x1800841b3  lea     r8, off_18014C810; "login.windows.net"
0x1800841ba  mov     edx, 4
0x1800841bf  mov     rcx, rbx
0x1800841c2  call    _IsStringInList
0x1800841c7  test    al, al
0x1800841c9  jnz     loc_180084358
0x1800841cf  xor     edx, edx
0x1800841d1  lea     rcx, [rsp+3A8h+hObject]
0x1800841d6  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800841db  lea     r8, [rsp+3A8h+hObject]; unsigned __int64 *
0x1800841e0  mov     rdx, [rsp+3A8h+var_378]
0x1800841e5  mov     rdx, [rdx+20h]; pszKeyName
0x1800841e9  mov     rcx, [rsp+3A8h+hProvider]; hProvider
0x1800841f1  call    ?WebAuthNOpenUserIdKey@@YAJ_KPEBGPEA_K@Z; WebAuthNOpenUserIdKey(unsigned __int64,ushort const *,unsigned __int64 *)
0x1800841f6  mov     rcx, [rsp+3A8h]; this
0x1800841fe  test    eax, eax
0x180084200  jns     short loc_18008421B
0x180084202  mov     edx, 1321h; void *
0x180084207  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18008420e  mov     r9d, eax; char *
0x180084211  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180084216  jmp     loc_18008415C
0x18008421b  lea     rax, [rsp+3A8h+var_368]
0x180084220  mov     [rsp+3A8h+var_350], rax
0x180084225  mov     [rsp+3A8h+var_348], rsi
0x18008422a  mov     [rsp+3A8h+var_340], 1
0x18008422f  lea     rax, [rsp+3A8h+var_348]
0x180084234  mov     qword ptr [rsp+3A8h+dwFlags], rax
0x180084239  lea     rax, [rsp+3A8h+var_358]
0x18008423e  mov     [rsp+3A8h+pcbResult], rax; int
0x180084243  mov     r9d, 3
0x180084249  mov     r8, [rsp+3A8h+hObject]
0x18008424e  mov     rdx, [rsp+3A8h+var_378]
0x180084253  mov     rcx, rbx
0x180084256  call    I_NgcGetAccountInformation
0x18008425b  mov     ebx, eax
0x18008425d  mov     rcx, [rsp+3A8h]; this
0x180084265  test    eax, eax
0x180084267  jns     short loc_18008427E
0x180084269  mov     r9d, eax; char *
0x18008426c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180084273  mov     edx, 1329h; void *
0x180084278  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008427d  nop
0x18008427e  lea     rcx, [rsp+3A8h+var_350]
0x180084283  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180084288  shr     ebx, 1Fh
0x18008428b  test    bl, bl
0x18008428d  jnz     loc_18008415C
0x180084293  lea     rax, [rsp+3A8h+hMem]
0x180084298  mov     [rsp+3A8h+var_350], rax
0x18008429d  mov     [rsp+3A8h+var_348], rsi
0x1800842a2  mov     [rsp+3A8h+var_340], 1
0x1800842a7  lea     rax, [rsp+3A8h+var_330]
0x1800842ac  mov     [rsp+3A8h+pcbResult], rax
0x1800842b1  lea     r9, [rsp+3A8h+var_318]
0x1800842b9  lea     r8, [rsp+3A8h+var_348]
0x1800842be  mov     rdx, [rsp+3A8h+var_368]
0x1800842c3  mov     ecx, [rsp+3A8h+var_358]
0x1800842c7  call    CtapCborDecodeAccountInformation
0x1800842cc  mov     ebx, eax
0x1800842ce  lea     rcx, [rsp+3A8h+var_350]
0x1800842d3  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800842d8  test    ebx, ebx
0x1800842da  jnz     loc_18008415C
0x1800842e0  mov     [rsp+3A8h+dwFlags], esi
0x1800842e4  mov     dword ptr [rsp+3A8h+pcbResult], 3
0x1800842ec  mov     r9, [rsp+3A8h+hObject]
0x1800842f1  mov     r8d, [rsp+3A8h+var_328]
0x1800842f9  mov     rdx, [rsp+3A8h+hMem]
0x1800842fe  lea     rcx, [rsp+3A8h+var_198]
0x180084306  call    EncodeDeviceBoundNgcKeyDetails
0x18008430b  mov     rdx, rax
0x18008430e  lea     rcx, [rsp+3A8h+var_2A8]
0x180084316  call    ??4WebAuthNCredentialDetails@CtapCbor@@QEAAAEAU01@$$QEAU01@@Z; CtapCbor::WebAuthNCredentialDetails::operator=(CtapCbor::WebAuthNCredentialDetails &&)
0x18008431b  lea     rcx, [rsp+3A8h+var_198]; this
0x180084323  call    ??1WebAuthNCredentialDetails@CtapCbor@@QEAA@XZ; CtapCbor::WebAuthNCredentialDetails::~WebAuthNCredentialDetails(void)
0x180084328  jmp     loc_1800844A7
0x18008432d  lea     rcx, [rsp+3A8h+var_338]
0x180084332  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180084337  nop
0x180084338  lea     rcx, [rsp+3A8h+var_2A8]; this
0x180084340  call    ??1WebAuthNCredentialDetails@CtapCbor@@QEAA@XZ; CtapCbor::WebAuthNCredentialDetails::~WebAuthNCredentialDetails(void)
0x180084345  nop
0x180084346  lea     rcx, [rsp+3A8h+hObject]
0x18008434b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180084350  nop
0x180084351  xor     esi, esi
0x180084353  jmp     loc_18008467E
0x180084358  xor     edx, edx
0x18008435a  lea     rcx, [rsp+3A8h+hObject]
0x18008435f  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180084364  lea     r8, [rsp+3A8h+hObject]; unsigned __int64 *
0x180084369  mov     rdx, [rsp+3A8h+var_378]
0x18008436e  mov     rdx, [rdx+20h]; pszKeyName
0x180084372  mov     rcx, [rsp+3A8h+hProvider]; hProvider
0x18008437a  call    ?WebAuthNOpenUserIdKey@@YAJ_KPEBGPEA_K@Z; WebAuthNOpenUserIdKey(unsigned __int64,ushort const *,unsigned __int64 *)
0x18008437f  mov     rcx, [rsp+3A8h]
0x180084387  test    eax, eax
0x180084389  jns     short loc_180084395
0x18008438b  mov     edx, 12F6h
0x180084390  jmp     loc_180084207
0x180084395  lea     rax, [rsp+3A8h+var_368]
0x18008439a  mov     [rsp+3A8h+var_350], rax
0x18008439f  mov     [rsp+3A8h+var_348], rsi
0x1800843a4  mov     [rsp+3A8h+var_340], 1
0x1800843a9  lea     rax, [rsp+3A8h+var_348]
0x1800843ae  mov     qword ptr [rsp+3A8h+dwFlags], rax
0x1800843b3  lea     rax, [rsp+3A8h+var_358]
0x1800843b8  mov     [rsp+3A8h+pcbResult], rax; int
0x1800843bd  mov     r9d, 3
0x1800843c3  mov     r8, [rsp+3A8h+hObject]
0x1800843c8  mov     rdx, [rsp+3A8h+var_378]
0x1800843cd  lea     rcx, aLoginMicrosoft_0; "login.microsoft.com"
0x1800843d4  call    I_NgcGetAccountInformation
0x1800843d9  mov     ebx, eax
0x1800843db  mov     rcx, [rsp+3A8h]; this
0x1800843e3  test    eax, eax
0x1800843e5  jns     short loc_1800843FC
0x1800843e7  mov     r9d, eax; char *
0x1800843ea  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800843f1  mov     edx, 12FEh; void *
0x1800843f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800843fb  nop
0x1800843fc  lea     rcx, [rsp+3A8h+var_350]
0x180084401  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180084406  shr     ebx, 1Fh
0x180084409  test    bl, bl
0x18008440b  jnz     loc_18008415C
0x180084411  lea     rax, [rsp+3A8h+hMem]
0x180084416  mov     [rsp+3A8h+var_350], rax
0x18008441b  mov     [rsp+3A8h+var_348], rsi
0x180084420  mov     [rsp+3A8h+var_340], 1
0x180084425  lea     rax, [rsp+3A8h+var_330]
0x18008442a  mov     [rsp+3A8h+pcbResult], rax
0x18008442f  lea     r9, [rsp+3A8h+var_318]
  ... truncated ...
```
