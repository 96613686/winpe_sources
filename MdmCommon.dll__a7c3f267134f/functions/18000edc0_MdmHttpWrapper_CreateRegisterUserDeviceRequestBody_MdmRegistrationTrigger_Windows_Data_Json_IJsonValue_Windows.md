# MdmHttpWrapper::CreateRegisterUserDeviceRequestBody(MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000edc0`
- end: `0x18000f3b0`
- name: `?CreateRegisterUserDeviceRequestBody@MdmHttpWrapper@@CAJW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1520`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011e50`

## callees

- `0x180001520`
- `0x1800028e4`
- `0x180002de8`
- `0x1800065c0`
- `0x18000af24`
- `0x18000afa4`
- `0x18000edc0`
- `0x1800117e4`
- `0x1800120d0`
- `0x18001dbfc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000eea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ef1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f0ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f153`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000eea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ef1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f0ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f153`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000ef44`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000ef44`

## string_xrefs

- `0x18000ef15`: `Windows.Data.Json.JsonValue`
- `0x18000eea2`: `Windows.Data.Json.JsonObject`
- `0x18000ee56`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000eee2`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18000ef63`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18000effa`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrTrigger.c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000f07f`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"RegistrationTrigger").Get(), pJsonValue.Get()))`
- `0x18000f1fb`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x18000f255`: `CHR(pJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))`
- `0x18000f108`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"DeviceInfo").Get(), pDeviceInfo))`
- `0x18000f191`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"UserInfo").Get(), pUserInfo))`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall MdmHttpWrapper::CreateRegisterUserDeviceRequestBody(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  int v7; // edx
  int v8; // ecx
  int ActivationFactory; // edi
  _WORD *v10; // rax
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  int v14; // edx
  int v15; // ecx
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  int v19; // edx
  int v20; // ecx
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rdi
  __int64 v23; // rcx
  __int128 *v24; // rdx
  __int64 v25; // rax
  int v26; // edx
  int v27; // ecx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v29)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v30; // r15
  HRESULT v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  int v34; // edx
  int v35; // ecx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v37)(_QWORD, _QWORD, _QWORD); // rdi
  HRESULT v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  int v41; // edx
  int v42; // ecx
  __int64 (__fastcall ***v43)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v44)(_QWORD, _QWORD, _QWORD); // rdi
  HRESULT v45; // eax
  int v46; // edx
  unsigned int v47; // r8d
  int v48; // edx
  int v49; // ecx
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v51)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v52; // rcx
  int v53; // edx
  int v54; // ecx
  _QWORD *v55; // rdi
  __int64 (__fastcall *v56)(_QWORD *, HSTRING *); // rbx
  int v57; // edx
  int v58; // ecx
  PCWSTR StringRawBuffer; // rax
  __int64 v60; // r8
  unsigned __int64 v61; // rdx
  __int64 v62; // rbx
  int v63; // ecx
  __int64 v64; // rcx
  __int64 v65; // rcx
  _QWORD *v66; // rcx
  __int64 (__fastcall ***v67)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v69; // [rsp+0h] [rbp-E8h] BYREF
  __int64 (__fastcall ***v70)(_QWORD, GUID *, _QWORD **); // [rsp+30h] [rbp-B8h] BYREF
  __int64 v71; // [rsp+38h] [rbp-B0h] BYREF
  _QWORD *v72; // [rsp+40h] [rbp-A8h] BYREF
  HSTRING v73; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v74; // [rsp+50h] [rbp-98h] BYREF
  __int128 *v75; // [rsp+58h] [rbp-90h] BYREF
  unsigned __int64 *v76; // [rsp+60h] [rbp-88h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-80h] BYREF
  HSTRING string; // [rsp+80h] [rbp-68h] BYREF
  __int128 v79; // [rsp+88h] [rbp-60h] BYREF
  __m128i si128; // [rsp+98h] [rbp-50h]

  v73 = 0;
  v70 = 0;
  v72 = 0;
  v71 = 0;
  v74 = 0;
  v79 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v79) = 0;
  ActivationFactory = MdmHttpWrapper::RegistrationTriggerToString(a1, &v79);
  if ( ActivationFactory >= 0 )
  {
    v76 = a4 + 2;
    a4[2] = 0;
    if ( a4[3] <= 7u )
      v10 = a4;
    else
      v10 = (_WORD *)*a4;
    *v10 = 0;
    string = 0;
    v11 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
    if ( v11 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
      __debugbreak();
    }
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(string, &v70);
    if ( ActivationFactory >= 0 )
    {
      string = 0;
      v16 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v16 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
        __debugbreak();
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v74);
      if ( ActivationFactory >= 0 )
      {
        v21 = v74;
        v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v74 + 80LL);
        v23 = v71;
        if ( v71 )
        {
          v71 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = &v79;
        if ( si128.m128i_i64[1] > 7uLL )
          v24 = (__int128 *)v79;
        v75 = v24;
        v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v75);
        ActivationFactory = v22(v21, *(_QWORD *)(v25 + 24), &v71);
        if ( ActivationFactory >= 0 )
        {
          v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v70;
          v29 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v70;
          v30 = v71;
          string = 0;
          v31 = WindowsCreateStringReference(L"RegistrationTrigger", 0x13u, &hstringHeader, &string);
          if ( v31 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
            __debugbreak();
          }
          ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v29)[7](v28, string, v30);
          if ( ActivationFactory >= 0 )
          {
            if ( !a2 )
              goto LABEL_76;
            v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v70;
            v37 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v70;
            string = 0;
            v38 = WindowsCreateStringReference(L"DeviceInfo", 0xAu, &hstringHeader, &string);
            if ( v38 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
              __debugbreak();
            }
            ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v37)[7](v36, string, a2);
            if ( ActivationFactory < 0 )
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v42,
                  v41,
                  ActivationFactory,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                  117,
                  "CHR(pJsonObject->SetNamedValue(HStringReference(L\"DeviceInfo\").Get(), pDeviceInfo))");
            }
            else
            {
LABEL_76:
              if ( !a3 )
                goto LABEL_36;
              v43 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v70;
              v44 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v70;
              string = 0;
              v45 = WindowsCreateStringReference(L"UserInfo", 8u, &hstringHeader, &string);
              if ( v45 < 0 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v45, v46, v47);
                JUMPOUT(0x18000F3AFLL);
              }
              ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v44)[7](v43, string, a3);
              if ( ActivationFactory < 0 )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v49,
                    v48,
                    ActivationFactory,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    122,
                    "CHR(pJsonObject->SetNamedValue(HStringReference(L\"UserInfo\").Get(), pUserInfo))");
              }
              else
              {
LABEL_36:
                v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v70;
                v51 = **v70;
                v52 = v72;
                if ( v72 )
                {
                  v72 = 0;
                  (*(void (__fastcall **)(_QWORD *, _QWORD))(*v52 + 16LL))(v52, *v52);
                }
                ActivationFactory = v51(v50, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v72);
                if ( ActivationFactory >= 0 )
                {
                  v55 = v72;
                  v56 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v72 + 56LL);
                  WindowsDeleteString(v73);
                  v73 = 0;
                  ActivationFactory = v56(v55, &v73);
                  if ( ActivationFactory >= 0 )
                  {
                    StringRawBuffer = WindowsGetStringRawBuffer(v73, 0);
                    v61 = -1;
                    do
                      ++v61;
                    while ( StringRawBuffer[v61] );
                    if ( v61 > a4[3] )
                    {
                      try
                      {
                        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                          a4,
                          v61,
                          v60,
                          StringRawBuffer);
                      }
                      catch ( std::bad_alloc )
                      {
                        LODWORD(v75) = -2147024882;
                        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                          McTemplateU0dsqs_EventWriteTransfer(
                            v63,
                            (unsigned int)&v69,
                            -2147024882,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                            134,
                            "CHR(((HRESULT)0x8007000EL))");
                        ActivationFactory = (int)v75;
                      }
                    }
                    else
                    {
                      if ( a4[3] > 7u )
                        a4 = (_QWORD *)*a4;
                      *v76 = v61;
                      v62 = 2 * v61;
                      memmove_0(a4, StringRawBuffer, 2 * v61);
                      *(_WORD *)((char *)a4 + v62) = 0;
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v58,
                      v57,
                      ActivationFactory,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                      126,
                      "CHR(pJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))");
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v54,
                    v53,
                    ActivationFactory,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    125,
                    "CHR(pJsonObject.As(&pJsonObjectAsValue))");
                }
              }
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v35,
              v34,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
              113,
              "CHR(pJsonObject->SetNamedValue(HStringReference(L\"RegistrationTrigger\").Get(), pJsonValue.Get()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v27,
            v26,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            112,
            "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrTrigger.c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v20,
          v19,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          110,
          "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v15,
        v14,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
        109,
        "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v8,
      v7,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      105,
      "CHR(RegistrationTriggerToString(eTrigger, wstrTrigger))");
  }
  std::wstring::~wstring(&v79);
  v64 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  }
  v65 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  }
  v66 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v66 + 16LL))(v66);
  }
  v67 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v70;
  if ( v70 )
  {
    v70 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v67)[2])(v67);
  }
  WindowsDeleteString(v73);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000edc0  mov     r11, rsp
0x18000edc3  push    rbx
0x18000edc4  push    rsi
0x18000edc5  push    rdi
0x18000edc6  push    r12
0x18000edc8  push    r13
0x18000edca  push    r14
0x18000edcc  push    r15
0x18000edce  sub     rsp, 0B0h
0x18000edd5  mov     rax, cs:__security_cookie
0x18000eddc  xor     rax, rsp
0x18000eddf  mov     [rsp+0E8h+var_40], rax
0x18000ede7  mov     r14, r9
0x18000edea  mov     r13, r8
0x18000eded  mov     r12, rdx
0x18000edf0  xor     esi, esi
0x18000edf2  mov     [rsp+0E8h+var_A0], rsi
0x18000edf7  mov     [rsp+0E8h+var_B8], rsi
0x18000edfc  mov     [rsp+0E8h+var_A8], rsi
0x18000ee01  mov     [rsp+0E8h+var_B0], rsi
0x18000ee06  mov     [rsp+0E8h+var_98], rsi
0x18000ee0b  xorps   xmm0, xmm0
0x18000ee0e  movups  xmmword ptr [r11-60h], xmm0
0x18000ee13  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000ee1b  movdqu  xmmword ptr [r11-50h], xmm1
0x18000ee21  mov     [r11-60h], si
0x18000ee26  lea     rdx, [r11-60h]
0x18000ee2a  call    ?RegistrationTriggerToString@MdmHttpWrapper@@CAJW4MdmRegistrationTrigger@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpWrapper::RegistrationTriggerToString(MdmRegistrationTrigger,std::wstring &)
0x18000ee2f  mov     edi, eax
0x18000ee31  test    eax, eax
0x18000ee33  jns     short loc_18000EE6A
0x18000ee35  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ee3c  jz      loc_18000F2D3
0x18000ee42  lea     rax, aChrRegistratio; "CHR(RegistrationTriggerToString(eTrigge"...
0x18000ee49  mov     [rsp+0E8h+var_C0], rax
0x18000ee4e  mov     [rsp+0E8h+var_C8], 369h
0x18000ee56  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000ee5d  mov     r8d, edi
0x18000ee60  call    McTemplateU0dsqs_EventWriteTransfer
0x18000ee65  jmp     loc_18000F2D3
0x18000ee6a  lea     rax, [r14+10h]
0x18000ee6e  mov     [rsp+0E8h+var_88], rax
0x18000ee73  mov     [rax], rsi
0x18000ee76  cmp     qword ptr [r14+18h], 7
0x18000ee7b  jbe     short loc_18000EE82
0x18000ee7d  mov     rax, [r14]
0x18000ee80  jmp     short loc_18000EE85
0x18000ee82  mov     rax, r14
0x18000ee85  mov     [rax], si
0x18000ee88  mov     [rsp+0E8h+string], rsi
0x18000ee90  lea     r9, [rsp+0E8h+string]; string
0x18000ee98  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000ee9d  mov     edx, 1Ch; length
0x18000eea2  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000eea9  call    cs:__imp_WindowsCreateStringReference
0x18000eeb0  nop     dword ptr [rax+rax+00h]
0x18000eeb5  test    eax, eax
0x18000eeb7  js      loc_18000F388
0x18000eebd  lea     rdx, [rsp+0E8h+var_B8]
0x18000eec2  mov     rcx, [rsp+0E8h+string]
0x18000eeca  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18000eecf  mov     edi, eax
0x18000eed1  test    eax, eax
0x18000eed3  jns     short loc_18000EEFB
0x18000eed5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000eedc  jz      loc_18000F2D3
0x18000eee2  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18000eee9  mov     [rsp+0E8h+var_C0], rax
0x18000eeee  mov     [rsp+0E8h+var_C8], 36Dh
0x18000eef6  jmp     loc_18000EE56
0x18000eefb  mov     [rsp+0E8h+string], rsi
0x18000ef03  lea     r9, [rsp+0E8h+string]; string
0x18000ef0b  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000ef10  mov     edx, 1Bh; length
0x18000ef15  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18000ef1c  call    cs:__imp_WindowsCreateStringReference
0x18000ef23  nop     dword ptr [rax+rax+00h]
0x18000ef28  test    eax, eax
0x18000ef2a  js      loc_18000F390
0x18000ef30  lea     r8, [rsp+0E8h+var_98]
0x18000ef35  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000ef3c  mov     rcx, [rsp+0E8h+string]
0x18000ef44  call    cs:__imp_RoGetActivationFactory
0x18000ef4b  nop     dword ptr [rax+rax+00h]
0x18000ef50  mov     edi, eax
0x18000ef52  test    eax, eax
0x18000ef54  jns     short loc_18000EF7C
0x18000ef56  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ef5d  jz      loc_18000F2D3
0x18000ef63  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x18000ef6a  mov     [rsp+0E8h+var_C0], rax
0x18000ef6f  mov     [rsp+0E8h+var_C8], 36Eh
0x18000ef77  jmp     loc_18000EE56
0x18000ef7c  mov     rbx, [rsp+0E8h+var_98]
0x18000ef81  mov     rax, [rbx]
0x18000ef84  mov     rdi, [rax+50h]
0x18000ef88  mov     rcx, [rsp+0E8h+var_B0]
0x18000ef8d  test    rcx, rcx
0x18000ef90  jz      short loc_18000EFA4
0x18000ef92  mov     [rsp+0E8h+var_B0], rsi
0x18000ef97  mov     rax, [rcx]
0x18000ef9a  mov     rax, [rax+10h]
0x18000ef9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efa3  nop
0x18000efa4  lea     rdx, [rsp+0E8h+var_60]
0x18000efac  cmp     [rsp+0E8h+var_48], 7
0x18000efb5  cmova   rdx, qword ptr [rsp+0E8h+var_60]
0x18000efbe  mov     [rsp+0E8h+var_90], rdx
0x18000efc3  lea     rdx, [rsp+0E8h+var_90]
0x18000efc8  lea     rcx, [rsp+0E8h+hstringHeader]
0x18000efcd  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000efd2  nop
0x18000efd3  lea     r8, [rsp+0E8h+var_B0]
0x18000efd8  mov     rdx, [rax+18h]
0x18000efdc  mov     rcx, rbx
0x18000efdf  mov     rax, rdi
0x18000efe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efe7  mov     edi, eax
0x18000efe9  test    eax, eax
0x18000efeb  jns     short loc_18000F013
0x18000efed  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000eff4  jz      loc_18000F2D3
0x18000effa  lea     rax, aChrPjsonvalues_11; "CHR(pJsonValueStatics->CreateStringValu"...
0x18000f001  mov     [rsp+0E8h+var_C0], rax
0x18000f006  mov     [rsp+0E8h+var_C8], 370h
0x18000f00e  jmp     loc_18000EE56
0x18000f013  mov     rbx, [rsp+0E8h+var_B8]
0x18000f018  mov     rdi, [rbx]
0x18000f01b  mov     r15, [rsp+0E8h+var_B0]
0x18000f020  mov     [rsp+0E8h+string], rsi
0x18000f028  lea     r9, [rsp+0E8h+string]; string
0x18000f030  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000f035  mov     edx, 13h; length
0x18000f03a  lea     rcx, aRegistrationtr; "RegistrationTrigger"
0x18000f041  call    cs:__imp_WindowsCreateStringReference
0x18000f048  nop     dword ptr [rax+rax+00h]
0x18000f04d  test    eax, eax
0x18000f04f  js      loc_18000F398
0x18000f055  mov     r8, r15
0x18000f058  mov     rdx, [rsp+0E8h+string]
0x18000f060  mov     rcx, rbx
0x18000f063  mov     rax, [rdi+38h]
0x18000f067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f06c  mov     edi, eax
0x18000f06e  test    eax, eax
0x18000f070  jns     short loc_18000F098
0x18000f072  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000f079  jz      loc_18000F2D3
0x18000f07f  lea     rax, aChrPjsonobject_23; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000f086  mov     [rsp+0E8h+var_C0], rax
0x18000f08b  mov     [rsp+0E8h+var_C8], 371h
0x18000f093  jmp     loc_18000EE56
0x18000f098  test    r12, r12
0x18000f09b  jz      loc_18000F121
0x18000f0a1  mov     rbx, [rsp+0E8h+var_B8]
0x18000f0a6  mov     rdi, [rbx]
0x18000f0a9  mov     [rsp+0E8h+string], rsi
0x18000f0b1  lea     r9, [rsp+0E8h+string]; string
0x18000f0b9  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000f0be  mov     edx, 0Ah; length
0x18000f0c3  lea     rcx, aDeviceinfo; "DeviceInfo"
0x18000f0ca  call    cs:__imp_WindowsCreateStringReference
0x18000f0d1  nop     dword ptr [rax+rax+00h]
0x18000f0d6  test    eax, eax
0x18000f0d8  js      loc_18000F3A0
0x18000f0de  mov     r8, r12
0x18000f0e1  mov     rdx, [rsp+0E8h+string]
0x18000f0e9  mov     rcx, rbx
0x18000f0ec  mov     rax, [rdi+38h]
0x18000f0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0f5  mov     edi, eax
0x18000f0f7  test    eax, eax
0x18000f0f9  jns     short loc_18000F121
0x18000f0fb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000f102  jz      loc_18000F2D3
0x18000f108  lea     rax, aChrPjsonobject_34; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000f10f  mov     [rsp+0E8h+var_C0], rax
0x18000f114  mov     [rsp+0E8h+var_C8], 375h
0x18000f11c  jmp     loc_18000EE56
0x18000f121  test    r13, r13
0x18000f124  jz      loc_18000F1AA
0x18000f12a  mov     rbx, [rsp+0E8h+var_B8]
0x18000f12f  mov     rdi, [rbx]
0x18000f132  mov     [rsp+0E8h+string], rsi
0x18000f13a  lea     r9, [rsp+0E8h+string]; string
0x18000f142  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18000f147  mov     edx, 8; length
0x18000f14c  lea     rcx, aUserinfo; "UserInfo"
0x18000f153  call    cs:__imp_WindowsCreateStringReference
0x18000f15a  nop     dword ptr [rax+rax+00h]
0x18000f15f  test    eax, eax
0x18000f161  js      loc_18000F3A8
0x18000f167  mov     r8, r13
0x18000f16a  mov     rdx, [rsp+0E8h+string]
0x18000f172  mov     rcx, rbx
0x18000f175  mov     rax, [rdi+38h]
0x18000f179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f17e  mov     edi, eax
0x18000f180  test    eax, eax
0x18000f182  jns     short loc_18000F1AA
0x18000f184  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000f18b  jz      loc_18000F2D3
0x18000f191  lea     rax, aChrPjsonobject_29; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000f198  mov     [rsp+0E8h+var_C0], rax
0x18000f19d  mov     [rsp+0E8h+var_C8], 37Ah
0x18000f1a5  jmp     loc_18000EE56
0x18000f1aa  mov     rbx, [rsp+0E8h+var_B8]
0x18000f1af  mov     rax, [rbx]
0x18000f1b2  mov     rdi, [rax]
0x18000f1b5  mov     rcx, [rsp+0E8h+var_A8]
0x18000f1ba  test    rcx, rcx
0x18000f1bd  jz      short loc_18000F1D1
0x18000f1bf  mov     [rsp+0E8h+var_A8], rsi
0x18000f1c4  mov     rdx, [rcx]
0x18000f1c7  mov     rax, [rdx+10h]
0x18000f1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1d0  nop
0x18000f1d1  lea     r8, [rsp+0E8h+var_A8]
0x18000f1d6  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18000f1dd  mov     rcx, rbx
0x18000f1e0  mov     rax, rdi
0x18000f1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1e8  mov     edi, eax
0x18000f1ea  test    eax, eax
0x18000f1ec  jns     short loc_18000F214
0x18000f1ee  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000f1f5  jz      loc_18000F2D3
0x18000f1fb  lea     rax, aChrPjsonobject_3; "CHR(pJsonObject.As(&pJsonObjectAsValue)"...
0x18000f202  mov     [rsp+0E8h+var_C0], rax
0x18000f207  mov     [rsp+0E8h+var_C8], 37Dh
0x18000f20f  jmp     loc_18000EE56
0x18000f214  mov     rdi, [rsp+0E8h+var_A8]
0x18000f219  mov     rax, [rdi]
0x18000f21c  mov     rbx, [rax+38h]
0x18000f220  mov     rcx, [rsp+0E8h+var_A0]; string
0x18000f225  call    cs:__imp_WindowsDeleteString
0x18000f22c  nop     dword ptr [rax+rax+00h]
0x18000f231  mov     [rsp+0E8h+var_A0], rsi
0x18000f236  lea     rdx, [rsp+0E8h+var_A0]
0x18000f23b  mov     rcx, rdi
0x18000f23e  mov     rax, rbx
0x18000f241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f246  mov     edi, eax
0x18000f248  test    eax, eax
0x18000f24a  jns     short loc_18000F26E
0x18000f24c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000f253  jz      short loc_18000F2D3
0x18000f255  lea     rax, aChrPjsonobject_33; "CHR(pJsonObjectAsValue->Stringify(hstrB"...
0x18000f25c  mov     [rsp+0E8h+var_C0], rax
0x18000f261  mov     [rsp+0E8h+var_C8], 37Eh
0x18000f269  jmp     loc_18000EE56
0x18000f26e  xor     edx, edx; length
0x18000f270  mov     rcx, [rsp+0E8h+var_A0]; string
0x18000f275  call    cs:__imp_WindowsGetStringRawBuffer
0x18000f27c  nop     dword ptr [rax+rax+00h]
0x18000f281  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000f285  inc     rdx
0x18000f288  cmp     [rax+rdx*2], si
0x18000f28c  jnz     short loc_18000F285
0x18000f28e  cmp     rdx, [r14+18h]
0x18000f292  ja      short loc_18000F2BF
0x18000f294  cmp     qword ptr [r14+18h], 7
0x18000f299  jbe     short loc_18000F29E
0x18000f29b  mov     r14, [r14]
0x18000f29e  mov     rcx, [rsp+0E8h+var_88]
0x18000f2a3  mov     [rcx], rdx
0x18000f2a6  lea     rbx, [rdx+rdx]
0x18000f2aa  mov     r8, rbx; Size
0x18000f2ad  mov     rdx, rax; Src
0x18000f2b0  mov     rcx, r14; void *
0x18000f2b3  call    memmove_0
0x18000f2b8  mov     [rbx+r14], si
0x18000f2bd  jmp     short loc_18000F2CB
0x18000f2bf  mov     r9, rax
0x18000f2c2  mov     rcx, r14
0x18000f2c5  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000f2ca  nop
0x18000f2cb  jmp     short loc_18000F2D3
0x18000f2cd  xor     esi, esi
0x18000f2cf  mov     edi, dword ptr [rsp+0E8h+var_90]
0x18000f2d3  lea     rcx, [rsp+0E8h+var_60]
0x18000f2db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f2e0  nop
0x18000f2e1  mov     rcx, [rsp+0E8h+var_98]
0x18000f2e6  test    rcx, rcx
0x18000f2e9  jz      short loc_18000F2FD
0x18000f2eb  mov     [rsp+0E8h+var_98], rsi
0x18000f2f0  mov     rax, [rcx]
0x18000f2f3  mov     rax, [rax+10h]
0x18000f2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2fc  nop
0x18000f2fd  mov     rcx, [rsp+0E8h+var_B0]
0x18000f302  test    rcx, rcx
0x18000f305  jz      short loc_18000F319
0x18000f307  mov     [rsp+0E8h+var_B0], rsi
0x18000f30c  mov     rax, [rcx]
0x18000f30f  mov     rax, [rax+10h]
0x18000f313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f318  nop
0x18000f319  mov     rcx, [rsp+0E8h+var_A8]
  ... truncated ...
```
