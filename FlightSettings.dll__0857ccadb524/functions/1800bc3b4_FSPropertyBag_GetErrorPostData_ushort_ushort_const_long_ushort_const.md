# FSPropertyBag::GetErrorPostData(ushort * *,ushort const *,long,ushort const *)

- ea: `0x1800bc3b4`
- end: `0x1800bca24`
- name: `?GetErrorPostData@FSPropertyBag@@QEAAJPEAPEAGPEBGJ1@Z`
- size: `1648`
- prototype: `int(FSPropertyBag *__hidden this, unsigned __int16 **, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180098278`
- `0x1800987a4`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001c6f4`
- `0x18002035c`
- `0x1800325f4`
- `0x180032640`
- `0x1800327e4`
- `0x18003290c`
- `0x1800334f0`
- `0x18008fbd8`
- `0x1800bc3b4`
- `0x1800bec84`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc4bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc568`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc641`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc6e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc766`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc806`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc8a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc4bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc568`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc641`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc6e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc766`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc806`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bc8a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc57d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc6f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc77b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc81b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc57d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc6f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc77b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc81b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bc8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc95f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc95f`

## string_xrefs

- `0x1800bc432`: `Windows.Data.Json.JsonValue`
- `0x1800bc418`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc45b`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc4f5`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc5d6`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc67a`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc79f`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc8ed`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc93c`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc990`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall FSPropertyBag::GetErrorPostData(
        FSPropertyBag *this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const unsigned __int16 *sourceString)
{
  __int64 *v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 *v10; // rax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING, __int64 *); // r14
  __int64 v14; // rbx
  unsigned __int64 v15; // rcx
  int v16; // edi
  __int64 v17; // rdx
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64); // r15
  __int64 v20; // r14
  unsigned __int64 v21; // rcx
  const ULONG_PTR *v22; // r9
  int v23; // eax
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, HSTRING, __int64 *); // r14
  const WCHAR *v26; // rdi
  unsigned __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64); // r15
  __int64 v31; // r14
  unsigned __int64 v32; // rcx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, HSTRING, __int64 *); // rsi
  unsigned __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v38)(_QWORD, GUID *, __int64); // r15
  __int64 v39; // r14
  unsigned __int64 v40; // rcx
  FSPropertyBag *v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v43)(_QWORD, GUID *, __int64); // r15
  struct Windows::Data::Json::IJsonValue *v44; // r14
  unsigned __int64 v45; // rcx
  int v46; // eax
  int v47; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v49; // rdx
  int v50; // eax
  int v52; // [rsp+20h] [rbp-91h]
  UINT32 length; // [rsp+30h] [rbp-81h] BYREF
  __int64 v54; // [rsp+38h] [rbp-79h] BYREF
  __int64 v55; // [rsp+40h] [rbp-71h] BYREF
  __int64 v56; // [rsp+48h] [rbp-69h] BYREF
  __int64 v57; // [rsp+50h] [rbp-61h] BYREF
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-59h] BYREF
  struct Windows::Data::Json::IJsonValue *v59; // [rsp+60h] [rbp-51h] BYREF
  __int64 v60; // [rsp+68h] [rbp-49h] BYREF
  HSTRING v61; // [rsp+70h] [rbp-41h] BYREF
  unsigned __int16 **v62; // [rsp+78h] [rbp-39h]
  HSTRING string; // [rsp+80h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-29h] BYREF
  HSTRING v65; // [rsp+A0h] [rbp-11h] BYREF
  HSTRING_HEADER v66; // [rsp+A8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v62 = a2;
  *a2 = 0;
  v58 = 0;
  v7 = (__int64 *)Windows::Internal::StringReference::StringReference(&v65, (const unsigned __int16 (*)[29])a2);
  v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v7, &v58);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v54 = 0;
    v10 = (__int64 *)Windows::Internal::StringReference::StringReference(&v65, L"Windows.Data.Json.JsonValue");
    v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(
            *v10,
            (__int64)&v54);
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27A,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v11,
        v52);
LABEL_66:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
      goto LABEL_67;
    }
    v55 = 0;
    v12 = v54;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v54 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
    length = 0;
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( a3[v15] );
    if ( (int)ULongLongToUInt(v15, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a3, length, &hstringHeader, &string);
    v16 = v13(v12, string, &v55);
    if ( v16 < 0 )
    {
      v17 = 638;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v16,
        v52);
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
      v9 = v16;
      goto LABEL_67;
    }
    v18 = v58;
    v19 = (*v58)[7];
    v20 = v55;
    length = 0;
    v21 = -1;
    do
      ++v21;
    while ( FSPropertyBag::s_errorInstanceId[v21] );
    if ( (int)ULongLongToUInt(v21, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, v22);
    WindowsCreateStringReference(FSPropertyBag::s_errorInstanceId, length, &hstringHeader, &string);
    v16 = v19(v18, (GUID *)string, v20);
    if ( v16 < 0 )
    {
      v17 = 639;
      goto LABEL_11;
    }
    string = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
    v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            &string,
            L"%lu",
            a4);
    v16 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x283,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v23,
        v52);
LABEL_21:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
      goto LABEL_12;
    }
    v56 = 0;
    v24 = v54;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v54 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
    v26 = (const WCHAR *)string;
    length = 0;
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)string + v27) );
    if ( (int)ULongLongToUInt(v27, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(v26, length, &v66, &v65);
    v16 = v25(v24, v65, &v56);
    if ( v16 < 0 )
    {
      v28 = 647;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v16,
        v52);
LABEL_29:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      goto LABEL_21;
    }
    v29 = v58;
    v30 = (*v58)[7];
    v31 = v56;
    length = 0;
    v32 = -1;
    do
      ++v32;
    while ( FSPropertyBag::s_errorErrorCode[v32] );
    if ( (int)ULongLongToUInt(v32, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSPropertyBag::s_errorErrorCode, length, &v66, &v65);
    v16 = v30(v29, (GUID *)v65, v31);
    if ( v16 < 0 )
    {
      v28 = 648;
      goto LABEL_28;
    }
    v57 = 0;
    v33 = v54;
    v34 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v54 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
    length = 0;
    v35 = -1;
    do
      ++v35;
    while ( sourceString[v35] );
    if ( (int)ULongLongToUInt(v35, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(sourceString, length, &v66, &v65);
    v16 = v34(v33, v65, &v57);
    if ( v16 >= 0 )
    {
      v37 = v58;
      v38 = (*v58)[7];
      v39 = v57;
      length = 0;
      v40 = -1;
      do
        ++v40;
      while ( FSPropertyBag::s_errorFailedAction[v40] );
      if ( (int)ULongLongToUInt(v40, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(FSPropertyBag::s_errorFailedAction, length, &v66, &v65);
      v16 = v38(v37, (GUID *)v65, v39);
      if ( v16 >= 0 )
      {
        v59 = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
        if ( (int)FSPropertyBag::GetServiceDrivenActionResultsAsJsonValue(v41, &v59) >= 0 )
        {
          v42 = v58;
          v43 = (*v58)[7];
          v44 = v59;
          length = 0;
          v45 = -1;
          do
            ++v45;
          while ( FSPropertyBag::s_postServiceDrivenActionResults[v45] );
          if ( (int)ULongLongToUInt(v45, &length) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          WindowsCreateStringReference(FSPropertyBag::s_postServiceDrivenActionResults, length, &v66, &v65);
          v43(v42, (GUID *)v65, (__int64)v44);
        }
        v60 = 0;
        v46 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                &v58,
                (__int64)&v60);
        v16 = v46;
        if ( v46 >= 0 )
        {
          v61 = 0;
          v47 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v60 + 56LL))(v60, &v61);
          v16 = v47;
          if ( v47 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v61, 0);
            do
              ++v14;
            while ( StringRawBuffer[v14] );
            v50 = _AllocStringWorker<CTCoAllocPolicy>(v62, v49, StringRawBuffer);
            v9 = v50;
            if ( v50 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x29E,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
                (const char *)(unsigned int)v50,
                v52);
            Windows::Internal::String::~String((Windows::Internal::String *)&v61);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
            goto LABEL_66;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x29D,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
            (const char *)(unsigned int)v47,
            v52);
          Windows::Internal::String::~String((Windows::Internal::String *)&v61);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x29A,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
            (const char *)(unsigned int)v46,
            v52);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
        goto LABEL_43;
      }
      v36 = 655;
    }
    else
    {
      v36 = 652;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v16,
      v52);
LABEL_43:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x277,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
    (const char *)(unsigned int)v8,
    v52);
LABEL_67:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
  return v9;
}

```

## disassembly

```asm
0x1800bc3b4  mov     [rsp-8+arg_0], rbx
0x1800bc3b9  push    rbp
0x1800bc3ba  push    rsi
0x1800bc3bb  push    rdi
0x1800bc3bc  push    r12
0x1800bc3be  push    r13
0x1800bc3c0  push    r14
0x1800bc3c2  push    r15
0x1800bc3c4  lea     rbp, [rsp-1Fh]
0x1800bc3c9  sub     rsp, 0D0h
0x1800bc3d0  mov     rax, cs:__security_cookie
0x1800bc3d7  xor     rax, rsp
0x1800bc3da  mov     [rbp+4Fh+var_40], rax
0x1800bc3de  mov     r12d, r9d
0x1800bc3e1  mov     rsi, r8
0x1800bc3e4  mov     [rbp+4Fh+var_88], rdx
0x1800bc3e8  mov     r13, [rbp+4Fh+sourceString]
0x1800bc3ec  xor     r15d, r15d
0x1800bc3ef  mov     [rdx], r15
0x1800bc3f2  mov     [rbp+4Fh+var_A8], r15
0x1800bc3f6  lea     rcx, [rbp+4Fh+var_60]; string
0x1800bc3fa  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x1800bc3ff  lea     rdx, [rbp+4Fh+var_A8]
0x1800bc403  mov     rcx, [rax]
0x1800bc406  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800bc40b  mov     ebx, eax
0x1800bc40d  test    eax, eax
0x1800bc40f  jns     short loc_1800BC42E
0x1800bc411  mov     rcx, [rbp+57h]; this
0x1800bc415  mov     r9d, eax; char *
0x1800bc418  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bc41f  mov     edx, 277h; void *
0x1800bc424  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc429  jmp     loc_1800BC9F2
0x1800bc42e  mov     [rbp+4Fh+var_C8], r15
0x1800bc432  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800bc439  lea     rcx, [rbp+4Fh+var_60]; string
0x1800bc43d  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1800bc442  lea     rdx, [rbp+4Fh+var_C8]
0x1800bc446  mov     rcx, [rax]
0x1800bc449  call    ??$GetActivationFactory@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>)
0x1800bc44e  mov     ebx, eax
0x1800bc450  test    eax, eax
0x1800bc452  jns     short loc_1800BC471
0x1800bc454  mov     rcx, [rbp+57h]; this
0x1800bc458  mov     r9d, eax; char *
0x1800bc45b  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bc462  mov     edx, 27Ah; void *
0x1800bc467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc46c  jmp     loc_1800BC9E8
0x1800bc471  mov     [rbp+4Fh+var_C0], r15
0x1800bc475  mov     rdi, [rbp+4Fh+var_C8]
0x1800bc479  mov     rax, [rdi]
0x1800bc47c  mov     r14, [rax+50h]
0x1800bc480  lea     rcx, [rbp+4Fh+var_C0]
0x1800bc484  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc489  mov     [rsp+100h+length], r15d
0x1800bc48e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bc492  mov     rcx, rbx
0x1800bc495  inc     rcx; unsigned __int64
0x1800bc498  cmp     [rsi+rcx*2], r15w
0x1800bc49d  jnz     short loc_1800BC495
0x1800bc49f  lea     rdx, [rsp+100h+length]; unsigned int *
0x1800bc4a4  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bc4a9  test    eax, eax
0x1800bc4ab  jns     short loc_1800BC4C2
0x1800bc4ad  xor     r9d, r9d; lpArguments
0x1800bc4b0  xor     r8d, r8d; nNumberOfArguments
0x1800bc4b3  lea     edx, [r9+1]; dwExceptionFlags
0x1800bc4b7  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bc4bc  call    cs:__imp_RaiseException
0x1800bc4c2  lea     r9, [rbp+4Fh+string]; string
0x1800bc4c6  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800bc4ca  mov     edx, [rsp+100h+length]; length
0x1800bc4ce  mov     rcx, rsi; sourceString
0x1800bc4d1  call    cs:__imp_WindowsCreateStringReference
0x1800bc4d7  lea     r8, [rbp+4Fh+var_C0]
0x1800bc4db  mov     rdx, [rbp+4Fh+string]
0x1800bc4df  mov     rcx, rdi
0x1800bc4e2  mov     rax, r14
0x1800bc4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc4ea  mov     edi, eax
0x1800bc4ec  test    eax, eax
0x1800bc4ee  jns     short loc_1800BC523
0x1800bc4f0  mov     edx, 27Eh; void *
0x1800bc4f5  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bc4fc  mov     r9d, edi; char *
0x1800bc4ff  mov     rcx, [rbp+57h]; this
0x1800bc503  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc508  nop
0x1800bc509  lea     rcx, [rbp+4Fh+var_C0]
0x1800bc50d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc512  nop
0x1800bc513  lea     rcx, [rbp+4Fh+var_C8]
0x1800bc517  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc51c  mov     ebx, edi
0x1800bc51e  jmp     loc_1800BC9F2
0x1800bc523  mov     rsi, [rbp+4Fh+var_A8]
0x1800bc527  mov     rax, [rsi]
0x1800bc52a  mov     r15, [rax+38h]
0x1800bc52e  mov     r14, [rbp+4Fh+var_C0]
0x1800bc532  mov     rdi, cs:?s_errorInstanceId@FSPropertyBag@@0QEBGEB; ushort const * const FSPropertyBag::s_errorInstanceId
0x1800bc539  xor     r9d, r9d
0x1800bc53c  mov     [rsp+100h+length], r9d
0x1800bc541  mov     rcx, rbx
0x1800bc544  inc     rcx; unsigned __int64
0x1800bc547  cmp     [rdi+rcx*2], r9w
0x1800bc54c  jnz     short loc_1800BC544
0x1800bc54e  lea     rdx, [rsp+100h+length]; unsigned int *
0x1800bc553  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bc558  test    eax, eax
0x1800bc55a  jns     short loc_1800BC56E
0x1800bc55c  xor     r8d, r8d; nNumberOfArguments
0x1800bc55f  lea     edx, [r8+1]; dwExceptionFlags
0x1800bc563  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bc568  call    cs:__imp_RaiseException
0x1800bc56e  lea     r9, [rbp+4Fh+string]; string
0x1800bc572  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800bc576  mov     edx, [rsp+100h+length]; length
0x1800bc57a  mov     rcx, rdi; sourceString
0x1800bc57d  call    cs:__imp_WindowsCreateStringReference
0x1800bc583  mov     r8, r14
0x1800bc586  mov     rdx, [rbp+4Fh+string]
0x1800bc58a  mov     rcx, rsi
0x1800bc58d  mov     rax, r15
0x1800bc590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc595  mov     edi, eax
0x1800bc597  xor     eax, eax
0x1800bc599  test    edi, edi
0x1800bc59b  jns     short loc_1800BC5A7
0x1800bc59d  mov     edx, 27Fh
0x1800bc5a2  jmp     loc_1800BC4F5
0x1800bc5a7  mov     [rbp+4Fh+string], rax
0x1800bc5ab  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved], rax
0x1800bc5af  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+8], rax
0x1800bc5b3  mov     r8d, r12d
0x1800bc5b6  lea     rdx, aLu; "%lu"
0x1800bc5bd  lea     rcx, [rbp+4Fh+string]
0x1800bc5c1  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800bc5c6  mov     edi, eax
0x1800bc5c8  xor     r12d, r12d
0x1800bc5cb  test    eax, eax
0x1800bc5cd  jns     short loc_1800BC5F6
0x1800bc5cf  mov     rcx, [rbp+57h]; this
0x1800bc5d3  mov     r9d, eax; char *
0x1800bc5d6  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bc5dd  mov     edx, 283h; void *
0x1800bc5e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc5e7  nop
0x1800bc5e8  lea     rcx, [rbp+4Fh+string]
0x1800bc5ec  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800bc5f1  jmp     loc_1800BC509
0x1800bc5f6  mov     [rbp+4Fh+var_B8], r12
0x1800bc5fa  mov     rsi, [rbp+4Fh+var_C8]
0x1800bc5fe  mov     rax, [rsi]
0x1800bc601  mov     r14, [rax+50h]
0x1800bc605  lea     rcx, [rbp+4Fh+var_B8]
0x1800bc609  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc60e  mov     rdi, [rbp+4Fh+string]
0x1800bc612  mov     [rsp+100h+length], r12d
0x1800bc617  mov     rcx, rbx
0x1800bc61a  inc     rcx; unsigned __int64
0x1800bc61d  cmp     [rdi+rcx*2], r12w
0x1800bc622  jnz     short loc_1800BC61A
0x1800bc624  lea     rdx, [rsp+100h+length]; unsigned int *
0x1800bc629  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bc62e  test    eax, eax
0x1800bc630  jns     short loc_1800BC647
0x1800bc632  xor     r9d, r9d; lpArguments
0x1800bc635  xor     r8d, r8d; nNumberOfArguments
0x1800bc638  lea     edx, [r9+1]; dwExceptionFlags
0x1800bc63c  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bc641  call    cs:__imp_RaiseException
0x1800bc647  lea     r9, [rbp+4Fh+var_60]; string
0x1800bc64b  lea     r8, [rbp+4Fh+var_58]; hstringHeader
0x1800bc64f  mov     edx, [rsp+100h+length]; length
0x1800bc653  mov     rcx, rdi; sourceString
0x1800bc656  call    cs:__imp_WindowsCreateStringReference
0x1800bc65c  lea     r8, [rbp+4Fh+var_B8]
0x1800bc660  mov     rdx, [rbp+4Fh+var_60]
0x1800bc664  mov     rcx, rsi
0x1800bc667  mov     rax, r14
0x1800bc66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc66f  mov     edi, eax
0x1800bc671  test    eax, eax
0x1800bc673  jns     short loc_1800BC69C
0x1800bc675  mov     edx, 287h; void *
0x1800bc67a  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bc681  mov     r9d, edi; char *
0x1800bc684  mov     rcx, [rbp+57h]; this
0x1800bc688  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc68d  nop
0x1800bc68e  lea     rcx, [rbp+4Fh+var_B8]
0x1800bc692  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc697  jmp     loc_1800BC5E8
0x1800bc69c  mov     rsi, [rbp+4Fh+var_A8]
0x1800bc6a0  mov     rax, [rsi]
0x1800bc6a3  mov     r15, [rax+38h]
0x1800bc6a7  mov     r14, [rbp+4Fh+var_B8]
0x1800bc6ab  mov     rdi, cs:?s_errorErrorCode@FSPropertyBag@@0QEBGEB; ushort const * const FSPropertyBag::s_errorErrorCode
0x1800bc6b2  mov     [rsp+100h+length], r12d
0x1800bc6b7  mov     rcx, rbx
0x1800bc6ba  inc     rcx; unsigned __int64
0x1800bc6bd  cmp     [rdi+rcx*2], r12w
0x1800bc6c2  jnz     short loc_1800BC6BA
0x1800bc6c4  lea     rdx, [rsp+100h+length]; unsigned int *
0x1800bc6c9  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bc6ce  test    eax, eax
0x1800bc6d0  jns     short loc_1800BC6E7
0x1800bc6d2  xor     r9d, r9d; lpArguments
0x1800bc6d5  xor     r8d, r8d; nNumberOfArguments
0x1800bc6d8  lea     edx, [r9+1]; dwExceptionFlags
0x1800bc6dc  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bc6e1  call    cs:__imp_RaiseException
0x1800bc6e7  lea     r9, [rbp+4Fh+var_60]; string
0x1800bc6eb  lea     r8, [rbp+4Fh+var_58]; hstringHeader
0x1800bc6ef  mov     edx, [rsp+100h+length]; length
0x1800bc6f3  mov     rcx, rdi; sourceString
0x1800bc6f6  call    cs:__imp_WindowsCreateStringReference
0x1800bc6fc  mov     r8, r14
0x1800bc6ff  mov     rdx, [rbp+4Fh+var_60]
0x1800bc703  mov     rcx, rsi
0x1800bc706  mov     rax, r15
0x1800bc709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc70e  mov     edi, eax
0x1800bc710  test    eax, eax
0x1800bc712  jns     short loc_1800BC71E
0x1800bc714  mov     edx, 288h
0x1800bc719  jmp     loc_1800BC67A
0x1800bc71e  mov     [rbp+4Fh+var_B0], r12
0x1800bc722  mov     rdi, [rbp+4Fh+var_C8]
0x1800bc726  mov     rax, [rdi]
0x1800bc729  mov     rsi, [rax+30h]
0x1800bc72d  lea     rcx, [rbp+4Fh+var_B0]
0x1800bc731  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc736  mov     [rsp+100h+length], r12d
0x1800bc73b  mov     rcx, rbx
0x1800bc73e  inc     rcx; unsigned __int64
0x1800bc741  cmp     [r13+rcx*2+0], r12w
0x1800bc747  jnz     short loc_1800BC73E
0x1800bc749  lea     rdx, [rsp+100h+length]; unsigned int *
0x1800bc74e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bc753  test    eax, eax
0x1800bc755  jns     short loc_1800BC76C
0x1800bc757  xor     r9d, r9d; lpArguments
0x1800bc75a  xor     r8d, r8d; nNumberOfArguments
0x1800bc75d  lea     edx, [r9+1]; dwExceptionFlags
0x1800bc761  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bc766  call    cs:__imp_RaiseException
0x1800bc76c  lea     r9, [rbp+4Fh+var_60]; string
0x1800bc770  lea     r8, [rbp+4Fh+var_58]; hstringHeader
0x1800bc774  mov     edx, [rsp+100h+length]; length
0x1800bc778  mov     rcx, r13; sourceString
0x1800bc77b  call    cs:__imp_WindowsCreateStringReference
0x1800bc781  lea     r8, [rbp+4Fh+var_B0]
0x1800bc785  mov     rdx, [rbp+4Fh+var_60]
0x1800bc789  mov     rcx, rdi
0x1800bc78c  mov     rax, rsi
0x1800bc78f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc794  mov     edi, eax
0x1800bc796  test    eax, eax
0x1800bc798  jns     short loc_1800BC7C1
0x1800bc79a  mov     edx, 28Ch; void *
0x1800bc79f  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bc7a6  mov     r9d, edi; char *
0x1800bc7a9  mov     rcx, [rbp+57h]; this
0x1800bc7ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc7b2  nop
0x1800bc7b3  lea     rcx, [rbp+4Fh+var_B0]
0x1800bc7b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc7bc  jmp     loc_1800BC68E
0x1800bc7c1  mov     rsi, [rbp+4Fh+var_A8]
0x1800bc7c5  mov     rax, [rsi]
0x1800bc7c8  mov     r15, [rax+38h]
0x1800bc7cc  mov     r14, [rbp+4Fh+var_B0]
0x1800bc7d0  mov     rdi, cs:?s_errorFailedAction@FSPropertyBag@@0QEBGEB; ushort const * const FSPropertyBag::s_errorFailedAction
0x1800bc7d7  mov     [rsp+100h+length], r12d
0x1800bc7dc  mov     rcx, rbx
0x1800bc7df  inc     rcx; unsigned __int64
0x1800bc7e2  cmp     [rdi+rcx*2], r12w
0x1800bc7e7  jnz     short loc_1800BC7DF
0x1800bc7e9  lea     rdx, [rsp+100h+length]; unsigned int *
0x1800bc7ee  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bc7f3  test    eax, eax
0x1800bc7f5  jns     short loc_1800BC80C
0x1800bc7f7  xor     r9d, r9d; lpArguments
0x1800bc7fa  xor     r8d, r8d; nNumberOfArguments
0x1800bc7fd  lea     edx, [r9+1]; dwExceptionFlags
0x1800bc801  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bc806  call    cs:__imp_RaiseException
0x1800bc80c  lea     r9, [rbp+4Fh+var_60]; string
0x1800bc810  lea     r8, [rbp+4Fh+var_58]; hstringHeader
0x1800bc814  mov     edx, [rsp+100h+length]; length
0x1800bc818  mov     rcx, rdi; sourceString
0x1800bc81b  call    cs:__imp_WindowsCreateStringReference
0x1800bc821  mov     r8, r14
0x1800bc824  mov     rdx, [rbp+4Fh+var_60]
0x1800bc828  mov     rcx, rsi
0x1800bc82b  mov     rax, r15
0x1800bc82e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
