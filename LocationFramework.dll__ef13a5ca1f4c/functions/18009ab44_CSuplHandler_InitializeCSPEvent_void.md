# CSuplHandler::InitializeCSPEvent(void)

- ea: `0x18009ab44`
- end: `0x18009b1a4`
- name: `?InitializeCSPEvent@CSuplHandler@@QEAAJXZ`
- size: `1632`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e179c`

## callees

- `0x180012310`
- `0x180012398`
- `0x18005e900`
- `0x18009ab44`
- `0x18009c344`
- `0x1800a4f44`
- `0x1800a98c0`
- `0x1800e06e0`
- `0x1800e07b0`
- `0x1800e0854`
- `0x1800e08f8`
- `0x1800e2630`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18009b0a0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18009b0a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009affe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009affe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009aba9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009aba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b01f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b01f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b0b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009ab8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009ab8d`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18009b00f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18009b00f`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18009af6a`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18009af6a`

## string_xrefs

- `0x18009af63`: `SuplCspUpdatedEvent3`
- `0x18009afee`: `SuplCspUpdatedEvent3`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CSuplHandler::InitializeCSPEvent(_QWORD *pv)
{
  _QWORD *v2; // r12
  HSTRING v3; // rbx
  __int64 result; // rax
  int v5; // ebx
  __int64 *v6; // rax
  __int64 v7; // rsi
  __int64 *v8; // rax
  __int64 v9; // r14
  __int64 *v10; // rax
  __int64 v11; // rbx
  __int64 *v12; // rax
  __int64 v13; // rdi
  int v14; // r13d
  int v15; // r12d
  int TransientObjectSecurityDescriptor; // eax
  signed int v17; // eax
  unsigned int v18; // r15d
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  _QWORD v21[5]; // [rsp+20h] [rbp-69h] BYREF
  struct IWeakReferenceSource *v22; // [rsp+48h] [rbp-41h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+50h] [rbp-39h] BYREF
  struct IWeakReferenceSource *v24; // [rsp+68h] [rbp-21h] BYREF
  HSTRING hstringHeader[4]; // [rsp+70h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  memset(hstringHeader, 0, sizeof(hstringHeader));
  if ( WindowsCreateStringReference(
         L"Windows.Networking.NetworkOperators.MobileBroadbandAccountWatcher",
         0x41u,
         (HSTRING_HEADER *)&hstringHeader[1],
         hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = pv + 96;
  v3 = hstringHeader[0];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(pv + 96);
  result = Windows::Foundation::ActivateInstance<Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher>(
             v3,
             pv + 96);
  if ( (int)result >= 0 )
  {
    v24 = 0;
    v22 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IWeakReferenceSource **))*pv)(
           pv,
           &GUID_00000038_0000_0000_c000_000000000046,
           &v22);
    if ( v5 >= 0 )
    {
      v5 = CComWeakRef::From((CComWeakRef *)&v24, v22);
      if ( v5 >= 0 )
        v5 = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    if ( v5 < 0 )
      goto LABEL_107;
    v21[0] = v24;
    if ( v24 )
      ((void (__fastcall *)(struct IWeakReferenceSource *))v24->lpVtbl->AddRef)(v24);
    v6 = (__int64 *)___Make_U__DelegateInvokeHelper_U__ITypedEventHandler_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAVMobileBroadbandAccountEventArgs_234__Foundation_Windows__V_lambda_1___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__0_0PEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountEventArgs_893____DelegateArgTraits_P8__ITypedEventHandler_impl_U__AggregateType_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountWatcher_234__Internal_Foundation_Windows__U__AggregateType_PEAVMobileBroadbandAccountEventArgs_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountEventArgs_234__234__Foundation_Windows__EAAJPEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountEventArgs_563__Z_Details_WRL_Microsoft__V_lambda_1___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__Details_WRL_Microsoft__YA_AV__ComPtr_U__DelegateInvokeHelper_U__ITypedEventHandler_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAVMobileBroadbandAccountEventArgs_234__Foundation_Windows__V_lambda_1___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__0_0PEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountEventArgs_893____DelegateArgTraits_P8__ITypedEventHandler_impl_U__AggregateType_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountWatcher_234__Internal_Foundation_Windows__U__AggregateType_PEAVMobileBroadbandAccountEventArgs_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountEventArgs_234__234__Foundation_Windows__EAAJPEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountEventArgs_563__Z_Details_WRL_Microsoft___12___QEAV_lambda_1___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__Z(
                      &v22,
                      v21);
    v7 = *v6;
    v21[1] = *v6;
    *v6 = 0;
    if ( v22 )
    {
      v22 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>>::Release();
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v21);
    v22 = v24;
    if ( v24 )
      ((void (__fastcall *)(struct IWeakReferenceSource *))v24->lpVtbl->AddRef)(v24);
    v8 = (__int64 *)___Make_U__DelegateInvokeHelper_U__ITypedEventHandler_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAVMobileBroadbandAccountUpdatedEventArgs_234__Foundation_Windows__V_lambda_2___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__0_0PEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountUpdatedEventArgs_893____DelegateArgTraits_P8__ITypedEventHandler_impl_U__AggregateType_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountWatcher_234__Internal_Foundation_Windows__U__AggregateType_PEAVMobileBroadbandAccountUpdatedEventArgs_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountUpdatedEventArgs_234__234__Foundation_Windows__EAAJPEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountUpdatedEventArgs_563__Z_Details_WRL_Microsoft__V_lambda_2___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__Details_WRL_Microsoft__YA_AV__ComPtr_U__DelegateInvokeHelper_U__ITypedEventHandler_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAVMobileBroadbandAccountUpdatedEventArgs_234__Foundation_Windows__V_lambda_2___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__0_0PEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountUpdatedEventArgs_893____DelegateArgTraits_P8__ITypedEventHandler_impl_U__AggregateType_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountWatcher_234__Internal_Foundation_Windows__U__AggregateType_PEAVMobileBroadbandAccountUpdatedEventArgs_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountUpdatedEventArgs_234__234__Foundation_Windows__EAAJPEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountUpdatedEventArgs_563__Z_Details_WRL_Microsoft___12___QEAV_lambda_2___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__Z(
                      v21,
                      &v22);
    v9 = *v8;
    v21[2] = *v8;
    *v8 = 0;
    if ( v21[0] )
    {
      v21[0] = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>>::Release();
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    v22 = v24;
    if ( v24 )
      ((void (__fastcall *)(struct IWeakReferenceSource *))v24->lpVtbl->AddRef)(v24);
    v10 = (__int64 *)___Make_U__DelegateInvokeHelper_U__ITypedEventHandler_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAVMobileBroadbandAccountEventArgs_234__Foundation_Windows__V_lambda_3___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__0_0PEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountEventArgs_893____DelegateArgTraits_P8__ITypedEventHandler_impl_U__AggregateType_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountWatcher_234__Internal_Foundation_Windows__U__AggregateType_PEAVMobileBroadbandAccountEventArgs_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountEventArgs_234__234__Foundation_Windows__EAAJPEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountEventArgs_563__Z_Details_WRL_Microsoft__V_lambda_3___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__Details_WRL_Microsoft__YA_AV__ComPtr_U__DelegateInvokeHelper_U__ITypedEventHandler_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAVMobileBroadbandAccountEventArgs_234__Foundation_Windows__V_lambda_3___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__0_0PEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountEventArgs_893____DelegateArgTraits_P8__ITypedEventHandler_impl_U__AggregateType_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountWatcher_234__Internal_Foundation_Windows__U__AggregateType_PEAVMobileBroadbandAccountEventArgs_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountEventArgs_234__234__Foundation_Windows__EAAJPEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIMobileBroadbandAccountEventArgs_563__Z_Details_WRL_Microsoft___12___QEAV_lambda_3___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__Z(
                       v21,
                       &v22);
    v11 = *v10;
    v21[3] = *v10;
    *v10 = 0;
    if ( v21[0] )
    {
      v21[0] = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>>::Release();
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    v22 = v24;
    if ( v24 )
      ((void (__fastcall *)(struct IWeakReferenceSource *))v24->lpVtbl->AddRef)(v24);
    v12 = (__int64 *)___Make_U__DelegateInvokeHelper_U__ITypedEventHandler_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIInspectable___Foundation_Windows__V_lambda_4___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__0_0PEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIInspectable_____DelegateArgTraits_P8__ITypedEventHandler_impl_U__AggregateType_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountWatcher_234__Internal_Foundation_Windows__PEAUIInspectable___Foundation_Windows__EAAJPEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIInspectable___Z_Details_WRL_Microsoft__V_lambda_4___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__Details_WRL_Microsoft__YA_AV__ComPtr_U__DelegateInvokeHelper_U__ITypedEventHandler_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIInspectable___Foundation_Windows__V_lambda_4___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__0_0PEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIInspectable_____DelegateArgTraits_P8__ITypedEventHandler_impl_U__AggregateType_PEAVMobileBroadbandAccountWatcher_NetworkOperators_Networking_Windows__PEAUIMobileBroadbandAccountWatcher_234__Internal_Foundation_Windows__PEAUIInspectable___Foundation_Windows__EAAJPEAUIMobileBroadbandAccountWatcher_NetworkOperators_Networking_3_PEAUIInspectable___Z_Details_WRL_Microsoft___12___QEAV_lambda_4___1__InitializeCSPEvent_CSuplHandler__QEAAJXZ__Z(
                       v21,
                       &v22);
    v13 = *v12;
    v21[4] = *v12;
    *v12 = 0;
    if ( v21[0] )
    {
      v21[0] = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>>::Release();
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v2 + 48LL))(*v2, v7, (char *)pv + 776);
    if ( v14 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v2 + 64LL))(*v2, v9, (char *)pv + 784);
      if ( v14 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v2 + 80LL))(*v2, v11, (char *)pv + 792);
        if ( v14 >= 0 )
        {
          v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v2 + 112LL))(
                  *v2,
                  v13,
                  (char *)pv + 800);
          if ( v15 >= 0 )
          {
            *(_OWORD *)&EventAttributes.nLength = 0;
            *(&EventAttributes.bInheritHandle + 1) = 0;
            EventAttributes.nLength = 24;
            EventAttributes.bInheritHandle = 1;
            TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(
                                                  1,
                                                  L"SuplCspUpdatedEvent3",
                                                  &EventAttributes.lpSecurityDescriptor);
            v15 = TransientObjectSecurityDescriptor | 0x10000000;
            if ( TransientObjectSecurityDescriptor >= 0 )
            {
              pv[17] = CreateEventW(&EventAttributes, 0, 0, L"SuplCspUpdatedEvent3");
              FreeTransientObjectSecurityDescriptor(EventAttributes.lpSecurityDescriptor);
              if ( pv[17] )
              {
                ThreadpoolWait = CreateThreadpoolWait(CSuplHandler::OnCspUpdated_Static, pv, 0);
                pv[18] = ThreadpoolWait;
                if ( ThreadpoolWait )
                {
                  if ( v13 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                  if ( v11 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                  if ( v9 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                  if ( v7 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
                  v5 = 0;
                  goto LABEL_107;
                }
                LastError = GetLastError();
                v18 = LastError;
                if ( LastError > 0 )
                  v18 = (unsigned __int16)LastError | 0x80070000;
                if ( v13 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                if ( v11 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                if ( v9 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                if ( v7 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
              }
              else
              {
                v17 = GetLastError();
                v18 = v17;
                if ( v17 > 0 )
                  v18 = (unsigned __int16)v17 | 0x80070000;
                if ( v13 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                if ( v11 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                if ( v9 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                if ( v7 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
              }
              v5 = v18;
LABEL_107:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
              return (unsigned int)v5;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x624,
              (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\suplhandler.cpp",
              (const char *)(unsigned int)v15,
              v21[0]);
            if ( v13 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            if ( v11 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            if ( v9 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            if ( v7 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          }
          else
          {
            if ( v13 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            if ( v11 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            if ( v9 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            if ( v7 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          }
          v5 = v15;
          goto LABEL_107;
        }
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      else
      {
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    else
    {
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v5 = v14;
    goto LABEL_107;
  }
  return result;
}

```

## disassembly

```asm
0x18009ab44  push    rbp
0x18009ab46  push    rbx
0x18009ab47  push    rsi
0x18009ab48  push    rdi
0x18009ab49  push    r12
0x18009ab4b  push    r13
0x18009ab4d  push    r14
0x18009ab4f  push    r15
0x18009ab51  lea     rbp, [rsp-1Fh]
0x18009ab56  sub     rsp, 0A8h
0x18009ab5d  mov     rax, cs:__security_cookie
0x18009ab64  xor     rax, rsp
0x18009ab67  mov     [rbp+57h+var_50], rax
0x18009ab6b  mov     r15, rcx
0x18009ab6e  xorps   xmm0, xmm0
0x18009ab71  movups  xmmword ptr [rbp+57h+hstringHeader], xmm0
0x18009ab75  movups  xmmword ptr [rbp+57h+hstringHeader+10h], xmm0
0x18009ab79  lea     r9, [rbp+57h+hstringHeader]; string
0x18009ab7d  lea     r8, [rbp+57h+hstringHeader+8]; hstringHeader
0x18009ab81  mov     edx, 41h ; 'A'; length
0x18009ab86  lea     rcx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandAccountWatcher@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x18009ab8d  call    cs:__imp_WindowsCreateStringReference
0x18009ab93  xor     r13d, r13d
0x18009ab96  test    eax, eax
0x18009ab98  jns     short loc_18009ABAF
0x18009ab9a  xor     r9d, r9d; lpArguments
0x18009ab9d  xor     r8d, r8d; nNumberOfArguments
0x18009aba0  lea     edx, [r13+1]; dwExceptionFlags
0x18009aba4  mov     ecx, 0C000000Dh; dwExceptionCode
0x18009aba9  call    cs:__imp_RaiseException
0x18009abaf  lea     r12, [r15+300h]
0x18009abb6  mov     rbx, qword ptr [rbp+57h+hstringHeader]
0x18009abba  mov     rcx, r12
0x18009abbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009abc2  mov     rdx, r12
0x18009abc5  mov     rcx, rbx
0x18009abc8  call    ??$ActivateInstance@UIMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@1@@Z; Windows::Foundation::ActivateInstance<Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher>(HSTRING__ *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher * *)
0x18009abcd  nop
0x18009abce  test    eax, eax
0x18009abd0  js      loc_18009B184
0x18009abd6  mov     [rbp+57h+var_78], r13
0x18009abda  mov     [rbp+57h+var_98], r13
0x18009abde  mov     rax, [r15]
0x18009abe1  lea     r8, [rbp+57h+var_98]
0x18009abe5  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x18009abec  mov     rcx, r15
0x18009abef  mov     rax, [rax]
0x18009abf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009abf7  mov     ebx, eax
0x18009abf9  test    eax, eax
0x18009abfb  jns     short loc_18009ABFF
0x18009abfd  jmp     short loc_18009AC15
0x18009abff  mov     rdx, [rbp+57h+var_98]; struct IWeakReferenceSource *
0x18009ac03  lea     rcx, [rbp+57h+var_78]; this
0x18009ac07  call    ?From@CComWeakRef@@QEAAJPEAUIWeakReferenceSource@@@Z; CComWeakRef::From(IWeakReferenceSource *)
0x18009ac0c  mov     ebx, eax
0x18009ac0e  test    eax, eax
0x18009ac10  js      short loc_18009AC15
0x18009ac12  mov     ebx, r13d
0x18009ac15  lea     rcx, [rbp+57h+var_98]
0x18009ac19  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009ac1e  test    ebx, ebx
0x18009ac20  js      loc_18009B179
0x18009ac26  mov     rcx, [rbp+57h+var_78]
0x18009ac2a  mov     [rbp+57h+var_C0], rcx
0x18009ac2e  test    rcx, rcx
0x18009ac31  jz      short loc_18009AC40
0x18009ac33  mov     rax, [rcx]
0x18009ac36  mov     rax, [rax+8]
0x18009ac3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ac3f  nop
0x18009ac40  lea     rdx, [rbp+57h+var_C0]
0x18009ac44  lea     rcx, [rbp+57h+var_98]
0x18009ac48  call    ??$Make@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountEventArgs@234@@Foundation@Windows@@V_lambda_1_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@$0?0PEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountEventArgs@893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountWatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVMobileBroadbandAccountEventArgs@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountEventArgs@563@@Z@Details@WRL@Microsoft@@V_lambda_1_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountEventArgs@234@@Foundation@Windows@@V_lambda_1_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@$0?0PEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountEventArgs@893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountWatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVMobileBroadbandAccountEventArgs@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountEventArgs@563@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_1_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountEventArgs *>>::*)(Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>,`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_1_,-1,Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountEventArgs *>,`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_1_>(`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_1_ &&)
0x18009ac4d  mov     rsi, [rax]
0x18009ac50  mov     [rbp+57h+var_B8], rsi
0x18009ac54  mov     [rax], r13
0x18009ac57  mov     rcx, [rbp+57h+var_98]
0x18009ac5b  test    rcx, rcx
0x18009ac5e  jz      short loc_18009AC6A
0x18009ac60  mov     [rbp+57h+var_98], r13
0x18009ac64  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>>::Release(void)
0x18009ac69  nop
0x18009ac6a  lea     rcx, [rbp+57h+var_C0]
0x18009ac6e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009ac73  mov     rcx, [rbp+57h+var_78]
0x18009ac77  mov     [rbp+57h+var_98], rcx
0x18009ac7b  test    rcx, rcx
0x18009ac7e  jz      short loc_18009AC8D
0x18009ac80  mov     rax, [rcx]
0x18009ac83  mov     rax, [rax+8]
0x18009ac87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ac8c  nop
0x18009ac8d  lea     rdx, [rbp+57h+var_98]
0x18009ac91  lea     rcx, [rbp+57h+var_C0]
0x18009ac95  call    ??$Make@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountUpdatedEventArgs@234@@Foundation@Windows@@V_lambda_2_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@$0?0PEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountUpdatedEventArgs@893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountWatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVMobileBroadbandAccountUpdatedEventArgs@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountUpdatedEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountUpdatedEventArgs@563@@Z@Details@WRL@Microsoft@@V_lambda_2_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountUpdatedEventArgs@234@@Foundation@Windows@@V_lambda_2_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@$0?0PEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountUpdatedEventArgs@893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountWatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVMobileBroadbandAccountUpdatedEventArgs@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountUpdatedEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountUpdatedEventArgs@563@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_2_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::Networking::NetworkOperators::MobileBroadbandAccountUpdatedEventArgs *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountUpdatedEventArgs *>>::*)(Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountUpdatedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountUpdatedEventArgs *>,`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_2_,-1,Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountUpdatedEventArgs *>,`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_2_>(`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_2_ &&)
0x18009ac9a  mov     r14, [rax]
0x18009ac9d  mov     [rbp+57h+var_B0], r14
0x18009aca1  mov     [rax], r13
0x18009aca4  mov     rcx, [rbp+57h+var_C0]
0x18009aca8  test    rcx, rcx
0x18009acab  jz      short loc_18009ACB7
0x18009acad  mov     [rbp+57h+var_C0], r13
0x18009acb1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>>::Release(void)
0x18009acb6  nop
0x18009acb7  lea     rcx, [rbp+57h+var_98]
0x18009acbb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009acc0  mov     rcx, [rbp+57h+var_78]
0x18009acc4  mov     [rbp+57h+var_98], rcx
0x18009acc8  test    rcx, rcx
0x18009accb  jz      short loc_18009ACDA
0x18009accd  mov     rax, [rcx]
0x18009acd0  mov     rax, [rax+8]
0x18009acd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009acd9  nop
0x18009acda  lea     rdx, [rbp+57h+var_98]
0x18009acde  lea     rcx, [rbp+57h+var_C0]
0x18009ace2  call    ??$Make@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountEventArgs@234@@Foundation@Windows@@V_lambda_3_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@$0?0PEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountEventArgs@893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountWatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVMobileBroadbandAccountEventArgs@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountEventArgs@563@@Z@Details@WRL@Microsoft@@V_lambda_3_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountEventArgs@234@@Foundation@Windows@@V_lambda_3_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@$0?0PEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountEventArgs@893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountWatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVMobileBroadbandAccountEventArgs@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIMobileBroadbandAccountEventArgs@563@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_3_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountEventArgs *>>::*)(Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>,`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_3_,-1,Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountEventArgs *>,`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_3_>(`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_3_ &&)
0x18009ace7  mov     rbx, [rax]
0x18009acea  mov     [rbp+57h+var_A8], rbx
0x18009acee  mov     [rax], r13
0x18009acf1  mov     rcx, [rbp+57h+var_C0]
0x18009acf5  test    rcx, rcx
0x18009acf8  jz      short loc_18009AD04
0x18009acfa  mov     [rbp+57h+var_C0], r13
0x18009acfe  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>>::Release(void)
0x18009ad03  nop
0x18009ad04  lea     rcx, [rbp+57h+var_98]
0x18009ad08  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009ad0d  mov     rcx, [rbp+57h+var_78]
0x18009ad11  mov     [rbp+57h+var_98], rcx
0x18009ad15  test    rcx, rcx
0x18009ad18  jz      short loc_18009AD27
0x18009ad1a  mov     rax, [rcx]
0x18009ad1d  mov     rax, [rax+8]
0x18009ad21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad26  nop
0x18009ad27  lea     rdx, [rbp+57h+var_98]
0x18009ad2b  lea     rcx, [rbp+57h+var_C0]
0x18009ad2f  call    ??$Make@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIInspectable@@@Foundation@Windows@@V_lambda_4_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@$0?0PEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIInspectable@@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountWatcher@234@@Internal@Foundation@Windows@@PEAUIInspectable@@@Foundation@Windows@@EAAJPEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIInspectable@@@Z@Details@WRL@Microsoft@@V_lambda_4_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIInspectable@@@Foundation@Windows@@V_lambda_4_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@$0?0PEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIInspectable@@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAUIMobileBroadbandAccountWatcher@234@@Internal@Foundation@Windows@@PEAUIInspectable@@@Foundation@Windows@@EAAJPEAUIMobileBroadbandAccountWatcher@NetworkOperators@Networking@3@PEAUIInspectable@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_4_@?1??InitializeCSPEvent@CSuplHandler@@QEAAJXZ@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *>,IInspectable *>::*)(Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,IInspectable *>,`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_4_,-1,Windows::Networking::NetworkOperators::IMobileBroadbandAccountWatcher *,IInspectable *>,`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_4_>(`CSuplHandler::InitializeCSPEvent(void)'::`2'::_lambda_4_ &&)
0x18009ad34  mov     rdi, [rax]
0x18009ad37  mov     [rbp+57h+var_A0], rdi
0x18009ad3b  mov     [rax], r13
0x18009ad3e  mov     rcx, [rbp+57h+var_C0]
0x18009ad42  test    rcx, rcx
0x18009ad45  jz      short loc_18009AD51
0x18009ad47  mov     [rbp+57h+var_C0], r13
0x18009ad4b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAVMobileBroadbandAccountWatcher@NetworkOperators@Networking@Windows@@PEAVMobileBroadbandAccountEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Networking::NetworkOperators::MobileBroadbandAccountWatcher *,Windows::Networking::NetworkOperators::MobileBroadbandAccountEventArgs *>>::Release(void)
0x18009ad50  nop
0x18009ad51  lea     rcx, [rbp+57h+var_98]
0x18009ad55  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009ad5a  mov     rcx, [r12]
0x18009ad5e  mov     rax, [rcx]
0x18009ad61  lea     r8, [r15+308h]
0x18009ad68  mov     rdx, rsi
0x18009ad6b  mov     rax, [rax+30h]
0x18009ad6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad74  mov     r13d, eax
0x18009ad77  test    eax, eax
0x18009ad79  jns     short loc_18009ADD7
0x18009ad7b  test    rdi, rdi
0x18009ad7e  jz      short loc_18009AD90
0x18009ad80  mov     rcx, [rdi]
0x18009ad83  mov     rax, [rcx+10h]
0x18009ad87  mov     rcx, rdi
0x18009ad8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad8f  nop
0x18009ad90  test    rbx, rbx
0x18009ad93  jz      short loc_18009ADA5
0x18009ad95  mov     rax, [rbx]
0x18009ad98  mov     rcx, rbx
0x18009ad9b  mov     rax, [rax+10h]
0x18009ad9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ada4  nop
0x18009ada5  test    r14, r14
0x18009ada8  jz      short loc_18009ADBA
0x18009adaa  mov     rax, [r14]
0x18009adad  mov     rcx, r14
0x18009adb0  mov     rax, [rax+10h]
0x18009adb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009adb9  nop
0x18009adba  test    rsi, rsi
0x18009adbd  jz      short loc_18009ADCF
0x18009adbf  mov     rax, [rsi]
0x18009adc2  mov     rcx, rsi
0x18009adc5  mov     rax, [rax+10h]
0x18009adc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009adce  nop
0x18009adcf  mov     ebx, r13d
0x18009add2  jmp     loc_18009B179
0x18009add7  mov     rcx, [r12]
0x18009addb  mov     rax, [rcx]
0x18009adde  lea     r8, [r15+310h]
0x18009ade5  mov     rdx, r14
0x18009ade8  mov     rax, [rax+40h]
0x18009adec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009adf1  mov     r13d, eax
0x18009adf4  test    eax, eax
0x18009adf6  jns     short loc_18009AE4E
0x18009adf8  test    rdi, rdi
0x18009adfb  jz      short loc_18009AE0D
0x18009adfd  mov     rcx, [rdi]
0x18009ae00  mov     rax, [rcx+10h]
0x18009ae04  mov     rcx, rdi
0x18009ae07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae0c  nop
0x18009ae0d  test    rbx, rbx
0x18009ae10  jz      short loc_18009AE22
0x18009ae12  mov     rax, [rbx]
0x18009ae15  mov     rcx, rbx
0x18009ae18  mov     rax, [rax+10h]
0x18009ae1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae21  nop
0x18009ae22  test    r14, r14
0x18009ae25  jz      short loc_18009AE37
0x18009ae27  mov     rax, [r14]
0x18009ae2a  mov     rcx, r14
0x18009ae2d  mov     rax, [rax+10h]
0x18009ae31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae36  nop
0x18009ae37  test    rsi, rsi
0x18009ae3a  jz      short loc_18009AE4C
0x18009ae3c  mov     rax, [rsi]
0x18009ae3f  mov     rcx, rsi
0x18009ae42  mov     rax, [rax+10h]
0x18009ae46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae4b  nop
0x18009ae4c  jmp     short loc_18009ADCF
0x18009ae4e  mov     rcx, [r12]
0x18009ae52  mov     rax, [rcx]
0x18009ae55  lea     r8, [r15+318h]
0x18009ae5c  mov     rdx, rbx
0x18009ae5f  mov     rax, [rax+50h]
0x18009ae63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae68  mov     r13d, eax
0x18009ae6b  test    eax, eax
0x18009ae6d  jns     short loc_18009AEC8
0x18009ae6f  test    rdi, rdi
0x18009ae72  jz      short loc_18009AE84
0x18009ae74  mov     rcx, [rdi]
0x18009ae77  mov     rax, [rcx+10h]
0x18009ae7b  mov     rcx, rdi
0x18009ae7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae83  nop
0x18009ae84  test    rbx, rbx
0x18009ae87  jz      short loc_18009AE99
0x18009ae89  mov     rax, [rbx]
0x18009ae8c  mov     rcx, rbx
0x18009ae8f  mov     rax, [rax+10h]
0x18009ae93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae98  nop
0x18009ae99  test    r14, r14
0x18009ae9c  jz      short loc_18009AEAE
0x18009ae9e  mov     rax, [r14]
0x18009aea1  mov     rcx, r14
0x18009aea4  mov     rax, [rax+10h]
0x18009aea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aead  nop
0x18009aeae  test    rsi, rsi
0x18009aeb1  jz      short loc_18009AEC3
0x18009aeb3  mov     rax, [rsi]
0x18009aeb6  mov     rcx, rsi
0x18009aeb9  mov     rax, [rax+10h]
0x18009aebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aec2  nop
0x18009aec3  jmp     loc_18009ADCF
0x18009aec8  mov     rcx, [r12]
0x18009aecc  mov     rax, [rcx]
0x18009aecf  lea     r8, [r15+320h]
0x18009aed6  mov     rdx, rdi
0x18009aed9  mov     rax, [rax+70h]
0x18009aedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aee2  mov     r12d, eax
0x18009aee5  test    eax, eax
0x18009aee7  jns     short loc_18009AF45
0x18009aee9  test    rdi, rdi
0x18009aeec  jz      short loc_18009AEFE
0x18009aeee  mov     rcx, [rdi]
0x18009aef1  mov     rax, [rcx+10h]
0x18009aef5  mov     rcx, rdi
0x18009aef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aefd  nop
0x18009aefe  test    rbx, rbx
0x18009af01  jz      short loc_18009AF13
0x18009af03  mov     rax, [rbx]
0x18009af06  mov     rcx, rbx
0x18009af09  mov     rax, [rax+10h]
0x18009af0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af12  nop
0x18009af13  test    r14, r14
0x18009af16  jz      short loc_18009AF28
0x18009af18  mov     rax, [r14]
0x18009af1b  mov     rcx, r14
0x18009af1e  mov     rax, [rax+10h]
0x18009af22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af27  nop
0x18009af28  test    rsi, rsi
0x18009af2b  jz      short loc_18009AF3D
0x18009af2d  mov     rax, [rsi]
0x18009af30  mov     rcx, rsi
  ... truncated ...
```
