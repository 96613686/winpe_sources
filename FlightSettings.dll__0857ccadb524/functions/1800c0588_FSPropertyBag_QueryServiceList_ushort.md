# FSPropertyBag::QueryServiceList(ushort * *)

- ea: `0x1800c0588`
- end: `0x1800c0a4d`
- name: `?QueryServiceList@FSPropertyBag@@AEAAJPEAPEAG@Z`
- size: `1221`
- prototype: `__int64 __fastcall(FSPropertyBag *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ba770`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001c6f4`
- `0x18001ec78`
- `0x1800325f4`
- `0x180032640`
- `0x1800327ac`
- `0x1800327e4`
- `0x1800328bc`
- `0x18003290c`
- `0x1800334f0`
- `0x180085a24`
- `0x18008fbd8`
- `0x1800bf3ec`
- `0x1800c0588`
- `0x1800c0bf0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c07a1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c0801`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c07a1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c0801`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c08f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c08f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c0906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c0906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c098a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c098a`

## string_xrefs

- `0x1800c0637`: `Windows.Data.Json.JsonArray`
- `0x1800c06b2`: `Windows.Data.Json.JsonValue`
- `0x1800c0604`: `serviceInfo`
- `0x1800c05ee`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c0661`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c0698`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c06db`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c0778`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c081a`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c085d`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c0897`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c094c`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c09b8`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800c071a`: `QueryServiceList`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall FSPropertyBag::QueryServiceList(FSPropertyBag *this, unsigned __int16 **a2)
{
  __int64 v4; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  unsigned __int16 *v7; // rax
  __int64 *v8; // rax
  int v9; // eax
  int v10; // eax
  __int64 *v11; // rax
  int v12; // eax
  int FlightingRegString; // eax
  wchar_t *v14; // rbx
  int v15; // eax
  __int64 v16; // rdx
  struct Windows::Data::Json::IJsonValue **v17; // rcx
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  __int64 *v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64); // r12
  __int64 v25; // r15
  unsigned __int64 v26; // rcx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v34; // [rsp+20h] [rbp-99h]
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-89h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-81h] BYREF
  struct Windows::Data::Json::IJsonValueStatics *v37; // [rsp+40h] [rbp-79h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-71h] BYREF
  __int64 v39; // [rsp+50h] [rbp-69h] BYREF
  struct Windows::Data::Json::IJsonValue *v40; // [rsp+58h] [rbp-61h] BYREF
  UINT32 length; // [rsp+60h] [rbp-59h] BYREF
  __int64 v42; // [rsp+68h] [rbp-51h] BYREF
  wchar_t *String; // [rsp+70h] [rbp-49h] BYREF
  __int64 v44; // [rsp+78h] [rbp-41h]
  __int64 v45; // [rsp+80h] [rbp-39h]
  HSTRING v46; // [rsp+88h] [rbp-31h] BYREF
  wchar_t *Context; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int16 *v48; // [rsp+98h] [rbp-21h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-19h]
  __int64 v50; // [rsp+A8h] [rbp-11h]
  HSTRING string; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *a2 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v4 = -1;
  v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         &v48,
         &LocaleName,
         -1);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( !FSPropertyBag::ShouldIncludeProperty(this, L"serviceInfo") )
    {
      v7 = v48;
      v48 = 0;
      v50 = 0;
      v49 = 0;
      *a2 = v7;
      v6 = 0;
      goto LABEL_52;
    }
    v36 = 0;
    v8 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, L"Windows.Data.Json.JsonArray");
    v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(*v8, &v36);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x763,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v9,
        v34);
LABEL_51:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      goto LABEL_52;
    }
    v35 = 0;
    v10 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
            &v36,
            (__int64)&v35);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x765,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v10,
        v34);
LABEL_50:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
      goto LABEL_51;
    }
    v37 = 0;
    v11 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, L"Windows.Data.Json.JsonValue");
    v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(
            *v11,
            (__int64)&v37);
    v6 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x767,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v12,
        v34);
LABEL_49:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      goto LABEL_50;
    }
    String = 0;
    v44 = 0;
    v45 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&String);
    v44 = -1;
    v45 = -1;
    v40 = (struct Windows::Data::Json::IJsonValue *)-2147483646LL;
    FlightingRegString = FSRegUtils::GetFlightingRegString((HKEY *)&v40, 2u, L"QueryServiceList", &String);
    v6 = FlightingRegString;
    if ( FlightingRegString == -2147024894 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&String);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v6 = -2147024894;
      goto LABEL_52;
    }
    if ( FlightingRegString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x76E,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)FlightingRegString,
        v34);
LABEL_48:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&String);
      goto LABEL_49;
    }
    Context = 0;
    v14 = wcstok_s(String, L";", &Context);
    while ( v14 )
    {
      v40 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      v15 = FSPropertyBag::QueryService(this, v14, v37, &v40);
      v6 = v15;
      if ( v15 < 0 )
      {
        v16 = 1914;
        goto LABEL_21;
      }
      v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), struct Windows::Data::Json::IJsonValue *))(*v35)[13])(
              v35,
              v40);
      v6 = v15;
      if ( v15 < 0 )
      {
        v16 = 1918;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
          (const char *)(unsigned int)v15,
          v34);
        v17 = &v40;
        goto LABEL_47;
      }
      v14 = wcstok_s(0, L";", &Context);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    }
    v39 = 0;
    v18 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v35,
            (__int64)&v39);
    v6 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x785,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v18,
        v34);
      goto LABEL_46;
    }
    v38 = 0;
    v20 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[29])v19);
    v21 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v20, &v38);
    v6 = v21;
    if ( v21 < 0 )
    {
      v22 = 1927;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v21,
        v34);
LABEL_45:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
LABEL_46:
      v17 = (struct Windows::Data::Json::IJsonValue **)&v39;
LABEL_47:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v17);
      goto LABEL_48;
    }
    v23 = v38;
    v24 = (*v38)[7];
    v25 = v39;
    length = 0;
    v26 = -1;
    do
      ++v26;
    while ( FSPropertyBag::s_serviceInfoTag[v26] );
    if ( (int)ULongLongToUInt(v26, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSPropertyBag::s_serviceInfoTag, length, &hstringHeader, &string);
    v21 = v24(v23, (GUID *)string, v25);
    v6 = v21;
    if ( v21 < 0 )
    {
      v22 = 1928;
      goto LABEL_27;
    }
    v42 = 0;
    v27 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v38,
            (__int64)&v42);
    v6 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78C,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v27,
        v34);
LABEL_44:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
      goto LABEL_45;
    }
    v46 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 56LL))(v42, &v46);
    v6 = v28;
    if ( v28 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v46, 0);
      do
        ++v4;
      while ( StringRawBuffer[v4] );
      v28 = _AllocStringWorker<CTCoAllocPolicy>(v32, v31, StringRawBuffer);
      v6 = v28;
      if ( v28 >= 0 )
        goto LABEL_43;
      v29 = 1935;
    }
    else
    {
      v29 = 1934;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v28,
      v34);
LABEL_43:
    Windows::Internal::String::~String((Windows::Internal::String *)&v46);
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x759,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
    (const char *)(unsigned int)v5,
    v34);
LABEL_52:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v48);
  return v6;
}

```

## disassembly

```asm
0x1800c0588  mov     [rsp-8+arg_10], rbx
0x1800c058d  push    rbp
0x1800c058e  push    rsi
0x1800c058f  push    rdi
0x1800c0590  push    r12
0x1800c0592  push    r13
0x1800c0594  push    r14
0x1800c0596  push    r15
0x1800c0598  lea     rbp, [rsp-27h]
0x1800c059d  sub     rsp, 0E0h
0x1800c05a4  mov     rax, cs:__security_cookie
0x1800c05ab  xor     rax, rsp
0x1800c05ae  mov     [rbp+57h+var_40], rax
0x1800c05b2  mov     r14, rdx
0x1800c05b5  mov     rsi, rcx
0x1800c05b8  xor     r13d, r13d
0x1800c05bb  mov     [rdx], r13
0x1800c05be  mov     [rbp+57h+var_78], r13
0x1800c05c2  mov     [rbp+57h+var_70], r13
0x1800c05c6  mov     [rbp+57h+var_68], r13
0x1800c05ca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c05ce  mov     r8, rdi
0x1800c05d1  lea     rdx, LocaleName
0x1800c05d8  lea     rcx, [rbp+57h+var_78]
0x1800c05dc  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800c05e1  mov     ebx, eax
0x1800c05e3  test    eax, eax
0x1800c05e5  jns     short loc_1800C0604
0x1800c05e7  mov     rcx, [rbp+5Fh]; this
0x1800c05eb  mov     r9d, eax; char *
0x1800c05ee  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c05f5  mov     edx, 759h; void *
0x1800c05fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c05ff  jmp     loc_1800C0A1B
0x1800c0604  lea     rdx, aServiceinfo; "serviceInfo"
0x1800c060b  mov     rcx, rsi; this
0x1800c060e  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800c0613  test    al, al
0x1800c0615  jnz     short loc_1800C0632
0x1800c0617  mov     rax, [rbp+57h+var_78]
0x1800c061b  mov     [rbp+57h+var_78], r13
0x1800c061f  mov     [rbp+57h+var_68], r13
0x1800c0623  mov     [rbp+57h+var_70], r13
0x1800c0627  mov     [r14], rax
0x1800c062a  mov     ebx, r13d
0x1800c062d  jmp     loc_1800C0A1B
0x1800c0632  mov     [rsp+110h+var_D8], r13
0x1800c0637  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800c063e  lea     rcx, [rbp+57h+string]; string
0x1800c0642  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1800c0647  lea     rdx, [rsp+110h+var_D8]
0x1800c064c  mov     rcx, [rax]
0x1800c064f  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x1800c0654  mov     ebx, eax
0x1800c0656  test    eax, eax
0x1800c0658  jns     short loc_1800C0677
0x1800c065a  mov     rcx, [rbp+5Fh]; this
0x1800c065e  mov     r9d, eax; char *
0x1800c0661  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c0668  mov     edx, 763h; void *
0x1800c066d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0672  jmp     loc_1800C0A10
0x1800c0677  mov     [rsp+110h+var_E0], r13
0x1800c067c  lea     rdx, [rsp+110h+var_E0]
0x1800c0681  lea     rcx, [rsp+110h+var_D8]
0x1800c0686  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x1800c068b  mov     ebx, eax
0x1800c068d  test    eax, eax
0x1800c068f  jns     short loc_1800C06AE
0x1800c0691  mov     rcx, [rbp+5Fh]; this
0x1800c0695  mov     r9d, eax; char *
0x1800c0698  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c069f  mov     edx, 765h; void *
0x1800c06a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c06a9  jmp     loc_1800C0A05
0x1800c06ae  mov     [rbp+57h+var_D0], r13
0x1800c06b2  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800c06b9  lea     rcx, [rbp+57h+string]; string
0x1800c06bd  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1800c06c2  lea     rdx, [rbp+57h+var_D0]
0x1800c06c6  mov     rcx, [rax]
0x1800c06c9  call    ??$GetActivationFactory@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>)
0x1800c06ce  mov     ebx, eax
0x1800c06d0  test    eax, eax
0x1800c06d2  jns     short loc_1800C06F1
0x1800c06d4  mov     rcx, [rbp+5Fh]; this
0x1800c06d8  mov     r9d, eax; char *
0x1800c06db  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c06e2  mov     edx, 767h; void *
0x1800c06e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c06ec  jmp     loc_1800C09FB
0x1800c06f1  mov     [rbp+57h+String], r13
0x1800c06f5  mov     [rbp+57h+var_98], r13
0x1800c06f9  mov     [rbp+57h+var_90], r13
0x1800c06fd  lea     rcx, [rbp+57h+String]
0x1800c0701  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c0706  mov     [rbp+57h+var_98], rdi
0x1800c070a  mov     [rbp+57h+var_90], rdi
0x1800c070e  mov     [rbp+57h+var_B8], 0FFFFFFFF80000002h
0x1800c0716  lea     r9, [rbp+57h+String]
0x1800c071a  lea     r8, aQueryserviceli; "QueryServiceList"
0x1800c0721  mov     edx, 2
0x1800c0726  lea     rcx, [rbp+57h+var_B8]
0x1800c072a  call    ?GetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAPEAG@Z; FSRegUtils::GetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort * *)
0x1800c072f  mov     ebx, eax
0x1800c0731  mov     r15d, 80070002h
0x1800c0737  cmp     eax, r15d
0x1800c073a  jnz     short loc_1800C076D
0x1800c073c  lea     rcx, [rbp+57h+String]
0x1800c0740  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c0745  nop
0x1800c0746  lea     rcx, [rbp+57h+var_D0]
0x1800c074a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c074f  nop
0x1800c0750  lea     rcx, [rsp+110h+var_E0]
0x1800c0755  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c075a  nop
0x1800c075b  lea     rcx, [rsp+110h+var_D8]
0x1800c0760  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c0765  mov     ebx, r15d
0x1800c0768  jmp     loc_1800C0A1B
0x1800c076d  test    eax, eax
0x1800c076f  jns     short loc_1800C078E
0x1800c0771  mov     rcx, [rbp+5Fh]; this
0x1800c0775  mov     r9d, eax; char *
0x1800c0778  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c077f  mov     edx, 76Eh; void *
0x1800c0784  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0789  jmp     loc_1800C09F1
0x1800c078e  mov     [rbp+57h+Context], r13
0x1800c0792  lea     r8, [rbp+57h+Context]; Context
0x1800c0796  lea     rdx, Delimiter; ";"
0x1800c079d  mov     rcx, [rbp+57h+String]; String
0x1800c07a1  call    cs:__imp_wcstok_s
0x1800c07a7  mov     rbx, rax
0x1800c07aa  test    rbx, rbx
0x1800c07ad  jz      loc_1800C083E
0x1800c07b3  mov     [rbp+57h+var_B8], r13
0x1800c07b7  lea     rcx, [rbp+57h+var_B8]
0x1800c07bb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c07c0  lea     r9, [rbp+57h+var_B8]; struct Windows::Data::Json::IJsonValue **
0x1800c07c4  mov     r8, [rbp+57h+var_D0]; struct Windows::Data::Json::IJsonValueStatics *
0x1800c07c8  mov     rdx, rbx; unsigned __int16 *
0x1800c07cb  mov     rcx, rsi; this
0x1800c07ce  call    ?QueryService@FSPropertyBag@@AEAAJPEBGPEAUIJsonValueStatics@Json@Data@Windows@@PEAPEAUIJsonValue@345@@Z; FSPropertyBag::QueryService(ushort const *,Windows::Data::Json::IJsonValueStatics *,Windows::Data::Json::IJsonValue * *)
0x1800c07d3  mov     ebx, eax
0x1800c07d5  test    eax, eax
0x1800c07d7  js      short loc_1800C0837
0x1800c07d9  mov     rcx, [rsp+110h+var_E0]
0x1800c07de  mov     rax, [rcx]
0x1800c07e1  mov     rdx, [rbp+57h+var_B8]
0x1800c07e5  mov     rax, [rax+68h]
0x1800c07e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c07ee  mov     ebx, eax
0x1800c07f0  test    eax, eax
0x1800c07f2  js      short loc_1800C0815
0x1800c07f4  lea     r8, [rbp+57h+Context]; Context
0x1800c07f8  lea     rdx, Delimiter; ";"
0x1800c07ff  xor     ecx, ecx; String
0x1800c0801  call    cs:__imp_wcstok_s
0x1800c0807  mov     rbx, rax
0x1800c080a  lea     rcx, [rbp+57h+var_B8]
0x1800c080e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c0813  jmp     short loc_1800C07AA
0x1800c0815  mov     edx, 77Eh; void *
0x1800c081a  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c0821  mov     r9d, eax; char *
0x1800c0824  mov     rcx, [rbp+5Fh]; this
0x1800c0828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c082d  nop
0x1800c082e  lea     rcx, [rbp+57h+var_B8]
0x1800c0832  jmp     loc_1800C09EB
0x1800c0837  mov     edx, 77Ah
0x1800c083c  jmp     short loc_1800C081A
0x1800c083e  mov     [rbp+57h+var_C0], r13
0x1800c0842  lea     rdx, [rbp+57h+var_C0]
0x1800c0846  lea     rcx, [rsp+110h+var_E0]
0x1800c084b  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800c0850  mov     ebx, eax
0x1800c0852  test    eax, eax
0x1800c0854  jns     short loc_1800C0873
0x1800c0856  mov     rcx, [rbp+5Fh]; this
0x1800c085a  mov     r9d, eax; char *
0x1800c085d  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c0864  mov     edx, 785h; void *
0x1800c0869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c086e  jmp     loc_1800C09E7
0x1800c0873  mov     [rbp+57h+var_C8], r13
0x1800c0877  lea     rcx, [rbp+57h+string]; string
0x1800c087b  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x1800c0880  lea     rdx, [rbp+57h+var_C8]
0x1800c0884  mov     rcx, [rax]
0x1800c0887  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800c088c  mov     ebx, eax
0x1800c088e  test    eax, eax
0x1800c0890  jns     short loc_1800C08AF
0x1800c0892  mov     edx, 787h; void *
0x1800c0897  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c089e  mov     r9d, eax; char *
0x1800c08a1  mov     rcx, [rbp+5Fh]; this
0x1800c08a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c08aa  jmp     loc_1800C09DD
0x1800c08af  mov     rsi, [rbp+57h+var_C8]
0x1800c08b3  mov     rax, [rsi]
0x1800c08b6  mov     r12, [rax+38h]
0x1800c08ba  mov     r15, [rbp+57h+var_C0]
0x1800c08be  mov     rbx, cs:?s_serviceInfoTag@FSPropertyBag@@0QEBGEB; ushort const * const FSPropertyBag::s_serviceInfoTag
0x1800c08c5  mov     [rbp+57h+length], r13d
0x1800c08c9  mov     rcx, rdi
0x1800c08cc  inc     rcx; unsigned __int64
0x1800c08cf  cmp     [rbx+rcx*2], r13w
0x1800c08d4  jnz     short loc_1800C08CC
0x1800c08d6  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800c08da  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800c08df  test    eax, eax
0x1800c08e1  jns     short loc_1800C08F8
0x1800c08e3  xor     r9d, r9d; lpArguments
0x1800c08e6  xor     r8d, r8d; nNumberOfArguments
0x1800c08e9  lea     edx, [r9+1]; dwExceptionFlags
0x1800c08ed  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800c08f2  call    cs:__imp_RaiseException
0x1800c08f8  lea     r9, [rbp+57h+string]; string
0x1800c08fc  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800c0900  mov     edx, [rbp+57h+length]; length
0x1800c0903  mov     rcx, rbx; sourceString
0x1800c0906  call    cs:__imp_WindowsCreateStringReference
0x1800c090c  mov     r8, r15
0x1800c090f  mov     rdx, [rbp+57h+string]
0x1800c0913  mov     rcx, rsi
0x1800c0916  mov     rax, r12
0x1800c0919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c091e  mov     ebx, eax
0x1800c0920  test    eax, eax
0x1800c0922  jns     short loc_1800C092E
0x1800c0924  mov     edx, 788h
0x1800c0929  jmp     loc_1800C0897
0x1800c092e  mov     [rbp+57h+var_A8], r13
0x1800c0932  lea     rdx, [rbp+57h+var_A8]
0x1800c0936  lea     rcx, [rbp+57h+var_C8]
0x1800c093a  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800c093f  mov     ebx, eax
0x1800c0941  test    eax, eax
0x1800c0943  jns     short loc_1800C095F
0x1800c0945  mov     rcx, [rbp+5Fh]; this
0x1800c0949  mov     r9d, eax; char *
0x1800c094c  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c0953  mov     edx, 78Ch; void *
0x1800c0958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c095d  jmp     short loc_1800C09D3
0x1800c095f  mov     [rbp+57h+var_88], r13
0x1800c0963  mov     rcx, [rbp+57h+var_A8]
0x1800c0967  mov     rax, [rcx]
0x1800c096a  lea     rdx, [rbp+57h+var_88]
0x1800c096e  mov     rax, [rax+38h]
0x1800c0972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0977  mov     ebx, eax
0x1800c0979  test    eax, eax
0x1800c097b  jns     short loc_1800C0984
0x1800c097d  mov     edx, 78Eh
0x1800c0982  jmp     short loc_1800C09B5
0x1800c0984  xor     edx, edx; length
0x1800c0986  mov     rcx, [rbp+57h+var_88]; string
0x1800c098a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0990  inc     rdi
0x1800c0993  cmp     [rax+rdi*2], r13w
0x1800c0998  jnz     short loc_1800C0990
0x1800c099a  mov     [rsp+110h+var_E8], r14
0x1800c099f  mov     r9, rdi
0x1800c09a2  mov     r8, rax
0x1800c09a5  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800c09aa  mov     ebx, eax
0x1800c09ac  test    eax, eax
0x1800c09ae  jns     short loc_1800C09C9
0x1800c09b0  mov     edx, 78Fh; void *
0x1800c09b5  mov     r9d, eax; char *
0x1800c09b8  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800c09bf  mov     rcx, [rbp+5Fh]; this
0x1800c09c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c09c8  nop
0x1800c09c9  lea     rcx, [rbp+57h+var_88]; this
0x1800c09cd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c09d2  nop
0x1800c09d3  lea     rcx, [rbp+57h+var_A8]
0x1800c09d7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c09dc  nop
0x1800c09dd  lea     rcx, [rbp+57h+var_C8]
0x1800c09e1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c09e6  nop
0x1800c09e7  lea     rcx, [rbp+57h+var_C0]
0x1800c09eb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c09f0  nop
0x1800c09f1  lea     rcx, [rbp+57h+String]
0x1800c09f5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c09fa  nop
0x1800c09fb  lea     rcx, [rbp+57h+var_D0]
0x1800c09ff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c0a04  nop
0x1800c0a05  lea     rcx, [rsp+110h+var_E0]
0x1800c0a0a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800c0a0f  nop
  ... truncated ...
```
