# Windows::Internal::Flighting::AttributeStateDetection::EmitCriticalStateTelemetryPayload(std::vector<Windows::Internal::Flighting::AttributeStateDetection::AttributeEvent,std::allocator<Windows::Internal::Flighting::AttributeStateDetection::AttributeEvent>> const &)

- ea: `0x180043f60`
- end: `0x180044372`
- name: `?EmitCriticalStateTelemetryPayload@AttributeStateDetection@Flighting@Internal@Windows@@AEAAJAEBV?$vector@UAttributeEvent@AttributeStateDetection@Flighting@Internal@Windows@@V?$allocator@UAttributeEvent@AttributeStateDetection@Flighting@Internal@Windows@@@std@@@std@@@Z`
- size: `1042`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044378`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x18001146c`
- `0x180023fa8`
- `0x1800325f4`
- `0x1800327ac`
- `0x1800327e4`
- `0x1800328bc`
- `0x18003290c`
- `0x1800334f0`
- `0x180037194`
- `0x180042a28`
- `0x180043768`
- `0x18004391c`
- `0x180043f60`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004429a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800442d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004429a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800442d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800442ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800442ea`

## string_xrefs

- `0x180043ffe`: `Windows.Data.Json.JsonArray`
- `0x18004409f`: `Windows.Data.Json.JsonObject`
- `0x180043fad`: `Windows.Data.Json.JsonValue`
- `0x180043fd6`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x180044028`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x180044065`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x1800441ea`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x180044215`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x18004425b`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x1800442c0`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Flighting::AttributeStateDetection::EmitCriticalStateTelemetryPayload(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // rdx
  int v12; // edi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64); // [rsp+20h] [rbp-69h] BYREF
  __int64 v29; // [rsp+28h] [rbp-61h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-59h] BYREF
  HSTRING string; // [rsp+38h] [rbp-51h] BYREF
  __int64 v32; // [rsp+40h] [rbp-49h] BYREF
  __int64 v33; // [rsp+48h] [rbp-41h] BYREF
  __int64 v34; // [rsp+50h] [rbp-39h] BYREF
  int v35; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v36[2]; // [rsp+60h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-19h] BYREF
  __int64 v38; // [rsp+88h] [rbp-1h]
  HSTRING_HEADER v39; // [rsp+90h] [rbp+7h] BYREF
  __int64 v40; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( !*(_BYTE *)(a1 + 276) || *a2 == a2[1] )
    return 0;
  v34 = 0;
  v4 = (__int64 *)Windows::Internal::StringReference::StringReference((HSTRING *)&v39, L"Windows.Data.Json.JsonValue");
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(
         *v4,
         (__int64)&v34);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37A,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
      (const char *)(unsigned int)v5,
      (int)v28);
    goto LABEL_37;
  }
  v28 = 0;
  v38 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonArray",
    0x1Cu,
    0x1Bu);
  v7 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(v38, &v28);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37D,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
      (const char *)(unsigned int)v7,
      (int)v28);
LABEL_7:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    goto LABEL_37;
  }
  v29 = 0;
  v8 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
         &v28,
         (__int64)&v29);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x380,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
      (const char *)(unsigned int)v8,
      (int)v28);
LABEL_10:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
    goto LABEL_7;
  }
  v9 = *a2;
  v10 = a2[1];
  while ( 1 )
  {
    if ( v9 == v10 )
    {
      v33 = 0;
      v21 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
              &v28,
              (__int64)&v33);
      v6 = v21;
      if ( v21 >= 0 )
      {
        string = 0;
        v24 = v33;
        v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 56LL);
        WindowsDeleteString(0);
        string = 0;
        v26 = v25(v24, &string);
        v6 = v26;
        if ( v26 >= 0 )
        {
          v36[0] = WindowsGetStringRawBuffer(string, 0);
          v35 = 0;
          hstringHeader.Reserved.Reserved1 = *(PVOID *)(a1 + 192);
          CtacTelemetry::AttributeState<unsigned short const *,long,unsigned short const *>(&hstringHeader, &v35, v36);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
          v6 = 0;
          goto LABEL_37;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A5,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
          (const char *)(unsigned int)v26,
          (int)v28);
        WindowsDeleteString(string);
        string = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A2,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
          (const char *)(unsigned int)v21,
          (int)v28);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      goto LABEL_10;
    }
    v30 = 0;
    v40 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v39, L"Windows.Data.Json.JsonObject", 0x1Du, 0x1Cu);
    v12 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v40, &v30);
    if ( v12 < 0 )
    {
      v23 = 901;
      goto LABEL_32;
    }
    hstringHeader.Reserved.Reserved1 = &v34;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v30;
    v36[0] = &v34;
    v36[1] = &v30;
    v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9, v11, v13, v14);
    v12 = lambda_0691d63f03be4057b93de2a10c098f19_::operator()(&hstringHeader, L"AttributeName", v15);
    if ( v12 < 0 )
    {
      v23 = 919;
      goto LABEL_32;
    }
    v16 = CTAC::Telemetry::EventTypeToString(*(unsigned int *)(v9 + 32));
    v12 = lambda_0691d63f03be4057b93de2a10c098f19_::operator()(&hstringHeader, L"EventType", v16);
    if ( v12 < 0 )
    {
      v23 = 920;
      goto LABEL_32;
    }
    v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9 + 40, v17, v18, v19);
    v12 = lambda_0691d63f03be4057b93de2a10c098f19_::operator()(&hstringHeader, L"Provider", v20);
    if ( v12 < 0 )
    {
      v23 = 921;
      goto LABEL_32;
    }
    v12 = lambda_af31fa38806b49adbee2e6cbaf6f1e62_::operator()(v36);
    if ( v12 < 0 )
    {
      v23 = 922;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
        (const char *)(unsigned int)v12,
        (int)v28);
      goto LABEL_33;
    }
    v32 = 0;
    v12 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v30,
            (__int64)&v32);
    if ( v12 < 0 )
      break;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 104LL))(v29, v32);
    if ( v12 < 0 )
    {
      v22 = 926;
      goto LABEL_26;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
    v9 += 88;
  }
  v22 = 925;
LABEL_26:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v22,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
    (const char *)(unsigned int)v12,
    (int)v28);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
LABEL_33:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
  v6 = v12;
LABEL_37:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  return v6;
}

```

## disassembly

```asm
0x180043f60  mov     [rsp-8+arg_10], rbx
0x180043f65  push    rbp
0x180043f66  push    rsi
0x180043f67  push    rdi
0x180043f68  push    r14
0x180043f6a  push    r15
0x180043f6c  lea     rbp, [rsp-37h]
0x180043f71  sub     rsp, 0C0h
0x180043f78  mov     rax, cs:__security_cookie
0x180043f7f  xor     rax, rsp
0x180043f82  mov     [rbp+57h+var_30], rax
0x180043f86  mov     rdi, rdx
0x180043f89  mov     r14, rcx
0x180043f8c  xor     r15d, r15d
0x180043f8f  cmp     [rcx+114h], r15b
0x180043f96  jz      loc_18004434D
0x180043f9c  mov     rax, [rdx+8]
0x180043fa0  cmp     [rdx], rax
0x180043fa3  jz      loc_18004434D
0x180043fa9  mov     [rbp+57h+var_90], r15
0x180043fad  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180043fb4  lea     rcx, [rbp+57h+var_50]; string
0x180043fb8  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x180043fbd  lea     rdx, [rbp+57h+var_90]
0x180043fc1  mov     rcx, [rax]
0x180043fc4  call    ??$GetActivationFactory@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>)
0x180043fc9  mov     ebx, eax
0x180043fcb  test    eax, eax
0x180043fcd  jns     short loc_180043FEC
0x180043fcf  mov     rcx, [rbp+5Fh]; this
0x180043fd3  mov     r9d, eax; char *
0x180043fd6  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180043fdd  mov     edx, 37Ah; void *
0x180043fe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043fe7  jmp     loc_180044340
0x180043fec  mov     [rbp+57h+var_C0], r15
0x180043ff0  mov     [rbp+57h+var_58], r15
0x180043ff4  mov     r9d, 1Bh; unsigned int
0x180043ffa  lea     r8d, [r9+1]; unsigned int
0x180043ffe  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x180044005  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180044009  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004400e  lea     rdx, [rbp+57h+var_C0]
0x180044012  mov     rcx, [rbp+57h+var_58]
0x180044016  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x18004401b  mov     ebx, eax
0x18004401d  test    eax, eax
0x18004401f  jns     short loc_180044047
0x180044021  mov     rcx, [rbp+5Fh]; this
0x180044025  mov     r9d, eax; char *
0x180044028  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x18004402f  mov     edx, 37Dh; void *
0x180044034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044039  lea     rcx, [rbp+57h+var_C0]
0x18004403d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180044042  jmp     loc_180044340
0x180044047  mov     [rbp+57h+var_B8], r15
0x18004404b  lea     rdx, [rbp+57h+var_B8]
0x18004404f  lea     rcx, [rbp+57h+var_C0]
0x180044053  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180044058  mov     ebx, eax
0x18004405a  test    eax, eax
0x18004405c  jns     short loc_180044081
0x18004405e  mov     rcx, [rbp+5Fh]; this
0x180044062  mov     r9d, eax; char *
0x180044065  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x18004406c  mov     edx, 380h; void *
0x180044071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044076  lea     rcx, [rbp+57h+var_B8]
0x18004407a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004407f  jmp     short loc_180044039
0x180044081  mov     rbx, [rdi]
0x180044084  mov     rsi, [rdi+8]
0x180044088  jmp     loc_1800441BF
0x18004408d  mov     [rbp+57h+var_B0], r15
0x180044091  mov     [rbp+57h+var_38], r15
0x180044095  mov     r9d, 1Ch; unsigned int
0x18004409b  lea     r8d, [r9+1]; unsigned int
0x18004409f  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800440a6  lea     rcx, [rbp+57h+var_50]; hstringHeader
0x1800440aa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800440af  lea     rdx, [rbp+57h+var_B0]
0x1800440b3  mov     rcx, [rbp+57h+var_38]
0x1800440b7  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800440bc  mov     edi, eax
0x1800440be  test    eax, eax
0x1800440c0  js      loc_18004424F
0x1800440c6  lea     rax, [rbp+57h+var_90]
0x1800440ca  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800440ce  lea     rax, [rbp+57h+var_B0]
0x1800440d2  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x1800440d6  lea     rax, [rbp+57h+var_90]
0x1800440da  mov     [rbp+57h+var_80], rax
0x1800440de  lea     rax, [rbp+57h+var_B0]
0x1800440e2  mov     [rbp+57h+var_78], rax
0x1800440e6  mov     rcx, rbx
0x1800440e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800440ee  mov     r8, rax
0x1800440f1  lea     rdx, aAttributename; "AttributeName"
0x1800440f8  lea     rcx, [rbp+57h+hstringHeader]
0x1800440fc  call    _lambda_0691d63f03be4057b93de2a10c098f19___operator__
0x180044101  mov     edi, eax
0x180044103  test    eax, eax
0x180044105  js      loc_180044248
0x18004410b  mov     ecx, [rbx+20h]
0x18004410e  call    ?EventTypeToString@Telemetry@CTAC@@YAPEBGW4AttributeEventType@12@@Z; CTAC::Telemetry::EventTypeToString(CTAC::Telemetry::AttributeEventType)
0x180044113  mov     r8, rax
0x180044116  lea     rdx, aEventtype; "EventType"
0x18004411d  lea     rcx, [rbp+57h+hstringHeader]
0x180044121  call    _lambda_0691d63f03be4057b93de2a10c098f19___operator__
0x180044126  mov     edi, eax
0x180044128  test    eax, eax
0x18004412a  js      loc_180044241
0x180044130  lea     rcx, [rbx+28h]
0x180044134  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044139  mov     r8, rax
0x18004413c  lea     rdx, aProvider; "Provider"
0x180044143  lea     rcx, [rbp+57h+hstringHeader]
0x180044147  call    _lambda_0691d63f03be4057b93de2a10c098f19___operator__
0x18004414c  mov     edi, eax
0x18004414e  test    eax, eax
0x180044150  js      loc_18004423A
0x180044156  mov     eax, [rbx+50h]
0x180044159  xorps   xmm2, xmm2
0x18004415c  cvtsi2sd xmm2, rax
0x180044161  lea     rcx, [rbp+57h+var_80]
0x180044165  call    _lambda_af31fa38806b49adbee2e6cbaf6f1e62___operator__
0x18004416a  mov     edi, eax
0x18004416c  test    eax, eax
0x18004416e  js      loc_180044233
0x180044174  mov     [rbp+57h+var_A0], r15
0x180044178  lea     rdx, [rbp+57h+var_A0]
0x18004417c  lea     rcx, [rbp+57h+var_B0]
0x180044180  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180044185  mov     edi, eax
0x180044187  test    eax, eax
0x180044189  js      loc_180044210
0x18004418f  mov     rcx, [rbp+57h+var_B8]
0x180044193  mov     rax, [rcx]
0x180044196  mov     rdx, [rbp+57h+var_A0]
0x18004419a  mov     rax, [rax+68h]
0x18004419e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441a3  mov     edi, eax
0x1800441a5  test    eax, eax
0x1800441a7  js      short loc_180044209
0x1800441a9  lea     rcx, [rbp+57h+var_A0]
0x1800441ad  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800441b2  lea     rcx, [rbp+57h+var_B0]
0x1800441b6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800441bb  add     rbx, 58h ; 'X'
0x1800441bf  cmp     rbx, rsi
0x1800441c2  jnz     loc_18004408D
0x1800441c8  mov     [rbp+57h+var_98], r15
0x1800441cc  lea     rdx, [rbp+57h+var_98]
0x1800441d0  lea     rcx, [rbp+57h+var_C0]
0x1800441d4  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800441d9  mov     ebx, eax
0x1800441db  test    eax, eax
0x1800441dd  jns     loc_180044289
0x1800441e3  mov     rcx, [rbp+5Fh]; this
0x1800441e7  mov     r9d, eax; char *
0x1800441ea  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x1800441f1  mov     edx, 3A2h; void *
0x1800441f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800441fb  lea     rcx, [rbp+57h+var_98]
0x1800441ff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180044204  jmp     loc_180044076
0x180044209  mov     edx, 39Eh
0x18004420e  jmp     short loc_180044215
0x180044210  mov     edx, 39Dh; void *
0x180044215  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x18004421c  mov     r9d, edi; char *
0x18004421f  mov     rcx, [rbp+5Fh]; this
0x180044223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044228  lea     rcx, [rbp+57h+var_A0]
0x18004422c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180044231  jmp     short loc_180044267
0x180044233  mov     edx, 39Ah
0x180044238  jmp     short loc_180044254
0x18004423a  mov     edx, 399h
0x18004423f  jmp     short loc_180044254
0x180044241  mov     edx, 398h
0x180044246  jmp     short loc_180044254
0x180044248  mov     edx, 397h
0x18004424d  jmp     short loc_180044254
0x18004424f  mov     edx, 385h; void *
0x180044254  mov     rcx, [rbp+5Fh]; this
0x180044258  mov     r9d, edi; char *
0x18004425b  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180044262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044267  lea     rcx, [rbp+57h+var_B0]
0x18004426b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180044270  lea     rcx, [rbp+57h+var_B8]
0x180044274  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180044279  lea     rcx, [rbp+57h+var_C0]
0x18004427d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180044282  mov     ebx, edi
0x180044284  jmp     loc_180044340
0x180044289  mov     [rbp+57h+string], r15
0x18004428d  mov     rdi, [rbp+57h+var_98]
0x180044291  mov     rax, [rdi]
0x180044294  mov     rbx, [rax+38h]
0x180044298  xor     ecx, ecx; string
0x18004429a  call    cs:__imp_WindowsDeleteString
0x1800442a0  mov     [rbp+57h+string], r15
0x1800442a4  lea     rdx, [rbp+57h+string]
0x1800442a8  mov     rcx, rdi
0x1800442ab  mov     rax, rbx
0x1800442ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442b3  mov     ebx, eax
0x1800442b5  test    eax, eax
0x1800442b7  jns     short loc_1800442E4
0x1800442b9  mov     rcx, [rbp+5Fh]; this
0x1800442bd  mov     r9d, eax; char *
0x1800442c0  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x1800442c7  mov     edx, 3A5h; void *
0x1800442cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442d1  mov     rcx, [rbp+57h+string]; string
0x1800442d5  call    cs:__imp_WindowsDeleteString
0x1800442db  mov     [rbp+57h+string], r15
0x1800442df  jmp     loc_1800441FB
0x1800442e4  xor     edx, edx; length
0x1800442e6  mov     rcx, [rbp+57h+string]; string
0x1800442ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800442f0  mov     [rbp+57h+var_80], rax
0x1800442f4  mov     [rbp+57h+var_88], r15d
0x1800442f8  mov     rax, [r14+0C0h]
0x1800442ff  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180044303  lea     r8, [rbp+57h+var_80]
0x180044307  lea     rdx, [rbp+57h+var_88]
0x18004430b  lea     rcx, [rbp+57h+hstringHeader]
0x18004430f  call    ??$AttributeState@PEBGJPEBG@CtacTelemetry@@SAX$$QEAPEBG$$QEAJ0@Z; CtacTelemetry::AttributeState<ushort const *,long,ushort const *>(ushort const * &&,long &&,ushort const * &&)
0x180044314  mov     rcx, [rbp+57h+string]; string
0x180044318  call    cs:__imp_WindowsDeleteString
0x18004431e  mov     [rbp+57h+string], r15
0x180044322  lea     rcx, [rbp+57h+var_98]
0x180044326  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004432b  lea     rcx, [rbp+57h+var_B8]
0x18004432f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180044334  lea     rcx, [rbp+57h+var_C0]
0x180044338  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004433d  mov     ebx, r15d
0x180044340  lea     rcx, [rbp+57h+var_90]
0x180044344  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180044349  mov     eax, ebx
0x18004434b  jmp     short loc_18004434F
0x18004434d  xor     eax, eax
0x18004434f  mov     rcx, [rbp+57h+var_30]
0x180044353  xor     rcx, rsp; StackCookie
0x180044356  call    __security_check_cookie
0x18004435b  mov     rbx, [rsp+0E0h+arg_10]
0x180044363  add     rsp, 0C0h
0x18004436a  pop     r15
0x18004436c  pop     r14
0x18004436e  pop     rdi
0x18004436f  pop     rsi
0x180044370  pop     rbp
0x180044371  retn
```
