# DdcProtectionStateHelper::GetAssessmentValues(_tagHealthAdvisorAssessment,IHealthAdvisorShield *,Windows::Data::Json::IJsonObject *)

- ea: `0x18001dcfc`
- end: `0x18001e15b`
- name: `?GetAssessmentValues@DdcProtectionStateHelper@@CAJW4_tagHealthAdvisorAssessment@@PEAUIHealthAdvisorShield@@PEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `1119`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f23c`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x180013938`
- `0x180013ae8`
- `0x180013b38`
- `0x18001dc38`
- `0x18001dcfc`
- `0x18001f6fc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001dd83`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001dd83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0e2`

## string_xrefs

- `0x18001dd64`: `Windows.Data.Json.JsonValue`
- `0x18001ddc3`: `Windows.Data.Json.JsonArray`
- `0x18001dd9c`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18001ddf4`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))`
- `0x18001de2d`: `CHR(pJsonArray.As(&pJsonArrayAsVector))`
- `0x18001df47`: `CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))`
- `0x18001e066`: `CHR(pJsonArray.As(&pJsonArrayAsValue))`
- `0x18001e0ca`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001e031`: `CHR(pProtectionState->SetNamedValue(HStringReference(pwszJsonHealth).Get(), pJsonValue.Get()))`
- `0x18001de68`: `CHR(GetAssessmentFieldNames(eAssessment, &pwszJsonHealth, &pwszJsonStatus))`
- `0x18001df6d`: `CHR(pJsonValueStatics->CreateNumberValue(pAssessmentStatus[i].uiStatusCode, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001dfda`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAssessmentHealth).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001e0b6`: `CHR(pProtectionState->SetNamedValue(HStringReference(pwszJsonStatus).Get(), pJsonArrayAsValue.Get()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcProtectionStateHelper::GetAssessmentValues(unsigned int a1, __int64 a2, __int64 a3)
{
  int v6; // edx
  int v7; // ecx
  int ActivationFactory; // ebx
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  int v13; // edx
  int v14; // ecx
  int v15; // eax
  __int64 v16; // rcx
  unsigned int i; // esi
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, LPVOID, __int64 *); // rbx
  int v20; // edx
  int v21; // ecx
  int v22; // edx
  int v23; // ecx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, PVOID, __int64 *); // rbx
  char v26; // r8
  HSTRING_HEADER *v27; // rax
  int v28; // edx
  int v29; // ecx
  char v30; // r8
  __int64 (__fastcall *v31)(__int64, PVOID, __int64); // rdi
  __int64 v32; // rbx
  HSTRING_HEADER *v33; // rax
  int v34; // edx
  int v35; // ecx
  int v36; // edx
  int v37; // ecx
  char v38; // r8
  __int64 (__fastcall *v39)(__int64, PVOID, __int64); // rdi
  __int64 v40; // rbx
  HSTRING_HEADER *v41; // rax
  int v42; // edx
  int v43; // ecx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64); // rcx
  __int64 v45; // rcx
  __int64 v47; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v48; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v49; // [rsp+3Ch] [rbp-4Dh] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-49h] BYREF
  __int64 v51; // [rsp+48h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-39h] BYREF
  __int64 v53; // [rsp+58h] [rbp-31h] BYREF
  __int64 v54; // [rsp+60h] [rbp-29h] BYREF
  const WCHAR *PillarHealthMapping; // [rsp+68h] [rbp-21h] BYREF
  const WCHAR *v56; // [rsp+70h] [rbp-19h] BYREF
  const WCHAR *v57; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  __int64 v59; // [rsp+98h] [rbp+Fh]

  v56 = 0;
  v57 = 0;
  v48 = 1;
  v49 = 0;
  pv = 0;
  v51 = 0;
  v47 = 0;
  v50 = 0;
  v54 = 0;
  v53 = 0;
  v59 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v59, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v51);
  if ( ActivationFactory >= 0 )
  {
    v59 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonArray",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v59, &v50);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                            &v50,
                            (__int64)&v54);
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = DdcProtectionStateHelper::GetAssessmentFieldNames(a1, &v56, &v57);
        if ( ActivationFactory >= 0 )
        {
          if ( a2 )
          {
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, a1, &v48);
            v16 = v48;
            if ( v15 < 0 )
              v16 = 1;
            PillarHealthMapping = (const WCHAR *)GetPillarHealthMapping(v16);
            if ( (*(int (__fastcall **)(__int64, _QWORD, unsigned int *, LPVOID *))(*(_QWORD *)a2 + 88LL))(
                   a2,
                   a1,
                   &v49,
                   &pv) >= 0 )
            {
              for ( i = 0; i < v49; ++i )
              {
                v18 = v51;
                v19 = *(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)v51 + 72LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
                ActivationFactory = v19(v18, pv, &v47);
                if ( ActivationFactory < 0 )
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    McTemplateU0dsqs_EventWriteTransfer(
                      v21,
                      v20,
                      ActivationFactory,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                      167,
                      "CHR(pJsonValueStatics->CreateNumberValue(pAssessmentStatus[i].uiStatusCode, pJsonValue.ReleaseAndGetAddressOf()))");
                  goto LABEL_39;
                }
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 104LL))(v54, v47);
                if ( ActivationFactory < 0 )
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    McTemplateU0dsqs_EventWriteTransfer(
                      v23,
                      v22,
                      ActivationFactory,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                      168,
                      "CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))");
                  goto LABEL_39;
                }
              }
            }
          }
          else
          {
            PillarHealthMapping = (const WCHAR *)GetPillarHealthMapping(1);
          }
          v24 = v51;
          v25 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v51 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
          v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &PillarHealthMapping, v26);
          ActivationFactory = v25(v24, v27[1].Reserved.Reserved1, &v47);
          if ( ActivationFactory >= 0 )
          {
            v31 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
            v32 = v47;
            v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v56, v30);
            ActivationFactory = v31(a3, v33[1].Reserved.Reserved1, v32);
            if ( ActivationFactory >= 0 )
            {
              ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                    &v50,
                                    (__int64)&v53);
              if ( ActivationFactory >= 0 )
              {
                v39 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
                v40 = v53;
                v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v57, v38);
                ActivationFactory = v39(a3, v41[1].Reserved.Reserved1, v40);
                if ( ActivationFactory < 0
                  && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v43,
                    v42,
                    ActivationFactory,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                    182,
                    "CHR(pProtectionState->SetNamedValue(HStringReference(pwszJsonStatus).Get(), pJsonArrayAsValue.Get()))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v37,
                  v36,
                  ActivationFactory,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                  181,
                  "CHR(pJsonArray.As(&pJsonArrayAsValue))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v35,
                v34,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                179,
                "CHR(pProtectionState->SetNamedValue(HStringReference(pwszJsonHealth).Get(), pJsonValue.Get()))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v29,
              v28,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
              178,
              "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAssessmentHealth).Get(), pJsonValue.ReleaseA"
              "ndGetAddressOf()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v14,
            v13,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
            146,
            "CHR(GetAssessmentFieldNames(eAssessment, &pwszJsonHealth, &pwszJsonStatus))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
          144,
          "CHR(pJsonArray.As(&pJsonArrayAsVector))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        v9,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        143,
        "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      v6,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      142,
      "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
  }
LABEL_39:
  if ( pv )
    CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
  v44 = v50;
  if ( v50 )
  {
    v50 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v44)[2])(v44);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  v45 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001dcfc  push    rbp
0x18001dcfe  push    rbx
0x18001dcff  push    rsi
0x18001dd00  push    rdi
0x18001dd01  push    r12
0x18001dd03  push    r14
0x18001dd05  push    r15
0x18001dd07  lea     rbp, [rsp-27h]
0x18001dd0c  sub     rsp, 0B0h
0x18001dd13  mov     rax, cs:__security_cookie
0x18001dd1a  xor     rax, rsp
0x18001dd1d  mov     [rbp+57h+var_40], rax
0x18001dd21  mov     r14, r8
0x18001dd24  mov     rdi, rdx
0x18001dd27  mov     esi, ecx
0x18001dd29  xor     r15d, r15d
0x18001dd2c  mov     [rbp+57h+var_70], r15
0x18001dd30  mov     [rbp+57h+var_68], r15
0x18001dd34  lea     r12d, [r15+1]
0x18001dd38  mov     [rbp+57h+var_A8], r12d
0x18001dd3c  mov     [rbp+57h+var_A4], r15d
0x18001dd40  mov     [rbp+57h+pv], r15
0x18001dd44  mov     [rbp+57h+var_98], r15
0x18001dd48  mov     [rbp+57h+var_B0], r15
0x18001dd4c  mov     [rbp+57h+var_A0], r15
0x18001dd50  mov     [rbp+57h+var_80], r15
0x18001dd54  mov     [rbp+57h+var_88], r15
0x18001dd58  mov     [rbp+57h+var_48], r15
0x18001dd5c  lea     r9d, [r15+1Bh]; unsigned int
0x18001dd60  lea     r8d, [r15+1Ch]; unsigned int
0x18001dd64  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001dd6b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001dd6f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001dd74  lea     r8, [rbp+57h+var_98]
0x18001dd78  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001dd7f  mov     rcx, [rbp+57h+var_48]
0x18001dd83  call    cs:__imp_RoGetActivationFactory
0x18001dd89  mov     ebx, eax
0x18001dd8b  test    eax, eax
0x18001dd8d  jns     short loc_18001DDB5
0x18001dd8f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001dd96  jz      loc_18001E0D9
0x18001dd9c  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18001dda3  mov     [rsp+0E0h+var_B8], rax
0x18001dda8  mov     [rsp+0E0h+var_C0], 48Eh
0x18001ddb0  jmp     loc_18001E0CA
0x18001ddb5  mov     [rbp+57h+var_48], r15
0x18001ddb9  mov     r9d, 1Bh; unsigned int
0x18001ddbf  lea     r8d, [r9+1]; unsigned int
0x18001ddc3  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x18001ddca  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001ddce  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001ddd3  nop
0x18001ddd4  lea     rdx, [rbp+57h+var_A0]
0x18001ddd8  mov     rcx, [rbp+57h+var_48]
0x18001dddc  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x18001dde1  mov     ebx, eax
0x18001dde3  test    eax, eax
0x18001dde5  jns     short loc_18001DE0D
0x18001dde7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001ddee  jz      loc_18001E0D9
0x18001ddf4  lea     rax, aChrActivateins_9; "CHR(ActivateInstance(HStringReference(R"...
0x18001ddfb  mov     [rsp+0E0h+var_B8], rax
0x18001de00  mov     [rsp+0E0h+var_C0], 48Fh
0x18001de08  jmp     loc_18001E0CA
0x18001de0d  lea     rdx, [rbp+57h+var_80]
0x18001de11  lea     rcx, [rbp+57h+var_A0]
0x18001de15  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18001de1a  mov     ebx, eax
0x18001de1c  test    eax, eax
0x18001de1e  jns     short loc_18001DE46
0x18001de20  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001de27  jz      loc_18001E0D9
0x18001de2d  lea     rax, aChrPjsonarrayA; "CHR(pJsonArray.As(&pJsonArrayAsVector))"
0x18001de34  mov     [rsp+0E0h+var_B8], rax
0x18001de39  mov     [rsp+0E0h+var_C0], 490h
0x18001de41  jmp     loc_18001E0CA
0x18001de46  lea     r8, [rbp+57h+var_68]
0x18001de4a  lea     rdx, [rbp+57h+var_70]
0x18001de4e  mov     ecx, esi
0x18001de50  call    ?GetAssessmentFieldNames@DdcProtectionStateHelper@@CAJW4_tagHealthAdvisorAssessment@@PEAPEBG1@Z; DdcProtectionStateHelper::GetAssessmentFieldNames(_tagHealthAdvisorAssessment,ushort const * *,ushort const * *)
0x18001de55  mov     ebx, eax
0x18001de57  test    eax, eax
0x18001de59  jns     short loc_18001DE81
0x18001de5b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001de62  jz      loc_18001E0D9
0x18001de68  lea     rax, aChrGetassessme; "CHR(GetAssessmentFieldNames(eAssessment"...
0x18001de6f  mov     [rsp+0E0h+var_B8], rax
0x18001de74  mov     [rsp+0E0h+var_C0], 492h
0x18001de7c  jmp     loc_18001E0CA
0x18001de81  test    rdi, rdi
0x18001de84  jz      loc_18001DF86
0x18001de8a  mov     rax, [rdi]
0x18001de8d  lea     r8, [rbp+57h+var_A8]
0x18001de91  mov     edx, esi
0x18001de93  mov     rcx, rdi
0x18001de96  mov     rax, [rax+50h]
0x18001de9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de9f  test    eax, eax
0x18001dea1  mov     ecx, [rbp+57h+var_A8]
0x18001dea4  jns     short loc_18001DEA9
0x18001dea6  mov     ecx, r12d
0x18001dea9  call    ?GetPillarHealthMapping@@YAPEBGW4PillarHealth@@@Z; GetPillarHealthMapping(PillarHealth)
0x18001deae  mov     [rbp+57h+var_78], rax
0x18001deb2  mov     rax, [rdi]
0x18001deb5  lea     r9, [rbp+57h+pv]
0x18001deb9  lea     r8, [rbp+57h+var_A4]
0x18001debd  mov     edx, esi
0x18001debf  mov     rcx, rdi
0x18001dec2  mov     rax, [rax+58h]
0x18001dec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001decb  test    eax, eax
0x18001decd  js      loc_18001DF92
0x18001ded3  mov     esi, r15d
0x18001ded6  cmp     esi, [rbp+57h+var_A4]
0x18001ded9  jnb     loc_18001DF92
0x18001dedf  mov     rdi, [rbp+57h+var_98]
0x18001dee3  mov     rax, [rdi]
0x18001dee6  mov     rbx, [rax+48h]
0x18001deea  lea     rcx, [rbp+57h+var_B0]
0x18001deee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001def3  mov     r8d, esi
0x18001def6  mov     rdx, [rbp+57h+pv]
0x18001defa  mov     r8d, [rdx+r8*8]
0x18001defe  xorps   xmm1, xmm1
0x18001df01  cvtsi2sd xmm1, r8
0x18001df06  lea     r8, [rbp+57h+var_B0]
0x18001df0a  mov     rcx, rdi
0x18001df0d  mov     rax, rbx
0x18001df10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df15  mov     ebx, eax
0x18001df17  test    eax, eax
0x18001df19  js      short loc_18001DF60
0x18001df1b  mov     rcx, [rbp+57h+var_80]
0x18001df1f  mov     rax, [rcx]
0x18001df22  mov     rdx, [rbp+57h+var_B0]
0x18001df26  mov     rax, [rax+68h]
0x18001df2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df2f  mov     ebx, eax
0x18001df31  test    eax, eax
0x18001df33  js      short loc_18001DF3A
0x18001df35  add     esi, r12d
0x18001df38  jmp     short loc_18001DED6
0x18001df3a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001df41  jz      loc_18001E0D9
0x18001df47  lea     rax, aChrPjsonarraya; "CHR(pJsonArrayAsVector->Append(pJsonVal"...
0x18001df4e  mov     [rsp+0E0h+var_B8], rax
0x18001df53  mov     [rsp+0E0h+var_C0], 4A8h
0x18001df5b  jmp     loc_18001E0CA
0x18001df60  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001df67  jz      loc_18001E0D9
0x18001df6d  lea     rax, aChrPjsonvalues_29; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18001df74  mov     [rsp+0E0h+var_B8], rax
0x18001df79  mov     [rsp+0E0h+var_C0], 4A7h
0x18001df81  jmp     loc_18001E0CA
0x18001df86  mov     ecx, r12d
0x18001df89  call    ?GetPillarHealthMapping@@YAPEBGW4PillarHealth@@@Z; GetPillarHealthMapping(PillarHealth)
0x18001df8e  mov     [rbp+57h+var_78], rax
0x18001df92  mov     rdi, [rbp+57h+var_98]
0x18001df96  mov     rax, [rdi]
0x18001df99  mov     rbx, [rax+50h]
0x18001df9d  lea     rcx, [rbp+57h+var_B0]
0x18001dfa1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dfa6  lea     rdx, [rbp+57h+var_78]
0x18001dfaa  lea     rcx, [rbp+57h+hstringHeader]
0x18001dfae  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001dfb3  nop
0x18001dfb4  lea     r8, [rbp+57h+var_B0]
0x18001dfb8  mov     rdx, [rax+18h]
0x18001dfbc  mov     rcx, rdi
0x18001dfbf  mov     rax, rbx
0x18001dfc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfc7  mov     ebx, eax
0x18001dfc9  test    eax, eax
0x18001dfcb  jns     short loc_18001DFF3
0x18001dfcd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001dfd4  jz      loc_18001E0D9
0x18001dfda  lea     rax, aChrPjsonvalues_5; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001dfe1  mov     [rsp+0E0h+var_B8], rax
0x18001dfe6  mov     [rsp+0E0h+var_C0], 4B2h
0x18001dfee  jmp     loc_18001E0CA
0x18001dff3  mov     rax, [r14]
0x18001dff6  mov     rdi, [rax+38h]
0x18001dffa  mov     rbx, [rbp+57h+var_B0]
0x18001dffe  lea     rdx, [rbp+57h+var_70]
0x18001e002  lea     rcx, [rbp+57h+hstringHeader]
0x18001e006  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e00b  nop
0x18001e00c  mov     r8, rbx
0x18001e00f  mov     rdx, [rax+18h]
0x18001e013  mov     rcx, r14
0x18001e016  mov     rax, rdi
0x18001e019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e01e  mov     ebx, eax
0x18001e020  test    eax, eax
0x18001e022  jns     short loc_18001E04A
0x18001e024  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001e02b  jz      loc_18001E0D9
0x18001e031  lea     rax, aChrPprotection_19; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001e038  mov     [rsp+0E0h+var_B8], rax
0x18001e03d  mov     [rsp+0E0h+var_C0], 4B3h
0x18001e045  jmp     loc_18001E0CA
0x18001e04a  lea     rdx, [rbp+57h+var_88]
0x18001e04e  lea     rcx, [rbp+57h+var_A0]
0x18001e052  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18001e057  mov     ebx, eax
0x18001e059  test    eax, eax
0x18001e05b  jns     short loc_18001E07C
0x18001e05d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001e064  jz      short loc_18001E0D9
0x18001e066  lea     rax, aChrPjsonarrayA_0; "CHR(pJsonArray.As(&pJsonArrayAsValue))"
0x18001e06d  mov     [rsp+0E0h+var_B8], rax
0x18001e072  mov     [rsp+0E0h+var_C0], 4B5h
0x18001e07a  jmp     short loc_18001E0CA
0x18001e07c  mov     rax, [r14]
0x18001e07f  mov     rdi, [rax+38h]
0x18001e083  mov     rbx, [rbp+57h+var_88]
0x18001e087  lea     rdx, [rbp+57h+var_68]
0x18001e08b  lea     rcx, [rbp+57h+hstringHeader]
0x18001e08f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e094  nop
0x18001e095  mov     r8, rbx
0x18001e098  mov     rdx, [rax+18h]
0x18001e09c  mov     rcx, r14
0x18001e09f  mov     rax, rdi
0x18001e0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0a7  mov     ebx, eax
0x18001e0a9  test    eax, eax
0x18001e0ab  jns     short loc_18001E0D9
0x18001e0ad  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18001e0b4  jz      short loc_18001E0D9
0x18001e0b6  lea     rax, aChrPprotection_20; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001e0bd  mov     [rsp+0E0h+var_B8], rax
0x18001e0c2  mov     [rsp+0E0h+var_C0], 4B6h
0x18001e0ca  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001e0d1  mov     r8d, ebx
0x18001e0d4  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e0d9  mov     rcx, [rbp+57h+pv]; pv
0x18001e0dd  test    rcx, rcx
0x18001e0e0  jz      short loc_18001E0E9
0x18001e0e2  call    cs:__imp_CoTaskMemFree
0x18001e0e8  nop
0x18001e0e9  lea     rcx, [rbp+57h+var_88]
0x18001e0ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e0f2  nop
0x18001e0f3  lea     rcx, [rbp+57h+var_80]
0x18001e0f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e0fc  nop
0x18001e0fd  mov     rcx, [rbp+57h+var_A0]
0x18001e101  test    rcx, rcx
0x18001e104  jz      short loc_18001E117
0x18001e106  mov     [rbp+57h+var_A0], r15
0x18001e10a  mov     rax, [rcx]
0x18001e10d  mov     rax, [rax+10h]
0x18001e111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e116  nop
0x18001e117  lea     rcx, [rbp+57h+var_B0]
0x18001e11b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e120  nop
0x18001e121  mov     rcx, [rbp+57h+var_98]
0x18001e125  test    rcx, rcx
0x18001e128  jz      short loc_18001E13B
0x18001e12a  mov     [rbp+57h+var_98], r15
0x18001e12e  mov     rax, [rcx]
0x18001e131  mov     rax, [rax+10h]
0x18001e135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e13a  nop
0x18001e13b  mov     eax, ebx
0x18001e13d  mov     rcx, [rbp+57h+var_40]
0x18001e141  xor     rcx, rsp; StackCookie
0x18001e144  call    __security_check_cookie
0x18001e149  add     rsp, 0B0h
0x18001e150  pop     r15
0x18001e152  pop     r14
0x18001e154  pop     r12
0x18001e156  pop     rdi
0x18001e157  pop     rsi
0x18001e158  pop     rbx
0x18001e159  pop     rbp
0x18001e15a  retn
```
