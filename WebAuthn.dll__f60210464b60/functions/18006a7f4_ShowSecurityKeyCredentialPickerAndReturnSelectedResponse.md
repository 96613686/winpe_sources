# ShowSecurityKeyCredentialPickerAndReturnSelectedResponse

- ea: `0x18006a7f4`
- end: `0x18006afdd`
- name: `ShowSecurityKeyCredentialPickerAndReturnSelectedResponse`
- size: `2025`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180070e70`

## callees

- `0x18000f6a0`
- `0x18001687c`
- `0x180017a88`
- `0x180017bb4`
- `0x18001c0d4`
- `0x18001ee7c`
- `0x1800205e4`
- `0x180025880`
- `0x180027338`
- `0x180028918`
- `0x18002a07c`
- `0x1800350b4`
- `0x180046988`
- `0x180047464`
- `0x180047b08`
- `0x180048280`
- `0x1800537a4`
- `0x180062fcc`
- `0x180063088`
- `0x180063680`
- `0x180067f80`
- `0x18006a7f4`
- `0x18006b260`
- `0x18006c82c`
- `0x18006c9f4`
- `0x18006f750`
- `0x180073a90`
- `0x180131e40`
- `0x18013b6f4`
- `0x18013baac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ac32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ac48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ac32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ac48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ae9f`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x18006ad83`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x18006ad83`

## string_xrefs

- `0x18006a99f`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006ab16`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006af38`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006af4d`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006af62`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006af77`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006af8c`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006afa1`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006afb6`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006afcb`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall ShowSecurityKeyCredentialPickerAndReturnSelectedResponse(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rsi
  HLOCAL v5; // r15
  unsigned int v6; // ebx
  int v7; // r14d
  __int64 v8; // r12
  unsigned int v9; // eax
  int AssertionUserList; // ebx
  int UserSid; // eax
  char *v12; // r9
  int FormattedMessage; // eax
  unsigned __int16 **v14; // r9
  unsigned int v15; // ebx
  __int64 i; // r13
  unsigned __int16 **v17; // r9
  int v18; // eax
  int v19; // eax
  HLOCAL v20; // rax
  char IsEnabled; // al
  int v22; // ecx
  HLOCAL v23; // rcx
  HLOCAL v24; // rcx
  int v25; // eax
  DWORD v26; // eax
  int v27; // eax
  int v28; // ebx
  int v29; // eax
  int Assertion; // eax
  void *v31; // rcx
  unsigned __int8 *v32; // rcx
  unsigned int v34; // eax
  const char *v35; // r9
  unsigned __int16 **ulInAuthBufferSize; // [rsp+20h] [rbp-218h]
  unsigned int ulInAuthBufferSizea; // [rsp+20h] [rbp-218h]
  int ulInAuthBufferSizeb; // [rsp+20h] [rbp-218h]
  struct CREDUI_PICKER_ITEM *v39; // [rsp+50h] [rbp-1E8h] BYREF
  const WCHAR **p_hMem; // [rsp+58h] [rbp-1E0h] BYREF
  unsigned __int8 *ppvOutAuthBuffer; // [rsp+60h] [rbp-1D8h] BYREF
  char v42; // [rsp+68h] [rbp-1D0h]
  HLOCAL v43; // [rsp+70h] [rbp-1C8h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-1C0h] BYREF
  ULONG pulOutAuthBufferSize; // [rsp+80h] [rbp-1B8h] BYREF
  __int64 *v46; // [rsp+88h] [rbp-1B0h] BYREF
  unsigned __int16 *v47; // [rsp+90h] [rbp-1A8h] BYREF
  char v48; // [rsp+98h] [rbp-1A0h]
  LPVOID pv; // [rsp+A0h] [rbp-198h] BYREF
  unsigned __int8 *v50; // [rsp+A8h] [rbp-190h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-188h] BYREF
  ULONG pulAuthPackage; // [rsp+B8h] [rbp-180h] BYREF
  const WCHAR *v53; // [rsp+C0h] [rbp-178h] BYREF
  int v54[2]; // [rsp+C8h] [rbp-170h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-168h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-160h] BYREF
  __int64 v57[3]; // [rsp+E0h] [rbp-158h] BYREF
  LPCVOID pvInAuthBuffer[2]; // [rsp+F8h] [rbp-140h] BYREF
  __int64 v59; // [rsp+108h] [rbp-130h]
  int *v60; // [rsp+110h] [rbp-128h] BYREF
  unsigned int v61[2]; // [rsp+118h] [rbp-120h] BYREF
  char v62; // [rsp+120h] [rbp-118h]
  _DWORD v63[4]; // [rsp+128h] [rbp-110h] BYREF
  HLOCAL v64; // [rsp+138h] [rbp-100h]
  __int64 v65; // [rsp+140h] [rbp-F8h]
  struct CREDUI_PICKER_ITEM *v66; // [rsp+148h] [rbp-F0h]
  __int128 v67; // [rsp+150h] [rbp-E8h] BYREF
  __int64 v68; // [rsp+160h] [rbp-D8h]
  struct _CREDUI_INFOW pUiInfo; // [rsp+170h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]
  unsigned int v72; // [rsp+248h] [rbp+10h] BYREF
  __int64 v73; // [rsp+258h] [rbp+20h] BYREF

  v4 = a1;
  v67 = 0;
  v68 = 0;
  v55 = 0;
  v73 = 0;
  v72 = 0;
  v51 = 0;
  v46 = &v51;
  v47 = 0;
  v48 = 1;
  v5 = (HLOCAL)(a2 + 312);
  v6 = CtapCborEncodeRpcRequest(*(_QWORD *)(*(_QWORD *)(a2 + 312) + 56LL), &v72, &v47, 0);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&v46);
  if ( v6 )
  {
    v34 = HRESULT_FROM_CBOR_ERROR(v6);
    v35 = (const char *)(unsigned int)wil::verify_hresult<long>(v34);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x190F,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      v35,
      0);
  }
  v46 = &v55;
  v47 = 0;
  v48 = 1;
  v43 = *(HLOCAL *)a3;
  v7 = (int)v43;
  v8 = *(_QWORD *)(a3 + 8);
  v57[0] = v8;
  v9 = wil::safe_cast<unsigned long,unsigned __int64,0>(v8);
  ulInAuthBufferSize = &v47;
  AssertionUserList = WebAuthNCtapRpcGetAssertionUserList(v72, v51, v9, v43);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v46);
  if ( AssertionUserList == -2146893807 )
  {
    std::vector<unsigned char>::vector<unsigned char>(v4, v43, (char *)v43 + v8);
  }
  else
  {
    hMem = v5;
    if ( AssertionUserList < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1922,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)(unsigned int)AssertionUserList,
        (int)&v47);
    try
    {
      v56 = 0;
      wil::impersonate_token(&v39, *(_QWORD *)(*(_QWORD *)v5 + 64LL));
      v46 = &v56;
      v47 = 0;
      v48 = 1;
      UserSid = FidoGetUserSid(&v47);
      if ( UserSid < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1928,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
          (const char *)(unsigned int)UserSid,
          (int)&v47);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v46);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v39);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x192A,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        v12);
      v4 = a1;
      v5 = hMem;
      v7 = (int)v43;
      v8 = v57[0];
    }
    *(_QWORD *)v54 = 0;
    v60 = v54;
    *(_QWORD *)v61 = 0;
    v62 = 1;
    FormattedMessage = FidoCommon::FidoGetFormattedMessage(
                         (FidoCommon *)g_hInstance,
                         (HINSTANCE)0x40B,
                         (unsigned int)v61,
                         (unsigned __int16 **)v12);
    if ( FormattedMessage < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1930,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)(unsigned int)FormattedMessage,
        (int)ulInAuthBufferSize);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v60);
    *(_OWORD *)pvInAuthBuffer = 0;
    v59 = 0;
    v15 = 0;
    for ( i = v73; v15 < *(_DWORD *)i; ++v15 )
    {
      v39 = 0;
      v17 = *(unsigned __int16 ***)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL * v15) + 16LL);
      p_hMem = (const WCHAR **)&v39;
      ppvOutAuthBuffer = 0;
      v42 = 1;
      LODWORD(ulInAuthBufferSize) = v54[0];
      v18 = FidoCommon::FidoGetFormattedMessage(
              (FidoCommon *)g_hInstance,
              (HINSTANCE)0x411,
              (unsigned int)&ppvOutAuthBuffer,
              v17);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x193B,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
          (const char *)(unsigned int)v18,
          (int)ulInAuthBufferSize);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hMem);
      LODWORD(v73) = 0;
      v43 = 0;
      p_hMem = (const WCHAR **)&v43;
      ppvOutAuthBuffer = 0;
      v42 = 1;
      v19 = WebAuthNGetImageBufferfromRes(0x60u, (unsigned int *)&v73, &ppvOutAuthBuffer);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1942,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
          (const char *)(unsigned int)v19,
          (int)ulInAuthBufferSize);
      wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      v63[0] = v15;
      v63[2] = v73;
      v63[3] = 0;
      v20 = v43;
      v43 = 0;
      v64 = v20;
      v65 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL * v15) + 16LL);
      v66 = v39;
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::GetImpl'::`2'::impl);
      v22 = 0;
      if ( IsEnabled )
        v22 = 3;
      v63[1] = v22;
      hMem = 0;
      LODWORD(v73) = 0;
      p_hMem = (const WCHAR **)&hMem;
      ppvOutAuthBuffer = 0;
      v42 = 1;
      SerializeCredUIPickerScreenItem((const struct CREDUI_PICKER_ITEM *)v63, &ppvOutAuthBuffer, (unsigned int *)&v73);
      wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      v57[0] = (__int64)hMem;
      v57[1] = (unsigned int)v73;
      std::ranges::_Copy_fn::operator()<std::span<unsigned char const,-1>,std::back_insert_iterator<std::vector<unsigned char>>>(
        &v46,
        v57,
        (__int64)pvInAuthBuffer);
      v23 = hMem;
      hMem = 0;
      if ( v23 )
        LocalFree(v23);
      v24 = v43;
      v43 = 0;
      if ( v24 )
        LocalFree(v24);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v39);
    }
    v53 = 0;
    p_hMem = &v53;
    ppvOutAuthBuffer = 0;
    v42 = 1;
    v25 = FidoCommon::FidoGetFormattedMessage(
            (FidoCommon *)g_hInstance,
            (HINSTANCE)0x421,
            (unsigned int)&ppvOutAuthBuffer,
            v14);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x195C,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)(unsigned int)v25,
        (int)ulInAuthBufferSize);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hMem);
    memset_0(&pUiInfo, 0, 0x88u);
    pUiInfo.cbSize = 136;
    pUiInfo.pszCaptionText = v53;
    pUiInfo.hwndParent = **(HWND **)(*(_QWORD *)(*(_QWORD *)v5 + 56LL) + 152LL);
    LODWORD(pUiInfo.hbmBanner) = 0x10000;
    v50 = 0;
    pulOutAuthBufferSize = 0;
    pulAuthPackage = 212664323;
    p_hMem = (const WCHAR **)&v50;
    ppvOutAuthBuffer = 0;
    v42 = 1;
    v26 = CredUIPromptForWindowsCredentialsW(
            &pUiInfo,
            0,
            &pulAuthPackage,
            pvInAuthBuffer[0],
            LODWORD(pvInAuthBuffer[1]) - LODWORD(pvInAuthBuffer[0]),
            (LPVOID *)&ppvOutAuthBuffer,
            &pulOutAuthBufferSize,
            0,
            0x48000210u);
    if ( v26 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1973,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)v26,
        ulInAuthBufferSizea);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_hMem);
    v39 = 0;
    v27 = DeserializeCredUIPickerScreenItem(v50, pulOutAuthBufferSize, &v39, (unsigned int *)&v73);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x197B,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)(unsigned int)v27,
        ulInAuthBufferSizea);
    pv = 0;
    LODWORD(v73) = 0;
    p_hMem = (const WCHAR **)&pv;
    ppvOutAuthBuffer = 0;
    v42 = 1;
    v28 = *(_DWORD *)v39;
    v29 = wil::safe_cast<unsigned long,unsigned __int64,0>(v8);
    Assertion = WebAuthNCtapRpcSelectGetAssertion(v29, v7, v28, (unsigned int)&v73, (__int64)&ppvOutAuthBuffer);
    if ( Assertion < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1985,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)(unsigned int)Assertion,
        ulInAuthBufferSizeb);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_hMem);
    std::vector<unsigned char>::vector<unsigned char>(v4, pv, (char *)pv + (unsigned int)v73);
    v31 = pv;
    pv = 0;
    if ( v31 )
      CoTaskMemFree(v31);
    wil::details::unique_storage<wil::details::resource_policy<CREDUI_PICKER_ITEM *,void (*)(CREDUI_PICKER_ITEM *),&void DeleteCredUIPickerItem(CREDUI_PICKER_ITEM *),wistd::integral_constant<unsigned __int64,0>,CREDUI_PICKER_ITEM *,CREDUI_PICKER_ITEM *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_PICKER_ITEM *,void (*)(CREDUI_PICKER_ITEM *),&void DeleteCredUIPickerItem(CREDUI_PICKER_ITEM *),wistd::integral_constant<unsigned __int64,0>,CREDUI_PICKER_ITEM *,CREDUI_PICKER_ITEM *,0,std::nullptr_t>>(&v39);
    v32 = v50;
    v50 = 0;
    if ( v32 )
      CoTaskMemFree(v32);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v53);
    std::vector<unsigned char>::_Tidy(pvInAuthBuffer);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v54);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v56);
  }
  wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>::reset(&v51, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v55);
  std::vector<unsigned char>::_Tidy(&v67);
  return v4;
}

```

## disassembly

```asm
0x18006a7f4  mov     r11, rsp
0x18006a7f7  mov     [r11+8], rcx
0x18006a7fb  push    rbx
0x18006a7fc  push    rsi
0x18006a7fd  push    rdi
0x18006a7fe  push    r12
0x18006a800  push    r13
0x18006a802  push    r14
0x18006a804  push    r15
0x18006a806  sub     rsp, 200h
0x18006a80d  mov     r12, r8
0x18006a810  mov     rsi, rcx
0x18006a813  xor     edi, edi
0x18006a815  xorps   xmm0, xmm0
0x18006a818  movdqu  [rsp+238h+var_E8], xmm0
0x18006a821  mov     [r11-0D8h], rdi
0x18006a828  mov     [r11-168h], rdi
0x18006a82f  mov     [r11+20h], rdi
0x18006a833  mov     [r11+10h], edi
0x18006a837  mov     [r11-188h], rdi
0x18006a83e  lea     rax, [r11-188h]
0x18006a845  mov     [r11-1B0h], rax
0x18006a84c  mov     [r11-1A8h], rdi
0x18006a853  mov     [rsp+238h+var_1A0], 1
0x18006a85b  lea     r15, [rdx+138h]
0x18006a862  mov     rcx, [r15]
0x18006a865  mov     qword ptr [rsp+238h+ulInAuthBufferSize], rdi; int
0x18006a86a  xor     r9d, r9d
0x18006a86d  lea     r8, [r11-1A8h]
0x18006a874  lea     rdx, [r11+10h]
0x18006a878  mov     rcx, [rcx+38h]
0x18006a87c  call    CtapCborEncodeRpcRequest
0x18006a881  mov     ebx, eax
0x18006a883  lea     rcx, [rsp+238h+var_1B0]
0x18006a88b  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x18006a890  test    ebx, ebx
0x18006a892  jnz     loc_18006AF1F
0x18006a898  lea     rax, [rsp+238h+var_168]
0x18006a8a0  mov     [rsp+238h+var_1B0], rax
0x18006a8a8  mov     [rsp+238h+var_1A8], rdi
0x18006a8b0  mov     [rsp+238h+var_1A0], 1
0x18006a8b8  mov     r14, [r12]
0x18006a8bc  mov     [rsp+238h+var_1C8], r14
0x18006a8c1  mov     r12, [r12+8]
0x18006a8c6  mov     [rsp+238h+var_158], r12
0x18006a8ce  mov     rcx, r12
0x18006a8d1  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x18006a8d6  lea     rcx, [rsp+238h+arg_18]
0x18006a8de  mov     [rsp+238h+ppvOutAuthBuffer], rcx
0x18006a8e3  lea     rcx, [rsp+238h+var_1A8]
0x18006a8eb  mov     qword ptr [rsp+238h+ulInAuthBufferSize], rcx; int
0x18006a8f0  mov     r9, r14
0x18006a8f3  mov     r8d, eax
0x18006a8f6  mov     rdx, [rsp+238h+var_188]
0x18006a8fe  mov     ecx, [rsp+238h+arg_8]
0x18006a905  call    WebAuthNCtapRpcGetAssertionUserList
0x18006a90a  mov     ebx, eax
0x18006a90c  lea     rcx, [rsp+238h+var_1B0]
0x18006a914  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006a919  cmp     ebx, 80090011h
0x18006a91f  jnz     short loc_18006A935
0x18006a921  lea     r8, [r12+r14]
0x18006a925  mov     rdx, r14
0x18006a928  mov     rcx, rsi
0x18006a92b  call    ??$?0U?$_Span_iterator@$$CBE@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@U?$_Span_iterator@$$CBE@1@0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(std::_Span_iterator<uchar const>,std::_Span_iterator<uchar const>,std::allocator<uchar> const &)
0x18006a930  jmp     loc_18006AEDE
0x18006a935  mov     [rsp+238h+hMem], r15
0x18006a93a  mov     rcx, [rsp+238h]; this
0x18006a942  test    ebx, ebx
0x18006a944  js      loc_18006AF4A
0x18006a94a  mov     [rsp+238h+var_160], rdi
0x18006a952  mov     rdx, [r15]
0x18006a955  mov     rdx, [rdx+40h]
0x18006a959  lea     rcx, [rsp+238h+var_1E8]
0x18006a95e  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18006a963  lea     rax, [rsp+238h+var_160]
0x18006a96b  mov     [rsp+238h+var_1B0], rax
0x18006a973  mov     [rsp+238h+var_1A8], rdi
0x18006a97b  mov     [rsp+238h+var_1A0], 1
0x18006a983  lea     rcx, [rsp+238h+var_1A8]; unsigned __int16 **
0x18006a98b  call    ?FidoGetUserSid@@YAJPEAPEAG@Z; FidoGetUserSid(ushort * *)
0x18006a990  mov     rcx, [rsp+238h]; this
0x18006a998  test    eax, eax
0x18006a99a  jns     short loc_18006A9B0
0x18006a99c  mov     r9d, eax; char *
0x18006a99f  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18006a9a6  mov     edx, 1928h; void *
0x18006a9ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006a9b0  lea     rcx, [rsp+238h+var_1B0]
0x18006a9b8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006a9bd  lea     rcx, [rsp+238h+var_1E8]
0x18006a9c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18006a9c7  nop
0x18006a9c8  jmp     short loc_18006A9E6
0x18006a9ca  xor     edi, edi
0x18006a9cc  mov     rsi, [rsp+238h+arg_0]
0x18006a9d4  mov     r15, [rsp+238h+hMem]
0x18006a9d9  mov     r14, [rsp+238h+var_1C8]
0x18006a9de  mov     r12, [rsp+238h+var_158]
0x18006a9e6  mov     qword ptr [rsp+238h+var_170], rdi
0x18006a9ee  lea     rax, [rsp+238h+var_170]
0x18006a9f6  mov     [rsp+238h+var_128], rax
0x18006a9fe  mov     qword ptr [rsp+238h+var_120], rdi
0x18006aa06  mov     [rsp+238h+var_118], 1
0x18006aa0e  lea     r8, [rsp+238h+var_120]; unsigned int
0x18006aa16  mov     edx, 40Bh; HINSTANCE
0x18006aa1b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; this
0x18006aa22  call    ?FidoGetFormattedMessage@FidoCommon@@YAJPEAUHINSTANCE__@@KPEAPEAGZZ; FidoCommon::FidoGetFormattedMessage(HINSTANCE__ *,ulong,ushort * *,...)
0x18006aa27  mov     rcx, [rsp+238h]; this
0x18006aa2f  test    eax, eax
0x18006aa31  js      loc_18006AF5F
0x18006aa37  lea     rcx, [rsp+238h+var_128]
0x18006aa3f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006aa44  xorps   xmm0, xmm0
0x18006aa47  movdqu  xmmword ptr [rsp+238h+pvInAuthBuffer], xmm0
0x18006aa50  mov     [rsp+238h+var_130], rdi
0x18006aa58  mov     ebx, edi
0x18006aa5a  mov     r13, [rsp+238h+arg_18]
0x18006aa62  cmp     [r13+0], edi
0x18006aa66  jbe     loc_18006AC65
0x18006aa6c  mov     [rsp+238h+var_1E8], rdi
0x18006aa71  mov     rdx, qword ptr [rsp+238h+var_170]
0x18006aa79  mov     ecx, ebx
0x18006aa7b  mov     rax, [r13+8]
0x18006aa7f  mov     rcx, [rax+rcx*8]
0x18006aa83  mov     r9, [rcx+10h]; unsigned __int16 **
0x18006aa87  lea     rax, [rsp+238h+var_1E8]
0x18006aa8c  mov     [rsp+238h+var_1E0], rax
0x18006aa91  mov     [rsp+238h+var_1D8], rdi
0x18006aa96  mov     [rsp+238h+var_1D0], 1
0x18006aa9b  mov     qword ptr [rsp+238h+ulInAuthBufferSize], rdx; int
0x18006aaa0  lea     r8, [rsp+238h+var_1D8]; unsigned int
0x18006aaa5  mov     edx, 411h; HINSTANCE
0x18006aaaa  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; this
0x18006aab1  call    ?FidoGetFormattedMessage@FidoCommon@@YAJPEAUHINSTANCE__@@KPEAPEAGZZ; FidoCommon::FidoGetFormattedMessage(HINSTANCE__ *,ulong,ushort * *,...)
0x18006aab6  mov     rcx, [rsp+238h]; this
0x18006aabe  test    eax, eax
0x18006aac0  js      loc_18006AF89
0x18006aac6  lea     rcx, [rsp+238h+var_1E0]
0x18006aacb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006aad0  mov     dword ptr [rsp+238h+arg_18], edi
0x18006aad7  mov     [rsp+238h+var_1C8], rdi
0x18006aadc  lea     rax, [rsp+238h+var_1C8]
0x18006aae1  mov     [rsp+238h+var_1E0], rax
0x18006aae6  mov     [rsp+238h+var_1D8], rdi
0x18006aaeb  mov     [rsp+238h+var_1D0], 1
0x18006aaf0  lea     r8, [rsp+238h+var_1D8]; unsigned __int8 **
0x18006aaf5  lea     rdx, [rsp+238h+arg_18]; unsigned int *
0x18006aafd  mov     ecx, 60h ; '`'; unsigned int
0x18006ab02  call    ?WebAuthNGetImageBufferfromRes@@YAJKPEAIPEAPEAE@Z; WebAuthNGetImageBufferfromRes(ulong,uint *,uchar * *)
0x18006ab07  mov     rcx, [rsp+238h]; this
0x18006ab0f  test    eax, eax
0x18006ab11  jns     short loc_18006AB28
0x18006ab13  mov     r9d, eax; char *
0x18006ab16  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18006ab1d  mov     edx, 1942h; void *
0x18006ab22  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006ab27  nop
0x18006ab28  lea     rcx, [rsp+238h+var_1E0]
0x18006ab2d  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18006ab32  mov     [rsp+238h+var_110], ebx
0x18006ab39  mov     eax, dword ptr [rsp+238h+arg_18]
0x18006ab40  mov     [rsp+238h+var_108], eax
0x18006ab47  xor     eax, eax
0x18006ab49  mov     [rsp+238h+var_104], eax
0x18006ab50  mov     rax, [rsp+238h+var_1C8]
0x18006ab55  mov     [rsp+238h+var_1C8], rdi
0x18006ab5a  mov     [rsp+238h+var_100], rax
0x18006ab62  mov     rax, [r13+8]
0x18006ab66  mov     ecx, ebx
0x18006ab68  mov     rcx, [rax+rcx*8]
0x18006ab6c  mov     rax, [rcx+10h]
0x18006ab70  mov     [rsp+238h+var_F8], rax
0x18006ab78  mov     rax, [rsp+238h+var_1E8]
0x18006ab7d  mov     [rsp+238h+var_F0], rax
0x18006ab85  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG> `wil::Feature<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::GetImpl(void)'::`2'::impl
0x18006ab8c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::__private_IsEnabled(void)
0x18006ab91  mov     ecx, edi
0x18006ab93  mov     edx, 3
0x18006ab98  test    al, al
0x18006ab9a  cmovnz  ecx, edx
0x18006ab9d  mov     [rsp+238h+var_10C], ecx
0x18006aba4  mov     [rsp+238h+hMem], rdi
0x18006aba9  mov     dword ptr [rsp+238h+arg_18], edi
0x18006abb0  lea     rax, [rsp+238h+hMem]
0x18006abb5  mov     [rsp+238h+var_1E0], rax
0x18006abba  mov     [rsp+238h+var_1D8], rdi
0x18006abbf  mov     [rsp+238h+var_1D0], 1
0x18006abc4  lea     r8, [rsp+238h+arg_18]; unsigned int *
0x18006abcc  lea     rdx, [rsp+238h+var_1D8]; unsigned __int8 **
0x18006abd1  lea     rcx, [rsp+238h+var_110]; struct CREDUI_PICKER_ITEM *
0x18006abd9  call    ?SerializeCredUIPickerScreenItem@@YAJPEBUCREDUI_PICKER_ITEM@@PEAPEAEAEAK@Z; SerializeCredUIPickerScreenItem(CREDUI_PICKER_ITEM const *,uchar * *,ulong &)
0x18006abde  nop
0x18006abdf  lea     rcx, [rsp+238h+var_1E0]
0x18006abe4  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18006abe9  mov     rax, [rsp+238h+hMem]
0x18006abee  mov     [rsp+238h+var_158], rax
0x18006abf6  mov     eax, dword ptr [rsp+238h+arg_18]
0x18006abfd  mov     [rsp+238h+var_150], rax
0x18006ac05  lea     r8, [rsp+238h+pvInAuthBuffer]
0x18006ac0d  lea     rdx, [rsp+238h+var_158]
0x18006ac15  lea     rcx, [rsp+238h+var_1B0]
0x18006ac1d  call    ??$?RV?$span@$$CBE$0?0@std@@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@1@@_Copy_fn@ranges@std@@SA?AU?$in_out_result@U?$_Span_iterator@$$CBE@std@@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@2@@12@$$QEAV?$span@$$CBE$0?0@2@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@2@@Z; std::ranges::_Copy_fn::operator()<std::span<uchar const,-1>,std::back_insert_iterator<std::vector<uchar>>>(std::span<uchar const,-1> &&,std::back_insert_iterator<std::vector<uchar>>)
0x18006ac22  nop
0x18006ac23  mov     rcx, [rsp+238h+hMem]; hMem
0x18006ac28  mov     [rsp+238h+hMem], rdi
0x18006ac2d  test    rcx, rcx
0x18006ac30  jz      short loc_18006AC39
0x18006ac32  call    cs:__imp_LocalFree
0x18006ac38  nop
0x18006ac39  mov     rcx, [rsp+238h+var_1C8]; hMem
0x18006ac3e  mov     [rsp+238h+var_1C8], rdi
0x18006ac43  test    rcx, rcx
0x18006ac46  jz      short loc_18006AC4F
0x18006ac48  call    cs:__imp_LocalFree
0x18006ac4e  nop
0x18006ac4f  lea     rcx, [rsp+238h+var_1E8]
0x18006ac54  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18006ac59  inc     ebx
0x18006ac5b  cmp     ebx, [r13+0]
0x18006ac5f  jb      loc_18006AA6C
0x18006ac65  mov     [rsp+238h+var_178], rdi
0x18006ac6d  lea     rax, [rsp+238h+var_178]
0x18006ac75  mov     [rsp+238h+var_1E0], rax
0x18006ac7a  mov     [rsp+238h+var_1D8], rdi
0x18006ac7f  mov     [rsp+238h+var_1D0], 1
0x18006ac84  lea     r8, [rsp+238h+var_1D8]; unsigned int
0x18006ac89  mov     edx, 421h; HINSTANCE
0x18006ac8e  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; this
0x18006ac95  call    ?FidoGetFormattedMessage@FidoCommon@@YAJPEAUHINSTANCE__@@KPEAPEAGZZ; FidoCommon::FidoGetFormattedMessage(HINSTANCE__ *,ulong,ushort * *,...)
0x18006ac9a  mov     rcx, [rsp+238h]; this
0x18006aca2  test    eax, eax
0x18006aca4  js      loc_18006AF74
0x18006acaa  lea     rcx, [rsp+238h+var_1E0]
0x18006acaf  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006acb4  mov     ebx, 88h
0x18006acb9  mov     r8d, ebx; Size
0x18006acbc  xor     edx, edx; Val
0x18006acbe  lea     rcx, [rsp+238h+pUiInfo]; void *
0x18006acc6  call    memset_0
0x18006accb  mov     [rsp+238h+pUiInfo.cbSize], ebx
0x18006acd2  mov     rax, [rsp+238h+var_178]
0x18006acda  mov     [rsp+238h+pUiInfo.pszCaptionText], rax
0x18006ace2  mov     rax, [r15]
0x18006ace5  mov     rcx, [rax+38h]
0x18006ace9  mov     rax, [rcx+98h]
0x18006acf0  mov     rcx, [rax]
0x18006acf3  mov     [rsp+238h+pUiInfo.hwndParent], rcx
0x18006acfb  mov     dword ptr [rsp+238h+pUiInfo.hbmBanner], 10000h
0x18006ad06  mov     [rsp+238h+var_190], rdi
0x18006ad0e  mov     [rsp+238h+var_1B8], edi
0x18006ad15  mov     [rsp+238h+pulAuthPackage], 0CAD0003h
0x18006ad20  lea     rax, [rsp+238h+var_190]
0x18006ad28  mov     [rsp+238h+var_1E0], rax
0x18006ad2d  mov     [rsp+238h+var_1D8], rdi
0x18006ad32  mov     [rsp+238h+var_1D0], 1
0x18006ad37  mov     r9, [rsp+238h+pvInAuthBuffer]; pvInAuthBuffer
0x18006ad3f  mov     eax, dword ptr [rsp+238h+pvInAuthBuffer+8]
0x18006ad46  sub     eax, r9d
0x18006ad49  mov     [rsp+238h+dwFlags], 48000210h; dwFlags
0x18006ad51  mov     [rsp+238h+pfSave], rdi; pfSave
0x18006ad56  lea     rcx, [rsp+238h+var_1B8]
0x18006ad5e  mov     [rsp+238h+pulOutAuthBufferSize], rcx; pulOutAuthBufferSize
0x18006ad63  lea     rcx, [rsp+238h+var_1D8]
0x18006ad68  mov     [rsp+238h+ppvOutAuthBuffer], rcx; ppvOutAuthBuffer
0x18006ad6d  mov     [rsp+238h+ulInAuthBufferSize], eax; int
0x18006ad71  lea     r8, [rsp+238h+pulAuthPackage]; pulAuthPackage
0x18006ad79  xor     edx, edx; dwAuthError
0x18006ad7b  lea     rcx, [rsp+238h+pUiInfo]; pUiInfo
0x18006ad83  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x18006ad89  mov     rcx, [rsp+238h]; this
0x18006ad91  test    eax, eax
0x18006ad93  jnz     loc_18006AF9E
0x18006ad99  lea     rcx, [rsp+238h+var_1E0]
0x18006ad9e  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18006ada3  mov     [rsp+238h+var_1E8], rdi
0x18006ada8  lea     r9, [rsp+238h+arg_18]; unsigned int *
0x18006adb0  lea     r8, [rsp+238h+var_1E8]; struct CREDUI_PICKER_ITEM **
0x18006adb5  mov     edx, [rsp+238h+var_1B8]; unsigned int
0x18006adbc  mov     rcx, [rsp+238h+var_190]; unsigned __int8 *
0x18006adc4  call    ?DeserializeCredUIPickerScreenItem@@YAJPEBEKPEAPEAUCREDUI_PICKER_ITEM@@AEAK@Z; DeserializeCredUIPickerScreenItem(uchar const *,ulong,CREDUI_PICKER_ITEM * *,ulong &)
0x18006adc9  mov     rcx, [rsp+238h]; this
0x18006add1  test    eax, eax
0x18006add3  js      loc_18006AFB3
0x18006add9  mov     [rsp+238h+pv], rdi
0x18006ade1  mov     dword ptr [rsp+238h+arg_18], edi
0x18006ade8  lea     rax, [rsp+238h+pv]
0x18006adf0  mov     [rsp+238h+var_1E0], rax
0x18006adf5  mov     [rsp+238h+var_1D8], rdi
0x18006adfa  mov     [rsp+238h+var_1D0], 1
0x18006adff  mov     rax, [rsp+238h+var_1E8]
0x18006ae04  mov     ebx, [rax]
0x18006ae06  mov     rcx, r12
0x18006ae09  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x18006ae0e  lea     rcx, [rsp+238h+var_1D8]
0x18006ae13  mov     qword ptr [rsp+238h+ulInAuthBufferSize], rcx; int
0x18006ae18  lea     r9, [rsp+238h+arg_18]
0x18006ae20  mov     r8d, ebx
0x18006ae23  mov     rdx, r14
0x18006ae26  mov     ecx, eax
  ... truncated ...
```
