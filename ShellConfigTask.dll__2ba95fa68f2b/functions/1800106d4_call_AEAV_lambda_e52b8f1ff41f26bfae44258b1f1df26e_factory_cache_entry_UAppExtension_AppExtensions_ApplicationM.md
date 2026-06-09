# ??$call@AEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@Z

- ea: `0x1800106d4`
- end: `0x180010868`
- name: `??$call@AEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@Z`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014f9c`

## callees

- `0x180003bb1`
- `0x1800106d4`
- `0x180011f78`
- `0x180024b4c`
- `0x180024f28`
- `0x180033010`

## string_xrefs

- `0x1800106fc`: `WindowsUdk.ApplicationModel.AppExtensions.AppExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>::call<_lambda_e52b8f1ff41f26bfae44258b1f1df26e_ &>(
        __int64 *a1,
        unsigned int **a2)
{
  signed __int64 v3; // rbx
  __int64 result; // rax
  int v5; // eax
  int v6; // [rsp+20h] [rbp-40h] BYREF
  __int128 v7; // [rsp+28h] [rbp-38h]
  _DWORD *v8; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v9[4]; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v10; // [rsp+50h] [rbp-10h]
  __int64 *v11; // [rsp+70h] [rbp+10h] BYREF
  __int64 *v12; // [rsp+80h] [rbp+20h] BYREF

  v11 = a1;
  v9[0] = 1;
  v9[1] = 54;
  v10 = L"WindowsUdk.ApplicationModel.AppExtensions.AppExtension";
  v8 = v9;
  v12 = 0;
  v6 = 0;
  v7 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v8,
    (__int64)winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>,
    (__int64)&v12);
  if ( (int)v11 < 0 )
    winrt::throw_hresult((unsigned int)v11, &v6);
  v3 = (signed __int64)v12;
  v11 = v12;
  if ( !v12
    || (v12 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, __int64 **))v3)(
          v3,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v12),
        !v12) )
  {
    v6 = 0;
    v7 = 0;
    v5 = (*(__int64 (__fastcall **)(signed __int64, _QWORD))(*(_QWORD *)v3 + 48LL))(v3, **a2);
    if ( v5 < 0 )
      winrt::throw_hresult((unsigned int)v5, &v6);
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  v12 = &qword_1800420B8;
  _InterlockedIncrement64(&qword_1800420B8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>,
          v3,
          0) )
  {
    v3 = 0;
    v11 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800420C0);
  }
  v6 = 0;
  v7 = 0;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
                                                      + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>,
             **a2);
  if ( (int)result < 0 )
    winrt::throw_hresult((unsigned int)result, &v6);
  _InterlockedDecrement64(&qword_1800420B8);
  if ( v3 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  return result;
}

```

## disassembly

```asm
0x1800106d4  mov     [rsp-8+arg_8], rbx
0x1800106d9  mov     [rsp-8+arg_18], rdi
0x1800106de  mov     [rsp-8+arg_0], rcx
0x1800106e3  push    rbp
0x1800106e4  mov     rbp, rsp
0x1800106e7  sub     rsp, 60h
0x1800106eb  mov     rdi, rdx
0x1800106ee  mov     [rbp+var_20], 1
0x1800106f5  mov     [rbp+var_1C], 36h ; '6'
0x1800106fc  lea     rax, aWindowsudkAppl; "WindowsUdk.ApplicationModel.AppExtensio"...
0x180010703  mov     [rbp+var_10], rax
0x180010707  lea     rax, [rbp+var_20]
0x18001070b  mov     [rbp+var_28], rax
0x18001070f  mov     [rbp+arg_10], 0
0x180010717  mov     [rbp+var_40], 0
0x18001071e  xorps   xmm0, xmm0
0x180010721  movdqu  [rbp+var_38], xmm0
0x180010726  lea     r9, [rbp+arg_10]
0x18001072a  lea     r8, ??$guid_v@UIAppExtensionStatics2@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
0x180010731  lea     rdx, [rbp+var_28]
0x180010735  lea     rcx, [rbp+arg_0]
0x180010739  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001073e  mov     ecx, dword ptr [rbp+arg_0]
0x180010741  test    ecx, ecx
0x180010743  js      loc_180010852
0x180010749  mov     rbx, [rbp+arg_10]
0x18001074d  mov     [rbp+arg_0], rbx
0x180010751  test    rbx, rbx
0x180010754  jz      loc_180010804
0x18001075a  mov     [rbp+arg_10], 0
0x180010762  mov     rax, [rbx]
0x180010765  lea     r8, [rbp+arg_10]
0x180010769  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180010770  mov     rcx, rbx
0x180010773  mov     rax, [rax]
0x180010776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001077b  mov     rax, [rbp+arg_10]
0x18001077f  mov     [rbp+arg_10], rax
0x180010783  test    rax, rax
0x180010786  jz      short loc_180010804
0x180010788  lea     rcx, [rbp+arg_10]
0x18001078c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010791  lea     rax, qword_1800420B8
0x180010798  mov     [rbp+arg_10], rax
0x18001079c  lock inc cs:qword_1800420B8
0x1800107a4  xor     eax, eax
0x1800107a6  lock cmpxchg cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@12@A, rbx; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
0x1800107af  jnz     short loc_1800107CA
0x1800107b1  xor     ebx, ebx
0x1800107b3  mov     [rbp+arg_0], rbx
0x1800107b7  lea     rdx, stru_1800420C0; ListEntry
0x1800107be  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800107c5  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800107ca  mov     rcx, cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
0x1800107d1  mov     [rbp+var_40], 0
0x1800107d8  xorps   xmm0, xmm0
0x1800107db  movdqu  [rbp+var_38], xmm0
0x1800107e0  mov     rax, [rcx]
0x1800107e3  mov     rdx, [rdi]
0x1800107e6  mov     edx, [rdx]
0x1800107e8  mov     rax, [rax+30h]
0x1800107ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107f1  test    eax, eax
0x1800107f3  js      short loc_18001085C
0x1800107f5  lock dec cs:qword_1800420B8
0x1800107fd  test    rbx, rbx
0x180010800  jz      short loc_180010834
0x180010802  jmp     short loc_18001082B
0x180010804  mov     [rbp+var_40], 0
0x18001080b  xorps   xmm0, xmm0
0x18001080e  movdqu  [rbp+var_38], xmm0
0x180010813  mov     rax, [rbx]
0x180010816  mov     rdx, [rdi]
0x180010819  mov     edx, [rdx]
0x18001081b  mov     rcx, rbx
0x18001081e  mov     rax, [rax+30h]
0x180010822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010827  test    eax, eax
0x180010829  js      short loc_180010846
0x18001082b  lea     rcx, [rbp+arg_0]
0x18001082f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010834  lea     r11, [rsp+60h+var_s0]
0x180010839  mov     rbx, [r11+18h]
0x18001083d  mov     rdi, [r11+28h]
0x180010841  mov     rsp, r11
0x180010844  pop     rbp
0x180010845  retn
0x180010846  lea     rdx, [rbp+var_40]
0x18001084a  mov     ecx, eax
0x18001084c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180010852  lea     rdx, [rbp+var_40]
0x180010856  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001085c  lea     rdx, [rbp+var_40]
0x180010860  mov     ecx, eax
0x180010862  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
