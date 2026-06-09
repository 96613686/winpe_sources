# DdcAccountHelper::EnumerateUsers(int,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,ulong *,ulong *,ulong *)

- ea: `0x18001bf54`
- end: `0x18001c89c`
- name: `?EnumerateUsers@DdcAccountHelper@@SAJHPEAPEAUIJsonValue@Json@Data@Windows@@00PEAK11@Z`
- size: `2376`
- prototype: `__int64 __fastcall(unsigned int, struct Windows::Data::Json::IJsonValue **, struct Windows::Data::Json::IJsonValue **, struct Windows::Data::Json::IJsonValue **, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c8a4`

## callees

- `0x1800024c0`
- `0x1800035b0`
- `0x180004060`
- `0x180004d5c`
- `0x1800050b8`
- `0x180005a64`
- `0x180005a9c`
- `0x18000fc64`
- `0x18000fd48`
- `0x180013938`
- `0x180013ae8`
- `0x180013b38`
- `0x18001bf54`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c110`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c110`
- `MdmCommon!MdmEnumerateUsers` at `0x18001c325`
- `MdmCommon!MdmEnumerateUsers` at `0x18001c325`

## string_xrefs

- `0x18001c0f0`: `Windows.Data.Json.JsonValue`
- `0x18001c15c`: `Windows.Data.Json.JsonArray`
- `0x18001c1f5`: `Windows.Data.Json.JsonArray`
- `0x18001c291`: `Windows.Data.Json.JsonArray`
- `0x18001c129`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18001c05a`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcaccounthelper.cpp`
- `0x18001c18e`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pAdmins.GetAddressOf()))`
- `0x18001c227`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pDeviceOwners.GetAddressOf()))`
- `0x18001c2c3`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pStandardUsers.GetAddressOf()))`
- `0x18001c425`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(iter.c_str()).Get(), pCID.ReleaseAndGetAddressOf()))`
- `0x18001c501`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(iter.c_str()).Get(), pCID.ReleaseAndGetAddressOf()))`
- `0x18001c5dc`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(iter.c_str()).Get(), pCID.ReleaseAndGetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DdcAccountHelper::EnumerateUsers(
        unsigned int a1,
        struct Windows::Data::Json::IJsonValue **a2,
        struct Windows::Data::Json::IJsonValue **a3,
        struct Windows::Data::Json::IJsonValue **a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  _QWORD *v11; // rdx
  int v12; // ecx
  _QWORD *v13; // r8
  _QWORD *v14; // r9
  int v15; // r8d
  int ActivationFactory; // ebx
  int v17; // r13d
  __int64 v18; // rax
  __int64 i; // rsi
  unsigned __int128 v20; // kr00_16
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, PVOID, __int64 *); // rbx
  char v23; // r8
  HSTRING_HEADER *v24; // rax
  int v25; // edi
  __int64 j; // rsi
  __int64 v27; // r13
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, PVOID, __int64 *); // rbx
  char v30; // r8
  HSTRING_HEADER *v31; // rax
  unsigned int v32; // r13d
  __int64 v33; // rax
  __int64 k; // rsi
  unsigned __int128 v35; // kr10_16
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, PVOID, __int64 *); // rbx
  char v38; // r8
  HSTRING_HEADER *v39; // rax
  struct Windows::Data::Json::IJsonValue *v40; // rax
  struct Windows::Data::Json::IJsonValue *v41; // rax
  struct Windows::Data::Json::IJsonValue *v42; // rax
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64); // rcx
  __int64 v46; // rcx
  char v48; // [rsp+20h] [rbp-E0h]
  const char *v49; // [rsp+28h] [rbp-D8h]
  __int64 v50; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v52; // [rsp+40h] [rbp-C0h]
  __int64 (__fastcall ***v53)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v55)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v56; // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Data::Json::IJsonValue *v57; // [rsp+68h] [rbp-98h] BYREF
  struct Windows::Data::Json::IJsonValue *v58; // [rsp+70h] [rbp-90h] BYREF
  struct Windows::Data::Json::IJsonValue *v59; // [rsp+78h] [rbp-88h] BYREF
  __int64 v60; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+88h] [rbp-78h] BYREF
  __int64 v62; // [rsp+90h] [rbp-70h] BYREF
  const WCHAR *v63; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int128 v64; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-50h]
  __int128 v66; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v67; // [rsp+C8h] [rbp-38h]
  unsigned __int128 v68; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v69; // [rsp+E0h] [rbp-20h]
  __int64 v70; // [rsp+E8h] [rbp-18h]
  unsigned int *v71; // [rsp+F0h] [rbp-10h]
  unsigned int *v72; // [rsp+F8h] [rbp-8h]
  unsigned int *v73; // [rsp+100h] [rbp+0h]
  HSTRING_HEADER hstringHeader; // [rsp+108h] [rbp+8h] BYREF
  __int64 v75; // [rsp+120h] [rbp+20h]

  v71 = a5;
  v72 = a6;
  v73 = a7;
  v50 = 0;
  v51 = 0;
  v55 = 0;
  v54 = 0;
  v53 = 0;
  v62 = 0;
  v61 = 0;
  v60 = 0;
  v59 = 0;
  v58 = 0;
  v57 = 0;
  std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(&v68);
  std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(&v66);
  std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(&v64);
  if ( v11 && *v11 )
  {
    v15 = -2147024809;
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_97;
    v49 = "CBR(*ppAdmins == nullptr)";
    v48 = 72;
    goto LABEL_5;
  }
  if ( a3 && *v13 )
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        (_DWORD)v11,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcaccounthelper.cpp",
        77,
        "CBR(*ppDeviceOwners == nullptr)");
    goto LABEL_97;
  }
  if ( a4 && *v14 )
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        (_DWORD)v11,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcaccounthelper.cpp",
        82,
        "CBR(*ppStandardUsers == nullptr)");
    goto LABEL_97;
  }
  v75 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v75, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v51);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      v49 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics"
            ".GetAddressOf()))";
      v48 = 85;
      goto LABEL_18;
    }
    goto LABEL_97;
  }
  if ( a2 )
  {
    v75 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonArray",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v75, &v55);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v49 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pAdmins.GetAddressOf()))";
        v48 = 89;
        goto LABEL_18;
      }
      goto LABEL_97;
    }
    ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                          &v55,
                          (__int64)&v62);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v49 = "CHR(pAdmins.As(&pAdminsAsVector))";
        v48 = 90;
        goto LABEL_18;
      }
      goto LABEL_97;
    }
  }
  if ( a3 )
  {
    v75 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonArray",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v75, &v54);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v49 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pDeviceOwners.GetAddressOf()))";
        v48 = 95;
        goto LABEL_18;
      }
      goto LABEL_97;
    }
    ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                          &v54,
                          (__int64)&v61);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v49 = "CHR(pDeviceOwners.As(&pDeviceOwnersAsVector))";
        v48 = 96;
        goto LABEL_18;
      }
      goto LABEL_97;
    }
  }
  if ( a4 )
  {
    v75 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonArray",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v75, &v53);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v49 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pStandardUsers.GetAddressOf()))";
        v48 = 101;
        goto LABEL_18;
      }
      goto LABEL_97;
    }
    ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                          &v53,
                          (__int64)&v60);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v49 = "CHR(pStandardUsers.As(&pStandardUsersAsVector))";
        v48 = 102;
        goto LABEL_18;
      }
      goto LABEL_97;
    }
  }
  ActivationFactory = MdmEnumerateUsers(&v68, &v66, &v64, a1);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      v49 = "CHR(MdmEnumerateUsers(&vAdmins, &vDeviceOwners, &vStandardUsers, fConnectedOnly))";
      v48 = 105;
      goto LABEL_18;
    }
    goto LABEL_97;
  }
  v17 = 0;
  v18 = *((_QWORD *)&v68 + 1);
  v20 = v68;
  v52 = v20 >> 64;
  for ( i = v20; ; i += 32 )
  {
    LODWORD(v56) = v17;
    if ( i == v18 )
      break;
    if ( a2 )
    {
      v21 = v51;
      v22 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v51 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
      v56 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v56, v23);
      ActivationFactory = v22(v21, v24[1].Reserved.Reserved1, &v50);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          v49 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(iter.c_str()).Get(), pCID.ReleaseAndGetAddressOf()))";
          v48 = 112;
          goto LABEL_18;
        }
        goto LABEL_97;
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 104LL))(v62, v50);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          v49 = "CHR(pAdminsAsVector->Append(pCID.Get()))";
          v48 = 113;
          goto LABEL_18;
        }
        goto LABEL_97;
      }
      v18 = v52;
    }
    ++v17;
  }
  v25 = 0;
  v27 = *((_QWORD *)&v66 + 1);
  for ( j = v66; ; j += 32 )
  {
    LODWORD(v52) = v25;
    if ( j == v27 )
    {
      v32 = 0;
      v33 = *((_QWORD *)&v64 + 1);
      v35 = v64;
      v70 = v35 >> 64;
      for ( k = v35; k != v33; k += 32 )
      {
        if ( a4 )
        {
          v36 = v51;
          v37 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v51 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
          v63 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
          v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v63, v38);
          ActivationFactory = v37(v36, v39[1].Reserved.Reserved1, &v50);
          if ( ActivationFactory < 0 )
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_97;
            v49 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(iter.c_str()).Get(), pCID.ReleaseAndGetAddressOf()))";
            v48 = -124;
            goto LABEL_18;
          }
          ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 104LL))(v60, v50);
          if ( ActivationFactory < 0 )
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_97;
            v49 = "CHR(pStandardUsersAsVector->Append(pCID.Get()))";
            v48 = -123;
            goto LABEL_18;
          }
          v33 = v70;
        }
        ++v32;
      }
      if ( a2 )
      {
        ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                              &v55,
                              (__int64)&v59);
        if ( ActivationFactory < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_97;
          v49 = "CHR(pAdmins.As(&pAdminsAsValue))";
          v48 = -117;
LABEL_18:
          v15 = ActivationFactory;
LABEL_5:
          McTemplateU0dsqs_EventWriteTransfer(
            v12,
            (_DWORD)v11,
            v15,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcaccounthelper.cpp",
            v48,
            v49);
          goto LABEL_97;
        }
        v40 = v59;
        v59 = 0;
        *a2 = v40;
      }
      if ( a3 )
      {
        ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                              &v54,
                              (__int64)&v58);
        if ( ActivationFactory < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_97;
          v49 = "CHR(pDeviceOwners.As(&pDeviceOwnersAsValue))";
          v48 = -111;
          goto LABEL_18;
        }
        v41 = v58;
        v58 = 0;
        *a3 = v41;
      }
      if ( a4 )
      {
        ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                              &v53,
                              (__int64)&v57);
        if ( ActivationFactory < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_97;
          v49 = "CHR(pStandardUsers.As(&pStandardUsersAsValue))";
          v48 = -105;
          goto LABEL_18;
        }
        v42 = v57;
        v57 = 0;
        *a4 = v42;
      }
      if ( v71 )
        *v71 = (unsigned int)v56;
      if ( v72 )
        *v72 = v52;
      if ( v73 )
        *v73 = v32;
      goto LABEL_97;
    }
    if ( !a3 )
      goto LABEL_60;
    v28 = v51;
    v29 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v51 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    v63 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v63, v30);
    ActivationFactory = v29(v28, v31[1].Reserved.Reserved1, &v50);
    if ( ActivationFactory < 0 )
      break;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v61 + 104LL))(v61, v50);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v49 = "CHR(pDeviceOwnersAsVector->Append(pCID.Get()))";
        v48 = 123;
        goto LABEL_18;
      }
      goto LABEL_97;
    }
    v25 = v52;
LABEL_60:
    ++v25;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v49 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(iter.c_str()).Get(), pCID.ReleaseAndGetAddressOf()))";
    v48 = 122;
    goto LABEL_18;
  }
LABEL_97:
  if ( (_QWORD)v64 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v64, *((_QWORD *)&v64 + 1));
    std::_Deallocate<16>((_QWORD *)v64, (v65 - v64) & 0xFFFFFFFFFFFFFFE0uLL);
    v64 = 0;
    v65 = 0;
  }
  if ( (_QWORD)v66 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v66, *((_QWORD *)&v66 + 1));
    std::_Deallocate<16>((_QWORD *)v66, (v67 - v66) & 0xFFFFFFFFFFFFFFE0uLL);
    v66 = 0;
    v67 = 0;
  }
  if ( (_QWORD)v68 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v68, *((_QWORD *)&v68 + 1));
    std::_Deallocate<16>((_QWORD *)v68, (v69 - v68) & 0xFFFFFFFFFFFFFFE0uLL);
    v68 = 0;
    v69 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  v43 = v53;
  if ( v53 )
  {
    v53 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v43)[2])(v43);
  }
  v44 = v54;
  if ( v54 )
  {
    v54 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v44)[2])(v44);
  }
  v45 = v55;
  if ( v55 )
  {
    v55 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v45)[2])(v45);
  }
  v46 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001bf54  push    rbp
0x18001bf56  push    rbx
0x18001bf57  push    rsi
0x18001bf58  push    rdi
0x18001bf59  push    r12
0x18001bf5b  push    r13
0x18001bf5d  push    r14
0x18001bf5f  push    r15
0x18001bf61  lea     rbp, [rsp-38h]
0x18001bf66  sub     rsp, 138h
0x18001bf6d  mov     rax, cs:__security_cookie
0x18001bf74  xor     rax, rsp
0x18001bf77  mov     [rbp+70h+var_48], rax
0x18001bf7b  mov     r15, r9
0x18001bf7e  mov     r14, r8
0x18001bf81  mov     r12, rdx
0x18001bf84  mov     edi, ecx
0x18001bf86  mov     rax, [rbp+70h+arg_20]
0x18001bf8d  mov     [rbp+70h+var_80], rax
0x18001bf91  mov     rax, [rbp+70h+arg_28]
0x18001bf98  mov     [rbp+70h+var_78], rax
0x18001bf9c  mov     rax, [rbp+70h+arg_30]
0x18001bfa3  mov     [rbp+70h+var_70], rax
0x18001bfa7  mov     [rsp+170h+var_140], 0
0x18001bfb0  mov     [rsp+170h+var_138], 0
0x18001bfb9  mov     [rsp+170h+var_118], 0
0x18001bfc2  mov     [rsp+170h+var_120], 0
0x18001bfcb  mov     [rsp+170h+var_128], 0
0x18001bfd4  mov     [rbp+70h+var_E0], 0
0x18001bfdc  mov     [rbp+70h+var_E8], 0
0x18001bfe4  mov     [rbp+70h+var_F0], 0
0x18001bfec  mov     [rsp+170h+var_F8], 0
0x18001bff5  mov     [rsp+170h+var_100], 0
0x18001bffe  mov     [rsp+170h+var_108], 0
0x18001c007  lea     rcx, [rbp+70h+var_A0]
0x18001c00b  call    ??0?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(void)
0x18001c010  nop
0x18001c011  lea     rcx, [rbp+70h+var_B8]
0x18001c015  call    ??0?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(void)
0x18001c01a  nop
0x18001c01b  lea     rcx, [rbp+70h+var_D0]
0x18001c01f  call    ??0?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(void)
0x18001c024  nop
0x18001c025  test    rdx, rdx
0x18001c028  jz      short loc_18001C06B
0x18001c02a  cmp     qword ptr [rdx], 0
0x18001c02e  jz      short loc_18001C06B
0x18001c030  mov     r8d, 80070057h
0x18001c036  mov     ebx, r8d
0x18001c039  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c040  jz      loc_18001C70F
0x18001c046  lea     rax, aCbrPpadminsNul; "CBR(*ppAdmins == nullptr)"
0x18001c04d  mov     [rsp+170h+var_148], rax
0x18001c052  mov     dword ptr [rsp+170h+var_150], 48h ; 'H'
0x18001c05a  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001c061  call    McTemplateU0dsqs_EventWriteTransfer
0x18001c066  jmp     loc_18001C70F
0x18001c06b  test    r14, r14
0x18001c06e  jz      short loc_18001C0A2
0x18001c070  cmp     qword ptr [r8], 0
0x18001c074  jz      short loc_18001C0A2
0x18001c076  mov     r8d, 80070057h
0x18001c07c  mov     ebx, r8d
0x18001c07f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c086  jz      loc_18001C70F
0x18001c08c  lea     rax, aCbrPpdeviceown; "CBR(*ppDeviceOwners == nullptr)"
0x18001c093  mov     [rsp+170h+var_148], rax
0x18001c098  mov     dword ptr [rsp+170h+var_150], 4Dh ; 'M'
0x18001c0a0  jmp     short loc_18001C05A
0x18001c0a2  test    r15, r15
0x18001c0a5  jz      short loc_18001C0D9
0x18001c0a7  cmp     qword ptr [r9], 0
0x18001c0ab  jz      short loc_18001C0D9
0x18001c0ad  mov     r8d, 80070057h
0x18001c0b3  mov     ebx, r8d
0x18001c0b6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c0bd  jz      loc_18001C70F
0x18001c0c3  lea     rax, aCbrPpstandardu; "CBR(*ppStandardUsers == nullptr)"
0x18001c0ca  mov     [rsp+170h+var_148], rax
0x18001c0cf  mov     dword ptr [rsp+170h+var_150], 52h ; 'R'
0x18001c0d7  jmp     short loc_18001C05A
0x18001c0d9  mov     [rbp+70h+var_50], 0
0x18001c0e1  mov     esi, 1Bh
0x18001c0e6  mov     r9d, esi; unsigned int
0x18001c0e9  lea     r13d, [rsi+1]
0x18001c0ed  mov     r8d, r13d; unsigned int
0x18001c0f0  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001c0f7  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x18001c0fb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c100  lea     r8, [rsp+170h+var_138]
0x18001c105  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001c10c  mov     rcx, [rbp+70h+var_50]
0x18001c110  call    cs:__imp_RoGetActivationFactory
0x18001c116  mov     ebx, eax
0x18001c118  test    eax, eax
0x18001c11a  jns     short loc_18001C145
0x18001c11c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c123  jz      loc_18001C70F
0x18001c129  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18001c130  mov     [rsp+170h+var_148], rax
0x18001c135  mov     dword ptr [rsp+170h+var_150], 55h ; 'U'
0x18001c13d  mov     r8d, ebx
0x18001c140  jmp     loc_18001C05A
0x18001c145  test    r12, r12
0x18001c148  jz      loc_18001C1DE
0x18001c14e  mov     [rbp+70h+var_50], 0
0x18001c156  mov     r9d, esi; unsigned int
0x18001c159  mov     r8d, r13d; unsigned int
0x18001c15c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x18001c163  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x18001c167  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c16c  nop
0x18001c16d  lea     rdx, [rsp+170h+var_118]
0x18001c172  mov     rcx, [rbp+70h+var_50]
0x18001c176  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x18001c17b  mov     ebx, eax
0x18001c17d  test    eax, eax
0x18001c17f  jns     short loc_18001C1A4
0x18001c181  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c188  jz      loc_18001C70F
0x18001c18e  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18001c195  mov     [rsp+170h+var_148], rax
0x18001c19a  mov     dword ptr [rsp+170h+var_150], 59h ; 'Y'
0x18001c1a2  jmp     short loc_18001C13D
0x18001c1a4  lea     rdx, [rbp+70h+var_E0]
0x18001c1a8  lea     rcx, [rsp+170h+var_118]
0x18001c1ad  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18001c1b2  mov     ebx, eax
0x18001c1b4  test    eax, eax
0x18001c1b6  jns     short loc_18001C1DE
0x18001c1b8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c1bf  jz      loc_18001C70F
0x18001c1c5  lea     rax, aChrPadminsAsPa; "CHR(pAdmins.As(&pAdminsAsVector))"
0x18001c1cc  mov     [rsp+170h+var_148], rax
0x18001c1d1  mov     dword ptr [rsp+170h+var_150], 5Ah ; 'Z'
0x18001c1d9  jmp     loc_18001C13D
0x18001c1de  test    r14, r14
0x18001c1e1  jz      loc_18001C27A
0x18001c1e7  mov     [rbp+70h+var_50], 0
0x18001c1ef  mov     r9d, esi; unsigned int
0x18001c1f2  mov     r8d, r13d; unsigned int
0x18001c1f5  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x18001c1fc  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x18001c200  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c205  nop
0x18001c206  lea     rdx, [rsp+170h+var_120]
0x18001c20b  mov     rcx, [rbp+70h+var_50]
0x18001c20f  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x18001c214  mov     ebx, eax
0x18001c216  test    eax, eax
0x18001c218  jns     short loc_18001C240
0x18001c21a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c221  jz      loc_18001C70F
0x18001c227  lea     rax, aChrActivateins_4; "CHR(ActivateInstance(HStringReference(R"...
0x18001c22e  mov     [rsp+170h+var_148], rax
0x18001c233  mov     dword ptr [rsp+170h+var_150], 5Fh ; '_'
0x18001c23b  jmp     loc_18001C13D
0x18001c240  lea     rdx, [rbp+70h+var_E8]
0x18001c244  lea     rcx, [rsp+170h+var_120]
0x18001c249  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18001c24e  mov     ebx, eax
0x18001c250  test    eax, eax
0x18001c252  jns     short loc_18001C27A
0x18001c254  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c25b  jz      loc_18001C70F
0x18001c261  lea     rax, aChrPdeviceowne_1; "CHR(pDeviceOwners.As(&pDeviceOwnersAsVe"...
0x18001c268  mov     [rsp+170h+var_148], rax
0x18001c26d  mov     dword ptr [rsp+170h+var_150], 60h ; '`'
0x18001c275  jmp     loc_18001C13D
0x18001c27a  test    r15, r15
0x18001c27d  jz      loc_18001C316
0x18001c283  mov     [rbp+70h+var_50], 0
0x18001c28b  mov     r9d, esi; unsigned int
0x18001c28e  mov     r8d, r13d; unsigned int
0x18001c291  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x18001c298  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x18001c29c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c2a1  nop
0x18001c2a2  lea     rdx, [rsp+170h+var_128]
0x18001c2a7  mov     rcx, [rbp+70h+var_50]
0x18001c2ab  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x18001c2b0  mov     ebx, eax
0x18001c2b2  test    eax, eax
0x18001c2b4  jns     short loc_18001C2DC
0x18001c2b6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c2bd  jz      loc_18001C70F
0x18001c2c3  lea     rax, aChrActivateins_2; "CHR(ActivateInstance(HStringReference(R"...
0x18001c2ca  mov     [rsp+170h+var_148], rax
0x18001c2cf  mov     dword ptr [rsp+170h+var_150], 65h ; 'e'
0x18001c2d7  jmp     loc_18001C13D
0x18001c2dc  lea     rdx, [rbp+70h+var_F0]
0x18001c2e0  lea     rcx, [rsp+170h+var_128]
0x18001c2e5  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18001c2ea  mov     ebx, eax
0x18001c2ec  test    eax, eax
0x18001c2ee  jns     short loc_18001C316
0x18001c2f0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c2f7  jz      loc_18001C70F
0x18001c2fd  lea     rax, aChrPstandardus_1; "CHR(pStandardUsers.As(&pStandardUsersAs"...
0x18001c304  mov     [rsp+170h+var_148], rax
0x18001c309  mov     dword ptr [rsp+170h+var_150], 66h ; 'f'
0x18001c311  jmp     loc_18001C13D
0x18001c316  mov     r9d, edi
0x18001c319  lea     r8, [rbp+70h+var_D0]
0x18001c31d  lea     rdx, [rbp+70h+var_B8]
0x18001c321  lea     rcx, [rbp+70h+var_A0]
0x18001c325  call    cs:__imp_?MdmEnumerateUsers@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00H@Z; MdmEnumerateUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *,int)
0x18001c32b  mov     ebx, eax
0x18001c32d  test    eax, eax
0x18001c32f  jns     short loc_18001C357
0x18001c331  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c338  jz      loc_18001C70F
0x18001c33e  lea     rax, aChrMdmenumerat; "CHR(MdmEnumerateUsers(&vAdmins, &vDevic"...
0x18001c345  mov     [rsp+170h+var_148], rax
0x18001c34a  mov     dword ptr [rsp+170h+var_150], 69h ; 'i'
0x18001c352  jmp     loc_18001C13D
0x18001c357  xor     r13d, r13d
0x18001c35a  mov     rsi, qword ptr [rbp+70h+var_A0]
0x18001c35e  mov     rax, qword ptr [rbp+70h+var_A0+8]
0x18001c362  mov     [rsp+170h+var_130], rax
0x18001c367  mov     dword ptr [rsp+170h+var_110], r13d
0x18001c36c  cmp     rsi, rax
0x18001c36f  jz      loc_18001C43E
0x18001c375  test    r12, r12
0x18001c378  jz      short loc_18001C3E6
0x18001c37a  mov     rdi, [rsp+170h+var_138]
0x18001c37f  mov     rax, [rdi]
0x18001c382  mov     rbx, [rax+50h]
0x18001c386  lea     rcx, [rsp+170h+var_140]
0x18001c38b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c390  mov     rcx, rsi
0x18001c393  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c398  mov     [rsp+170h+var_110], rax
0x18001c39d  lea     rdx, [rsp+170h+var_110]
0x18001c3a2  lea     rcx, [rbp+70h+hstringHeader]
0x18001c3a6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001c3ab  nop
0x18001c3ac  lea     r8, [rsp+170h+var_140]
0x18001c3b1  mov     rdx, [rax+18h]
0x18001c3b5  mov     rcx, rdi
0x18001c3b8  mov     rax, rbx
0x18001c3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3c0  mov     ebx, eax
0x18001c3c2  test    eax, eax
0x18001c3c4  js      short loc_18001C418
0x18001c3c6  mov     rcx, [rbp+70h+var_E0]
0x18001c3ca  mov     rax, [rcx]
0x18001c3cd  mov     rdx, [rsp+170h+var_140]
0x18001c3d2  mov     rax, [rax+68h]
0x18001c3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3db  mov     ebx, eax
0x18001c3dd  test    eax, eax
0x18001c3df  js      short loc_18001C3F2
0x18001c3e1  mov     rax, [rsp+170h+var_130]
0x18001c3e6  inc     r13d
0x18001c3e9  add     rsi, 20h ; ' '
0x18001c3ed  jmp     loc_18001C367
0x18001c3f2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c3f9  jz      loc_18001C70F
0x18001c3ff  lea     rax, aChrPadminsasve; "CHR(pAdminsAsVector->Append(pCID.Get())"...
0x18001c406  mov     [rsp+170h+var_148], rax
0x18001c40b  mov     dword ptr [rsp+170h+var_150], 71h ; 'q'
0x18001c413  jmp     loc_18001C13D
0x18001c418  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c41f  jz      loc_18001C70F
0x18001c425  lea     rax, aChrPjsonvalues_66; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001c42c  mov     [rsp+170h+var_148], rax
0x18001c431  mov     dword ptr [rsp+170h+var_150], 70h ; 'p'
0x18001c439  jmp     loc_18001C13D
0x18001c43e  xor     edi, edi
0x18001c440  mov     rsi, qword ptr [rbp+70h+var_B8]
0x18001c444  mov     r13, qword ptr [rbp+70h+var_B8+8]
0x18001c448  mov     dword ptr [rsp+170h+var_130], edi
0x18001c44c  cmp     rsi, r13
0x18001c44f  jz      loc_18001C51A
0x18001c455  test    r14, r14
0x18001c458  jz      short loc_18001C4C3
0x18001c45a  mov     rdi, [rsp+170h+var_138]
0x18001c45f  mov     rax, [rdi]
0x18001c462  mov     rbx, [rax+50h]
0x18001c466  lea     rcx, [rsp+170h+var_140]
0x18001c46b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c470  mov     rcx, rsi
0x18001c473  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c478  mov     [rbp+70h+var_D8], rax
0x18001c47c  lea     rdx, [rbp+70h+var_D8]
0x18001c480  lea     rcx, [rbp+70h+hstringHeader]
0x18001c484  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001c489  nop
0x18001c48a  lea     r8, [rsp+170h+var_140]
0x18001c48f  mov     rdx, [rax+18h]
0x18001c493  mov     rcx, rdi
0x18001c496  mov     rax, rbx
0x18001c499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c49e  mov     ebx, eax
0x18001c4a0  test    eax, eax
0x18001c4a2  js      short loc_18001C4F4
0x18001c4a4  mov     rcx, [rbp+70h+var_E8]
0x18001c4a8  mov     rax, [rcx]
0x18001c4ab  mov     rdx, [rsp+170h+var_140]
  ... truncated ...
```
