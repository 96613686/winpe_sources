# GetCallerPackageDetails(void * const,int &,int &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18003737c`
- end: `0x180037a22`
- name: `?GetCallerPackageDetails@@YAJQEAXAEAH1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@222@Z`
- size: `1702`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e848`
- `0x18010f334`
- `0x18011a3cc`

## callees

- `0x18001df88`
- `0x180023bc8`
- `0x18002bbc8`
- `0x18002cbb4`
- `0x18002cf0c`
- `0x180036da4`
- `0x18003737c`
- `0x180037f6c`
- `0x18007e064`
- `0x18011c554`
- `0x18011e1e8`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003780b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037976`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003780b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037976`

## string_xrefs

- `0x180037476`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x180037509`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18003755a`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x1800375d9`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x180037663`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x1800376ef`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x1800377a4`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18003786d`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x180037904`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall GetCallerPackageDetails(
        __int64 a1,
        _DWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  HANDLE v10; // r9
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, _QWORD); // rsi
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rdi
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v29; // rsi
  __int64 v30; // r8
  int v31; // eax
  __int64 v32; // rcx
  PCWSTR v33; // rax
  __int64 v34; // r8
  __int64 (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v36)(_QWORD, GUID *, __int64 *); // rdi
  int v37; // eax
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  PCWSTR v41; // rax
  __int64 v42; // rcx
  int v43[2]; // [rsp+20h] [rbp-D8h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-D0h] BYREF
  __int64 v45; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C0h] BYREF
  int v47; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+48h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-A8h] BYREF
  HSTRING v50; // [rsp+58h] [rbp-A0h] BYREF
  HSTRING v51; // [rsp+60h] [rbp-98h] BYREF
  _QWORD *v52; // [rsp+68h] [rbp-90h] BYREF
  __int64 v53; // [rsp+70h] [rbp-88h]
  _BYTE v54[32]; // [rsp+78h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-60h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v53 = a6;
  *a3 = 0;
  *a2 = 0;
  std::wstring::wstring(v54);
  if ( GetPackageFullName(v10, (__int64)v54) < 0 || (std::wstring::operator=(a4, v54), !a4[2]) )
  {
    std::wstring::_Tidy_deallocate(v54);
    return 2147943568LL;
  }
  v45 = 0;
  v56 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Management.Deployment.PackageManager",
    0x2Du,
    0x2Cu);
  v12 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
          v56,
          &v45);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)v12,
      v43[0]);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v45);
    std::wstring::_Tidy_deallocate(v54);
    return v13;
  }
  v44 = 0;
  v14 = v45;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v45 + 136LL);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
  if ( a4[3] > 7u )
    a4 = (_QWORD *)*a4;
  v52 = a4;
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v52);
  v17 = v15(v14, *(_QWORD *)(v16 + 24), &v44);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)v17,
      v43[0]);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v45);
    std::wstring::_Tidy_deallocate(v54);
    return v18;
  }
  v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
  if ( !v44 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)0x80070490LL,
      v43[0]);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v45);
    std::wstring::_Tidy_deallocate(v54);
    return 2147943568LL;
  }
  v46 = 0;
  v20 = **v44;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v46);
  v21 = v20(v19, &GUID_65aed1ae_b95b_450c_882b_6255187f397e, &v46);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)v21,
      v43[0]);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v46);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v45);
    std::wstring::_Tidy_deallocate(v54);
    return v22;
  }
  v47 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 48LL))(v46, &v47);
  *(_QWORD *)v43 = 0;
  v23 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int *))(*v44)[6])(v44, v43);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C8,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)v23,
      v43[0]);
    v25 = *(_QWORD *)v43;
    if ( *(_QWORD *)v43 )
    {
      *(_QWORD *)v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
LABEL_37:
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v46);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v45);
    std::wstring::_Tidy_deallocate(v54);
    return v24;
  }
  string = 0;
  v26 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)v43 + 104LL))(*(_QWORD *)v43, &string);
  v24 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)v26,
      v43[0]);
    v27 = *(_QWORD *)v43;
    if ( *(_QWORD *)v43 )
    {
      *(_QWORD *)v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_37;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v29 = -1;
  v30 = -1;
  do
    ++v30;
  while ( StringRawBuffer[v30] );
  std::wstring::_Assign<unsigned short>(a5, StringRawBuffer);
  v50 = 0;
  v31 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)v43 + 88LL))(*(_QWORD *)v43, &v50);
  v24 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)v31,
      v43[0]);
    v32 = *(_QWORD *)v43;
    if ( *(_QWORD *)v43 )
    {
      *(_QWORD *)v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    goto LABEL_37;
  }
  v33 = WindowsGetStringRawBuffer(v50, 0);
  v34 = -1;
  do
    ++v34;
  while ( v33[v34] );
  std::wstring::_Assign<unsigned short>(a7, v33);
  v48 = 0;
  v35 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
  v36 = **v44;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v48);
  v37 = v36(v35, &GUID_a6612fb6_7688_4ace_95fb_359538e7aa01, &v48);
  v24 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)v37,
      v43[0]);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v48);
    v38 = *(_QWORD *)v43;
    if ( *(_QWORD *)v43 )
    {
      *(_QWORD *)v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    goto LABEL_37;
  }
  v51 = 0;
  v39 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 56LL))(v48, &v51);
  v24 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)v39,
      v43[0]);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v48);
    v40 = *(_QWORD *)v43;
    if ( *(_QWORD *)v43 )
    {
      *(_QWORD *)v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    goto LABEL_37;
  }
  v41 = WindowsGetStringRawBuffer(v51, 0);
  do
    ++v29;
  while ( v41[v29] );
  std::wstring::_Assign<unsigned short>(v53, v41);
  *a3 = v47;
  *a2 = 1;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v48);
  v42 = *(_QWORD *)v43;
  if ( *(_QWORD *)v43 )
  {
    *(_QWORD *)v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v46);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v45);
  std::wstring::_Tidy_deallocate(v54);
  return 0;
}

```

## disassembly

```asm
0x18003737c  push    rbx
0x18003737e  push    rsi
0x18003737f  push    rdi
0x180037380  push    r12
0x180037382  push    r13
0x180037384  push    r14
0x180037386  push    r15
0x180037388  sub     rsp, 0C0h
0x18003738f  mov     rax, cs:__security_cookie
0x180037396  xor     rax, rsp
0x180037399  mov     [rsp+0F8h+var_40], rax
0x1800373a1  mov     rbx, r9
0x1800373a4  mov     r12, r8
0x1800373a7  mov     r15, rdx
0x1800373aa  mov     r9, rcx
0x1800373ad  mov     r14, [rsp+0F8h+arg_20]
0x1800373b5  mov     rax, [rsp+0F8h+arg_28]
0x1800373bd  mov     [rsp+0F8h+var_88], rax
0x1800373c2  mov     r13, [rsp+0F8h+arg_30]
0x1800373ca  xor     esi, esi
0x1800373cc  mov     [r8], esi
0x1800373cf  mov     [rdx], esi
0x1800373d1  lea     rcx, [rsp+0F8h+var_80]
0x1800373d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800373db  nop
0x1800373dc  lea     rdx, [rsp+0F8h+var_80]
0x1800373e1  mov     rcx, r9; token
0x1800373e4  call    ?GetPackageFullName@@YAJQEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPackageFullName(void * const,std::wstring &)
0x1800373e9  test    eax, eax
0x1800373eb  jns     short loc_180037401
0x1800373ed  lea     rcx, [rsp+0F8h+var_80]
0x1800373f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800373f7  mov     eax, 80070490h
0x1800373fc  jmp     loc_1800379FE
0x180037401  lea     rdx, [rsp+0F8h+var_80]
0x180037406  mov     rcx, rbx
0x180037409  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003740e  cmp     [rbx+10h], rsi
0x180037412  jnz     short loc_180037428
0x180037414  lea     rcx, [rsp+0F8h+var_80]
0x180037419  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003741e  mov     eax, 80070490h
0x180037423  jmp     loc_1800379FE
0x180037428  mov     [rsp+0F8h+var_C8], rsi
0x18003742d  mov     [rsp+0F8h+var_48], rsi
0x180037435  mov     r9d, 2Ch ; ','; unsigned int
0x18003743b  lea     r8d, [r9+1]; unsigned int
0x18003743f  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180037446  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x18003744e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180037453  lea     rdx, [rsp+0F8h+var_C8]
0x180037458  mov     rcx, [rsp+0F8h+var_48]
0x180037460  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x180037465  mov     edi, eax
0x180037467  test    eax, eax
0x180037469  jns     short loc_1800374A4
0x18003746b  mov     rcx, [rsp+0F8h]; this
0x180037473  mov     r9d, eax; char *
0x180037476  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003747d  mov     edx, 1BCh; void *
0x180037482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037487  nop
0x180037488  lea     rcx, [rsp+0F8h+var_C8]
0x18003748d  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x180037492  nop
0x180037493  lea     rcx, [rsp+0F8h+var_80]
0x180037498  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003749d  mov     eax, edi
0x18003749f  jmp     loc_1800379FE
0x1800374a4  mov     [rsp+0F8h+var_D0], rsi
0x1800374a9  mov     rdi, [rsp+0F8h+var_C8]
0x1800374ae  mov     rax, [rdi]
0x1800374b1  mov     rsi, [rax+88h]
0x1800374b8  lea     rcx, [rsp+0F8h+var_D0]
0x1800374bd  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800374c2  cmp     qword ptr [rbx+18h], 7
0x1800374c7  jbe     short loc_1800374CC
0x1800374c9  mov     rbx, [rbx]
0x1800374cc  mov     [rsp+0F8h+var_90], rbx
0x1800374d1  lea     rdx, [rsp+0F8h+var_90]
0x1800374d6  lea     rcx, [rsp+0F8h+hstringHeader]
0x1800374de  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800374e3  nop
0x1800374e4  lea     r8, [rsp+0F8h+var_D0]
0x1800374e9  mov     rdx, [rax+18h]
0x1800374ed  mov     rcx, rdi
0x1800374f0  mov     rax, rsi
0x1800374f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374f8  mov     ebx, eax
0x1800374fa  test    eax, eax
0x1800374fc  jns     short loc_180037542
0x1800374fe  mov     rcx, [rsp+0F8h]; this
0x180037506  mov     r9d, eax; char *
0x180037509  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180037510  mov     edx, 1BFh; void *
0x180037515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003751a  nop
0x18003751b  lea     rcx, [rsp+0F8h+var_D0]
0x180037520  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x180037525  nop
0x180037526  lea     rcx, [rsp+0F8h+var_C8]
0x18003752b  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x180037530  nop
0x180037531  lea     rcx, [rsp+0F8h+var_80]
0x180037536  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003753b  mov     eax, ebx
0x18003753d  jmp     loc_1800379FE
0x180037542  mov     rbx, [rsp+0F8h+var_D0]
0x180037547  test    rbx, rbx
0x18003754a  jnz     short loc_180037596
0x18003754c  mov     rcx, [rsp+0F8h]; this
0x180037554  mov     r9d, 80070490h; char *
0x18003755a  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180037561  mov     edx, 1C0h; void *
0x180037566  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003756b  nop
0x18003756c  lea     rcx, [rsp+0F8h+var_D0]
0x180037571  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x180037576  nop
0x180037577  lea     rcx, [rsp+0F8h+var_C8]
0x18003757c  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x180037581  nop
0x180037582  lea     rcx, [rsp+0F8h+var_80]
0x180037587  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003758c  mov     eax, 80070490h
0x180037591  jmp     loc_1800379FE
0x180037596  mov     [rsp+0F8h+var_C0], 0
0x18003759f  mov     rax, [rbx]
0x1800375a2  mov     rdi, [rax]
0x1800375a5  lea     rcx, [rsp+0F8h+var_C0]
0x1800375aa  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800375af  lea     r8, [rsp+0F8h+var_C0]
0x1800375b4  lea     rdx, _GUID_65aed1ae_b95b_450c_882b_6255187f397e
0x1800375bb  mov     rcx, rbx
0x1800375be  mov     rax, rdi
0x1800375c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375c6  mov     ebx, eax
0x1800375c8  xor     edi, edi
0x1800375ca  test    eax, eax
0x1800375cc  jns     short loc_18003761D
0x1800375ce  mov     rcx, [rsp+0F8h]; this
0x1800375d6  mov     r9d, eax; char *
0x1800375d9  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800375e0  mov     edx, 1C3h; void *
0x1800375e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800375ea  nop
0x1800375eb  lea     rcx, [rsp+0F8h+var_C0]
0x1800375f0  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800375f5  nop
0x1800375f6  lea     rcx, [rsp+0F8h+var_D0]
0x1800375fb  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x180037600  nop
0x180037601  lea     rcx, [rsp+0F8h+var_C8]
0x180037606  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18003760b  nop
0x18003760c  lea     rcx, [rsp+0F8h+var_80]
0x180037611  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037616  mov     eax, ebx
0x180037618  jmp     loc_1800379FE
0x18003761d  mov     [rsp+0F8h+var_B8], edi
0x180037621  mov     rcx, [rsp+0F8h+var_C0]
0x180037626  mov     rax, [rcx]
0x180037629  lea     rdx, [rsp+0F8h+var_B8]
0x18003762e  mov     rax, [rax+30h]
0x180037632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037637  mov     qword ptr [rsp+0F8h+var_D8], rdi; int
0x18003763c  mov     rcx, [rsp+0F8h+var_D0]
0x180037641  mov     rax, [rcx]
0x180037644  lea     rdx, [rsp+0F8h+var_D8]
0x180037649  mov     rax, [rax+30h]
0x18003764d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037652  mov     ebx, eax
0x180037654  test    eax, eax
0x180037656  jns     short loc_1800376C3
0x180037658  mov     rcx, [rsp+0F8h]; this
0x180037660  mov     r9d, eax; char *
0x180037663  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003766a  mov     edx, 1C8h; void *
0x18003766f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037674  nop
0x180037675  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x18003767a  test    rcx, rcx
0x18003767d  jz      short loc_180037691
0x18003767f  mov     qword ptr [rsp+0F8h+var_D8], rdi
0x180037684  mov     rax, [rcx]
0x180037687  mov     rax, [rax+10h]
0x18003768b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037690  nop
0x180037691  lea     rcx, [rsp+0F8h+var_C0]
0x180037696  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18003769b  nop
0x18003769c  lea     rcx, [rsp+0F8h+var_D0]
0x1800376a1  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800376a6  nop
0x1800376a7  lea     rcx, [rsp+0F8h+var_C8]
0x1800376ac  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800376b1  nop
0x1800376b2  lea     rcx, [rsp+0F8h+var_80]
0x1800376b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800376bc  mov     eax, ebx
0x1800376be  jmp     loc_1800379FE
0x1800376c3  mov     [rsp+0F8h+string], rdi
0x1800376c8  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x1800376cd  mov     rax, [rcx]
0x1800376d0  lea     rdx, [rsp+0F8h+string]
0x1800376d5  mov     rax, [rax+68h]
0x1800376d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376de  mov     ebx, eax
0x1800376e0  test    eax, eax
0x1800376e2  jns     short loc_18003774F
0x1800376e4  mov     rcx, [rsp+0F8h]; this
0x1800376ec  mov     r9d, eax; char *
0x1800376ef  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800376f6  mov     edx, 1CBh; void *
0x1800376fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037700  nop
0x180037701  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x180037706  test    rcx, rcx
0x180037709  jz      short loc_18003771D
0x18003770b  mov     qword ptr [rsp+0F8h+var_D8], rdi
0x180037710  mov     rax, [rcx]
0x180037713  mov     rax, [rax+10h]
0x180037717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003771c  nop
0x18003771d  lea     rcx, [rsp+0F8h+var_C0]
0x180037722  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x180037727  nop
0x180037728  lea     rcx, [rsp+0F8h+var_D0]
0x18003772d  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x180037732  nop
0x180037733  lea     rcx, [rsp+0F8h+var_C8]
0x180037738  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18003773d  nop
0x18003773e  lea     rcx, [rsp+0F8h+var_80]
0x180037743  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037748  mov     eax, ebx
0x18003774a  jmp     loc_1800379FE
0x18003774f  xor     edx, edx; length
0x180037751  mov     rcx, [rsp+0F8h+string]; string
0x180037756  call    cs:__imp_WindowsGetStringRawBuffer
0x18003775c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180037760  mov     r8, rsi
0x180037763  inc     r8
0x180037766  cmp     [rax+r8*2], di
0x18003776b  jnz     short loc_180037763
0x18003776d  mov     rdx, rax
0x180037770  mov     rcx, r14
0x180037773  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180037778  mov     [rsp+0F8h+var_A0], rdi
0x18003777d  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x180037782  mov     rax, [rcx]
0x180037785  lea     rdx, [rsp+0F8h+var_A0]
0x18003778a  mov     rax, [rax+58h]
0x18003778e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037793  mov     ebx, eax
0x180037795  test    eax, eax
0x180037797  jns     short loc_180037804
0x180037799  mov     rcx, [rsp+0F8h]; this
0x1800377a1  mov     r9d, eax; char *
0x1800377a4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800377ab  mov     edx, 1CFh; void *
0x1800377b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800377b5  nop
0x1800377b6  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x1800377bb  test    rcx, rcx
0x1800377be  jz      short loc_1800377D2
0x1800377c0  mov     qword ptr [rsp+0F8h+var_D8], rdi
0x1800377c5  mov     rax, [rcx]
0x1800377c8  mov     rax, [rax+10h]
0x1800377cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377d1  nop
0x1800377d2  lea     rcx, [rsp+0F8h+var_C0]
0x1800377d7  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800377dc  nop
0x1800377dd  lea     rcx, [rsp+0F8h+var_D0]
0x1800377e2  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800377e7  nop
0x1800377e8  lea     rcx, [rsp+0F8h+var_C8]
0x1800377ed  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800377f2  nop
0x1800377f3  lea     rcx, [rsp+0F8h+var_80]
0x1800377f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800377fd  mov     eax, ebx
0x1800377ff  jmp     loc_1800379FE
0x180037804  xor     edx, edx; length
0x180037806  mov     rcx, [rsp+0F8h+var_A0]; string
0x18003780b  call    cs:__imp_WindowsGetStringRawBuffer
0x180037811  mov     r8, rsi
0x180037814  inc     r8
0x180037817  cmp     [rax+r8*2], di
0x18003781c  jnz     short loc_180037814
0x18003781e  mov     rdx, rax
0x180037821  mov     rcx, r13
0x180037824  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180037829  mov     [rsp+0F8h+var_B0], rdi
0x18003782e  mov     rbx, [rsp+0F8h+var_D0]
0x180037833  mov     rax, [rbx]
0x180037836  mov     rdi, [rax]
0x180037839  lea     rcx, [rsp+0F8h+var_B0]
0x18003783e  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
  ... truncated ...
```
