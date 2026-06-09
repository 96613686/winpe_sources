# _anonymous_namespace_::SerializePropertiesToJsonString

- ea: `0x180016ae4`
- end: `0x180016da1`
- name: `_anonymous_namespace_::SerializePropertiesToJsonString`
- size: `701`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800142e8`

## callees

- `0x180007b84`
- `0x180011c3c`
- `0x180012674`
- `0x180012860`
- `0x180013f94`
- `0x180016ae4`
- `0x1800ca010`

## string_xrefs

- `0x180016cee`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x180016bb5`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 *__fastcall anonymous_namespace_::SerializePropertiesToJsonString(__int64 *a1, __int64 a2, __int64 *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // r15
  int v8; // eax
  __int64 v9; // rsi
  int v10; // eax
  __int64 *v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 *v14; // rcx
  int v15; // eax
  __int64 *v17; // [rsp+38h] [rbp-48h] BYREF
  __int64 *v18; // [rsp+40h] [rbp-40h] BYREF
  int v19; // [rsp+48h] [rbp-38h] BYREF
  const char *v20; // [rsp+50h] [rbp-30h]
  __int64 v21; // [rsp+58h] [rbp-28h]
  __int64 v22; // [rsp+60h] [rbp-20h] BYREF
  __int64 *v23; // [rsp+C8h] [rbp+48h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, __int64 *, __int64 **); // [rsp+D8h] [rbp+58h] BYREF

  v23 = &qword_18010F7B8;
  _InterlockedIncrement64(&qword_18010F7B8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_3__::operator()(
      (__int64)a1,
      &v24,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18010F7B8);
  }
  else
  {
    _InterlockedDecrement64(&qword_18010F7B8);
    v23 = (__int64 *)`winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_3__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      a1,
      (__int64)&v24,
      (void (__fastcall **)(__int64, __int64 *))&v23);
  }
  if ( *(_DWORD *)(a2 + 8) )
  {
    v6 = 0;
    v7 = *a3;
    do
    {
      v22 = *(_QWORD *)(v7 + 8LL * v6);
      v23 = &v22;
      v18 = &qword_18010F798;
      _InterlockedIncrement64(&qword_18010F798);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> )
      {
        v23 = 0;
        v19 = 638;
        v20 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
        v21 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                                     + 80LL))(
               winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
               v22,
               &v23);
        if ( v8 < 0 )
          winrt::throw_hresult((unsigned int)v8, &v19);
        v17 = v23;
        _InterlockedDecrement64(&qword_18010F798);
      }
      else
      {
        _InterlockedDecrement64(&qword_18010F798);
        ___call_AEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_2_SA_AEBUhstring_param_2__Z__Z(
          0,
          (signed __int64 *)&v17,
          &v23);
      }
      v9 = *(_QWORD *)(*(_QWORD *)a2 + 8LL * v6);
      LOBYTE(v23) = 0;
      v18 = 0;
      if ( v24 )
      {
        v10 = (**v24)(
                v24,
                winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,
                &v18);
        v11 = v18;
      }
      else
      {
        v10 = 0;
        v11 = 0;
      }
      v19 = 325;
      v20 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
      v21 = 0;
      if ( v10 < 0 )
        winrt::throw_hresult((unsigned int)v10, &v19);
      v19 = 327;
      v20 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
      v21 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, __int64 **))(*v11 + 80))(v11, v9, v17, &v23);
      if ( v12 < 0 )
        winrt::throw_hresult((unsigned int)v12, &v19);
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
      if ( v17 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v17);
      ++v6;
    }
    while ( v6 < *(_DWORD *)(a2 + 8) );
  }
  v18 = 0;
  v23 = 0;
  if ( v24 )
  {
    v13 = (**v24)(v24, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v23);
    v14 = v23;
  }
  else
  {
    v13 = 0;
    v14 = 0;
  }
  v19 = 451;
  v20 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v21 = 0;
  if ( v13 < 0 )
    winrt::throw_hresult((unsigned int)v13, &v19);
  v19 = 453;
  v20 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v21 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(*v14 + 56))(v14, &v18);
  if ( v15 < 0 )
    winrt::throw_hresult((unsigned int)v15, &v19);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
  *a1 = (__int64)v18;
  if ( v24 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
  return a1;
}

```

## disassembly

```asm
0x180016ae4  mov     [rsp-38h+arg_0], rbx
0x180016ae9  push    rbp
0x180016aea  push    rsi
0x180016aeb  push    rdi
0x180016aec  push    r12
0x180016aee  push    r13
0x180016af0  push    r14
0x180016af2  push    r15
0x180016af4  mov     rbp, rsp
0x180016af7  sub     rsp, 80h
0x180016afe  mov     rsi, r8
0x180016b01  mov     r14, rdx
0x180016b04  mov     rdi, rcx
0x180016b07  xor     r12d, r12d
0x180016b0a  lea     rax, qword_18010F7B8
0x180016b11  mov     [rbp+arg_8], rax
0x180016b15  lock inc cs:qword_18010F7B8
0x180016b1d  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, r12; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x180016b24  jz      short loc_180016B41
0x180016b26  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x180016b2d  lea     rdx, [rbp+arg_18]
0x180016b31  call    ??R_lambda_3__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_3__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180016b36  nop
0x180016b37  lock dec cs:qword_18010F7B8
0x180016b3f  jmp     short loc_180016B62
0x180016b41  lock dec cs:qword_18010F7B8
0x180016b49  lea     rax, ?_lambda_invoker_cdecl_@_lambda_3__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@56@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_3__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180016b50  mov     [rbp+arg_8], rax
0x180016b54  lea     r8, [rbp+arg_8]
0x180016b58  lea     rdx, [rbp+arg_18]
0x180016b5c  call    ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x180016b61  nop
0x180016b62  cmp     [r14+8], r12d
0x180016b66  jbe     loc_180016CB0
0x180016b6c  mov     ebx, r12d
0x180016b6f  mov     r15, [rsi]
0x180016b72  lea     r13, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016b79  mov     esi, ebx
0x180016b7b  mov     rax, [r15+rsi*8]
0x180016b7f  mov     [rbp+var_20], rax
0x180016b83  lea     rax, [rbp+var_20]
0x180016b87  mov     [rbp+arg_8], rax
0x180016b8b  lea     rax, qword_18010F798
0x180016b92  mov     [rbp+var_40], rax
0x180016b96  lock inc cs:qword_18010F798
0x180016b9e  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180016ba5  test    rcx, rcx
0x180016ba8  jz      short loc_180016BF2
0x180016baa  mov     [rbp+arg_8], r12
0x180016bae  mov     [rbp+var_38], 27Eh
0x180016bb5  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016bbc  mov     [rbp+var_30], rax
0x180016bc0  mov     [rbp+var_28], r12
0x180016bc4  mov     rax, [rcx]
0x180016bc7  lea     r8, [rbp+arg_8]
0x180016bcb  mov     rdx, [rbp+var_20]
0x180016bcf  mov     rax, [rax+50h]
0x180016bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bd8  test    eax, eax
0x180016bda  js      loc_180016D71
0x180016be0  mov     rax, [rbp+arg_8]
0x180016be4  mov     [rbp+var_48], rax
0x180016be8  lock dec cs:qword_18010F798
0x180016bf0  jmp     short loc_180016C08
0x180016bf2  lock dec cs:qword_18010F798
0x180016bfa  lea     r8, [rbp+arg_8]
0x180016bfe  lea     rdx, [rbp+var_48]
0x180016c02  call    ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x180016c07  nop
0x180016c08  mov     rax, [r14]
0x180016c0b  mov     rsi, [rax+rsi*8]
0x180016c0f  mov     byte ptr [rbp+arg_8], r12b
0x180016c13  mov     rcx, [rbp+arg_18]
0x180016c17  mov     [rbp+var_40], r12
0x180016c1b  test    rcx, rcx
0x180016c1e  jnz     short loc_180016C28
0x180016c20  mov     eax, r12d
0x180016c23  mov     rcx, r12
0x180016c26  jmp     short loc_180016C46
0x180016c28  mov     rax, [rcx]
0x180016c2b  lea     r8, [rbp+var_40]
0x180016c2f  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>
0x180016c36  mov     rax, [rax]
0x180016c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c3e  mov     rcx, [rbp+var_40]
0x180016c42  mov     [rbp+var_40], rcx
0x180016c46  mov     [rbp+var_38], 145h
0x180016c4d  mov     [rbp+var_30], r13
0x180016c51  mov     [rbp+var_28], r12
0x180016c55  test    eax, eax
0x180016c57  js      loc_180016D89
0x180016c5d  mov     [rbp+var_38], 147h
0x180016c64  mov     [rbp+var_30], r13
0x180016c68  mov     [rbp+var_28], r12
0x180016c6c  mov     rax, [rcx]
0x180016c6f  lea     r9, [rbp+arg_8]
0x180016c73  mov     r8, [rbp+var_48]
0x180016c77  mov     rdx, rsi
0x180016c7a  mov     rax, [rax+50h]
0x180016c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c83  test    eax, eax
0x180016c85  js      loc_180016D7D
0x180016c8b  lea     rcx, [rbp+var_40]
0x180016c8f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016c94  nop
0x180016c95  cmp     [rbp+var_48], r12
0x180016c99  jz      short loc_180016CA4
0x180016c9b  lea     rcx, [rbp+var_48]
0x180016c9f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016ca4  inc     ebx
0x180016ca6  cmp     ebx, [r14+8]
0x180016caa  jb      loc_180016B79
0x180016cb0  mov     [rbp+var_40], r12
0x180016cb4  mov     rcx, [rbp+arg_18]
0x180016cb8  mov     [rbp+arg_8], r12
0x180016cbc  test    rcx, rcx
0x180016cbf  jnz     short loc_180016CC9
0x180016cc1  mov     eax, r12d
0x180016cc4  mov     rcx, r12
0x180016cc7  jmp     short loc_180016CE7
0x180016cc9  mov     rax, [rcx]
0x180016ccc  lea     r8, [rbp+arg_8]
0x180016cd0  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x180016cd7  mov     rax, [rax]
0x180016cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cdf  mov     rcx, [rbp+arg_8]
0x180016ce3  mov     [rbp+arg_8], rcx
0x180016ce7  mov     [rbp+var_38], 1C3h
0x180016cee  lea     rdx, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016cf5  mov     [rbp+var_30], rdx
0x180016cf9  mov     [rbp+var_28], r12
0x180016cfd  test    eax, eax
0x180016cff  js      loc_180016D95
0x180016d05  mov     [rbp+var_38], 1C5h
0x180016d0c  mov     [rbp+var_30], rdx
0x180016d10  mov     [rbp+var_28], r12
0x180016d14  mov     rax, [rcx]
0x180016d17  lea     rdx, [rbp+var_40]
0x180016d1b  mov     rax, [rax+38h]
0x180016d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d24  test    eax, eax
0x180016d26  js      short loc_180016D65
0x180016d28  lea     rcx, [rbp+arg_8]
0x180016d2c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016d31  mov     rax, [rbp+var_40]
0x180016d35  mov     [rdi], rax
0x180016d38  cmp     [rbp+arg_18], r12
0x180016d3c  jz      short loc_180016D47
0x180016d3e  lea     rcx, [rbp+arg_18]
0x180016d42  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016d47  mov     rax, rdi
0x180016d4a  mov     rbx, [rsp+80h+arg_0]
0x180016d52  add     rsp, 80h
0x180016d59  pop     r15
0x180016d5b  pop     r14
0x180016d5d  pop     r13
0x180016d5f  pop     r12
0x180016d61  pop     rdi
0x180016d62  pop     rsi
0x180016d63  pop     rbp
0x180016d64  retn
0x180016d65  lea     rdx, [rbp+var_38]
0x180016d69  mov     ecx, eax
0x180016d6b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180016d71  lea     rdx, [rbp+var_38]
0x180016d75  mov     ecx, eax
0x180016d77  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180016d7d  lea     rdx, [rbp+var_38]
0x180016d81  mov     ecx, eax
0x180016d83  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180016d89  lea     rdx, [rbp+var_38]
0x180016d8d  mov     ecx, eax
0x180016d8f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180016d95  lea     rdx, [rbp+var_38]
0x180016d99  mov     ecx, eax
0x180016d9b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
