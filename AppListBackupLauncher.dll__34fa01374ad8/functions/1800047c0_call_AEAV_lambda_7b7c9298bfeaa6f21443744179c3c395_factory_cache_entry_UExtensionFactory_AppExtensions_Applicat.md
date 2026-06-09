# ??$call@AEAV_lambda_7b7c9298bfeaa6f21443744179c3c395_@@@?$factory_cache_entry@UExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIExtensionFactoryStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_7b7c9298bfeaa6f21443744179c3c395_@@@Z

- ea: `0x1800047c0`
- end: `0x1800049a0`
- name: `??$call@AEAV_lambda_7b7c9298bfeaa6f21443744179c3c395_@@@?$factory_cache_entry@UExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIExtensionFactoryStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_7b7c9298bfeaa6f21443744179c3c395_@@@Z`
- size: `480`
- prototype: `signed __int64 *__fastcall(signed __int64, signed __int64 *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008564`

## callees

- `0x180002f51`
- `0x1800047c0`
- `0x1800049a8`
- `0x18000f214`
- `0x18000f544`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800047f0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800047f0`

## string_xrefs

- `0x180004805`: `WindowsUdk.ApplicationModel.AppExtensions.ExtensionFactory`

## pseudocode

```c
signed __int64 *__fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>::call<_lambda_7b7c9298bfeaa6f21443744179c3c395_ &>(
        signed __int64 a1,
        signed __int64 *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+40h] [rbp-40h] BYREF
  __int128 v10; // [rsp+48h] [rbp-38h]
  _DWORD *v11; // [rsp+58h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+60h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+70h] [rbp-10h]
  signed __int64 v14; // [rsp+A0h] [rbp+20h] BYREF
  signed __int64 v15; // [rsp+B8h] [rbp+38h] BYREF

  v14 = a1;
  if ( aWindowsudkAppl[58] )
    abort();
  v12[0] = 1;
  v12[1] = 58;
  v13 = L"WindowsUdk.ApplicationModel.AppExtensions.ExtensionFactory";
  v11 = v12;
  v15 = 0;
  v9 = 0;
  v10 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v11,
    winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>,
    &v15);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v9);
  v5 = v15;
  v14 = v15;
  if ( !v15
    || (v15 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, signed __int64 *))v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD, signed __int64 *))(*(_QWORD *)v5 + 80LL))(
           v5,
           **a3,
           *a3[1],
           &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_13;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_1800197C8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>,
          v5,
          0) )
  {
    v5 = 0;
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, signed __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>
                                                                            + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>,
         **a3,
         *a3[1],
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_1800197C8);
  if ( v5 )
LABEL_13:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x1800047c0  mov     [rsp-18h+arg_8], rbx
0x1800047c5  mov     [rsp-18h+arg_10], rsi
0x1800047ca  mov     [rsp-18h+arg_0], rcx
0x1800047cf  push    rbp
0x1800047d0  push    rdi
0x1800047d1  push    r14
0x1800047d3  mov     rbp, rsp
0x1800047d6  sub     rsp, 80h
0x1800047dd  mov     rsi, r8
0x1800047e0  mov     rdi, rdx
0x1800047e3  xor     r14d, r14d
0x1800047e6  cmp     word ptr cs:aWindowsudkAppl+74h, r14w; ""
0x1800047ee  jz      short loc_1800047F7
0x1800047f0  call    cs:__imp_abort
0x1800047f7  mov     [rbp+var_20], 1
0x1800047fe  mov     [rbp+var_1C], 3Ah ; ':'
0x180004805  lea     rax, aWindowsudkAppl; "WindowsUdk.ApplicationModel.AppExtensio"...
0x18000480c  mov     [rbp+var_10], rax
0x180004810  lea     rax, [rbp+var_20]
0x180004814  mov     [rbp+var_28], rax
0x180004818  mov     [rbp+arg_18], r14
0x18000481c  mov     [rbp+var_40], r14d
0x180004820  xorps   xmm0, xmm0
0x180004823  movdqu  [rbp+var_38], xmm0
0x180004828  lea     r9, [rbp+arg_18]
0x18000482c  lea     r8, ??$guid_v@UIExtensionFactoryStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>
0x180004833  lea     rdx, [rbp+var_28]
0x180004837  lea     rcx, [rbp+arg_0]
0x18000483b  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180004840  mov     ecx, dword ptr [rbp+arg_0]
0x180004843  test    ecx, ecx
0x180004845  js      loc_18000498A
0x18000484b  mov     rbx, [rbp+arg_18]
0x18000484f  mov     [rbp+arg_0], rbx
0x180004853  test    rbx, rbx
0x180004856  jz      loc_18000491F
0x18000485c  mov     [rbp+arg_18], r14
0x180004860  mov     rax, [rbx]
0x180004863  lea     r8, [rbp+arg_18]
0x180004867  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000486e  mov     rcx, rbx
0x180004871  mov     rax, [rax]
0x180004874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004879  mov     rax, [rbp+arg_18]
0x18000487d  mov     [rbp+arg_18], rax
0x180004881  test    rax, rax
0x180004884  jz      loc_18000491F
0x18000488a  lea     rcx, [rbp+arg_18]
0x18000488e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004893  lea     rax, qword_1800197C8
0x18000489a  mov     [rbp+var_48], rax
0x18000489e  lock inc cs:qword_1800197C8
0x1800048a6  xor     eax, eax
0x1800048a8  lock cmpxchg cs:??$factory_cache_entry_v@UExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIExtensionFactoryStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIExtensionFactoryStatics@2345@@12@A, rbx; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>
0x1800048b1  jnz     short loc_1800048CD
0x1800048b3  mov     rbx, r14
0x1800048b6  mov     [rbp+arg_0], rbx
0x1800048ba  lea     rdx, ListEntry; ListEntry
0x1800048c1  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800048c8  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800048cd  mov     [rbp+arg_18], r14
0x1800048d1  mov     rcx, cs:??$factory_cache_entry_v@UExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIExtensionFactoryStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIExtensionFactoryStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>
0x1800048d8  mov     [rbp+var_40], r14d
0x1800048dc  xorps   xmm0, xmm0
0x1800048df  movdqu  [rbp+var_38], xmm0
0x1800048e4  mov     rax, [rcx]
0x1800048e7  mov     r8, [rsi+8]
0x1800048eb  mov     rdx, [rsi]
0x1800048ee  lea     r9, [rbp+arg_18]
0x1800048f2  mov     r8, [r8]
0x1800048f5  mov     rdx, [rdx]
0x1800048f8  mov     rax, [rax+50h]
0x1800048fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004901  test    eax, eax
0x180004903  js      loc_180004994
0x180004909  mov     rax, [rbp+arg_18]
0x18000490d  mov     [rdi], rax
0x180004910  lock dec cs:qword_1800197C8
0x180004918  test    rbx, rbx
0x18000491b  jz      short loc_180004963
0x18000491d  jmp     short loc_18000495A
0x18000491f  mov     [rbp+arg_18], r14
0x180004923  mov     [rbp+var_40], r14d
0x180004927  xorps   xmm0, xmm0
0x18000492a  movdqu  [rbp+var_38], xmm0
0x18000492f  mov     rax, [rbx]
0x180004932  mov     r8, [rsi+8]
0x180004936  mov     rdx, [rsi]
0x180004939  lea     r9, [rbp+arg_18]
0x18000493d  mov     r8, [r8]
0x180004940  mov     rdx, [rdx]
0x180004943  mov     rcx, rbx
0x180004946  mov     rax, [rax+50h]
0x18000494a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000494f  test    eax, eax
0x180004951  js      short loc_18000497E
0x180004953  mov     rax, [rbp+arg_18]
0x180004957  mov     [rdi], rax
0x18000495a  lea     rcx, [rbp+arg_0]
0x18000495e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004963  mov     rax, rdi
0x180004966  lea     r11, [rsp+80h+var_s0]
0x18000496e  mov     rbx, [r11+28h]
0x180004972  mov     rsi, [r11+30h]
0x180004976  mov     rsp, r11
0x180004979  pop     r14
0x18000497b  pop     rdi
0x18000497c  pop     rbp
0x18000497d  retn
0x18000497e  lea     rdx, [rbp+var_40]
0x180004982  mov     ecx, eax
0x180004984  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000498a  lea     rdx, [rbp+var_40]
0x18000498e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180004994  lea     rdx, [rbp+var_40]
0x180004998  mov     ecx, eax
0x18000499a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
