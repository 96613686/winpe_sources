# ??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z

- ea: `0x180014e40`
- end: `0x180014fe3`
- name: `??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800168a0`

## callees

- `0x1800051fd`
- `0x1800145d8`
- `0x180014974`
- `0x180014e40`
- `0x180015e90`
- `0x180032010`

## string_xrefs

- `0x180014e68`: `Windows.Data.Json.JsonValue`
- `0x180014f24`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x180014f79`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateBooleanValue_JsonValue_Json_Data_Windows_winrt__SA__N_Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateBooleanValue_JsonValue_Json_Data_Windows_2_SA__N_Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _BYTE **a3)
{
  signed __int64 v5; // rdi
  _BYTE *v6; // rdx
  int v7; // eax
  _BYTE *v8; // rdx
  int v9; // eax
  int v11; // [rsp+30h] [rbp-40h] BYREF
  const char *v12; // [rsp+38h] [rbp-38h]
  __int64 v13; // [rsp+40h] [rbp-30h]
  _DWORD *v14; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v15[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v16; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v17)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+38h] BYREF

  v17 = a1;
  v15[0] = 1;
  v15[1] = 27;
  v16 = L"Windows.Data.Json.JsonValue";
  v14 = v15;
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(&v17, &v14);
  v5 = (signed __int64)v17;
  if ( !v17 || (v18 = 0, (**v17)(v17, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v18), !v18) )
  {
    v18 = 0;
    v11 = 602;
    v12 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
    v13 = 0;
    v8 = *a3;
    LOBYTE(v8) = **a3;
    v9 = (*(__int64 (__fastcall **)(signed __int64, _BYTE *, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, v8, &v18);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v11);
    *a2 = v18;
    goto LABEL_10;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
  _InterlockedIncrement64(&qword_18005FAC8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v17 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18005FAD0);
    v5 = 0;
  }
  v18 = 0;
  v11 = 602;
  v12 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
  v13 = 0;
  v6 = *a3;
  LOBYTE(v6) = **a3;
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                              + 64LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         v6,
         &v18);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v11);
  *a2 = v18;
  _InterlockedDecrement64(&qword_18005FAC8);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v17);
  return a2;
}

```

## disassembly

```asm
0x180014e40  mov     [rsp-18h+arg_8], rbx
0x180014e45  mov     [rsp-18h+arg_0], rcx
0x180014e4a  push    rbp
0x180014e4b  push    rsi
0x180014e4c  push    rdi
0x180014e4d  mov     rbp, rsp
0x180014e50  sub     rsp, 70h
0x180014e54  mov     rsi, r8
0x180014e57  mov     rbx, rdx
0x180014e5a  mov     [rbp+var_20], 1
0x180014e61  mov     [rbp+var_1C], 1Bh
0x180014e68  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x180014e6f  mov     [rbp+var_10], rax
0x180014e73  lea     rax, [rbp+var_20]
0x180014e77  mov     [rbp+var_28], rax
0x180014e7b  lea     rdx, [rbp+var_28]
0x180014e7f  lea     rcx, [rbp+arg_0]
0x180014e83  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180014e88  nop
0x180014e89  mov     rdi, [rbp+arg_0]
0x180014e8d  test    rdi, rdi
0x180014e90  jz      loc_180014F6A
0x180014e96  mov     [rbp+arg_18], 0
0x180014e9e  mov     rax, [rdi]
0x180014ea1  lea     r8, [rbp+arg_18]
0x180014ea5  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180014eac  mov     rcx, rdi
0x180014eaf  mov     rax, [rax]
0x180014eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eb7  mov     rax, [rbp+arg_18]
0x180014ebb  mov     [rbp+arg_18], rax
0x180014ebf  test    rax, rax
0x180014ec2  jz      loc_180014F6A
0x180014ec8  lea     rcx, [rbp+arg_18]
0x180014ecc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180014ed1  lea     rax, qword_18005FAC8
0x180014ed8  mov     [rbp+var_48], rax
0x180014edc  lock inc cs:qword_18005FAC8
0x180014ee4  xor     eax, eax
0x180014ee6  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180014eef  jnz     short loc_180014F0E
0x180014ef1  mov     [rbp+arg_0], 0
0x180014ef9  lea     rdx, stru_18005FAD0; ListEntry
0x180014f00  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180014f07  call    WINRT_IMPL_InterlockedPushEntrySList
0x180014f0c  xor     edi, edi
0x180014f0e  mov     [rbp+arg_18], 0
0x180014f16  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180014f1d  mov     [rbp+var_40], 25Ah
0x180014f24  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180014f2b  mov     [rbp+var_38], rax
0x180014f2f  mov     [rbp+var_30], 0
0x180014f37  mov     rax, [rcx]
0x180014f3a  mov     rdx, [rsi]
0x180014f3d  lea     r8, [rbp+arg_18]
0x180014f41  mov     dl, [rdx]
0x180014f43  mov     rax, [rax+40h]
0x180014f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f4c  test    eax, eax
0x180014f4e  js      loc_180014FD7
0x180014f54  mov     rax, [rbp+arg_18]
0x180014f58  mov     [rbx], rax
0x180014f5b  lock dec cs:qword_18005FAC8
0x180014f63  test    rdi, rdi
0x180014f66  jz      short loc_180014FB8
0x180014f68  jmp     short loc_180014FAF
0x180014f6a  mov     [rbp+arg_18], 0
0x180014f72  mov     [rbp+var_40], 25Ah
0x180014f79  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180014f80  mov     [rbp+var_38], rax
0x180014f84  mov     [rbp+var_30], 0
0x180014f8c  mov     rax, [rdi]
0x180014f8f  mov     rdx, [rsi]
0x180014f92  lea     r8, [rbp+arg_18]
0x180014f96  mov     dl, [rdx]
0x180014f98  mov     rcx, rdi
0x180014f9b  mov     rax, [rax+40h]
0x180014f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fa4  test    eax, eax
0x180014fa6  js      short loc_180014FCB
0x180014fa8  mov     rax, [rbp+arg_18]
0x180014fac  mov     [rbx], rax
0x180014faf  lea     rcx, [rbp+arg_0]
0x180014fb3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180014fb8  mov     rax, rbx
0x180014fbb  mov     rbx, [rsp+70h+arg_8]
0x180014fc3  add     rsp, 70h
0x180014fc7  pop     rdi
0x180014fc8  pop     rsi
0x180014fc9  pop     rbp
0x180014fca  retn
0x180014fcb  lea     rdx, [rbp+var_40]
0x180014fcf  mov     ecx, eax
0x180014fd1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180014fd7  lea     rdx, [rbp+var_40]
0x180014fdb  mov     ecx, eax
0x180014fdd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
