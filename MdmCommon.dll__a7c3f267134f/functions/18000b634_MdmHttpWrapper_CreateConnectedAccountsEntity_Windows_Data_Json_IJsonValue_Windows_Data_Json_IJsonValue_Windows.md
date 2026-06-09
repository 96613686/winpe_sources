# MdmHttpWrapper::CreateConnectedAccountsEntity(Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue * *)

- ea: `0x18000b634`
- end: `0x18000bb94`
- name: `?CreateConnectedAccountsEntity@MdmHttpWrapper@@SAJPEAUIJsonValue@Json@Data@Windows@@000PEAPEAU2345@@Z`
- size: `1376`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800030c0`
- `0x18000c6e8`
- `0x18000f3b8`

## callees

- `0x180001520`
- `0x1800065c0`
- `0x18000afa4`
- `0x18000b634`
- `0x1800117e4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b7d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b853`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b8c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b936`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b9ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ba22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b7d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b853`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b8c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b936`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b9ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ba22`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b7fc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b7fc`

## string_xrefs

- `0x18000b7d2`: `Windows.Data.Json.JsonValue`
- `0x18000b84c`: `Windows.Data.Json.JsonObject`
- `0x18000b6ad`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000b887`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18000b81b`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18000bac2`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x18000b76f`: `CPR(ppJsonValue)`
- `0x18000b7a4`: `CBR(*ppJsonValue == nullptr)`
- `0x18000b8fa`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"AdminCids").Get(), pAdmins))`
- `0x18000b970`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"DeviceOwnerCids").Get(), pDeviceOwners))`
- `0x18000b9e6`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"StandardCids").Get(), pStandardUsers))`
- `0x18000ba5c`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"ConnectedAdminCids").Get(), pConnectedAdmins))`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall MdmHttpWrapper::CreateConnectedAccountsEntity(
        struct Windows::Data::Json::IJsonValue *a1,
        struct Windows::Data::Json::IJsonValue *a2,
        struct Windows::Data::Json::IJsonValue *a3,
        struct Windows::Data::Json::IJsonValue *a4,
        struct Windows::Data::Json::IJsonValue **a5)
{
  int v9; // r8d
  int ActivationFactory; // ebx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v18)(_QWORD, _QWORD, _QWORD); // rsi
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v23)(_QWORD, _QWORD, _QWORD); // rsi
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v28)(_QWORD, _QWORD, _QWORD); // rsi
  HRESULT v29; // eax
  int v30; // edx
  unsigned int v31; // r8d
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v33)(_QWORD, _QWORD, _QWORD); // rsi
  HRESULT v34; // eax
  int v35; // edx
  unsigned int v36; // r8d
  __int64 (__fastcall ***v37)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v38)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // rsi
  struct Windows::Data::Json::IJsonValue *v39; // rcx
  struct Windows::Data::Json::IJsonValue *v40; // rax
  struct Windows::Data::Json::IJsonValue *v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v43; // rcx
  char v45; // [rsp+20h] [rbp-58h]
  const char *v46; // [rsp+28h] [rbp-50h]
  __int64 (__fastcall ***v47)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // [rsp+30h] [rbp-48h] BYREF
  struct Windows::Data::Json::IJsonValue *v48; // [rsp+38h] [rbp-40h] BYREF
  __int64 v49; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF

  v49 = 0;
  v47 = 0;
  v48 = 0;
  if ( !a1 )
  {
    v9 = -2147024809;
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_52;
    v46 = "CPR(pAdmins)";
    v45 = 79;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      v9,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      v45,
      v46);
    goto LABEL_52;
  }
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( a5 )
        {
          if ( !*a5 )
          {
            string = 0;
            v11 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
            if ( v11 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
              __debugbreak();
            }
            ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v49);
            if ( ActivationFactory >= 0 )
            {
              string = 0;
              v14 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
              if ( v14 < 0 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
                __debugbreak();
              }
              ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(string, &v47);
              if ( ActivationFactory >= 0 )
              {
                v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
                v18 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v47;
                string = 0;
                v19 = WindowsCreateStringReference(L"AdminCids", 9u, &hstringHeader, &string);
                if ( v19 < 0 )
                {
                  Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
                  __debugbreak();
                }
                ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v18)[7](
                                      v17,
                                      string,
                                      a1);
                if ( ActivationFactory >= 0 )
                {
                  v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
                  v23 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v47;
                  string = 0;
                  v24 = WindowsCreateStringReference(L"DeviceOwnerCids", 0xFu, &hstringHeader, &string);
                  if ( v24 < 0 )
                  {
                    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
                    __debugbreak();
                  }
                  ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v23)[7](
                                        v22,
                                        string,
                                        a2);
                  if ( ActivationFactory >= 0 )
                  {
                    v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
                    v28 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v47;
                    string = 0;
                    v29 = WindowsCreateStringReference(L"StandardCids", 0xCu, &hstringHeader, &string);
                    if ( v29 < 0 )
                    {
                      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v31);
                      JUMPOUT(0x18000BB93LL);
                    }
                    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v28)[7](
                                          v27,
                                          string,
                                          a3);
                    if ( ActivationFactory >= 0 )
                    {
                      v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
                      v33 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v47;
                      string = 0;
                      v34 = WindowsCreateStringReference(L"ConnectedAdminCids", 0x12u, &hstringHeader, &string);
                      if ( v34 < 0 )
                      {
                        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v34, v35, v36);
                        __debugbreak();
                      }
                      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v33)[7](
                                            v32,
                                            string,
                                            a4);
                      if ( ActivationFactory >= 0 )
                      {
                        v37 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
                        v38 = **v47;
                        v39 = v48;
                        if ( v48 )
                        {
                          v48 = 0;
                          (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v39 + 16LL))(v39);
                        }
                        ActivationFactory = v38(v37, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v48);
                        if ( ActivationFactory >= 0 )
                        {
                          v40 = v48;
                          v48 = 0;
                          *a5 = v40;
                          goto LABEL_52;
                        }
                        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                          goto LABEL_52;
                        v46 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
                        v45 = 94;
                      }
                      else
                      {
                        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                          goto LABEL_52;
                        v46 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"ConnectedAdminCids\").Get(), pConnectedAdmins))";
                        v45 = 92;
                      }
                    }
                    else
                    {
                      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                        goto LABEL_52;
                      v46 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"StandardCids\").Get(), pStandardUsers))";
                      v45 = 91;
                    }
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                      goto LABEL_52;
                    v46 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"DeviceOwnerCids\").Get(), pDeviceOwners))";
                    v45 = 90;
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                    goto LABEL_52;
                  v46 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"AdminCids\").Get(), pAdmins))";
                  v45 = 89;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                  goto LABEL_52;
                v46 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObjec"
                      "t.GetAddressOf()))";
                v45 = 87;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                goto LABEL_52;
              v46 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValu"
                    "eStatics.GetAddressOf()))";
              v45 = 86;
            }
            v9 = ActivationFactory;
            goto LABEL_4;
          }
          ActivationFactory = -2147024809;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)a1,
              (_DWORD)a2,
              -2147024809,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
              84,
              "CBR(*ppJsonValue == nullptr)");
        }
        else
        {
          ActivationFactory = -2147024809;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)a1,
              (_DWORD)a2,
              -2147024809,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
              83,
              "CPR(ppJsonValue)");
        }
      }
      else
      {
        ActivationFactory = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)a1,
            (_DWORD)a2,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            82,
            "CPR(pConnectedAdmins)");
      }
    }
    else
    {
      ActivationFactory = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          81,
          "CPR(pStandardUsers)");
    }
  }
  else
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
        80,
        "CPR(pDeviceOwners)");
  }
LABEL_52:
  v41 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
  if ( v47 )
  {
    v47 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v42)[2])(v42);
  }
  v43 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000b634  push    rbp
0x18000b636  push    rbx
0x18000b637  push    rsi
0x18000b638  push    rdi
0x18000b639  push    r12
0x18000b63b  push    r13
0x18000b63d  push    r14
0x18000b63f  push    r15
0x18000b641  mov     rbp, rsp
0x18000b644  sub     rsp, 78h
0x18000b648  mov     rax, cs:__security_cookie
0x18000b64f  xor     rax, rsp
0x18000b652  mov     [rbp+var_10], rax
0x18000b656  mov     r12, r9
0x18000b659  mov     r15, r8
0x18000b65c  mov     r14, rdx
0x18000b65f  mov     r13, rcx
0x18000b662  mov     rdi, [rbp+arg_20]
0x18000b666  mov     [rbp+var_38], 0
0x18000b66e  mov     [rbp+var_48], 0
0x18000b676  mov     [rbp+var_40], 0
0x18000b67e  test    rcx, rcx
0x18000b681  jnz     short loc_18000B6BE
0x18000b683  mov     r8d, 80070057h
0x18000b689  mov     ebx, r8d
0x18000b68c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b693  jz      loc_18000BAEA
0x18000b699  lea     rax, aCprPadmins; "CPR(pAdmins)"
0x18000b6a0  mov     [rsp+78h+var_50], rax
0x18000b6a5  mov     dword ptr [rsp+78h+var_58], 44Fh
0x18000b6ad  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000b6b4  call    McTemplateU0dsqs_EventWriteTransfer
0x18000b6b9  jmp     loc_18000BAEA
0x18000b6be  test    r14, r14
0x18000b6c1  jnz     short loc_18000B6EF
0x18000b6c3  mov     r8d, 80070057h
0x18000b6c9  mov     ebx, r8d
0x18000b6cc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b6d3  jz      loc_18000BAEA
0x18000b6d9  lea     rax, aCprPdeviceowne; "CPR(pDeviceOwners)"
0x18000b6e0  mov     [rsp+78h+var_50], rax
0x18000b6e5  mov     dword ptr [rsp+78h+var_58], 450h
0x18000b6ed  jmp     short loc_18000B6AD
0x18000b6ef  test    r15, r15
0x18000b6f2  jnz     short loc_18000B720
0x18000b6f4  mov     r8d, 80070057h
0x18000b6fa  mov     ebx, r8d
0x18000b6fd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b704  jz      loc_18000BAEA
0x18000b70a  lea     rax, aCprPstandardus; "CPR(pStandardUsers)"
0x18000b711  mov     [rsp+78h+var_50], rax
0x18000b716  mov     dword ptr [rsp+78h+var_58], 451h
0x18000b71e  jmp     short loc_18000B6AD
0x18000b720  test    r12, r12
0x18000b723  jnz     short loc_18000B754
0x18000b725  mov     r8d, 80070057h
0x18000b72b  mov     ebx, r8d
0x18000b72e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b735  jz      loc_18000BAEA
0x18000b73b  lea     rax, aCprPconnecteda; "CPR(pConnectedAdmins)"
0x18000b742  mov     [rsp+78h+var_50], rax
0x18000b747  mov     dword ptr [rsp+78h+var_58], 452h
0x18000b74f  jmp     loc_18000B6AD
0x18000b754  test    rdi, rdi
0x18000b757  jnz     short loc_18000B788
0x18000b759  mov     r8d, 80070057h
0x18000b75f  mov     ebx, r8d
0x18000b762  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b769  jz      loc_18000BAEA
0x18000b76f  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x18000b776  mov     [rsp+78h+var_50], rax
0x18000b77b  mov     dword ptr [rsp+78h+var_58], 453h
0x18000b783  jmp     loc_18000B6AD
0x18000b788  cmp     qword ptr [rdi], 0
0x18000b78c  jz      short loc_18000B7BD
0x18000b78e  mov     r8d, 80070057h
0x18000b794  mov     ebx, r8d
0x18000b797  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b79e  jz      loc_18000BAEA
0x18000b7a4  lea     rax, aCbrPpjsonvalue; "CBR(*ppJsonValue == nullptr)"
0x18000b7ab  mov     [rsp+78h+var_50], rax
0x18000b7b0  mov     dword ptr [rsp+78h+var_58], 454h
0x18000b7b8  jmp     loc_18000B6AD
0x18000b7bd  mov     [rbp+string], 0
0x18000b7c5  lea     r9, [rbp+string]; string
0x18000b7c9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b7cd  mov     edx, 1Bh; length
0x18000b7d2  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18000b7d9  call    cs:__imp_WindowsCreateStringReference
0x18000b7e0  nop     dword ptr [rax+rax+00h]
0x18000b7e5  test    eax, eax
0x18000b7e7  js      loc_18000BB6C
0x18000b7ed  lea     r8, [rbp+var_38]
0x18000b7f1  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000b7f8  mov     rcx, [rbp+string]
0x18000b7fc  call    cs:__imp_RoGetActivationFactory
0x18000b803  nop     dword ptr [rax+rax+00h]
0x18000b808  mov     ebx, eax
0x18000b80a  test    eax, eax
0x18000b80c  jns     short loc_18000B837
0x18000b80e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b815  jz      loc_18000BAEA
0x18000b81b  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x18000b822  mov     [rsp+78h+var_50], rax
0x18000b827  mov     dword ptr [rsp+78h+var_58], 456h
0x18000b82f  mov     r8d, ebx
0x18000b832  jmp     loc_18000B6AD
0x18000b837  mov     [rbp+string], 0
0x18000b83f  lea     r9, [rbp+string]; string
0x18000b843  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b847  mov     edx, 1Ch; length
0x18000b84c  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000b853  call    cs:__imp_WindowsCreateStringReference
0x18000b85a  nop     dword ptr [rax+rax+00h]
0x18000b85f  test    eax, eax
0x18000b861  js      loc_18000BB74
0x18000b867  lea     rdx, [rbp+var_48]
0x18000b86b  mov     rcx, [rbp+string]
0x18000b86f  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18000b874  mov     ebx, eax
0x18000b876  test    eax, eax
0x18000b878  jns     short loc_18000B89D
0x18000b87a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b881  jz      loc_18000BAEA
0x18000b887  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18000b88e  mov     [rsp+78h+var_50], rax
0x18000b893  mov     dword ptr [rsp+78h+var_58], 457h
0x18000b89b  jmp     short loc_18000B82F
0x18000b89d  mov     rbx, [rbp+var_48]
0x18000b8a1  mov     rsi, [rbx]
0x18000b8a4  mov     [rbp+string], 0
0x18000b8ac  lea     r9, [rbp+string]; string
0x18000b8b0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b8b4  mov     edx, 9; length
0x18000b8b9  lea     rcx, aAdmincids; "AdminCids"
0x18000b8c0  call    cs:__imp_WindowsCreateStringReference
0x18000b8c7  nop     dword ptr [rax+rax+00h]
0x18000b8cc  test    eax, eax
0x18000b8ce  js      loc_18000BB7C
0x18000b8d4  mov     r8, r13
0x18000b8d7  mov     rdx, [rbp+string]
0x18000b8db  mov     rcx, rbx
0x18000b8de  mov     rax, [rsi+38h]
0x18000b8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8e7  mov     ebx, eax
0x18000b8e9  test    eax, eax
0x18000b8eb  jns     short loc_18000B913
0x18000b8ed  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b8f4  jz      loc_18000BAEA
0x18000b8fa  lea     rax, aChrPjsonobject_39; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b901  mov     [rsp+78h+var_50], rax
0x18000b906  mov     dword ptr [rsp+78h+var_58], 459h
0x18000b90e  jmp     loc_18000B82F
0x18000b913  mov     rbx, [rbp+var_48]
0x18000b917  mov     rsi, [rbx]
0x18000b91a  mov     [rbp+string], 0
0x18000b922  lea     r9, [rbp+string]; string
0x18000b926  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b92a  mov     edx, 0Fh; length
0x18000b92f  lea     rcx, aDeviceownercid; "DeviceOwnerCids"
0x18000b936  call    cs:__imp_WindowsCreateStringReference
0x18000b93d  nop     dword ptr [rax+rax+00h]
0x18000b942  test    eax, eax
0x18000b944  js      loc_18000BB84
0x18000b94a  mov     r8, r14
0x18000b94d  mov     rdx, [rbp+string]
0x18000b951  mov     rcx, rbx
0x18000b954  mov     rax, [rsi+38h]
0x18000b958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b95d  mov     ebx, eax
0x18000b95f  test    eax, eax
0x18000b961  jns     short loc_18000B989
0x18000b963  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b96a  jz      loc_18000BAEA
0x18000b970  lea     rax, aChrPjsonobject_7; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b977  mov     [rsp+78h+var_50], rax
0x18000b97c  mov     dword ptr [rsp+78h+var_58], 45Ah
0x18000b984  jmp     loc_18000B82F
0x18000b989  mov     rbx, [rbp+var_48]
0x18000b98d  mov     rsi, [rbx]
0x18000b990  mov     [rbp+string], 0
0x18000b998  lea     r9, [rbp+string]; string
0x18000b99c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b9a0  mov     edx, 0Ch; length
0x18000b9a5  lea     rcx, aStandardcids; "StandardCids"
0x18000b9ac  call    cs:__imp_WindowsCreateStringReference
0x18000b9b3  nop     dword ptr [rax+rax+00h]
0x18000b9b8  test    eax, eax
0x18000b9ba  js      loc_18000BB8C
0x18000b9c0  mov     r8, r15
0x18000b9c3  mov     rdx, [rbp+string]
0x18000b9c7  mov     rcx, rbx
0x18000b9ca  mov     rax, [rsi+38h]
0x18000b9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9d3  mov     ebx, eax
0x18000b9d5  test    eax, eax
0x18000b9d7  jns     short loc_18000B9FF
0x18000b9d9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b9e0  jz      loc_18000BAEA
0x18000b9e6  lea     rax, aChrPjsonobject_27; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b9ed  mov     [rsp+78h+var_50], rax
0x18000b9f2  mov     dword ptr [rsp+78h+var_58], 45Bh
0x18000b9fa  jmp     loc_18000B82F
0x18000b9ff  mov     rbx, [rbp+var_48]
0x18000ba03  mov     rsi, [rbx]
0x18000ba06  mov     [rbp+string], 0
0x18000ba0e  lea     r9, [rbp+string]; string
0x18000ba12  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000ba16  mov     edx, 12h; length
0x18000ba1b  lea     rcx, aConnectedadmin; "ConnectedAdminCids"
0x18000ba22  call    cs:__imp_WindowsCreateStringReference
0x18000ba29  nop     dword ptr [rax+rax+00h]
0x18000ba2e  test    eax, eax
0x18000ba30  js      loc_18000BB64
0x18000ba36  mov     r8, r12
0x18000ba39  mov     rdx, [rbp+string]
0x18000ba3d  mov     rcx, rbx
0x18000ba40  mov     rax, [rsi+38h]
0x18000ba44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba49  mov     ebx, eax
0x18000ba4b  test    eax, eax
0x18000ba4d  jns     short loc_18000BA75
0x18000ba4f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ba56  jz      loc_18000BAEA
0x18000ba5c  lea     rax, aChrPjsonobject_0; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000ba63  mov     [rsp+78h+var_50], rax
0x18000ba68  mov     dword ptr [rsp+78h+var_58], 45Ch
0x18000ba70  jmp     loc_18000B82F
0x18000ba75  mov     rbx, [rbp+var_48]
0x18000ba79  mov     rax, [rbx]
0x18000ba7c  mov     rsi, [rax]
0x18000ba7f  mov     rcx, [rbp+var_40]
0x18000ba83  test    rcx, rcx
0x18000ba86  jz      short loc_18000BA9D
0x18000ba88  mov     [rbp+var_40], 0
0x18000ba90  mov     rdx, [rcx]
0x18000ba93  mov     rax, [rdx+10h]
0x18000ba97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba9c  nop
0x18000ba9d  lea     r8, [rbp+var_40]
0x18000baa1  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18000baa8  mov     rcx, rbx
0x18000baab  mov     rax, rsi
0x18000baae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab3  mov     ebx, eax
0x18000bab5  test    eax, eax
0x18000bab7  jns     short loc_18000BADB
0x18000bab9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bac0  jz      short loc_18000BAEA
0x18000bac2  lea     rax, aChrPjsonobject_3; "CHR(pJsonObject.As(&pJsonObjectAsValue)"...
0x18000bac9  mov     [rsp+78h+var_50], rax
0x18000bace  mov     dword ptr [rsp+78h+var_58], 45Eh
0x18000bad6  jmp     loc_18000B82F
0x18000badb  mov     rax, [rbp+var_40]
0x18000badf  mov     [rbp+var_40], 0
0x18000bae7  mov     [rdi], rax
0x18000baea  mov     rcx, [rbp+var_40]
0x18000baee  test    rcx, rcx
0x18000baf1  jz      short loc_18000BB08
0x18000baf3  mov     [rbp+var_40], 0
0x18000bafb  mov     rax, [rcx]
0x18000bafe  mov     rax, [rax+10h]
0x18000bb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb07  nop
0x18000bb08  mov     rcx, [rbp+var_48]
0x18000bb0c  test    rcx, rcx
0x18000bb0f  jz      short loc_18000BB26
0x18000bb11  mov     [rbp+var_48], 0
0x18000bb19  mov     rax, [rcx]
0x18000bb1c  mov     rax, [rax+10h]
0x18000bb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb25  nop
0x18000bb26  mov     rcx, [rbp+var_38]
0x18000bb2a  test    rcx, rcx
0x18000bb2d  jz      short loc_18000BB44
0x18000bb2f  mov     [rbp+var_38], 0
0x18000bb37  mov     rax, [rcx]
0x18000bb3a  mov     rax, [rax+10h]
0x18000bb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb43  nop
0x18000bb44  mov     eax, ebx
0x18000bb46  mov     rcx, [rbp+var_10]
0x18000bb4a  xor     rcx, rsp; StackCookie
0x18000bb4d  call    __security_check_cookie
0x18000bb52  add     rsp, 78h
0x18000bb56  pop     r15
0x18000bb58  pop     r14
0x18000bb5a  pop     r13
0x18000bb5c  pop     r12
0x18000bb5e  pop     rdi
0x18000bb5f  pop     rsi
0x18000bb60  pop     rbx
0x18000bb61  pop     rbp
0x18000bb62  retn
0x18000bb64  mov     ecx, eax; this
0x18000bb66  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000bb6b  int     3; Trap to Debugger
0x18000bb6c  mov     ecx, eax; this
0x18000bb6e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000bb73  int     3; Trap to Debugger
  ... truncated ...
```
