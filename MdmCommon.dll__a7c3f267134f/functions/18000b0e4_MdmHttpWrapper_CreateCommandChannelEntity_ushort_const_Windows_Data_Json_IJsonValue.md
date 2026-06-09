# MdmHttpWrapper::CreateCommandChannelEntity(ushort const *,Windows::Data::Json::IJsonValue * *)

- ea: `0x18000b0e4`
- end: `0x18000b62c`
- name: `?CreateCommandChannelEntity@MdmHttpWrapper@@CAJPEBGPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `1352`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c6e8`

## callees

- `0x180001520`
- `0x1800065c0`
- `0x18000af24`
- `0x18000afa4`
- `0x18000b0e4`
- `0x1800117e4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b3d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b4b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b3d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b4b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b236`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b236`

## string_xrefs

- `0x18000b20c`: `Windows.Data.Json.JsonValue`
- `0x18000b1a4`: `Windows.Data.Json.JsonObject`
- `0x18000b151`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000b1df`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18000b255`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18000b552`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x18000b13d`: `CPR(ppJsonValue)`
- `0x18000b17d`: `CBR(*ppJsonValue == nullptr)`
- `0x18000b2c4`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszChannelUrl).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000b2f9`: `CommandChannelUrl`
- `0x18000b33a`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"CommandChannelUrl").Get(), pJsonValue.Get()))`
- `0x18000b39c`: `CHR(pJsonValueStatics->CreateBooleanValue(false, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000b412`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"MpnsEnabled").Get(), pJsonValue.Get()))`
- `0x18000b47a`: `CHR(pJsonValueStatics->CreateNumberValue(1, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000b4f0`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"PushChannelType").Get(), pJsonValue.Get()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
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
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rsi
  __int64 v13; // rax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v15)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v16; // r14
  HRESULT v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rsi
  __int64 v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v24)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v25; // r14
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int64, struct Windows::Data::Json::IJsonValue **, __int64 *); // rsi
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v33)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v34; // r14
  HRESULT v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  __int64 (__fastcall ***v38)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v39)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // rsi
  struct Windows::Data::Json::IJsonValue *v40; // rcx
  struct Windows::Data::Json::IJsonValue *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  struct Windows::Data::Json::IJsonValue *v44; // rcx
  __int64 (__fastcall ***v45)(_QWORD, _QWORD, _QWORD); // rcx
  char v47; // [rsp+20h] [rbp-60h]
  const char *v48; // [rsp+28h] [rbp-58h]
  __int64 v49; // [rsp+30h] [rbp-50h] BYREF
  struct Windows::Data::Json::IJsonValue *v50; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // [rsp+40h] [rbp-40h] BYREF
  __int64 v52; // [rsp+48h] [rbp-38h] BYREF
  const unsigned __int16 *v53; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF

  v53 = a1;
  v51 = 0;
  v50 = 0;
  v49 = 0;
  v52 = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_48;
    v48 = "CPR(ppJsonValue)";
    v47 = -105;
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
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(string, &v51);
    if ( ActivationFactory >= 0 )
    {
      string = 0;
      v8 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v8 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
        __debugbreak();
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v52);
      if ( ActivationFactory >= 0 )
      {
        v11 = v52;
        v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 80LL);
        v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v53);
        ActivationFactory = v12(v11, *(_QWORD *)(v13 + 24), &v49);
        if ( ActivationFactory >= 0 )
        {
          v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v51;
          v15 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v51;
          v16 = v49;
          string = 0;
          v17 = WindowsCreateStringReference(L"CommandChannelUrl", 0x11u, &hstringHeader, &string);
          if ( v17 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
            __debugbreak();
          }
          ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v15)[7](v14, string, v16);
          if ( ActivationFactory >= 0 )
          {
            v20 = v52;
            v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 64LL);
            v22 = v49;
            if ( v49 )
            {
              v49 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
            ActivationFactory = v21(v20, 0, &v49);
            if ( ActivationFactory >= 0 )
            {
              v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v51;
              v24 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v51;
              v25 = v49;
              string = 0;
              v26 = WindowsCreateStringReference(L"MpnsEnabled", 0xBu, &hstringHeader, &string);
              if ( v26 < 0 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
                JUMPOUT(0x18000B62BLL);
              }
              ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v24)[7](v23, string, v25);
              if ( ActivationFactory >= 0 )
              {
                v29 = v52;
                v30 = *(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue **, __int64 *))(*(_QWORD *)v52 + 72LL);
                v31 = v49;
                if ( v49 )
                {
                  v49 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                }
                ActivationFactory = v30(v29, a2, &v49);
                if ( ActivationFactory >= 0 )
                {
                  v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v51;
                  v33 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v51;
                  v34 = v49;
                  string = 0;
                  v35 = WindowsCreateStringReference(L"PushChannelType", 0xFu, &hstringHeader, &string);
                  if ( v35 < 0 )
                  {
                    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
                    __debugbreak();
                  }
                  ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v33)[7](v32, string, v34);
                  if ( ActivationFactory >= 0 )
                  {
                    v38 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v51;
                    v39 = **v51;
                    v40 = v50;
                    if ( v50 )
                    {
                      v50 = 0;
                      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v40 + 16LL))(v40);
                    }
                    ActivationFactory = v39(v38, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v50);
                    if ( ActivationFactory >= 0 )
                    {
                      v41 = v50;
                      v50 = 0;
                      *a2 = v41;
                      goto LABEL_48;
                    }
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                      goto LABEL_48;
                    v48 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
                    v47 = -87;
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                      goto LABEL_48;
                    v48 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"PushChannelType\").Get(), pJsonValue.Get()))";
                    v47 = -89;
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                    goto LABEL_48;
                  v48 = "CHR(pJsonValueStatics->CreateNumberValue(1, pJsonValue.ReleaseAndGetAddressOf()))";
                  v47 = -90;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                  goto LABEL_48;
                v48 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"MpnsEnabled\").Get(), pJsonValue.Get()))";
                v47 = -93;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                goto LABEL_48;
              v48 = "CHR(pJsonValueStatics->CreateBooleanValue(false, pJsonValue.ReleaseAndGetAddressOf()))";
              v47 = -94;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
              goto LABEL_48;
            v48 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"CommandChannelUrl\").Get(), pJsonValue.Get()))";
            v47 = -97;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_48;
          v48 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszChannelUrl).Get(), pJsonValue.ReleaseAndGetAddressOf()))";
          v47 = -98;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_48;
        v48 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStati"
              "cs.GetAddressOf()))";
        v47 = -101;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_48;
      v48 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))";
      v47 = -102;
    }
    v3 = ActivationFactory;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      v3,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      v47,
      v48);
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
      "CBR(*ppJsonValue == nullptr)");
LABEL_48:
  v42 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v51;
  if ( v51 )
  {
    v51 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v45)[2])(v45);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000b0e4  mov     [rsp-28h+arg_10], rbx
0x18000b0e9  push    rbp
0x18000b0ea  push    rsi
0x18000b0eb  push    rdi
0x18000b0ec  push    r14
0x18000b0ee  push    r15
0x18000b0f0  mov     rbp, rsp
0x18000b0f3  sub     rsp, 80h
0x18000b0fa  mov     rax, cs:__security_cookie
0x18000b101  xor     rax, rsp
0x18000b104  mov     [rbp+var_8], rax
0x18000b108  mov     rdi, rdx
0x18000b10b  mov     [rbp+var_30], rcx
0x18000b10f  xor     r15d, r15d
0x18000b112  mov     [rbp+var_40], r15
0x18000b116  mov     [rbp+var_48], r15
0x18000b11a  mov     [rbp+var_50], r15
0x18000b11e  mov     [rbp+var_38], r15
0x18000b122  test    rdx, rdx
0x18000b125  jnz     short loc_18000B162
0x18000b127  mov     r8d, 80070057h
0x18000b12d  mov     ebx, r8d
0x18000b130  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b137  jz      loc_18000B576
0x18000b13d  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x18000b144  mov     [rsp+80h+var_58], rax
0x18000b149  mov     dword ptr [rsp+80h+var_60], 397h
0x18000b151  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000b158  call    McTemplateU0dsqs_EventWriteTransfer
0x18000b15d  jmp     loc_18000B576
0x18000b162  cmp     [rdx], r15
0x18000b165  jz      short loc_18000B193
0x18000b167  mov     r8d, 80070057h
0x18000b16d  mov     ebx, r8d
0x18000b170  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b177  jz      loc_18000B576
0x18000b17d  lea     rax, aCbrPpjsonvalue; "CBR(*ppJsonValue == nullptr)"
0x18000b184  mov     [rsp+80h+var_58], rax
0x18000b189  mov     dword ptr [rsp+80h+var_60], 398h
0x18000b191  jmp     short loc_18000B151
0x18000b193  mov     [rbp+string], r15
0x18000b197  lea     r9, [rbp+string]; string
0x18000b19b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b19f  mov     edx, 1Ch; length
0x18000b1a4  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000b1ab  call    cs:__imp_WindowsCreateStringReference
0x18000b1b2  nop     dword ptr [rax+rax+00h]
0x18000b1b7  test    eax, eax
0x18000b1b9  js      loc_18000B60C
0x18000b1bf  lea     rdx, [rbp+var_40]
0x18000b1c3  mov     rcx, [rbp+string]
0x18000b1c7  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18000b1cc  mov     ebx, eax
0x18000b1ce  test    eax, eax
0x18000b1d0  jns     short loc_18000B1FB
0x18000b1d2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b1d9  jz      loc_18000B576
0x18000b1df  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18000b1e6  mov     [rsp+80h+var_58], rax
0x18000b1eb  mov     dword ptr [rsp+80h+var_60], 39Ah
0x18000b1f3  mov     r8d, ebx
0x18000b1f6  jmp     loc_18000B151
0x18000b1fb  mov     [rbp+string], r15
0x18000b1ff  lea     r9, [rbp+string]; string
0x18000b203  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b207  mov     edx, 1Bh; length
0x18000b20c  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18000b213  call    cs:__imp_WindowsCreateStringReference
0x18000b21a  nop     dword ptr [rax+rax+00h]
0x18000b21f  test    eax, eax
0x18000b221  js      loc_18000B614
0x18000b227  lea     r8, [rbp+var_38]
0x18000b22b  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000b232  mov     rcx, [rbp+string]
0x18000b236  call    cs:__imp_RoGetActivationFactory
0x18000b23d  nop     dword ptr [rax+rax+00h]
0x18000b242  mov     ebx, eax
0x18000b244  test    eax, eax
0x18000b246  jns     short loc_18000B26B
0x18000b248  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b24f  jz      loc_18000B576
0x18000b255  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x18000b25c  mov     [rsp+80h+var_58], rax
0x18000b261  mov     dword ptr [rsp+80h+var_60], 39Bh
0x18000b269  jmp     short loc_18000B1F3
0x18000b26b  mov     rbx, [rbp+var_38]
0x18000b26f  mov     rax, [rbx]
0x18000b272  mov     rsi, [rax+50h]
0x18000b276  mov     rcx, [rbp+var_50]
0x18000b27a  test    rcx, rcx
0x18000b27d  jz      short loc_18000B290
0x18000b27f  mov     [rbp+var_50], r15
0x18000b283  mov     rax, [rcx]
0x18000b286  mov     rax, [rax+10h]
0x18000b28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b28f  nop
0x18000b290  lea     rdx, [rbp+var_30]
0x18000b294  lea     rcx, [rbp+hstringHeader]
0x18000b298  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000b29d  nop
0x18000b29e  lea     r8, [rbp+var_50]
0x18000b2a2  mov     rdx, [rax+18h]
0x18000b2a6  mov     rcx, rbx
0x18000b2a9  mov     rax, rsi
0x18000b2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2b1  mov     ebx, eax
0x18000b2b3  test    eax, eax
0x18000b2b5  jns     short loc_18000B2DD
0x18000b2b7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b2be  jz      loc_18000B576
0x18000b2c4  lea     rax, aChrPjsonvalues_2; "CHR(pJsonValueStatics->CreateStringValu"...
0x18000b2cb  mov     [rsp+80h+var_58], rax
0x18000b2d0  mov     dword ptr [rsp+80h+var_60], 39Eh
0x18000b2d8  jmp     loc_18000B1F3
0x18000b2dd  mov     rbx, [rbp+var_40]
0x18000b2e1  mov     rsi, [rbx]
0x18000b2e4  mov     r14, [rbp+var_50]
0x18000b2e8  mov     [rbp+string], r15
0x18000b2ec  lea     r9, [rbp+string]; string
0x18000b2f0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b2f4  mov     edx, 11h; length
0x18000b2f9  lea     rcx, sourceString; "CommandChannelUrl"
0x18000b300  call    cs:__imp_WindowsCreateStringReference
0x18000b307  nop     dword ptr [rax+rax+00h]
0x18000b30c  test    eax, eax
0x18000b30e  js      loc_18000B61C
0x18000b314  mov     r8, r14
0x18000b317  mov     rdx, [rbp+string]
0x18000b31b  mov     rcx, rbx
0x18000b31e  mov     rax, [rsi+38h]
0x18000b322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b327  mov     ebx, eax
0x18000b329  test    eax, eax
0x18000b32b  jns     short loc_18000B353
0x18000b32d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b334  jz      loc_18000B576
0x18000b33a  lea     rax, aChrPjsonobject_14; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b341  mov     [rsp+80h+var_58], rax
0x18000b346  mov     dword ptr [rsp+80h+var_60], 39Fh
0x18000b34e  jmp     loc_18000B1F3
0x18000b353  mov     rbx, [rbp+var_38]
0x18000b357  mov     rax, [rbx]
0x18000b35a  mov     rsi, [rax+40h]
0x18000b35e  mov     rcx, [rbp+var_50]
0x18000b362  test    rcx, rcx
0x18000b365  jz      short loc_18000B378
0x18000b367  mov     [rbp+var_50], r15
0x18000b36b  mov     rdx, [rcx]
0x18000b36e  mov     rax, [rdx+10h]
0x18000b372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b377  nop
0x18000b378  lea     r8, [rbp+var_50]
0x18000b37c  xor     edx, edx
0x18000b37e  mov     rcx, rbx
0x18000b381  mov     rax, rsi
0x18000b384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b389  mov     ebx, eax
0x18000b38b  test    eax, eax
0x18000b38d  jns     short loc_18000B3B5
0x18000b38f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b396  jz      loc_18000B576
0x18000b39c  lea     rax, aChrPjsonvalues_12; "CHR(pJsonValueStatics->CreateBooleanVal"...
0x18000b3a3  mov     [rsp+80h+var_58], rax
0x18000b3a8  mov     dword ptr [rsp+80h+var_60], 3A2h
0x18000b3b0  jmp     loc_18000B1F3
0x18000b3b5  mov     rbx, [rbp+var_40]
0x18000b3b9  mov     rsi, [rbx]
0x18000b3bc  mov     r14, [rbp+var_50]
0x18000b3c0  mov     [rbp+string], r15
0x18000b3c4  lea     r9, [rbp+string]; string
0x18000b3c8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b3cc  mov     edx, 0Bh; length
0x18000b3d1  lea     rcx, aMpnsenabled; "MpnsEnabled"
0x18000b3d8  call    cs:__imp_WindowsCreateStringReference
0x18000b3df  nop     dword ptr [rax+rax+00h]
0x18000b3e4  test    eax, eax
0x18000b3e6  js      loc_18000B624
0x18000b3ec  mov     r8, r14
0x18000b3ef  mov     rdx, [rbp+string]
0x18000b3f3  mov     rcx, rbx
0x18000b3f6  mov     rax, [rsi+38h]
0x18000b3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ff  mov     ebx, eax
0x18000b401  test    eax, eax
0x18000b403  jns     short loc_18000B42B
0x18000b405  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b40c  jz      loc_18000B576
0x18000b412  lea     rax, aChrPjsonobject_17; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b419  mov     [rsp+80h+var_58], rax
0x18000b41e  mov     dword ptr [rsp+80h+var_60], 3A3h
0x18000b426  jmp     loc_18000B1F3
0x18000b42b  mov     rbx, [rbp+var_38]
0x18000b42f  mov     rax, [rbx]
0x18000b432  mov     rsi, [rax+48h]
0x18000b436  mov     rcx, [rbp+var_50]
0x18000b43a  test    rcx, rcx
0x18000b43d  jz      short loc_18000B450
0x18000b43f  mov     [rbp+var_50], r15
0x18000b443  mov     rdx, [rcx]
0x18000b446  mov     rax, [rdx+10h]
0x18000b44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b44f  nop
0x18000b450  lea     r8, [rbp+var_50]
0x18000b454  movsd   xmm1, cs:__real@3ff0000000000000
0x18000b45c  mov     rcx, rbx
0x18000b45f  mov     rax, rsi
0x18000b462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b467  mov     ebx, eax
0x18000b469  test    eax, eax
0x18000b46b  jns     short loc_18000B493
0x18000b46d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b474  jz      loc_18000B576
0x18000b47a  lea     rax, aChrPjsonvalues_8; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000b481  mov     [rsp+80h+var_58], rax
0x18000b486  mov     dword ptr [rsp+80h+var_60], 3A6h
0x18000b48e  jmp     loc_18000B1F3
0x18000b493  mov     rbx, [rbp+var_40]
0x18000b497  mov     rsi, [rbx]
0x18000b49a  mov     r14, [rbp+var_50]
0x18000b49e  mov     [rbp+string], r15
0x18000b4a2  lea     r9, [rbp+string]; string
0x18000b4a6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b4aa  mov     edx, 0Fh; length
0x18000b4af  lea     rcx, aPushchanneltyp; "PushChannelType"
0x18000b4b6  call    cs:__imp_WindowsCreateStringReference
0x18000b4bd  nop     dword ptr [rax+rax+00h]
0x18000b4c2  test    eax, eax
0x18000b4c4  js      loc_18000B604
0x18000b4ca  mov     r8, r14
0x18000b4cd  mov     rdx, [rbp+string]
0x18000b4d1  mov     rcx, rbx
0x18000b4d4  mov     rax, [rsi+38h]
0x18000b4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4dd  mov     ebx, eax
0x18000b4df  test    eax, eax
0x18000b4e1  jns     short loc_18000B509
0x18000b4e3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b4ea  jz      loc_18000B576
0x18000b4f0  lea     rax, aChrPjsonobject_9; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000b4f7  mov     [rsp+80h+var_58], rax
0x18000b4fc  mov     dword ptr [rsp+80h+var_60], 3A7h
0x18000b504  jmp     loc_18000B1F3
0x18000b509  mov     rbx, [rbp+var_40]
0x18000b50d  mov     rax, [rbx]
0x18000b510  mov     rsi, [rax]
0x18000b513  mov     rcx, [rbp+var_48]
0x18000b517  test    rcx, rcx
0x18000b51a  jz      short loc_18000B52D
0x18000b51c  mov     [rbp+var_48], r15
0x18000b520  mov     rdx, [rcx]
0x18000b523  mov     rax, [rdx+10h]
0x18000b527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b52c  nop
0x18000b52d  lea     r8, [rbp+var_48]
0x18000b531  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18000b538  mov     rcx, rbx
0x18000b53b  mov     rax, rsi
0x18000b53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b543  mov     ebx, eax
0x18000b545  test    eax, eax
0x18000b547  jns     short loc_18000B56B
0x18000b549  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b550  jz      short loc_18000B576
0x18000b552  lea     rax, aChrPjsonobject_3; "CHR(pJsonObject.As(&pJsonObjectAsValue)"...
0x18000b559  mov     [rsp+80h+var_58], rax
0x18000b55e  mov     dword ptr [rsp+80h+var_60], 3A9h
0x18000b566  jmp     loc_18000B1F3
0x18000b56b  mov     rax, [rbp+var_48]
0x18000b56f  mov     [rbp+var_48], r15
0x18000b573  mov     [rdi], rax
0x18000b576  mov     rcx, [rbp+var_38]
0x18000b57a  test    rcx, rcx
0x18000b57d  jz      short loc_18000B590
0x18000b57f  mov     [rbp+var_38], r15
0x18000b583  mov     rax, [rcx]
0x18000b586  mov     rax, [rax+10h]
0x18000b58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b58f  nop
0x18000b590  mov     rcx, [rbp+var_50]
0x18000b594  test    rcx, rcx
0x18000b597  jz      short loc_18000B5AA
0x18000b599  mov     [rbp+var_50], r15
0x18000b59d  mov     rax, [rcx]
0x18000b5a0  mov     rax, [rax+10h]
0x18000b5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a9  nop
0x18000b5aa  mov     rcx, [rbp+var_48]
0x18000b5ae  test    rcx, rcx
0x18000b5b1  jz      short loc_18000B5C4
0x18000b5b3  mov     [rbp+var_48], r15
0x18000b5b7  mov     rax, [rcx]
0x18000b5ba  mov     rax, [rax+10h]
0x18000b5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c3  nop
0x18000b5c4  mov     rcx, [rbp+var_40]
0x18000b5c8  test    rcx, rcx
0x18000b5cb  jz      short loc_18000B5DE
0x18000b5cd  mov     [rbp+var_40], r15
0x18000b5d1  mov     rax, [rcx]
0x18000b5d4  mov     rax, [rax+10h]
  ... truncated ...
```
