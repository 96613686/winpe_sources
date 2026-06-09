# ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x180012674`
- end: `0x18001285a`
- name: `??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `486`
- prototype: `signed __int64 *__fastcall(signed __int64, signed __int64 *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016ae4`

## callees

- `0x180003ab9`
- `0x180007b84`
- `0x1800104f8`
- `0x180011c3c`
- `0x180012674`
- `0x1800ca010`

## string_xrefs

- `0x18001269c`: `Windows.Data.Json.JsonValue`
- `0x18001278f`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x1800127e5`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
signed __int64 *__fastcall ___call_AEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_2_SA_AEBUhstring_param_2__Z__Z(
        signed __int64 a1,
        signed __int64 *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  const char *v10; // [rsp+38h] [rbp-38h]
  __int64 v11; // [rsp+40h] [rbp-30h]
  _DWORD *v12; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v13[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v14; // [rsp+60h] [rbp-10h]
  signed __int64 v15; // [rsp+90h] [rbp+20h] BYREF
  signed __int64 v16; // [rsp+A8h] [rbp+38h] BYREF

  v15 = a1;
  v13[0] = 1;
  v13[1] = 27;
  v14 = L"Windows.Data.Json.JsonValue";
  v12 = v13;
  v16 = 0;
  v9 = 6172;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/base.h";
  v11 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v15,
    &v12,
    winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValueStatics>,
    &v16);
  if ( (int)v15 < 0 )
    winrt::throw_hresult((unsigned int)v15, &v9);
  v5 = v16;
  v15 = v16;
  if ( !v16
    || (v16 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, signed __int64 *))v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v16),
        !v16) )
  {
    v16 = 0;
    v9 = 638;
    v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, signed __int64 *))(*(_QWORD *)v5 + 80LL))(v5, **a3, &v16);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v16;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  _InterlockedIncrement64(&qword_18010F798);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v5 = 0;
    v15 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18010F7A0);
  }
  v16 = 0;
  v9 = 638;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                                    + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         **a3,
         &v16);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v16;
  _InterlockedDecrement64(&qword_18010F798);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  return a2;
}

```

## disassembly

```asm
0x180012674  mov     [rsp-18h+arg_8], rbx
0x180012679  mov     [rsp-18h+arg_0], rcx
0x18001267e  push    rbp
0x18001267f  push    rsi
0x180012680  push    rdi
0x180012681  mov     rbp, rsp
0x180012684  sub     rsp, 70h
0x180012688  mov     rsi, r8
0x18001268b  mov     rdi, rdx
0x18001268e  mov     [rbp+var_20], 1
0x180012695  mov     [rbp+var_1C], 1Bh
0x18001269c  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x1800126a3  mov     [rbp+var_10], rax
0x1800126a7  lea     rax, [rbp+var_20]
0x1800126ab  mov     [rbp+var_28], rax
0x1800126af  mov     [rbp+arg_18], 0
0x1800126b7  mov     [rbp+var_40], 181Ch
0x1800126be  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800126c5  mov     [rbp+var_38], rax
0x1800126c9  mov     [rbp+var_30], 0
0x1800126d1  lea     r9, [rbp+arg_18]
0x1800126d5  lea     r8, ??$guid_v@UIJsonValueStatics@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValueStatics>
0x1800126dc  lea     rdx, [rbp+var_28]
0x1800126e0  lea     rcx, [rbp+arg_0]
0x1800126e4  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x1800126e9  mov     ecx, dword ptr [rbp+arg_0]
0x1800126ec  test    ecx, ecx
0x1800126ee  js      loc_180012844
0x1800126f4  mov     rbx, [rbp+arg_18]
0x1800126f8  mov     [rbp+arg_0], rbx
0x1800126fc  test    rbx, rbx
0x1800126ff  jz      loc_1800127D6
0x180012705  mov     [rbp+arg_18], 0
0x18001270d  mov     rax, [rbx]
0x180012710  lea     r8, [rbp+arg_18]
0x180012714  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001271b  mov     rcx, rbx
0x18001271e  mov     rax, [rax]
0x180012721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012726  mov     rax, [rbp+arg_18]
0x18001272a  mov     [rbp+arg_18], rax
0x18001272e  test    rax, rax
0x180012731  jz      loc_1800127D6
0x180012737  lea     rcx, [rbp+arg_18]
0x18001273b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012740  lea     rax, qword_18010F798
0x180012747  mov     [rbp+var_48], rax
0x18001274b  lock inc cs:qword_18010F798
0x180012753  xor     eax, eax
0x180012755  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001275e  jnz     short loc_180012779
0x180012760  xor     ebx, ebx
0x180012762  mov     [rbp+arg_0], rbx
0x180012766  lea     rdx, stru_18010F7A0; ListEntry
0x18001276d  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180012774  call    WINRT_IMPL_InterlockedPushEntrySList
0x180012779  mov     [rbp+arg_18], 0
0x180012781  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180012788  mov     [rbp+var_40], 27Eh
0x18001278f  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180012796  mov     [rbp+var_38], rax
0x18001279a  mov     [rbp+var_30], 0
0x1800127a2  mov     rax, [rcx]
0x1800127a5  mov     rdx, [rsi]
0x1800127a8  lea     r8, [rbp+arg_18]
0x1800127ac  mov     rdx, [rdx]
0x1800127af  mov     rax, [rax+50h]
0x1800127b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127b8  test    eax, eax
0x1800127ba  js      loc_18001284E
0x1800127c0  mov     rax, [rbp+arg_18]
0x1800127c4  mov     [rdi], rax
0x1800127c7  lock dec cs:qword_18010F798
0x1800127cf  test    rbx, rbx
0x1800127d2  jz      short loc_180012825
0x1800127d4  jmp     short loc_18001281C
0x1800127d6  mov     [rbp+arg_18], 0
0x1800127de  mov     [rbp+var_40], 27Eh
0x1800127e5  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800127ec  mov     [rbp+var_38], rax
0x1800127f0  mov     [rbp+var_30], 0
0x1800127f8  mov     rax, [rbx]
0x1800127fb  mov     rdx, [rsi]
0x1800127fe  lea     r8, [rbp+arg_18]
0x180012802  mov     rdx, [rdx]
0x180012805  mov     rcx, rbx
0x180012808  mov     rax, [rax+50h]
0x18001280c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012811  test    eax, eax
0x180012813  js      short loc_180012838
0x180012815  mov     rax, [rbp+arg_18]
0x180012819  mov     [rdi], rax
0x18001281c  lea     rcx, [rbp+arg_0]
0x180012820  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012825  mov     rax, rdi
0x180012828  mov     rbx, [rsp+70h+arg_8]
0x180012830  add     rsp, 70h
0x180012834  pop     rdi
0x180012835  pop     rsi
0x180012836  pop     rbp
0x180012837  retn
0x180012838  lea     rdx, [rbp+var_40]
0x18001283c  mov     ecx, eax
0x18001283e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180012844  lea     rdx, [rbp+var_40]
0x180012848  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001284e  lea     rdx, [rbp+var_40]
0x180012852  mov     ecx, eax
0x180012854  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
