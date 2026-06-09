# ??$call@AEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@Z

- ea: `0x18001d7f8`
- end: `0x18001d908`
- name: `??$call@AEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023898`

## callees

- `0x180005236`
- `0x1800072d8`
- `0x18000dfc0`
- `0x18001d7f8`
- `0x18001e618`
- `0x180020388`
- `0x18002094c`
- `0x180035010`

## string_xrefs

- `0x18001d812`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        __int64 a3)
{
  signed __int64 v5; // rdi
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+80h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = a1;
  v7[0] = L"Windows.Data.Json.JsonObject";
  v7[1] = 28;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonObjectStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180046C18;
    _InterlockedIncrement64(&qword_180046C18);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_180046C18);
  }
  else
  {
    _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x18001d7f8  mov     [rsp-18h+arg_8], rbx
0x18001d7fd  mov     [rsp-18h+arg_0], rcx
0x18001d802  push    rbp
0x18001d803  push    rsi
0x18001d804  push    rdi
0x18001d805  mov     rbp, rsp
0x18001d808  sub     rsp, 60h
0x18001d80c  mov     rsi, r8
0x18001d80f  mov     rbx, rdx
0x18001d812  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x18001d819  mov     [rbp+var_38], rax
0x18001d81d  mov     [rbp+var_30], 1Ch
0x18001d825  lea     rdx, [rbp+var_38]
0x18001d829  lea     rcx, [rbp+var_28]
0x18001d82d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d832  lea     rdx, [rbp+var_28]
0x18001d836  lea     rcx, [rbp+arg_0]
0x18001d83a  call    ??$get_activation_factory@UIJsonObjectStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonObjectStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonObjectStatics>(winrt::param::hstring const &)
0x18001d83f  nop
0x18001d840  mov     rdi, [rbp+arg_0]
0x18001d844  test    rdi, rdi
0x18001d847  jz      loc_18001D8DC
0x18001d84d  mov     [rbp+arg_18], 0
0x18001d855  mov     rax, [rdi]
0x18001d858  lea     r8, [rbp+arg_18]
0x18001d85c  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d863  mov     rcx, rdi
0x18001d866  mov     rax, [rax]
0x18001d869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d86e  mov     rax, [rbp+arg_18]
0x18001d872  mov     [rbp+arg_18], rax
0x18001d876  test    rax, rax
0x18001d879  jz      short loc_18001D8DC
0x18001d87b  lea     rcx, [rbp+arg_18]
0x18001d87f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d884  lea     rax, qword_180046C18
0x18001d88b  mov     [rbp+arg_18], rax
0x18001d88f  lock inc cs:qword_180046C18
0x18001d897  xor     eax, eax
0x18001d899  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001d8a2  jnz     short loc_18001D8BF
0x18001d8a4  mov     [rbp+arg_0], 0
0x18001d8ac  lea     rdx, ListEntry; ListEntry
0x18001d8b3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d8ba  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d8bf  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001d8c6  mov     rdx, rbx
0x18001d8c9  mov     rcx, rsi
0x18001d8cc  call    ??R_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18001d8d1  nop
0x18001d8d2  lock dec cs:qword_180046C18
0x18001d8da  jmp     short loc_18001D8EC
0x18001d8dc  lea     r8, [rbp+arg_0]
0x18001d8e0  mov     rdx, rbx
0x18001d8e3  mov     rcx, rsi
0x18001d8e6  call    ??R_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18001d8eb  nop
0x18001d8ec  lea     rcx, [rbp+arg_0]
0x18001d8f0  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001d8f5  mov     rax, rbx
0x18001d8f8  mov     rbx, [rsp+60h+arg_8]
0x18001d900  add     rsp, 60h
0x18001d904  pop     rdi
0x18001d905  pop     rsi
0x18001d906  pop     rbp
0x18001d907  retn
```
