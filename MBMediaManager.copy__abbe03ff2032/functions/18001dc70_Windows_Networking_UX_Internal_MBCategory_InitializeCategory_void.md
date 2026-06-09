# Windows::Networking::UX::Internal::MBCategory::_InitializeCategory(void)

- ea: `0x18001dc70`
- end: `0x18001e61e`
- name: `?_InitializeCategory@MBCategory@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `2478`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this)`
- caller_count: `1`
- callee_count: `50`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800434d0`

## callees

- `0x180001e24`
- `0x180002150`
- `0x180005fc0`
- `0x180008c84`
- `0x180009150`
- `0x180009f08`
- `0x18000ad20`
- `0x18000bde0`
- `0x18000c50c`
- `0x18000c6ac`
- `0x18000c724`
- `0x18000c890`
- `0x18000cc50`
- `0x18000d8d0`
- `0x18000dc54`
- `0x18000e02c`
- `0x18000e26c`
- `0x18000e3e8`
- `0x18000ea3c`
- `0x18000ead4`
- `0x18000efa4`
- `0x180011450`
- `0x1800116e0`
- `0x180011be0`
- `0x1800132cc`
- `0x1800148b8`
- `0x1800164ec`
- `0x180017ac4`
- `0x180017e08`
- `0x1800187e4`
- `0x1800189c4`
- `0x18001a14c`
- `0x18001a864`
- `0x18001ac24`
- `0x18001accc`
- `0x18001b1d4`
- `0x18001bdb8`
- `0x18001bfa8`
- `0x18001dc70`
- `0x18001f34c`
- `0x18001f5b8`
- `0x18001f7ec`
- `0x18002381c`
- `0x180023b84`
- `0x1800242fc`
- `0x1800262d0`
- `0x18002cd20`
- `0x18003a1c4`
- `0x18003a220`
- `0x18003a27c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e37e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e4ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e4d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e37e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e4ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e4d8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001e5ba`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001e5ba`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001dce8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001dce8`

## string_xrefs

- `0x18001deec`: `old _wwanDataClasses=%d, new _wwanDataClasses=%d`
- `0x18001def8`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateRadioAccessCapabilities`
- `0x18001dfcc`: `DeviceObject data updated. _wwanDataClasses=%d, _cellularClass=%d, _customDataClassName=%ls`
- `0x18001e1cf`: `ReadyObject data updated. _selectedSlot=%d, _readyState=%d, _iccId=%ls, _subscriberId=%ls, _telephoneNumber=%ls`
- `0x18001e572`: `Completed InitCategory. interfaceGuid=%hs, Connectivity=%d, BlockedReason=%d, ActionRequiredReason=%d, fAutoConnect=%hs, IsRoaming=%hs, Name=%ls, BrandingIconPath=%ls`
- `0x18001df94`: `Failed to cache Adapter Properties`
- `0x18001dff2`: `MBCategory::_InitializeCategory  DeviceObject is not ready`
- `0x18001e039`: `RadioObject data updated. _radioPowerState=%d`
- `0x18001e05d`: `MBCategory::_InitializeCategory RadioObject is not ready`
- `0x18001e08a`: `SignalObject data updated. _uSignalBars=%d`
- `0x18001e1f3`: `MBCategory::_InitializeCategory ReadyObject is not ready`
- `0x18001e257`: `PacketObject data updated. _currentDataClass=%d, _strName=%ls, _availableDataClasses=%d`
- `0x18001e27d`: `MBCategory::_InitializeCategory PacketObject is not ready.`
- `0x18001e3dc`: `RegisterObject data updated. ulNetworkError=%d, registerState=%d, _fIsRoaming=%hs, registerMode=%d, ProviderName=%ls, ProviderId=%ls, _availableDataClasses=%d`
- `0x18001e412`: `ContextObject data updated. _activationState=%d`
- `0x18001e428`: `ContextObject is not ready. status=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::_InitializeCategory(
        Windows::Networking::UX::Internal::MBCategory *this)
{
  Windows::Networking::UX::Internal::MBCategory *v1; // r13
  unsigned int v2; // eax
  int WwanInterfaceObject; // ebx
  bool v5; // dl
  int v6; // eax
  HSTRING *v7; // rdi
  __int64 v8; // rdx
  unsigned int v9; // eax
  int v10; // ebx
  int *v11; // r15
  __int64 v12; // rbx
  const wchar_t *v13; // rax
  Windows::Networking::UX::Internal::MBCategory *v14; // rcx
  unsigned int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rdx
  Windows::Networking::UX::Internal::MBCategory *v18; // rcx
  unsigned int v19; // eax
  Windows::Networking::UX::Internal::MBCategory *v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // edx
  __int64 v23; // rcx
  unsigned int ready; // eax
  unsigned __int64 v25; // rcx
  const wchar_t *v26; // rcx
  const wchar_t *v27; // rdx
  const wchar_t *v28; // rax
  Windows::Networking::UX::Internal::MBCategory *v29; // rcx
  unsigned int v30; // eax
  int v31; // ebx
  const wchar_t *StringRawBuffer; // rax
  int v33; // edi
  const wchar_t *v34; // rbx
  const wchar_t *v35; // rax
  const char *v36; // rcx
  int v37; // r9d
  int v38; // r9d
  bool v39; // dl
  int v40; // eax
  HSTRING *v41; // rbx
  bool v42; // dl
  const wchar_t *v43; // r12
  const wchar_t *v44; // r15
  const char *v45; // rax
  const char *v46; // r14
  int v47; // ebx
  int v48; // edi
  int v49; // esi
  __int64 v50; // rax
  __int64 v51; // rcx
  unsigned int v52; // [rsp+20h] [rbp-208h]
  __int64 v53; // [rsp+60h] [rbp-1C8h] BYREF
  Windows::Networking::UX::Internal::MBCategory *v54; // [rsp+68h] [rbp-1C0h] BYREF
  int v55; // [rsp+70h] [rbp-1B8h] BYREF
  const char *v56; // [rsp+78h] [rbp-1B0h]
  unsigned __int16 *v57; // [rsp+80h] [rbp-1A8h] BYREF
  __int64 v58; // [rsp+88h] [rbp-1A0h]
  __int64 v59; // [rsp+90h] [rbp-198h]
  unsigned __int16 *v60; // [rsp+98h] [rbp-190h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-188h]
  __int64 v62; // [rsp+A8h] [rbp-180h]
  int *v63; // [rsp+B0h] [rbp-178h]
  _OWORD v64[13]; // [rsp+C0h] [rbp-168h] BYREF
  int v65; // [rsp+190h] [rbp-98h]
  struct WWAN_INTERFACE_OBJECT *v66[2]; // [rsp+1A0h] [rbp-88h] BYREF
  _BYTE v67[19]; // [rsp+1B0h] [rbp-78h]
  char v68[2]; // [rsp+1C8h] [rbp-60h] BYREF
  __int16 v69; // [rsp+1F4h] [rbp-34h]
  Windows::Networking::UX::Internal::MBCategory *retaddr; // [rsp+228h] [rbp+0h]

  v1 = this;
  v54 = this;
  MBSettingUXLogging::Info("Windows::Networking::UX::Internal::MBCategory::_InitializeCategory", 0x49u, "Enter");
  v55 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset((char *)v1 + 304);
  v2 = WwanOpenHandle(1, 0, &v55, (char *)v1 + 304);
  if ( v2 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x4B,
             (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
             (const char *)v2,
             v52);
  v53 = 0;
  v66[0] = (struct WWAN_INTERFACE_OBJECT *)&v53;
  v66[1] = 0;
  v67[0] = 1;
  WwanInterfaceObject = Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(v1, &v66[1]);
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(v66);
  if ( WwanInterfaceObject < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)WwanInterfaceObject,
      v52);
LABEL_5:
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
      0xF7u,
      "Failed to do GetWwanInterfaceObject");
    goto LABEL_6;
  }
  v8 = v53;
  if ( !v53 )
    goto LABEL_5;
  v9 = *(_DWORD *)(v53 + 904);
  if ( v9 )
  {
    LODWORD(v54) = Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(retaddr, v9);
    MBSettingUXLogging::WarnHRESULT<char const (&)[59],long>(
      "MBCategory::_InitializeCategory  DeviceObject is not ready",
      &v54);
  }
  else
  {
    v56 = (char *)v1 + 664;
    *((_DWORD *)v1 + 166) = *(_DWORD *)(v53 + 556);
    v10 = *(_DWORD *)(v8 + 568);
    v11 = (int *)((char *)v1 + 668);
    v63 = (int *)((char *)v1 + 668);
    if ( *((_DWORD *)v1 + 167) != v10 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateRadioAccessCapabilities",
        0xEF6u,
        "old _wwanDataClasses=%d, new _wwanDataClasses=%d",
        *v11,
        v10);
      *v11 = v10;
      Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(v1, 14);
      v8 = v53;
    }
    try
    {
      std::wstring::wstring(v66, v8 + 572);
      Windows::Networking::UX::Internal::MBCategory::tp_UpdateCustomDataClassName(v1, v66);
      std::wstring::_Tidy_deallocate(v66);
    }
    catch ( ... )
    {
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
        0x5Fu,
        "Failed to cache the CustomDataClass name. CustomDataClass=%ls",
        (const wchar_t *)(v53 + 572));
      v1 = v54;
      v11 = v63;
    }
    v12 = v53;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v1 + 704);
    if ( (int)Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::MBAdapterProperties,Windows::Networking::UX::IMBAdapterProperties,_GUID &,_WWAN_DEVICE_CAPS &>(
                (char *)v1 + 704,
                (char *)v1 + 24,
                v12 + 552) < 0 )
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
        0x64u,
        "Failed to cache Adapter Properties");
    v13 = (const wchar_t *)((char *)v1 + 672);
    if ( *((_QWORD *)v1 + 87) > 7u )
      v13 = *(const wchar_t **)v13;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
      0x6Cu,
      "DeviceObject data updated. _wwanDataClasses=%d, _cellularClass=%d, _customDataClassName=%ls",
      *v11,
      *(_DWORD *)v56,
      v13);
  }
  v15 = *(_DWORD *)(v53 + 1044);
  if ( v15 )
  {
    LODWORD(v54) = Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(v14, v15);
    MBSettingUXLogging::WarnHRESULT<char const (&)[57],long>(
      "MBCategory::_InitializeCategory RadioObject is not ready",
      &v54);
  }
  else
  {
    v16 = *(_QWORD *)(v53 + 1036);
    if ( !(_DWORD)v16 || (v17 = 2, !HIDWORD(v16)) )
      v17 = 1;
    Windows::Networking::UX::Internal::MBCategory::tp_UpdateRadioState(v1, v17);
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
      0x80u,
      "RadioObject data updated. _radioPowerState=%d",
      *((_DWORD *)v1 + 150));
  }
  v19 = *(_DWORD *)(v53 + 1284);
  if ( v19 )
  {
    LODWORD(v54) = Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(v18, v19);
    MBSettingUXLogging::WarnHRESULT<char const (&)[58],long>(v21, &v54);
  }
  else
  {
    Windows::Networking::UX::Internal::MBCategory::tp_UpdateSignalBars(v1, *(_DWORD *)(v53 + 1236));
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
      0x8Eu,
      "SignalObject data updated. _uSignalBars=%d",
      *((_DWORD *)v1 + 15));
  }
  v22 = *(_DWORD *)(v53 + 1024);
  if ( v22 )
  {
    LODWORD(v54) = Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(v20, v22);
    MBSettingUXLogging::WarnHRESULT<char const (&)[57],long>(
      "MBCategory::_InitializeCategory ReadyObject is not ready",
      &v54);
  }
  else
  {
    Windows::Networking::UX::Internal::MBCategory::tp_UpdateIccId(v1, (const unsigned __int16 *)(v53 + 952));
    Windows::Networking::UX::Internal::MBCategory::tp_UpdateSubscriberId(v1, (const unsigned __int16 *)(v53 + 920));
    ready = Windows::Networking::UX::Internal::MBCategory::_MbReadyStateFromWwanReadyState(
              v23,
              *(unsigned int *)(v53 + 912));
    Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState(v1, ready);
    Windows::Networking::UX::Internal::MBCategory::tp_RefreshProfiles(v1);
    if ( *(_WORD *)(v53 + 952) )
    {
      if ( !*(_DWORD *)(v53 + 1004) )
      {
        if ( *(_DWORD *)(v53 + 1008) )
        {
          v25 = *(_QWORD *)(v53 + 1016);
          if ( v25 )
          {
            *(_QWORD *)(v53 + 1016) = v53 + 2 * (v25 >> 1);
            StringCchCopyW((unsigned __int16 *)v68, 0x17u, *(const unsigned __int16 **)(v53 + 1016));
            v69 = 0;
            Windows::Networking::UX::Internal::MBCategory::tp_UpdatePhoneNumber(v1, (const unsigned __int16 *)v68);
          }
        }
      }
    }
    v26 = (const wchar_t *)((char *)v1 + 432);
    if ( *((_QWORD *)v1 + 57) > 7u )
      v26 = *(const wchar_t **)v26;
    v27 = (const wchar_t *)((char *)v1 + 400);
    if ( *((_QWORD *)v1 + 53) > 7u )
      v27 = *(const wchar_t **)v27;
    v28 = (const wchar_t *)((char *)v1 + 368);
    if ( *((_QWORD *)v1 + 49) > 7u )
      v28 = *(const wchar_t **)v28;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
      0xB7u,
      "ReadyObject data updated. _selectedSlot=%d, _readyState=%d, _iccId=%ls, _subscriberId=%ls, _telephoneNumber=%ls",
      *((_DWORD *)v1 + 118),
      *((_DWORD *)v1 + 151),
      v28,
      v27,
      v26);
  }
  v30 = *(_DWORD *)(v53 + 1688);
  if ( v30 )
  {
    LODWORD(v54) = Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(v29, v30);
    MBSettingUXLogging::WarnHRESULT<char const (&)[59],long>(
      "MBCategory::_InitializeCategory PacketObject is not ready.",
      &v54);
  }
  else
  {
    Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo(
      (HSTRING *)v1,
      *(_DWORD *)(v53 + 1664),
      *(_DWORD *)(v53 + 1660),
      *(_DWORD *)(v53 + 1672),
      *(_DWORD *)(v53 + 1668));
    v31 = *((_DWORD *)v1 + 154);
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v1 + 5), 0);
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
      0xD3u,
      "PacketObject data updated. _currentDataClass=%d, _strName=%ls, _availableDataClasses=%d",
      *((_DWORD *)v1 + 153),
      StringRawBuffer,
      v31);
  }
  v64[0] = *(_OWORD *)(v53 + 1440);
  v64[1] = *(_OWORD *)(v53 + 1456);
  v64[2] = *(_OWORD *)(v53 + 1472);
  v64[3] = *(_OWORD *)(v53 + 1488);
  v64[4] = *(_OWORD *)(v53 + 1504);
  v64[5] = *(_OWORD *)(v53 + 1520);
  v64[6] = *(_OWORD *)(v53 + 1536);
  v64[7] = *(_OWORD *)(v53 + 1552);
  v64[8] = *(_OWORD *)(v53 + 1568);
  v64[9] = *(_OWORD *)(v53 + 1584);
  v64[10] = *(_OWORD *)(v53 + 1600);
  v64[11] = *(_OWORD *)(v53 + 1616);
  v64[12] = *(_OWORD *)(v53 + 1632);
  v65 = *(_DWORD *)(v53 + 1648);
  Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration((__int64)v1, (__int64)v64);
  v33 = *((_DWORD *)v1 + 154);
  v34 = WindowsGetStringRawBuffer(*((HSTRING *)v1 + 92), 0);
  v35 = WindowsGetStringRawBuffer(*((HSTRING *)v1 + 91), 0);
  v36 = "true";
  if ( !*((_BYTE *)v1 + 88) )
    v36 = "false";
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
    0xE8u,
    "RegisterObject data updated. ulNetworkError=%d, registerState=%d, _fIsRoaming=%hs, registerMode=%d, ProviderName=%ls"
    ", ProviderId=%ls, _availableDataClasses=%d",
    *((_DWORD *)v1 + 186),
    *((_DWORD *)v1 + 180),
    v36,
    *((_DWORD *)v1 + 181),
    v35,
    v34,
    v33);
  v37 = *(_DWORD *)(v53 + 1948);
  if ( v37 )
  {
    MBSettingUXLogging::Warn(
      "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
      0xF2u,
      "ContextObject is not ready. status=0x%x",
      v37);
  }
  else
  {
    v38 = *(_DWORD *)(v53 + 1700);
    *((_DWORD *)v1 + 208) = v38;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
      0xEEu,
      "ContextObject data updated. _activationState=%d",
      v38);
  }
LABEL_6:
  Windows::Networking::UX::Internal::MBCategory::tp_GetEnterpriseParams(v1);
  Windows::Networking::UX::Internal::MBCategory::tp_GetModemOptionalFeatures(v1);
  Windows::Networking::UX::Internal::MBCategory::tp_GetMultiSimInfo(v1);
  Windows::Networking::UX::Internal::MBCategory::tp_GetRoamingPreference(v1);
  Windows::Networking::UX::Internal::MBCategory::tp_GetDataEnablement(v1);
  Windows::Networking::UX::Internal::MBCategory::tp_GetAutoconnectEnabled(v1);
  Windows::Networking::UX::Internal::MBCategory::tp_GetProvisioningState(v1);
  Windows::Networking::UX::Internal::MBCategory::tp_GetLTEAttachInfo(v1);
  Windows::Networking::UX::Internal::MBCategory::tp_GetConnectionIStream(v1);
  if ( *((_DWORD *)v1 + 117) > 1u )
    Windows::Networking::UX::Internal::MBCategory::tp_GetMultiSimSlotMapping(v1);
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
    &v60,
    &sourceString,
    -1);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
    &v57,
    &sourceString,
    -1);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v60);
  v61 = -1;
  v62 = -1;
  v6 = Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName(v1, v5, &v60);
  if ( v6 >= 0 )
  {
    v7 = (HSTRING *)((char *)v1 + 40);
    Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>((HSTRING *)v1 + 5);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)v6,
      v52);
    v7 = (HSTRING *)((char *)v1 + 40);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
  v58 = -1;
  v59 = -1;
  v40 = Windows::Networking::UX::Internal::MBCategory::_CalculateBrandingIconPath(v1, v39, &v57);
  if ( v40 >= 0 )
  {
    if ( !(unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(&v57) )
    {
      v41 = (HSTRING *)((char *)v1 + 64);
      Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>((HSTRING *)v1 + 8);
      goto LABEL_55;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)v40,
      v52);
  }
  v41 = (HSTRING *)((char *)v1 + 64);
  Microsoft::WRL::Wrappers::HString::Set(
    (Windows::Networking::UX::Internal::MBCategory *)((char *)v1 + 64),
    &sourceString,
    0);
LABEL_55:
  Windows::Networking::UX::Internal::MBCategory::_CalculateConnectivity(v1, v42);
  *((_BYTE *)v1 + 300) = 1;
  v43 = WindowsGetStringRawBuffer(*v41, 0);
  v44 = WindowsGetStringRawBuffer(*v7, 0);
  v45 = "true";
  v46 = "true";
  if ( !*((_BYTE *)v1 + 88) )
    v46 = "false";
  if ( !*((_BYTE *)v1 + 90) )
    v45 = "false";
  v56 = v45;
  v47 = *((_DWORD *)v1 + 20);
  v48 = *((_DWORD *)v1 + 19);
  v49 = *((_DWORD *)v1 + 18);
  v50 = MbLoggingHelperGuidToString(v68);
  *(_OWORD *)v66 = *(_OWORD *)v50;
  *(_OWORD *)v67 = *(_OWORD *)(v50 + 16);
  *(_DWORD *)&v67[15] = *(_DWORD *)(v50 + 31);
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBCategory::_InitializeCategory",
    0x12Eu,
    "Completed InitCategory. interfaceGuid=%hs, Connectivity=%d, BlockedReason=%d, ActionRequiredReason=%d, fAutoConnect="
    "%hs, IsRoaming=%hs, Name=%ls, BrandingIconPath=%ls",
    (const char *)v66,
    v49,
    v48,
    v47,
    v56,
    v46,
    v44,
    v43);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v60);
  v51 = v53;
  v53 = 0;
  if ( v51 )
    WwanFreeMemory(v51);
  return 0;
}

```

## disassembly

```asm
0x18001dc70  mov     [rsp+arg_8], rbx
0x18001dc75  mov     [rsp+arg_10], rsi
0x18001dc7a  push    rdi
0x18001dc7b  push    r12
0x18001dc7d  push    r13
0x18001dc7f  push    r14
0x18001dc81  push    r15
0x18001dc83  sub     rsp, 200h
0x18001dc8a  mov     rax, cs:__security_cookie
0x18001dc91  xor     rax, rsp
0x18001dc94  mov     [rsp+228h+var_30], rax
0x18001dc9c  mov     r13, rcx
0x18001dc9f  mov     [rsp+228h+var_1C0], rcx
0x18001dca4  lea     r8, aEnter; "Enter"
0x18001dcab  mov     edx, 49h ; 'I'; unsigned int
0x18001dcb0  lea     r14, aWindowsNetwork_5; "Windows::Networking::UX::Internal::MBCa"...
0x18001dcb7  mov     rcx, r14; char *
0x18001dcba  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001dcbf  xor     esi, esi
0x18001dcc1  mov     [rsp+228h+var_1B8], esi
0x18001dcc5  lea     rbx, [r13+130h]
0x18001dccc  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001dcd0  mov     rdx, r12
0x18001dcd3  mov     rcx, rbx
0x18001dcd6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(void *)
0x18001dcdb  mov     r9, rbx
0x18001dcde  lea     r8, [rsp+228h+var_1B8]
0x18001dce3  xor     edx, edx
0x18001dce5  lea     ecx, [rsi+1]
0x18001dce8  call    cs:__imp_WwanOpenHandle
0x18001dcee  test    eax, eax
0x18001dcf0  jz      short loc_18001DD11
0x18001dcf2  mov     rcx, [rsp+228h]; this
0x18001dcfa  mov     r9d, eax; char *
0x18001dcfd  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001dd04  lea     edx, [rsi+4Bh]; void *
0x18001dd07  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001dd0c  jmp     loc_18001E5C2
0x18001dd11  mov     [rsp+228h+var_1C8], rsi
0x18001dd16  lea     rax, [rsp+228h+var_1C8]
0x18001dd1b  mov     [rsp+228h+var_88], rax
0x18001dd23  mov     [rsp+228h+var_88+8], rsi
0x18001dd2b  mov     [rsp+228h+var_78], 1
0x18001dd33  lea     rdx, [rsp+228h+var_88+8]; struct WWAN_INTERFACE_OBJECT **
0x18001dd3b  mov     rcx, r13; this
0x18001dd3e  call    ?_GetWwanInterfaceObject@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEAPEAUWWAN_INTERFACE_OBJECT@@@Z; Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(WWAN_INTERFACE_OBJECT * *)
0x18001dd43  mov     ebx, eax
0x18001dd45  lea     rcx, [rsp+228h+var_88]
0x18001dd4d  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18001dd52  mov     rcx, [rsp+228h]; this
0x18001dd5a  test    ebx, ebx
0x18001dd5c  jns     loc_18001DE9B
0x18001dd62  mov     r9d, ebx; char *
0x18001dd65  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001dd6c  mov     edx, 4Fh ; 'O'; void *
0x18001dd71  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dd76  lea     r8, aFailedToDoGetw; "Failed to do GetWwanInterfaceObject"
0x18001dd7d  mov     edx, 0F7h; unsigned int
0x18001dd82  mov     rcx, r14; char *
0x18001dd85  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18001dd8a  mov     rcx, r13; this
0x18001dd8d  call    ?tp_GetEnterpriseParams@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetEnterpriseParams(void)
0x18001dd92  mov     rcx, r13; this
0x18001dd95  call    ?tp_GetModemOptionalFeatures@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetModemOptionalFeatures(void)
0x18001dd9a  mov     rcx, r13; this
0x18001dd9d  call    ?tp_GetMultiSimInfo@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetMultiSimInfo(void)
0x18001dda2  mov     rcx, r13; this
0x18001dda5  call    ?tp_GetRoamingPreference@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetRoamingPreference(void)
0x18001ddaa  mov     rcx, r13; this
0x18001ddad  call    ?tp_GetDataEnablement@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetDataEnablement(void)
0x18001ddb2  mov     rcx, r13; this
0x18001ddb5  call    ?tp_GetAutoconnectEnabled@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetAutoconnectEnabled(void)
0x18001ddba  mov     rcx, r13; this
0x18001ddbd  call    ?tp_GetProvisioningState@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetProvisioningState(void)
0x18001ddc2  mov     rcx, r13; this
0x18001ddc5  call    ?tp_GetLTEAttachInfo@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetLTEAttachInfo(void)
0x18001ddca  mov     rcx, r13; this
0x18001ddcd  call    ?tp_GetConnectionIStream@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetConnectionIStream(void)
0x18001ddd2  cmp     dword ptr [r13+1D4h], 1
0x18001ddda  jbe     short loc_18001DDE4
0x18001dddc  mov     rcx, r13; this
0x18001dddf  call    ?tp_GetMultiSimSlotMapping@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetMultiSimSlotMapping(void)
0x18001dde4  mov     [rsp+228h+var_190], rsi
0x18001ddec  mov     [rsp+228h+var_188], rsi
0x18001ddf4  mov     [rsp+228h+var_180], rsi
0x18001ddfc  mov     [rsp+228h+var_1A8], rsi
0x18001de04  mov     [rsp+228h+var_1A0], rsi
0x18001de0c  mov     [rsp+228h+var_198], rsi
0x18001de14  mov     r8, r12
0x18001de17  lea     r14, sourceString
0x18001de1e  mov     rdx, r14
0x18001de21  lea     rcx, [rsp+228h+var_190]
0x18001de29  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001de2e  mov     r8, r12
0x18001de31  mov     rdx, r14
0x18001de34  lea     rcx, [rsp+228h+var_1A8]
0x18001de3c  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001de41  lea     rcx, [rsp+228h+var_190]
0x18001de49  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001de4e  mov     [rsp+228h+var_188], r12
0x18001de56  mov     [rsp+228h+var_180], r12
0x18001de5e  lea     r8, [rsp+228h+var_190]; unsigned __int16 **
0x18001de66  mov     rcx, r13; this
0x18001de69  call    ?_CalculateCategoryName@MBCategory@Internal@UX@Networking@Windows@@AEAAJ_NPEAPEAG@Z; Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName(bool,ushort * *)
0x18001de6e  mov     rcx, [rsp+228h]; this
0x18001de76  test    eax, eax
0x18001de78  jns     loc_18001E43E
0x18001de7e  mov     r9d, eax; char *
0x18001de81  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001de88  mov     edx, 112h; void *
0x18001de8d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001de92  lea     rdi, [r13+28h]
0x18001de96  jmp     loc_18001E452
0x18001de9b  mov     rdx, [rsp+228h+var_1C8]
0x18001dea0  test    rdx, rdx
0x18001dea3  jz      loc_18001DD76
0x18001dea9  mov     eax, [rdx+388h]
0x18001deaf  test    eax, eax
0x18001deb1  jnz     loc_18001DFE2
0x18001deb7  lea     rcx, [r13+298h]
0x18001debe  mov     [rsp+228h+var_1B0], rcx
0x18001dec3  mov     eax, [rdx+22Ch]
0x18001dec9  mov     [rcx], eax
0x18001decb  mov     ebx, [rdx+238h]
0x18001ded1  lea     r15, [r13+29Ch]
0x18001ded8  mov     [rsp+228h+var_178], r15
0x18001dee0  cmp     [r15], ebx
0x18001dee3  jz      short loc_18001DF19
0x18001dee5  mov     dword ptr [rsp+228h+var_208], ebx
0x18001dee9  mov     r9d, [r15]
0x18001deec  lea     r8, aOldWwandatacla; "old _wwanDataClasses=%d, new _wwanDataC"...
0x18001def3  mov     edx, 0EF6h; unsigned int
0x18001def8  lea     rcx, aWindowsNetwork_17; "Windows::Networking::UX::Internal::MBCa"...
0x18001deff  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001df04  mov     [r15], ebx
0x18001df07  mov     edx, 0Eh
0x18001df0c  mov     rcx, r13
0x18001df0f  call    ?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJW4MbInterfaceChangeProperty@345@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Windows::Networking::UX::MbInterfaceChangeProperty)
0x18001df14  mov     rdx, [rsp+228h+var_1C8]
0x18001df19  add     rdx, 23Ch
0x18001df20  lea     rcx, [rsp+228h+var_88]
0x18001df28  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001df2d  nop
0x18001df2e  lea     rdx, [rsp+228h+var_88]
0x18001df36  mov     rcx, r13
0x18001df39  call    ?tp_UpdateCustomDataClassName@MBCategory@Internal@UX@Networking@Windows@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdateCustomDataClassName(std::wstring const &)
0x18001df3e  nop
0x18001df3f  lea     rcx, [rsp+228h+var_88]
0x18001df47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001df4c  nop
0x18001df4d  jmp     short loc_18001DF69
0x18001df4f  lea     r14, aWindowsNetwork_5; "Windows::Networking::UX::Internal::MBCa"...
0x18001df56  xor     esi, esi
0x18001df58  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001df5c  mov     r13, [rsp+228h+var_1C0]
0x18001df61  mov     r15, [rsp+228h+var_178]
0x18001df69  mov     rbx, [rsp+228h+var_1C8]
0x18001df6e  lea     rdi, [r13+2C0h]
0x18001df75  mov     rcx, rdi
0x18001df78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001df7d  lea     rdx, [r13+18h]
0x18001df81  lea     r8, [rbx+228h]
0x18001df88  mov     rcx, rdi
0x18001df8b  call    ??$MakeAndInitialize@VMBAdapterProperties@Internal@UX@Networking@Windows@@UIMBAdapterProperties@345@AEAU_GUID@@AEAU_WWAN_DEVICE_CAPS@@@Details@WRL@Microsoft@@YAJPEAPEAUIMBAdapterProperties@UX@Networking@Windows@@AEAU_GUID@@AEAU_WWAN_DEVICE_CAPS@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::MBAdapterProperties,Windows::Networking::UX::IMBAdapterProperties,_GUID &,_WWAN_DEVICE_CAPS &>(Windows::Networking::UX::IMBAdapterProperties * *,_GUID &,_WWAN_DEVICE_CAPS &)
0x18001df90  test    eax, eax
0x18001df92  jns     short loc_18001DFA8
0x18001df94  lea     r8, aFailedToCacheA; "Failed to cache Adapter Properties"
0x18001df9b  mov     edx, 64h ; 'd'; unsigned int
0x18001dfa0  mov     rcx, r14; char *
0x18001dfa3  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18001dfa8  lea     rax, [r13+2A0h]
0x18001dfaf  cmp     qword ptr [rax+18h], 7
0x18001dfb4  jbe     short loc_18001DFB9
0x18001dfb6  mov     rax, [rax]
0x18001dfb9  mov     [rsp+228h+var_200], rax
0x18001dfbe  mov     rax, [rsp+228h+var_1B0]
0x18001dfc3  mov     eax, [rax]
0x18001dfc5  mov     dword ptr [rsp+228h+var_208], eax
0x18001dfc9  mov     r9d, [r15]
0x18001dfcc  lea     r8, aDeviceobjectDa; "DeviceObject data updated. _wwanDataCla"...
0x18001dfd3  mov     edx, 6Ch ; 'l'; unsigned int
0x18001dfd8  mov     rcx, r14; char *
0x18001dfdb  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001dfe0  jmp     short loc_18001DFFE
0x18001dfe2  mov     edx, eax; unsigned int
0x18001dfe4  call    ?_HResultFromWwanStatus@MBCategory@Internal@UX@Networking@Windows@@AEAAJK@Z; Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(ulong)
0x18001dfe9  mov     dword ptr [rsp+228h+var_1C0], eax
0x18001dfed  lea     rdx, [rsp+228h+var_1C0]
0x18001dff2  lea     rcx, aMbcategoryInit; "MBCategory::_InitializeCategory  Device"...
0x18001dff9  call    ??$WarnHRESULT@AEAY0DL@$$CBDJ@MBSettingUXLogging@@SAXAEAY0DL@$$CBD$$QEAJ@Z; MBSettingUXLogging::WarnHRESULT<char const (&)[59],long>(char const (&)[59],long &&)
0x18001dffe  mov     rax, [rsp+228h+var_1C8]
0x18001e003  mov     edx, [rax+414h]; unsigned int
0x18001e009  test    edx, edx
0x18001e00b  jnz     short loc_18001E04F
0x18001e00d  mov     rax, [rax+40Ch]
0x18001e014  test    eax, eax
0x18001e016  jz      short loc_18001E025
0x18001e018  mov     edx, 2
0x18001e01d  shr     rax, 20h
0x18001e021  test    eax, eax
0x18001e023  jnz     short loc_18001E02A
0x18001e025  mov     edx, 1
0x18001e02a  mov     rcx, r13
0x18001e02d  call    ?tp_UpdateRadioState@MBCategory@Internal@UX@Networking@Windows@@AEAAXW4MbRadioPowerState@345@@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdateRadioState(Windows::Networking::UX::MbRadioPowerState)
0x18001e032  mov     r9d, [r13+258h]
0x18001e039  lea     r8, aRadioobjectDat; "RadioObject data updated. _radioPowerSt"...
0x18001e040  mov     edx, 80h; unsigned int
0x18001e045  mov     rcx, r14; char *
0x18001e048  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001e04d  jmp     short loc_18001E069
0x18001e04f  call    ?_HResultFromWwanStatus@MBCategory@Internal@UX@Networking@Windows@@AEAAJK@Z; Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(ulong)
0x18001e054  mov     dword ptr [rsp+228h+var_1C0], eax
0x18001e058  lea     rdx, [rsp+228h+var_1C0]
0x18001e05d  lea     rcx, aMbcategoryInit_1; "MBCategory::_InitializeCategory RadioOb"...
0x18001e064  call    ??$WarnHRESULT@AEAY0DJ@$$CBDJ@MBSettingUXLogging@@SAXAEAY0DJ@$$CBD$$QEAJ@Z; MBSettingUXLogging::WarnHRESULT<char const (&)[57],long>(char const (&)[57],long &&)
0x18001e069  mov     rdx, [rsp+228h+var_1C8]
0x18001e06e  mov     eax, [rdx+504h]
0x18001e074  test    eax, eax
0x18001e076  jnz     short loc_18001E0A0
0x18001e078  mov     edx, [rdx+4D4h]; unsigned int
0x18001e07e  mov     rcx, r13; this
0x18001e081  call    ?tp_UpdateSignalBars@MBCategory@Internal@UX@Networking@Windows@@AEAAXK@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdateSignalBars(ulong)
0x18001e086  mov     r9d, [r13+3Ch]
0x18001e08a  lea     r8, aSignalobjectDa; "SignalObject data updated. _uSignalBars"...
0x18001e091  mov     edx, 8Eh; unsigned int
0x18001e096  mov     rcx, r14; char *
0x18001e099  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001e09e  jmp     short loc_18001E0B5
0x18001e0a0  mov     edx, eax; unsigned int
0x18001e0a2  call    ?_HResultFromWwanStatus@MBCategory@Internal@UX@Networking@Windows@@AEAAJK@Z; Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(ulong)
0x18001e0a7  mov     dword ptr [rsp+228h+var_1C0], eax
0x18001e0ab  lea     rdx, [rsp+228h+var_1C0]
0x18001e0b0  call    ??$WarnHRESULT@AEAY0DK@$$CBDJ@MBSettingUXLogging@@SAXAEAY0DK@$$CBD$$QEAJ@Z; MBSettingUXLogging::WarnHRESULT<char const (&)[58],long>(char const (&)[58],long &&)
0x18001e0b5  mov     rax, [rsp+228h+var_1C8]
0x18001e0ba  mov     edx, [rax+400h]; unsigned int
0x18001e0c0  test    edx, edx
0x18001e0c2  jnz     loc_18001E1E5
0x18001e0c8  lea     rdx, [rax+3B8h]; unsigned __int16 *
0x18001e0cf  mov     rcx, r13; this
0x18001e0d2  call    ?tp_UpdateIccId@MBCategory@Internal@UX@Networking@Windows@@AEAAXPEBG@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdateIccId(ushort const *)
0x18001e0d7  mov     rdx, [rsp+228h+var_1C8]
0x18001e0dc  add     rdx, 398h; unsigned __int16 *
0x18001e0e3  mov     rcx, r13; this
0x18001e0e6  call    ?tp_UpdateSubscriberId@MBCategory@Internal@UX@Networking@Windows@@AEAAXPEBG@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdateSubscriberId(ushort const *)
0x18001e0eb  mov     rdx, [rsp+228h+var_1C8]
0x18001e0f0  mov     edx, [rdx+390h]
0x18001e0f6  call    ?_MbReadyStateFromWwanReadyState@MBCategory@Internal@UX@Networking@Windows@@AEAA?AW4MbCategoryReadyState@345@W4_WWAN_READY_STATE@@@Z; Windows::Networking::UX::Internal::MBCategory::_MbReadyStateFromWwanReadyState(_WWAN_READY_STATE)
0x18001e0fb  mov     edx, eax
0x18001e0fd  mov     rcx, r13
0x18001e100  call    ?tp_UpdateReadyState@MBCategory@Internal@UX@Networking@Windows@@AEAAXW4MbCategoryReadyState@345@@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState(Windows::Networking::UX::MbCategoryReadyState)
0x18001e105  mov     rcx, r13; this
0x18001e108  call    ?tp_RefreshProfiles@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_RefreshProfiles(void)
0x18001e10d  mov     rax, [rsp+228h+var_1C8]
0x18001e112  cmp     [rax+3B8h], si
0x18001e119  jz      short loc_18001E17B
0x18001e11b  cmp     [rax+3ECh], esi
0x18001e121  jnz     short loc_18001E17B
0x18001e123  cmp     [rax+3F0h], esi
0x18001e129  jbe     short loc_18001E17B
0x18001e12b  mov     rcx, [rax+3F8h]
0x18001e132  test    rcx, rcx
0x18001e135  jz      short loc_18001E17B
0x18001e137  shr     rcx, 1
0x18001e13a  lea     rcx, [rax+rcx*2]
0x18001e13e  mov     [rax+3F8h], rcx
0x18001e145  mov     r8, [rsp+228h+var_1C8]
0x18001e14a  mov     r8, [r8+3F8h]; unsigned __int16 *
0x18001e151  mov     edx, 17h; unsigned __int64
0x18001e156  lea     rcx, [rsp+228h+var_60]; unsigned __int16 *
0x18001e15e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e163  mov     [rsp+228h+var_34], si
0x18001e16b  lea     rdx, [rsp+228h+var_60]; unsigned __int16 *
0x18001e173  mov     rcx, r13; this
0x18001e176  call    ?tp_UpdatePhoneNumber@MBCategory@Internal@UX@Networking@Windows@@AEAAXPEBG@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdatePhoneNumber(ushort const *)
0x18001e17b  lea     rcx, [r13+1B0h]
0x18001e182  cmp     qword ptr [rcx+18h], 7
0x18001e187  jbe     short loc_18001E18C
0x18001e189  mov     rcx, [rcx]
0x18001e18c  lea     rdx, [r13+190h]
0x18001e193  cmp     qword ptr [rdx+18h], 7
0x18001e198  jbe     short loc_18001E19D
0x18001e19a  mov     rdx, [rdx]
0x18001e19d  lea     rax, [r13+170h]
0x18001e1a4  cmp     qword ptr [rax+18h], 7
0x18001e1a9  jbe     short loc_18001E1AE
0x18001e1ab  mov     rax, [rax]
0x18001e1ae  mov     [rsp+228h+var_1F0], rcx
0x18001e1b3  mov     [rsp+228h+var_1F8], rdx
0x18001e1b8  mov     [rsp+228h+var_200], rax
0x18001e1bd  mov     eax, [r13+25Ch]
0x18001e1c4  mov     dword ptr [rsp+228h+var_208], eax
0x18001e1c8  mov     r9d, [r13+1D8h]
0x18001e1cf  lea     r8, aReadyobjectDat; "ReadyObject data updated. _selectedSlot"...
0x18001e1d6  mov     edx, 0B7h; unsigned int
0x18001e1db  mov     rcx, r14; char *
0x18001e1de  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001e1e3  jmp     short loc_18001E1FF
0x18001e1e5  call    ?_HResultFromWwanStatus@MBCategory@Internal@UX@Networking@Windows@@AEAAJK@Z; Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(ulong)
0x18001e1ea  mov     dword ptr [rsp+228h+var_1C0], eax
0x18001e1ee  lea     rdx, [rsp+228h+var_1C0]
  ... truncated ...
```
