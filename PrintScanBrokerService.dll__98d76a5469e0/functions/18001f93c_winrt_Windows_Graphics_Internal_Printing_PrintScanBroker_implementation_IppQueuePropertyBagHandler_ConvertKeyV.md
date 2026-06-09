# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertKeyValuePairsToJson(winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>> const &)

- ea: `0x18001f93c`
- end: `0x18001fd35`
- name: `?_ConvertKeyValuePairsToJson@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUhstring@8@AEBU?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@78@@Z`
- size: `1017`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cce4`

## callees

- `0x180007a58`
- `0x18000fa48`
- `0x18000fb60`
- `0x1800115a4`
- `0x180012ef4`
- `0x18001793c`
- `0x1800181ac`
- `0x180018224`
- `0x1800185b0`
- `0x18001a190`
- `0x18001c7a4`
- `0x18001cc68`
- `0x18001ce7c`
- `0x18001cfb4`
- `0x18001cfd4`
- `0x18001d130`
- `0x18001f93c`
- `0x18001fd3c`
- `0x180048010`

## string_xrefs

- `0x18001fa27`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18001fcea`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18001fd05`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18001fd20`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertKeyValuePairsToJson(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  double v3; // xmm0_8
  int v6; // r12d
  unsigned int v7; // r13d
  __int64 v8; // r14
  struct IUnknown *v9; // rdx
  int v10; // r13d
  __int64 (__fastcall *v11)(__int64, void **); // rbx
  void **v12; // rax
  unsigned int v13; // eax
  struct IUnknownVtbl *lpVtbl; // rcx
  unsigned int v15; // eax
  __int64 NumberValue; // rbx
  int v18; // [rsp+20h] [rbp-59h]
  const char *v19; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-41h]
  __int64 v21; // [rsp+40h] [rbp-39h] BYREF
  const char *v22; // [rsp+48h] [rbp-31h] BYREF
  void (__fastcall ***v23)(_QWORD, __int64 *, const char **); // [rsp+50h] [rbp-29h] BYREF
  struct IUnknown v24; // [rsp+58h] [rbp-21h] BYREF
  struct IUnknown v25; // [rsp+60h] [rbp-19h] BYREF
  __int64 v26; // [rsp+68h] [rbp-11h] BYREF
  __int64 v27; // [rsp+70h] [rbp-9h] BYREF
  __int64 v28; // [rsp+78h] [rbp-1h] BYREF
  __int128 v29; // [rsp+80h] [rbp+7h]
  _BYTE v30[4]; // [rsp+98h] [rbp+1Fh] BYREF
  _BYTE v31[4]; // [rsp+9Ch] [rbp+23h] BYREF
  struct IUnknown v32[6]; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v35; // [rsp+F8h] [rbp+7Fh] BYREF

  v20 = 0;
  v35 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a3, &v35) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)0x80070057LL,
      v18);
  v6 = 0;
  winrt::Windows::Data::Json::JsonObject::JsonObject(&v25);
  winrt::impl::get_begin_iterator<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,0>(
    &v21,
    a3);
  v7 = 2;
  v27 = 0;
  v8 = v21;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v21, &v27) )
  {
    v35 = 0;
    v10 = v7 | 8;
    v20 = v10;
    LODWORD(v28) = 0;
    v29 = 0;
    v11 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v8 + 48LL);
    v12 = winrt::put_abi((winrt *)&v35, v9);
    v13 = v11(v8, v12);
    winrt::check_hresult(v30, v13, &v28);
    v20 = v10 & 0xFFFFFFF7;
    v7 = v10 & 0xFFFFFFF3 | 4;
    if ( !v35 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
        (const char *)0x80070057LL,
        v18);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)0x80070057LL,
      (unsigned int)++v6 > 0xC8,
      (bool)"Number of properties exceeds the maximum allowed limit!",
      v19);
    winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
      &v35,
      &v26);
    winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Value(
      &v35,
      &v23);
    v19 = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v23, &v19) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEE,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
        (const char *)0x83760002LL,
        v18);
    if ( v23 )
    {
      v19 = 0;
      (**v23)(v23, winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, &v19);
      v22 = v19;
    }
    else
    {
      v22 = 0;
    }
    v19 = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v22, &v19) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
        (const char *)0x80070057LL,
        v18);
    lpVtbl = winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_CreateJsonObjectFromProperty(
               a1,
               v32,
               (__int64 *)&v22)->lpVtbl;
    v19 = 0;
    if ( lpVtbl )
      (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, const char **))lpVtbl->QueryInterface)(
        lpVtbl,
        winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
        &v19);
    v28 = v26;
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v25,
      &v28,
      &v19);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v19);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v32);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v22);
    if ( v23 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v26);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v35);
    LOBYTE(v35) = 0;
    LODWORD(v28) = 0;
    v3 = 0.0;
    v29 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 64LL))(v8, &v35);
    winrt::check_hresult(v31, v15, &v28);
    if ( !(_BYTE)v35 )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
      v35 = 0;
      v8 = 0;
      v21 = 0;
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v35);
    }
  }
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v27);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v21);
  winrt::Windows::Data::Json::JsonObject::JsonObject(&v24);
  NumberValue = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v3);
  winrt::param::hstring::hstring((winrt::param::hstring *)&v28, L"Version");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v24,
    &v28,
    NumberValue);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v35);
  v35 = 0;
  if ( v25.lpVtbl )
    (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, __int64 *))v25.lpVtbl->QueryInterface)(
      v25.lpVtbl,
      winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
      &v35);
  winrt::param::hstring::hstring((winrt::param::hstring *)&v28, L"QueuePropertyBag");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v24,
    &v28,
    &v35);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v35);
  winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(&v24, a2);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v24);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v25);
  return a2;
}

```

## disassembly

```asm
0x18001f93c  mov     [rsp-8+arg_8], rbx
0x18001f941  mov     [rsp-8+arg_0], rcx
0x18001f946  push    rbp
0x18001f947  push    r12
0x18001f949  push    r13
0x18001f94b  push    r14
0x18001f94d  push    r15
0x18001f94f  lea     rbp, [rsp-37h]
0x18001f954  sub     rsp, 0B0h
0x18001f95b  mov     rbx, r8
0x18001f95e  mov     r15, rdx
0x18001f961  mov     [rbp+57h+var_98], 0
0x18001f968  mov     r14, [rbp+5Fh]
0x18001f96c  mov     [rbp+57h+arg_18], 0
0x18001f974  lea     rdx, [rbp+57h+arg_18]
0x18001f978  mov     rcx, r8
0x18001f97b  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001f980  test    al, al
0x18001f982  jnz     loc_18001FCE4
0x18001f988  xor     r12d, r12d
0x18001f98b  lea     rcx, [rbp+57h+var_70]; this
0x18001f98f  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18001f994  nop
0x18001f995  mov     rdx, rbx
0x18001f998  lea     rcx, [rbp+57h+var_90]
0x18001f99c  call    ??$get_begin_iterator@U?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@impl@winrt@@YA?AU?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@1@AEBU?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@3451@@Z; winrt::impl::get_begin_iterator<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,0>(winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>> const &)
0x18001f9a1  lea     r13d, [r12+2]
0x18001f9a6  xor     ebx, ebx
0x18001f9a8  mov     [rbp+57h+var_60], rbx
0x18001f9ac  mov     r14, [rbp+57h+var_90]
0x18001f9b0  lea     rdx, [rbp+57h+var_60]
0x18001f9b4  lea     rcx, [rbp+57h+var_90]
0x18001f9b8  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001f9bd  test    al, al
0x18001f9bf  jnz     loc_18001FBE8
0x18001f9c5  mov     [rbp+57h+arg_18], rbx
0x18001f9c9  or      r13d, 8
0x18001f9cd  mov     [rbp+57h+var_98], r13d
0x18001f9d1  mov     dword ptr [rbp+57h+var_58], ebx
0x18001f9d4  xorps   xmm0, xmm0
0x18001f9d7  movdqu  [rbp+57h+var_50], xmm0
0x18001f9dc  mov     rax, [r14]
0x18001f9df  mov     rbx, [rax+30h]
0x18001f9e3  lea     rcx, [rbp+57h+arg_18]; this
0x18001f9e7  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18001f9ec  mov     rdx, rax
0x18001f9ef  mov     rcx, r14
0x18001f9f2  mov     rax, rbx
0x18001f9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9fa  lea     r8, [rbp+57h+var_58]
0x18001f9fe  mov     edx, eax
0x18001fa00  lea     rcx, [rbp+57h+var_38]
0x18001fa04  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001fa09  and     r13d, 0FFFFFFF7h
0x18001fa0d  mov     [rbp+57h+var_98], r13d
0x18001fa11  or      r13d, 4
0x18001fa15  cmp     [rbp+57h+arg_18], 0
0x18001fa1a  setz    al
0x18001fa1d  mov     rcx, [rbp+5Fh]; this
0x18001fa21  mov     r9d, 80070057h; char *
0x18001fa27  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001fa2e  test    al, al
0x18001fa30  jnz     loc_18001FCD9
0x18001fa36  inc     r12d
0x18001fa39  cmp     r12d, 0C8h
0x18001fa40  setnbe  al
0x18001fa43  mov     rcx, [rbp+5Fh]; this
0x18001fa47  lea     rdx, aNumberOfProper; "Number of properties exceeds the maximu"...
0x18001fa4e  mov     qword ptr [rsp+0D0h+var_A8], rdx; bool
0x18001fa53  mov     [rsp+0D0h+var_B0], al; int
0x18001fa57  mov     edx, 0EBh; void *
0x18001fa5c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001fa61  lea     rdx, [rbp+57h+var_68]
0x18001fa65  lea     rcx, [rbp+57h+arg_18]
0x18001fa69  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x18001fa6e  nop
0x18001fa6f  lea     rdx, [rbp+57h+var_80]
0x18001fa73  lea     rcx, [rbp+57h+arg_18]
0x18001fa77  call    ?Value@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Value(void)
0x18001fa7c  nop
0x18001fa7d  mov     rbx, [rbp+5Fh]
0x18001fa81  mov     [rbp+57h+var_A0], 0
0x18001fa89  lea     rdx, [rbp+57h+var_A0]
0x18001fa8d  lea     rcx, [rbp+57h+var_80]
0x18001fa91  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001fa96  test    al, al
0x18001fa98  jnz     loc_18001FD1A
0x18001fa9e  mov     rcx, [rbp+57h+var_80]
0x18001faa2  test    rcx, rcx
0x18001faa5  jnz     short loc_18001FAAD
0x18001faa7  mov     [rbp+57h+var_88], rcx
0x18001faab  jmp     short loc_18001FAD3
0x18001faad  mov     [rbp+57h+var_A0], 0
0x18001fab5  mov     rax, [rcx]
0x18001fab8  lea     r8, [rbp+57h+var_A0]
0x18001fabc  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x18001fac3  mov     rax, [rax]
0x18001fac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001facb  mov     rax, [rbp+57h+var_A0]
0x18001facf  mov     [rbp+57h+var_88], rax
0x18001fad3  mov     rbx, [rbp+5Fh]
0x18001fad7  mov     [rbp+57h+var_A0], 0
0x18001fadf  lea     rdx, [rbp+57h+var_A0]
0x18001fae3  lea     rcx, [rbp+57h+var_88]
0x18001fae7  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001faec  test    al, al
0x18001faee  jnz     loc_18001FCFF
0x18001faf4  lea     r8, [rbp+57h+var_88]
0x18001faf8  lea     rdx, [rbp+57h+var_30]
0x18001fafc  mov     rcx, [rbp+57h+arg_0]
0x18001fb00  call    ?_CreateJsonObjectFromProperty@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUJsonObject@Json@Data@78@AEBUIPropertyValue@Foundation@78@@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_CreateJsonObjectFromProperty(winrt::Windows::Foundation::IPropertyValue const &)
0x18001fb05  nop
0x18001fb06  mov     rcx, [rax]
0x18001fb09  xor     ebx, ebx
0x18001fb0b  mov     [rbp+57h+var_A0], rbx
0x18001fb0f  test    rcx, rcx
0x18001fb12  jz      short loc_18001FB32
0x18001fb14  mov     rax, [rcx]
0x18001fb17  lea     r8, [rbp+57h+var_A0]
0x18001fb1b  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x18001fb22  mov     rax, [rax]
0x18001fb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb2a  mov     rax, [rbp+57h+var_A0]
0x18001fb2e  mov     [rbp+57h+var_A0], rax
0x18001fb32  mov     rax, [rbp+57h+var_68]
0x18001fb36  mov     [rbp+57h+var_58], rax
0x18001fb3a  lea     r8, [rbp+57h+var_A0]
0x18001fb3e  lea     rdx, [rbp+57h+var_58]
0x18001fb42  lea     rcx, [rbp+57h+var_70]
0x18001fb46  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001fb4b  nop
0x18001fb4c  lea     rcx, [rbp+57h+var_A0]; this
0x18001fb50  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fb55  nop
0x18001fb56  lea     rcx, [rbp+57h+var_30]; this
0x18001fb5a  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fb5f  nop
0x18001fb60  lea     rcx, [rbp+57h+var_88]; this
0x18001fb64  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fb69  nop
0x18001fb6a  cmp     [rbp+57h+var_80], rbx
0x18001fb6e  jz      short loc_18001FB7A
0x18001fb70  lea     rcx, [rbp+57h+var_80]
0x18001fb74  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fb79  nop
0x18001fb7a  lea     rcx, [rbp+57h+var_68]
0x18001fb7e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001fb83  nop
0x18001fb84  lea     rcx, [rbp+57h+arg_18]; this
0x18001fb88  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fb8d  mov     byte ptr [rbp+57h+arg_18], bl
0x18001fb90  mov     dword ptr [rbp+57h+var_58], ebx
0x18001fb93  xorps   xmm0, xmm0
0x18001fb96  movdqu  [rbp+57h+var_50], xmm0
0x18001fb9b  mov     rax, [r14]
0x18001fb9e  lea     rdx, [rbp+57h+arg_18]
0x18001fba2  mov     rcx, r14
0x18001fba5  mov     rax, [rax+40h]
0x18001fba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbae  lea     r8, [rbp+57h+var_58]
0x18001fbb2  mov     edx, eax
0x18001fbb4  lea     rcx, [rbp+57h+var_34]
0x18001fbb8  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001fbbd  cmp     byte ptr [rbp+57h+arg_18], bl
0x18001fbc0  jnz     loc_18001F9B0
0x18001fbc6  lea     rcx, [rbp+57h+var_90]
0x18001fbca  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fbcf  mov     [rbp+57h+arg_18], rbx
0x18001fbd3  mov     r14, rbx
0x18001fbd6  mov     [rbp+57h+var_90], rbx
0x18001fbda  lea     rcx, [rbp+57h+arg_18]; this
0x18001fbde  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fbe3  jmp     loc_18001F9B0
0x18001fbe8  lea     rcx, [rbp+57h+var_60]; this
0x18001fbec  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fbf1  nop
0x18001fbf2  lea     rcx, [rbp+57h+var_90]; this
0x18001fbf6  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fbfb  lea     rcx, [rbp+57h+var_78]; this
0x18001fbff  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18001fc04  nop
0x18001fc05  movsd   xmm1, cs:__real@3ff0000000000000
0x18001fc0d  lea     rcx, [rbp+57h+arg_18]
0x18001fc11  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18001fc16  mov     rbx, rax
0x18001fc19  lea     rdx, aVersion; "Version"
0x18001fc20  lea     rcx, [rbp+57h+var_58]; this
0x18001fc24  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001fc29  mov     r8, rbx
0x18001fc2c  lea     rdx, [rbp+57h+var_58]
0x18001fc30  lea     rcx, [rbp+57h+var_78]
0x18001fc34  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001fc39  nop
0x18001fc3a  lea     rcx, [rbp+57h+arg_18]; this
0x18001fc3e  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fc43  mov     rcx, [rbp+57h+var_70]
0x18001fc47  mov     [rbp+57h+arg_18], 0
0x18001fc4f  test    rcx, rcx
0x18001fc52  jz      short loc_18001FC72
0x18001fc54  mov     rax, [rcx]
0x18001fc57  lea     r8, [rbp+57h+arg_18]
0x18001fc5b  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x18001fc62  mov     rax, [rax]
0x18001fc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc6a  mov     rax, [rbp+57h+arg_18]
0x18001fc6e  mov     [rbp+57h+arg_18], rax
0x18001fc72  lea     rdx, aQueuepropertyb; "QueuePropertyBag"
0x18001fc79  lea     rcx, [rbp+57h+var_58]; this
0x18001fc7d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001fc82  lea     r8, [rbp+57h+arg_18]
0x18001fc86  lea     rdx, [rbp+57h+var_58]
0x18001fc8a  lea     rcx, [rbp+57h+var_78]
0x18001fc8e  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001fc93  nop
0x18001fc94  lea     rcx, [rbp+57h+arg_18]; this
0x18001fc98  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fc9d  mov     rdx, r15
0x18001fca0  lea     rcx, [rbp+57h+var_78]
0x18001fca4  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x18001fca9  nop
0x18001fcaa  lea     rcx, [rbp+57h+var_78]; this
0x18001fcae  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fcb3  nop
0x18001fcb4  lea     rcx, [rbp+57h+var_70]; this
0x18001fcb8  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fcbd  mov     rax, r15
0x18001fcc0  mov     rbx, [rsp+0D0h+arg_8]
0x18001fcc8  add     rsp, 0B0h
0x18001fccf  pop     r15
0x18001fcd1  pop     r14
0x18001fcd3  pop     r13
0x18001fcd5  pop     r12
0x18001fcd7  pop     rbp
0x18001fcd8  retn
0x18001fcd9  mov     edx, 0E9h; void *
0x18001fcde  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001fce4  mov     r9d, 80070057h; char *
0x18001fcea  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001fcf1  mov     edx, 0E2h; void *
0x18001fcf6  mov     rcx, r14; this
0x18001fcf9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001fcff  mov     r9d, 80070057h; char *
0x18001fd05  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001fd0c  mov     edx, 0F0h; void *
0x18001fd11  mov     rcx, rbx; this
0x18001fd14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001fd1a  mov     r9d, 83760002h; char *
0x18001fd20  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001fd27  mov     edx, 0EEh; void *
0x18001fd2c  mov     rcx, rbx; this
0x18001fd2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
