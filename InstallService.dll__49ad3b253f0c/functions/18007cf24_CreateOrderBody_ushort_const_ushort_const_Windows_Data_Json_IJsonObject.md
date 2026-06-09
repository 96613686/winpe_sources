# CreateOrderBody(ushort const *,ushort const *,Windows::Data::Json::IJsonObject * *)

- ea: `0x18007cf24`
- end: `0x18007d280`
- name: `?CreateOrderBody@@YAJPEBG0PEAPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject **)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007ca8c`
- `0x18007d288`

## callees

- `0x180009ea0`
- `0x18000ad30`
- `0x1800101f4`
- `0x1800252e8`
- `0x1800341b0`
- `0x180068578`
- `0x18007cf24`
- `0x1800d5f08`
- `0x1800d5fa8`
- `0x1800da324`
- `0x1800ffe38`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d1d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d24f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d1d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d24f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d05d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d088`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d1fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d05d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d088`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d1fc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007cfe8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007cfe8`

## string_xrefs

- `0x18007cf9a`: `Windows.Data.Json.JsonObject`
- `0x18007d0bf`: `Windows.Data.Json.JsonObject`
- `0x18007d198`: `Windows.Data.Json.JsonObject`
- `0x18007d0e7`: `StoreAgent`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CreateOrderBody(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct Windows::Data::Json::IJsonObject **a3)
{
  HRESULT LanguageAndRegion; // ebx
  const unsigned __int16 *v7; // rsi
  unsigned __int64 v8; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v10; // rax
  struct Windows::Data::Json::IJsonObject *v11; // rsi
  __int64 (__fastcall *v12)(struct Windows::Data::Json::IJsonObject *, __int64, PVOID); // rdi
  PVOID Reserved1; // rbx
  const unsigned __int16 *v14; // rax
  struct Windows::Data::Json::IJsonObject *v15; // rax
  struct Windows::Data::Json::IJsonObject *v17; // [rsp+20h] [rbp-99h] BYREF
  struct IInspectable *v18; // [rsp+28h] [rbp-91h] BYREF
  HSTRING v19; // [rsp+30h] [rbp-89h] BYREF
  HSTRING string; // [rsp+38h] [rbp-81h] BYREF
  HSTRING_HEADER pguid; // [rsp+40h] [rbp-79h] BYREF
  __int64 v22; // [rsp+58h] [rbp-61h]
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-59h] BYREF
  __int64 v24; // [rsp+78h] [rbp-41h]
  unsigned __int16 v25[40]; // [rsp+80h] [rbp-39h] BYREF

  *a3 = 0;
  v17 = 0;
  WindowsDeleteString(0);
  v19 = 0;
  WindowsDeleteString(0);
  string = 0;
  LanguageAndRegion = GetLanguageAndRegion(&string, &v19);
  if ( LanguageAndRegion >= 0 )
  {
    v22 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&pguid, L"Windows.Data.Json.JsonObject", 0x1Du, 0x1Cu);
    LanguageAndRegion = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                          v22,
                          &v17);
  }
  memset_0(v25, 0, sizeof(v25));
  if ( LanguageAndRegion >= 0 )
  {
    v7 = L"Purchased";
    if ( !a1 )
    {
      *(_OWORD *)&pguid.Reserved.Reserved1 = 0;
      LanguageAndRegion = CoCreateGuid((GUID *)&pguid);
      if ( LanguageAndRegion < 0 )
        goto LABEL_26;
      LanguageAndRegion = GUIDToString((const struct _GUID *)&pguid, v25, v8);
      if ( LanguageAndRegion < 0 )
        goto LABEL_26;
      v7 = L"CheckingOut";
      a1 = v25;
    }
    LanguageAndRegion = Json_SetNamedValue(v17, L"orderId", a1);
    if ( LanguageAndRegion >= 0 )
    {
      LanguageAndRegion = Json_SetNamedValue(v17, L"orderState", v7);
      if ( LanguageAndRegion >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        LanguageAndRegion = Json_SetNamedValue(v17, L"language", StringRawBuffer);
        if ( LanguageAndRegion >= 0 )
        {
          v10 = WindowsGetStringRawBuffer(v19, 0);
          LanguageAndRegion = Json_SetNamedValue(v17, L"market", v10);
          if ( LanguageAndRegion >= 0 )
          {
            v18 = 0;
            v22 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &pguid,
              L"Windows.Data.Json.JsonObject",
              0x1Du,
              0x1Cu);
            LanguageAndRegion = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                                  v22,
                                  &v18);
            if ( LanguageAndRegion >= 0 )
            {
              LanguageAndRegion = Json_SetNamedValue(
                                    (struct Windows::Data::Json::IJsonObject *)v18,
                                    L"client",
                                    L"StoreAgent");
              if ( LanguageAndRegion >= 0 )
              {
                pguid.Reserved.Reserved1 = 0;
                LanguageAndRegion = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::As<Windows::Data::Json::IJsonValue>(
                                      &v18,
                                      &pguid);
                if ( LanguageAndRegion >= 0 )
                {
                  v11 = v17;
                  v12 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, PVOID))(*(_QWORD *)v17 + 56LL);
                  Reserved1 = pguid.Reserved.Reserved1;
                  v24 = 0;
                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                    &hstringHeader,
                    L"clientContext",
                    0xEu,
                    0xDu);
                  LanguageAndRegion = v12(v11, v24, Reserved1);
                }
                Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&pguid);
              }
            }
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
            if ( LanguageAndRegion >= 0 )
            {
              if ( !a2 )
                goto LABEL_25;
              v18 = 0;
              v24 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"Windows.Data.Json.JsonObject",
                0x1Du,
                0x1Cu);
              LanguageAndRegion = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                                    v24,
                                    &v18);
              if ( LanguageAndRegion >= 0 )
              {
                LanguageAndRegion = Json_SetNamedValue(
                                      (struct Windows::Data::Json::IJsonObject *)v18,
                                      L"callerApplicationId",
                                      a2);
                if ( LanguageAndRegion >= 0 )
                {
                  WindowsDeleteString(0);
                  pguid.Reserved.Reserved1 = 0;
                  LanguageAndRegion = Json_Stringify(v18, (HSTRING *)&pguid);
                  if ( LanguageAndRegion >= 0 )
                  {
                    v14 = WindowsGetStringRawBuffer((HSTRING)pguid.Reserved.Reserved1, 0);
                    LanguageAndRegion = Json_SetNamedValue(v17, L"orderAdditionalMetadata", v14);
                  }
                  WindowsDeleteString((HSTRING)pguid.Reserved.Reserved1);
                }
              }
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
              if ( LanguageAndRegion >= 0 )
              {
LABEL_25:
                v15 = v17;
                v17 = 0;
                *a3 = v15;
              }
            }
          }
        }
      }
    }
  }
LABEL_26:
  WindowsDeleteString(v19);
  WindowsDeleteString(string);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v17);
  return (unsigned int)LanguageAndRegion;
}

```

## disassembly

```asm
0x18007cf24  push    rbp
0x18007cf26  push    rbx
0x18007cf27  push    rsi
0x18007cf28  push    rdi
0x18007cf29  push    r12
0x18007cf2b  push    r14
0x18007cf2d  push    r15
0x18007cf2f  lea     rbp, [rsp-27h]
0x18007cf34  sub     rsp, 0E0h
0x18007cf3b  mov     rax, cs:__security_cookie
0x18007cf42  xor     rax, rsp
0x18007cf45  mov     [rbp+57h+var_40], rax
0x18007cf49  mov     r15, r8
0x18007cf4c  mov     r14, rdx
0x18007cf4f  mov     rdi, rcx
0x18007cf52  xor     r12d, r12d
0x18007cf55  mov     [r8], r12
0x18007cf58  mov     [rsp+110h+var_F0], r12
0x18007cf5d  xor     ecx, ecx; string
0x18007cf5f  call    cs:__imp_WindowsDeleteString
0x18007cf65  mov     [rsp+110h+var_E0], r12
0x18007cf6a  xor     ecx, ecx; string
0x18007cf6c  call    cs:__imp_WindowsDeleteString
0x18007cf72  mov     [rsp+110h+string], r12
0x18007cf77  lea     rdx, [rsp+110h+var_E0]; HSTRING *
0x18007cf7c  lea     rcx, [rsp+110h+string]; HSTRING *
0x18007cf81  call    ?GetLanguageAndRegion@@YAJPEAPEAUHSTRING__@@0@Z; GetLanguageAndRegion(HSTRING__ * *,HSTRING__ * *)
0x18007cf86  mov     ebx, eax
0x18007cf88  test    eax, eax
0x18007cf8a  js      short loc_18007CFBA
0x18007cf8c  mov     [rbp+57h+var_B8], r12
0x18007cf90  lea     r9d, [r12+1Ch]; unsigned int
0x18007cf95  lea     r8d, [r12+1Dh]; unsigned int
0x18007cf9a  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18007cfa1  lea     rcx, [rbp+57h+pguid]; hstringHeader
0x18007cfa5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007cfaa  lea     rdx, [rsp+110h+var_F0]
0x18007cfaf  mov     rcx, [rbp+57h+var_B8]
0x18007cfb3  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18007cfb8  mov     ebx, eax
0x18007cfba  xor     edx, edx; Val
0x18007cfbc  lea     r8d, [rdx+50h]; Size
0x18007cfc0  lea     rcx, [rbp+57h+var_90]; void *
0x18007cfc4  call    memset_0
0x18007cfc9  test    ebx, ebx
0x18007cfcb  js      loc_18007D23E
0x18007cfd1  lea     rsi, aPurchased; "Purchased"
0x18007cfd8  test    rdi, rdi
0x18007cfdb  jnz     short loc_18007D01A
0x18007cfdd  xorps   xmm0, xmm0
0x18007cfe0  movups  xmmword ptr [rbp+57h+pguid], xmm0
0x18007cfe4  lea     rcx, [rbp+57h+pguid]; pguid
0x18007cfe8  call    cs:__imp_CoCreateGuid
0x18007cfee  mov     ebx, eax
0x18007cff0  test    eax, eax
0x18007cff2  js      loc_18007D23E
0x18007cff8  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x18007cffc  lea     rcx, [rbp+57h+pguid]; struct _GUID *
0x18007d000  call    ?GUIDToString@@YAJAEBU_GUID@@PEAG_K@Z; GUIDToString(_GUID const &,ushort *,unsigned __int64)
0x18007d005  mov     ebx, eax
0x18007d007  test    eax, eax
0x18007d009  js      loc_18007D23E
0x18007d00f  lea     rsi, aCheckingout; "CheckingOut"
0x18007d016  lea     rdi, [rbp+57h+var_90]
0x18007d01a  mov     r8, rdi; unsigned __int16 *
0x18007d01d  lea     rdx, aOrderid_0; "orderId"
0x18007d024  mov     rcx, [rsp+110h+var_F0]; struct Windows::Data::Json::IJsonObject *
0x18007d029  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18007d02e  mov     ebx, eax
0x18007d030  test    eax, eax
0x18007d032  js      loc_18007D23E
0x18007d038  mov     r8, rsi; unsigned __int16 *
0x18007d03b  lea     rdx, aOrderstate; "orderState"
0x18007d042  mov     rcx, [rsp+110h+var_F0]; struct Windows::Data::Json::IJsonObject *
0x18007d047  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18007d04c  mov     ebx, eax
0x18007d04e  test    eax, eax
0x18007d050  js      loc_18007D23E
0x18007d056  xor     edx, edx; length
0x18007d058  mov     rcx, [rsp+110h+string]; string
0x18007d05d  call    cs:__imp_WindowsGetStringRawBuffer
0x18007d063  mov     r8, rax; unsigned __int16 *
0x18007d066  lea     rdx, aLanguage; "language"
0x18007d06d  mov     rcx, [rsp+110h+var_F0]; struct Windows::Data::Json::IJsonObject *
0x18007d072  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18007d077  mov     ebx, eax
0x18007d079  test    eax, eax
0x18007d07b  js      loc_18007D23E
0x18007d081  xor     edx, edx; length
0x18007d083  mov     rcx, [rsp+110h+var_E0]; string
0x18007d088  call    cs:__imp_WindowsGetStringRawBuffer
0x18007d08e  mov     r8, rax; unsigned __int16 *
0x18007d091  lea     rdx, aMarket_0; "market"
0x18007d098  mov     rcx, [rsp+110h+var_F0]; struct Windows::Data::Json::IJsonObject *
0x18007d09d  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18007d0a2  mov     ebx, eax
0x18007d0a4  test    eax, eax
0x18007d0a6  js      loc_18007D23E
0x18007d0ac  mov     [rsp+110h+var_E8], r12
0x18007d0b1  mov     [rbp+57h+var_B8], r12
0x18007d0b5  mov     r9d, 1Ch; unsigned int
0x18007d0bb  lea     r8d, [r9+1]; unsigned int
0x18007d0bf  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18007d0c6  lea     rcx, [rbp+57h+pguid]; hstringHeader
0x18007d0ca  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007d0cf  lea     rdx, [rsp+110h+var_E8]
0x18007d0d4  mov     rcx, [rbp+57h+var_B8]
0x18007d0d8  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18007d0dd  mov     ebx, eax
0x18007d0df  test    eax, eax
0x18007d0e1  js      loc_18007D16A
0x18007d0e7  lea     r8, aStoreagent; "StoreAgent"
0x18007d0ee  lea     rdx, aClient; "client"
0x18007d0f5  mov     rcx, [rsp+110h+var_E8]; struct Windows::Data::Json::IJsonObject *
0x18007d0fa  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18007d0ff  mov     ebx, eax
0x18007d101  test    eax, eax
0x18007d103  js      short loc_18007D16A
0x18007d105  mov     qword ptr [rbp+57h+pguid], r12
0x18007d109  lea     rdx, [rbp+57h+pguid]
0x18007d10d  lea     rcx, [rsp+110h+var_E8]
0x18007d112  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18007d117  mov     ebx, eax
0x18007d119  test    eax, eax
0x18007d11b  js      short loc_18007D160
0x18007d11d  mov     rsi, [rsp+110h+var_F0]
0x18007d122  mov     rax, [rsi]
0x18007d125  mov     rdi, [rax+38h]
0x18007d129  mov     rbx, qword ptr [rbp+57h+pguid]
0x18007d12d  mov     [rbp+57h+var_98], r12
0x18007d131  mov     r9d, 0Dh; unsigned int
0x18007d137  lea     r8d, [r9+1]; unsigned int
0x18007d13b  lea     rdx, aClientcontext; "clientContext"
0x18007d142  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007d146  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007d14b  nop
0x18007d14c  mov     r8, rbx
0x18007d14f  mov     rdx, [rbp+57h+var_98]
0x18007d153  mov     rcx, rsi
0x18007d156  mov     rax, rdi
0x18007d159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d15e  mov     ebx, eax
0x18007d160  lea     rcx, [rbp+57h+pguid]
0x18007d164  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007d169  nop
0x18007d16a  lea     rcx, [rsp+110h+var_E8]
0x18007d16f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007d174  test    ebx, ebx
0x18007d176  js      loc_18007D23E
0x18007d17c  test    r14, r14
0x18007d17f  jz      loc_18007D231
0x18007d185  mov     [rsp+110h+var_E8], r12
0x18007d18a  mov     [rbp+57h+var_98], r12
0x18007d18e  mov     r9d, 1Ch; unsigned int
0x18007d194  lea     r8d, [r9+1]; unsigned int
0x18007d198  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18007d19f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007d1a3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007d1a8  lea     rdx, [rsp+110h+var_E8]
0x18007d1ad  mov     rcx, [rbp+57h+var_98]
0x18007d1b1  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18007d1b6  mov     ebx, eax
0x18007d1b8  test    eax, eax
0x18007d1ba  js      short loc_18007D223
0x18007d1bc  mov     r8, r14; unsigned __int16 *
0x18007d1bf  lea     rdx, aCallerapplicat_1; "callerApplicationId"
0x18007d1c6  mov     rcx, [rsp+110h+var_E8]; struct Windows::Data::Json::IJsonObject *
0x18007d1cb  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18007d1d0  mov     ebx, eax
0x18007d1d2  test    eax, eax
0x18007d1d4  js      short loc_18007D223
0x18007d1d6  xor     ecx, ecx; string
0x18007d1d8  call    cs:__imp_WindowsDeleteString
0x18007d1de  mov     qword ptr [rbp+57h+pguid], r12
0x18007d1e2  lea     rdx, [rbp+57h+pguid]; HSTRING *
0x18007d1e6  mov     rcx, [rsp+110h+var_E8]; struct IInspectable *
0x18007d1eb  call    ?Json_Stringify@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; Json_Stringify(IInspectable *,HSTRING__ * *)
0x18007d1f0  mov     ebx, eax
0x18007d1f2  test    eax, eax
0x18007d1f4  js      short loc_18007D218
0x18007d1f6  xor     edx, edx; length
0x18007d1f8  mov     rcx, qword ptr [rbp+57h+pguid]; string
0x18007d1fc  call    cs:__imp_WindowsGetStringRawBuffer
0x18007d202  mov     r8, rax; unsigned __int16 *
0x18007d205  lea     rdx, aOrderadditiona; "orderAdditionalMetadata"
0x18007d20c  mov     rcx, [rsp+110h+var_F0]; struct Windows::Data::Json::IJsonObject *
0x18007d211  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18007d216  mov     ebx, eax
0x18007d218  mov     rcx, qword ptr [rbp+57h+pguid]; string
0x18007d21c  call    cs:__imp_WindowsDeleteString
0x18007d222  nop
0x18007d223  lea     rcx, [rsp+110h+var_E8]
0x18007d228  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007d22d  test    ebx, ebx
0x18007d22f  js      short loc_18007D23E
0x18007d231  mov     rax, [rsp+110h+var_F0]
0x18007d236  mov     [rsp+110h+var_F0], r12
0x18007d23b  mov     [r15], rax
0x18007d23e  mov     rcx, [rsp+110h+var_E0]; string
0x18007d243  call    cs:__imp_WindowsDeleteString
0x18007d249  nop
0x18007d24a  mov     rcx, [rsp+110h+string]; string
0x18007d24f  call    cs:__imp_WindowsDeleteString
0x18007d255  nop
0x18007d256  lea     rcx, [rsp+110h+var_F0]
0x18007d25b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007d260  mov     eax, ebx
0x18007d262  mov     rcx, [rbp+57h+var_40]
0x18007d266  xor     rcx, rsp; StackCookie
0x18007d269  call    __security_check_cookie
0x18007d26e  add     rsp, 0E0h
0x18007d275  pop     r15
0x18007d277  pop     r14
0x18007d279  pop     r12
0x18007d27b  pop     rdi
0x18007d27c  pop     rsi
0x18007d27d  pop     rbx
0x18007d27e  pop     rbp
0x18007d27f  retn
```
