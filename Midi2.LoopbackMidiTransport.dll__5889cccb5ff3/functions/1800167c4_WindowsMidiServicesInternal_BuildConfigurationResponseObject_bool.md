# WindowsMidiServicesInternal::BuildConfigurationResponseObject(bool)

- ea: `0x1800167c4`
- end: `0x18001689a`
- name: `?BuildConfigurationResponseObject@WindowsMidiServicesInternal@@YA?AUJsonObject@Json@Data@Windows@winrt@@_N@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018710`

## callees

- `0x180014974`
- `0x1800152f8`
- `0x180016638`
- `0x1800167c4`
- `0x1800168a0`
- `0x1800183a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall WindowsMidiServicesInternal::BuildConfigurationResponseObject(__int64 *a1)
{
  _DWORD *v3; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v4[4]; // [rsp+30h] [rbp-20h] BYREF
  const unsigned __int16 *v5; // [rsp+40h] [rbp-10h]
  char *v6; // [rsp+70h] [rbp+20h] BYREF

  v6 = (char *)&qword_18005FA88;
  _InterlockedIncrement64(&qword_18005FA88);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::operator()(
      (__int64)a1,
      a1,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18005FA88);
  }
  else
  {
    _InterlockedDecrement64(&qword_18005FA88);
    v6 = (char *)`winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      a1,
      (__int64)a1,
      (void (__fastcall **)(__int64, __int64 *))&v6);
  }
  winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(&v6, 0);
  v4[0] = 1;
  v4[1] = 7;
  v5 = L"success";
  v3 = v4;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    (__int64 **)a1,
    (__int64 *)&v3,
    (__int64 *)&v6);
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v6);
  return a1;
}

```

## disassembly

```asm
0x1800167c4  mov     [rsp-8+arg_8], rbx
0x1800167c9  mov     [rsp-8+arg_0], rcx
0x1800167ce  push    rbp
0x1800167cf  mov     rbp, rsp
0x1800167d2  sub     rsp, 50h
0x1800167d6  mov     rbx, rcx
0x1800167d9  mov     [rbp+var_30], 0
0x1800167e0  lea     rax, qword_18005FA88
0x1800167e7  mov     [rbp+arg_10], rax
0x1800167eb  lock inc cs:qword_18005FA88
0x1800167f3  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, 0; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x1800167fb  jz      short loc_180016817
0x1800167fd  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x180016804  mov     rdx, rcx
0x180016807  call    ??R_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18001680c  nop
0x18001680d  lock dec cs:qword_18005FA88
0x180016815  jmp     short loc_180016836
0x180016817  lock dec cs:qword_18005FA88
0x18001681f  lea     rax, ?_lambda_invoker_cdecl_@_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@56@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180016826  mov     [rbp+arg_10], rax
0x18001682a  lea     r8, [rbp+arg_10]
0x18001682e  mov     rdx, rbx
0x180016831  call    ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x180016836  mov     [rbp+var_30], 3
0x18001683d  xor     edx, edx
0x18001683f  lea     rcx, [rbp+arg_10]; bool
0x180016843  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180016848  nop
0x180016849  mov     [rbp+var_20], 1
0x180016850  mov     [rbp+var_1C], 7
0x180016857  lea     rax, aSuccess; "success"
0x18001685e  mov     [rbp+var_10], rax
0x180016862  lea     rax, [rbp+var_20]
0x180016866  mov     [rbp+var_28], rax
0x18001686a  lea     r8, [rbp+arg_10]
0x18001686e  lea     rdx, [rbp+var_28]
0x180016872  mov     rcx, rbx
0x180016875  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001687a  nop
0x18001687b  cmp     [rbp+arg_10], 0
0x180016880  jz      short loc_18001688B
0x180016882  lea     rcx, [rbp+arg_10]
0x180016886  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001688b  mov     rax, rbx
0x18001688e  mov     rbx, [rsp+50h+arg_8]
0x180016893  add     rsp, 50h
0x180016897  pop     rbp
0x180016898  retn
```
