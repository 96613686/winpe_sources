# DdcUserInfoHelper::GetUserInfo(Windows::Data::Json::IJsonValue * *)

- ea: `0x180027dc8`
- end: `0x1800280de`
- name: `?GetUserInfo@DdcUserInfoHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `790`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ca4c`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x1800139c8`
- `0x180013a58`
- `0x180013b38`
- `0x180027c9c`
- `0x180027cbc`
- `0x180027dc8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027eba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027eba`

## string_xrefs

- `0x180027e9b`: `Windows.Data.Json.JsonValue`
- `0x180027f76`: `Windows.Data.Json.JsonValue`
- `0x180027e2f`: `Windows.Data.Json.JsonObject`
- `0x180027ed3`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x180027fa7`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180027e60`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pUserInfo.GetAddressOf()))`
- `0x180027e74`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcuserinfohelper.cpp`
- `0x180027f4a`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(browser.get()).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180028001`: `CHR(pUserInfo->SetNamedValue(HStringReference(JSON_DEFAULT_BROWSER).Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall DdcUserInfoHelper::GetUserInfo(struct Windows::Data::Json::IJsonValue **a1)
{
  int v2; // edx
  int v3; // ecx
  int ActivationFactory; // ebx
  int v5; // edx
  int v6; // ecx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, PVOID, __int64 *); // rbx
  char v9; // r8
  HSTRING_HEADER *v10; // rax
  int v11; // edx
  int v12; // ecx
  char v13; // r8
  int v14; // edx
  int v15; // ecx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64); // rdi
  __int64 v18; // rbx
  HSTRING_HEADER *v19; // rax
  int v20; // edx
  int v21; // ecx
  int v22; // edx
  int v23; // ecx
  struct Windows::Data::Json::IJsonValue *v24; // rax
  __int64 v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64); // rcx
  __int64 v28; // [rsp+30h] [rbp-19h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-11h] BYREF
  __int64 v30; // [rsp+40h] [rbp-9h] BYREF
  struct Windows::Data::Json::IJsonValue *v31; // [rsp+48h] [rbp-1h] BYREF
  const WCHAR *v32; // [rsp+50h] [rbp+7h] BYREF
  const WCHAR *v33; // [rsp+58h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+17h] BYREF
  __int64 v35; // [rsp+78h] [rbp+2Fh]

  v29 = 0;
  v31 = 0;
  v28 = 0;
  v30 = 0;
  v32 = 0;
  v35 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v35, &v29);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcuserinfohelper.cpp",
        37,
        "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pUserInfo.GetAddressOf()))");
    goto LABEL_22;
  }
  v35 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v35, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v30);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcuserinfohelper.cpp",
        38,
        "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
    goto LABEL_22;
  }
  if ( (int)DdcUserInfoHelper::GetDefaultBrowser((void **)&v32) >= 0 )
  {
    v7 = v30;
    v8 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v30 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v33 = v32;
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v33, v9);
    ActivationFactory = v8(v7, v10[1].Reserved.Reserved1, &v28);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcuserinfohelper.cpp",
          42,
          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(browser.get()).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_22;
    }
    goto LABEL_15;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v35 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v35, &v28);
  if ( ActivationFactory >= 0 )
  {
LABEL_15:
    v16 = v29;
    v17 = (*v29)[7];
    v18 = v28;
    v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&off_18002B7E8,
            v13);
    ActivationFactory = v17(v16, (GUID *)v19[1].Reserved.Reserved1, v18);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                            &v29,
                            (__int64)&v31);
      if ( ActivationFactory >= 0 )
      {
        v24 = v31;
        v31 = 0;
        *a1 = v24;
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v23,
          v22,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcuserinfohelper.cpp",
          51,
          "CHR(pUserInfo.As(&pUserInfoAsValue))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v21,
        v20,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcuserinfohelper.cpp",
        49,
        "CHR(pUserInfo->SetNamedValue(HStringReference(JSON_DEFAULT_BROWSER).Get(), pJsonValue.Get()))");
    }
    goto LABEL_22;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v15,
      v14,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcuserinfohelper.cpp",
      46,
      "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v32);
  v25 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v26 = v29;
  if ( v29 )
  {
    v29 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v26)[2])(v26);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180027dc8  mov     [rsp-8+arg_8], rbx
0x180027dcd  mov     [rsp-8+arg_10], rsi
0x180027dd2  push    rbp
0x180027dd3  push    rdi
0x180027dd4  push    r14
0x180027dd6  lea     rbp, [rsp-47h]
0x180027ddb  sub     rsp, 90h
0x180027de2  mov     rax, cs:__security_cookie
0x180027de9  xor     rax, rsp
0x180027dec  mov     [rbp+57h+var_20], rax
0x180027df0  mov     r14, rcx
0x180027df3  mov     [rbp+57h+var_68], 0
0x180027dfb  mov     [rbp+57h+var_58], 0
0x180027e03  mov     [rbp+57h+var_70], 0
0x180027e0b  mov     [rbp+57h+var_60], 0
0x180027e13  mov     [rbp+57h+var_50], 0
0x180027e1b  mov     [rbp+57h+var_28], 0
0x180027e23  mov     edi, 1Ch
0x180027e28  mov     r9d, edi; unsigned int
0x180027e2b  lea     r8d, [rdi+1]; unsigned int
0x180027e2f  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180027e36  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180027e3a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027e3f  nop
0x180027e40  lea     rdx, [rbp+57h+var_68]
0x180027e44  mov     rcx, [rbp+57h+var_28]
0x180027e48  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180027e4d  mov     ebx, eax
0x180027e4f  test    eax, eax
0x180027e51  jns     short loc_180027E88
0x180027e53  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180027e5a  jz      loc_18002805E
0x180027e60  lea     rax, aChrActivateins_3; "CHR(ActivateInstance(HStringReference(R"...
0x180027e67  mov     [rsp+0A0h+var_78], rax
0x180027e6c  mov     [rsp+0A0h+var_80], 25h ; '%'
0x180027e74  lea     r9, aOnecoreuapShel_16; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180027e7b  mov     r8d, ebx
0x180027e7e  call    McTemplateU0dsqs_EventWriteTransfer
0x180027e83  jmp     loc_18002805E
0x180027e88  mov     [rbp+57h+var_28], 0
0x180027e90  mov     esi, 1Bh
0x180027e95  mov     r9d, esi; unsigned int
0x180027e98  mov     r8d, edi; unsigned int
0x180027e9b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180027ea2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180027ea6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027eab  lea     r8, [rbp+57h+var_60]
0x180027eaf  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180027eb6  mov     rcx, [rbp+57h+var_28]
0x180027eba  call    cs:__imp_RoGetActivationFactory
0x180027ec0  mov     ebx, eax
0x180027ec2  test    eax, eax
0x180027ec4  jns     short loc_180027EE9
0x180027ec6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180027ecd  jz      loc_18002805E
0x180027ed3  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x180027eda  mov     [rsp+0A0h+var_78], rax
0x180027edf  mov     [rsp+0A0h+var_80], 26h ; '&'
0x180027ee7  jmp     short loc_180027E74
0x180027ee9  lea     rcx, [rbp+57h+var_50]
0x180027eed  call    ?GetDefaultBrowser@DdcUserInfoHelper@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; DdcUserInfoHelper::GetDefaultBrowser(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180027ef2  lea     rcx, [rbp+57h+var_70]
0x180027ef6  test    eax, eax
0x180027ef8  js      short loc_180027F63
0x180027efa  mov     rdi, [rbp+57h+var_60]
0x180027efe  mov     rax, [rdi]
0x180027f01  mov     rbx, [rax+50h]
0x180027f05  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027f0a  mov     rdx, [rbp+57h+var_50]
0x180027f0e  mov     [rbp+57h+var_48], rdx
0x180027f12  lea     rdx, [rbp+57h+var_48]
0x180027f16  lea     rcx, [rbp+57h+hstringHeader]
0x180027f1a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180027f1f  nop
0x180027f20  lea     r8, [rbp+57h+var_70]
0x180027f24  mov     rdx, [rax+18h]
0x180027f28  mov     rcx, rdi
0x180027f2b  mov     rax, rbx
0x180027f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f33  mov     ebx, eax
0x180027f35  test    eax, eax
0x180027f37  jns     loc_180027FC0
0x180027f3d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180027f44  jz      loc_18002805E
0x180027f4a  lea     rax, aChrPjsonvalues_43; "CHR(pJsonValueStatics->CreateStringValu"...
0x180027f51  mov     [rsp+0A0h+var_78], rax
0x180027f56  mov     [rsp+0A0h+var_80], 2Ah ; '*'
0x180027f5e  jmp     loc_180027E74
0x180027f63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027f68  mov     [rbp+57h+var_28], 0
0x180027f70  mov     r9d, esi; unsigned int
0x180027f73  mov     r8d, edi; unsigned int
0x180027f76  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180027f7d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180027f81  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027f86  nop
0x180027f87  lea     rdx, [rbp+57h+var_70]
0x180027f8b  mov     rcx, [rbp+57h+var_28]
0x180027f8f  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x180027f94  mov     ebx, eax
0x180027f96  test    eax, eax
0x180027f98  jns     short loc_180027FC0
0x180027f9a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180027fa1  jz      loc_18002805E
0x180027fa7  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x180027fae  mov     [rsp+0A0h+var_78], rax
0x180027fb3  mov     [rsp+0A0h+var_80], 2Eh ; '.'
0x180027fbb  jmp     loc_180027E74
0x180027fc0  mov     rsi, [rbp+57h+var_68]
0x180027fc4  mov     rax, [rsi]
0x180027fc7  mov     rdi, [rax+38h]
0x180027fcb  mov     rbx, [rbp+57h+var_70]
0x180027fcf  lea     rdx, off_18002B7E8; "DefaultBrowser"
0x180027fd6  lea     rcx, [rbp+57h+hstringHeader]
0x180027fda  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180027fdf  nop
0x180027fe0  mov     r8, rbx
0x180027fe3  mov     rdx, [rax+18h]
0x180027fe7  mov     rcx, rsi
0x180027fea  mov     rax, rdi
0x180027fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ff2  mov     ebx, eax
0x180027ff4  test    eax, eax
0x180027ff6  jns     short loc_18002801A
0x180027ff8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180027fff  jz      short loc_18002805E
0x180028001  lea     rax, aChrPuserinfoSe; "CHR(pUserInfo->SetNamedValue(HStringRef"...
0x180028008  mov     [rsp+0A0h+var_78], rax
0x18002800d  mov     [rsp+0A0h+var_80], 31h ; '1'
0x180028015  jmp     loc_180027E74
0x18002801a  lea     rdx, [rbp+57h+var_58]
0x18002801e  lea     rcx, [rbp+57h+var_68]
0x180028022  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180028027  mov     ebx, eax
0x180028029  test    eax, eax
0x18002802b  jns     short loc_18002804F
0x18002802d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180028034  jz      short loc_18002805E
0x180028036  lea     rax, aChrPuserinfoAs; "CHR(pUserInfo.As(&pUserInfoAsValue))"
0x18002803d  mov     [rsp+0A0h+var_78], rax
0x180028042  mov     [rsp+0A0h+var_80], 33h ; '3'
0x18002804a  jmp     loc_180027E74
0x18002804f  mov     rax, [rbp+57h+var_58]
0x180028053  mov     [rbp+57h+var_58], 0
0x18002805b  mov     [r14], rax
0x18002805e  lea     rcx, [rbp+57h+var_50]
0x180028062  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028067  nop
0x180028068  mov     rcx, [rbp+57h+var_60]
0x18002806c  test    rcx, rcx
0x18002806f  jz      short loc_180028086
0x180028071  mov     [rbp+57h+var_60], 0
0x180028079  mov     rax, [rcx]
0x18002807c  mov     rax, [rax+10h]
0x180028080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028085  nop
0x180028086  lea     rcx, [rbp+57h+var_70]
0x18002808a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002808f  nop
0x180028090  lea     rcx, [rbp+57h+var_58]
0x180028094  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028099  nop
0x18002809a  mov     rcx, [rbp+57h+var_68]
0x18002809e  test    rcx, rcx
0x1800280a1  jz      short loc_1800280B8
0x1800280a3  mov     [rbp+57h+var_68], 0
0x1800280ab  mov     rax, [rcx]
0x1800280ae  mov     rax, [rax+10h]
0x1800280b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280b7  nop
0x1800280b8  mov     eax, ebx
0x1800280ba  mov     rcx, [rbp+57h+var_20]
0x1800280be  xor     rcx, rsp; StackCookie
0x1800280c1  call    __security_check_cookie
0x1800280c6  lea     r11, [rsp+0A0h+var_10]
0x1800280ce  mov     rbx, [r11+28h]
0x1800280d2  mov     rsi, [r11+30h]
0x1800280d6  mov     rsp, r11
0x1800280d9  pop     r14
0x1800280db  pop     rdi
0x1800280dc  pop     rbp
0x1800280dd  retn
```
