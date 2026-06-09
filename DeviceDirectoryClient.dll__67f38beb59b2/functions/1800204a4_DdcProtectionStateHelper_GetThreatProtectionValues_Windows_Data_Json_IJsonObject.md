# DdcProtectionStateHelper::GetThreatProtectionValues(Windows::Data::Json::IJsonObject *)

- ea: `0x1800204a4`
- end: `0x180020994`
- name: `?GetThreatProtectionValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `1264`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020068`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x180013938`
- `0x180013ae8`
- `0x180013b38`
- `0x18001d420`
- `0x18001e164`
- `0x18001f6d0`
- `0x1800204a4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800206ef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800206ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800208a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800208cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800208f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800208a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800208cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800208f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020909`

## string_xrefs

- `0x1800206d0`: `Windows.Data.Json.JsonValue`
- `0x180020530`: `Windows.Data.Json.JsonArray`
- `0x180020708`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x180020561`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))`
- `0x18002059a`: `CHR(pJsonArray.As(&pJsonArrayAsVector))`
- `0x180020678`: `CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))`
- `0x1800207f8`: `CHR(pJsonArray.As(&pJsonArrayAsValue))`
- `0x18002085f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18002069e`: `CHR(GetAvProviderValues(&pProducts->pList[i], pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180020769`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszThirdPartyAvActive).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800207c3`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_THIRD_PARTY_AV_ACTIVE).Get(), pJsonValue.Get()))`
- `0x18002084b`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_THREAT_PROTECTION_AV_PROVIDERS).Get(), pJsonArrayAsValue.Get()))`

## pseudocode

```c
__int64 __fastcall DdcProtectionStateHelper::GetThreatProtectionValues(
        struct Windows::Data::Json::IJsonObject *a1,
        int a2)
{
  int AvProviderValues; // ebx
  int v4; // edx
  int v5; // ecx
  int v6; // edx
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  IUnknown *v10; // rbx
  int *v11; // rcx
  unsigned int i; // edi
  int v13; // edx
  int v14; // ecx
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // ecx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, PVOID, struct Windows::Data::Json::IJsonValue **); // rbx
  char v21; // r8
  HSTRING_HEADER *v22; // rax
  int v23; // edx
  int v24; // ecx
  char v25; // r8
  __int64 (__fastcall *v26)(struct Windows::Data::Json::IJsonObject *, PVOID, struct Windows::Data::Json::IJsonValue *); // rdi
  struct Windows::Data::Json::IJsonValue *v27; // rbx
  HSTRING_HEADER *v28; // rax
  int v29; // edx
  int v30; // ecx
  int v31; // edx
  int v32; // ecx
  char v33; // r8
  __int64 (__fastcall *v34)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v35; // rbx
  HSTRING_HEADER *v36; // rax
  int v37; // edx
  int v38; // ecx
  LPVOID v39; // rcx
  unsigned int v40; // esi
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64); // rcx
  __int64 v44; // rcx
  LPVOID pv; // [rsp+30h] [rbp-29h] BYREF
  struct Windows::Data::Json::IJsonValue *v47; // [rsp+38h] [rbp-21h] BYREF
  int v48; // [rsp+40h] [rbp-19h] BYREF
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-11h] BYREF
  __int64 v50; // [rsp+50h] [rbp-9h] BYREF
  IUnknown *v51; // [rsp+58h] [rbp-1h] BYREF
  __int64 v52; // [rsp+60h] [rbp+7h] BYREF
  __int64 v53; // [rsp+68h] [rbp+Fh] BYREF
  const WCHAR *v54; // [rsp+70h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v56; // [rsp+90h] [rbp+37h]

  v51 = 0;
  pv = 0;
  v48 = 0;
  v50 = 0;
  v47 = 0;
  v49 = 0;
  v53 = 0;
  v52 = 0;
  if ( a1 )
  {
    v56 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonArray",
      0x1Cu,
      0x1Bu);
    AvProviderValues = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v56, &v49);
    if ( AvProviderValues >= 0 )
    {
      AvProviderValues = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                           &v49,
                           (__int64)&v53);
      if ( AvProviderValues >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        if ( (int)CreateInstanceWithCloak<IThreatProtectionShield>(v9, v8, &v51) < 0 )
        {
          v54 = GetOnOffMapping(0);
        }
        else
        {
          v10 = v51;
          if ( ((int (__fastcall *)(IUnknown *, int *))v51->lpVtbl[2].AddRef)(v51, &v48) < 0 )
            v11 = 0;
          else
            v11 = &v48;
          v54 = GetOnOffMapping(v11);
          if ( ((int (__fastcall *)(IUnknown *, LPVOID *))v10->lpVtbl[3].AddRef)(v10, &pv) >= 0 )
          {
            for ( i = 0; i < *(_DWORD *)pv; ++i )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              AvProviderValues = DdcProtectionStateHelper::GetAvProviderValues(
                                   (struct tagWSC_AV_PRODUCT_INFO *)(*((_QWORD *)pv + 1) + 80LL * i),
                                   &v47);
              if ( AvProviderValues < 0 )
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v14,
                    v13,
                    AvProviderValues,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                    2,
                    "CHR(GetAvProviderValues(&pProducts->pList[i], pJsonValue.ReleaseAndGetAddressOf()))");
                goto LABEL_40;
              }
              AvProviderValues = (*(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v53 + 104LL))(
                                   v53,
                                   v47);
              if ( AvProviderValues < 0 )
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v16,
                    v15,
                    AvProviderValues,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                    3,
                    "CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))");
                goto LABEL_40;
              }
            }
          }
        }
        v56 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonValue",
          0x1Cu,
          0x1Bu);
        AvProviderValues = RoGetActivationFactory(v56, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v50);
        if ( AvProviderValues >= 0 )
        {
          v19 = v50;
          v20 = *(__int64 (__fastcall **)(__int64, PVOID, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)v50 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
          v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v54, v21);
          AvProviderValues = v20(v19, v22[1].Reserved.Reserved1, &v47);
          if ( AvProviderValues >= 0 )
          {
            v26 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)a1 + 56LL);
            v27 = v47;
            v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    (const WCHAR **)off_18002B6A8,
                    v25);
            AvProviderValues = v26(a1, v28[1].Reserved.Reserved1, v27);
            if ( AvProviderValues >= 0 )
            {
              AvProviderValues = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                   &v49,
                                   (__int64)&v52);
              if ( AvProviderValues >= 0 )
              {
                v34 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                v35 = v52;
                v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        (const WCHAR **)off_18002B6A0,
                        v33);
                AvProviderValues = v34(a1, v36[1].Reserved.Reserved1, v35);
                if ( AvProviderValues < 0
                  && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v38,
                    v37,
                    AvProviderValues,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                    18,
                    "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_THREAT_PROTECTION_AV_PROVIDERS).Get(), pJs"
                    "onArrayAsValue.Get()))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v32,
                  v31,
                  AvProviderValues,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                  17,
                  "CHR(pJsonArray.As(&pJsonArrayAsValue))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v30,
                v29,
                AvProviderValues,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                16,
                "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_THIRD_PARTY_AV_ACTIVE).Get(), pJsonValue.Get()))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v24,
              v23,
              AvProviderValues,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
              15,
              "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszThirdPartyAvActive).Get(), pJsonValue.Releas"
              "eAndGetAddressOf()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v18,
            v17,
            AvProviderValues,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
            14,
            "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics"
            ".GetAddressOf()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          AvProviderValues,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
          237,
          "CHR(pJsonArray.As(&pJsonArrayAsVector))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        AvProviderValues,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        236,
        "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))");
    }
  }
  else
  {
    AvProviderValues = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_50;
    McTemplateU0dsqs_EventWriteTransfer(
      0,
      a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      234,
      "CPR(pProtectionState)");
  }
LABEL_40:
  v39 = pv;
  if ( pv )
  {
    if ( *((_QWORD *)pv + 1) )
    {
      v40 = 0;
      if ( *(_DWORD *)pv )
      {
        do
        {
          v41 = *((_QWORD *)v39 + 1);
          if ( *(_QWORD *)(v41 + 80LL * v40 + 8) )
          {
            CoTaskMemFree(*(LPVOID *)(v41 + 80LL * v40 + 8));
            *(_QWORD *)(*((_QWORD *)pv + 1) + 80LL * v40 + 8) = 0;
            v39 = pv;
          }
          v42 = *((_QWORD *)v39 + 1);
          if ( *(_QWORD *)(v42 + 80LL * v40 + 16) )
          {
            CoTaskMemFree(*(LPVOID *)(v42 + 80LL * v40 + 16));
            *(_QWORD *)(*((_QWORD *)pv + 1) + 80LL * v40 + 16) = 0;
            v39 = pv;
          }
          ++v40;
        }
        while ( v40 < *(_DWORD *)v39 );
      }
      CoTaskMemFree(*((LPVOID *)v39 + 1));
      *((_QWORD *)pv + 1) = 0;
      *(_DWORD *)pv = 0;
      v39 = pv;
    }
    CoTaskMemFree(v39);
    pv = 0;
  }
LABEL_50:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  v43 = v49;
  if ( v49 )
  {
    v49 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v43)[2])(v43);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  v44 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  return (unsigned int)AvProviderValues;
}

```

## disassembly

```asm
0x1800204a4  mov     [rsp-8+arg_8], rbx
0x1800204a9  mov     [rsp-8+arg_10], rsi
0x1800204ae  push    rbp
0x1800204af  push    rdi
0x1800204b0  push    r14
0x1800204b2  lea     rbp, [rsp-47h]
0x1800204b7  sub     rsp, 0A0h
0x1800204be  mov     rax, cs:__security_cookie
0x1800204c5  xor     rax, rsp
0x1800204c8  mov     [rbp+57h+var_18], rax
0x1800204cc  mov     rsi, rcx
0x1800204cf  xor     r14d, r14d
0x1800204d2  mov     [rbp+57h+var_58], r14
0x1800204d6  mov     [rbp+57h+pv], r14
0x1800204da  mov     [rbp+57h+var_70], r14d
0x1800204de  mov     [rbp+57h+var_60], r14
0x1800204e2  mov     [rbp+57h+var_78], r14
0x1800204e6  mov     [rbp+57h+var_68], r14
0x1800204ea  mov     [rbp+57h+var_48], r14
0x1800204ee  mov     [rbp+57h+var_50], r14
0x1800204f2  test    rcx, rcx
0x1800204f5  jnz     short loc_180020522
0x1800204f7  mov     ebx, 80070057h
0x1800204fc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020503  jz      loc_180020913
0x180020509  lea     rax, aCprPprotection; "CPR(pProtectionState)"
0x180020510  mov     [rsp+0B0h+var_88], rax
0x180020515  mov     [rsp+0B0h+var_90], 2EAh
0x18002051d  jmp     loc_18002085F
0x180020522  mov     [rbp+57h+var_20], r14
0x180020526  mov     r9d, 1Bh; unsigned int
0x18002052c  lea     r8d, [r9+1]; unsigned int
0x180020530  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x180020537  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002053b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020540  nop
0x180020541  lea     rdx, [rbp+57h+var_68]
0x180020545  mov     rcx, [rbp+57h+var_20]
0x180020549  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x18002054e  mov     ebx, eax
0x180020550  test    eax, eax
0x180020552  jns     short loc_18002057A
0x180020554  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002055b  jz      loc_18002086E
0x180020561  lea     rax, aChrActivateins_9; "CHR(ActivateInstance(HStringReference(R"...
0x180020568  mov     [rsp+0B0h+var_88], rax
0x18002056d  mov     [rsp+0B0h+var_90], 2ECh
0x180020575  jmp     loc_18002085F
0x18002057a  lea     rdx, [rbp+57h+var_48]
0x18002057e  lea     rcx, [rbp+57h+var_68]
0x180020582  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180020587  mov     ebx, eax
0x180020589  test    eax, eax
0x18002058b  jns     short loc_1800205B3
0x18002058d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020594  jz      loc_18002086E
0x18002059a  lea     rax, aChrPjsonarrayA; "CHR(pJsonArray.As(&pJsonArrayAsVector))"
0x1800205a1  mov     [rsp+0B0h+var_88], rax
0x1800205a6  mov     [rsp+0B0h+var_90], 2EDh
0x1800205ae  jmp     loc_18002085F
0x1800205b3  lea     rcx, [rbp+57h+var_58]
0x1800205b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800205bc  lea     r8, [rbp+57h+var_58]
0x1800205c0  call    ??$CreateInstanceWithCloak@UIThreatProtectionShield@@@@YAJAEBU_GUID@@0PEAPEAUIThreatProtectionShield@@@Z; CreateInstanceWithCloak<IThreatProtectionShield>(_GUID const &,_GUID const &,IThreatProtectionShield * *)
0x1800205c5  test    eax, eax
0x1800205c7  js      loc_1800206B7
0x1800205cd  mov     rbx, [rbp+57h+var_58]
0x1800205d1  mov     rax, [rbx]
0x1800205d4  lea     rdx, [rbp+57h+var_70]
0x1800205d8  mov     rcx, rbx
0x1800205db  mov     rax, [rax+38h]
0x1800205df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205e4  test    eax, eax
0x1800205e6  js      short loc_1800205EE
0x1800205e8  lea     rcx, [rbp+57h+var_70]
0x1800205ec  jmp     short loc_1800205F0
0x1800205ee  xor     ecx, ecx; int *
0x1800205f0  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x1800205f5  mov     [rbp+57h+var_40], rax
0x1800205f9  mov     rax, [rbx]
0x1800205fc  lea     rdx, [rbp+57h+pv]
0x180020600  mov     rcx, rbx
0x180020603  mov     rax, [rax+50h]
0x180020607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002060c  test    eax, eax
0x18002060e  js      loc_1800206C2
0x180020614  mov     edi, r14d
0x180020617  mov     rax, [rbp+57h+pv]
0x18002061b  cmp     edi, [rax]
0x18002061d  jnb     loc_1800206C2
0x180020623  lea     rcx, [rbp+57h+var_78]
0x180020627  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002062c  mov     eax, edi
0x18002062e  lea     rcx, [rax+rax*4]
0x180020632  shl     rcx, 4
0x180020636  mov     rax, [rbp+57h+pv]
0x18002063a  add     rcx, [rax+8]; struct tagWSC_AV_PRODUCT_INFO *
0x18002063e  lea     rdx, [rbp+57h+var_78]; struct Windows::Data::Json::IJsonValue **
0x180020642  call    ?GetAvProviderValues@DdcProtectionStateHelper@@CAJPEAUtagWSC_AV_PRODUCT_INFO@@PEAPEAUIJsonValue@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetAvProviderValues(tagWSC_AV_PRODUCT_INFO *,Windows::Data::Json::IJsonValue * *)
0x180020647  mov     ebx, eax
0x180020649  test    eax, eax
0x18002064b  js      short loc_180020691
0x18002064d  mov     rcx, [rbp+57h+var_48]
0x180020651  mov     rax, [rcx]
0x180020654  mov     rdx, [rbp+57h+var_78]
0x180020658  mov     rax, [rax+68h]
0x18002065c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020661  mov     ebx, eax
0x180020663  test    eax, eax
0x180020665  js      short loc_18002066B
0x180020667  inc     edi
0x180020669  jmp     short loc_180020617
0x18002066b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020672  jz      loc_18002086E
0x180020678  lea     rax, aChrPjsonarraya; "CHR(pJsonArrayAsVector->Append(pJsonVal"...
0x18002067f  mov     [rsp+0B0h+var_88], rax
0x180020684  mov     [rsp+0B0h+var_90], 303h
0x18002068c  jmp     loc_18002085F
0x180020691  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020698  jz      loc_18002086E
0x18002069e  lea     rax, aChrGetavprovid; "CHR(GetAvProviderValues(&pProducts->pLi"...
0x1800206a5  mov     [rsp+0B0h+var_88], rax
0x1800206aa  mov     [rsp+0B0h+var_90], 302h
0x1800206b2  jmp     loc_18002085F
0x1800206b7  xor     ecx, ecx; int *
0x1800206b9  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x1800206be  mov     [rbp+57h+var_40], rax
0x1800206c2  mov     [rbp+57h+var_20], r14
0x1800206c6  mov     r9d, 1Bh; unsigned int
0x1800206cc  lea     r8d, [r9+1]; unsigned int
0x1800206d0  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800206d7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800206db  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800206e0  lea     r8, [rbp+57h+var_60]
0x1800206e4  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800206eb  mov     rcx, [rbp+57h+var_20]
0x1800206ef  call    cs:__imp_RoGetActivationFactory
0x1800206f5  mov     ebx, eax
0x1800206f7  test    eax, eax
0x1800206f9  jns     short loc_180020721
0x1800206fb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020702  jz      loc_18002086E
0x180020708  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18002070f  mov     [rsp+0B0h+var_88], rax
0x180020714  mov     [rsp+0B0h+var_90], 30Eh
0x18002071c  jmp     loc_18002085F
0x180020721  mov     rdi, [rbp+57h+var_60]
0x180020725  mov     rax, [rdi]
0x180020728  mov     rbx, [rax+50h]
0x18002072c  lea     rcx, [rbp+57h+var_78]
0x180020730  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020735  lea     rdx, [rbp+57h+var_40]
0x180020739  lea     rcx, [rbp+57h+hstringHeader]
0x18002073d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020742  nop
0x180020743  lea     r8, [rbp+57h+var_78]
0x180020747  mov     rdx, [rax+18h]
0x18002074b  mov     rcx, rdi
0x18002074e  mov     rax, rbx
0x180020751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020756  mov     ebx, eax
0x180020758  test    eax, eax
0x18002075a  jns     short loc_180020782
0x18002075c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020763  jz      loc_18002086E
0x180020769  lea     rax, aChrPjsonvalues_7; "CHR(pJsonValueStatics->CreateStringValu"...
0x180020770  mov     [rsp+0B0h+var_88], rax
0x180020775  mov     [rsp+0B0h+var_90], 30Fh
0x18002077d  jmp     loc_18002085F
0x180020782  mov     rax, [rsi]
0x180020785  mov     rdi, [rax+38h]
0x180020789  mov     rbx, [rbp+57h+var_78]
0x18002078d  lea     rdx, off_18002B6A8; "ThreatProtectionThirdPartyAvActive"
0x180020794  lea     rcx, [rbp+57h+hstringHeader]
0x180020798  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002079d  nop
0x18002079e  mov     r8, rbx
0x1800207a1  mov     rdx, [rax+18h]
0x1800207a5  mov     rcx, rsi
0x1800207a8  mov     rax, rdi
0x1800207ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207b0  mov     ebx, eax
0x1800207b2  test    eax, eax
0x1800207b4  jns     short loc_1800207DC
0x1800207b6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800207bd  jz      loc_18002086E
0x1800207c3  lea     rax, aChrPprotection; "CHR(pProtectionState->SetNamedValue(HSt"...
0x1800207ca  mov     [rsp+0B0h+var_88], rax
0x1800207cf  mov     [rsp+0B0h+var_90], 310h
0x1800207d7  jmp     loc_18002085F
0x1800207dc  lea     rdx, [rbp+57h+var_50]
0x1800207e0  lea     rcx, [rbp+57h+var_68]
0x1800207e4  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800207e9  mov     ebx, eax
0x1800207eb  test    eax, eax
0x1800207ed  jns     short loc_18002080E
0x1800207ef  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800207f6  jz      short loc_18002086E
0x1800207f8  lea     rax, aChrPjsonarrayA_0; "CHR(pJsonArray.As(&pJsonArrayAsValue))"
0x1800207ff  mov     [rsp+0B0h+var_88], rax
0x180020804  mov     [rsp+0B0h+var_90], 311h
0x18002080c  jmp     short loc_18002085F
0x18002080e  mov     rax, [rsi]
0x180020811  mov     rdi, [rax+38h]
0x180020815  mov     rbx, [rbp+57h+var_50]
0x180020819  lea     rdx, off_18002B6A0; "ThreatProtectionAvProviders"
0x180020820  lea     rcx, [rbp+57h+hstringHeader]
0x180020824  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020829  nop
0x18002082a  mov     r8, rbx
0x18002082d  mov     rdx, [rax+18h]
0x180020831  mov     rcx, rsi
0x180020834  mov     rax, rdi
0x180020837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002083c  mov     ebx, eax
0x18002083e  test    eax, eax
0x180020840  jns     short loc_18002086E
0x180020842  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020849  jz      short loc_18002086E
0x18002084b  lea     rax, aChrPprotection_8; "CHR(pProtectionState->SetNamedValue(HSt"...
0x180020852  mov     [rsp+0B0h+var_88], rax
0x180020857  mov     [rsp+0B0h+var_90], 312h
0x18002085f  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180020866  mov     r8d, ebx
0x180020869  call    McTemplateU0dsqs_EventWriteTransfer
0x18002086e  mov     rcx, [rbp+57h+pv]
0x180020872  test    rcx, rcx
0x180020875  jz      loc_180020913
0x18002087b  cmp     [rcx+8], r14
0x18002087f  jz      loc_180020909
0x180020885  mov     esi, r14d
0x180020888  cmp     [rcx], r14d
0x18002088b  jbe     short loc_1800208EC
0x18002088d  mov     eax, esi
0x18002088f  lea     rdi, [rax+rax*4]
0x180020893  add     rdi, rdi
0x180020896  mov     rax, [rcx+8]
0x18002089a  mov     rdx, [rax+rdi*8+8]
0x18002089f  test    rdx, rdx
0x1800208a2  jz      short loc_1800208BE
0x1800208a4  mov     rcx, rdx; pv
0x1800208a7  call    cs:__imp_CoTaskMemFree
0x1800208ad  mov     rax, [rbp+57h+pv]
0x1800208b1  mov     rcx, [rax+8]
0x1800208b5  mov     [rcx+rdi*8+8], r14
0x1800208ba  mov     rcx, [rbp+57h+pv]
0x1800208be  mov     rax, [rcx+8]
0x1800208c2  mov     rdx, [rax+rdi*8+10h]
0x1800208c7  test    rdx, rdx
0x1800208ca  jz      short loc_1800208E6
0x1800208cc  mov     rcx, rdx; pv
0x1800208cf  call    cs:__imp_CoTaskMemFree
0x1800208d5  mov     rax, [rbp+57h+pv]
0x1800208d9  mov     rcx, [rax+8]
0x1800208dd  mov     [rcx+rdi*8+10h], r14
0x1800208e2  mov     rcx, [rbp+57h+pv]
0x1800208e6  inc     esi
0x1800208e8  cmp     esi, [rcx]
0x1800208ea  jb      short loc_18002088D
0x1800208ec  mov     rcx, [rcx+8]; pv
0x1800208f0  call    cs:__imp_CoTaskMemFree
0x1800208f6  mov     rax, [rbp+57h+pv]
0x1800208fa  mov     [rax+8], r14
0x1800208fe  mov     rax, [rbp+57h+pv]
0x180020902  mov     [rax], r14d
0x180020905  mov     rcx, [rbp+57h+pv]; pv
0x180020909  call    cs:__imp_CoTaskMemFree
0x18002090f  mov     [rbp+57h+pv], r14
0x180020913  lea     rcx, [rbp+57h+var_50]
0x180020917  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002091c  nop
0x18002091d  lea     rcx, [rbp+57h+var_48]
0x180020921  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020926  nop
0x180020927  mov     rcx, [rbp+57h+var_68]
0x18002092b  test    rcx, rcx
0x18002092e  jz      short loc_180020941
0x180020930  mov     [rbp+57h+var_68], r14
0x180020934  mov     rax, [rcx]
0x180020937  mov     rax, [rax+10h]
0x18002093b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020940  nop
0x180020941  lea     rcx, [rbp+57h+var_78]
0x180020945  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002094a  nop
0x18002094b  mov     rcx, [rbp+57h+var_60]
0x18002094f  test    rcx, rcx
0x180020952  jz      short loc_180020965
0x180020954  mov     [rbp+57h+var_60], r14
0x180020958  mov     rax, [rcx]
0x18002095b  mov     rax, [rax+10h]
0x18002095f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020964  nop
0x180020965  lea     rcx, [rbp+57h+var_58]
0x180020969  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002096e  mov     eax, ebx
0x180020970  mov     rcx, [rbp+57h+var_18]
0x180020974  xor     rcx, rsp; StackCookie
0x180020977  call    __security_check_cookie
0x18002097c  lea     r11, [rsp+0B0h+var_10]
  ... truncated ...
```
