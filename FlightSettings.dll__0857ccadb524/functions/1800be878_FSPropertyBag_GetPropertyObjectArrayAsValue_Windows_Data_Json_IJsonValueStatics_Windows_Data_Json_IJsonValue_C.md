# FSPropertyBag::GetPropertyObjectArrayAsValue(Windows::Data::Json::IJsonValueStatics *,Windows::Data::Json::IJsonValue * *,CFlightStoreItem * const)

- ea: `0x1800be878`
- end: `0x1800bec7c`
- name: `?GetPropertyObjectArrayAsValue@FSPropertyBag@@AEAAJPEAUIJsonValueStatics@Json@Data@Windows@@PEAPEAUIJsonValue@345@QEAVCFlightStoreItem@@@Z`
- size: `1028`
- prototype: `int(FSPropertyBag *__hidden this, struct Windows::Data::Json::IJsonValueStatics *, struct Windows::Data::Json::IJsonValue **, struct CFlightStoreItem *const)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bcd58`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800325f4`
- `0x1800327ac`
- `0x18003281c`
- `0x1800328bc`
- `0x18003290c`
- `0x1800bddb8`
- `0x1800be878`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bea8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bea9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bea8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bea9a`

## string_xrefs

- `0x1800be8cb`: `Windows.Data.Json.JsonArray`
- `0x1800be8f4`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be928`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be96f`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be9be`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800beb7d`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800beba8`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bebd3`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bec03`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall FSPropertyBag::GetPropertyObjectArrayAsValue(
        FSPropertyBag *this,
        struct Windows::Data::Json::IJsonValueStatics *a2,
        struct Windows::Data::Json::IJsonValue **a3,
        struct CFlightStoreItem *const a4)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64); // rbx
  __int64 *v7; // rax
  int v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  int v19; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v21; // rax
  int JsonValueForProperties; // eax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdx
  struct Windows::Data::Json::IJsonValue *v26; // rax
  int v28; // [rsp+20h] [rbp-59h]
  _BYTE v29[8]; // [rsp+30h] [rbp-49h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-41h] BYREF
  __int64 v31; // [rsp+40h] [rbp-39h] BYREF
  __int64 v32; // [rsp+48h] [rbp-31h] BYREF
  __int64 v33; // [rsp+50h] [rbp-29h] BYREF
  HSTRING string; // [rsp+58h] [rbp-21h] BYREF
  HSTRING v35; // [rsp+60h] [rbp-19h] BYREF
  struct Windows::Data::Json::IJsonValue *v36; // [rsp+68h] [rbp-11h] BYREF
  struct Windows::Data::Json::IJsonValue *v37; // [rsp+70h] [rbp-9h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp-1h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64); // [rsp+80h] [rbp+7h] BYREF
  HSTRING v40; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)a4 + 16);
  v39 = v6;
  if ( v6 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v6)[1])(v6);
  v38 = 0;
  v7 = (__int64 *)Windows::Internal::StringReference::StringReference(&v40, L"Windows.Data.Json.JsonArray");
  v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(*v7, &v38);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v30 = 0;
    v10 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
            &v38,
            (__int64)&v30);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B8,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v10,
        v28);
LABEL_7:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
      goto LABEL_40;
    }
    if ( !v6 )
    {
LABEL_28:
      v37 = 0;
      v23 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
              &v30,
              (__int64)&v37);
      v9 = v23;
      if ( v23 >= 0 )
      {
        v26 = v37;
        v37 = 0;
        *a3 = v26;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
        v9 = 0;
        goto LABEL_40;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E7,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v23,
        v28);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      goto LABEL_7;
    }
    v33 = 0;
    v11 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(
            &v39,
            (__int64)&v33);
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5BE,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v11,
        v28);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      goto LABEL_7;
    }
    v31 = 0;
    v12 = v33;
    v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    v14 = v13(v12, &v31);
    v9 = v14;
    if ( v14 >= 0 )
    {
      v29[0] = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 56LL))(v31, v29);
      v9 = v14;
      if ( v14 >= 0 )
      {
        while ( 1 )
        {
          if ( !v29[0] )
            goto LABEL_27;
          v32 = 0;
          v16 = v31;
          v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
          v18 = v17(v16, &v32);
          v9 = v18;
          if ( v18 < 0 )
            break;
          v35 = 0;
          string = 0;
          v19 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL))(v32, &v35);
          v9 = v19;
          if ( v19 < 0 )
          {
            v25 = 1490;
            goto LABEL_35;
          }
          v19 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 56LL))(v32, &string);
          v9 = v19;
          if ( v19 < 0 )
          {
            v25 = 1491;
LABEL_35:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v25,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
              (const char *)(unsigned int)v19,
              v28);
            goto LABEL_36;
          }
          v36 = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v21 = WindowsGetStringRawBuffer(v35, 0);
          JsonValueForProperties = FSPropertyBag::GetJsonValueForProperties(
                                     (FSPropertyBag *)&v36,
                                     a2,
                                     v21,
                                     StringRawBuffer,
                                     &v36);
          v9 = JsonValueForProperties;
          if ( JsonValueForProperties < 0 )
          {
            v24 = 1495;
LABEL_32:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v24,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
              (const char *)(unsigned int)JsonValueForProperties,
              v28);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
LABEL_36:
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            Windows::Internal::String::~String((Windows::Internal::String *)&v35);
            goto LABEL_38;
          }
          JsonValueForProperties = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), struct Windows::Data::Json::IJsonValue *))(*v30)[13])(
                                     v30,
                                     v36);
          v9 = JsonValueForProperties;
          if ( JsonValueForProperties < 0 )
          {
            v24 = 1497;
            goto LABEL_32;
          }
          if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 64LL))(v31, v29) < 0 )
          {
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            Windows::Internal::String::~String((Windows::Internal::String *)&v35);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
LABEL_27:
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
            goto LABEL_28;
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          Windows::Internal::String::~String((Windows::Internal::String *)&v35);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5CE,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
          (const char *)(unsigned int)v18,
          v28);
LABEL_38:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
        goto LABEL_15;
      }
      v15 = 1479;
    }
    else
    {
      v15 = 1473;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v14,
      v28);
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5B5,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
    (const char *)(unsigned int)v8,
    v28);
LABEL_40:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  return v9;
}

```

## disassembly

```asm
0x1800be878  mov     [rsp-8+arg_0], rbx
0x1800be87d  push    rbp
0x1800be87e  push    rsi
0x1800be87f  push    rdi
0x1800be880  push    r14
0x1800be882  push    r15
0x1800be884  lea     rbp, [rsp-37h]
0x1800be889  sub     rsp, 0B0h
0x1800be890  mov     rax, cs:__security_cookie
0x1800be897  xor     rax, rsp
0x1800be89a  mov     [rbp+57h+var_28], rax
0x1800be89e  mov     rsi, r8
0x1800be8a1  mov     r14, rdx
0x1800be8a4  mov     rbx, [r9+80h]
0x1800be8ab  mov     [rbp+57h+var_50], rbx
0x1800be8af  xor     r15d, r15d
0x1800be8b2  test    rbx, rbx
0x1800be8b5  jz      short loc_1800BE8C7
0x1800be8b7  mov     rax, [rbx]
0x1800be8ba  mov     rcx, rbx
0x1800be8bd  mov     rax, [rax+8]
0x1800be8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8c6  nop
0x1800be8c7  mov     [rbp+57h+var_58], r15
0x1800be8cb  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800be8d2  lea     rcx, [rbp+57h+var_48]; string
0x1800be8d6  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1800be8db  lea     rdx, [rbp+57h+var_58]
0x1800be8df  mov     rcx, [rax]
0x1800be8e2  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x1800be8e7  mov     edi, eax
0x1800be8e9  test    eax, eax
0x1800be8eb  jns     short loc_1800BE90A
0x1800be8ed  mov     rcx, [rbp+5Fh]; this
0x1800be8f1  mov     r9d, eax; char *
0x1800be8f4  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800be8fb  mov     edx, 5B5h; void *
0x1800be900  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be905  jmp     loc_1800BEC44
0x1800be90a  mov     [rbp+57h+var_98], r15
0x1800be90e  lea     rdx, [rbp+57h+var_98]
0x1800be912  lea     rcx, [rbp+57h+var_58]
0x1800be916  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x1800be91b  mov     edi, eax
0x1800be91d  test    eax, eax
0x1800be91f  jns     short loc_1800BE948
0x1800be921  mov     rcx, [rbp+5Fh]; this
0x1800be925  mov     r9d, eax; char *
0x1800be928  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800be92f  mov     edx, 5B8h; void *
0x1800be934  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be939  nop
0x1800be93a  lea     rcx, [rbp+57h+var_98]
0x1800be93e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800be943  jmp     loc_1800BEC44
0x1800be948  test    rbx, rbx
0x1800be94b  jz      loc_1800BEB5B
0x1800be951  mov     [rbp+57h+var_80], r15
0x1800be955  lea     rdx, [rbp+57h+var_80]
0x1800be959  lea     rcx, [rbp+57h+var_50]
0x1800be95d  call    ??$As@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>>)
0x1800be962  mov     edi, eax
0x1800be964  test    eax, eax
0x1800be966  jns     short loc_1800BE98C
0x1800be968  mov     rcx, [rbp+5Fh]; this
0x1800be96c  mov     r9d, eax; char *
0x1800be96f  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800be976  mov     edx, 5BEh; void *
0x1800be97b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be980  nop
0x1800be981  lea     rcx, [rbp+57h+var_80]
0x1800be985  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800be98a  jmp     short loc_1800BE93A
0x1800be98c  mov     [rbp+57h+var_90], r15
0x1800be990  mov     rdi, [rbp+57h+var_80]
0x1800be994  mov     rax, [rdi]
0x1800be997  mov     rbx, [rax+30h]
0x1800be99b  lea     rcx, [rbp+57h+var_90]
0x1800be99f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800be9a4  lea     rdx, [rbp+57h+var_90]
0x1800be9a8  mov     rcx, rdi
0x1800be9ab  mov     rax, rbx
0x1800be9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be9b3  mov     edi, eax
0x1800be9b5  test    eax, eax
0x1800be9b7  jns     short loc_1800BE9DD
0x1800be9b9  mov     edx, 5C1h; void *
0x1800be9be  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800be9c5  mov     r9d, eax; char *
0x1800be9c8  mov     rcx, [rbp+5Fh]; this
0x1800be9cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be9d1  nop
0x1800be9d2  lea     rcx, [rbp+57h+var_90]
0x1800be9d6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800be9db  jmp     short loc_1800BE981
0x1800be9dd  mov     [rbp+57h+var_A0], r15b
0x1800be9e1  mov     rcx, [rbp+57h+var_90]
0x1800be9e5  mov     rax, [rcx]
0x1800be9e8  lea     rdx, [rbp+57h+var_A0]
0x1800be9ec  mov     rax, [rax+38h]
0x1800be9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be9f5  mov     edi, eax
0x1800be9f7  test    eax, eax
0x1800be9f9  jns     short loc_1800BEA02
0x1800be9fb  mov     edx, 5C7h
0x1800bea00  jmp     short loc_1800BE9BE
0x1800bea02  cmp     [rbp+57h+var_A0], r15b
0x1800bea06  jz      loc_1800BEB48
0x1800bea0c  mov     [rbp+57h+var_88], r15
0x1800bea10  mov     rdi, [rbp+57h+var_90]
0x1800bea14  mov     rax, [rdi]
0x1800bea17  mov     rbx, [rax+30h]
0x1800bea1b  lea     rcx, [rbp+57h+var_88]
0x1800bea1f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bea24  lea     rdx, [rbp+57h+var_88]
0x1800bea28  mov     rcx, rdi
0x1800bea2b  mov     rax, rbx
0x1800bea2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bea33  mov     edi, eax
0x1800bea35  test    eax, eax
0x1800bea37  js      loc_1800BEBFC
0x1800bea3d  mov     [rbp+57h+var_70], r15
0x1800bea41  mov     [rbp+57h+string], r15
0x1800bea45  mov     rcx, [rbp+57h+var_88]
0x1800bea49  mov     rax, [rcx]
0x1800bea4c  lea     rdx, [rbp+57h+var_70]
0x1800bea50  mov     rax, [rax+30h]
0x1800bea54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bea59  mov     edi, eax
0x1800bea5b  test    eax, eax
0x1800bea5d  js      loc_1800BEBCE
0x1800bea63  mov     rcx, [rbp+57h+var_88]
0x1800bea67  mov     rax, [rcx]
0x1800bea6a  lea     rdx, [rbp+57h+string]
0x1800bea6e  mov     rax, [rax+38h]
0x1800bea72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bea77  mov     edi, eax
0x1800bea79  test    eax, eax
0x1800bea7b  js      loc_1800BEBC7
0x1800bea81  mov     [rbp+57h+var_68], r15
0x1800bea85  xor     edx, edx; length
0x1800bea87  mov     rcx, [rbp+57h+string]; string
0x1800bea8b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bea91  mov     rbx, rax
0x1800bea94  xor     edx, edx; length
0x1800bea96  mov     rcx, [rbp+57h+var_70]; string
0x1800bea9a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800beaa0  lea     rcx, [rbp+57h+var_68]; this
0x1800beaa4  mov     qword ptr [rsp+0D0h+var_B0], rcx; int
0x1800beaa9  mov     r9, rbx; unsigned __int16 *
0x1800beaac  mov     r8, rax; unsigned __int16 *
0x1800beaaf  mov     rdx, r14; struct Windows::Data::Json::IJsonValueStatics *
0x1800beab2  call    ?GetJsonValueForProperties@FSPropertyBag@@AEAAJPEAUIJsonValueStatics@Json@Data@Windows@@PEBG1PEAPEAUIJsonValue@345@@Z; FSPropertyBag::GetJsonValueForProperties(Windows::Data::Json::IJsonValueStatics *,ushort const *,ushort const *,Windows::Data::Json::IJsonValue * *)
0x1800beab7  mov     edi, eax
0x1800beab9  test    eax, eax
0x1800beabb  js      loc_1800BEBA3
0x1800beac1  mov     rcx, [rbp+57h+var_98]
0x1800beac5  mov     rax, [rcx]
0x1800beac8  mov     rdx, [rbp+57h+var_68]
0x1800beacc  mov     rax, [rax+68h]
0x1800bead0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bead5  mov     edi, eax
0x1800bead7  test    eax, eax
0x1800bead9  js      loc_1800BEB9C
0x1800beadf  mov     rcx, [rbp+57h+var_90]
0x1800beae3  mov     rax, [rcx]
0x1800beae6  lea     rdx, [rbp+57h+var_A0]
0x1800beaea  mov     rax, [rax+40h]
0x1800beaee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beaf3  nop
0x1800beaf4  lea     rcx, [rbp+57h+var_68]
0x1800beaf8  test    eax, eax
0x1800beafa  js      short loc_1800BEB24
0x1800beafc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800beb01  nop
0x1800beb02  lea     rcx, [rbp+57h+string]; this
0x1800beb06  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800beb0b  nop
0x1800beb0c  lea     rcx, [rbp+57h+var_70]; this
0x1800beb10  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800beb15  nop
0x1800beb16  lea     rcx, [rbp+57h+var_88]
0x1800beb1a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800beb1f  jmp     loc_1800BEA02
0x1800beb24  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800beb29  nop
0x1800beb2a  lea     rcx, [rbp+57h+string]; this
0x1800beb2e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800beb33  nop
0x1800beb34  lea     rcx, [rbp+57h+var_70]; this
0x1800beb38  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800beb3d  nop
0x1800beb3e  lea     rcx, [rbp+57h+var_88]
0x1800beb42  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800beb47  nop
0x1800beb48  lea     rcx, [rbp+57h+var_90]
0x1800beb4c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800beb51  nop
0x1800beb52  lea     rcx, [rbp+57h+var_80]
0x1800beb56  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800beb5b  mov     [rbp+57h+var_60], r15
0x1800beb5f  lea     rdx, [rbp+57h+var_60]
0x1800beb63  lea     rcx, [rbp+57h+var_98]
0x1800beb67  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800beb6c  mov     edi, eax
0x1800beb6e  test    eax, eax
0x1800beb70  jns     loc_1800BEC23
0x1800beb76  mov     rcx, [rbp+5Fh]; this
0x1800beb7a  mov     r9d, eax; char *
0x1800beb7d  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800beb84  mov     edx, 5E7h; void *
0x1800beb89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800beb8e  lea     rcx, [rbp+57h+var_60]
0x1800beb92  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800beb97  jmp     loc_1800BE93A
0x1800beb9c  mov     edx, 5D9h
0x1800beba1  jmp     short loc_1800BEBA8
0x1800beba3  mov     edx, 5D7h; void *
0x1800beba8  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bebaf  mov     r9d, eax; char *
0x1800bebb2  mov     rcx, [rbp+5Fh]; this
0x1800bebb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bebbb  nop
0x1800bebbc  lea     rcx, [rbp+57h+var_68]
0x1800bebc0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bebc5  jmp     short loc_1800BEBE7
0x1800bebc7  mov     edx, 5D3h
0x1800bebcc  jmp     short loc_1800BEBD3
0x1800bebce  mov     edx, 5D2h; void *
0x1800bebd3  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bebda  mov     r9d, eax; char *
0x1800bebdd  mov     rcx, [rbp+5Fh]; this
0x1800bebe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bebe6  nop
0x1800bebe7  lea     rcx, [rbp+57h+string]; this
0x1800bebeb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800bebf0  nop
0x1800bebf1  lea     rcx, [rbp+57h+var_70]; this
0x1800bebf5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800bebfa  jmp     short loc_1800BEC15
0x1800bebfc  mov     rcx, [rbp+5Fh]; this
0x1800bec00  mov     r9d, eax; char *
0x1800bec03  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bec0a  mov     edx, 5CEh; void *
0x1800bec0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bec14  nop
0x1800bec15  lea     rcx, [rbp+57h+var_88]
0x1800bec19  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bec1e  jmp     loc_1800BE9D2
0x1800bec23  mov     rax, [rbp+57h+var_60]
0x1800bec27  mov     [rbp+57h+var_60], r15
0x1800bec2b  mov     [rsi], rax
0x1800bec2e  lea     rcx, [rbp+57h+var_60]
0x1800bec32  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bec37  nop
0x1800bec38  lea     rcx, [rbp+57h+var_98]
0x1800bec3c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bec41  mov     edi, r15d
0x1800bec44  lea     rcx, [rbp+57h+var_58]
0x1800bec48  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bec4d  nop
0x1800bec4e  lea     rcx, [rbp+57h+var_50]
0x1800bec52  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bec57  mov     eax, edi
0x1800bec59  mov     rcx, [rbp+57h+var_28]
0x1800bec5d  xor     rcx, rsp; StackCookie
0x1800bec60  call    __security_check_cookie
0x1800bec65  mov     rbx, [rsp+0D0h+arg_0]
0x1800bec6d  add     rsp, 0B0h
0x1800bec74  pop     r15
0x1800bec76  pop     r14
0x1800bec78  pop     rdi
0x1800bec79  pop     rsi
0x1800bec7a  pop     rbp
0x1800bec7b  retn
```
