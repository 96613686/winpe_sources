# ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x180014fec`
- end: `0x180015191`
- name: `??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016ab4`

## callees

- `0x1800051fd`
- `0x1800145d8`
- `0x180014974`
- `0x180014fec`
- `0x180015e90`
- `0x180032010`

## string_xrefs

- `0x180015014`: `Windows.Data.Json.JsonValue`
- `0x1800150d0`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x180015126`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_2_SA_AEBUhstring_param_2__Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rdi
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  const char *v10; // [rsp+38h] [rbp-38h]
  __int64 v11; // [rsp+40h] [rbp-30h]
  _DWORD *v12; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v13[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v14; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v15)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+38h] BYREF

  v15 = a1;
  v13[0] = 1;
  v13[1] = 27;
  v14 = L"Windows.Data.Json.JsonValue";
  v12 = v13;
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(&v15, &v12);
  v5 = (signed __int64)v15;
  if ( !v15 || (v16 = 0, (**v15)(v15, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v16), !v16) )
  {
    v16 = 0;
    v9 = 638;
    v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 80LL))(v5, **a3, &v16);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v16;
    goto LABEL_10;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  _InterlockedIncrement64(&qword_18005FAC8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v15 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18005FAD0);
    v5 = 0;
  }
  v16 = 0;
  v9 = 638;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                             + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         **a3,
         &v16);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v16;
  _InterlockedDecrement64(&qword_18005FAC8);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  return a2;
}

```

## disassembly

```asm
0x180014fec  mov     [rsp-18h+arg_8], rbx
0x180014ff1  mov     [rsp-18h+arg_0], rcx
0x180014ff6  push    rbp
0x180014ff7  push    rsi
0x180014ff8  push    rdi
0x180014ff9  mov     rbp, rsp
0x180014ffc  sub     rsp, 70h
0x180015000  mov     rsi, r8
0x180015003  mov     rbx, rdx
0x180015006  mov     [rbp+var_20], 1
0x18001500d  mov     [rbp+var_1C], 1Bh
0x180015014  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x18001501b  mov     [rbp+var_10], rax
0x18001501f  lea     rax, [rbp+var_20]
0x180015023  mov     [rbp+var_28], rax
0x180015027  lea     rdx, [rbp+var_28]
0x18001502b  lea     rcx, [rbp+arg_0]
0x18001502f  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180015034  nop
0x180015035  mov     rdi, [rbp+arg_0]
0x180015039  test    rdi, rdi
0x18001503c  jz      loc_180015117
0x180015042  mov     [rbp+arg_18], 0
0x18001504a  mov     rax, [rdi]
0x18001504d  lea     r8, [rbp+arg_18]
0x180015051  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180015058  mov     rcx, rdi
0x18001505b  mov     rax, [rax]
0x18001505e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015063  mov     rax, [rbp+arg_18]
0x180015067  mov     [rbp+arg_18], rax
0x18001506b  test    rax, rax
0x18001506e  jz      loc_180015117
0x180015074  lea     rcx, [rbp+arg_18]
0x180015078  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001507d  lea     rax, qword_18005FAC8
0x180015084  mov     [rbp+var_48], rax
0x180015088  lock inc cs:qword_18005FAC8
0x180015090  xor     eax, eax
0x180015092  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001509b  jnz     short loc_1800150BA
0x18001509d  mov     [rbp+arg_0], 0
0x1800150a5  lea     rdx, stru_18005FAD0; ListEntry
0x1800150ac  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800150b3  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800150b8  xor     edi, edi
0x1800150ba  mov     [rbp+arg_18], 0
0x1800150c2  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800150c9  mov     [rbp+var_40], 27Eh
0x1800150d0  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800150d7  mov     [rbp+var_38], rax
0x1800150db  mov     [rbp+var_30], 0
0x1800150e3  mov     rax, [rcx]
0x1800150e6  mov     rdx, [rsi]
0x1800150e9  lea     r8, [rbp+arg_18]
0x1800150ed  mov     rdx, [rdx]
0x1800150f0  mov     rax, [rax+50h]
0x1800150f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150f9  test    eax, eax
0x1800150fb  js      loc_180015185
0x180015101  mov     rax, [rbp+arg_18]
0x180015105  mov     [rbx], rax
0x180015108  lock dec cs:qword_18005FAC8
0x180015110  test    rdi, rdi
0x180015113  jz      short loc_180015166
0x180015115  jmp     short loc_18001515D
0x180015117  mov     [rbp+arg_18], 0
0x18001511f  mov     [rbp+var_40], 27Eh
0x180015126  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001512d  mov     [rbp+var_38], rax
0x180015131  mov     [rbp+var_30], 0
0x180015139  mov     rax, [rdi]
0x18001513c  mov     rdx, [rsi]
0x18001513f  lea     r8, [rbp+arg_18]
0x180015143  mov     rdx, [rdx]
0x180015146  mov     rcx, rdi
0x180015149  mov     rax, [rax+50h]
0x18001514d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015152  test    eax, eax
0x180015154  js      short loc_180015179
0x180015156  mov     rax, [rbp+arg_18]
0x18001515a  mov     [rbx], rax
0x18001515d  lea     rcx, [rbp+arg_0]
0x180015161  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015166  mov     rax, rbx
0x180015169  mov     rbx, [rsp+70h+arg_8]
0x180015171  add     rsp, 70h
0x180015175  pop     rdi
0x180015176  pop     rsi
0x180015177  pop     rbp
0x180015178  retn
0x180015179  lea     rdx, [rbp+var_40]
0x18001517d  mov     ecx, eax
0x18001517f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180015185  lea     rdx, [rbp+var_40]
0x180015189  mov     ecx, eax
0x18001518b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
