# MdmHttpWrapper::CreateRegisterUserDeviceRequestBody(MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000e97c`
- end: `0x18000ef2d`
- name: `?CreateRegisterUserDeviceRequestBody@MdmHttpWrapper@@CAJW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1457`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011a78`

## callees

- `0x180001520`
- `0x1800028e4`
- `0x180002de4`
- `0x180006548`
- `0x18000ac7c`
- `0x18000acf4`
- `0x18000e97c`
- `0x180011414`
- `0x180011cf4`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000edff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000edff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000edb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000eeda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000edb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000eeda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ea65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ead2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ebeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ec6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ece9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ea65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ead2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ebeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ec6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ece9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000eaf4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000eaf4`

## string_xrefs

- `0x18000eacb`: `Windows.Data.Json.JsonValue`
- `0x18000ea5e`: `Windows.Data.Json.JsonObject`
- `0x18000ea12`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000ea98`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18000eb0d`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18000eba4`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrTrigger.c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000ec23`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"RegistrationTrigger").Get(), pJsonValue.Get()))`
- `0x18000ed8b`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x18000eddf`: `CHR(pJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))`
- `0x18000eca2`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"DeviceInfo").Get(), pDeviceInfo))`
- `0x18000ed21`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"UserInfo").Get(), pUserInfo))`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterUserDeviceRequestBody(__int64 a1, __int64 a2, __int64 a3, char *a4)
{
  int v7; // edx
  int v8; // ecx
  int ActivationFactory; // edi
  char *v10; // rax
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, PVOID, __int64 *); // rdi
  __int64 v20; // rcx
  const WCHAR *v21; // rdx
  HSTRING_HEADER *v22; // rax
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v24)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v25; // r15
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v30)(_QWORD, _QWORD, _QWORD); // rdi
  HRESULT v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v35)(_QWORD, _QWORD, _QWORD); // rdi
  HRESULT v36; // eax
  int v37; // edx
  unsigned int v38; // r8d
  __int64 (__fastcall ***v39)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v40)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v41; // rcx
  _QWORD *v42; // rdi
  __int64 (__fastcall *v43)(_QWORD *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v45; // r8
  unsigned __int64 v46; // rdx
  __int64 v47; // rbx
  int v48; // ecx
  __int64 v49; // rcx
  __int64 v50; // rcx
  _QWORD *v51; // rcx
  __int64 (__fastcall ***v52)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v54; // [rsp+0h] [rbp-E8h] BYREF
  int v55; // [rsp+20h] [rbp-C8h]
  const char *v56; // [rsp+28h] [rbp-C0h]
  __int64 (__fastcall ***v57)(_QWORD, GUID *, _QWORD **); // [rsp+30h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+38h] [rbp-B0h] BYREF
  _QWORD *v59; // [rsp+40h] [rbp-A8h] BYREF
  HSTRING v60; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v61; // [rsp+50h] [rbp-98h] BYREF
  const WCHAR *v62; // [rsp+58h] [rbp-90h] BYREF
  unsigned __int64 *v63; // [rsp+60h] [rbp-88h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-80h] BYREF
  HSTRING string; // [rsp+80h] [rbp-68h] BYREF
  __int128 v66; // [rsp+88h] [rbp-60h] BYREF
  __m128i si128; // [rsp+98h] [rbp-50h]

  v60 = 0;
  v57 = 0;
  v59 = 0;
  v58 = 0;
  v61 = 0;
  v66 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v66) = 0;
  ActivationFactory = MdmHttpWrapper::RegistrationTriggerToString(a1, (__int64)&v66);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_51;
    v56 = "CHR(RegistrationTriggerToString(eTrigger, wstrTrigger))";
    v55 = 873;
    goto LABEL_4;
  }
  v63 = (unsigned __int64 *)(a4 + 16);
  *((_QWORD *)a4 + 2) = 0;
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v10 = a4;
  else
    v10 = *(char **)a4;
  *(_WORD *)v10 = 0;
  string = 0;
  v11 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    ((void (__fastcall *)(Microsoft::WRL::Details *, int, unsigned int))Microsoft::WRL::Details::RaiseException)(
      (Microsoft::WRL::Details *)(unsigned int)v11,
      v12,
      v13);
    __debugbreak();
  }
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)string, &v57);
  if ( ActivationFactory >= 0 )
  {
    string = 0;
    v14 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
    if ( v14 < 0 )
    {
      ((void (__fastcall *)(Microsoft::WRL::Details *, int, unsigned int))Microsoft::WRL::Details::RaiseException)(
        (Microsoft::WRL::Details *)(unsigned int)v14,
        v15,
        v16);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v61);
    if ( ActivationFactory >= 0 )
    {
      v18 = v61;
      v19 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v61 + 80LL);
      v20 = v58;
      if ( v58 )
      {
        v58 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v21 = (const WCHAR *)&v66;
      if ( si128.m128i_i64[1] > 7uLL )
        v21 = (const WCHAR *)v66;
      v62 = v21;
      v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v62, v17);
      ActivationFactory = v19(v18, v22[1].Reserved.Reserved1, &v58);
      if ( ActivationFactory >= 0 )
      {
        v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
        v24 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v57;
        v25 = v58;
        string = 0;
        v26 = WindowsCreateStringReference(L"RegistrationTrigger", 0x13u, &hstringHeader, &string);
        if ( v26 < 0 )
        {
          ((void (__fastcall *)(Microsoft::WRL::Details *, int, unsigned int))Microsoft::WRL::Details::RaiseException)(
            (Microsoft::WRL::Details *)(unsigned int)v26,
            v27,
            v28);
          __debugbreak();
        }
        ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v24)[7](v23, string, v25);
        if ( ActivationFactory >= 0 )
        {
          if ( !a2 )
            goto LABEL_77;
          v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
          v30 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v57;
          string = 0;
          v31 = WindowsCreateStringReference(L"DeviceInfo", 0xAu, &hstringHeader, &string);
          if ( v31 < 0 )
          {
            ((void (__fastcall *)(Microsoft::WRL::Details *, int, unsigned int))Microsoft::WRL::Details::RaiseException)(
              (Microsoft::WRL::Details *)(unsigned int)v31,
              v32,
              v33);
            __debugbreak();
          }
          ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v30)[7](v29, string, a2);
          if ( ActivationFactory < 0 )
          {
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            {
              v56 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"DeviceInfo\").Get(), pDeviceInfo))";
              v55 = 885;
              goto LABEL_4;
            }
          }
          else
          {
LABEL_77:
            if ( !a3 )
              goto LABEL_37;
            v34 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
            v35 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v57;
            string = 0;
            v36 = WindowsCreateStringReference(L"UserInfo", 8u, &hstringHeader, &string);
            if ( v36 < 0 )
            {
              ((void (__fastcall *)(Microsoft::WRL::Details *, int, unsigned int))Microsoft::WRL::Details::RaiseException)(
                (Microsoft::WRL::Details *)(unsigned int)v36,
                v37,
                v38);
              JUMPOUT(0x18000EF2CLL);
            }
            ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v35)[7](v34, string, a3);
            if ( ActivationFactory < 0 )
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              {
                v56 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"UserInfo\").Get(), pUserInfo))";
                v55 = 890;
                goto LABEL_4;
              }
            }
            else
            {
LABEL_37:
              v39 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
              v40 = **v57;
              v41 = v59;
              if ( v59 )
              {
                v59 = 0;
                (*(void (__fastcall **)(_QWORD *, _QWORD))(*v41 + 16LL))(v41, *v41);
              }
              ActivationFactory = v40(v39, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v59);
              if ( ActivationFactory >= 0 )
              {
                v42 = v59;
                v43 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v59 + 56LL);
                WindowsDeleteString(v60);
                v60 = 0;
                ActivationFactory = v43(v42, &v60);
                if ( ActivationFactory >= 0 )
                {
                  StringRawBuffer = WindowsGetStringRawBuffer(v60, 0);
                  v46 = -1;
                  do
                    ++v46;
                  while ( StringRawBuffer[v46] );
                  if ( v46 > *((_QWORD *)a4 + 3) )
                  {
                    if ( __eh34_try(-1, 0) )
                    {
                      __eh34_scope_strut(0);
                      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                        (char **)a4,
                        v46,
                        v45,
                        StringRawBuffer);
                    }
                    if ( __eh34_catch(0) )
                    {
                      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
                      {
                        LODWORD(v62) = -2147024882;
                        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                          McTemplateU0dsqs_EventWriteTransfer(
                            v48,
                            (unsigned int)&v54,
                            -2147024882,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                            134,
                            "CHR(((HRESULT)0x8007000EL))");
                        ActivationFactory = (int)v62;
                        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000EE51);
                      }
                    }
                  }
                  else
                  {
                    if ( *((_QWORD *)a4 + 3) > 7u )
                      a4 = *(char **)a4;
                    *v63 = v46;
                    v47 = 2 * v46;
                    memmove_0(a4, StringRawBuffer, 2 * v46);
                    *(_WORD *)&a4[v47] = 0;
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                {
                  v56 = "CHR(pJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))";
                  v55 = 894;
                  goto LABEL_4;
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              {
                v56 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
                v55 = 893;
                goto LABEL_4;
              }
            }
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v56 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"RegistrationTrigger\").Get(), pJsonValue.Get()))";
          v55 = 881;
          goto LABEL_4;
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v56 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrTrigger.c_str()).Get(), pJsonValue.ReleaseAn"
              "dGetAddressOf()))";
        v55 = 880;
        goto LABEL_4;
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v56 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics"
            ".GetAddressOf()))";
      v55 = 878;
      goto LABEL_4;
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    v56 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))";
    v55 = 877;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      v8,
      v7,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      v55,
      v56);
  }
LABEL_51:
  std::wstring::~wstring((char **)&v66);
  v49 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
  }
  v52 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
  if ( v57 )
  {
    v57 = 0;
    ((void (__fastcall *)(_QWORD))(*v52)[2])(v52);
  }
  WindowsDeleteString(v60);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000e97c  mov     r11, rsp
0x18000e97f  push    rbx
0x18000e980  push    rsi
0x18000e981  push    rdi
0x18000e982  push    r12
0x18000e984  push    r13
0x18000e986  push    r14
0x18000e988  push    r15
0x18000e98a  sub     rsp, 0B0h
0x18000e991  mov     rax, cs:__security_cookie
0x18000e998  xor     rax, rsp
0x18000e99b  mov     [rsp+0E8h+var_40], rax
0x18000e9a3  mov     r14, r9
0x18000e9a6  mov     r13, r8
0x18000e9a9  mov     r12, rdx
0x18000e9ac  xor     esi, esi
0x18000e9ae  mov     [rsp+0E8h+var_A0], rsi
0x18000e9b3  mov     [rsp+0E8h+var_B8], rsi
0x18000e9b8  mov     [rsp+0E8h+var_A8], rsi
0x18000e9bd  mov     [rsp+0E8h+var_B0], rsi
0x18000e9c2  mov     [rsp+0E8h+var_98], rsi
0x18000e9c7  xorps   xmm0, xmm0
0x18000e9ca  movups  xmmword ptr [r11-60h], xmm0
0x18000e9cf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000e9d7  movdqu  xmmword ptr [r11-50h], xmm1
0x18000e9dd  mov     [r11-60h], si
0x18000e9e2  lea     rdx, [r11-60h]
0x18000e9e6  call    ?RegistrationTriggerToString@MdmHttpWrapper@@CAJW4MdmRegistrationTrigger@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpWrapper::RegistrationTriggerToString(MdmRegistrationTrigger,std::wstring &)
0x18000e9eb  mov     edi, eax
0x18000e9ed  test    eax, eax
0x18000e9ef  jns     short loc_18000EA26
0x18000e9f1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000e9f8  jz      loc_18000EE57
0x18000e9fe  lea     rax, aChrRegistratio; "CHR(RegistrationTriggerToString(eTrigge"...
0x18000ea05  mov     [rsp+0E8h+var_C0], rax
0x18000ea0a  mov     [rsp+0E8h+var_C8], 369h
0x18000ea12  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000ea19  mov     r8d, edi
0x18000ea1c  call    McTemplateU0dsqs_EventWriteTransfer
0x18000ea21  jmp     loc_18000EE57
0x18000ea26  lea     rax, [r14+10h]
0x18000ea2a  mov     [rsp+0E8h+var_88], rax
0x18000ea2f  mov     [rax], rsi
0x18000ea32  cmp     qword ptr [r14+18h], 7
0x18000ea37  jbe     short loc_18000EA3E
0x18000ea39  mov     rax, [r14]
0x18000ea3c  jmp     short loc_18000EA41
0x18000ea3e  mov     rax, r14
0x18000ea41  mov     [rax], si
0x18000ea44  mov     [rsp+0E8h+string], rsi
0x18000ea4c  lea     r9, [rsp+0E8h+string]; string
0x18000ea54  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000ea59  mov     edx, 1Ch; length
0x18000ea5e  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000ea65  call    cs:__imp_WindowsCreateStringReference
0x18000ea6b  test    eax, eax
0x18000ea6d  js      loc_18000EF05
0x18000ea73  lea     rdx, [rsp+0E8h+var_B8]
0x18000ea78  mov     rcx, [rsp+0E8h+string]
0x18000ea80  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18000ea85  mov     edi, eax
0x18000ea87  test    eax, eax
0x18000ea89  jns     short loc_18000EAB1
0x18000ea8b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ea92  jz      loc_18000EE57
0x18000ea98  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18000ea9f  mov     [rsp+0E8h+var_C0], rax
0x18000eaa4  mov     [rsp+0E8h+var_C8], 36Dh
0x18000eaac  jmp     loc_18000EA12
0x18000eab1  mov     [rsp+0E8h+string], rsi
0x18000eab9  lea     r9, [rsp+0E8h+string]; string
0x18000eac1  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000eac6  mov     edx, 1Bh; length
0x18000eacb  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18000ead2  call    cs:__imp_WindowsCreateStringReference
0x18000ead8  test    eax, eax
0x18000eada  js      loc_18000EF0D
0x18000eae0  lea     r8, [rsp+0E8h+var_98]
0x18000eae5  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000eaec  mov     rcx, [rsp+0E8h+string]
0x18000eaf4  call    cs:__imp_RoGetActivationFactory
0x18000eafa  mov     edi, eax
0x18000eafc  test    eax, eax
0x18000eafe  jns     short loc_18000EB26
0x18000eb00  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000eb07  jz      loc_18000EE57
0x18000eb0d  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x18000eb14  mov     [rsp+0E8h+var_C0], rax
0x18000eb19  mov     [rsp+0E8h+var_C8], 36Eh
0x18000eb21  jmp     loc_18000EA12
0x18000eb26  mov     rbx, [rsp+0E8h+var_98]
0x18000eb2b  mov     rax, [rbx]
0x18000eb2e  mov     rdi, [rax+50h]
0x18000eb32  mov     rcx, [rsp+0E8h+var_B0]
0x18000eb37  test    rcx, rcx
0x18000eb3a  jz      short loc_18000EB4E
0x18000eb3c  mov     [rsp+0E8h+var_B0], rsi
0x18000eb41  mov     rax, [rcx]
0x18000eb44  mov     rax, [rax+10h]
0x18000eb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb4d  nop
0x18000eb4e  lea     rdx, [rsp+0E8h+var_60]
0x18000eb56  cmp     [rsp+0E8h+var_48], 7
0x18000eb5f  cmova   rdx, qword ptr [rsp+0E8h+var_60]
0x18000eb68  mov     [rsp+0E8h+var_90], rdx
0x18000eb6d  lea     rdx, [rsp+0E8h+var_90]
0x18000eb72  lea     rcx, [rsp+0E8h+hstringHeader]
0x18000eb77  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000eb7c  nop
0x18000eb7d  lea     r8, [rsp+0E8h+var_B0]
0x18000eb82  mov     rdx, [rax+18h]
0x18000eb86  mov     rcx, rbx
0x18000eb89  mov     rax, rdi
0x18000eb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb91  mov     edi, eax
0x18000eb93  test    eax, eax
0x18000eb95  jns     short loc_18000EBBD
0x18000eb97  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000eb9e  jz      loc_18000EE57
0x18000eba4  lea     rax, aChrPjsonvalues_11; "CHR(pJsonValueStatics->CreateStringValu"...
0x18000ebab  mov     [rsp+0E8h+var_C0], rax
0x18000ebb0  mov     [rsp+0E8h+var_C8], 370h
0x18000ebb8  jmp     loc_18000EA12
0x18000ebbd  mov     rbx, [rsp+0E8h+var_B8]
0x18000ebc2  mov     rdi, [rbx]
0x18000ebc5  mov     r15, [rsp+0E8h+var_B0]
0x18000ebca  mov     [rsp+0E8h+string], rsi
0x18000ebd2  lea     r9, [rsp+0E8h+string]; string
0x18000ebda  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000ebdf  mov     edx, 13h; length
0x18000ebe4  lea     rcx, aRegistrationtr; "RegistrationTrigger"
0x18000ebeb  call    cs:__imp_WindowsCreateStringReference
0x18000ebf1  test    eax, eax
0x18000ebf3  js      loc_18000EF15
0x18000ebf9  mov     r8, r15
0x18000ebfc  mov     rdx, [rsp+0E8h+string]
0x18000ec04  mov     rcx, rbx
0x18000ec07  mov     rax, [rdi+38h]
0x18000ec0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec10  mov     edi, eax
0x18000ec12  test    eax, eax
0x18000ec14  jns     short loc_18000EC3C
0x18000ec16  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ec1d  jz      loc_18000EE57
0x18000ec23  lea     rax, aChrPjsonobject_23; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000ec2a  mov     [rsp+0E8h+var_C0], rax
0x18000ec2f  mov     [rsp+0E8h+var_C8], 371h
0x18000ec37  jmp     loc_18000EA12
0x18000ec3c  test    r12, r12
0x18000ec3f  jz      short loc_18000ECBB
0x18000ec41  mov     rbx, [rsp+0E8h+var_B8]
0x18000ec46  mov     rdi, [rbx]
0x18000ec49  mov     [rsp+0E8h+string], rsi
0x18000ec51  lea     r9, [rsp+0E8h+string]; string
0x18000ec59  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000ec5e  mov     edx, 0Ah; length
0x18000ec63  lea     rcx, aDeviceinfo; "DeviceInfo"
0x18000ec6a  call    cs:__imp_WindowsCreateStringReference
0x18000ec70  test    eax, eax
0x18000ec72  js      loc_18000EF1D
0x18000ec78  mov     r8, r12
0x18000ec7b  mov     rdx, [rsp+0E8h+string]
0x18000ec83  mov     rcx, rbx
0x18000ec86  mov     rax, [rdi+38h]
0x18000ec8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec8f  mov     edi, eax
0x18000ec91  test    eax, eax
0x18000ec93  jns     short loc_18000ECBB
0x18000ec95  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ec9c  jz      loc_18000EE57
0x18000eca2  lea     rax, aChrPjsonobject_34; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000eca9  mov     [rsp+0E8h+var_C0], rax
0x18000ecae  mov     [rsp+0E8h+var_C8], 375h
0x18000ecb6  jmp     loc_18000EA12
0x18000ecbb  test    r13, r13
0x18000ecbe  jz      short loc_18000ED3A
0x18000ecc0  mov     rbx, [rsp+0E8h+var_B8]
0x18000ecc5  mov     rdi, [rbx]
0x18000ecc8  mov     [rsp+0E8h+string], rsi
0x18000ecd0  lea     r9, [rsp+0E8h+string]; string
0x18000ecd8  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000ecdd  mov     edx, 8; length
0x18000ece2  lea     rcx, aUserinfo; "UserInfo"
0x18000ece9  call    cs:__imp_WindowsCreateStringReference
0x18000ecef  test    eax, eax
0x18000ecf1  js      loc_18000EF25
0x18000ecf7  mov     r8, r13
0x18000ecfa  mov     rdx, [rsp+0E8h+string]
0x18000ed02  mov     rcx, rbx
0x18000ed05  mov     rax, [rdi+38h]
0x18000ed09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed0e  mov     edi, eax
0x18000ed10  test    eax, eax
0x18000ed12  jns     short loc_18000ED3A
0x18000ed14  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ed1b  jz      loc_18000EE57
0x18000ed21  lea     rax, aChrPjsonobject_29; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000ed28  mov     [rsp+0E8h+var_C0], rax
0x18000ed2d  mov     [rsp+0E8h+var_C8], 37Ah
0x18000ed35  jmp     loc_18000EA12
0x18000ed3a  mov     rbx, [rsp+0E8h+var_B8]
0x18000ed3f  mov     rax, [rbx]
0x18000ed42  mov     rdi, [rax]
0x18000ed45  mov     rcx, [rsp+0E8h+var_A8]
0x18000ed4a  test    rcx, rcx
0x18000ed4d  jz      short loc_18000ED61
0x18000ed4f  mov     [rsp+0E8h+var_A8], rsi
0x18000ed54  mov     rdx, [rcx]
0x18000ed57  mov     rax, [rdx+10h]
0x18000ed5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed60  nop
0x18000ed61  lea     r8, [rsp+0E8h+var_A8]
0x18000ed66  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18000ed6d  mov     rcx, rbx
0x18000ed70  mov     rax, rdi
0x18000ed73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed78  mov     edi, eax
0x18000ed7a  test    eax, eax
0x18000ed7c  jns     short loc_18000EDA4
0x18000ed7e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ed85  jz      loc_18000EE57
0x18000ed8b  lea     rax, aChrPjsonobject_3; "CHR(pJsonObject.As(&pJsonObjectAsValue)"...
0x18000ed92  mov     [rsp+0E8h+var_C0], rax
0x18000ed97  mov     [rsp+0E8h+var_C8], 37Dh
0x18000ed9f  jmp     loc_18000EA12
0x18000eda4  mov     rdi, [rsp+0E8h+var_A8]
0x18000eda9  mov     rax, [rdi]
0x18000edac  mov     rbx, [rax+38h]
0x18000edb0  mov     rcx, [rsp+0E8h+var_A0]; string
0x18000edb5  call    cs:__imp_WindowsDeleteString
0x18000edbb  mov     [rsp+0E8h+var_A0], rsi
0x18000edc0  lea     rdx, [rsp+0E8h+var_A0]
0x18000edc5  mov     rcx, rdi
0x18000edc8  mov     rax, rbx
0x18000edcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edd0  mov     edi, eax
0x18000edd2  test    eax, eax
0x18000edd4  jns     short loc_18000EDF8
0x18000edd6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000eddd  jz      short loc_18000EE57
0x18000eddf  lea     rax, aChrPjsonobject_33; "CHR(pJsonObjectAsValue->Stringify(hstrB"...
0x18000ede6  mov     [rsp+0E8h+var_C0], rax
0x18000edeb  mov     [rsp+0E8h+var_C8], 37Eh
0x18000edf3  jmp     loc_18000EA12
0x18000edf8  xor     edx, edx; length
0x18000edfa  mov     rcx, [rsp+0E8h+var_A0]; string
0x18000edff  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ee05  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ee09  inc     rdx
0x18000ee0c  cmp     [rax+rdx*2], si
0x18000ee10  jnz     short loc_18000EE09
0x18000ee12  cmp     rdx, [r14+18h]
0x18000ee16  ja      short loc_18000EE43
0x18000ee18  cmp     qword ptr [r14+18h], 7
0x18000ee1d  jbe     short loc_18000EE22
0x18000ee1f  mov     r14, [r14]
0x18000ee22  mov     rcx, [rsp+0E8h+var_88]
0x18000ee27  mov     [rcx], rdx
0x18000ee2a  lea     rbx, [rdx+rdx]
0x18000ee2e  mov     r8, rbx; Size
0x18000ee31  mov     rdx, rax; Src
0x18000ee34  mov     rcx, r14; void *
0x18000ee37  call    memmove_0
0x18000ee3c  mov     [rbx+r14], si
0x18000ee41  jmp     short loc_18000EE4F
0x18000ee43  mov     r9, rax
0x18000ee46  mov     rcx, r14
0x18000ee49  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000ee4e  nop
0x18000ee4f  jmp     short loc_18000EE57
0x18000ee51  xor     esi, esi
0x18000ee53  mov     edi, dword ptr [rsp+0E8h+var_90]
0x18000ee57  lea     rcx, [rsp+0E8h+var_60]
0x18000ee5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ee64  nop
0x18000ee65  mov     rcx, [rsp+0E8h+var_98]
0x18000ee6a  test    rcx, rcx
0x18000ee6d  jz      short loc_18000EE81
0x18000ee6f  mov     [rsp+0E8h+var_98], rsi
0x18000ee74  mov     rax, [rcx]
0x18000ee77  mov     rax, [rax+10h]
0x18000ee7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee80  nop
0x18000ee81  mov     rcx, [rsp+0E8h+var_B0]
0x18000ee86  test    rcx, rcx
0x18000ee89  jz      short loc_18000EE9D
0x18000ee8b  mov     [rsp+0E8h+var_B0], rsi
0x18000ee90  mov     rax, [rcx]
0x18000ee93  mov     rax, [rax+10h]
0x18000ee97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee9c  nop
0x18000ee9d  mov     rcx, [rsp+0E8h+var_A8]
0x18000eea2  test    rcx, rcx
0x18000eea5  jz      short loc_18000EEB9
0x18000eea7  mov     [rsp+0E8h+var_A8], rsi
0x18000eeac  mov     rax, [rcx]
0x18000eeaf  mov     rax, [rax+10h]
0x18000eeb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeb8  nop
0x18000eeb9  mov     rcx, [rsp+0E8h+var_B8]
  ... truncated ...
```
