# MdmHttpWrapper::CreateCommandChannelEntity(ushort const *,Windows::Data::Json::IJsonValue * *)

- ea: `0x18000ae24`
- end: `0x18000b347`
- name: `?CreateCommandChannelEntity@MdmHttpWrapper@@CAJPEBGPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `1315`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c38c`

## callees

- `0x180001520`
- `0x180006548`
- `0x18000ac7c`
- `0x18000acf4`
- `0x18000ae24`
- `0x180011414`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000aeeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000af4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b02e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b1d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000aeeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000af4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b02e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b1d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000af6a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000af6a`

## string_xrefs

- `0x18000af46`: `Windows.Data.Json.JsonValue`
- `0x18000aee4`: `Windows.Data.Json.JsonObject`
- `0x18000ae91`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000af19`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18000af83`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18000b26e`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x18000ae7d`: `CPR(ppJsonValue)`
- `0x18000aebd`: `CBR(*ppJsonValue == nullptr)`
- `0x18000aff2`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszChannelUrl).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000b027`: `CommandChannelUrl`
- `0x18000b062`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"CommandChannelUrl").Get(), pJsonValue.Get()))`
- `0x18000b0c4`: `CHR(pJsonValueStatics->CreateBooleanValue(false, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000b134`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"MpnsEnabled").Get(), pJsonValue.Get()))`
- `0x18000b19c`: `CHR(pJsonValueStatics->CreateNumberValue(1, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000b20c`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"PushChannelType").Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateCommandChannelEntity(
        const unsigned __int16 *a1,
        struct Windows::Data::Json::IJsonValue **a2)
{
  int v3; // r8d
  int ActivationFactory; // ebx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, PVOID, __int64 *); // rsi
  HSTRING_HEADER *v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v16)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v17; // r14
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rsi
  __int64 v23; // rcx
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v25)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v26; // r14
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, struct Windows::Data::Json::IJsonValue **, __int64 *); // rsi
  __int64 v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v34)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v35; // r14
  HRESULT v36; // eax
  int v37; // edx
  unsigned int v38; // r8d
  __int64 (__fastcall ***v39)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v40)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // rsi
  struct Windows::Data::Json::IJsonValue *v41; // rcx
  struct Windows::Data::Json::IJsonValue *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rcx
  struct Windows::Data::Json::IJsonValue *v45; // rcx
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, _QWORD); // rcx
  char v48; // [rsp+20h] [rbp-60h]
  const char *v49; // [rsp+28h] [rbp-58h]
  __int64 v50; // [rsp+30h] [rbp-50h] BYREF
  struct Windows::Data::Json::IJsonValue *v51; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v52)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // [rsp+40h] [rbp-40h] BYREF
  __int64 v53; // [rsp+48h] [rbp-38h] BYREF
  const WCHAR *v54; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF

  v54 = a1;
  v52 = 0;
  v51 = 0;
  v50 = 0;
  v53 = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_48;
    v49 = "CPR(ppJsonValue)";
    v48 = -105;
    goto LABEL_4;
  }
  if ( !*a2 )
  {
    string = 0;
    v5 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
    if ( v5 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
      __debugbreak();
    }
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)string, &v52);
    if ( ActivationFactory >= 0 )
    {
      string = 0;
      v8 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v8 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
        __debugbreak();
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v53);
      if ( ActivationFactory >= 0 )
      {
        v12 = v53;
        v13 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v53 + 80LL);
        v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v54, v11);
        ActivationFactory = v13(v12, v14[1].Reserved.Reserved1, &v50);
        if ( ActivationFactory >= 0 )
        {
          v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v52;
          v16 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v52;
          v17 = v50;
          string = 0;
          v18 = WindowsCreateStringReference(L"CommandChannelUrl", 0x11u, &hstringHeader, &string);
          if ( v18 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
            __debugbreak();
          }
          ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v16)[7](v15, string, v17);
          if ( ActivationFactory >= 0 )
          {
            v21 = v53;
            v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v53 + 64LL);
            v23 = v50;
            if ( v50 )
            {
              v50 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            }
            ActivationFactory = v22(v21, 0, &v50);
            if ( ActivationFactory >= 0 )
            {
              v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v52;
              v25 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v52;
              v26 = v50;
              string = 0;
              v27 = WindowsCreateStringReference(L"MpnsEnabled", 0xBu, &hstringHeader, &string);
              if ( v27 < 0 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
                JUMPOUT(0x18000B346LL);
              }
              ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v25)[7](v24, string, v26);
              if ( ActivationFactory >= 0 )
              {
                v30 = v53;
                v31 = *(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue **, __int64 *))(*(_QWORD *)v53 + 72LL);
                v32 = v50;
                if ( v50 )
                {
                  v50 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                }
                ActivationFactory = v31(v30, a2, &v50);
                if ( ActivationFactory >= 0 )
                {
                  v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v52;
                  v34 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v52;
                  v35 = v50;
                  string = 0;
                  v36 = WindowsCreateStringReference(L"PushChannelType", 0xFu, &hstringHeader, &string);
                  if ( v36 < 0 )
                  {
                    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v36, v37, v38);
                    __debugbreak();
                  }
                  ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v34)[7](v33, string, v35);
                  if ( ActivationFactory >= 0 )
                  {
                    v39 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v52;
                    v40 = **v52;
                    v41 = v51;
                    if ( v51 )
                    {
                      v51 = 0;
                      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v41 + 16LL))(v41);
                    }
                    ActivationFactory = v40(v39, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v51);
                    if ( ActivationFactory >= 0 )
                    {
                      v42 = v51;
                      v51 = 0;
                      *a2 = v42;
                      goto LABEL_48;
                    }
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                      goto LABEL_48;
                    v49 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
                    v48 = -87;
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                      goto LABEL_48;
                    v49 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"PushChannelType\").Get(), pJsonValue.Get()))";
                    v48 = -89;
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                    goto LABEL_48;
                  v49 = "CHR(pJsonValueStatics->CreateNumberValue(1, pJsonValue.ReleaseAndGetAddressOf()))";
                  v48 = -90;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                  goto LABEL_48;
                v49 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"MpnsEnabled\").Get(), pJsonValue.Get()))";
                v48 = -93;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                goto LABEL_48;
              v49 = "CHR(pJsonValueStatics->CreateBooleanValue(false, pJsonValue.ReleaseAndGetAddressOf()))";
              v48 = -94;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
              goto LABEL_48;
            v49 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"CommandChannelUrl\").Get(), pJsonValue.Get()))";
            v48 = -97;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_48;
          v49 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszChannelUrl).Get(), pJsonValue.ReleaseAndGetAddressOf()))";
          v48 = -98;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_48;
        v49 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStati"
              "cs.GetAddressOf()))";
        v48 = -101;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_48;
      v49 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))";
      v48 = -102;
    }
    v3 = ActivationFactory;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      v3,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      v48,
      (__int64)v49);
    goto LABEL_48;
  }
  ActivationFactory = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      152,
      (__int64)"CBR(*ppJsonValue == nullptr)");
LABEL_48:
  v43 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v52;
  if ( v52 )
  {
    v52 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v46)[2])(v46);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000ae24  mov     [rsp-28h+arg_10], rbx
0x18000ae29  push    rbp
0x18000ae2a  push    rsi
0x18000ae2b  push    rdi
0x18000ae2c  push    r14
0x18000ae2e  push    r15
0x18000ae30  mov     rbp, rsp
0x18000ae33  sub     rsp, 80h
0x18000ae3a  mov     rax, cs:__security_cookie
0x18000ae41  xor     rax, rsp
0x18000ae44  mov     [rbp+var_8], rax
0x18000ae48  mov     rdi, rdx
0x18000ae4b  mov     [rbp+var_30], rcx
0x18000ae4f  xor     r15d, r15d
0x18000ae52  mov     [rbp+var_40], r15
0x18000ae56  mov     [rbp+var_48], r15
0x18000ae5a  mov     [rbp+var_50], r15
0x18000ae5e  mov     [rbp+var_38], r15
0x18000ae62  test    rdx, rdx
0x18000ae65  jnz     short loc_18000AEA2
0x18000ae67  mov     r8d, 80070057h
0x18000ae6d  mov     ebx, r8d
0x18000ae70  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ae77  jz      loc_18000B292
0x18000ae7d  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x18000ae84  mov     [rsp+80h+var_58], rax
0x18000ae89  mov     dword ptr [rsp+80h+var_60], 397h
0x18000ae91  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000ae98  call    McTemplateU0dsqs_EventWriteTransfer
0x18000ae9d  jmp     loc_18000B292
0x18000aea2  cmp     [rdx], r15
0x18000aea5  jz      short loc_18000AED3
0x18000aea7  mov     r8d, 80070057h
0x18000aead  mov     ebx, r8d
0x18000aeb0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000aeb7  jz      loc_18000B292
0x18000aebd  lea     rax, aCbrPpjsonvalue; "CBR(*ppJsonValue == nullptr)"
0x18000aec4  mov     [rsp+80h+var_58], rax
0x18000aec9  mov     dword ptr [rsp+80h+var_60], 398h
0x18000aed1  jmp     short loc_18000AE91
0x18000aed3  mov     [rbp+string], r15
0x18000aed7  lea     r9, [rbp+string]; string
0x18000aedb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000aedf  mov     edx, 1Ch; length
0x18000aee4  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000aeeb  call    cs:__imp_WindowsCreateStringReference
0x18000aef1  test    eax, eax
0x18000aef3  js      loc_18000B327
0x18000aef9  lea     rdx, [rbp+var_40]
0x18000aefd  mov     rcx, [rbp+string]
0x18000af01  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18000af06  mov     ebx, eax
0x18000af08  test    eax, eax
0x18000af0a  jns     short loc_18000AF35
0x18000af0c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000af13  jz      loc_18000B292
0x18000af19  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18000af20  mov     [rsp+80h+var_58], rax
0x18000af25  mov     dword ptr [rsp+80h+var_60], 39Ah
0x18000af2d  mov     r8d, ebx
0x18000af30  jmp     loc_18000AE91
0x18000af35  mov     [rbp+string], r15
0x18000af39  lea     r9, [rbp+string]; string
0x18000af3d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000af41  mov     edx, 1Bh; length
0x18000af46  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18000af4d  call    cs:__imp_WindowsCreateStringReference
0x18000af53  test    eax, eax
0x18000af55  js      loc_18000B32F
0x18000af5b  lea     r8, [rbp+var_38]
0x18000af5f  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000af66  mov     rcx, [rbp+string]
0x18000af6a  call    cs:__imp_RoGetActivationFactory
0x18000af70  mov     ebx, eax
0x18000af72  test    eax, eax
0x18000af74  jns     short loc_18000AF99
0x18000af76  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000af7d  jz      loc_18000B292
0x18000af83  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x18000af8a  mov     [rsp+80h+var_58], rax
0x18000af8f  mov     dword ptr [rsp+80h+var_60], 39Bh
0x18000af97  jmp     short loc_18000AF2D
0x18000af99  mov     rbx, [rbp+var_38]
0x18000af9d  mov     rax, [rbx]
0x18000afa0  mov     rsi, [rax+50h]
0x18000afa4  mov     rcx, [rbp+var_50]
0x18000afa8  test    rcx, rcx
0x18000afab  jz      short loc_18000AFBE
0x18000afad  mov     [rbp+var_50], r15
0x18000afb1  mov     rax, [rcx]
0x18000afb4  mov     rax, [rax+10h]
0x18000afb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afbd  nop
0x18000afbe  lea     rdx, [rbp+var_30]
0x18000afc2  lea     rcx, [rbp+hstringHeader]
0x18000afc6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000afcb  nop
0x18000afcc  lea     r8, [rbp+var_50]
0x18000afd0  mov     rdx, [rax+18h]
0x18000afd4  mov     rcx, rbx
0x18000afd7  mov     rax, rsi
0x18000afda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afdf  mov     ebx, eax
0x18000afe1  test    eax, eax
0x18000afe3  jns     short loc_18000B00B
0x18000afe5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000afec  jz      loc_18000B292
0x18000aff2  lea     rax, aChrPjsonvalues_2; "CHR(pJsonValueStatics->CreateStringValu"...
0x18000aff9  mov     [rsp+80h+var_58], rax
0x18000affe  mov     dword ptr [rsp+80h+var_60], 39Eh
0x18000b006  jmp     loc_18000AF2D
0x18000b00b  mov     rbx, [rbp+var_40]
0x18000b00f  mov     rsi, [rbx]
0x18000b012  mov     r14, [rbp+var_50]
0x18000b016  mov     [rbp+string], r15
0x18000b01a  lea     r9, [rbp+string]; string
0x18000b01e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b022  mov     edx, 11h; length
0x18000b027  lea     rcx, sourceString; "CommandChannelUrl"
0x18000b02e  call    cs:__imp_WindowsCreateStringReference
0x18000b034  test    eax, eax
0x18000b036  js      loc_18000B337
0x18000b03c  mov     r8, r14
0x18000b03f  mov     rdx, [rbp+string]
0x18000b043  mov     rcx, rbx
0x18000b046  mov     rax, [rsi+38h]
0x18000b04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b04f  mov     ebx, eax
0x18000b051  test    eax, eax
0x18000b053  jns     short loc_18000B07B
0x18000b055  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b05c  jz      loc_18000B292
0x18000b062  lea     rax, aChrPjsonobject_14; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b069  mov     [rsp+80h+var_58], rax
0x18000b06e  mov     dword ptr [rsp+80h+var_60], 39Fh
0x18000b076  jmp     loc_18000AF2D
0x18000b07b  mov     rbx, [rbp+var_38]
0x18000b07f  mov     rax, [rbx]
0x18000b082  mov     rsi, [rax+40h]
0x18000b086  mov     rcx, [rbp+var_50]
0x18000b08a  test    rcx, rcx
0x18000b08d  jz      short loc_18000B0A0
0x18000b08f  mov     [rbp+var_50], r15
0x18000b093  mov     rdx, [rcx]
0x18000b096  mov     rax, [rdx+10h]
0x18000b09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b09f  nop
0x18000b0a0  lea     r8, [rbp+var_50]
0x18000b0a4  xor     edx, edx
0x18000b0a6  mov     rcx, rbx
0x18000b0a9  mov     rax, rsi
0x18000b0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0b1  mov     ebx, eax
0x18000b0b3  test    eax, eax
0x18000b0b5  jns     short loc_18000B0DD
0x18000b0b7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b0be  jz      loc_18000B292
0x18000b0c4  lea     rax, aChrPjsonvalues_12; "CHR(pJsonValueStatics->CreateBooleanVal"...
0x18000b0cb  mov     [rsp+80h+var_58], rax
0x18000b0d0  mov     dword ptr [rsp+80h+var_60], 3A2h
0x18000b0d8  jmp     loc_18000AF2D
0x18000b0dd  mov     rbx, [rbp+var_40]
0x18000b0e1  mov     rsi, [rbx]
0x18000b0e4  mov     r14, [rbp+var_50]
0x18000b0e8  mov     [rbp+string], r15
0x18000b0ec  lea     r9, [rbp+string]; string
0x18000b0f0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b0f4  mov     edx, 0Bh; length
0x18000b0f9  lea     rcx, aMpnsenabled; "MpnsEnabled"
0x18000b100  call    cs:__imp_WindowsCreateStringReference
0x18000b106  test    eax, eax
0x18000b108  js      loc_18000B33F
0x18000b10e  mov     r8, r14
0x18000b111  mov     rdx, [rbp+string]
0x18000b115  mov     rcx, rbx
0x18000b118  mov     rax, [rsi+38h]
0x18000b11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b121  mov     ebx, eax
0x18000b123  test    eax, eax
0x18000b125  jns     short loc_18000B14D
0x18000b127  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b12e  jz      loc_18000B292
0x18000b134  lea     rax, aChrPjsonobject_17; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b13b  mov     [rsp+80h+var_58], rax
0x18000b140  mov     dword ptr [rsp+80h+var_60], 3A3h
0x18000b148  jmp     loc_18000AF2D
0x18000b14d  mov     rbx, [rbp+var_38]
0x18000b151  mov     rax, [rbx]
0x18000b154  mov     rsi, [rax+48h]
0x18000b158  mov     rcx, [rbp+var_50]
0x18000b15c  test    rcx, rcx
0x18000b15f  jz      short loc_18000B172
0x18000b161  mov     [rbp+var_50], r15
0x18000b165  mov     rdx, [rcx]
0x18000b168  mov     rax, [rdx+10h]
0x18000b16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b171  nop
0x18000b172  lea     r8, [rbp+var_50]
0x18000b176  movsd   xmm1, cs:__real@3ff0000000000000
0x18000b17e  mov     rcx, rbx
0x18000b181  mov     rax, rsi
0x18000b184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b189  mov     ebx, eax
0x18000b18b  test    eax, eax
0x18000b18d  jns     short loc_18000B1B5
0x18000b18f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b196  jz      loc_18000B292
0x18000b19c  lea     rax, aChrPjsonvalues_8; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000b1a3  mov     [rsp+80h+var_58], rax
0x18000b1a8  mov     dword ptr [rsp+80h+var_60], 3A6h
0x18000b1b0  jmp     loc_18000AF2D
0x18000b1b5  mov     rbx, [rbp+var_40]
0x18000b1b9  mov     rsi, [rbx]
0x18000b1bc  mov     r14, [rbp+var_50]
0x18000b1c0  mov     [rbp+string], r15
0x18000b1c4  lea     r9, [rbp+string]; string
0x18000b1c8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b1cc  mov     edx, 0Fh; length
0x18000b1d1  lea     rcx, aPushchanneltyp; "PushChannelType"
0x18000b1d8  call    cs:__imp_WindowsCreateStringReference
0x18000b1de  test    eax, eax
0x18000b1e0  js      loc_18000B31F
0x18000b1e6  mov     r8, r14
0x18000b1e9  mov     rdx, [rbp+string]
0x18000b1ed  mov     rcx, rbx
0x18000b1f0  mov     rax, [rsi+38h]
0x18000b1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1f9  mov     ebx, eax
0x18000b1fb  test    eax, eax
0x18000b1fd  jns     short loc_18000B225
0x18000b1ff  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b206  jz      loc_18000B292
0x18000b20c  lea     rax, aChrPjsonobject_9; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b213  mov     [rsp+80h+var_58], rax
0x18000b218  mov     dword ptr [rsp+80h+var_60], 3A7h
0x18000b220  jmp     loc_18000AF2D
0x18000b225  mov     rbx, [rbp+var_40]
0x18000b229  mov     rax, [rbx]
0x18000b22c  mov     rsi, [rax]
0x18000b22f  mov     rcx, [rbp+var_48]
0x18000b233  test    rcx, rcx
0x18000b236  jz      short loc_18000B249
0x18000b238  mov     [rbp+var_48], r15
0x18000b23c  mov     rdx, [rcx]
0x18000b23f  mov     rax, [rdx+10h]
0x18000b243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b248  nop
0x18000b249  lea     r8, [rbp+var_48]
0x18000b24d  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18000b254  mov     rcx, rbx
0x18000b257  mov     rax, rsi
0x18000b25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b25f  mov     ebx, eax
0x18000b261  test    eax, eax
0x18000b263  jns     short loc_18000B287
0x18000b265  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b26c  jz      short loc_18000B292
0x18000b26e  lea     rax, aChrPjsonobject_3; "CHR(pJsonObject.As(&pJsonObjectAsValue)"...
0x18000b275  mov     [rsp+80h+var_58], rax
0x18000b27a  mov     dword ptr [rsp+80h+var_60], 3A9h
0x18000b282  jmp     loc_18000AF2D
0x18000b287  mov     rax, [rbp+var_48]
0x18000b28b  mov     [rbp+var_48], r15
0x18000b28f  mov     [rdi], rax
0x18000b292  mov     rcx, [rbp+var_38]
0x18000b296  test    rcx, rcx
0x18000b299  jz      short loc_18000B2AC
0x18000b29b  mov     [rbp+var_38], r15
0x18000b29f  mov     rax, [rcx]
0x18000b2a2  mov     rax, [rax+10h]
0x18000b2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ab  nop
0x18000b2ac  mov     rcx, [rbp+var_50]
0x18000b2b0  test    rcx, rcx
0x18000b2b3  jz      short loc_18000B2C6
0x18000b2b5  mov     [rbp+var_50], r15
0x18000b2b9  mov     rax, [rcx]
0x18000b2bc  mov     rax, [rax+10h]
0x18000b2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c5  nop
0x18000b2c6  mov     rcx, [rbp+var_48]
0x18000b2ca  test    rcx, rcx
0x18000b2cd  jz      short loc_18000B2E0
0x18000b2cf  mov     [rbp+var_48], r15
0x18000b2d3  mov     rax, [rcx]
0x18000b2d6  mov     rax, [rax+10h]
0x18000b2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2df  nop
0x18000b2e0  mov     rcx, [rbp+var_40]
0x18000b2e4  test    rcx, rcx
0x18000b2e7  jz      short loc_18000B2FA
0x18000b2e9  mov     [rbp+var_40], r15
0x18000b2ed  mov     rax, [rcx]
0x18000b2f0  mov     rax, [rax+10h]
0x18000b2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2f9  nop
0x18000b2fa  mov     eax, ebx
0x18000b2fc  mov     rcx, [rbp+var_8]
0x18000b300  xor     rcx, rsp; StackCookie
0x18000b303  call    __security_check_cookie
  ... truncated ...
```
