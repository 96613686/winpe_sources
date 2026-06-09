# Private::GetTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::System::IUser *,Optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &)

- ea: `0x1800525e4`
- end: `0x18005359c`
- name: `?GetTicket@Private@@YA?AUUserTicketResult@MicrosoftAccount@wpc@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUser@System@Windows@@AEBV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@@Z`
- size: `4024`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005121c`
- `0x180053ab0`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180008d50`
- `0x1800093ac`
- `0x180009a80`
- `0x18000ecc0`
- `0x18000fef0`
- `0x18002ca60`
- `0x18002eb3c`
- `0x180030098`
- `0x180035e0c`
- `0x180046660`
- `0x1800504e4`
- `0x1800507d4`
- `0x180050cfc`
- `0x180050f90`
- `0x180051344`
- `0x1800515dc`
- `0x1800525e4`
- `0x180054044`
- `0x18005421c`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800526c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052783`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800526c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052783`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052db4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052db4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052cf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052cf5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180052705`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005285f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180052705`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005285f`

## string_xrefs

- `0x1800526bd`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x18005280e`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x18005277c`: `https://login.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=42
wpc::MicrosoftAccount::UserTicketResult *__fastcall Private::GetTicket(
        wpc::MicrosoftAccount::UserTicketResult *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v4; // rdi
  _QWORD *v6; // rcx
  _QWORD *v7; // r9
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // eax
  int v12; // esi
  _QWORD *v13; // rsi
  __int64 v14; // r13
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  HSTRING v18; // r15
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  int v22; // esi
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  HSTRING v26; // rsi
  __int64 v27; // rcx
  int v28; // esi
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, __int64, _QWORD, __int64, _DWORD, __int64 *); // r12
  __int64 v31; // r15
  __int64 v32; // rax
  int v33; // edi
  wpc::MicrosoftAccount::UserTicketResult *v34; // rcx
  _QWORD *v35; // rdi
  __int64 (__fastcall *v36)(_QWORD *, __int64, _QWORD, _QWORD **); // rsi
  __int64 v37; // rax
  int v38; // edi
  _QWORD *v39; // rsi
  int v40; // edi
  _QWORD *v41; // rdi
  __int64 (__fastcall *v42)(_QWORD *, __int64, __int64, __int64 *); // rsi
  __int64 v43; // rcx
  int v44; // edi
  __int64 v45; // rcx
  _QWORD *v46; // rcx
  __int64 v47; // rsi
  int v48; // edi
  int v49; // edi
  int v50; // edi
  unsigned int v51; // r8d
  _QWORD *v52; // rcx
  int v53; // eax
  int v54; // edi
  int v55; // eax
  int v56; // edi
  __int64 v57; // r8
  int v58; // eax
  int v59; // edi
  int v60; // eax
  int v61; // edi
  int v62; // eax
  int v63; // edi
  PCWSTR StringRawBuffer; // rax
  __int64 v65; // rcx
  __int128 *v66; // r9
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  _QWORD *v75; // rcx
  wpc::MicrosoftAccount::UserTicketResult *result; // rax
  __int64 v77; // r8
  __int64 v78; // r8
  int v79; // eax
  __int64 v80; // r8
  unsigned int v81; // ebx
  wpc::MicrosoftAccount::UserTicketResult *v82; // rcx
  unsigned int v83; // [rsp+40h] [rbp-618h] BYREF
  _QWORD *v84; // [rsp+48h] [rbp-610h] BYREF
  __int64 v85; // [rsp+50h] [rbp-608h] BYREF
  _QWORD *v86; // [rsp+58h] [rbp-600h] BYREF
  __int64 v87; // [rsp+60h] [rbp-5F8h] BYREF
  __int64 v88; // [rsp+68h] [rbp-5F0h] BYREF
  __int64 v89; // [rsp+70h] [rbp-5E8h] BYREF
  __int64 v90; // [rsp+78h] [rbp-5E0h] BYREF
  __int64 v91; // [rsp+80h] [rbp-5D8h] BYREF
  __int64 v92; // [rsp+88h] [rbp-5D0h] BYREF
  __int64 v93; // [rsp+90h] [rbp-5C8h] BYREF
  __int64 v94; // [rsp+98h] [rbp-5C0h] BYREF
  wpc::MicrosoftAccount::UserTicketResult *v95; // [rsp+A0h] [rbp-5B8h]
  HSTRING v96; // [rsp+B0h] [rbp-5A8h] BYREF
  wpc::MicrosoftAccount::UserTicketResult *v97; // [rsp+B8h] [rbp-5A0h] BYREF
  const wpc::MicrosoftAccount::UserTicketResult *v98; // [rsp+C8h] [rbp-590h] BYREF
  _BYTE v99[40]; // [rsp+D0h] [rbp-588h] BYREF
  _BYTE v100[40]; // [rsp+F8h] [rbp-560h] BYREF
  _BYTE v101[40]; // [rsp+120h] [rbp-538h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+148h] [rbp-510h] BYREF
  _BYTE v103[40]; // [rsp+170h] [rbp-4E8h] BYREF
  _BYTE v104[40]; // [rsp+198h] [rbp-4C0h] BYREF
  _BYTE v105[40]; // [rsp+1C0h] [rbp-498h] BYREF
  _BYTE v106[40]; // [rsp+1E8h] [rbp-470h] BYREF
  _BYTE v107[40]; // [rsp+210h] [rbp-448h] BYREF
  _BYTE v108[40]; // [rsp+238h] [rbp-420h] BYREF
  _BYTE v109[40]; // [rsp+260h] [rbp-3F8h] BYREF
  _BYTE v110[40]; // [rsp+288h] [rbp-3D0h] BYREF
  _BYTE v111[40]; // [rsp+2B0h] [rbp-3A8h] BYREF
  _BYTE v112[40]; // [rsp+2D8h] [rbp-380h] BYREF
  _BYTE v113[40]; // [rsp+300h] [rbp-358h] BYREF
  HSTRING_HEADER v114; // [rsp+328h] [rbp-330h] BYREF
  HSTRING v115; // [rsp+340h] [rbp-318h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+348h] [rbp-310h] BYREF
  HSTRING string; // [rsp+360h] [rbp-2F8h] BYREF
  __int128 v118; // [rsp+368h] [rbp-2F0h] BYREF
  __int128 v119; // [rsp+378h] [rbp-2E0h]
  _BYTE v120[80]; // [rsp+390h] [rbp-2C8h] BYREF
  _BYTE v121[80]; // [rsp+3E0h] [rbp-278h] BYREF
  _BYTE v122[80]; // [rsp+430h] [rbp-228h] BYREF
  _BYTE v123[80]; // [rsp+480h] [rbp-1D8h] BYREF
  _BYTE v124[80]; // [rsp+4D0h] [rbp-188h] BYREF
  _BYTE v125[80]; // [rsp+520h] [rbp-138h] BYREF
  _BYTE v126[80]; // [rsp+570h] [rbp-E8h] BYREF
  _BYTE v127[80]; // [rsp+5C0h] [rbp-98h] BYREF

  v85 = a4;
  v4 = a2;
  v95 = a1;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( a2[3] <= 7u )
        v7 = a2;
      else
        v7 = (_QWORD *)*a2;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d559cce52a1433e229f26c816596a62e_Traceguids, v7);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      WPP_SF_S(v6[2], 13, WPP_d559cce52a1433e229f26c816596a62e_Traceguids, L"{f1273a19-b987-46a7-8564-c35a5e715902}");
  }
  v86 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
         0x45u,
         &hstringHeader,
         &string);
  try
  {
    if ( v8 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v86);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
          (unsigned int)ActivationFactory);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v12);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v94 = 0;
    v13 = v86;
    v14 = *v86;
    string = 0;
    v15 = WindowsCreateStringReference(L"consumers", 9u, &hstringHeader, &string);
    if ( v15 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    }
    else
    {
      v18 = string;
      v115 = 0;
      v19 = WindowsCreateStringReference(L"https://login.microsoft.com", 0x1Bu, &v114, &v115);
      if ( v19 >= 0 )
      {
        LODWORD(v13) = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING, __int64 *))(v14 + 96))(
                         v13,
                         v115,
                         v18,
                         &v94);
        LODWORD(v14) = 0;
        if ( (int)v13 >= 0 )
        {
          v89 = 0;
          v22 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
                  v94,
                  &v89);
          if ( v22 < 0 || !v89 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v22);
            v79 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v89);
            v80 = 2147500035LL;
            if ( v79 != -1 )
              v80 = (unsigned int)v22;
            wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v127, 5, v80, 0);
            throw (wpc::MicrosoftAccount::UserTicketResult *)v127;
          }
          v91 = 0;
          v115 = 0;
          v23 = WindowsCreateStringReference(
                  L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
                  0x38u,
                  &v114,
                  &v115);
          if ( v23 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
            __debugbreak();
          }
          v26 = v115;
          v27 = v91;
          if ( v91 )
          {
            v91 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          v28 = RoGetActivationFactory(v26, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v91);
          if ( v28 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                19,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v28);
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v104, v28);
            throw (ErrorCodeException *)v104;
          }
          v90 = 0;
          v29 = v91;
          v30 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v91 + 56LL);
          v31 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v114, off_1800B3C30) + 24);
          if ( v4[3] > 7u )
            v4 = (_QWORD *)*v4;
          v84 = v4;
          v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v84);
          v33 = v30(v29, v89, *(_QWORD *)(v32 + 24), v31, 0, &v90);
          if ( v33 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v33);
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v105, v33);
            throw (ErrorCodeException *)v105;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_49666091>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49666091>::GetImpl'::`2'::impl) )
            Private::AddSsoPropertyToWebRequest(&v90);
          v88 = 0;
          v34 = *(wpc::MicrosoftAccount::UserTicketResult **)(v85 + 40);
          if ( v34 )
          {
            v84 = 0;
            v35 = v86;
            v36 = *(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD, _QWORD **))(*v86 + 80LL);
            if ( *((_QWORD *)v34 + 3) > 7u )
              v34 = *(wpc::MicrosoftAccount::UserTicketResult **)v34;
            v97 = v34;
            v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v114, &v97);
            v38 = v36(v35, v89, *(_QWORD *)(v37 + 24), &v84);
            if ( v38 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                  (unsigned int)v38);
              }
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)v106, v38);
              throw (ErrorCodeException *)v106;
            }
            v85 = 0;
            v39 = v84;
            v40 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(v84);
            if ( v40 < 0 || (v40 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v39 + 64LL))(v39, &v85), v40 < 0) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  22,
                  WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                  (unsigned int)v40);
              }
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)v108, v40);
              throw (ErrorCodeException *)v108;
            }
            v41 = v86;
            v42 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, __int64 *))(*v86 + 56LL);
            v43 = v88;
            if ( v88 )
            {
              v88 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            }
            v44 = v42(v41, v90, v85, &v88);
            if ( v44 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  23,
                  WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                  (unsigned int)v44);
              }
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)v107, v44);
              throw (ErrorCodeException *)v107;
            }
            v45 = v85;
            if ( v85 )
            {
              v85 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            }
            v46 = v84;
            if ( v84 )
            {
              v84 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
            }
          }
          else
          {
            v50 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(*v86 + 48LL))(v86, v90, &v88);
            if ( v50 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                  (unsigned int)v50);
              }
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)v109, v50);
              throw (ErrorCodeException *)v109;
            }
          }
          v87 = 0;
          v47 = v88;
          v48 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v88);
          if ( v48 < 0
            || (v48 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 64LL))(v47, &v87), v48 < 0) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v48);
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v101, v48);
            throw (ErrorCodeException *)v101;
          }
          v83 = 0;
          v49 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v87 + 56LL))(v87, &v83);
          if ( v49 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v49);
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v110, v49);
            throw (ErrorCodeException *)v110;
          }
          v51 = v83;
          if ( (unsigned __int64)(int)v83 >= 6 )
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_54;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_d559cce52a1433e229f26c816596a62e_Traceguids, v83);
          }
          else
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_54;
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)&Private::StatusString,
              v83,
              v83,
              (__int64)(&Private::StatusString)[v83]);
          }
          v51 = v83;
LABEL_54:
          if ( v51 )
          {
            LODWORD(v85) = 0;
            v84 = 0;
            if ( (*(int (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v87 + 64LL))(v87, &v84) >= 0 )
              (*(void (__fastcall **)(_QWORD *, __int64 *))(*v84 + 48LL))(v84, &v85);
            v52 = v84;
            if ( v84 )
            {
              v84 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v52 + 16LL))(v52);
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                v83,
                v85);
            if ( v83 != 1 )
            {
              if ( v83 == 3 )
              {
                v84 = 0;
                v53 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v87 + 72LL))(v87, &v84);
                v54 = v53;
                if ( v53 >= 0 )
                {
                  v55 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v84);
                  v56 = v55;
                  if ( v55 >= 0 )
                  {
                    v57 = (unsigned int)v85;
                    if ( (_DWORD)v85 != 1317 )
                    {
                      if ( (_DWORD)v85 != -2147023579 )
                      {
                        if ( (_DWORD)v85 != 1231 )
                        {
                          if ( (_DWORD)v85 == -2147023665 )
                          {
                            wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v123, 3, 2147943631LL, v83);
                            throw (wpc::MicrosoftAccount::UserTicketResult *)v123;
                          }
                          if ( (int)v85 > 0 )
                            v57 = (unsigned __int16)v85 | 0x80070000;
                          wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v124, 4, v57, v83);
                          throw (wpc::MicrosoftAccount::UserTicketResult *)v124;
                        }
                        wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v122, 3, 2147943631LL, v83);
                        throw (wpc::MicrosoftAccount::UserTicketResult *)v122;
                      }
                      wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v121, 1, 2147943717LL, v83);
                      throw (wpc::MicrosoftAccount::UserTicketResult *)v121;
                    }
                    wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v120, 1, 2147943717LL, v83);
                    throw (wpc::MicrosoftAccount::UserTicketResult *)v120;
                  }
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      31,
                      WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                      (unsigned int)v55);
                  }
                  ErrorCodeException::ErrorCodeException((ErrorCodeException *)v112, v56);
                  throw (ErrorCodeException *)v112;
                }
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    30,
                    WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                    (unsigned int)v53);
                }
                ErrorCodeException::ErrorCodeException((ErrorCodeException *)v111, v54);
                throw (ErrorCodeException *)v111;
              }
              v77 = (unsigned int)v85;
              if ( (int)v85 > 0 )
                v77 = (unsigned __int16)v85 | 0x80070000;
              wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v125, 3, v77, v83);
              throw (wpc::MicrosoftAccount::UserTicketResult *)v125;
            }
            v78 = (unsigned int)v85;
            if ( (int)v85 > 0 )
              v78 = (unsigned __int16)v85 | 0x80070000;
            wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v126, 2, v78, 1);
            throw (wpc::MicrosoftAccount::UserTicketResult *)v126;
          }
          v93 = 0;
          v58 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v87 + 48LL))(v87, &v93);
          v59 = v58;
          if ( v58 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                32,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v58);
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v113, v59);
            throw (ErrorCodeException *)v113;
          }
          v92 = 0;
          v60 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v93 + 48LL))(v93, 0, &v92);
          v61 = v60;
          if ( v60 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                33,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v60);
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v99, v61);
            throw (ErrorCodeException *)v99;
          }
          v96 = 0;
          v62 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v92 + 48LL))(v92, &v96);
          v63 = v62;
          if ( v62 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                34,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v62);
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v100, v63);
            throw (ErrorCodeException *)v100;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(v96, 0);
          v118 = 0;
          v119 = 0;
          v65 = -1;
          do
            ++v65;
          while ( StringRawBuffer[v65] );
          std::wstring::_Construct<1,unsigned short const *>(&v118, StringRawBuffer, v65);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v66 = &v118;
            if ( *((_QWORD *)&v119 + 1) > 7u )
              v66 = (__int128 *)v118;
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_d559cce52a1433e229f26c816596a62e_Traceguids, v66);
          }
          v97 = a1;
          *((_QWORD *)a1 + 2) = 0;
          *((_QWORD *)a1 + 8) = 0;
          std::wstring::wstring((char *)a1 + 32, &v118);
          *((_QWORD *)a1 + 8) = (char *)a1 + 32;
          std::wstring::~wstring(&v118);
          if ( v96 )
            WindowsDeleteString(v96);
          v67 = v92;
          if ( v92 )
          {
            v92 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
          }
          v68 = v93;
          if ( v93 )
          {
            v93 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
          }
          v69 = v87;
          if ( v87 )
          {
            v87 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
          }
          v70 = v88;
          if ( v88 )
          {
            v88 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
          }
          v71 = v90;
          if ( v90 )
          {
            v90 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
          }
          v72 = v91;
          if ( v91 )
          {
            v91 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
          }
          v73 = v89;
          if ( v89 )
          {
            v89 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
          }
          v74 = v94;
          if ( v94 )
          {
            v94 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
          }
          v75 = v86;
          if ( v86 )
          {
            v86 = 0;
            (*(void (__fastcall **)(_QWORD *, _QWORD))(*v75 + 16LL))(v75, *v75);
          }
          return a1;
        }
LABEL_109:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)(v14 + 17),
            WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
            (unsigned int)v13);
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)v103, (int)v13);
        throw (ErrorCodeException *)v103;
      }
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
    goto LABEL_109;
  }
  catch ( const wpc::MicrosoftAccount::UserTicketResult *v98 )
  {
    wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v95, v98);
    return v95;
  }
  catch ( ... )
  {
    v81 = ErrorCodeFromCaughtException();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_d559cce52a1433e229f26c816596a62e_Traceguids, v81);
    v82 = v95;
    *((_QWORD *)v95 + 2) = 0;
    *((_QWORD *)v82 + 8) = 0;
    *((_DWORD *)v82 + 1) = 0;
    *((_DWORD *)v82 + 2) = v81;
    *((_DWORD *)v82 + 3) = 3;
    *((_QWORD *)v82 + 2) = (char *)v82 + 4;
    return v95;
  }
  return result;
}

```

## disassembly

```asm
0x1800525e4  push    rbx
0x1800525e6  push    rsi
0x1800525e7  push    rdi
0x1800525e8  push    r12
0x1800525ea  push    r13
0x1800525ec  push    r14
0x1800525ee  push    r15
0x1800525f0  sub     rsp, 620h
0x1800525f7  mov     rax, cs:__security_cookie
0x1800525fe  xor     rax, rsp
0x180052601  mov     [rsp+658h+var_48], rax
0x180052609  mov     [rsp+658h+var_608], r9
0x18005260e  mov     rdi, rdx
0x180052611  mov     r14, rcx
0x180052614  mov     [rsp+658h+var_5B8], rcx
0x18005261c  xor     r12d, r12d
0x18005261f  lea     r15, WPP_GLOBAL_Control
0x180052626  mov     rcx, cs:WPP_GLOBAL_Control
0x18005262d  cmp     rcx, r15
0x180052630  jz      short loc_180052694
0x180052632  test    byte ptr [rcx+1Ch], 4
0x180052636  jz      short loc_180052668
0x180052638  cmp     qword ptr [rdx+18h], 7
0x18005263d  jbe     short loc_180052644
0x18005263f  mov     r9, [rdx]
0x180052642  jmp     short loc_180052647
0x180052644  mov     r9, rdi
0x180052647  mov     edx, 0Ch
0x18005264c  lea     rbx, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x180052653  mov     r8, rbx
0x180052656  mov     rcx, [rcx+10h]
0x18005265a  call    WPP_SF_S
0x18005265f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052666  jmp     short loc_18005266F
0x180052668  lea     rbx, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x18005266f  cmp     rcx, r15
0x180052672  jz      short loc_18005269B
0x180052674  test    byte ptr [rcx+1Ch], 4
0x180052678  jz      short loc_18005269B
0x18005267a  mov     edx, 0Dh
0x18005267f  lea     r9, aF1273a19B98746; "{f1273a19-b987-46a7-8564-c35a5e715902}"
0x180052686  mov     r8, rbx
0x180052689  mov     rcx, [rcx+10h]
0x18005268d  call    WPP_SF_S
0x180052692  jmp     short loc_18005269B
0x180052694  lea     rbx, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x18005269b  mov     [rsp+658h+var_600], r12
0x1800526a0  mov     [rsp+658h+string], r12
0x1800526a8  lea     r9, [rsp+658h+string]; string
0x1800526b0  lea     r8, [rsp+658h+hstringHeader]; hstringHeader
0x1800526b8  mov     edx, 45h ; 'E'; length
0x1800526bd  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800526c4  call    cs:__imp_WindowsCreateStringReference
0x1800526ca  test    eax, eax
0x1800526cc  js      loc_180052EFF
0x1800526d2  mov     rsi, [rsp+658h+string]
0x1800526da  mov     rcx, [rsp+658h+var_600]
0x1800526df  test    rcx, rcx
0x1800526e2  jz      short loc_1800526F6
0x1800526e4  mov     [rsp+658h+var_600], r12
0x1800526e9  mov     rax, [rcx]
0x1800526ec  mov     rax, [rax+10h]
0x1800526f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526f5  nop
0x1800526f6  lea     r8, [rsp+658h+var_600]
0x1800526fb  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180052702  mov     rcx, rsi
0x180052705  call    cs:__imp_RoGetActivationFactory
0x18005270b  mov     esi, eax
0x18005270d  test    eax, eax
0x18005270f  js      loc_180052F07
0x180052715  mov     [rsp+658h+var_5C0], r12
0x18005271d  mov     rsi, [rsp+658h+var_600]
0x180052722  mov     r13, [rsi]
0x180052725  mov     [rsp+658h+string], r12
0x18005272d  lea     r9, [rsp+658h+string]; string
0x180052735  lea     r8, [rsp+658h+hstringHeader]; hstringHeader
0x18005273d  mov     edx, 9; length
0x180052742  lea     rcx, aConsumers; "consumers"
0x180052749  call    cs:__imp_WindowsCreateStringReference
0x18005274f  test    eax, eax
0x180052751  js      loc_180052F51
0x180052757  mov     r15, [rsp+658h+string]
0x18005275f  mov     [rsp+658h+var_318], r12
0x180052767  lea     r9, [rsp+658h+var_318]; string
0x18005276f  lea     r8, [rsp+658h+var_330]; hstringHeader
0x180052777  mov     edx, 1Bh; length
0x18005277c  lea     rcx, aHttpsLoginMicr; "https://login.microsoft.com"
0x180052783  call    cs:__imp_WindowsCreateStringReference
0x180052789  test    eax, eax
0x18005278b  js      loc_180052F59
0x180052791  lea     r9, [rsp+658h+var_5C0]
0x180052799  mov     r8, r15
0x18005279c  mov     rdx, [rsp+658h+var_318]
0x1800527a4  mov     rcx, rsi
0x1800527a7  mov     rax, [r13+60h]
0x1800527ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527b0  mov     esi, eax
0x1800527b2  xor     r13d, r13d
0x1800527b5  test    eax, eax
0x1800527b7  js      loc_180052F61
0x1800527bd  mov     [rsp+658h+var_5E8], r13
0x1800527c2  lea     rdx, [rsp+658h+var_5E8]
0x1800527c7  mov     rcx, [rsp+658h+var_5C0]
0x1800527cf  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x1800527d4  mov     esi, eax
0x1800527d6  test    eax, eax
0x1800527d8  js      loc_18005352C
0x1800527de  cmp     [rsp+658h+var_5E8], r13
0x1800527e3  jz      loc_18005352C
0x1800527e9  mov     [rsp+658h+var_5D8], r13
0x1800527f1  mov     [rsp+658h+var_318], r13
0x1800527f9  lea     r9, [rsp+658h+var_318]; string
0x180052801  lea     r8, [rsp+658h+var_330]; hstringHeader
0x180052809  mov     edx, 38h ; '8'; length
0x18005280e  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180052815  call    cs:__imp_WindowsCreateStringReference
0x18005281b  test    eax, eax
0x18005281d  js      loc_180052FB1
0x180052823  mov     rsi, [rsp+658h+var_318]
0x18005282b  mov     rcx, [rsp+658h+var_5D8]
0x180052833  test    rcx, rcx
0x180052836  jz      short loc_18005284D
0x180052838  mov     [rsp+658h+var_5D8], r13
0x180052840  mov     rax, [rcx]
0x180052843  mov     rax, [rax+10h]
0x180052847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005284c  nop
0x18005284d  lea     r8, [rsp+658h+var_5D8]
0x180052855  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x18005285c  mov     rcx, rsi
0x18005285f  call    cs:__imp_RoGetActivationFactory
0x180052865  mov     esi, eax
0x180052867  test    eax, eax
0x180052869  js      loc_180052FB9
0x18005286f  mov     [rsp+658h+var_5E0], r13
0x180052874  mov     rsi, [rsp+658h+var_5D8]
0x18005287c  mov     rax, [rsi]
0x18005287f  mov     r12, [rax+38h]
0x180052883  lea     rdx, off_1800B3C30; "{f1273a19-b987-46a7-8564-c35a5e715902}"
0x18005288a  lea     rcx, [rsp+658h+var_330]
0x180052892  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180052897  nop
0x180052898  mov     r15, [rax+18h]
0x18005289c  cmp     qword ptr [rdi+18h], 7
0x1800528a1  jbe     short loc_1800528A6
0x1800528a3  mov     rdi, [rdi]
0x1800528a6  mov     [rsp+658h+var_610], rdi
0x1800528ab  lea     rdx, [rsp+658h+var_610]
0x1800528b0  lea     rcx, [rsp+658h+hstringHeader]
0x1800528b8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800528bd  nop
0x1800528be  lea     rcx, [rsp+658h+var_5E0]
0x1800528c3  mov     [rsp+658h+var_630], rcx
0x1800528c8  mov     dword ptr [rsp+658h+var_638], r13d
0x1800528cd  mov     r9, r15
0x1800528d0  mov     r8, [rax+18h]
0x1800528d4  mov     rdx, [rsp+658h+var_5E8]
0x1800528d9  mov     rcx, rsi
0x1800528dc  mov     rax, r12
0x1800528df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528e4  mov     edi, eax
0x1800528e6  test    eax, eax
0x1800528e8  js      loc_18005300A
0x1800528ee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_49666091@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_49666091@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49666091> `wil::Feature<__WilFeatureTraits_Feature_49666091>::GetImpl(void)'::`2'::impl
0x1800528f5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_49666091@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49666091>::__private_IsEnabled(void)
0x1800528fa  test    al, al
0x1800528fc  jz      short loc_180052908
0x1800528fe  lea     rcx, [rsp+658h+var_5E0]
0x180052903  call    ?AddSsoPropertyToWebRequest@Private@@YAXAEAV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Z; Private::AddSsoPropertyToWebRequest(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> &)
0x180052908  mov     [rsp+658h+var_5F0], r13
0x18005290d  mov     rcx, [rsp+658h+var_608]
0x180052912  mov     rcx, [rcx+28h]
0x180052916  test    rcx, rcx
0x180052919  jz      loc_180052A9A
0x18005291f  mov     [rsp+658h+var_610], r13
0x180052924  mov     rdi, [rsp+658h+var_600]
0x180052929  mov     rax, [rdi]
0x18005292c  mov     rsi, [rax+50h]
0x180052930  cmp     qword ptr [rcx+18h], 7
0x180052935  jbe     short loc_18005293A
0x180052937  mov     rcx, [rcx]
0x18005293a  mov     [rsp+658h+var_5A0], rcx
0x180052942  lea     rdx, [rsp+658h+var_5A0]
0x18005294a  lea     rcx, [rsp+658h+var_330]
0x180052952  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180052957  nop
0x180052958  lea     r9, [rsp+658h+var_610]
0x18005295d  mov     r8, [rax+18h]
0x180052961  mov     rdx, [rsp+658h+var_5E8]
0x180052966  mov     rcx, rdi
0x180052969  mov     rax, rsi
0x18005296c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052971  mov     edi, eax
0x180052973  test    eax, eax
0x180052975  js      loc_18005305B
0x18005297b  mov     [rsp+658h+var_608], r13
0x180052980  mov     rsi, [rsp+658h+var_610]
0x180052985  mov     rcx, rsi
0x180052988  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)
0x18005298d  mov     edi, eax
0x18005298f  test    eax, eax
0x180052991  js      loc_18005314E
0x180052997  mov     rax, [rsi]
0x18005299a  lea     rdx, [rsp+658h+var_608]
0x18005299f  mov     rcx, rsi
0x1800529a2  mov     rax, [rax+40h]
0x1800529a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529ab  mov     edi, eax
0x1800529ad  test    eax, eax
0x1800529af  js      loc_18005314E
0x1800529b5  mov     rdi, [rsp+658h+var_600]
0x1800529ba  mov     rax, [rdi]
0x1800529bd  mov     rsi, [rax+38h]
0x1800529c1  mov     rcx, [rsp+658h+var_5F0]
0x1800529c6  test    rcx, rcx
0x1800529c9  jz      short loc_1800529DD
0x1800529cb  mov     [rsp+658h+var_5F0], r13
0x1800529d0  mov     rax, [rcx]
0x1800529d3  mov     rax, [rax+10h]
0x1800529d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529dc  nop
0x1800529dd  lea     r9, [rsp+658h+var_5F0]
0x1800529e2  mov     r8, [rsp+658h+var_608]
0x1800529e7  mov     rdx, [rsp+658h+var_5E0]
0x1800529ec  mov     rcx, rdi
0x1800529ef  mov     rax, rsi
0x1800529f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529f7  mov     edi, eax
0x1800529f9  test    eax, eax
0x1800529fb  js      loc_1800530AC
0x180052a01  mov     rcx, [rsp+658h+var_608]
0x180052a06  test    rcx, rcx
0x180052a09  jz      short loc_180052A1D
0x180052a0b  mov     [rsp+658h+var_608], r13
0x180052a10  mov     rax, [rcx]
0x180052a13  mov     rax, [rax+10h]
0x180052a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a1c  nop
0x180052a1d  mov     rcx, [rsp+658h+var_610]
0x180052a22  test    rcx, rcx
0x180052a25  jz      short loc_180052A39
0x180052a27  mov     [rsp+658h+var_610], r13
0x180052a2c  mov     rax, [rcx]
0x180052a2f  mov     rax, [rax+10h]
0x180052a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a38  nop
0x180052a39  mov     [rsp+658h+var_5F8], r13
0x180052a3e  mov     rsi, [rsp+658h+var_5F0]
0x180052a43  mov     rcx, rsi
0x180052a46  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)
0x180052a4b  mov     edi, eax
0x180052a4d  test    eax, eax
0x180052a4f  js      loc_1800534DB
0x180052a55  mov     rax, [rsi]
0x180052a58  lea     rdx, [rsp+658h+var_5F8]
0x180052a5d  mov     rcx, rsi
0x180052a60  mov     rax, [rax+40h]
0x180052a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a69  mov     edi, eax
0x180052a6b  test    eax, eax
0x180052a6d  js      loc_1800534DB
0x180052a73  mov     [rsp+658h+var_618], r13d
0x180052a78  mov     rcx, [rsp+658h+var_5F8]
0x180052a7d  mov     rax, [rcx]
0x180052a80  lea     rdx, [rsp+658h+var_618]
0x180052a85  mov     rax, [rax+38h]
0x180052a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a8e  mov     edi, eax
0x180052a90  test    eax, eax
0x180052a92  js      loc_1800530FD
0x180052a98  jmp     short loc_180052AC4
0x180052a9a  mov     rcx, [rsp+658h+var_600]
0x180052a9f  mov     rax, [rcx]
0x180052aa2  lea     r8, [rsp+658h+var_5F0]
0x180052aa7  mov     rdx, [rsp+658h+var_5E0]
0x180052aac  mov     rax, [rax+30h]
0x180052ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ab5  mov     edi, eax
0x180052ab7  test    eax, eax
0x180052ab9  js      loc_18005319F
0x180052abf  jmp     loc_180052A39
0x180052ac4  movsxd  r8, [rsp+658h+var_618]
0x180052ac9  cmp     r8, 6
0x180052acd  jnb     short loc_180052B06
0x180052acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ad6  lea     rsi, WPP_GLOBAL_Control
0x180052add  cmp     rcx, rsi
0x180052ae0  jz      short loc_180052B38
0x180052ae2  test    byte ptr [rcx+1Ch], 4
0x180052ae6  jz      short loc_180052B38
0x180052ae8  lea     rdx, ?StatusString@Private@@3PAPEBGA; ushort const * near * Private::StatusString
0x180052aef  mov     rax, [rdx+r8*8]
0x180052af3  mov     [rsp+658h+var_638], rax
0x180052af8  mov     r9d, r8d
0x180052afb  mov     rcx, [rcx+10h]
0x180052aff  call    WPP_SF_dS
0x180052b04  jmp     short loc_180052B33
0x180052b06  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b0d  lea     rsi, WPP_GLOBAL_Control
  ... truncated ...
```
