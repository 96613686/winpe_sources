# _GetFidoGattServiceWithDeviceId

- ea: `0x18002b1b8`
- end: `0x18002bbc1`
- name: `_GetFidoGattServiceWithDeviceId`
- size: `2569`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e250`

## callees

- `0x18000a210`
- `0x18000b770`
- `0x18002b1b8`
- `0x18002bbc8`
- `0x18002bbf4`
- `0x18002cbb4`
- `0x18002d984`
- `0x18002e6d4`
- `0x180044900`
- `0x1800f2258`
- `0x1800f24f8`
- `0x1800f270c`
- `0x1800f34a8`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002b40a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002b40a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b22b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b262`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b22b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb69`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b7bb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b7bb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002b4dc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002b659`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002b4dc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002b659`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b2b2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b321`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b2b2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b321`

## string_xrefs

- `0x18002b77f`: `_GetFidoGattService`
- `0x18002ba3e`: `_GetFidoGattService`
- `0x18002bb41`: `_GetFidoGattService`
- `0x18002bb0d`: `GetServices`
- `0x18002ba4e`: `AsyncComplete`
- `0x18002b8dd`: `Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall GetFidoGattServiceWithDeviceId(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rsi
  const char *v7; // r12
  int v8; // eax
  int FidoGattServiceFromServicesResult; // ebx
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64); // rbx
  __int64 v14; // rdi
  int v15; // eax
  __int64 v16; // rdx
  _QWORD *v17; // rbx
  __int64 v18; // rcx
  DWORD RemainingTimeoutMilliseconds; // r13d
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *); // rsi
  __int64 *v23; // rax
  __int64 v24; // rdi
  DWORD v25; // ebx
  int NonzeroLastError; // eax
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64); // rbx
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64); // rsi
  __int64 *v29; // rax
  __int64 v30; // rdi
  int v31; // esi
  int v32; // edi
  __int64 v33; // rdx
  DWORD v34; // ecx
  DWORD v35; // r9d
  DWORD v36; // eax
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64); // rcx
  int v39; // eax
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v41)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64); // rcx
  __int64 v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v48)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v52)(_QWORD, GUID *, __int64); // rcx
  GUID *v53; // rcx
  __int64 (__fastcall ***v55)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+38h] [rbp-C8h] BYREF
  char v57[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v58; // [rsp+48h] [rbp-B8h] BYREF
  int v59; // [rsp+50h] [rbp-B0h] BYREF
  int v60; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE hEvent; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v62; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  __int64 v64; // [rsp+70h] [rbp-90h] BYREF
  GUID *v65; // [rsp+78h] [rbp-88h] BYREF
  __int128 v66; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v67; // [rsp+90h] [rbp-70h]
  __int64 v68; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-48h]
  __int64 v72; // [rsp+C0h] [rbp-40h]
  __int64 v73; // [rsp+C8h] [rbp-38h]
  __int64 v74; // [rsp+D0h] [rbp-30h]
  HANDLE Handles; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v76; // [rsp+E0h] [rbp-20h]
  HSTRING_HEADER v77; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v78; // [rsp+100h] [rbp+0h]

  v74 = a4;
  v73 = a2;
  v71 = *(_QWORD *)(a1 + 40);
  v6 = *(_QWORD *)(v71 + 312);
  v72 = v6;
  hEvent = 0;
  v69 = 0;
  v62 = 0;
  v7 = 0;
  v65 = 0;
  v64 = 0;
  hObject = CreateEventW(0, 0, 0, 0);
  if ( hObject )
  {
    hEvent = CreateEventW(0, 0, 0, 0);
    if ( hEvent )
    {
      LODWORD(v58) = 0;
      v78 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v77,
        L"Windows.Devices.Bluetooth.BluetoothDeviceId",
        0x2Cu,
        0x2Bu);
      v10 = v78;
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v64);
      if ( (int)RoGetActivationFactory(v10, &GUID_a7884e67_3efb_4f31_bbc2_810e09977404, &v64) >= 0
        && (*(int (__fastcall **)(__int64, __int64, GUID **))(*(_QWORD *)v64 + 48LL))(v64, a3, &v65) >= 0 )
      {
        v55 = 0;
        v78 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &v77,
          L"Windows.Devices.Bluetooth.GenericAttributeProfile.GattSession",
          0x3Eu,
          0x3Du);
        v11 = v78;
        _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v55);
        if ( (int)RoGetActivationFactory(v11, &GUID_2e65b95c_539f_4db7_82a8_73bdbbf73ebf, &v55) >= 0 )
        {
          v56 = 0;
          v12 = v55;
          v13 = (*v55)[6];
          _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
          if ( (int)v13(v12, v65, (__int64)&v56) >= 0 )
          {
            v14 = v56;
            v15 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattSession *> *>(v56);
            v17 = (_QWORD *)(a1 + 88);
            if ( v15 >= 0 )
              v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 64LL))(v14, a1 + 88);
            if ( v15 >= 0 )
            {
              LOBYTE(v16) = 1;
              if ( (*(int (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v17 + 64LL))(*v17, v16) < 0 )
              {
                v18 = *v17;
                if ( *v17 )
                {
                  *v17 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                }
              }
            }
          }
          _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
        }
        _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v55);
      }
      while ( 1 )
      {
        RemainingTimeoutMilliseconds = CtapDeviceGetRemainingTimeoutMilliseconds(v6, 0);
        v59 = -2147467259;
        v55 = 0;
        v56 = 0;
        v60 = 0;
        ResetEvent(hEvent);
        v20 = *(_QWORD *)(a1 + 88);
        if ( !v20 )
          goto LABEL_31;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 88LL))(v20, &v60);
        v21 = *(_QWORD *)(a1 + 88);
        v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v21 + 112LL);
        *(_QWORD *)&v66 = &hEvent;
        v23 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Bluetooth::GenericAttributeProfile::GattSession___Windows::Devices::Bluetooth::GenericAttributeProfile::IGattSession____Windows::Foundation::Internal::AggregateType_Windows::Devices::Bluetooth::GenericAttributeProfile::GattSessionStatusChangedEventArgs___Windows::Devices::Bluetooth::GenericAttributeProfile::IGattSessionStatusChangedEventArgs_____::___Windows::Devices::Bluetooth::GenericAttributeProfile::IGattSession___Windows::Devices::Bluetooth::GenericAttributeProfile::IGattSessionStatusChangedEventArgs____::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::Devices::Bluetooth::GenericAttributeProfile::GattSession___Windows::Devices::Bluetooth::GenericAttributeProfile::GattSessionStatusChangedEventArgs______GetFidoGattServiceWithDeviceId_::_32_::_lambda_1___1_Windows::Devices::Bluetooth::GenericAttributeProfile::IGattSession___Windows::Devices::Bluetooth::GenericAttributeProfile::IGattSessionStatusChangedEventArgs______GetFidoGattServiceWithDeviceId_::_32_::_lambda_1___(
                           &v68,
                           &v66);
        v24 = *v23;
        *(_QWORD *)&v66 = *v23;
        *v23 = 0;
        if ( v68 )
        {
          v68 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWTSListenerCallback>::Release();
        }
        FidoGattServiceFromServicesResult = v22(v21, v24, &v69);
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        if ( FidoGattServiceFromServicesResult < 0 )
        {
          _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
          v41 = v55;
          if ( v55 )
          {
            v55 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v41)[2])(v41);
          }
          goto LABEL_120;
        }
        if ( v60 == 1 )
          goto LABEL_31;
        Handles = hEvent;
        v76 = *(_QWORD *)(v71 + 32);
        v25 = WaitForMultipleObjects((v76 != 0) + 1, &Handles, 0, RemainingTimeoutMilliseconds);
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 88) + 120LL))(*(_QWORD *)(a1 + 88), v69);
        if ( v25 )
        {
          if ( v25 == 1 )
          {
            FidoGattServiceFromServicesResult = -2147023673;
LABEL_77:
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v40 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v40)[2])(v40);
            }
            goto LABEL_120;
          }
          if ( v25 == 258 )
          {
            FidoGattServiceFromServicesResult = -2147023436;
            goto LABEL_77;
          }
          if ( v25 != -1 )
          {
            FidoGattServiceFromServicesResult = -2147418113;
            goto LABEL_77;
          }
          NonzeroLastError = _GetNonzeroLastError();
          FidoGattServiceFromServicesResult = NonzeroLastError;
          if ( NonzeroLastError > 0 )
            FidoGattServiceFromServicesResult = (unsigned __int16)NonzeroLastError | 0x80070000;
          if ( FidoGattServiceFromServicesResult < 0 )
            goto LABEL_77;
LABEL_31:
          v66 = xmmword_18014FEE0;
          FidoGattServiceFromServicesResult = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v73 + 88LL))(
                                                v73,
                                                &v66,
                                                1,
                                                &v55);
          if ( FidoGattServiceFromServicesResult < 0 )
          {
            v7 = "GetServices";
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v52 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v52)[2])(v52);
            }
            goto LABEL_120;
          }
          if ( !v55 )
          {
            FidoGattServiceFromServicesResult = -2147418113;
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v51 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v51)[2])(v51);
            }
            goto LABEL_120;
          }
          FidoGattServiceFromServicesResult = Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult *>>::As<IAsyncInfo>(
                                                &v55,
                                                (__int64)&v56);
          if ( FidoGattServiceFromServicesResult < 0 )
          {
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v50 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v50)[2])(v50);
            }
            goto LABEL_120;
          }
          v27 = v55;
          v28 = (*v55)[6];
          *(_QWORD *)&v66 = &hObject;
          *((_QWORD *)&v66 + 1) = &v59;
          v67 = &v62;
          v29 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult___Windows::Devices::Bluetooth::GenericAttributeProfile::IGattDeviceServicesResult_____::___Windows::Foundation::IAsyncOperation_Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult______GetFidoGattServiceWithDeviceId_::_29_::_lambda_2___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult______enum_ABI::Windows::Foundation::AsyncStatus____GetFidoGattServiceWithDeviceId_::_29_::_lambda_2___(
                             &v70,
                             &v66);
          v30 = *v29;
          *(_QWORD *)&v66 = *v29;
          *v29 = 0;
          if ( v70 )
          {
            v70 = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWTSListenerCallback>::Release();
          }
          FidoGattServiceFromServicesResult = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64))v28)(
                                                v27,
                                                v30);
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          if ( FidoGattServiceFromServicesResult < 0 )
          {
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v49 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v49)[2])(v49);
            }
            goto LABEL_120;
          }
          v31 = 0;
          v32 = 0;
          while ( 1 )
          {
            v77.Reserved.Reserved1 = hObject;
            v33 = *(_QWORD *)(v71 + 32);
            *(_QWORD *)&v77.Reserved.Reserved2[8] = v33;
            v34 = 2 - (v32 != 0);
            v35 = 500;
            if ( !v32 )
              v35 = RemainingTimeoutMilliseconds;
            if ( !v33 )
              v34 = 1;
            v36 = WaitForMultipleObjects(v34, &v77.Reserved.Reserved1, 0, v35);
            FidoGattServiceFromServicesResult = -2147023436;
            if ( !v36 )
              break;
            if ( v36 == 1 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 72LL))(v56);
              if ( (unsigned int)++v32 > 1 )
                goto LABEL_58;
              v31 = 1;
            }
            else
            {
              if ( v36 != 258 )
              {
                if ( v36 == -1 )
                {
                  v39 = _GetNonzeroLastError();
                  FidoGattServiceFromServicesResult = v39;
                  if ( v39 > 0 )
                    FidoGattServiceFromServicesResult = (unsigned __int16)v39 | 0x80070000;
                }
                else
                {
                  FidoGattServiceFromServicesResult = -2147418113;
                }
                goto LABEL_58;
              }
              if ( v32 )
              {
                if ( v31 )
                  FidoGattServiceFromServicesResult = -2147023673;
                goto LABEL_58;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 72LL))(v56);
              v32 = 1;
            }
          }
          if ( v59 != -2147023673 || v31 )
            FidoGattServiceFromServicesResult = v59;
LABEL_58:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 80LL))(v56);
          if ( FidoGattServiceFromServicesResult < 0 )
          {
            LODWORD(v58) = 0;
            (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 64LL))(v56, &v58);
            CtapBleLogError((unsigned int)v58, "_GetFidoGattService", "ErrorCode");
            v7 = "AsyncComplete";
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v48 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v48)[2])(v48);
            }
            goto LABEL_120;
          }
          if ( !v62 )
          {
            FidoGattServiceFromServicesResult = -2147418113;
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v47 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v47)[2])(v47);
            }
            goto LABEL_120;
          }
          LODWORD(v66) = 3;
          FidoGattServiceFromServicesResult = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v62 + 48LL))(
                                                v62,
                                                &v66);
          if ( FidoGattServiceFromServicesResult < 0 )
          {
            v7 = "Status";
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v46 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v46)[2])(v46);
            }
            goto LABEL_120;
          }
          if ( !(_DWORD)v66 )
          {
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v45 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v45)[2])(v45);
            }
            FidoGattServiceFromServicesResult = GetFidoGattServiceFromServicesResult(a1, v62, v74);
            goto LABEL_120;
          }
          if ( (_DWORD)v66 != 1 )
          {
            FidoGattServiceFromServicesResult = -2147023729;
            if ( (_DWORD)v66 == 2 )
            {
              v58 = 0;
              v7 = "Protocol";
              FidoGattServiceFromServicesResult = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 56LL))(
                                                    v62,
                                                    &v58);
              if ( FidoGattServiceFromServicesResult < 0 )
                goto LABEL_91;
              v43 = v58;
              if ( v58 )
              {
                v57[0] = 0;
                FidoGattServiceFromServicesResult = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 48LL))(
                                                      v58,
                                                      v57);
                if ( FidoGattServiceFromServicesResult >= 0 )
                  FidoGattServiceFromServicesResult = (unsigned __int8)v57[0] | 0x80650000;
LABEL_91:
                v43 = v58;
              }
              if ( v43 )
              {
                v58 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
              }
            }
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v44 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v44)[2])(v44);
            }
            goto LABEL_120;
          }
          CtapDevicePublishWnfState(4u, 0x65u, 0, 0);
          CtapBleLogError(2147942721LL, "_GetFidoGattService", "Unreachable");
          LODWORD(v58) = v58 + 1;
          if ( (unsigned int)v58 > 3 )
          {
            FidoGattServiceFromServicesResult = -2147024575;
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
            v42 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v42)[2])(v42);
            }
            goto LABEL_120;
          }
          v6 = v72;
          if ( (unsigned int)CtapDeviceGetRemainingTimeoutMilliseconds(v72, 0) > 0x96 )
            Sleep(0x32u);
          _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
          v38 = v55;
          if ( v55 )
          {
            v55 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v38)[2])(v38);
          }
        }
        else
        {
          _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v56);
          v37 = v55;
          if ( v55 )
          {
            v55 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v37)[2])(v37);
          }
          v6 = v72;
        }
      }
    }
  }
  v8 = _GetNonzeroLastError();
  FidoGattServiceFromServicesResult = v8;
  if ( v8 > 0 )
    FidoGattServiceFromServicesResult = (unsigned __int16)v8 | 0x80070000;
LABEL_120:
  CtapBleLogError((unsigned int)FidoGattServiceFromServicesResult, "_GetFidoGattService", v7);
  if ( hObject )
    CloseHandle(hObject);
  if ( hEvent )
    CloseHandle(hEvent);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v64);
  v53 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v53->Data1 + 16LL))(v53);
  }
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v62);
  return (unsigned int)FidoGattServiceFromServicesResult;
}

```

## disassembly

```asm
0x18002b1b8  push    rbp
0x18002b1ba  push    rbx
0x18002b1bb  push    rsi
0x18002b1bc  push    rdi
0x18002b1bd  push    r12
0x18002b1bf  push    r13
0x18002b1c1  push    r15
0x18002b1c3  lea     rbp, [rsp-10h]
0x18002b1c8  sub     rsp, 110h
0x18002b1cf  mov     rax, cs:__security_cookie
0x18002b1d6  xor     rax, rsp
0x18002b1d9  mov     [rbp+40h+var_38], rax
0x18002b1dd  mov     [rbp+40h+var_70], r9
0x18002b1e1  mov     rdi, r8
0x18002b1e4  mov     [rbp+40h+var_78], rdx
0x18002b1e8  mov     r15, rcx
0x18002b1eb  mov     rax, [rcx+28h]
0x18002b1ef  mov     [rbp+40h+var_88], rax
0x18002b1f3  mov     rsi, [rax+138h]
0x18002b1fa  mov     [rbp+40h+var_80], rsi
0x18002b1fe  xor     r13d, r13d
0x18002b201  mov     [rsp+140h+hObject], r13
0x18002b206  mov     [rsp+140h+hEvent], r13
0x18002b20b  mov     [rbp+40h+var_98], r13
0x18002b20f  mov     [rsp+140h+var_E0], r13
0x18002b214  mov     r12d, r13d
0x18002b217  mov     [rsp+140h+var_C8], r13
0x18002b21c  mov     [rsp+140h+var_D0], r13
0x18002b221  xor     r9d, r9d; lpName
0x18002b224  xor     r8d, r8d; bInitialState
0x18002b227  xor     edx, edx; bManualReset
0x18002b229  xor     ecx, ecx; lpEventAttributes
0x18002b22b  call    cs:__imp_CreateEventW
0x18002b231  mov     [rsp+140h+hObject], rax
0x18002b236  test    rax, rax
0x18002b239  jnz     short loc_18002B258
0x18002b23b  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x18002b240  mov     ebx, eax
0x18002b242  test    eax, eax
0x18002b244  jle     loc_18002BB3E
0x18002b24a  movzx   ebx, ax
0x18002b24d  or      ebx, 80070000h
0x18002b253  jmp     loc_18002BB3E
0x18002b258  xor     r9d, r9d; lpName
0x18002b25b  xor     r8d, r8d; bInitialState
0x18002b25e  xor     edx, edx; bManualReset
0x18002b260  xor     ecx, ecx; lpEventAttributes
0x18002b262  call    cs:__imp_CreateEventW
0x18002b268  mov     [rsp+140h+hEvent], rax
0x18002b26d  test    rax, rax
0x18002b270  jz      short loc_18002B23B
0x18002b272  mov     dword ptr [rsp+140h+var_F8], r13d
0x18002b277  mov     [rbp+40h+var_40], r13
0x18002b27b  mov     r9d, 2Bh ; '+'; unsigned int
0x18002b281  lea     r8d, [r9+1]; unsigned int
0x18002b285  lea     rdx, ?RuntimeClass_Windows_Devices_Bluetooth_BluetoothDeviceId@@3QBGB; "Windows.Devices.Bluetooth.BluetoothDevi"...
0x18002b28c  lea     rcx, [rbp+40h+var_58]; hstringHeader
0x18002b290  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b295  mov     rbx, [rbp+40h+var_40]
0x18002b299  lea     rcx, [rsp+140h+var_D0]
0x18002b29e  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002b2a3  lea     r8, [rsp+140h+var_D0]
0x18002b2a8  lea     rdx, _GUID_a7884e67_3efb_4f31_bbc2_810e09977404
0x18002b2af  mov     rcx, rbx
0x18002b2b2  call    cs:__imp_RoGetActivationFactory
0x18002b2b8  test    eax, eax
0x18002b2ba  js      loc_18002B3D1
0x18002b2c0  mov     rcx, [rsp+140h+var_D0]
0x18002b2c5  mov     rax, [rcx]
0x18002b2c8  lea     r8, [rsp+140h+var_C8]
0x18002b2cd  mov     rdx, rdi
0x18002b2d0  mov     rax, [rax+30h]
0x18002b2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2d9  test    eax, eax
0x18002b2db  js      loc_18002B3D1
0x18002b2e1  mov     [rsp+140h+var_110], r13
0x18002b2e6  mov     [rbp+40h+var_40], r13
0x18002b2ea  mov     r9d, 3Dh ; '='; unsigned int
0x18002b2f0  lea     r8d, [r9+1]; unsigned int
0x18002b2f4  lea     rdx, ?RuntimeClass_Windows_Devices_Bluetooth_GenericAttributeProfile_GattSession@@3QBGB; "Windows.Devices.Bluetooth.GenericAttrib"...
0x18002b2fb  lea     rcx, [rbp+40h+var_58]; hstringHeader
0x18002b2ff  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b304  mov     rbx, [rbp+40h+var_40]
0x18002b308  lea     rcx, [rsp+140h+var_110]
0x18002b30d  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002b312  lea     r8, [rsp+140h+var_110]
0x18002b317  lea     rdx, _GUID_2e65b95c_539f_4db7_82a8_73bdbbf73ebf
0x18002b31e  mov     rcx, rbx
0x18002b321  call    cs:__imp_RoGetActivationFactory
0x18002b327  test    eax, eax
0x18002b329  js      loc_18002B3C7
0x18002b32f  mov     [rsp+140h+var_108], r13
0x18002b334  mov     rdi, [rsp+140h+var_110]
0x18002b339  mov     rax, [rdi]
0x18002b33c  mov     rbx, [rax+30h]
0x18002b340  lea     rcx, [rsp+140h+var_108]
0x18002b345  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002b34a  lea     r8, [rsp+140h+var_108]
0x18002b34f  mov     rdx, [rsp+140h+var_C8]
0x18002b354  mov     rcx, rdi
0x18002b357  mov     rax, rbx
0x18002b35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b35f  test    eax, eax
0x18002b361  js      short loc_18002B3BC
0x18002b363  mov     rdi, [rsp+140h+var_108]
0x18002b368  mov     rcx, rdi
0x18002b36b  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGattSession@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGattSession@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattSession *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattSession *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18002b370  lea     rbx, [r15+58h]
0x18002b374  test    eax, eax
0x18002b376  js      short loc_18002B38B
0x18002b378  mov     rax, [rdi]
0x18002b37b  mov     rdx, rbx
0x18002b37e  mov     rcx, rdi
0x18002b381  mov     rax, [rax+40h]
0x18002b385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b38a  nop
0x18002b38b  test    eax, eax
0x18002b38d  js      short loc_18002B3BC
0x18002b38f  mov     rcx, [rbx]
0x18002b392  mov     rax, [rcx]
0x18002b395  mov     dl, 1
0x18002b397  mov     rax, [rax+40h]
0x18002b39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3a0  test    eax, eax
0x18002b3a2  jns     short loc_18002B3BC
0x18002b3a4  mov     rcx, [rbx]
0x18002b3a7  test    rcx, rcx
0x18002b3aa  jz      short loc_18002B3BC
0x18002b3ac  mov     [rbx], r13
0x18002b3af  mov     rax, [rcx]
0x18002b3b2  mov     rax, [rax+10h]
0x18002b3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3bb  nop
0x18002b3bc  lea     rcx, [rsp+140h+var_108]
0x18002b3c1  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002b3c6  nop
0x18002b3c7  lea     rcx, [rsp+140h+var_110]
0x18002b3cc  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002b3d1  mov     edi, 1
0x18002b3d6  xor     edx, edx
0x18002b3d8  mov     rcx, rsi
0x18002b3db  call    CtapDeviceGetRemainingTimeoutMilliseconds
0x18002b3e0  mov     r13d, eax
0x18002b3e3  mov     [rsp+140h+var_F0], 80004005h
0x18002b3eb  mov     [rsp+140h+var_110], 0
0x18002b3f4  mov     [rsp+140h+var_108], 0
0x18002b3fd  mov     [rsp+140h+var_EC], 0
0x18002b405  mov     rcx, [rsp+140h+hEvent]; hEvent
0x18002b40a  call    cs:__imp_ResetEvent
0x18002b410  mov     rcx, [r15+58h]
0x18002b414  test    rcx, rcx
0x18002b417  jz      loc_18002B53C
0x18002b41d  mov     rax, [rcx]
0x18002b420  lea     rdx, [rsp+140h+var_EC]
0x18002b425  mov     rax, [rax+58h]
0x18002b429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b42e  mov     rbx, [r15+58h]
0x18002b432  mov     rax, [rbx]
0x18002b435  mov     rsi, [rax+70h]
0x18002b439  lea     rax, [rsp+140h+hEvent]
0x18002b43e  mov     qword ptr [rbp+40h+var_C0], rax
0x18002b442  lea     rdx, [rbp+40h+var_C0]
0x18002b446  lea     rcx, [rbp+40h+var_A0]
0x18002b44a  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Devices__Bluetooth__GenericAttributeProfile__GattSession___Windows__Devices__Bluetooth__GenericAttributeProfile__IGattSession____Windows__Foundation__Internal__AggregateType_Windows__Devices__Bluetooth__GenericAttributeProfile__GattSessionStatusChangedEventArgs___Windows__Devices__Bluetooth__GenericAttributeProfile__IGattSessionStatusChangedEventArgs__________Windows__Devices__Bluetooth__GenericAttributeProfile__IGattSession___Windows__Devices__Bluetooth__GenericAttributeProfile__IGattSessionStatusChangedEventArgs______DelegateInvokeHelper_Windows__Foundation__ITypedEventHandler_Windows__Devices__Bluetooth__GenericAttributeProfile__GattSession___Windows__Devices__Bluetooth__GenericAttributeProfile__GattSessionStatusChangedEventArgs______GetFidoGattServiceWithDeviceId____32____lambda_1___1_Windows__Devices__Bluetooth__GenericAttributeProfile__IGattSession___Windows__Devices__Bluetooth__GenericAttributeProfile__IGattSessionStatusChangedEventArgs______GetFidoGattServiceWithDeviceId____32____lambda_1___
0x18002b44f  mov     rdi, [rax]
0x18002b452  mov     qword ptr [rbp+40h+var_C0], rdi
0x18002b456  mov     qword ptr [rax], 0
0x18002b45d  mov     rcx, [rbp+40h+var_A0]
0x18002b461  test    rcx, rcx
0x18002b464  jz      short loc_18002B474
0x18002b466  mov     [rbp+40h+var_A0], 0
0x18002b46e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWTSListenerCallback@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWTSListenerCallback>::Release(void)
0x18002b473  nop
0x18002b474  lea     r8, [rbp+40h+var_98]
0x18002b478  mov     rdx, rdi
0x18002b47b  mov     rcx, rbx
0x18002b47e  mov     rax, rsi
0x18002b481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b486  mov     ebx, eax
0x18002b488  test    rdi, rdi
0x18002b48b  jz      short loc_18002B49D
0x18002b48d  mov     rcx, [rdi]
0x18002b490  mov     rax, [rcx+10h]
0x18002b494  mov     rcx, rdi
0x18002b497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b49c  nop
0x18002b49d  test    ebx, ebx
0x18002b49f  js      loc_18002B86E
0x18002b4a5  mov     edi, 1
0x18002b4aa  cmp     [rsp+140h+var_EC], edi
0x18002b4ae  jz      loc_18002B53C
0x18002b4b4  mov     rax, [rsp+140h+hEvent]
0x18002b4b9  mov     [rbp+40h+Handles], rax
0x18002b4bd  mov     rax, [rbp+40h+var_88]
0x18002b4c1  mov     rax, [rax+20h]
0x18002b4c5  mov     [rbp+40h+var_60], rax
0x18002b4c9  neg     rax
0x18002b4cc  sbb     ecx, ecx
0x18002b4ce  neg     ecx
0x18002b4d0  add     ecx, edi; nCount
0x18002b4d2  mov     r9d, r13d; dwMilliseconds
0x18002b4d5  xor     r8d, r8d; bWaitAll
0x18002b4d8  lea     rdx, [rbp+40h+Handles]; lpHandles
0x18002b4dc  call    cs:__imp_WaitForMultipleObjects
0x18002b4e2  mov     ebx, eax
0x18002b4e4  mov     r8, [r15+58h]
0x18002b4e8  mov     rcx, [r8]
0x18002b4eb  mov     rax, [rcx+78h]
0x18002b4ef  mov     rdx, [rbp+40h+var_98]
0x18002b4f3  mov     rcx, r8
0x18002b4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4fb  test    ebx, ebx
0x18002b4fd  jz      loc_18002B691
0x18002b503  cmp     ebx, edi
0x18002b505  jz      loc_18002B83A
0x18002b50b  cmp     ebx, 102h
0x18002b511  jz      loc_18002B833
0x18002b517  cmp     ebx, 0FFFFFFFFh
0x18002b51a  jnz     loc_18002B82C
0x18002b520  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x18002b525  mov     ebx, eax
0x18002b527  test    eax, eax
0x18002b529  jle     short loc_18002B534
0x18002b52b  movzx   ebx, ax
0x18002b52e  or      ebx, 80070000h
0x18002b534  test    ebx, ebx
0x18002b536  js      loc_18002B83F
0x18002b53c  movups  xmm0, cs:xmmword_18014FEE0
0x18002b543  movdqu  [rbp+40h+var_C0], xmm0
0x18002b548  mov     rcx, [rbp+40h+var_78]
0x18002b54c  mov     rax, [rcx]
0x18002b54f  lea     r9, [rsp+140h+var_110]
0x18002b554  mov     r8d, edi
0x18002b557  lea     rdx, [rbp+40h+var_C0]
0x18002b55b  mov     rax, [rax+58h]
0x18002b55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b564  mov     ebx, eax
0x18002b566  test    eax, eax
0x18002b568  js      loc_18002BB0D
0x18002b56e  cmp     [rsp+140h+var_110], 0
0x18002b574  jz      loc_18002BADC
0x18002b57a  lea     rdx, [rsp+140h+var_108]
0x18002b57f  lea     rcx, [rsp+140h+var_110]
0x18002b584  call    ??$As@UIAsyncInfo@@@?$ComPtr@U?$IAsyncOperation@PEAVGattDeviceServicesResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult *>>::As<IAsyncInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18002b589  mov     ebx, eax
0x18002b58b  test    eax, eax
0x18002b58d  js      loc_18002BAB0
0x18002b593  mov     rbx, [rsp+140h+var_110]
0x18002b598  mov     rax, [rbx]
0x18002b59b  mov     rsi, [rax+30h]
0x18002b59f  lea     rax, [rsp+140h+hObject]
0x18002b5a4  mov     qword ptr [rbp+40h+var_C0], rax
0x18002b5a8  lea     rax, [rsp+140h+var_F0]
0x18002b5ad  mov     qword ptr [rbp+40h+var_C0+8], rax
0x18002b5b1  lea     rax, [rsp+140h+var_E0]
0x18002b5b6  mov     [rbp+40h+var_B0], rax
0x18002b5ba  lea     rdx, [rbp+40h+var_C0]
0x18002b5be  lea     rcx, [rbp+40h+var_90]
0x18002b5c2  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Devices__Bluetooth__GenericAttributeProfile__GattDeviceServicesResult___Windows__Devices__Bluetooth__GenericAttributeProfile__IGattDeviceServicesResult__________Windows__Foundation__IAsyncOperation_Windows__Devices__Bluetooth__GenericAttributeProfile__GattDeviceServicesResult______enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Devices__Bluetooth__GenericAttributeProfile__GattDeviceServicesResult______GetFidoGattServiceWithDeviceId____29____lambda_2___1_Windows__Foundation__IAsyncOperation_Windows__Devices__Bluetooth__GenericAttributeProfile__GattDeviceServicesResult______enum_ABI__Windows__Foundation__AsyncStatus____GetFidoGattServiceWithDeviceId____29____lambda_2___
0x18002b5c7  mov     rdi, [rax]
0x18002b5ca  mov     qword ptr [rbp+40h+var_C0], rdi
0x18002b5ce  mov     qword ptr [rax], 0
0x18002b5d5  mov     rcx, [rbp+40h+var_90]
0x18002b5d9  test    rcx, rcx
0x18002b5dc  jz      short loc_18002B5EC
0x18002b5de  mov     [rbp+40h+var_90], 0
0x18002b5e6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWTSListenerCallback@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWTSListenerCallback>::Release(void)
0x18002b5eb  nop
0x18002b5ec  mov     rdx, rdi
0x18002b5ef  mov     rcx, rbx
0x18002b5f2  mov     rax, rsi
0x18002b5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5fa  mov     ebx, eax
0x18002b5fc  test    rdi, rdi
0x18002b5ff  jz      short loc_18002B611
0x18002b601  mov     rax, [rdi]
0x18002b604  mov     rcx, rdi
0x18002b607  mov     rax, [rax+10h]
0x18002b60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b610  nop
0x18002b611  test    ebx, ebx
0x18002b613  js      loc_18002BA81
0x18002b619  xor     esi, esi
0x18002b61b  xor     edi, edi
0x18002b61d  mov     rax, [rsp+140h+hObject]
0x18002b622  mov     [rbp+40h+var_58], rax
0x18002b626  mov     rax, [rbp+40h+var_88]
0x18002b62a  mov     rdx, [rax+20h]
0x18002b62e  mov     [rbp+40h+var_50], rdx
0x18002b632  mov     eax, edi
0x18002b634  neg     eax
0x18002b636  sbb     ecx, ecx
0x18002b638  add     ecx, 2
0x18002b63b  mov     r9d, 1F4h
0x18002b641  test    edi, edi
0x18002b643  cmovz   r9d, r13d; dwMilliseconds
0x18002b647  test    rdx, rdx
0x18002b64a  mov     eax, 1
0x18002b64f  cmovz   ecx, eax; nCount
0x18002b652  xor     r8d, r8d; bWaitAll
  ... truncated ...
```
