# DdcProtectionStateHelper::GetAvProviderValues(tagWSC_AV_PRODUCT_INFO *,Windows::Data::Json::IJsonValue * *)

- ea: `0x18001e164`
- end: `0x18001e806`
- name: `?GetAvProviderValues@DdcProtectionStateHelper@@CAJPEAUtagWSC_AV_PRODUCT_INFO@@PEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `1698`
- prototype: `__int64 __fastcall(struct tagWSC_AV_PRODUCT_INFO *, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800204a4`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x1800139c8`
- `0x180013b38`
- `0x18001e164`
- `0x18001f6fc`
- `0x18001f734`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e363`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e363`

## string_xrefs

- `0x18001e344`: `Windows.Data.Json.JsonValue`
- `0x18001e238`: `Windows.Data.Json.JsonObject`
- `0x18001e37c`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18001e269`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18001e768`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x18001e1cd`: `CPR(ppJsonValue)`
- `0x18001e20e`: `CBR(*ppJsonValue == nullptr)`
- `0x18001e1e1`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001e3dd`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszProviderName).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001e43b`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_NAME).Get(), pJsonValue.Get()))`
- `0x18001e49c`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszRtpStatus).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001e4fa`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_RTP_STATUS).Get(), pJsonValue.Get()))`
- `0x18001e55b`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszSignatureStatus).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001e5b9`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_SIGNATURE_STATUS).Get(), pJsonValue.Get()))`
- `0x18001e61a`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszHealth).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001e678`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_HEALTH).Get(), pJsonValue.Get()))`
- `0x18001e6d9`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszStatus).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001e733`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_STATUS).Get(), pJsonValue.Get()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcProtectionStateHelper::GetAvProviderValues(
        struct tagWSC_AV_PRODUCT_INFO *a1,
        struct Windows::Data::Json::IJsonValue **a2)
{
  int v4; // r8d
  int ActivationFactory; // ebx
  const WCHAR *v6; // rax
  const WCHAR *v7; // rdx
  const WCHAR *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, PVOID, __int64 *); // rbx
  char v12; // r8
  HSTRING_HEADER *v13; // rax
  char v14; // r8
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64); // rdi
  __int64 v17; // rbx
  HSTRING_HEADER *v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, PVOID, __int64 *); // rbx
  char v21; // r8
  HSTRING_HEADER *v22; // rax
  char v23; // r8
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v25)(_QWORD, GUID *, __int64); // rdi
  __int64 v26; // rbx
  HSTRING_HEADER *v27; // rax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, PVOID, __int64 *); // rbx
  char v30; // r8
  HSTRING_HEADER *v31; // rax
  char v32; // r8
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v34)(_QWORD, GUID *, __int64); // rdi
  __int64 v35; // rbx
  HSTRING_HEADER *v36; // rax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, PVOID, __int64 *); // rbx
  char v39; // r8
  HSTRING_HEADER *v40; // rax
  char v41; // r8
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v43)(_QWORD, GUID *, __int64); // rdi
  __int64 v44; // rbx
  HSTRING_HEADER *v45; // rax
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, PVOID, __int64 *); // rbx
  char v48; // r8
  HSTRING_HEADER *v49; // rax
  char v50; // r8
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v52)(_QWORD, GUID *, __int64); // rdi
  __int64 v53; // rbx
  HSTRING_HEADER *v54; // rax
  struct Windows::Data::Json::IJsonValue *v55; // rax
  __int64 (__fastcall ***v56)(_QWORD, GUID *, __int64); // rcx
  __int64 v57; // rcx
  char v59; // [rsp+20h] [rbp-39h]
  const char *v60; // [rsp+28h] [rbp-31h]
  __int64 v61; // [rsp+30h] [rbp-29h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-21h] BYREF
  __int64 v63; // [rsp+40h] [rbp-19h] BYREF
  struct Windows::Data::Json::IJsonValue *v64; // [rsp+48h] [rbp-11h] BYREF
  const WCHAR *v65; // [rsp+50h] [rbp-9h] BYREF
  const WCHAR *v66; // [rsp+58h] [rbp-1h] BYREF
  const WCHAR *v67; // [rsp+60h] [rbp+7h] BYREF
  const WCHAR *PillarHealthMapping; // [rsp+68h] [rbp+Fh] BYREF
  const WCHAR *PillarStatusFlagMapping; // [rsp+70h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v71; // [rsp+90h] [rbp+37h]

  v63 = 0;
  v61 = 0;
  v62 = 0;
  v64 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_68;
    v60 = "CPR(ppJsonValue)";
    v59 = -70;
    goto LABEL_4;
  }
  if ( !*a2 )
  {
    v71 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v71, &v62);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_68;
      v60 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))";
      v59 = -66;
      goto LABEL_11;
    }
    v6 = (const WCHAR *)&qword_180033BD8;
    if ( *((_QWORD *)a1 + 1) )
      v6 = (const WCHAR *)*((_QWORD *)a1 + 1);
    v66 = v6;
    v7 = L"Unknown";
    if ( a1 )
    {
      if ( *(_DWORD *)a1 )
      {
        switch ( *(_DWORD *)a1 )
        {
          case 1:
            v8 = L"Off";
            break;
          case 2:
            v8 = L"Snoozed";
            break;
          case 3:
            v8 = L"Expired";
            break;
          default:
            v8 = L"Unknown";
            break;
        }
      }
      else
      {
        v8 = L"On";
      }
      v65 = v8;
      v9 = (__int64)a1 + 4;
      if ( a1 == (struct tagWSC_AV_PRODUCT_INFO *)-4LL )
        goto LABEL_31;
    }
    else
    {
      v65 = L"Unknown";
      v9 = 4;
    }
    if ( *(_DWORD *)v9 )
    {
      if ( *(_DWORD *)v9 == 1 )
        v7 = L"UpToDate";
    }
    else
    {
      v7 = L"OutOfDate";
    }
LABEL_31:
    v67 = v7;
    PillarHealthMapping = (const WCHAR *)GetPillarHealthMapping(*((unsigned int *)a1 + 9));
    PillarStatusFlagMapping = (const WCHAR *)GetPillarStatusFlagMapping(*((unsigned int *)a1 + 8));
    v71 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = RoGetActivationFactory(v71, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v63);
    if ( ActivationFactory >= 0 )
    {
      v10 = v63;
      v11 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v63 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
      v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v66, v12);
      ActivationFactory = v11(v10, v13[1].Reserved.Reserved1, &v61);
      if ( ActivationFactory >= 0 )
      {
        v15 = v62;
        v16 = (*v62)[7];
        v17 = v61;
        v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)off_18002B698,
                v14);
        ActivationFactory = v16(v15, (GUID *)v18[1].Reserved.Reserved1, v17);
        if ( ActivationFactory >= 0 )
        {
          v19 = v63;
          v20 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v63 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
          v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v65, v21);
          ActivationFactory = v20(v19, v22[1].Reserved.Reserved1, &v61);
          if ( ActivationFactory >= 0 )
          {
            v24 = v62;
            v25 = (*v62)[7];
            v26 = v61;
            v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    (const WCHAR **)off_18002B690,
                    v23);
            ActivationFactory = v25(v24, (GUID *)v27[1].Reserved.Reserved1, v26);
            if ( ActivationFactory >= 0 )
            {
              v28 = v63;
              v29 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v63 + 80LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
              v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v67, v30);
              ActivationFactory = v29(v28, v31[1].Reserved.Reserved1, &v61);
              if ( ActivationFactory >= 0 )
              {
                v33 = v62;
                v34 = (*v62)[7];
                v35 = v61;
                v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        (const WCHAR **)off_18002B688,
                        v32);
                ActivationFactory = v34(v33, (GUID *)v36[1].Reserved.Reserved1, v35);
                if ( ActivationFactory >= 0 )
                {
                  v37 = v63;
                  v38 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v63 + 80LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
                  v40 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                          &hstringHeader,
                          &PillarHealthMapping,
                          v39);
                  ActivationFactory = v38(v37, v40[1].Reserved.Reserved1, &v61);
                  if ( ActivationFactory >= 0 )
                  {
                    v42 = v62;
                    v43 = (*v62)[7];
                    v44 = v61;
                    v45 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                            &hstringHeader,
                            (const WCHAR **)off_18002B680,
                            v41);
                    ActivationFactory = v43(v42, (GUID *)v45[1].Reserved.Reserved1, v44);
                    if ( ActivationFactory >= 0 )
                    {
                      v46 = v63;
                      v47 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v63 + 80LL);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
                      v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                              &hstringHeader,
                              &PillarStatusFlagMapping,
                              v48);
                      ActivationFactory = v47(v46, v49[1].Reserved.Reserved1, &v61);
                      if ( ActivationFactory >= 0 )
                      {
                        v51 = v62;
                        v52 = (*v62)[7];
                        v53 = v61;
                        v54 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                &hstringHeader,
                                (const WCHAR **)off_18002B678,
                                v50);
                        ActivationFactory = v52(v51, (GUID *)v54[1].Reserved.Reserved1, v53);
                        if ( ActivationFactory >= 0 )
                        {
                          ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                                &v62,
                                                (__int64)&v64);
                          if ( ActivationFactory >= 0 )
                          {
                            v55 = v64;
                            v64 = 0;
                            *a2 = v55;
                            goto LABEL_68;
                          }
                          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                            goto LABEL_68;
                          v60 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
                          v59 = -43;
                        }
                        else
                        {
                          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                            goto LABEL_68;
                          v60 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_STATUS).Get(), pJsonValue.Get()))";
                          v59 = -46;
                        }
                      }
                      else
                      {
                        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                          goto LABEL_68;
                        v60 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszStatus).Get(), pJsonValue.Re"
                              "leaseAndGetAddressOf()))";
                        v59 = -47;
                      }
                    }
                    else
                    {
                      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                        goto LABEL_68;
                      v60 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_HEALTH).Get(), pJsonValue.Get()))";
                      v59 = -48;
                    }
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                      goto LABEL_68;
                    v60 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszHealth).Get(), pJsonValue.Releas"
                          "eAndGetAddressOf()))";
                    v59 = -49;
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_68;
                  v60 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_SIGNATURE_STATUS).Get(), pJsonValue.Get()))";
                  v59 = -50;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                  goto LABEL_68;
                v60 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszSignatureStatus).Get(), pJsonValue.R"
                      "eleaseAndGetAddressOf()))";
                v59 = -51;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_68;
              v60 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_RTP_STATUS).Get(), pJsonValue.Get()))";
              v59 = -52;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_68;
            v60 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszRtpStatus).Get(), pJsonValue.ReleaseAndGetAddressOf()))";
            v59 = -53;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_68;
          v60 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_AV_PROVIDER_NAME).Get(), pJsonValue.Get()))";
          v59 = -54;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_68;
        v60 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszProviderName).Get(), pJsonValue.ReleaseAndGetAddressOf()))";
        v59 = -55;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_68;
      v60 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics"
            ".GetAddressOf()))";
      v59 = -56;
    }
LABEL_11:
    v4 = ActivationFactory;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      v4,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      v59,
      v60);
    goto LABEL_68;
  }
  ActivationFactory = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      187,
      "CBR(*ppJsonValue == nullptr)");
LABEL_68:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  v56 = v62;
  if ( v62 )
  {
    v62 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v56)[2])(v56);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  v57 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001e164  mov     [rsp-8+arg_10], rbx
0x18001e169  mov     [rsp-8+arg_18], rsi
0x18001e16e  push    rbp
0x18001e16f  push    rdi
0x18001e170  push    r14
0x18001e172  lea     rbp, [rsp-47h]
0x18001e177  sub     rsp, 0A0h
0x18001e17e  mov     rax, cs:__security_cookie
0x18001e185  xor     rax, rsp
0x18001e188  mov     [rbp+57h+var_18], rax
0x18001e18c  mov     r14, rdx
0x18001e18f  mov     rdi, rcx
0x18001e192  mov     [rbp+57h+var_70], 0
0x18001e19a  mov     [rbp+57h+var_80], 0
0x18001e1a2  mov     [rbp+57h+var_78], 0
0x18001e1aa  mov     [rbp+57h+var_68], 0
0x18001e1b2  test    rdx, rdx
0x18001e1b5  jnz     short loc_18001E1F2
0x18001e1b7  mov     r8d, 80070057h
0x18001e1bd  mov     ebx, r8d
0x18001e1c0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e1c7  jz      loc_18001E790
0x18001e1cd  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x18001e1d4  mov     [rsp+0B0h+var_88], rax
0x18001e1d9  mov     dword ptr [rsp+0B0h+var_90], 2BAh
0x18001e1e1  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001e1e8  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e1ed  jmp     loc_18001E790
0x18001e1f2  cmp     qword ptr [rdx], 0
0x18001e1f6  jz      short loc_18001E224
0x18001e1f8  mov     r8d, 80070057h
0x18001e1fe  mov     ebx, r8d
0x18001e201  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e208  jz      loc_18001E790
0x18001e20e  lea     rax, aCbrPpjsonvalue_0; "CBR(*ppJsonValue == nullptr)"
0x18001e215  mov     [rsp+0B0h+var_88], rax
0x18001e21a  mov     dword ptr [rsp+0B0h+var_90], 2BBh
0x18001e222  jmp     short loc_18001E1E1
0x18001e224  mov     [rbp+57h+var_20], 0
0x18001e22c  mov     esi, 1Ch
0x18001e231  mov     r9d, esi; unsigned int
0x18001e234  lea     r8d, [rsi+1]; unsigned int
0x18001e238  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001e23f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001e243  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001e248  nop
0x18001e249  lea     rdx, [rbp+57h+var_78]
0x18001e24d  mov     rcx, [rbp+57h+var_20]
0x18001e251  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18001e256  mov     ebx, eax
0x18001e258  test    eax, eax
0x18001e25a  jns     short loc_18001E285
0x18001e25c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e263  jz      loc_18001E790
0x18001e269  lea     rax, aChrActivateins_5; "CHR(ActivateInstance(HStringReference(R"...
0x18001e270  mov     [rsp+0B0h+var_88], rax
0x18001e275  mov     dword ptr [rsp+0B0h+var_90], 2BEh
0x18001e27d  mov     r8d, ebx
0x18001e280  jmp     loc_18001E1E1
0x18001e285  lea     rax, qword_180033BD8
0x18001e28c  cmp     qword ptr [rdi+8], 0
0x18001e291  cmovnz  rax, [rdi+8]
0x18001e296  mov     [rbp+57h+var_58], rax
0x18001e29a  lea     rdx, aUnknown; "Unknown"
0x18001e2a1  test    rdi, rdi
0x18001e2a4  jz      short loc_18001E2F1
0x18001e2a6  mov     ecx, [rdi]
0x18001e2a8  test    ecx, ecx
0x18001e2aa  jz      short loc_18001E2DB
0x18001e2ac  sub     ecx, 1
0x18001e2af  jz      short loc_18001E2D2
0x18001e2b1  sub     ecx, 1
0x18001e2b4  jz      short loc_18001E2C9
0x18001e2b6  cmp     ecx, 1
0x18001e2b9  jz      short loc_18001E2C0
0x18001e2bb  mov     rax, rdx
0x18001e2be  jmp     short loc_18001E2E2
0x18001e2c0  lea     rax, aExpired; "Expired"
0x18001e2c7  jmp     short loc_18001E2E2
0x18001e2c9  lea     rax, aSnoozed; "Snoozed"
0x18001e2d0  jmp     short loc_18001E2E2
0x18001e2d2  lea     rax, aOff; "Off"
0x18001e2d9  jmp     short loc_18001E2E2
0x18001e2db  lea     rax, aOn; "On"
0x18001e2e2  mov     [rbp+57h+var_60], rax
0x18001e2e6  lea     rcx, [rdi+4]
0x18001e2ea  test    rcx, rcx
0x18001e2ed  jnz     short loc_18001E2F9
0x18001e2ef  jmp     short loc_18001E317
0x18001e2f1  mov     [rbp+57h+var_60], rdx
0x18001e2f5  lea     rcx, [rdi+4]
0x18001e2f9  mov     r8d, [rcx]
0x18001e2fc  test    r8d, r8d
0x18001e2ff  jz      short loc_18001E310
0x18001e301  cmp     r8d, 1
0x18001e305  jnz     short loc_18001E317
0x18001e307  lea     rdx, aUptodate; "UpToDate"
0x18001e30e  jmp     short loc_18001E317
0x18001e310  lea     rdx, aOutofdate; "OutOfDate"
0x18001e317  mov     [rbp+57h+var_50], rdx
0x18001e31b  mov     ecx, [rdi+24h]
0x18001e31e  call    ?GetPillarHealthMapping@@YAPEBGW4PillarHealth@@@Z; GetPillarHealthMapping(PillarHealth)
0x18001e323  mov     [rbp+57h+var_48], rax
0x18001e327  mov     ecx, [rdi+20h]
0x18001e32a  call    ?GetPillarStatusFlagMapping@@YAPEBGW4PillarStatusFlag@@@Z; GetPillarStatusFlagMapping(PillarStatusFlag)
0x18001e32f  mov     [rbp+57h+var_40], rax
0x18001e333  mov     [rbp+57h+var_20], 0
0x18001e33b  mov     r9d, 1Bh; unsigned int
0x18001e341  mov     r8d, esi; unsigned int
0x18001e344  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001e34b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001e34f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001e354  lea     r8, [rbp+57h+var_70]
0x18001e358  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001e35f  mov     rcx, [rbp+57h+var_20]
0x18001e363  call    cs:__imp_RoGetActivationFactory
0x18001e369  mov     ebx, eax
0x18001e36b  test    eax, eax
0x18001e36d  jns     short loc_18001E395
0x18001e36f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e376  jz      loc_18001E790
0x18001e37c  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18001e383  mov     [rsp+0B0h+var_88], rax
0x18001e388  mov     dword ptr [rsp+0B0h+var_90], 2C8h
0x18001e390  jmp     loc_18001E27D
0x18001e395  mov     rdi, [rbp+57h+var_70]
0x18001e399  mov     rax, [rdi]
0x18001e39c  mov     rbx, [rax+50h]
0x18001e3a0  lea     rcx, [rbp+57h+var_80]
0x18001e3a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e3a9  lea     rdx, [rbp+57h+var_58]
0x18001e3ad  lea     rcx, [rbp+57h+hstringHeader]
0x18001e3b1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e3b6  nop
0x18001e3b7  lea     r8, [rbp+57h+var_80]
0x18001e3bb  mov     rdx, [rax+18h]
0x18001e3bf  mov     rcx, rdi
0x18001e3c2  mov     rax, rbx
0x18001e3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3ca  mov     ebx, eax
0x18001e3cc  test    eax, eax
0x18001e3ce  jns     short loc_18001E3F6
0x18001e3d0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e3d7  jz      loc_18001E790
0x18001e3dd  lea     rax, aChrPjsonvalues_4; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001e3e4  mov     [rsp+0B0h+var_88], rax
0x18001e3e9  mov     dword ptr [rsp+0B0h+var_90], 2C9h
0x18001e3f1  jmp     loc_18001E27D
0x18001e3f6  mov     rsi, [rbp+57h+var_78]
0x18001e3fa  mov     rax, [rsi]
0x18001e3fd  mov     rdi, [rax+38h]
0x18001e401  mov     rbx, [rbp+57h+var_80]
0x18001e405  lea     rdx, off_18002B698; "AvProviderName"
0x18001e40c  lea     rcx, [rbp+57h+hstringHeader]
0x18001e410  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e415  nop
0x18001e416  mov     r8, rbx
0x18001e419  mov     rdx, [rax+18h]
0x18001e41d  mov     rcx, rsi
0x18001e420  mov     rax, rdi
0x18001e423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e428  mov     ebx, eax
0x18001e42a  test    eax, eax
0x18001e42c  jns     short loc_18001E454
0x18001e42e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e435  jz      loc_18001E790
0x18001e43b  lea     rax, aChrPjsonobject_13; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18001e442  mov     [rsp+0B0h+var_88], rax
0x18001e447  mov     dword ptr [rsp+0B0h+var_90], 2CAh
0x18001e44f  jmp     loc_18001E27D
0x18001e454  mov     rdi, [rbp+57h+var_70]
0x18001e458  mov     rax, [rdi]
0x18001e45b  mov     rbx, [rax+50h]
0x18001e45f  lea     rcx, [rbp+57h+var_80]
0x18001e463  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e468  lea     rdx, [rbp+57h+var_60]
0x18001e46c  lea     rcx, [rbp+57h+hstringHeader]
0x18001e470  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e475  nop
0x18001e476  lea     r8, [rbp+57h+var_80]
0x18001e47a  mov     rdx, [rax+18h]
0x18001e47e  mov     rcx, rdi
0x18001e481  mov     rax, rbx
0x18001e484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e489  mov     ebx, eax
0x18001e48b  test    eax, eax
0x18001e48d  jns     short loc_18001E4B5
0x18001e48f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e496  jz      loc_18001E790
0x18001e49c  lea     rax, aChrPjsonvalues_72; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001e4a3  mov     [rsp+0B0h+var_88], rax
0x18001e4a8  mov     dword ptr [rsp+0B0h+var_90], 2CBh
0x18001e4b0  jmp     loc_18001E27D
0x18001e4b5  mov     rsi, [rbp+57h+var_78]
0x18001e4b9  mov     rax, [rsi]
0x18001e4bc  mov     rdi, [rax+38h]
0x18001e4c0  mov     rbx, [rbp+57h+var_80]
0x18001e4c4  lea     rdx, off_18002B690; "AvProviderRtpStatus"
0x18001e4cb  lea     rcx, [rbp+57h+hstringHeader]
0x18001e4cf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e4d4  nop
0x18001e4d5  mov     r8, rbx
0x18001e4d8  mov     rdx, [rax+18h]
0x18001e4dc  mov     rcx, rsi
0x18001e4df  mov     rax, rdi
0x18001e4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4e7  mov     ebx, eax
0x18001e4e9  test    eax, eax
0x18001e4eb  jns     short loc_18001E513
0x18001e4ed  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e4f4  jz      loc_18001E790
0x18001e4fa  lea     rax, aChrPjsonobject_25; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18001e501  mov     [rsp+0B0h+var_88], rax
0x18001e506  mov     dword ptr [rsp+0B0h+var_90], 2CCh
0x18001e50e  jmp     loc_18001E27D
0x18001e513  mov     rdi, [rbp+57h+var_70]
0x18001e517  mov     rax, [rdi]
0x18001e51a  mov     rbx, [rax+50h]
0x18001e51e  lea     rcx, [rbp+57h+var_80]
0x18001e522  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e527  lea     rdx, [rbp+57h+var_50]
0x18001e52b  lea     rcx, [rbp+57h+hstringHeader]
0x18001e52f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e534  nop
0x18001e535  lea     r8, [rbp+57h+var_80]
0x18001e539  mov     rdx, [rax+18h]
0x18001e53d  mov     rcx, rdi
0x18001e540  mov     rax, rbx
0x18001e543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e548  mov     ebx, eax
0x18001e54a  test    eax, eax
0x18001e54c  jns     short loc_18001E574
0x18001e54e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e555  jz      loc_18001E790
0x18001e55b  lea     rax, aChrPjsonvalues_39; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001e562  mov     [rsp+0B0h+var_88], rax
0x18001e567  mov     dword ptr [rsp+0B0h+var_90], 2CDh
0x18001e56f  jmp     loc_18001E27D
0x18001e574  mov     rsi, [rbp+57h+var_78]
0x18001e578  mov     rax, [rsi]
0x18001e57b  mov     rdi, [rax+38h]
0x18001e57f  mov     rbx, [rbp+57h+var_80]
0x18001e583  lea     rdx, off_18002B688; "AvProviderSignatureStatus"
0x18001e58a  lea     rcx, [rbp+57h+hstringHeader]
0x18001e58e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e593  nop
0x18001e594  mov     r8, rbx
0x18001e597  mov     rdx, [rax+18h]
0x18001e59b  mov     rcx, rsi
0x18001e59e  mov     rax, rdi
0x18001e5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5a6  mov     ebx, eax
0x18001e5a8  test    eax, eax
0x18001e5aa  jns     short loc_18001E5D2
0x18001e5ac  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e5b3  jz      loc_18001E790
0x18001e5b9  lea     rax, aChrPjsonobject_15; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18001e5c0  mov     [rsp+0B0h+var_88], rax
0x18001e5c5  mov     dword ptr [rsp+0B0h+var_90], 2CEh
0x18001e5cd  jmp     loc_18001E27D
0x18001e5d2  mov     rdi, [rbp+57h+var_70]
0x18001e5d6  mov     rax, [rdi]
0x18001e5d9  mov     rbx, [rax+50h]
0x18001e5dd  lea     rcx, [rbp+57h+var_80]
0x18001e5e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e5e6  lea     rdx, [rbp+57h+var_48]
0x18001e5ea  lea     rcx, [rbp+57h+hstringHeader]
0x18001e5ee  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e5f3  nop
0x18001e5f4  lea     r8, [rbp+57h+var_80]
0x18001e5f8  mov     rdx, [rax+18h]
0x18001e5fc  mov     rcx, rdi
0x18001e5ff  mov     rax, rbx
0x18001e602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e607  mov     ebx, eax
0x18001e609  test    eax, eax
0x18001e60b  jns     short loc_18001E633
0x18001e60d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e614  jz      loc_18001E790
0x18001e61a  lea     rax, aChrPjsonvalues; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001e621  mov     [rsp+0B0h+var_88], rax
0x18001e626  mov     dword ptr [rsp+0B0h+var_90], 2CFh
0x18001e62e  jmp     loc_18001E27D
0x18001e633  mov     rsi, [rbp+57h+var_78]
0x18001e637  mov     rax, [rsi]
0x18001e63a  mov     rdi, [rax+38h]
0x18001e63e  mov     rbx, [rbp+57h+var_80]
0x18001e642  lea     rdx, off_18002B680; "AvProviderHealth"
0x18001e649  lea     rcx, [rbp+57h+hstringHeader]
0x18001e64d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e652  nop
0x18001e653  mov     r8, rbx
0x18001e656  mov     rdx, [rax+18h]
0x18001e65a  mov     rcx, rsi
0x18001e65d  mov     rax, rdi
0x18001e660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e665  mov     ebx, eax
0x18001e667  test    eax, eax
0x18001e669  jns     short loc_18001E691
0x18001e66b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
  ... truncated ...
```
