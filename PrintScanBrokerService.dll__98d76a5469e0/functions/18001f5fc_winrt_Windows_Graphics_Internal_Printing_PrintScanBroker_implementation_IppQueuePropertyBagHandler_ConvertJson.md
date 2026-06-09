# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertJsonToValueSet(winrt::hstring const &)

- ea: `0x18001f5fc`
- end: `0x18001f933`
- name: `?_ConvertJsonToValueSet@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUValueSet@Collections@Foundation@78@AEBUhstring@8@@Z`
- size: `823`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bad4`

## callees

- `0x180007a58`
- `0x18000fa48`
- `0x18000fb60`
- `0x1800115a4`
- `0x180012ef4`
- `0x1800135c0`
- `0x180015824`
- `0x180017700`
- `0x1800179f4`
- `0x180018224`
- `0x1800185b0`
- `0x180018ce8`
- `0x18001b7d4`
- `0x18001b828`
- `0x18001b944`
- `0x18001c7a4`
- `0x18001cfd4`
- `0x18001d228`
- `0x18001f5fc`
- `0x180048010`

## string_xrefs

- `0x18001f6d8`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
struct winrt::Windows::Foundation::Collections::ValueSet *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertJsonToValueSet(
        __int64 *a1,
        struct winrt::Windows::Foundation::Collections::ValueSet *a2,
        __int64 *a3)
{
  char v5; // al
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 **); // rcx
  int v7; // esi
  unsigned int v8; // esi
  __int64 v9; // r15
  struct IUnknown *v10; // rdx
  __int64 (__fastcall *v11)(__int64, void **); // rbx
  void **v12; // rax
  unsigned int v13; // eax
  void (__fastcall *v14)(__int64, __int64 *); // rdi
  __int64 (__fastcall *v15)(_QWORD, void **); // rbx
  struct IUnknown *v16; // rdx
  void **v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // eax
  const char *v21; // [rsp+30h] [rbp-69h]
  __int64 v22; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v23[8]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v25[8]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v26[8]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v27; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v28[8]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v29; // [rsp+70h] [rbp-29h] BYREF
  __int128 v30; // [rsp+78h] [rbp-21h]
  _BYTE v31[4]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v32[4]; // [rsp+94h] [rbp-5h] BYREF
  _BYTE v33[88]; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  void (__fastcall *v35)(__int64, __int64 *); // [rsp+110h] [rbp+77h] BYREF
  __int64 *v36; // [rsp+118h] [rbp+7Fh] BYREF

  v29 = *a3;
  v35 = (void (__fastcall *)(__int64, __int64 *))&v29;
  v36 = &qword_180060C68;
  _InterlockedIncrement64(&qword_180060C68);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
  {
    _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(
      &v35,
      v23,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_180060C68);
  }
  else
  {
    _InterlockedDecrement64(&qword_180060C68);
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_ &>(
      a1,
      (__int64)v23,
      (__int64)&v35);
  }
  LODWORD(v21) = 6;
  winrt::param::hstring::hstring((winrt::param::hstring *)v33, L"Version");
  v5 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
         v23,
         v33) != 1.0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xD3,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
    (const char *)0x83760002LL,
    v5,
    (bool)"Invalid version number in IPP Queue Property Bag!",
    v21);
  winrt::param::hstring::hstring((winrt::param::hstring *)v33, L"QueuePropertyBag");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
    v23,
    v28,
    v33);
  v35 = (void (__fastcall *)(__int64, __int64 *))&qword_180060C08;
  _InterlockedIncrement64(&qword_180060C08);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory> )
  {
    winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Foundation::Collections::ValueSet>(
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>,
      a2);
    v7 = 30;
    _InterlockedDecrement64(&qword_180060C08);
  }
  else
  {
    _InterlockedDecrement64(&qword_180060C08);
    v35 = (void (__fastcall *)(__int64, __int64 *))_lambda_f635e0c3324166f0c8ad227de6175e83_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Foundation::Collections::ValueSet (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v6,
      (__int64)a2,
      &v35);
    v7 = 14;
  }
  winrt::impl::get_begin_iterator<winrt::Windows::Data::Json::JsonObject,0>(&v22, (__int64)v28);
  v8 = v7 | 0x21;
  v27 = 0;
  v9 = v22;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v22, &v27) )
  {
    v35 = 0;
    LODWORD(v29) = 0;
    v30 = 0;
    v11 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v9 + 48LL);
    v12 = winrt::put_abi((winrt *)&v35, v10);
    v13 = v11(v9, v12);
    winrt::check_hresult(&v36, v13, &v29);
    winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
      &v35,
      v26);
    v24 = 0;
    v14 = v35;
    LODWORD(v29) = 0;
    v30 = 0;
    v15 = *(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)v35 + 56LL);
    v17 = winrt::put_abi((winrt *)&v24, v16);
    v18 = v15(v14, v17);
    winrt::check_hresult(v31, v18, &v29);
    winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(&v24, v25);
    v8 = v8 & 0xFFFFFD3F | 0x40;
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v24);
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_AddPropertyToValueSet(
      (winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *)a1,
      a2,
      (const struct winrt::hstring *)v26,
      (const struct winrt::Windows::Data::Json::JsonObject *)v25);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v25);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v26);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v35);
    LOBYTE(v35) = 0;
    LODWORD(v29) = 0;
    v30 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 64LL))(v9, &v35);
    winrt::check_hresult(v32, v19, &v29);
    if ( !(_BYTE)v35 )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
      v35 = 0;
      v9 = 0;
      v22 = 0;
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v35);
    }
  }
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v27);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v22);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v28);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v23);
  return a2;
}

```

## disassembly

```asm
0x18001f5fc  mov     [rsp-8+arg_0], rbx
0x18001f601  mov     [rsp-8+arg_8], rdx
0x18001f606  push    rbp
0x18001f607  push    rsi
0x18001f608  push    rdi
0x18001f609  push    r12
0x18001f60b  push    r13
0x18001f60d  push    r14
0x18001f60f  push    r15
0x18001f611  lea     rbp, [rsp-27h]
0x18001f616  sub     rsp, 0C0h
0x18001f61d  mov     r14, rdx
0x18001f620  mov     r12, rcx
0x18001f623  xor     r13d, r13d
0x18001f626  mov     dword ptr [rbp+57h+var_C0], r13d
0x18001f62a  mov     rax, [r8]
0x18001f62d  mov     [rbp+57h+var_80], rax
0x18001f631  lea     rax, [rbp+57h+var_80]
0x18001f635  mov     [rbp+57h+arg_10], rax
0x18001f639  lea     rax, qword_180060C68
0x18001f640  mov     [rbp+57h+arg_18], rax
0x18001f644  lock inc cs:qword_180060C68
0x18001f64c  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, r13; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001f653  jz      short loc_18001F674
0x18001f655  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001f65c  lea     rdx, [rbp+57h+var_B0]
0x18001f660  lea     rcx, [rbp+57h+arg_10]
0x18001f664  call    ??R_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18001f669  nop
0x18001f66a  lock dec cs:qword_180060C68
0x18001f672  jmp     short loc_18001F689
0x18001f674  lock dec cs:qword_180060C68
0x18001f67c  lea     r8, [rbp+57h+arg_10]
0x18001f680  lea     rdx, [rbp+57h+var_B0]
0x18001f684  call    ??$call@AEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@Z
0x18001f689  mov     dword ptr [rbp+57h+var_C0], 6
0x18001f690  lea     rdx, aVersion; "Version"
0x18001f697  lea     rcx, [rbp+57h+var_58]; this
0x18001f69b  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001f6a0  lea     rdx, [rbp+57h+var_58]
0x18001f6a4  lea     rcx, [rbp+57h+var_B0]
0x18001f6a8  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001f6ad  ucomisd xmm0, cs:__real@3ff0000000000000
0x18001f6b5  jp      short loc_18001F6BC
0x18001f6b7  mov     al, r13b
0x18001f6ba  jz      short loc_18001F6BE
0x18001f6bc  mov     al, 1
0x18001f6be  mov     rcx, [rbp+5Fh]; this
0x18001f6c2  lea     rdx, aInvalidVersion; "Invalid version number in IPP Queue Pro"...
0x18001f6c9  mov     qword ptr [rsp+0F0h+var_C8], rdx; bool
0x18001f6ce  mov     [rsp+0F0h+var_D0], al; char
0x18001f6d2  mov     r9d, 83760002h; char *
0x18001f6d8  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001f6df  mov     edx, 0D3h; void *
0x18001f6e4  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001f6e9  lea     rdx, aQueuepropertyb; "QueuePropertyBag"
0x18001f6f0  lea     rcx, [rbp+57h+var_58]; this
0x18001f6f4  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001f6f9  lea     r8, [rbp+57h+var_58]
0x18001f6fd  lea     rdx, [rbp+57h+var_88]
0x18001f701  lea     rcx, [rbp+57h+var_B0]
0x18001f705  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x18001f70a  nop
0x18001f70b  lea     rax, qword_180060C08
0x18001f712  mov     [rbp+57h+arg_10], rax
0x18001f716  lock inc cs:qword_180060C08
0x18001f71e  cmp     cs:??$factory_cache_entry_v@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@3U?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@12@A, r13; factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>
0x18001f725  jz      short loc_18001F745
0x18001f727  mov     rdx, r14
0x18001f72a  lea     rcx, ??$factory_cache_entry_v@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@3U?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@12@A; factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>
0x18001f731  call    ??$ActivateInstance@UValueSet@Collections@Foundation@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUValueSet@Collections@123@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Foundation::Collections::ValueSet>(void)
0x18001f736  mov     esi, 1Eh
0x18001f73b  lock dec cs:qword_180060C08
0x18001f743  jmp     short loc_18001F769
0x18001f745  lock dec cs:qword_180060C08
0x18001f74d  lea     rax, ?_lambda_invoker_cdecl_@_lambda_f635e0c3324166f0c8ad227de6175e83_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_f635e0c3324166f0c8ad227de6175e83_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x18001f754  mov     [rbp+57h+arg_10], rax
0x18001f758  lea     r8, [rbp+57h+arg_10]
0x18001f75c  mov     rdx, r14
0x18001f75f  call    ??$call@P6A?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUIActivationFactory@345@@Z@?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUValueSet@Collections@Foundation@Windows@2@AEBUIActivationFactory@562@@Z@Z
0x18001f764  mov     esi, 0Eh
0x18001f769  or      esi, 1
0x18001f76c  mov     dword ptr [rbp+57h+var_C0], esi
0x18001f76f  lea     rdx, [rbp+57h+var_88]
0x18001f773  lea     rcx, [rbp+57h+var_B8]
0x18001f777  call    ??$get_begin_iterator@UJsonObject@Json@Data@Windows@winrt@@$0A@@impl@winrt@@YA?AU?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@1@AEBUJsonObject@Json@Data@51@@Z; winrt::impl::get_begin_iterator<winrt::Windows::Data::Json::JsonObject,0>(winrt::Windows::Data::Json::JsonObject const &)
0x18001f77c  or      esi, 20h
0x18001f77f  mov     [rbp+57h+var_90], r13
0x18001f783  mov     r15, [rbp+57h+var_B8]
0x18001f787  lea     rdx, [rbp+57h+var_90]
0x18001f78b  lea     rcx, [rbp+57h+var_B8]
0x18001f78f  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001f794  test    al, al
0x18001f796  jnz     loc_18001F8ED
0x18001f79c  mov     [rbp+57h+arg_10], r13
0x18001f7a0  bts     esi, 7
0x18001f7a4  mov     dword ptr [rbp+57h+var_C0], esi
0x18001f7a7  mov     dword ptr [rbp+57h+var_80], r13d
0x18001f7ab  xorps   xmm0, xmm0
0x18001f7ae  movdqu  [rbp+57h+var_78], xmm0
0x18001f7b3  mov     rax, [r15]
0x18001f7b6  mov     rbx, [rax+30h]
0x18001f7ba  lea     rcx, [rbp+57h+arg_10]; this
0x18001f7be  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18001f7c3  mov     rdx, rax
0x18001f7c6  mov     rcx, r15
0x18001f7c9  mov     rax, rbx
0x18001f7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7d1  lea     r8, [rbp+57h+var_80]
0x18001f7d5  mov     edx, eax
0x18001f7d7  lea     rcx, [rbp+57h+arg_18]
0x18001f7db  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f7e0  btr     esi, 7
0x18001f7e4  or      esi, 40h
0x18001f7e7  mov     dword ptr [rbp+57h+var_C0], esi
0x18001f7ea  lea     rdx, [rbp+57h+var_98]
0x18001f7ee  lea     rcx, [rbp+57h+arg_10]
0x18001f7f2  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x18001f7f7  nop
0x18001f7f8  mov     [rbp+57h+var_A8], r13
0x18001f7fc  bts     esi, 9
0x18001f800  mov     dword ptr [rbp+57h+var_C0], esi
0x18001f803  mov     rdi, [rbp+57h+arg_10]
0x18001f807  mov     dword ptr [rbp+57h+var_80], r13d
0x18001f80b  xorps   xmm0, xmm0
0x18001f80e  movdqu  [rbp+57h+var_78], xmm0
0x18001f813  mov     rax, [rdi]
0x18001f816  mov     rbx, [rax+38h]
0x18001f81a  lea     rcx, [rbp+57h+var_A8]; this
0x18001f81e  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18001f823  mov     rdx, rax
0x18001f826  mov     rcx, rdi
0x18001f829  mov     rax, rbx
0x18001f82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f831  lea     r8, [rbp+57h+var_80]
0x18001f835  mov     edx, eax
0x18001f837  lea     rcx, [rbp+57h+var_60]
0x18001f83b  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f840  lea     rdx, [rbp+57h+var_A0]
0x18001f844  lea     rcx, [rbp+57h+var_A8]
0x18001f848  call    ?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)
0x18001f84d  nop
0x18001f84e  btr     esi, 9
0x18001f852  mov     dword ptr [rbp+57h+var_C0], esi
0x18001f855  lea     rcx, [rbp+57h+var_A8]; this
0x18001f859  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f85e  lea     r9, [rbp+57h+var_A0]; struct winrt::Windows::Data::Json::JsonObject *
0x18001f862  lea     r8, [rbp+57h+var_98]; struct winrt::hstring *
0x18001f866  mov     rdx, r14; struct winrt::Windows::Foundation::Collections::ValueSet *
0x18001f869  mov     rcx, r12; this
0x18001f86c  call    ?_AddPropertyToValueSet@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAAXAEAUValueSet@Collections@Foundation@78@AEBUhstring@8@AEBUJsonObject@Json@Data@78@@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_AddPropertyToValueSet(winrt::Windows::Foundation::Collections::ValueSet &,winrt::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x18001f871  nop
0x18001f872  lea     rcx, [rbp+57h+var_A0]; this
0x18001f876  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f87b  nop
0x18001f87c  lea     rcx, [rbp+57h+var_98]
0x18001f880  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001f885  nop
0x18001f886  lea     rcx, [rbp+57h+arg_10]; this
0x18001f88a  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f88f  mov     byte ptr [rbp+57h+arg_10], r13b
0x18001f893  mov     dword ptr [rbp+57h+var_80], r13d
0x18001f897  xorps   xmm0, xmm0
0x18001f89a  movdqu  [rbp+57h+var_78], xmm0
0x18001f89f  mov     rax, [r15]
0x18001f8a2  lea     rdx, [rbp+57h+arg_10]
0x18001f8a6  mov     rcx, r15
0x18001f8a9  mov     rax, [rax+40h]
0x18001f8ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8b2  lea     r8, [rbp+57h+var_80]
0x18001f8b6  mov     edx, eax
0x18001f8b8  lea     rcx, [rbp+57h+var_5C]
0x18001f8bc  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f8c1  cmp     byte ptr [rbp+57h+arg_10], r13b
0x18001f8c5  jnz     loc_18001F787
0x18001f8cb  lea     rcx, [rbp+57h+var_B8]
0x18001f8cf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f8d4  mov     [rbp+57h+arg_10], r13
0x18001f8d8  mov     r15, r13
0x18001f8db  mov     [rbp+57h+var_B8], r13
0x18001f8df  lea     rcx, [rbp+57h+arg_10]; this
0x18001f8e3  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f8e8  jmp     loc_18001F787
0x18001f8ed  lea     rcx, [rbp+57h+var_90]; this
0x18001f8f1  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f8f6  nop
0x18001f8f7  lea     rcx, [rbp+57h+var_B8]; this
0x18001f8fb  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f900  nop
0x18001f901  lea     rcx, [rbp+57h+var_88]; this
0x18001f905  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f90a  nop
0x18001f90b  lea     rcx, [rbp+57h+var_B0]; this
0x18001f90f  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f914  mov     rax, r14
0x18001f917  mov     rbx, [rsp+0F0h+arg_0]
0x18001f91f  add     rsp, 0C0h
0x18001f926  pop     r15
0x18001f928  pop     r14
0x18001f92a  pop     r13
0x18001f92c  pop     r12
0x18001f92e  pop     rdi
0x18001f92f  pop     rsi
0x18001f930  pop     rbp
0x18001f931  retn
```
