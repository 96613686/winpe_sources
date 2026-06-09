# TryGetTickets(bool,HSTRING__ *,TraceLoggingCorrelationVector *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *,Windows::Foundation::Collections::IVectorView<IInspectable *> * *)

- ea: `0x1800843f0`
- end: `0x180084c6d`
- name: `?TryGetTickets@@YAX_NPEAUHSTRING__@@PEAVTraceLoggingCorrelationVector@@PEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAPEAU?$IVectorView@PEAUIInspectable@@@456@@Z`
- size: `2173`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180080cb0`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800127c8`
- `0x18001c844`
- `0x18001df54`
- `0x18003f884`
- `0x18007fd04`
- `0x1800843f0`
- `0x180084cec`
- `0x180084d28`
- `0x18011b84c`
- `0x180145c58`
- `0x180149f14`
- `0x1801ecd94`
- `0x1801ecf9c`
- `0x1801ed094`
- `0x1801ed1a8`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180084497`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800844f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008497b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800849a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180084497`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800844f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008497b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800849a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008444f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008445b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008464e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084665`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008473a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084ad7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008444f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008445b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008464e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084665`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008473a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084ad7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084b95`

## string_xrefs

- `0x1800844d5`: `WinStoreAuth::GetTicketsForAccount(accountId.Get(), providerId.Get(), authority.Get(), &tickets, spWebTokenRequestResult.GetAddressOf())`
- `0x1800844e8`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180084637`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800846b8`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180084770`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180084941`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180084a29`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180084a9b`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180084b7e`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180084bc6`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180084c56`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180084515`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800849c2`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x18008453f`: `SlowResponseFromTokenBroker`
- `0x1800849ec`: `SlowResponseFromTokenBroker`
- `0x18008475d`: `WinStoreAuth::GetStorePrimaryAccountTicket( authTicket.GetAddressOf(), &providerType, spWebTokenRequestResult.GetAddressOf())`
- `0x180084ba9`: `Error attempting to fetch tickets. catalog access will be anonymous`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall TryGetTickets(unsigned __int8 a1, HSTRING a2, HSTRING a3, HSTRING *a4, _QWORD *a5)
{
  TraceLoggingCorrelationVector *v6; // rsi
  int v8; // r13d
  int StorePrimaryAccountTicketForUser; // edi
  ULONGLONG TickCount64; // rbx
  __int64 v11; // rcx
  int TicketsForAccountForUser; // eax
  HSTRING v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  HSTRING v17; // rbx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  HSTRING v23; // rsi
  __int64 (__fastcall *v24)(HSTRING, HSTRING *); // rdi
  HSTRING v25; // rax
  unsigned int v26; // r8d
  __int64 v27; // rcx
  ULONGLONG v28; // rbx
  int v29; // eax
  HSTRING v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // r9d
  struct _GUID *v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+28h] [rbp-D8h]
  unsigned int v37; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v38; // [rsp+48h] [rbp-B8h]
  HSTRING v39; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v40; // [rsp+58h] [rbp-A8h] BYREF
  int v41[2]; // [rsp+60h] [rbp-A0h] BYREF
  char *v42; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v44; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v45; // [rsp+80h] [rbp-80h] BYREF
  char v46[144]; // [rsp+90h] [rbp-70h] BYREF

  v6 = (TraceLoggingCorrelationVector *)a3;
  v44 = a3;
  v8 = a1;
  *a5 = 0;
  LODWORD(v42) = 0;
  if ( a2 )
  {
    WindowsDeleteString(0);
    string = 0;
    WindowsDeleteString(0);
    v45 = 0;
    WindowsDeleteString(0);
    v44 = 0;
    StorePrimaryAccountTicketForUser = ParseIdentityData(a2, &v44, &v45, &string, 0);
    if ( StorePrimaryAccountTicketForUser >= 0 )
    {
      v39 = 0;
      *(_QWORD *)v41 = 0;
      TickCount64 = GetTickCount64();
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
      TicketsForAccountForUser = GetTicketsForAccountForUser(v11, v44, v45, string, &v39);
      StorePrimaryAccountTicketForUser = TraceHR(
                                           "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                                           0x448u,
                                           "TryGetTickets",
                                           "WinStoreAuth::GetTicketsForAccount(accountId.Get(), providerId.Get(), authori"
                                           "ty.Get(), &tickets, spWebTokenRequestResult.GetAddressOf())",
                                           TicketsForAccountForUser,
                                           (int)v41);
      if ( GetTickCount64() - TickCount64 > 0xFA0 )
      {
        LODWORD(v35) = 0;
        WindowsUpdate::CommonTelemetry::TraceError(
          (WindowsUpdate::CommonTelemetry *)L"SlowResponseFromTokenBroker",
          L"Slow Response From WinStoreAuth::GetTicketsForAccount",
          (const unsigned __int16 *)2,
          (int)L"SlowResponse",
          (const unsigned __int16 *)v35,
          1105,
          v37,
          (unsigned __int8)L"onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
          L"TryGetTickets",
          v38);
      }
      if ( StorePrimaryAccountTicketForUser >= 0 )
      {
        StorePrimaryAccountTicketForUser = (*(__int64 (__fastcall **)(HSTRING, char **))(*(_QWORD *)v39 + 56LL))(
                                             v39,
                                             &v42);
        if ( StorePrimaryAccountTicketForUser >= 0 )
        {
          if ( (_DWORD)v42 )
          {
            v13 = v39;
            v39 = 0;
            *a4 = v13;
            v14 = *(_QWORD *)v41;
            if ( *(_QWORD *)v41 )
            {
              v40 = 0;
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
              if ( (int)Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<IInspectable,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>>(
                          v15,
                          &v40) >= 0 )
              {
                (*(void (__fastcall **)(HSTRING, __int64))(*(_QWORD *)v40 + 104LL))(v40, v14);
                (*(void (__fastcall **)(HSTRING, _QWORD *))(*(_QWORD *)v40 + 64LL))(v40, a5);
              }
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
            }
          }
          else
          {
            StorePrimaryAccountTicketForUser = -2147023579;
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::GetImpl'::`2'::impl) )
              LogSimpleMessage(
                2u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                0x473u,
                "TryGetTickets",
                -2147023579,
                L"No tickets found for the explicitly-specified account.",
                0,
                0);
          }
        }
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v41);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::GetImpl'::`2'::impl)
      && StorePrimaryAccountTicketForUser < 0 )
    {
      LogSimpleMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
        0x47Du,
        "TryGetTickets",
        StorePrimaryAccountTicketForUser,
        L"No tickets found for the explicitly-specified account.",
        0,
        0);
    }
    WindowsDeleteString(string);
    WindowsDeleteString(v45);
    WindowsDeleteString(v44);
LABEL_46:
    if ( StorePrimaryAccountTicketForUser >= 0 )
      goto LABEL_57;
    goto LABEL_47;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)v41 = 0;
    LODWORD(v40) = 0;
    v39 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SetTicketVariables>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SetTicketVariables>::GetImpl'::`2'::impl) )
    {
      WindowsDeleteString(0);
      v39 = 0;
      StorePrimaryAccountTicketForUser = GetStorePrimaryAccountTicketForUser(v16, &v39, &v40, v41);
      v17 = v39;
      if ( StorePrimaryAccountTicketForUser >= 0 && !v39 )
        StorePrimaryAccountTicketForUser = -2147023579;
    }
    else
    {
      WindowsDeleteString(0);
      v39 = 0;
      v19 = GetStorePrimaryAccountTicketForUser(v18, &v39, &v40, v41);
      v20 = TraceHR(
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
              0x49Au,
              "TryGetTickets",
              "WinStoreAuth::GetStorePrimaryAccountTicket( authTicket.GetAddressOf(), &providerType, spWebTokenRequestRes"
              "ult.GetAddressOf())",
              v19,
              v36);
      StorePrimaryAccountTicketForUser = -2147023579;
      v17 = v39;
      if ( v39 )
        StorePrimaryAccountTicketForUser = v20;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SetTicketVariables>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SetTicketVariables>::GetImpl'::`2'::impl) )
    {
      if ( StorePrimaryAccountTicketForUser >= 0 )
      {
        v40 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
        StorePrimaryAccountTicketForUser = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<IInspectable,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>>(
                                             v21,
                                             &v40);
        if ( StorePrimaryAccountTicketForUser >= 0 )
        {
          StorePrimaryAccountTicketForUser = (*(__int64 (__fastcall **)(HSTRING, _QWORD))(*(_QWORD *)v40 + 104LL))(
                                               v40,
                                               *(_QWORD *)v41);
          if ( StorePrimaryAccountTicketForUser >= 0 )
            StorePrimaryAccountTicketForUser = (*(__int64 (__fastcall **)(HSTRING, _QWORD *))(*(_QWORD *)v40 + 64LL))(
                                                 v40,
                                                 a5);
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
        if ( StorePrimaryAccountTicketForUser >= 0 )
        {
          string = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
          StorePrimaryAccountTicketForUser = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
                                               v22,
                                               &string);
          if ( StorePrimaryAccountTicketForUser >= 0 )
          {
            StorePrimaryAccountTicketForUser = (*(__int64 (__fastcall **)(HSTRING, HSTRING))(*(_QWORD *)string + 104LL))(
                                                 string,
                                                 v17);
            if ( StorePrimaryAccountTicketForUser >= 0 )
            {
              v40 = 0;
              v23 = string;
              v24 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 64LL);
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
              StorePrimaryAccountTicketForUser = v24(v23, &v40);
              if ( StorePrimaryAccountTicketForUser >= 0 )
              {
                v25 = v40;
                v40 = 0;
                *a4 = v25;
                LODWORD(v42) = 1;
              }
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
              v6 = (TraceLoggingCorrelationVector *)v44;
            }
          }
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
          if ( StorePrimaryAccountTicketForUser >= 0 )
            goto LABEL_45;
        }
      }
      v26 = 1221;
    }
    else
    {
      if ( StorePrimaryAccountTicketForUser >= 0 )
      {
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
        if ( (int)Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<IInspectable,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>>(
                    v27,
                    &string) >= 0 )
        {
          (*(void (__fastcall **)(HSTRING, _QWORD))(*(_QWORD *)string + 104LL))(string, *(_QWORD *)v41);
          (*(void (__fastcall **)(HSTRING, _QWORD *))(*(_QWORD *)string + 64LL))(string, a5);
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
        goto LABEL_45;
      }
      v26 = 1237;
    }
    LogSimpleMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
      v26,
      "TryGetTickets",
      StorePrimaryAccountTicketForUser,
      L"No tickets found for the store primary acount.",
      0,
      0);
LABEL_45:
    WindowsDeleteString(v17);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v41);
    goto LABEL_46;
  }
LABEL_47:
  v39 = 0;
  *(_QWORD *)v41 = 0;
  v28 = GetTickCount64();
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
  StorePrimaryAccountTicketForUser = GatherAllStoreTickets(v8 + 1);
  if ( GetTickCount64() - v28 > 0xFA0 )
  {
    LODWORD(v35) = 0;
    WindowsUpdate::CommonTelemetry::TraceError(
      (WindowsUpdate::CommonTelemetry *)L"SlowResponseFromTokenBroker",
      L"Slow Response From WinStoreAuth::GatherAllStoreTickets",
      (const unsigned __int16 *)2,
      (int)L"SlowResponse",
      (const unsigned __int16 *)v35,
      1259,
      v37,
      (unsigned __int8)L"onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
      L"TryGetTickets",
      v38);
  }
  if ( StorePrimaryAccountTicketForUser >= 0 )
  {
    v29 = (*(__int64 (__fastcall **)(HSTRING, char **))(*(_QWORD *)v39 + 56LL))(v39, &v42);
    StorePrimaryAccountTicketForUser = TraceHR(
                                         "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                                         0x4F2u,
                                         "TryGetTickets",
                                         "tickets->get_Size(&ticketCount)",
                                         v29,
                                         v36);
    if ( StorePrimaryAccountTicketForUser >= 0 )
    {
      if ( (_DWORD)v42 )
      {
        v30 = v39;
        v39 = 0;
        *a4 = v30;
        v31 = *(_QWORD *)v41;
        *(_QWORD *)v41 = 0;
        *a5 = v31;
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::GetImpl'::`2'::impl) )
      {
        StorePrimaryAccountTicketForUser = -2147023579;
      }
      else
      {
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
          0x503u,
          "TryGetTickets",
          -1,
          L"No tickets found for the current user.",
          0,
          0);
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::GetImpl'::`2'::impl)
    && StorePrimaryAccountTicketForUser < 0 )
  {
    LogSimpleMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
      0x50Cu,
      "TryGetTickets",
      StorePrimaryAccountTicketForUser,
      L"No tickets found for the current user.",
      0,
      0);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v41);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
LABEL_57:
  if ( !(_DWORD)v42 && !(_BYTE)v8 )
  {
    WindowsDeleteString(0);
    v44 = 0;
    LOBYTE(v32) = 1;
    StorePrimaryAccountTicketForUser = GetDeviceTicketWithBroker(v32, &v44);
    if ( StorePrimaryAccountTicketForUser >= 0 )
    {
      *(_QWORD *)v41 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v41);
      StorePrimaryAccountTicketForUser = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
                                           v33,
                                           v41);
      if ( StorePrimaryAccountTicketForUser >= 0 )
      {
        StorePrimaryAccountTicketForUser = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)v41 + 104LL))(
                                             *(_QWORD *)v41,
                                             v44);
        if ( StorePrimaryAccountTicketForUser >= 0 )
        {
          LODWORD(v42) = 1;
          StorePrimaryAccountTicketForUser = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)v41 + 64LL))(
                                               *(_QWORD *)v41,
                                               a4);
        }
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v41);
    }
    LogSimpleMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
      0x525u,
      "TryGetTickets",
      StorePrimaryAccountTicketForUser,
      L"Cannot get any user tickets. Using device ticket",
      0,
      0);
    WindowsDeleteString(v44);
  }
  if ( StorePrimaryAccountTicketForUser < 0 )
    LogSimpleMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
      0x52Cu,
      "TryGetTickets",
      StorePrimaryAccountTicketForUser,
      L"Error attempting to fetch tickets. catalog access will be anonymous",
      0,
      0);
  TraceLoggingCorrelationVector::Increment(v6, v46);
  WindowsUpdate::CommonTelemetry::CompleteGetAuthTickets(
    (WindowsUpdate::CommonTelemetry *)v46,
    (const char *)(unsigned int)v42,
    StorePrimaryAccountTicketForUser,
    v34);
}

```

## disassembly

```asm
0x1800843f0  push    rbp
0x1800843f2  push    rbx
0x1800843f3  push    rsi
0x1800843f4  push    rdi
0x1800843f5  push    r12
0x1800843f7  push    r13
0x1800843f9  push    r15
0x1800843fb  lea     rbp, [rsp-30h]
0x180084400  sub     rsp, 130h
0x180084407  mov     rax, cs:__security_cookie
0x18008440e  xor     rax, rsp
0x180084411  mov     [rbp+60h+var_40], rax
0x180084415  mov     r12, r9
0x180084418  mov     rsi, r8
0x18008441b  mov     [rsp+160h+var_E8], r8
0x180084420  mov     rbx, rdx
0x180084423  movzx   r13d, cl
0x180084427  mov     r15, [rbp+60h+arg_20]
0x18008442e  xor     edi, edi
0x180084430  mov     [r15], rdi
0x180084433  mov     dword ptr [rsp+160h+var_F8], edi
0x180084437  test    rdx, rdx
0x18008443a  jz      loc_1800846CE
0x180084440  xor     ecx, ecx; string
0x180084442  call    cs:__imp_WindowsDeleteString
0x180084448  mov     [rsp+160h+string], rdi
0x18008444d  xor     ecx, ecx; string
0x18008444f  call    cs:__imp_WindowsDeleteString
0x180084455  mov     [rbp+60h+var_E0], rdi
0x180084459  xor     ecx, ecx; string
0x18008445b  call    cs:__imp_WindowsDeleteString
0x180084461  mov     [rsp+160h+var_E8], rdi
0x180084466  mov     [rsp+160h+var_140], rdi; struct _GUID *
0x18008446b  lea     r9, [rsp+160h+string]; HSTRING *
0x180084470  lea     r8, [rbp+60h+var_E0]; HSTRING *
0x180084474  lea     rdx, [rsp+160h+var_E8]; HSTRING *
0x180084479  mov     rcx, rbx; HSTRING
0x18008447c  call    ?ParseIdentityData@@YAJPEAUHSTRING__@@PEAPEAU1@11PEAU_GUID@@@Z; ParseIdentityData(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,_GUID *)
0x180084481  mov     edi, eax
0x180084483  xor     ebx, ebx
0x180084485  test    eax, eax
0x180084487  js      loc_1800845FC
0x18008448d  mov     [rsp+160h+var_110], rbx
0x180084492  mov     qword ptr [rsp+160h+var_100], rbx
0x180084497  call    cs:__imp_GetTickCount64
0x18008449d  mov     rbx, rax
0x1800844a0  lea     rcx, [rsp+160h+var_110]
0x1800844a5  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800844aa  lea     rax, [rsp+160h+var_100]
0x1800844af  mov     [rsp+160h+var_138], rax; int
0x1800844b4  lea     rax, [rsp+160h+var_110]
0x1800844b9  mov     [rsp+160h+var_140], rax
0x1800844be  mov     r9, [rsp+160h+string]
0x1800844c3  mov     r8, [rbp+60h+var_E0]
0x1800844c7  mov     rdx, [rsp+160h+var_E8]
0x1800844cc  call    GetTicketsForAccountForUser
0x1800844d1  mov     dword ptr [rsp+160h+var_140], eax; int
0x1800844d5  lea     r9, aWinstoreauthGe_2; "WinStoreAuth::GetTicketsForAccount(acco"...
0x1800844dc  lea     r8, aTrygettickets; "TryGetTickets"
0x1800844e3  mov     edx, 448h; unsigned int
0x1800844e8  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800844ef  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800844f4  mov     edi, eax
0x1800844f6  call    cs:__imp_GetTickCount64
0x1800844fc  sub     rax, rbx
0x1800844ff  xor     ebx, ebx
0x180084501  cmp     rax, 0FA0h
0x180084507  jbe     short loc_18008454B
0x180084509  lea     rax, aTrygettickets_0; "TryGetTickets"
0x180084510  mov     [rsp+160h+var_120], rax; unsigned __int16 *
0x180084515  lea     rax, aOnecoreuapEndu_67; "onecoreuap\\enduser\\winstore\\installs"...
0x18008451c  mov     [rsp+160h+var_128], rax; unsigned __int8
0x180084521  mov     dword ptr [rsp+160h+var_138], 451h; int
0x180084529  mov     dword ptr [rsp+160h+var_140], ebx; unsigned __int16 *
0x18008452d  lea     r9, aSlowresponse; "SlowResponse"
0x180084534  lea     r8d, [rbx+2]; unsigned __int16 *
0x180084538  lea     rdx, aSlowResponseFr; "Slow Response From WinStoreAuth::GetTic"...
0x18008453f  lea     rcx, aSlowresponsefr; "SlowResponseFromTokenBroker"
0x180084546  call    ?TraceError@CommonTelemetry@WindowsUpdate@@YAXPEBG0H0HIE00@Z; WindowsUpdate::CommonTelemetry::TraceError(ushort const *,ushort const *,int,ushort const *,int,uint,uchar,ushort const *,ushort const *)
0x18008454b  test    edi, edi
0x18008454d  js      loc_1800845E7
0x180084553  mov     rcx, [rsp+160h+var_110]
0x180084558  mov     rax, [rcx]
0x18008455b  lea     rdx, [rsp+160h+var_F8]
0x180084560  mov     rax, [rax+38h]
0x180084564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084569  mov     edi, eax
0x18008456b  test    eax, eax
0x18008456d  js      short loc_1800845E7
0x18008456f  cmp     dword ptr [rsp+160h+var_F8], ebx
0x180084573  jz      loc_180084670
0x180084579  mov     rax, [rsp+160h+var_110]
0x18008457e  mov     [rsp+160h+var_110], rbx
0x180084583  mov     [r12], rax
0x180084587  mov     rbx, qword ptr [rsp+160h+var_100]
0x18008458c  test    rbx, rbx
0x18008458f  jz      short loc_1800845E5
0x180084591  mov     [rsp+160h+var_108], 0
0x18008459a  lea     rcx, [rsp+160h+var_108]
0x18008459f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800845a4  lea     rdx, [rsp+160h+var_108]
0x1800845a9  call    ??$CreateExternalObjectVector@UIInspectable@@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<IInspectable,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>> * *)
0x1800845ae  test    eax, eax
0x1800845b0  js      short loc_1800845DB
0x1800845b2  mov     rcx, [rsp+160h+var_108]
0x1800845b7  mov     rax, [rcx]
0x1800845ba  mov     rdx, rbx
0x1800845bd  mov     rax, [rax+68h]
0x1800845c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845c6  mov     rcx, [rsp+160h+var_108]
0x1800845cb  mov     rax, [rcx]
0x1800845ce  mov     rdx, r15
0x1800845d1  mov     rax, [rax+40h]
0x1800845d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845da  nop
0x1800845db  lea     rcx, [rsp+160h+var_108]
0x1800845e0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800845e5  xor     ebx, ebx
0x1800845e7  lea     rcx, [rsp+160h+var_100]
0x1800845ec  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800845f1  nop
0x1800845f2  lea     rcx, [rsp+160h+var_110]
0x1800845f7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800845fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity> `wil::Feature<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::GetImpl(void)'::`2'::impl
0x180084603  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::__private_IsEnabled(void)
0x180084608  test    al, al
0x18008460a  jz      short loc_180084649
0x18008460c  test    edi, edi
0x18008460e  jns     short loc_180084649
0x180084610  mov     [rsp+160h+var_128], rbx; unsigned __int16 *
0x180084615  mov     [rsp+160h+var_130], rbx; char *
0x18008461a  lea     rax, aNoTicketsFound; "No tickets found for the explicitly-spe"...
0x180084621  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x180084626  mov     dword ptr [rsp+160h+var_140], edi; int
0x18008462a  lea     r9, aTrygettickets; "TryGetTickets"
0x180084631  mov     r8d, 47Dh; unsigned int
0x180084637  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x18008463e  mov     ecx, 2; unsigned int
0x180084643  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180084648  nop
0x180084649  mov     rcx, [rsp+160h+string]; string
0x18008464e  call    cs:__imp_WindowsDeleteString
0x180084654  nop
0x180084655  mov     rcx, [rbp+60h+var_E0]; string
0x180084659  call    cs:__imp_WindowsDeleteString
0x18008465f  nop
0x180084660  mov     rcx, [rsp+160h+var_E8]; string
0x180084665  call    cs:__imp_WindowsDeleteString
0x18008466b  jmp     loc_180084969
0x180084670  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity> `wil::Feature<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::GetImpl(void)'::`2'::impl
0x180084677  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::__private_IsEnabled(void)
0x18008467c  test    al, al
0x18008467e  jz      short loc_18008468A
0x180084680  mov     edi, 80070525h
0x180084685  jmp     loc_1800845E7
0x18008468a  mov     ecx, 80070525h
0x18008468f  mov     edi, ecx
0x180084691  mov     [rsp+160h+var_128], rbx; unsigned __int16 *
0x180084696  mov     [rsp+160h+var_130], rbx; char *
0x18008469b  lea     rax, aNoTicketsFound; "No tickets found for the explicitly-spe"...
0x1800846a2  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x1800846a7  mov     dword ptr [rsp+160h+var_140], ecx; int
0x1800846ab  lea     r9, aTrygettickets; "TryGetTickets"
0x1800846b2  mov     r8d, 473h; unsigned int
0x1800846b8  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800846bf  mov     ecx, 2; unsigned int
0x1800846c4  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800846c9  jmp     loc_1800845E7
0x1800846ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity> `wil::Feature<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::GetImpl(void)'::`2'::impl
0x1800846d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HonorMSAWhenNoIdentity>::__private_IsEnabled(void)
0x1800846da  xor     ebx, ebx
0x1800846dc  test    al, al
0x1800846de  jz      loc_180084971
0x1800846e4  mov     qword ptr [rsp+160h+var_100], rbx
0x1800846e9  mov     dword ptr [rsp+160h+var_108], ebx
0x1800846ed  mov     [rsp+160h+var_110], rbx
0x1800846f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SetTicketVariables@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SetTicketVariables@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SetTicketVariables> `wil::Feature<__WilFeatureTraits_Feature_SetTicketVariables>::GetImpl(void)'::`2'::impl
0x1800846f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SetTicketVariables@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SetTicketVariables>::__private_IsEnabled(void)
0x1800846fe  xor     ecx, ecx; string
0x180084700  test    al, al
0x180084702  jz      short loc_18008473A
0x180084704  call    cs:__imp_WindowsDeleteString
0x18008470a  mov     [rsp+160h+var_110], rbx
0x18008470f  lea     r9, [rsp+160h+var_100]
0x180084714  lea     r8, [rsp+160h+var_108]
0x180084719  lea     rdx, [rsp+160h+var_110]
0x18008471e  call    GetStorePrimaryAccountTicketForUser
0x180084723  mov     edi, eax
0x180084725  mov     rbx, [rsp+160h+var_110]
0x18008472a  test    eax, eax
0x18008472c  js      short loc_18008478C
0x18008472e  test    rbx, rbx
0x180084731  jnz     short loc_18008478C
0x180084733  mov     edi, 80070525h
0x180084738  jmp     short loc_18008478C
0x18008473a  call    cs:__imp_WindowsDeleteString
0x180084740  mov     [rsp+160h+var_110], rbx
0x180084745  lea     r9, [rsp+160h+var_100]
0x18008474a  lea     r8, [rsp+160h+var_108]
0x18008474f  lea     rdx, [rsp+160h+var_110]
0x180084754  call    GetStorePrimaryAccountTicketForUser
0x180084759  mov     dword ptr [rsp+160h+var_140], eax; int
0x18008475d  lea     r9, aWinstoreauthGe_0; "WinStoreAuth::GetStorePrimaryAccountTic"...
0x180084764  lea     r8, aTrygettickets; "TryGetTickets"
0x18008476b  mov     edx, 49Ah; unsigned int
0x180084770  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x180084777  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18008477c  mov     edi, 80070525h
0x180084781  mov     rbx, [rsp+160h+var_110]
0x180084786  test    rbx, rbx
0x180084789  cmovnz  edi, eax
0x18008478c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SetTicketVariables@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SetTicketVariables@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SetTicketVariables> `wil::Feature<__WilFeatureTraits_Feature_SetTicketVariables>::GetImpl(void)'::`2'::impl
0x180084793  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SetTicketVariables@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SetTicketVariables>::__private_IsEnabled(void)
0x180084798  xor     ecx, ecx
0x18008479a  test    al, al
0x18008479c  jz      loc_1800848C2
0x1800847a2  test    edi, edi
0x1800847a4  js      loc_1800848BA
0x1800847aa  mov     [rsp+160h+var_108], rcx
0x1800847af  lea     rcx, [rsp+160h+var_108]
0x1800847b4  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800847b9  lea     rdx, [rsp+160h+var_108]
0x1800847be  call    ??$CreateExternalObjectVector@UIInspectable@@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<IInspectable,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>> * *)
0x1800847c3  mov     edi, eax
0x1800847c5  test    eax, eax
0x1800847c7  js      short loc_1800847FB
0x1800847c9  mov     rcx, [rsp+160h+var_108]
0x1800847ce  mov     rax, [rcx]
0x1800847d1  mov     rdx, qword ptr [rsp+160h+var_100]
0x1800847d6  mov     rax, [rax+68h]
0x1800847da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800847df  mov     edi, eax
0x1800847e1  test    eax, eax
0x1800847e3  js      short loc_1800847FB
0x1800847e5  mov     rcx, [rsp+160h+var_108]
0x1800847ea  mov     rax, [rcx]
0x1800847ed  mov     rdx, r15
0x1800847f0  mov     rax, [rax+40h]
0x1800847f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800847f9  mov     edi, eax
0x1800847fb  lea     rcx, [rsp+160h+var_108]
0x180084800  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180084805  xor     ecx, ecx
0x180084807  test    edi, edi
0x180084809  js      loc_1800848BA
0x18008480f  mov     [rsp+160h+string], rcx
0x180084814  lea     rcx, [rsp+160h+string]
0x180084819  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18008481e  lea     rdx, [rsp+160h+string]
0x180084823  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x180084828  mov     edi, eax
0x18008482a  test    eax, eax
0x18008482c  js      short loc_1800848A6
0x18008482e  mov     rcx, [rsp+160h+string]
0x180084833  mov     rax, [rcx]
0x180084836  mov     rdx, rbx
0x180084839  mov     rax, [rax+68h]
0x18008483d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084842  mov     edi, eax
0x180084844  test    eax, eax
0x180084846  js      short loc_1800848A6
0x180084848  mov     [rsp+160h+var_108], 0
0x180084851  mov     rsi, [rsp+160h+string]
0x180084856  mov     rax, [rsi]
0x180084859  mov     rdi, [rax+40h]
0x18008485d  lea     rcx, [rsp+160h+var_108]
0x180084862  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180084867  lea     rdx, [rsp+160h+var_108]
0x18008486c  mov     rcx, rsi
0x18008486f  mov     rax, rdi
0x180084872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084877  mov     edi, eax
0x180084879  test    eax, eax
0x18008487b  js      short loc_180084897
0x18008487d  mov     rax, [rsp+160h+var_108]
0x180084882  mov     [rsp+160h+var_108], 0
0x18008488b  mov     [r12], rax
0x18008488f  mov     dword ptr [rsp+160h+var_F8], 1
0x180084897  lea     rcx, [rsp+160h+var_108]
0x18008489c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800848a1  mov     rsi, [rsp+160h+var_E8]
0x1800848a6  lea     rcx, [rsp+160h+string]
0x1800848ab  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800848b0  xor     ecx, ecx
0x1800848b2  test    edi, edi
0x1800848b4  jns     loc_180084953
0x1800848ba  mov     r8d, 4C5h
0x1800848c0  jmp     short loc_180084920
0x1800848c2  test    edi, edi
0x1800848c4  js      short loc_18008491A
0x1800848c6  mov     [rsp+160h+string], rcx
0x1800848cb  lea     rcx, [rsp+160h+string]
0x1800848d0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800848d5  lea     rdx, [rsp+160h+string]
0x1800848da  call    ??$CreateExternalObjectVector@UIInspectable@@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<IInspectable,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>> * *)
0x1800848df  test    eax, eax
0x1800848e1  js      short loc_18008490E
0x1800848e3  mov     rcx, [rsp+160h+string]
0x1800848e8  mov     rax, [rcx]
0x1800848eb  mov     rdx, qword ptr [rsp+160h+var_100]
  ... truncated ...
```
