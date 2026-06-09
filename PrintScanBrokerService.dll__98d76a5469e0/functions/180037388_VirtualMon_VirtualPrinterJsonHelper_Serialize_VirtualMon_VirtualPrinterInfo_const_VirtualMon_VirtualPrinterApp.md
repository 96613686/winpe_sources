# VirtualMon::VirtualPrinterJsonHelper::Serialize(VirtualMon::VirtualPrinterInfo const &,VirtualMon::VirtualPrinterAppInfo const &)

- ea: `0x180037388`
- end: `0x180037ac4`
- name: `?Serialize@VirtualPrinterJsonHelper@VirtualMon@@SA?AUhstring@winrt@@AEBUVirtualPrinterInfo@2@AEBUVirtualPrinterAppInfo@2@@Z`
- size: `1852`
- prototype: `void (__fastcall ***__fastcall(void (__fastcall ***)(_QWORD, __int64 *, _QWORD), __int64, __int64))(_QWORD, __int64 *, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003666c`

## callees

- `0x180007a58`
- `0x180018134`
- `0x1800181ac`
- `0x180018224`
- `0x1800198e8`
- `0x18001a69c`
- `0x18001cc68`
- `0x18001ce7c`
- `0x180026b40`
- `0x180036270`
- `0x180037388`
- `0x180048010`

## string_xrefs

- `0x1800374ed`: `PrinterUri`
- `0x180037537`: `PdcFilePath`
- `0x1800375cb`: `PdrFilePath`
- `0x18003794d`: `AppSid`
- `0x180037997`: `UserSid`

## pseudocode

```c
void (__fastcall ***__fastcall VirtualMon::VirtualPrinterJsonHelper::Serialize(
        void (__fastcall ***a1)(_QWORD, __int64 *, _QWORD),
        __int64 a2,
        __int64 a3))(_QWORD, __int64 *, _QWORD)
{
  __int64 StringValue; // rbx
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rbx
  __int64 v22; // rbx
  __int64 v23; // rbx
  __int64 v24; // rbx
  __int64 v25; // rbx
  _BYTE v27[32]; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v28[32]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v29; // [rsp+60h] [rbp-9h] BYREF
  void (__fastcall ***v30)(_QWORD, __int64 *, _QWORD); // [rsp+68h] [rbp-1h] BYREF
  __int64 v31; // [rsp+70h] [rbp+7h] BYREF
  __int64 v32; // [rsp+78h] [rbp+Fh] BYREF
  char v33[8]; // [rsp+88h] [rbp+1Fh] BYREF
  _BYTE v34[48]; // [rsp+90h] [rbp+27h] BYREF
  void (__fastcall ***v35)(_QWORD, __int64 *, _QWORD); // [rsp+D0h] [rbp+67h] BYREF
  void (__fastcall ***v36)(_QWORD, __int64 *, _QWORD); // [rsp+D8h] [rbp+6Fh] BYREF
  void (__fastcall ***v37)(_QWORD, __int64 *, __int64 *); // [rsp+E0h] [rbp+77h] BYREF
  char v38; // [rsp+E8h] [rbp+7Fh] BYREF

  v35 = a1;
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v35);
  winrt::param::hstring::hstring(v28, a2);
  StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v27, L"PortName");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v27,
    StringValue);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 32);
  v7 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"AppEntryPoint");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v7);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 64);
  v8 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"DisplayName");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v8);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 96);
  v9 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"DisplayNameUrl");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v9);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 128);
  v10 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"PrinterUri");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v10);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 192);
  v11 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"PdcFilePath");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v11);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 160);
  v12 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"PdcFileResource");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v12);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 256);
  v13 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"PdrFilePath");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v13);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 224);
  v14 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"PdrFileResource");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v14);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 288);
  v15 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"PreferredInputFormat");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v15);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a2 + 320);
  v16 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"OutputFileTypes");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v28,
    v16);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::Windows::Data::Json::JsonArray::JsonArray((winrt::Windows::Data::Json::JsonArray *)&v30);
  v17 = **(_QWORD **)(a2 + 352);
  v32 = v17;
  while ( !*(_BYTE *)(v17 + 25) )
  {
    v18 = v17 + 32;
    winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v37);
    winrt::param::hstring::hstring(v27, v18);
    v19 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v33);
    winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"FormatMimeType");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v37,
      v28,
      v19);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v33);
    winrt::param::hstring::hstring(v27, v18 + 32);
    v20 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v34);
    winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"MaxSupportedVersion");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v37,
      v28,
      v20);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v34);
    if ( v37 )
    {
      v31 = 0;
      (**v37)(v37, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v31);
      v29 = v31;
    }
    else
    {
      v29 = 0;
    }
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
      &v30,
      &v29);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v29);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(&v32);
    v17 = v32;
  }
  v37 = 0;
  if ( v30 )
    (**v30)(v30, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v27, L"SupportedFormats");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v27,
    &v37);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v36);
  winrt::param::hstring::hstring(v27, a3);
  v21 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"AppAumid");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v36,
    v28,
    v21);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a3 + 32);
  v22 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"AppPackageFamilyName");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v36,
    v28,
    v22);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a3 + 64);
  v23 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"AppPackageFullName");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v36,
    v28,
    v23);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a3 + 96);
  v24 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"AppSid");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v36,
    v28,
    v24);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::param::hstring::hstring(v27, a3 + 128);
  v25 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"UserSid");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v36,
    v28,
    v25);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v38);
  v37 = 0;
  if ( v35 )
    (**v35)(v35, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v27, L"VirtualPrinterInfo");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v38,
    v27,
    &v37);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  v37 = 0;
  if ( v36 )
    (**v36)(v36, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v37);
  winrt::param::hstring::hstring((winrt::param::hstring *)v27, L"AppInfo");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v38,
    v27,
    &v37);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v37);
  winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(&v38, a1);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v38);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v36);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v30);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v35);
  return a1;
}

```

## disassembly

```asm
0x180037388  mov     [rsp-8+arg_0], rcx
0x18003738d  push    rbp
0x18003738e  push    rbx
0x18003738f  push    rsi
0x180037390  push    rdi
0x180037391  push    r14
0x180037393  lea     rbp, [rsp-37h]
0x180037398  sub     rsp, 0A0h
0x18003739f  mov     rsi, r8
0x1800373a2  mov     rdi, rdx
0x1800373a5  mov     r14, rcx
0x1800373a8  lea     rcx, [rbp+57h+arg_0]; this
0x1800373ac  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800373b1  nop
0x1800373b2  mov     rdx, rdi
0x1800373b5  lea     rcx, [rbp+57h+var_80]
0x1800373b9  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800373be  lea     rdx, [rbp+57h+var_80]
0x1800373c2  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x1800373c6  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800373cb  mov     rbx, rax
0x1800373ce  lea     rdx, aPortname; "PortName"
0x1800373d5  lea     rcx, [rbp+57h+var_A0]; this
0x1800373d9  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800373de  mov     r8, rbx
0x1800373e1  lea     rdx, [rbp+57h+var_A0]
0x1800373e5  lea     rcx, [rbp+57h+arg_0]
0x1800373e9  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800373ee  nop
0x1800373ef  lea     rcx, [rbp+57h+arg_10]; this
0x1800373f3  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800373f8  lea     rdx, [rdi+20h]
0x1800373fc  lea     rcx, [rbp+57h+var_A0]
0x180037400  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180037405  lea     rdx, [rbp+57h+var_A0]
0x180037409  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x18003740d  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180037412  mov     rbx, rax
0x180037415  lea     rdx, aAppentrypoint; "AppEntryPoint"
0x18003741c  lea     rcx, [rbp+57h+var_80]; this
0x180037420  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180037425  mov     r8, rbx
0x180037428  lea     rdx, [rbp+57h+var_80]
0x18003742c  lea     rcx, [rbp+57h+arg_0]
0x180037430  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180037435  nop
0x180037436  lea     rcx, [rbp+57h+arg_10]; this
0x18003743a  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18003743f  lea     rdx, [rdi+40h]
0x180037443  lea     rcx, [rbp+57h+var_A0]
0x180037447  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18003744c  lea     rdx, [rbp+57h+var_A0]
0x180037450  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x180037454  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180037459  mov     rbx, rax
0x18003745c  lea     rdx, aDisplayname; "DisplayName"
0x180037463  lea     rcx, [rbp+57h+var_80]; this
0x180037467  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18003746c  mov     r8, rbx
0x18003746f  lea     rdx, [rbp+57h+var_80]
0x180037473  lea     rcx, [rbp+57h+arg_0]
0x180037477  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18003747c  nop
0x18003747d  lea     rcx, [rbp+57h+arg_10]; this
0x180037481  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180037486  lea     rdx, [rdi+60h]
0x18003748a  lea     rcx, [rbp+57h+var_A0]
0x18003748e  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180037493  lea     rdx, [rbp+57h+var_A0]
0x180037497  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x18003749b  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800374a0  mov     rbx, rax
0x1800374a3  lea     rdx, aDisplaynameurl; "DisplayNameUrl"
0x1800374aa  lea     rcx, [rbp+57h+var_80]; this
0x1800374ae  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800374b3  mov     r8, rbx
0x1800374b6  lea     rdx, [rbp+57h+var_80]
0x1800374ba  lea     rcx, [rbp+57h+arg_0]
0x1800374be  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800374c3  nop
0x1800374c4  lea     rcx, [rbp+57h+arg_10]; this
0x1800374c8  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800374cd  lea     rdx, [rdi+80h]
0x1800374d4  lea     rcx, [rbp+57h+var_A0]
0x1800374d8  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800374dd  lea     rdx, [rbp+57h+var_A0]
0x1800374e1  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x1800374e5  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800374ea  mov     rbx, rax
0x1800374ed  lea     rdx, aPrinteruri; "PrinterUri"
0x1800374f4  lea     rcx, [rbp+57h+var_80]; this
0x1800374f8  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800374fd  mov     r8, rbx
0x180037500  lea     rdx, [rbp+57h+var_80]
0x180037504  lea     rcx, [rbp+57h+arg_0]
0x180037508  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18003750d  nop
0x18003750e  lea     rcx, [rbp+57h+arg_10]; this
0x180037512  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180037517  lea     rdx, [rdi+0C0h]
0x18003751e  lea     rcx, [rbp+57h+var_A0]
0x180037522  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180037527  lea     rdx, [rbp+57h+var_A0]
0x18003752b  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x18003752f  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180037534  mov     rbx, rax
0x180037537  lea     rdx, aPdcfilepath; "PdcFilePath"
0x18003753e  lea     rcx, [rbp+57h+var_80]; this
0x180037542  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180037547  mov     r8, rbx
0x18003754a  lea     rdx, [rbp+57h+var_80]
0x18003754e  lea     rcx, [rbp+57h+arg_0]
0x180037552  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180037557  nop
0x180037558  lea     rcx, [rbp+57h+arg_10]; this
0x18003755c  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180037561  lea     rdx, [rdi+0A0h]
0x180037568  lea     rcx, [rbp+57h+var_A0]
0x18003756c  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180037571  lea     rdx, [rbp+57h+var_A0]
0x180037575  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x180037579  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18003757e  mov     rbx, rax
0x180037581  lea     rdx, aPdcfileresourc; "PdcFileResource"
0x180037588  lea     rcx, [rbp+57h+var_80]; this
0x18003758c  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180037591  mov     r8, rbx
0x180037594  lea     rdx, [rbp+57h+var_80]
0x180037598  lea     rcx, [rbp+57h+arg_0]
0x18003759c  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800375a1  nop
0x1800375a2  lea     rcx, [rbp+57h+arg_10]; this
0x1800375a6  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800375ab  lea     rdx, [rdi+100h]
0x1800375b2  lea     rcx, [rbp+57h+var_A0]
0x1800375b6  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800375bb  lea     rdx, [rbp+57h+var_A0]
0x1800375bf  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x1800375c3  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800375c8  mov     rbx, rax
0x1800375cb  lea     rdx, aPdrfilepath; "PdrFilePath"
0x1800375d2  lea     rcx, [rbp+57h+var_80]; this
0x1800375d6  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800375db  mov     r8, rbx
0x1800375de  lea     rdx, [rbp+57h+var_80]
0x1800375e2  lea     rcx, [rbp+57h+arg_0]
0x1800375e6  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800375eb  nop
0x1800375ec  lea     rcx, [rbp+57h+arg_10]; this
0x1800375f0  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800375f5  lea     rdx, [rdi+0E0h]
0x1800375fc  lea     rcx, [rbp+57h+var_A0]
0x180037600  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180037605  lea     rdx, [rbp+57h+var_A0]
0x180037609  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x18003760d  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180037612  mov     rbx, rax
0x180037615  lea     rdx, aPdrfileresourc; "PdrFileResource"
0x18003761c  lea     rcx, [rbp+57h+var_80]; this
0x180037620  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180037625  mov     r8, rbx
0x180037628  lea     rdx, [rbp+57h+var_80]
0x18003762c  lea     rcx, [rbp+57h+arg_0]
0x180037630  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180037635  nop
0x180037636  lea     rcx, [rbp+57h+arg_10]; this
0x18003763a  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18003763f  lea     rdx, [rdi+120h]
0x180037646  lea     rcx, [rbp+57h+var_A0]
0x18003764a  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18003764f  lea     rdx, [rbp+57h+var_A0]
0x180037653  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x180037657  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18003765c  mov     rbx, rax
0x18003765f  lea     rdx, aPreferredinput; "PreferredInputFormat"
0x180037666  lea     rcx, [rbp+57h+var_80]; this
0x18003766a  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18003766f  mov     r8, rbx
0x180037672  lea     rdx, [rbp+57h+var_80]
0x180037676  lea     rcx, [rbp+57h+arg_0]
0x18003767a  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18003767f  nop
0x180037680  lea     rcx, [rbp+57h+arg_10]; this
0x180037684  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180037689  lea     rdx, [rdi+140h]
0x180037690  lea     rcx, [rbp+57h+var_A0]
0x180037694  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180037699  lea     rdx, [rbp+57h+var_A0]
0x18003769d  lea     rcx, [rbp+57h+arg_10]; struct winrt::param::hstring *
0x1800376a1  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800376a6  mov     rbx, rax
0x1800376a9  lea     rdx, aOutputfiletype; "OutputFileTypes"
0x1800376b0  lea     rcx, [rbp+57h+var_80]; this
0x1800376b4  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800376b9  mov     r8, rbx
0x1800376bc  lea     rdx, [rbp+57h+var_80]
0x1800376c0  lea     rcx, [rbp+57h+arg_0]
0x1800376c4  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800376c9  nop
0x1800376ca  lea     rcx, [rbp+57h+arg_10]; this
0x1800376ce  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800376d3  lea     rcx, [rbp+57h+var_58]; this
0x1800376d7  call    ??0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonArray::JsonArray(void)
0x1800376dc  nop
0x1800376dd  mov     rax, [rdi+160h]
0x1800376e4  mov     rax, [rax]
0x1800376e7  mov     [rbp+57h+var_48], rax
0x1800376eb  cmp     byte ptr [rax+19h], 0
0x1800376ef  jnz     loc_1800377F8
0x1800376f5  lea     rdi, [rax+20h]
0x1800376f9  lea     rcx, [rbp+57h+arg_10]; this
0x1800376fd  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x180037702  nop
0x180037703  mov     rdx, rdi
0x180037706  lea     rcx, [rbp+57h+var_A0]
0x18003770a  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18003770f  lea     rdx, [rbp+57h+var_A0]
0x180037713  lea     rcx, [rbp+57h+var_38]; struct winrt::param::hstring *
0x180037717  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18003771c  mov     rbx, rax
0x18003771f  lea     rdx, aFormatmimetype; "FormatMimeType"
0x180037726  lea     rcx, [rbp+57h+var_80]; this
0x18003772a  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18003772f  mov     r8, rbx
0x180037732  lea     rdx, [rbp+57h+var_80]
0x180037736  lea     rcx, [rbp+57h+arg_10]
0x18003773a  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18003773f  nop
0x180037740  lea     rcx, [rbp+57h+var_38]; this
0x180037744  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180037749  lea     rdx, [rdi+20h]
0x18003774d  lea     rcx, [rbp+57h+var_A0]
0x180037751  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180037756  lea     rdx, [rbp+57h+var_A0]
0x18003775a  lea     rcx, [rbp+57h+var_30]; struct winrt::param::hstring *
0x18003775e  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180037763  mov     rbx, rax
0x180037766  lea     rdx, aMaxsupportedve; "MaxSupportedVersion"
0x18003776d  lea     rcx, [rbp+57h+var_80]; this
0x180037771  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180037776  mov     r8, rbx
0x180037779  lea     rdx, [rbp+57h+var_80]
0x18003777d  lea     rcx, [rbp+57h+arg_10]
0x180037781  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180037786  nop
0x180037787  lea     rcx, [rbp+57h+var_30]; this
0x18003778b  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180037790  mov     rcx, [rbp+57h+arg_10]
0x180037794  test    rcx, rcx
0x180037797  jnz     short loc_18003779F
0x180037799  mov     [rbp+57h+var_60], rcx
0x18003779d  jmp     short loc_1800377C5
0x18003779f  mov     [rbp+57h+var_50], 0
0x1800377a7  mov     rax, [rcx]
0x1800377aa  lea     r8, [rbp+57h+var_50]
0x1800377ae  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x1800377b5  mov     rax, [rax]
0x1800377b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377bd  mov     rax, [rbp+57h+var_50]
0x1800377c1  mov     [rbp+57h+var_60], rax
0x1800377c5  lea     rdx, [rbp+57h+var_60]
0x1800377c9  lea     rcx, [rbp+57h+var_58]
0x1800377cd  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(winrt::Windows::Data::Json::IJsonValue const &)
0x1800377d2  nop
0x1800377d3  lea     rcx, [rbp+57h+var_60]; this
0x1800377d7  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800377dc  nop
0x1800377dd  lea     rcx, [rbp+57h+arg_10]; this
0x1800377e1  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800377e6  lea     rcx, [rbp+57h+var_48]
0x1800377ea  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x1800377ef  mov     rax, [rbp+57h+var_48]
0x1800377f3  jmp     loc_1800376EB
0x1800377f8  mov     rcx, [rbp+57h+var_58]
0x1800377fc  mov     [rbp+57h+arg_10], 0
0x180037804  test    rcx, rcx
0x180037807  jz      short loc_180037827
0x180037809  mov     rax, [rcx]
0x18003780c  lea     r8, [rbp+57h+arg_10]
0x180037810  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x180037817  mov     rax, [rax]
0x18003781a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003781f  mov     rax, [rbp+57h+arg_10]
0x180037823  mov     [rbp+57h+arg_10], rax
0x180037827  lea     rdx, aSupportedforma; "SupportedFormats"
0x18003782e  lea     rcx, [rbp+57h+var_A0]; this
0x180037832  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180037837  lea     r8, [rbp+57h+arg_10]
0x18003783b  lea     rdx, [rbp+57h+var_A0]
0x18003783f  lea     rcx, [rbp+57h+arg_0]
0x180037843  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180037848  nop
0x180037849  lea     rcx, [rbp+57h+arg_10]; this
0x18003784d  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180037852  lea     rcx, [rbp+57h+arg_8]; this
0x180037856  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18003785b  nop
0x18003785c  mov     rdx, rsi
0x18003785f  lea     rcx, [rbp+57h+var_A0]
0x180037863  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
  ... truncated ...
```
