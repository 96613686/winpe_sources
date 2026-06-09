# IsCallingProcessChildAccount(void)

- ea: `0x1800337d0`
- end: `0x180034890`
- name: `?IsCallingProcessChildAccount@@YA_NXZ`
- size: `4288`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032f38`

## callees

- `0x180002520`
- `0x180011e18`
- `0x180013270`
- `0x180031b58`
- `0x180031d64`
- `0x1800337d0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033869`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800342c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800342f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033869`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800342c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800342f4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003389b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003389b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800338da`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800339c9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033a9e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033bbc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033c58`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033dd1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033f44`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800340be`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034234`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800344d8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034625`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034759`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800347ea`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800338da`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800339c9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033a9e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033bbc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033c58`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033dd1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033f44`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800340be`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034234`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800344d8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034625`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034759`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800347ea`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180033805`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180033805`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003395d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003395d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033e8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034015`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003417b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003418b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003436b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034394`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003441f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003442f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003456c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003457c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800346a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800346b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033e8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034015`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003417b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003418b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003436b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034394`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003441f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003442f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003456c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003457c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800346a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800346b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800342a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800342db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800342a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800342db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800343bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800343f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800343bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800343f1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180033976`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180033976`

## string_xrefs

- `0x18003487e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18003384a`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x1800338c8`: `CreateTokenBrokerInternalStatics failed: %#x`
- `0x18003399b`: `ConvertAndSetProxyT<ITokenBrokerInternalStatics5> failed: %#x`
- `0x1800347bc`: `BlockOnCompletionAndGetResults failed: %#x`
- `0x180034409`: `The AgeGroup was %ws (considering a child).`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
char IsCallingProcessChildAccount(void)
{
  HRESULT v0; // eax
  int ActivationFactory; // ebx
  IUnknown *v2; // rcx
  int v3; // eax
  IUnknown *v4; // rcx
  int v5; // eax
  HRESULT v6; // edx
  __int64 v7; // r8
  IUnknown *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rcx
  int DefaultSignInAccount; // eax
  int v14; // eax
  IUnknown *v15; // rcx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  IUnknown *v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v28; // rcx
  IUnknown *v29; // rcx
  __int64 (__fastcall ***v30)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  __int64 (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rcx
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v41; // rcx
  IUnknown *v42; // rcx
  __int64 (__fastcall ***v43)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v47)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v48; // rcx
  int v49; // eax
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 (__fastcall ***v53)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v54; // rcx
  IUnknown *v55; // rcx
  __int64 (__fastcall ***v56)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rbx
  __int64 (__fastcall *v60)(__int64, __int64 *); // rdi
  __int64 v61; // rcx
  int v62; // eax
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 (__fastcall ***v66)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v67; // rcx
  IUnknown *v68; // rcx
  __int64 (__fastcall ***v69)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rbx
  void (__fastcall *v73)(__int64, __int64 *); // rdi
  __int64 v74; // rcx
  __int64 v75; // rdi
  void (__fastcall *v76)(__int64, HSTRING *); // rbx
  __int64 v77; // rdi
  void (__fastcall *v78)(__int64, HSTRING *); // rbx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 (__fastcall ***v82)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v83; // rcx
  IUnknown *v84; // rcx
  __int64 (__fastcall ***v85)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  IUnknown *v88; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 (__fastcall ***v93)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v94; // rcx
  IUnknown *v95; // rcx
  __int64 (__fastcall ***v96)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rcx
  __int64 v100; // rcx
  __int64 v101; // rcx
  __int64 (__fastcall ***v102)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v103; // rcx
  IUnknown *v104; // rcx
  __int64 (__fastcall ***v105)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  IUnknown *v108; // rcx
  __int64 v109; // rcx
  __int64 v110; // rcx
  IUnknown *v111; // rcx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  char v113[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v114)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v115; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v116; // [rsp+58h] [rbp-A8h] BYREF
  IUnknown *v117; // [rsp+60h] [rbp-A0h]
  IUnknown *v118; // [rsp+68h] [rbp-98h] BYREF
  __int64 v119; // [rsp+70h] [rbp-90h] BYREF
  __int64 v120; // [rsp+78h] [rbp-88h] BYREF
  __int64 v121; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v122)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-78h] BYREF
  __int64 v123; // [rsp+90h] [rbp-70h] BYREF
  IUnknown *pProxy; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v125; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string1; // [rsp+A8h] [rbp-58h] BYREF
  char v127; // [rsp+B0h] [rbp-50h]
  __int64 v128; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING string2; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER v132; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING v133; // [rsp+100h] [rbp+0h] BYREF
  HSTRING_HEADER v134; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v117 = 0;
  v116 = 0;
  v115 = 0;
  v114 = 0;
  v0 = CoImpersonateClient();
  if ( v0 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14AA,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v0,
      dwAuthnLevel);
  v127 = 1;
  pProxy = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
         0x40u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &pProxy);
  if ( ActivationFactory >= 0 )
  {
    CoSetProxyBlanket(
      pProxy,
      0xFFFFFFFF,
      0xFFFFFFFF,
      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
      0,
      3u,
      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
      0x40u);
    v117 = pProxy;
    v128 = 0;
    UMgrQueryUserContext(0, &v128);
    v118 = 0;
    v3 = Windows::Internal::Security::Authentication::TokenBroker::ConvertAndSetProxyT<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5>(
           (__int64)v117,
           &v118);
    if ( v3 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64 *))v118->lpVtbl[2].AddRef)(v118, v128, &v115);
      if ( v5 >= 0 )
      {
        v11 = v115;
        v12 = v116;
        if ( v116 )
        {
          v116 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
        DefaultSignInAccount = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(
                                 v11,
                                 v6,
                                 v7);
        if ( DefaultSignInAccount < 0
          || (DefaultSignInAccount = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 64LL))(v11, &v116),
              DefaultSignInAccount < 0) )
        {
          Log(2u, L"BlockOnCompletionAndGetResults failed: %#x", (unsigned int)DefaultSignInAccount);
          v108 = v118;
          if ( v118 )
          {
            v118 = 0;
            ((void (__fastcall *)(IUnknown *))v108->lpVtbl->Release)(v108);
          }
          CoRevertToSelf();
          v109 = v115;
          if ( v115 )
          {
            v115 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
          }
          v110 = v116;
          if ( v116 )
          {
            v116 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
          }
        }
        else
        {
          v14 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v116 + 48LL))(
                  v116,
                  &v114);
          if ( v14 >= 0 )
          {
            if ( v114 )
            {
              v123 = 0;
              v122 = 0;
              v121 = 0;
              v119 = 0;
              v120 = 0;
              string1 = 0;
              v125 = 0;
              v113[0] = 0;
              v23 = (**v114)(v114, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v123);
              if ( v23 >= 0 )
              {
                v33 = v123;
                v34 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v123 + 56LL);
                v35 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
                if ( v122 )
                {
                  v122 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v35)[2])(v35);
                }
                v36 = v34(v33, &v122);
                if ( v36 >= 0 )
                {
                  v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
                  v47 = **v122;
                  v48 = v121;
                  if ( v121 )
                  {
                    v121 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
                  }
                  v49 = v47(v46, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v121);
                  if ( v49 >= 0 )
                  {
                    v59 = v121;
                    v60 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v121 + 48LL);
                    v61 = v119;
                    if ( v119 )
                    {
                      v119 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                    }
                    v62 = v60(v59, &v119);
                    if ( v62 >= 0 )
                    {
                      if ( WindowsCreateStringReference(L"AgeGroup", 8u, &v132, &string2) < 0 )
                        RaiseException(0xC000000D, 1u, 0, 0);
                      if ( WindowsCreateStringReference(L"3", 1u, &v134, &v133) < 0 )
                        RaiseException(0xC000000D, 1u, 0, 0);
                      while ( 1 )
                      {
                        if ( (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v119 + 56LL))(v119, v113)
                          || !v113[0] )
                        {
                          Log(4u, L"AgeGroup for user is unknown.");
                          if ( v125 )
                            WindowsDeleteString(v125);
                          if ( string1 )
                            WindowsDeleteString(string1);
                          v99 = v120;
                          if ( v120 )
                          {
                            v120 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
                          }
                          v100 = v119;
                          if ( v119 )
                          {
                            v119 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
                          }
                          v101 = v121;
                          if ( v121 )
                          {
                            v121 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
                          }
                          v102 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
                          if ( v122 )
                          {
                            v122 = 0;
                            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v102)[2])(v102);
                          }
                          v103 = v123;
                          if ( v123 )
                          {
                            v123 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
                          }
                          v104 = v118;
                          if ( v118 )
                          {
                            v118 = 0;
                            ((void (__fastcall *)(IUnknown *))v104->lpVtbl->Release)(v104);
                          }
                          CoRevertToSelf();
                          v105 = v114;
                          if ( v114 )
                          {
                            v114 = 0;
                            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v105)[2])(v105);
                          }
                          v106 = v115;
                          if ( v115 )
                          {
                            v115 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
                          }
                          v107 = v116;
                          if ( v116 )
                          {
                            v116 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
                          }
                          goto LABEL_234;
                        }
                        v72 = v119;
                        v73 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v119 + 48LL);
                        v74 = v120;
                        if ( v120 )
                        {
                          v120 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
                        }
                        v73(v72, &v120);
                        v75 = v120;
                        v76 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v120 + 48LL);
                        WindowsDeleteString(string1);
                        string1 = 0;
                        v76(v75, &string1);
                        v77 = v120;
                        v78 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v120 + 56LL);
                        WindowsDeleteString(v125);
                        v125 = 0;
                        v78(v77, &v125);
                        LODWORD(pProxy) = 0;
                        WindowsCompareStringOrdinal(string1, string2, (INT32 *)&pProxy);
                        if ( !(_DWORD)pProxy )
                          break;
                        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v119 + 64LL))(v119, v113);
                      }
                      LODWORD(pProxy) = 0;
                      WindowsCompareStringOrdinal(v125, v133, (INT32 *)&pProxy);
                      if ( (_DWORD)pProxy )
                      {
                        Log(4u, L"The AgeGroup was %ws (considering a child).", v125);
                        if ( v125 )
                          WindowsDeleteString(v125);
                        if ( string1 )
                          WindowsDeleteString(string1);
                        v79 = v120;
                        if ( v120 )
                        {
                          v120 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
                        }
                        v80 = v119;
                        if ( v119 )
                        {
                          v119 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
                        }
                        v81 = v121;
                        if ( v121 )
                        {
                          v121 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
                        }
                        v82 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
                        if ( v122 )
                        {
                          v122 = 0;
                          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v82)[2])(v82);
                        }
                        v83 = v123;
                        if ( v123 )
                        {
                          v123 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
                        }
                        v84 = v118;
                        if ( v118 )
                        {
                          v118 = 0;
                          ((void (__fastcall *)(IUnknown *))v84->lpVtbl->Release)(v84);
                        }
                        CoRevertToSelf();
                        v85 = v114;
                        if ( v114 )
                        {
                          v114 = 0;
                          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v85)[2])(v85);
                        }
                        v86 = v115;
                        if ( v115 )
                        {
                          v115 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
                        }
                        v87 = v116;
                        if ( v116 )
                        {
                          v116 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
                        }
                        v88 = v117;
                        if ( v117 )
                        {
                          v117 = 0;
                          ((void (__fastcall *)(IUnknown *))v88->lpVtbl->Release)(v88);
                        }
                        return 1;
                      }
                      Log(4u, L"The AgeGroup was 3 (Adult).");
                      if ( v125 )
                        WindowsDeleteString(v125);
                      if ( string1 )
                        WindowsDeleteString(string1);
                      v90 = v120;
                      if ( v120 )
                      {
                        v120 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                      }
                      v91 = v119;
                      if ( v119 )
                      {
                        v119 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                      }
                      v92 = v121;
                      if ( v121 )
                      {
                        v121 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                      }
                      v93 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
                      if ( v122 )
                      {
                        v122 = 0;
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v93)[2])(v93);
                      }
                      v94 = v123;
                      if ( v123 )
                      {
                        v123 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                      }
                      v95 = v118;
                      if ( v118 )
                      {
                        v118 = 0;
                        ((void (__fastcall *)(IUnknown *))v95->lpVtbl->Release)(v95);
                      }
                      CoRevertToSelf();
                      v96 = v114;
                      if ( v114 )
                      {
                        v114 = 0;
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v96)[2])(v96);
                      }
                      v97 = v115;
                      if ( v115 )
                      {
                        v115 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                      }
                      v98 = v116;
                      if ( v116 )
                      {
                        v116 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                      }
                    }
                    else
                    {
                      Log(2u, L"Failed to get iterator from iteratable: %#x", (unsigned int)v62);
                      if ( v125 )
                        WindowsDeleteString(v125);
                      if ( string1 )
                        WindowsDeleteString(string1);
                      v63 = v120;
                      if ( v120 )
                      {
                        v120 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
                      }
                      v64 = v119;
                      if ( v119 )
                      {
                        v119 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
                      }
                      v65 = v121;
                      if ( v121 )
                      {
                        v121 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                      }
                      v66 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
                      if ( v122 )
                      {
                        v122 = 0;
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v66)[2])(v66);
                      }
                      v67 = v123;
                      if ( v123 )
                      {
                        v123 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
                      }
                      v68 = v118;
                      if ( v118 )
                      {
                        v118 = 0;
                        ((void (__fastcall *)(IUnknown *))v68->lpVtbl->Release)(v68);
                      }
                      CoRevertToSelf();
                      v69 = v114;
                      if ( v114 )
                      {
                        v114 = 0;
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v69)[2])(v69);
                      }
                      v70 = v115;
                      if ( v115 )
                      {
                        v115 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
                      }
                      v71 = v116;
                      if ( v116 )
                      {
                        v116 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
                      }
                    }
                  }
                  else
                  {
                    Log(2u, L"Failed to cast properties to IIterable: %#x", (unsigned int)v49);
                    if ( v125 )
                      WindowsDeleteString(v125);
                    if ( string1 )
                      WindowsDeleteString(string1);
                    v50 = v120;
                    if ( v120 )
                    {
                      v120 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                    }
                    v51 = v119;
                    if ( v119 )
                    {
                      v119 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                    }
                    v52 = v121;
                    if ( v121 )
                    {
                      v121 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                    }
                    v53 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
                    if ( v122 )
                    {
                      v122 = 0;
                      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v53)[2])(v53);
                    }
                    v54 = v123;
                    if ( v123 )
                    {
                      v123 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
                    }
                    v55 = v118;
                    if ( v118 )
                    {
                      v118 = 0;
                      ((void (__fastcall *)(IUnknown *))v55->lpVtbl->Release)(v55);
                    }
                    CoRevertToSelf();
                    v56 = v114;
                    if ( v114 )
                    {
                      v114 = 0;
                      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v56)[2])(v56);
                    }
                    v57 = v115;
                    if ( v115 )
                    {
                      v115 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
                    }
                    v58 = v116;
                    if ( v116 )
                    {
                      v116 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
                    }
                  }
                }
                else
                {
                  Log(2u, L"Failed to get properties from account2: %#x", (unsigned int)v36);
                  if ( v125 )
                    WindowsDeleteString(v125);
                  if ( string1 )
                    WindowsDeleteString(string1);
                  v37 = v120;
                  if ( v120 )
                  {
                    v120 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                  }
                  v38 = v119;
                  if ( v119 )
                  {
                    v119 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                  }
                  v39 = v121;
                  if ( v121 )
                  {
                    v121 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                  }
                  v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
                  if ( v122 )
                  {
                    v122 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v40)[2])(v40);
                  }
                  v41 = v123;
                  if ( v123 )
                  {
                    v123 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                  }
                  v42 = v118;
                  if ( v118 )
                  {
                    v118 = 0;
                    ((void (__fastcall *)(IUnknown *))v42->lpVtbl->Release)(v42);
                  }
                  CoRevertToSelf();
                  v43 = v114;
                  if ( v114 )
                  {
                    v114 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v43)[2])(v43);
                  }
                  v44 = v115;
                  if ( v115 )
                  {
                    v115 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                  }
                  v45 = v116;
                  if ( v116 )
                  {
                    v116 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
                  }
                }
              }
              else
              {
                Log(2u, L"Failed to cast defaultAccount to IWebAccount2: %#x", (unsigned int)v23);
                if ( v125 )
                  WindowsDeleteString(v125);
                if ( string1 )
                  WindowsDeleteString(string1);
                v24 = v120;
                if ( v120 )
                {
                  v120 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                }
                v25 = v119;
                if ( v119 )
                {
                  v119 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                }
                v26 = v121;
                if ( v121 )
                {
                  v121 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                }
                v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
                if ( v122 )
                {
                  v122 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v27)[2])(v27);
                }
                v28 = v123;
                if ( v123 )
                {
                  v123 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                }
                v29 = v118;
                if ( v118 )
                {
                  v118 = 0;
                  ((void (__fastcall *)(IUnknown *))v29->lpVtbl->Release)(v29);
                }
                CoRevertToSelf();
                v30 = v114;
                if ( v114 )
                {
                  v114 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v30)[2])(v30);
                }
                v31 = v115;
                if ( v115 )
                {
                  v115 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                }
                v32 = v116;
                if ( v116 )
                {
                  v116 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                }
              }
            }
            else
            {
              Log(4u, L"There is no default account.");
              v19 = v118;
              if ( v118 )
              {
                v118 = 0;
                ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
              }
              CoRevertToSelf();
              v20 = v114;
              if ( v114 )
              {
                v114 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v20)[2])(v20);
              }
              v21 = v115;
              if ( v115 )
              {
                v115 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              }
              v22 = v116;
              if ( v116 )
              {
                v116 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              }
            }
          }
          else
          {
            Log(2u, L"get_DefaultWebAccount failed: %#x", (unsigned int)v14);
            v15 = v118;
            if ( v118 )
            {
              v118 = 0;
              ((void (__fastcall *)(IUnknown *))v15->lpVtbl->Release)(v15);
            }
            CoRevertToSelf();
            v16 = v114;
            if ( v114 )
            {
              v114 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[2])(v16);
            }
            v17 = v115;
            if ( v115 )
            {
              v115 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
            v18 = v116;
            if ( v116 )
            {
              v116 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
          }
        }
      }
      else
      {
        Log(2u, L"GetDefaultSignInAccountAsyncForUser failed: %#x", (unsigned int)v5);
        v8 = v118;
        if ( v118 )
        {
          v118 = 0;
          ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
        }
        CoRevertToSelf();
        v9 = v115;
        if ( v115 )
        {
          v115 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        v10 = v116;
        if ( v116 )
        {
          v116 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
      }
    }
    else
    {
      Log(2u, L"ConvertAndSetProxyT<ITokenBrokerInternalStatics5> failed: %#x", (unsigned int)v3);
      v4 = v118;
      if ( v118 )
      {
        v118 = 0;
        ((void (__fastcall *)(IUnknown *))v4->lpVtbl->Release)(v4);
      }
      CoRevertToSelf();
    }
  }
  else
  {
    v2 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v2->lpVtbl->Release)(v2);
    }
    Log(2u, L"CreateTokenBrokerInternalStatics failed: %#x", (unsigned int)ActivationFactory);
    CoRevertToSelf();
  }
LABEL_234:
  v111 = v117;
  if ( v117 )
  {
    v117 = 0;
    ((void (__fastcall *)(IUnknown *))v111->lpVtbl->Release)(v111);
  }
  return 0;
}

```

## disassembly

```asm
0x1800337d0  push    rbp
0x1800337d2  push    rbx
0x1800337d3  push    rsi
0x1800337d4  push    rdi
0x1800337d5  lea     rbp, [rsp-38h]
0x1800337da  sub     rsp, 138h
0x1800337e1  mov     rax, cs:__security_cookie
0x1800337e8  xor     rax, rsp
0x1800337eb  mov     [rbp+50h+var_30], rax
0x1800337ef  xor     esi, esi
0x1800337f1  mov     [rsp+150h+var_F0], rsi
0x1800337f6  mov     [rsp+150h+var_F8], rsi
0x1800337fb  mov     [rsp+150h+var_100], rsi
0x180033800  mov     [rsp+150h+var_108], rsi
0x180033805  call    cs:__imp_CoImpersonateClient
0x18003380b  mov     rcx, [rbp+58h]; this
0x18003380f  test    eax, eax
0x180033811  js      loc_18003487B
0x180033817  mov     [rbp+50h+var_A0], 1
0x18003381b  mov     rcx, [rsp+150h+var_F0]
0x180033820  test    rcx, rcx
0x180033823  jz      short loc_180033837
0x180033825  mov     [rsp+150h+var_F0], rsi
0x18003382a  mov     rax, [rcx]
0x18003382d  mov     rax, [rax+10h]
0x180033831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033836  nop
0x180033837  mov     [rbp+50h+pProxy], rsi
0x18003383b  lea     r9, [rbp+50h+string]; string
0x18003383f  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x180033843  mov     edi, 40h ; '@'
0x180033848  mov     edx, edi; length
0x18003384a  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QB_WB; "Windows.Internal.Security.Authenticatio"...
0x180033851  call    cs:__imp_WindowsCreateStringReference
0x180033857  test    eax, eax
0x180033859  jns     short loc_18003386F
0x18003385b  xor     r9d, r9d; lpArguments
0x18003385e  xor     r8d, r8d; nNumberOfArguments
0x180033861  lea     edx, [rdi-3Fh]; dwExceptionFlags
0x180033864  mov     ecx, 0C000000Dh; dwExceptionCode
0x180033869  call    cs:__imp_RaiseException
0x18003386f  mov     rbx, [rbp+50h+string]
0x180033873  mov     rcx, [rbp+50h+pProxy]
0x180033877  test    rcx, rcx
0x18003387a  jz      short loc_18003388D
0x18003387c  mov     [rbp+50h+pProxy], rsi
0x180033880  mov     rax, [rcx]
0x180033883  mov     rax, [rax+10h]
0x180033887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003388c  nop
0x18003388d  lea     r8, [rbp+50h+pProxy]
0x180033891  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x180033898  mov     rcx, rbx
0x18003389b  call    cs:__imp_RoGetActivationFactory
0x1800338a1  mov     ebx, eax
0x1800338a3  test    eax, eax
0x1800338a5  jns     loc_18003393A
0x1800338ab  mov     rcx, [rbp+50h+pProxy]
0x1800338af  test    rcx, rcx
0x1800338b2  jz      short loc_1800338C5
0x1800338b4  mov     [rbp+50h+pProxy], rsi
0x1800338b8  mov     rdx, [rcx]
0x1800338bb  mov     rax, [rdx+10h]
0x1800338bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338c4  nop
0x1800338c5  mov     r8d, ebx
0x1800338c8  lea     rdx, aCreatetokenbro; "CreateTokenBrokerInternalStatics failed"...
0x1800338cf  mov     ecx, 2; unsigned __int8
0x1800338d4  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800338d9  nop
0x1800338da  call    cs:__imp_CoRevertToSelf
0x1800338e0  nop
0x1800338e1  mov     rcx, [rsp+150h+var_108]
0x1800338e6  test    rcx, rcx
0x1800338e9  jz      short loc_1800338FD
0x1800338eb  mov     [rsp+150h+var_108], rsi
0x1800338f0  mov     rax, [rcx]
0x1800338f3  mov     rax, [rax+10h]
0x1800338f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338fc  nop
0x1800338fd  mov     rcx, [rsp+150h+var_100]
0x180033902  test    rcx, rcx
0x180033905  jz      short loc_180033919
0x180033907  mov     [rsp+150h+var_100], rsi
0x18003390c  mov     rax, [rcx]
0x18003390f  mov     rax, [rax+10h]
0x180033913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033918  nop
0x180033919  mov     rcx, [rsp+150h+var_F8]
0x18003391e  test    rcx, rcx
0x180033921  jz      short loc_180033935
0x180033923  mov     [rsp+150h+var_F8], rsi
0x180033928  mov     rax, [rcx]
0x18003392b  mov     rax, [rax+10h]
0x18003392f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033934  nop
0x180033935  jmp     loc_180034845
0x18003393a  mov     [rsp+150h+dwCapabilities], edi; dwCapabilities
0x18003393e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180033942  mov     [rsp+150h+pAuthInfo], r9; pAuthInfo
0x180033947  mov     [rsp+150h+dwImpLevel], 3; dwImpLevel
0x18003394f  mov     [rsp+150h+dwAuthnLevel], esi; dwAuthnLevel
0x180033953  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180033956  mov     r8d, edx; dwAuthzSvc
0x180033959  mov     rcx, [rbp+50h+pProxy]; pProxy
0x18003395d  call    cs:__imp_CoSetProxyBlanket
0x180033963  mov     rax, [rbp+50h+pProxy]
0x180033967  mov     [rsp+150h+var_F0], rax
0x18003396c  mov     [rbp+50h+var_98], rsi
0x180033970  lea     rdx, [rbp+50h+var_98]
0x180033974  xor     ecx, ecx
0x180033976  call    cs:__imp_UMgrQueryUserContext
0x18003397c  mov     [rsp+150h+var_E8], rsi
0x180033981  lea     rdx, [rsp+150h+var_E8]
0x180033986  mov     rcx, [rsp+150h+var_F0]
0x18003398b  call    ??$ConvertAndSetProxyT@UITokenBrokerInternalStatics5@Web@Authentication@Security@Internal@Windows@@@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUITokenBrokerInternalStatics@Web@1234@PEAPEAUITokenBrokerInternalStatics5@61234@@Z; Windows::Internal::Security::Authentication::TokenBroker::ConvertAndSetProxyT<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5>(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5 * *)
0x180033990  test    eax, eax
0x180033992  jns     loc_180033A29
0x180033998  mov     r8d, eax
0x18003399b  lea     rdx, aConvertandsetp; "ConvertAndSetProxyT<ITokenBrokerInterna"...
0x1800339a2  mov     ecx, 2; unsigned __int8
0x1800339a7  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800339ac  nop
0x1800339ad  mov     rcx, [rsp+150h+var_E8]
0x1800339b2  test    rcx, rcx
0x1800339b5  jz      short loc_1800339C9
0x1800339b7  mov     [rsp+150h+var_E8], rsi
0x1800339bc  mov     rax, [rcx]
0x1800339bf  mov     rax, [rax+10h]
0x1800339c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339c8  nop
0x1800339c9  call    cs:__imp_CoRevertToSelf
0x1800339cf  nop
0x1800339d0  mov     rcx, [rsp+150h+var_108]
0x1800339d5  test    rcx, rcx
0x1800339d8  jz      short loc_1800339EC
0x1800339da  mov     [rsp+150h+var_108], rsi
0x1800339df  mov     rax, [rcx]
0x1800339e2  mov     rax, [rax+10h]
0x1800339e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339eb  nop
0x1800339ec  mov     rcx, [rsp+150h+var_100]
0x1800339f1  test    rcx, rcx
0x1800339f4  jz      short loc_180033A08
0x1800339f6  mov     [rsp+150h+var_100], rsi
0x1800339fb  mov     rax, [rcx]
0x1800339fe  mov     rax, [rax+10h]
0x180033a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a07  nop
0x180033a08  mov     rcx, [rsp+150h+var_F8]
0x180033a0d  test    rcx, rcx
0x180033a10  jz      short loc_180033A24
0x180033a12  mov     [rsp+150h+var_F8], rsi
0x180033a17  mov     rax, [rcx]
0x180033a1a  mov     rax, [rax+10h]
0x180033a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a23  nop
0x180033a24  jmp     loc_180034845
0x180033a29  mov     rbx, [rsp+150h+var_E8]
0x180033a2e  mov     rax, [rbx]
0x180033a31  mov     rdi, [rax+38h]
0x180033a35  mov     rcx, [rsp+150h+var_100]
0x180033a3a  test    rcx, rcx
0x180033a3d  jz      short loc_180033A51
0x180033a3f  mov     [rsp+150h+var_100], rsi
0x180033a44  mov     rdx, [rcx]
0x180033a47  mov     rax, [rdx+10h]
0x180033a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a50  nop
0x180033a51  lea     r8, [rsp+150h+var_100]
0x180033a56  mov     rdx, [rbp+50h+var_98]
0x180033a5a  mov     rcx, rbx
0x180033a5d  mov     rax, rdi
0x180033a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a65  test    eax, eax
0x180033a67  jns     loc_180033AFE
0x180033a6d  mov     r8d, eax
0x180033a70  lea     rdx, aGetdefaultsign; "GetDefaultSignInAccountAsyncForUser fai"...
0x180033a77  mov     ecx, 2; unsigned __int8
0x180033a7c  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180033a81  nop
0x180033a82  mov     rcx, [rsp+150h+var_E8]
0x180033a87  test    rcx, rcx
0x180033a8a  jz      short loc_180033A9E
0x180033a8c  mov     [rsp+150h+var_E8], rsi
0x180033a91  mov     rax, [rcx]
0x180033a94  mov     rax, [rax+10h]
0x180033a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a9d  nop
0x180033a9e  call    cs:__imp_CoRevertToSelf
0x180033aa4  nop
0x180033aa5  mov     rcx, [rsp+150h+var_108]
0x180033aaa  test    rcx, rcx
0x180033aad  jz      short loc_180033AC1
0x180033aaf  mov     [rsp+150h+var_108], rsi
0x180033ab4  mov     rax, [rcx]
0x180033ab7  mov     rax, [rax+10h]
0x180033abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ac0  nop
0x180033ac1  mov     rcx, [rsp+150h+var_100]
0x180033ac6  test    rcx, rcx
0x180033ac9  jz      short loc_180033ADD
0x180033acb  mov     [rsp+150h+var_100], rsi
0x180033ad0  mov     rax, [rcx]
0x180033ad3  mov     rax, [rax+10h]
0x180033ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033adc  nop
0x180033add  mov     rcx, [rsp+150h+var_F8]
0x180033ae2  test    rcx, rcx
0x180033ae5  jz      short loc_180033AF9
0x180033ae7  mov     [rsp+150h+var_F8], rsi
0x180033aec  mov     rax, [rcx]
0x180033aef  mov     rax, [rax+10h]
0x180033af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033af8  nop
0x180033af9  jmp     loc_180034845
0x180033afe  mov     rbx, [rsp+150h+var_100]
0x180033b03  mov     rcx, [rsp+150h+var_F8]
0x180033b08  test    rcx, rcx
0x180033b0b  jz      short loc_180033B1F
0x180033b0d  mov     [rsp+150h+var_F8], rsi
0x180033b12  mov     rax, [rcx]
0x180033b15  mov     rax, [rax+10h]
0x180033b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b1e  nop
0x180033b1f  mov     rcx, rbx
0x180033b22  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)
0x180033b27  test    eax, eax
0x180033b29  js      loc_1800347B9
0x180033b2f  mov     rax, [rbx]
0x180033b32  lea     rdx, [rsp+150h+var_F8]
0x180033b37  mov     rcx, rbx
0x180033b3a  mov     rax, [rax+40h]
0x180033b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b43  test    eax, eax
0x180033b45  js      loc_1800347B9
0x180033b4b  mov     rbx, [rsp+150h+var_F8]
0x180033b50  mov     rax, [rbx]
0x180033b53  mov     rdi, [rax+30h]
0x180033b57  mov     rcx, [rsp+150h+var_108]
0x180033b5c  test    rcx, rcx
0x180033b5f  jz      short loc_180033B73
0x180033b61  mov     [rsp+150h+var_108], rsi
0x180033b66  mov     rdx, [rcx]
0x180033b69  mov     rax, [rdx+10h]
0x180033b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b72  nop
0x180033b73  lea     rdx, [rsp+150h+var_108]
0x180033b78  mov     rcx, rbx
0x180033b7b  mov     rax, rdi
0x180033b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b83  test    eax, eax
0x180033b85  jns     loc_180033C1C
0x180033b8b  mov     r8d, eax
0x180033b8e  lea     rdx, aGetDefaultweba; "get_DefaultWebAccount failed: %#x"
0x180033b95  mov     ecx, 2; unsigned __int8
0x180033b9a  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180033b9f  nop
0x180033ba0  mov     rcx, [rsp+150h+var_E8]
0x180033ba5  test    rcx, rcx
0x180033ba8  jz      short loc_180033BBC
0x180033baa  mov     [rsp+150h+var_E8], rsi
0x180033baf  mov     rax, [rcx]
0x180033bb2  mov     rax, [rax+10h]
0x180033bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bbb  nop
0x180033bbc  call    cs:__imp_CoRevertToSelf
0x180033bc2  nop
0x180033bc3  mov     rcx, [rsp+150h+var_108]
0x180033bc8  test    rcx, rcx
0x180033bcb  jz      short loc_180033BDF
0x180033bcd  mov     [rsp+150h+var_108], rsi
0x180033bd2  mov     rax, [rcx]
0x180033bd5  mov     rax, [rax+10h]
0x180033bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bde  nop
0x180033bdf  mov     rcx, [rsp+150h+var_100]
0x180033be4  test    rcx, rcx
0x180033be7  jz      short loc_180033BFB
0x180033be9  mov     [rsp+150h+var_100], rsi
0x180033bee  mov     rax, [rcx]
0x180033bf1  mov     rax, [rax+10h]
0x180033bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bfa  nop
0x180033bfb  mov     rcx, [rsp+150h+var_F8]
0x180033c00  test    rcx, rcx
0x180033c03  jz      short loc_180033C17
0x180033c05  mov     [rsp+150h+var_F8], rsi
0x180033c0a  mov     rax, [rcx]
0x180033c0d  mov     rax, [rax+10h]
0x180033c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c16  nop
0x180033c17  jmp     loc_180034845
0x180033c1c  mov     rcx, [rsp+150h+var_108]
0x180033c21  test    rcx, rcx
0x180033c24  jnz     loc_180033CB8
0x180033c2a  lea     rdx, aThereIsNoDefau; "There is no default account."
0x180033c31  mov     ecx, 4; unsigned __int8
0x180033c36  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180033c3b  nop
  ... truncated ...
```
