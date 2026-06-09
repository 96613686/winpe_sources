# MdmHttpWrapper::CreateConnectedAccountsEntity(Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue * *)

- ea: `0x18000b350`
- end: `0x18000b885`
- name: `?CreateConnectedAccountsEntity@MdmHttpWrapper@@SAJPEAUIJsonValue@Json@Data@Windows@@000PEAPEAU2345@@Z`
- size: `1333`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800030c0`
- `0x18000c38c`
- `0x18000ef34`

## callees

- `0x180001520`
- `0x180006548`
- `0x18000acf4`
- `0x18000b350`
- `0x180011414`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b4f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b5ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b63a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b6aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b71a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b4f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b5ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b63a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b6aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b71a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b512`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b512`

## string_xrefs

- `0x18000b4ee`: `Windows.Data.Json.JsonValue`
- `0x18000b55c`: `Windows.Data.Json.JsonObject`
- `0x18000b3c9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000b591`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18000b52b`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18000b7b4`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x18000b48b`: `CPR(ppJsonValue)`
- `0x18000b4c0`: `CBR(*ppJsonValue == nullptr)`
- `0x18000b5fe`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"AdminCids").Get(), pAdmins))`
- `0x18000b66e`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"DeviceOwnerCids").Get(), pDeviceOwners))`
- `0x18000b6de`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"StandardCids").Get(), pStandardUsers))`
- `0x18000b74e`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"ConnectedAdminCids").Get(), pConnectedAdmins))`

## pseudocode

```c
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
      (__int64)v46);
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
              ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(
                                    (__int64)string,
                                    &v47);
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
                      JUMPOUT(0x18000B884LL);
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
              (__int64)"CBR(*ppJsonValue == nullptr)");
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
              (__int64)"CPR(ppJsonValue)");
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
            (__int64)"CPR(pConnectedAdmins)");
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
          (__int64)"CPR(pStandardUsers)");
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
        (__int64)"CPR(pDeviceOwners)");
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
0x18000b350  push    rbp
0x18000b352  push    rbx
0x18000b353  push    rsi
0x18000b354  push    rdi
0x18000b355  push    r12
0x18000b357  push    r13
0x18000b359  push    r14
0x18000b35b  push    r15
0x18000b35d  mov     rbp, rsp
0x18000b360  sub     rsp, 78h
0x18000b364  mov     rax, cs:__security_cookie
0x18000b36b  xor     rax, rsp
0x18000b36e  mov     [rbp+var_10], rax
0x18000b372  mov     r12, r9
0x18000b375  mov     r15, r8
0x18000b378  mov     r14, rdx
0x18000b37b  mov     r13, rcx
0x18000b37e  mov     rdi, [rbp+arg_20]
0x18000b382  mov     [rbp+var_38], 0
0x18000b38a  mov     [rbp+var_48], 0
0x18000b392  mov     [rbp+var_40], 0
0x18000b39a  test    rcx, rcx
0x18000b39d  jnz     short loc_18000B3DA
0x18000b39f  mov     r8d, 80070057h
0x18000b3a5  mov     ebx, r8d
0x18000b3a8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b3af  jz      loc_18000B7DC
0x18000b3b5  lea     rax, aCprPadmins; "CPR(pAdmins)"
0x18000b3bc  mov     [rsp+78h+var_50], rax
0x18000b3c1  mov     dword ptr [rsp+78h+var_58], 44Fh
0x18000b3c9  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000b3d0  call    McTemplateU0dsqs_EventWriteTransfer
0x18000b3d5  jmp     loc_18000B7DC
0x18000b3da  test    r14, r14
0x18000b3dd  jnz     short loc_18000B40B
0x18000b3df  mov     r8d, 80070057h
0x18000b3e5  mov     ebx, r8d
0x18000b3e8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b3ef  jz      loc_18000B7DC
0x18000b3f5  lea     rax, aCprPdeviceowne; "CPR(pDeviceOwners)"
0x18000b3fc  mov     [rsp+78h+var_50], rax
0x18000b401  mov     dword ptr [rsp+78h+var_58], 450h
0x18000b409  jmp     short loc_18000B3C9
0x18000b40b  test    r15, r15
0x18000b40e  jnz     short loc_18000B43C
0x18000b410  mov     r8d, 80070057h
0x18000b416  mov     ebx, r8d
0x18000b419  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b420  jz      loc_18000B7DC
0x18000b426  lea     rax, aCprPstandardus; "CPR(pStandardUsers)"
0x18000b42d  mov     [rsp+78h+var_50], rax
0x18000b432  mov     dword ptr [rsp+78h+var_58], 451h
0x18000b43a  jmp     short loc_18000B3C9
0x18000b43c  test    r12, r12
0x18000b43f  jnz     short loc_18000B470
0x18000b441  mov     r8d, 80070057h
0x18000b447  mov     ebx, r8d
0x18000b44a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b451  jz      loc_18000B7DC
0x18000b457  lea     rax, aCprPconnecteda; "CPR(pConnectedAdmins)"
0x18000b45e  mov     [rsp+78h+var_50], rax
0x18000b463  mov     dword ptr [rsp+78h+var_58], 452h
0x18000b46b  jmp     loc_18000B3C9
0x18000b470  test    rdi, rdi
0x18000b473  jnz     short loc_18000B4A4
0x18000b475  mov     r8d, 80070057h
0x18000b47b  mov     ebx, r8d
0x18000b47e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b485  jz      loc_18000B7DC
0x18000b48b  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x18000b492  mov     [rsp+78h+var_50], rax
0x18000b497  mov     dword ptr [rsp+78h+var_58], 453h
0x18000b49f  jmp     loc_18000B3C9
0x18000b4a4  cmp     qword ptr [rdi], 0
0x18000b4a8  jz      short loc_18000B4D9
0x18000b4aa  mov     r8d, 80070057h
0x18000b4b0  mov     ebx, r8d
0x18000b4b3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b4ba  jz      loc_18000B7DC
0x18000b4c0  lea     rax, aCbrPpjsonvalue; "CBR(*ppJsonValue == nullptr)"
0x18000b4c7  mov     [rsp+78h+var_50], rax
0x18000b4cc  mov     dword ptr [rsp+78h+var_58], 454h
0x18000b4d4  jmp     loc_18000B3C9
0x18000b4d9  mov     [rbp+string], 0
0x18000b4e1  lea     r9, [rbp+string]; string
0x18000b4e5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b4e9  mov     edx, 1Bh; length
0x18000b4ee  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18000b4f5  call    cs:__imp_WindowsCreateStringReference
0x18000b4fb  test    eax, eax
0x18000b4fd  js      loc_18000B85D
0x18000b503  lea     r8, [rbp+var_38]
0x18000b507  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000b50e  mov     rcx, [rbp+string]
0x18000b512  call    cs:__imp_RoGetActivationFactory
0x18000b518  mov     ebx, eax
0x18000b51a  test    eax, eax
0x18000b51c  jns     short loc_18000B547
0x18000b51e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b525  jz      loc_18000B7DC
0x18000b52b  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x18000b532  mov     [rsp+78h+var_50], rax
0x18000b537  mov     dword ptr [rsp+78h+var_58], 456h
0x18000b53f  mov     r8d, ebx
0x18000b542  jmp     loc_18000B3C9
0x18000b547  mov     [rbp+string], 0
0x18000b54f  lea     r9, [rbp+string]; string
0x18000b553  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b557  mov     edx, 1Ch; length
0x18000b55c  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000b563  call    cs:__imp_WindowsCreateStringReference
0x18000b569  test    eax, eax
0x18000b56b  js      loc_18000B865
0x18000b571  lea     rdx, [rbp+var_48]
0x18000b575  mov     rcx, [rbp+string]
0x18000b579  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18000b57e  mov     ebx, eax
0x18000b580  test    eax, eax
0x18000b582  jns     short loc_18000B5A7
0x18000b584  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b58b  jz      loc_18000B7DC
0x18000b591  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18000b598  mov     [rsp+78h+var_50], rax
0x18000b59d  mov     dword ptr [rsp+78h+var_58], 457h
0x18000b5a5  jmp     short loc_18000B53F
0x18000b5a7  mov     rbx, [rbp+var_48]
0x18000b5ab  mov     rsi, [rbx]
0x18000b5ae  mov     [rbp+string], 0
0x18000b5b6  lea     r9, [rbp+string]; string
0x18000b5ba  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b5be  mov     edx, 9; length
0x18000b5c3  lea     rcx, aAdmincids; "AdminCids"
0x18000b5ca  call    cs:__imp_WindowsCreateStringReference
0x18000b5d0  test    eax, eax
0x18000b5d2  js      loc_18000B86D
0x18000b5d8  mov     r8, r13
0x18000b5db  mov     rdx, [rbp+string]
0x18000b5df  mov     rcx, rbx
0x18000b5e2  mov     rax, [rsi+38h]
0x18000b5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5eb  mov     ebx, eax
0x18000b5ed  test    eax, eax
0x18000b5ef  jns     short loc_18000B617
0x18000b5f1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b5f8  jz      loc_18000B7DC
0x18000b5fe  lea     rax, aChrPjsonobject_39; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b605  mov     [rsp+78h+var_50], rax
0x18000b60a  mov     dword ptr [rsp+78h+var_58], 459h
0x18000b612  jmp     loc_18000B53F
0x18000b617  mov     rbx, [rbp+var_48]
0x18000b61b  mov     rsi, [rbx]
0x18000b61e  mov     [rbp+string], 0
0x18000b626  lea     r9, [rbp+string]; string
0x18000b62a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b62e  mov     edx, 0Fh; length
0x18000b633  lea     rcx, aDeviceownercid; "DeviceOwnerCids"
0x18000b63a  call    cs:__imp_WindowsCreateStringReference
0x18000b640  test    eax, eax
0x18000b642  js      loc_18000B875
0x18000b648  mov     r8, r14
0x18000b64b  mov     rdx, [rbp+string]
0x18000b64f  mov     rcx, rbx
0x18000b652  mov     rax, [rsi+38h]
0x18000b656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b65b  mov     ebx, eax
0x18000b65d  test    eax, eax
0x18000b65f  jns     short loc_18000B687
0x18000b661  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b668  jz      loc_18000B7DC
0x18000b66e  lea     rax, aChrPjsonobject_7; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b675  mov     [rsp+78h+var_50], rax
0x18000b67a  mov     dword ptr [rsp+78h+var_58], 45Ah
0x18000b682  jmp     loc_18000B53F
0x18000b687  mov     rbx, [rbp+var_48]
0x18000b68b  mov     rsi, [rbx]
0x18000b68e  mov     [rbp+string], 0
0x18000b696  lea     r9, [rbp+string]; string
0x18000b69a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b69e  mov     edx, 0Ch; length
0x18000b6a3  lea     rcx, aStandardcids; "StandardCids"
0x18000b6aa  call    cs:__imp_WindowsCreateStringReference
0x18000b6b0  test    eax, eax
0x18000b6b2  js      loc_18000B87D
0x18000b6b8  mov     r8, r15
0x18000b6bb  mov     rdx, [rbp+string]
0x18000b6bf  mov     rcx, rbx
0x18000b6c2  mov     rax, [rsi+38h]
0x18000b6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6cb  mov     ebx, eax
0x18000b6cd  test    eax, eax
0x18000b6cf  jns     short loc_18000B6F7
0x18000b6d1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b6d8  jz      loc_18000B7DC
0x18000b6de  lea     rax, aChrPjsonobject_27; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b6e5  mov     [rsp+78h+var_50], rax
0x18000b6ea  mov     dword ptr [rsp+78h+var_58], 45Bh
0x18000b6f2  jmp     loc_18000B53F
0x18000b6f7  mov     rbx, [rbp+var_48]
0x18000b6fb  mov     rsi, [rbx]
0x18000b6fe  mov     [rbp+string], 0
0x18000b706  lea     r9, [rbp+string]; string
0x18000b70a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b70e  mov     edx, 12h; length
0x18000b713  lea     rcx, aConnectedadmin; "ConnectedAdminCids"
0x18000b71a  call    cs:__imp_WindowsCreateStringReference
0x18000b720  test    eax, eax
0x18000b722  js      loc_18000B855
0x18000b728  mov     r8, r12
0x18000b72b  mov     rdx, [rbp+string]
0x18000b72f  mov     rcx, rbx
0x18000b732  mov     rax, [rsi+38h]
0x18000b736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b73b  mov     ebx, eax
0x18000b73d  test    eax, eax
0x18000b73f  jns     short loc_18000B767
0x18000b741  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b748  jz      loc_18000B7DC
0x18000b74e  lea     rax, aChrPjsonobject_0; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b755  mov     [rsp+78h+var_50], rax
0x18000b75a  mov     dword ptr [rsp+78h+var_58], 45Ch
0x18000b762  jmp     loc_18000B53F
0x18000b767  mov     rbx, [rbp+var_48]
0x18000b76b  mov     rax, [rbx]
0x18000b76e  mov     rsi, [rax]
0x18000b771  mov     rcx, [rbp+var_40]
0x18000b775  test    rcx, rcx
0x18000b778  jz      short loc_18000B78F
0x18000b77a  mov     [rbp+var_40], 0
0x18000b782  mov     rdx, [rcx]
0x18000b785  mov     rax, [rdx+10h]
0x18000b789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b78e  nop
0x18000b78f  lea     r8, [rbp+var_40]
0x18000b793  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18000b79a  mov     rcx, rbx
0x18000b79d  mov     rax, rsi
0x18000b7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7a5  mov     ebx, eax
0x18000b7a7  test    eax, eax
0x18000b7a9  jns     short loc_18000B7CD
0x18000b7ab  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b7b2  jz      short loc_18000B7DC
0x18000b7b4  lea     rax, aChrPjsonobject_3; "CHR(pJsonObject.As(&pJsonObjectAsValue)"...
0x18000b7bb  mov     [rsp+78h+var_50], rax
0x18000b7c0  mov     dword ptr [rsp+78h+var_58], 45Eh
0x18000b7c8  jmp     loc_18000B53F
0x18000b7cd  mov     rax, [rbp+var_40]
0x18000b7d1  mov     [rbp+var_40], 0
0x18000b7d9  mov     [rdi], rax
0x18000b7dc  mov     rcx, [rbp+var_40]
0x18000b7e0  test    rcx, rcx
0x18000b7e3  jz      short loc_18000B7FA
0x18000b7e5  mov     [rbp+var_40], 0
0x18000b7ed  mov     rax, [rcx]
0x18000b7f0  mov     rax, [rax+10h]
0x18000b7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f9  nop
0x18000b7fa  mov     rcx, [rbp+var_48]
0x18000b7fe  test    rcx, rcx
0x18000b801  jz      short loc_18000B818
0x18000b803  mov     [rbp+var_48], 0
0x18000b80b  mov     rax, [rcx]
0x18000b80e  mov     rax, [rax+10h]
0x18000b812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b817  nop
0x18000b818  mov     rcx, [rbp+var_38]
0x18000b81c  test    rcx, rcx
0x18000b81f  jz      short loc_18000B836
0x18000b821  mov     [rbp+var_38], 0
0x18000b829  mov     rax, [rcx]
0x18000b82c  mov     rax, [rax+10h]
0x18000b830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b835  nop
0x18000b836  mov     eax, ebx
0x18000b838  mov     rcx, [rbp+var_10]
0x18000b83c  xor     rcx, rsp; StackCookie
0x18000b83f  call    __security_check_cookie
0x18000b844  add     rsp, 78h
0x18000b848  pop     r15
0x18000b84a  pop     r14
0x18000b84c  pop     r13
0x18000b84e  pop     r12
0x18000b850  pop     rdi
0x18000b851  pop     rsi
0x18000b852  pop     rbx
0x18000b853  pop     rbp
0x18000b854  retn
0x18000b855  mov     ecx, eax; this
0x18000b857  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000b85c  int     3; Trap to Debugger
0x18000b85d  mov     ecx, eax; this
0x18000b85f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000b864  int     3; Trap to Debugger
0x18000b865  mov     ecx, eax; this
0x18000b867  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000b86c  int     3; Trap to Debugger
0x18000b86d  mov     ecx, eax; this
0x18000b86f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000b874  int     3; Trap to Debugger
0x18000b875  mov     ecx, eax; this
  ... truncated ...
```
