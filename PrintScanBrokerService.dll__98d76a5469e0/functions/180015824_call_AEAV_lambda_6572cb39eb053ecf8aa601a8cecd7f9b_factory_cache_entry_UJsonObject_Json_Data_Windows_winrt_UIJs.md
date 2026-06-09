# ??$call@AEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@Z

- ea: `0x180015824`
- end: `0x180015969`
- name: `??$call@AEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f5fc`

## callees

- `0x1800046b1`
- `0x180006460`
- `0x1800078e4`
- `0x180007a58`
- `0x18000fa48`
- `0x1800115a4`
- `0x180015824`
- `0x180018ce8`
- `0x180048010`

## string_xrefs

- `0x18001583e`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_ &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rdi
  const wchar_t *v7; // [rsp+28h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h]
  _BYTE v9[32]; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+80h] [rbp+20h] BYREF
  __int64 *v11; // [rsp+98h] [rbp+38h] BYREF

  v10 = a1;
  v7 = L"Windows.Data.Json.JsonObject";
  *(_QWORD *)&v8 = 28;
  winrt::param::hstring::hstring(v9, &v7);
  v11 = 0;
  LODWORD(v7) = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>,
    &v11);
  winrt::check_hresult(&v10, (unsigned int)v10, &v7);
  v5 = v11;
  v10 = v11;
  if ( v11
    && (v11 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
    v11 = &qword_180060C68;
    _InterlockedIncrement64(&qword_180060C68);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
            (signed __int64)v5,
            0) )
    {
      v10 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180060C70);
    }
    _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_180060C68);
  }
  else
  {
    _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(a3, a2, &v10);
  }
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v10);
  return a2;
}

```

## disassembly

```asm
0x180015824  mov     [rsp-18h+arg_8], rbx
0x180015829  mov     [rsp-18h+arg_0], rcx
0x18001582e  push    rbp
0x18001582f  push    rsi
0x180015830  push    rdi
0x180015831  mov     rbp, rsp
0x180015834  sub     rsp, 60h
0x180015838  mov     rsi, r8
0x18001583b  mov     rbx, rdx
0x18001583e  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x180015845  mov     [rbp+var_38], rax
0x180015849  mov     qword ptr [rbp+var_30], 1Ch
0x180015851  lea     rdx, [rbp+var_38]
0x180015855  lea     rcx, [rbp+var_20]
0x180015859  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001585e  mov     [rbp+arg_18], 0
0x180015866  mov     dword ptr [rbp+var_38], 0
0x18001586d  xorps   xmm0, xmm0
0x180015870  movdqu  [rbp+var_30], xmm0
0x180015875  lea     r9, [rbp+arg_18]
0x180015879  lea     r8, ??$guid_v@UIJsonObjectStatics@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>
0x180015880  lea     rdx, [rbp+var_20]
0x180015884  lea     rcx, [rbp+arg_0]
0x180015888  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001588d  lea     r8, [rbp+var_38]
0x180015891  mov     edx, dword ptr [rbp+arg_0]
0x180015894  lea     rcx, [rbp+arg_0]
0x180015898  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001589d  mov     rdi, [rbp+arg_18]
0x1800158a1  mov     [rbp+arg_0], rdi
0x1800158a5  test    rdi, rdi
0x1800158a8  jz      loc_18001593D
0x1800158ae  mov     [rbp+arg_18], 0
0x1800158b6  mov     rax, [rdi]
0x1800158b9  lea     r8, [rbp+arg_18]
0x1800158bd  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800158c4  mov     rcx, rdi
0x1800158c7  mov     rax, [rax]
0x1800158ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158cf  mov     rax, [rbp+arg_18]
0x1800158d3  mov     [rbp+arg_18], rax
0x1800158d7  test    rax, rax
0x1800158da  jz      short loc_18001593D
0x1800158dc  lea     rcx, [rbp+arg_18]
0x1800158e0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800158e5  lea     rax, qword_180060C68
0x1800158ec  mov     [rbp+arg_18], rax
0x1800158f0  lock inc cs:qword_180060C68
0x1800158f8  xor     eax, eax
0x1800158fa  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x180015903  jnz     short loc_180015920
0x180015905  mov     [rbp+arg_0], 0
0x18001590d  lea     rdx, stru_180060C70; ListEntry
0x180015914  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001591b  call    WINRT_IMPL_InterlockedPushEntrySList
0x180015920  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x180015927  mov     rdx, rbx
0x18001592a  mov     rcx, rsi
0x18001592d  call    ??R_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x180015932  nop
0x180015933  lock dec cs:qword_180060C68
0x18001593b  jmp     short loc_18001594D
0x18001593d  lea     r8, [rbp+arg_0]
0x180015941  mov     rdx, rbx
0x180015944  mov     rcx, rsi
0x180015947  call    ??R_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18001594c  nop
0x18001594d  lea     rcx, [rbp+arg_0]; this
0x180015951  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180015956  mov     rax, rbx
0x180015959  mov     rbx, [rsp+60h+arg_8]
0x180015961  add     rsp, 60h
0x180015965  pop     rdi
0x180015966  pop     rsi
0x180015967  pop     rbp
0x180015968  retn
```
