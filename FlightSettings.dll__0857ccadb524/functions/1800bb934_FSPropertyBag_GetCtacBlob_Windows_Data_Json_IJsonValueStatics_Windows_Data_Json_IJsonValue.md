# FSPropertyBag::GetCtacBlob(Windows::Data::Json::IJsonValueStatics *,Windows::Data::Json::IJsonValue * *)

- ea: `0x1800bb934`
- end: `0x1800bbca4`
- name: `?GetCtacBlob@FSPropertyBag@@AEAAJPEAUIJsonValueStatics@Json@Data@Windows@@PEAPEAUIJsonValue@345@@Z`
- size: `880`
- prototype: `int(FSPropertyBag *__hidden this, struct Windows::Data::Json::IJsonValueStatics *, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800be044`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x18001c6f4`
- `0x18001ec78`
- `0x1800314e0`
- `0x1800325f4`
- `0x1800327ac`
- `0x1800328bc`
- `0x18003290c`
- `0x180085a24`
- `0x18008b7b8`
- `0x1800bb934`
- `0x1800bbcac`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbade`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbade`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbac5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bbaff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bbaff`

## string_xrefs

- `0x1800bba2c`: `Windows.Data.Json.JsonArray`
- `0x1800bb9c8`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bba08`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bba55`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bba90`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bbb12`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bbbb2`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bbbf5`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall FSPropertyBag::GetCtacBlob(
        FSPropertyBag *this,
        struct Windows::Data::Json::IJsonValueStatics *a2,
        struct Windows::Data::Json::IJsonValue **a3)
{
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 *v9; // rax
  int v10; // eax
  int v11; // eax
  HSTRING v12; // rbx
  int ActivationFactory; // eax
  unsigned __int64 v14; // rbx
  __int64 v15; // rsi
  FSPropertyBag *v16; // rcx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  int v21; // [rsp+20h] [rbp-69h]
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-59h] BYREF
  struct Windows::Internal::Flighting::ICommonTargetingAttributesFactory *v23; // [rsp+38h] [rbp-51h] BYREF
  __int64 v24; // [rsp+40h] [rbp-49h] BYREF
  __int64 v25; // [rsp+48h] [rbp-41h] BYREF
  struct Windows::Data::Json::IJsonValue *v26; // [rsp+50h] [rbp-39h] BYREF
  __int64 v27; // [rsp+58h] [rbp-31h] BYREF
  __int64 v28; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int64 v29; // [rsp+68h] [rbp-21h]
  __int64 v30; // [rsp+70h] [rbp-19h]
  __int64 v31; // [rsp+78h] [rbp-11h]
  unsigned __int16 *v32; // [rsp+80h] [rbp-9h] BYREF
  __int64 v33; // [rsp+88h] [rbp-1h]
  __int64 v34; // [rsp+90h] [rbp+7h]
  HSTRING string; // [rsp+98h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v32 = 0;
  v33 = 0;
  v34 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
  v33 = -1;
  v34 = -1;
  v26 = (struct Windows::Data::Json::IJsonValue *)-2147483646LL;
  if ( FSRegUtils::GetFlightingRegString((HKEY *)&v26, 2u, L"RequestedCTACAppIds", &v32) >= 0
    || (v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               &v32,
               L"FSS",
               -1),
        v7 = v6,
        v6 >= 0) )
  {
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v8 = FlightSettingsAPICommon::SplitStringToArray(v32, v5, &v28);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v22 = 0;
      v9 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, L"Windows.Data.Json.JsonArray");
      v10 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(*v9, &v22);
      v7 = v10;
      if ( v10 >= 0 )
      {
        v24 = 0;
        v11 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                &v22,
                (__int64)&v24);
        v7 = v11;
        if ( v11 >= 0 )
        {
          v23 = 0;
          if ( WindowsCreateStringReference(
                 L"Windows.Internal.Flighting.ClientAttributes",
                 0x2Bu,
                 &hstringHeader,
                 &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v12 = string;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
          ActivationFactory = RoGetActivationFactory(v12, &GUID_41845433_1668_4264_8a63_315eb82ab0d6, &v23);
          v7 = ActivationFactory;
          if ( ActivationFactory >= 0 )
          {
            v14 = 0;
            if ( v29 )
            {
              v15 = v28;
              do
              {
                v26 = 0;
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
                if ( (int)FSPropertyBag::GetCtacCollection(
                            v16,
                            a2,
                            v23,
                            *(const unsigned __int16 **)(v15 + 24 * v14),
                            &v26) >= 0 )
                  (*(void (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v24 + 104LL))(
                    v24,
                    v26);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
                ++v14;
              }
              while ( v14 < v29 );
            }
            v25 = 0;
            v17 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                    &v22,
                    (__int64)&v25);
            v7 = v17;
            if ( v17 >= 0 )
            {
              v27 = 0;
              v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 56LL))(v25, &v27);
              v7 = v18;
              if ( v18 >= 0 )
              {
                v18 = (*(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, __int64, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)a2 + 80LL))(
                        a2,
                        v27,
                        a3);
                v7 = v18;
                if ( v18 >= 0 )
                {
                  Windows::Internal::String::~String((Windows::Internal::String *)&v27);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
                  CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::RemoveAll(&v28);
                  v7 = 0;
                  goto LABEL_32;
                }
                v19 = 1841;
              }
              else
              {
                v19 = 1839;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v19,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
                (const char *)(unsigned int)v18,
                v21);
              Windows::Internal::String::~String((Windows::Internal::String *)&v27);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x72B,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
                (const char *)(unsigned int)v17,
                v21);
            }
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x71F,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
              (const char *)(unsigned int)ActivationFactory,
              v21);
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x71B,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
            (const char *)(unsigned int)v11,
            v21);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x718,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
          (const char *)(unsigned int)v10,
          v21);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x714,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v8,
        v21);
    }
    CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::RemoveAll(&v28);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70F,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v6,
      v21);
  }
LABEL_32:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
  return v7;
}

```

## disassembly

```asm
0x1800bb934  mov     [rsp-8+arg_0], rbx
0x1800bb939  push    rbp
0x1800bb93a  push    rsi
0x1800bb93b  push    r12
0x1800bb93d  push    r14
0x1800bb93f  push    r15
0x1800bb941  lea     rbp, [rsp-37h]
0x1800bb946  sub     rsp, 0C0h
0x1800bb94d  mov     rax, cs:__security_cookie
0x1800bb954  xor     rax, rsp
0x1800bb957  mov     [rbp+57h+var_28], rax
0x1800bb95b  mov     r15, r8
0x1800bb95e  mov     r14, rdx
0x1800bb961  xor     r12d, r12d
0x1800bb964  mov     [rbp+57h+var_60], r12
0x1800bb968  mov     [rbp+57h+var_58], r12
0x1800bb96c  mov     [rbp+57h+var_50], r12
0x1800bb970  lea     rcx, [rbp+57h+var_60]
0x1800bb974  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800bb979  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bb97d  mov     [rbp+57h+var_58], rbx
0x1800bb981  mov     [rbp+57h+var_50], rbx
0x1800bb985  mov     [rbp+57h+var_90], 0FFFFFFFF80000002h
0x1800bb98d  lea     r9, [rbp+57h+var_60]
0x1800bb991  lea     r8, aRequestedctaca; "RequestedCTACAppIds"
0x1800bb998  lea     edx, [rbx+3]
0x1800bb99b  lea     rcx, [rbp+57h+var_90]
0x1800bb99f  call    ?GetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAPEAG@Z; FSRegUtils::GetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort * *)
0x1800bb9a4  test    eax, eax
0x1800bb9a6  jns     short loc_1800BB9DE
0x1800bb9a8  mov     r8, rbx
0x1800bb9ab  lea     rdx, aFss; "FSS"
0x1800bb9b2  lea     rcx, [rbp+57h+var_60]
0x1800bb9b6  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800bb9bb  mov     ebx, eax
0x1800bb9bd  test    eax, eax
0x1800bb9bf  jns     short loc_1800BB9DE
0x1800bb9c1  mov     rcx, [rbp+5Fh]; this
0x1800bb9c5  mov     r9d, eax; char *
0x1800bb9c8  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bb9cf  mov     edx, 70Fh; void *
0x1800bb9d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb9d9  jmp     loc_1800BBC75
0x1800bb9de  mov     [rbp+57h+var_80], r12
0x1800bb9e2  mov     [rbp+57h+var_78], r12
0x1800bb9e6  mov     [rbp+57h+var_70], r12
0x1800bb9ea  mov     [rbp+57h+var_68], r12
0x1800bb9ee  lea     r8, [rbp+57h+var_80]
0x1800bb9f2  mov     rcx, [rbp+57h+var_60]
0x1800bb9f6  call    ?SplitStringToArray@FlightSettingsAPICommon@@SAJPEBG0AEAV?$CCoSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@@Z; FlightSettingsAPICommon::SplitStringToArray(ushort const *,ushort const *,CCoSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>> &)
0x1800bb9fb  mov     ebx, eax
0x1800bb9fd  test    eax, eax
0x1800bb9ff  jns     short loc_1800BBA28
0x1800bba01  mov     rcx, [rbp+5Fh]; this
0x1800bba05  mov     r9d, eax; char *
0x1800bba08  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bba0f  mov     edx, 714h; void *
0x1800bba14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bba19  nop
0x1800bba1a  lea     rcx, [rbp+57h+var_80]
0x1800bba1e  call    ?RemoveAll@?$CTSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardMergeHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@QEAAXXZ; CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>>::RemoveAll(void)
0x1800bba23  jmp     loc_1800BBC75
0x1800bba28  mov     [rbp+57h+var_B0], r12
0x1800bba2c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800bba33  lea     rcx, [rbp+57h+string]; string
0x1800bba37  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1800bba3c  lea     rdx, [rbp+57h+var_B0]
0x1800bba40  mov     rcx, [rax]
0x1800bba43  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x1800bba48  mov     ebx, eax
0x1800bba4a  test    eax, eax
0x1800bba4c  jns     short loc_1800BBA72
0x1800bba4e  mov     rcx, [rbp+5Fh]; this
0x1800bba52  mov     r9d, eax; char *
0x1800bba55  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bba5c  mov     edx, 718h; void *
0x1800bba61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bba66  nop
0x1800bba67  lea     rcx, [rbp+57h+var_B0]
0x1800bba6b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bba70  jmp     short loc_1800BBA1A
0x1800bba72  mov     [rbp+57h+var_A0], r12
0x1800bba76  lea     rdx, [rbp+57h+var_A0]
0x1800bba7a  lea     rcx, [rbp+57h+var_B0]
0x1800bba7e  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x1800bba83  mov     ebx, eax
0x1800bba85  test    eax, eax
0x1800bba87  jns     short loc_1800BBAAD
0x1800bba89  mov     rcx, [rbp+5Fh]; this
0x1800bba8d  mov     r9d, eax; char *
0x1800bba90  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bba97  mov     edx, 71Bh; void *
0x1800bba9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbaa1  nop
0x1800bbaa2  lea     rcx, [rbp+57h+var_A0]
0x1800bbaa6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbaab  jmp     short loc_1800BBA67
0x1800bbaad  mov     [rbp+57h+var_A8], r12
0x1800bbab1  lea     r9, [rbp+57h+string]; string
0x1800bbab5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800bbab9  mov     edx, 2Bh ; '+'; length
0x1800bbabe  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_ClientAttributes@@3QBGB; "Windows.Internal.Flighting.ClientAttrib"...
0x1800bbac5  call    cs:__imp_WindowsCreateStringReference
0x1800bbacb  test    eax, eax
0x1800bbacd  jns     short loc_1800BBAE4
0x1800bbacf  xor     r9d, r9d; lpArguments
0x1800bbad2  xor     r8d, r8d; nNumberOfArguments
0x1800bbad5  lea     edx, [r9+1]; dwExceptionFlags
0x1800bbad9  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bbade  call    cs:__imp_RaiseException
0x1800bbae4  mov     rbx, [rbp+57h+string]
0x1800bbae8  lea     rcx, [rbp+57h+var_A8]
0x1800bbaec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbaf1  lea     r8, [rbp+57h+var_A8]
0x1800bbaf5  lea     rdx, _GUID_41845433_1668_4264_8a63_315eb82ab0d6
0x1800bbafc  mov     rcx, rbx
0x1800bbaff  call    cs:__imp_RoGetActivationFactory
0x1800bbb05  mov     ebx, eax
0x1800bbb07  test    eax, eax
0x1800bbb09  jns     short loc_1800BBB32
0x1800bbb0b  mov     rcx, [rbp+5Fh]; this
0x1800bbb0f  mov     r9d, eax; char *
0x1800bbb12  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bbb19  mov     edx, 71Fh; void *
0x1800bbb1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbb23  nop
0x1800bbb24  lea     rcx, [rbp+57h+var_A8]
0x1800bbb28  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbb2d  jmp     loc_1800BBAA2
0x1800bbb32  mov     rbx, r12
0x1800bbb35  cmp     [rbp+57h+var_78], r12
0x1800bbb39  jbe     short loc_1800BBB94
0x1800bbb3b  mov     rsi, [rbp+57h+var_80]
0x1800bbb3f  mov     [rbp+57h+var_90], r12
0x1800bbb43  lea     rcx, [rbp+57h+var_90]
0x1800bbb47  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbb4c  lea     r9, [rbx+rbx*2]
0x1800bbb50  lea     rax, [rbp+57h+var_90]
0x1800bbb54  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800bbb59  mov     r9, [rsi+r9*8]; unsigned __int16 *
0x1800bbb5d  mov     r8, [rbp+57h+var_A8]; struct Windows::Internal::Flighting::ICommonTargetingAttributesFactory *
0x1800bbb61  mov     rdx, r14; struct Windows::Data::Json::IJsonValueStatics *
0x1800bbb64  call    ?GetCtacCollection@FSPropertyBag@@AEAAJPEAUIJsonValueStatics@Json@Data@Windows@@PEAUICommonTargetingAttributesFactory@Flighting@Internal@5@PEBGPEAPEAUIJsonValue@345@@Z; FSPropertyBag::GetCtacCollection(Windows::Data::Json::IJsonValueStatics *,Windows::Internal::Flighting::ICommonTargetingAttributesFactory *,ushort const *,Windows::Data::Json::IJsonValue * *)
0x1800bbb69  test    eax, eax
0x1800bbb6b  js      short loc_1800BBB82
0x1800bbb6d  mov     rcx, [rbp+57h+var_A0]
0x1800bbb71  mov     rax, [rcx]
0x1800bbb74  mov     rdx, [rbp+57h+var_90]
0x1800bbb78  mov     rax, [rax+68h]
0x1800bbb7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb81  nop
0x1800bbb82  lea     rcx, [rbp+57h+var_90]
0x1800bbb86  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbb8b  inc     rbx
0x1800bbb8e  cmp     rbx, [rbp+57h+var_78]
0x1800bbb92  jb      short loc_1800BBB3F
0x1800bbb94  mov     [rbp+57h+var_98], r12
0x1800bbb98  lea     rdx, [rbp+57h+var_98]
0x1800bbb9c  lea     rcx, [rbp+57h+var_B0]
0x1800bbba0  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800bbba5  mov     ebx, eax
0x1800bbba7  test    eax, eax
0x1800bbba9  jns     short loc_1800BBBD2
0x1800bbbab  mov     rcx, [rbp+5Fh]; this
0x1800bbbaf  mov     r9d, eax; char *
0x1800bbbb2  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bbbb9  mov     edx, 72Bh; void *
0x1800bbbbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbbc3  nop
0x1800bbbc4  lea     rcx, [rbp+57h+var_98]
0x1800bbbc8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbbcd  jmp     loc_1800BBB24
0x1800bbbd2  mov     [rbp+57h+var_88], r12
0x1800bbbd6  mov     rcx, [rbp+57h+var_98]
0x1800bbbda  mov     rax, [rcx]
0x1800bbbdd  lea     rdx, [rbp+57h+var_88]
0x1800bbbe1  mov     rax, [rax+38h]
0x1800bbbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbbea  mov     ebx, eax
0x1800bbbec  test    eax, eax
0x1800bbbee  jns     short loc_1800BBC14
0x1800bbbf0  mov     edx, 72Fh; void *
0x1800bbbf5  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bbbfc  mov     r9d, eax; char *
0x1800bbbff  mov     rcx, [rbp+5Fh]; this
0x1800bbc03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbc08  nop
0x1800bbc09  lea     rcx, [rbp+57h+var_88]; this
0x1800bbc0d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800bbc12  jmp     short loc_1800BBBC4
0x1800bbc14  mov     rax, [r14]
0x1800bbc17  mov     r8, r15
0x1800bbc1a  mov     rdx, [rbp+57h+var_88]
0x1800bbc1e  mov     rcx, r14
0x1800bbc21  mov     rax, [rax+50h]
0x1800bbc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc2a  mov     ebx, eax
0x1800bbc2c  test    eax, eax
0x1800bbc2e  jns     short loc_1800BBC37
0x1800bbc30  mov     edx, 731h
0x1800bbc35  jmp     short loc_1800BBBF5
0x1800bbc37  lea     rcx, [rbp+57h+var_88]; this
0x1800bbc3b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800bbc40  nop
0x1800bbc41  lea     rcx, [rbp+57h+var_98]
0x1800bbc45  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbc4a  nop
0x1800bbc4b  lea     rcx, [rbp+57h+var_A8]
0x1800bbc4f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbc54  nop
0x1800bbc55  lea     rcx, [rbp+57h+var_A0]
0x1800bbc59  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbc5e  nop
0x1800bbc5f  lea     rcx, [rbp+57h+var_B0]
0x1800bbc63  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbc68  nop
0x1800bbc69  lea     rcx, [rbp+57h+var_80]
0x1800bbc6d  call    ?RemoveAll@?$CTSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardMergeHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@QEAAXXZ; CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>>::RemoveAll(void)
0x1800bbc72  mov     ebx, r12d
0x1800bbc75  lea     rcx, [rbp+57h+var_60]
0x1800bbc79  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800bbc7e  mov     eax, ebx
0x1800bbc80  mov     rcx, [rbp+57h+var_28]
0x1800bbc84  xor     rcx, rsp; StackCookie
0x1800bbc87  call    __security_check_cookie
0x1800bbc8c  mov     rbx, [rsp+0E0h+arg_0]
0x1800bbc94  add     rsp, 0C0h
0x1800bbc9b  pop     r15
0x1800bbc9d  pop     r14
0x1800bbc9f  pop     r12
0x1800bbca1  pop     rsi
0x1800bbca2  pop     rbp
0x1800bbca3  retn
```
