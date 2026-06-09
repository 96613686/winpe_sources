# ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x1400224e4`
- end: `0x140022603`
- name: `??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `287`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140022e58`

## callees

- `0x140006310`
- `0x14000cc2c`
- `0x1400224e4`
- `0x14002260c`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140022509`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140022509`

## string_xrefs

- `0x14002251e`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _DWORD *v6; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-10h]
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+88h] [rbp+38h] BYREF

  v9 = a1;
  if ( aWindowsDataJso[28] )
    abort();
  v7[0] = 1;
  v7[1] = 28;
  v8 = L"Windows.Data.Json.JsonObject";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_140096A78;
    _InterlockedIncrement64(&qword_140096A78);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140096A80);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_140096A78);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v9);
  }
  if ( v9 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x1400224e4  mov     [rsp-18h+arg_8], rbx
0x1400224e9  mov     [rsp-18h+arg_0], rcx
0x1400224ee  push    rbp
0x1400224ef  push    rsi
0x1400224f0  push    rdi
0x1400224f1  mov     rbp, rsp
0x1400224f4  sub     rsp, 50h
0x1400224f8  mov     rdi, r8
0x1400224fb  mov     rbx, rdx
0x1400224fe  xor     esi, esi
0x140022500  cmp     word ptr cs:aWindowsDataJso+38h, si; ""
0x140022507  jz      short loc_140022510
0x140022509  call    cs:__imp_abort
0x140022510  mov     [rbp+var_20], 1
0x140022517  mov     [rbp+var_1C], 1Ch
0x14002251e  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x140022525  mov     [rbp+var_10], rax
0x140022529  lea     rax, [rbp+var_20]
0x14002252d  mov     [rbp+var_28], rax
0x140022531  lea     rdx, [rbp+var_28]
0x140022535  lea     rcx, [rbp+arg_0]
0x140022539  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x14002253e  nop
0x14002253f  mov     rcx, [rbp+arg_0]
0x140022543  test    rcx, rcx
0x140022546  jz      loc_1400225D4
0x14002254c  mov     [rbp+arg_18], rsi
0x140022550  mov     rax, [rcx]
0x140022553  lea     r8, [rbp+arg_18]
0x140022557  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14002255e  mov     rax, [rax]
0x140022561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022566  mov     rax, [rbp+arg_18]
0x14002256a  mov     [rbp+arg_18], rax
0x14002256e  test    rax, rax
0x140022571  jz      short loc_1400225D4
0x140022573  lea     rcx, [rbp+arg_18]
0x140022577  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002257c  lea     rax, qword_140096A78
0x140022583  mov     [rbp+arg_18], rax
0x140022587  lock inc cs:qword_140096A78
0x14002258f  mov     rcx, [rbp+arg_0]
0x140022593  xor     eax, eax
0x140022595  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x14002259e  jnz     short loc_1400225B7
0x1400225a0  mov     [rbp+arg_0], rsi
0x1400225a4  lea     rdx, stru_140096A80; ListEntry
0x1400225ab  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1400225b2  call    WINRT_IMPL_InterlockedPushEntrySList
0x1400225b7  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x1400225be  mov     rcx, rbx
0x1400225c1  mov     rax, [rdi]
0x1400225c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400225c9  nop
0x1400225ca  lock dec cs:qword_140096A78
0x1400225d2  jmp     short loc_1400225E4
0x1400225d4  lea     rdx, [rbp+arg_0]
0x1400225d8  mov     rcx, rbx
0x1400225db  mov     rax, [rdi]
0x1400225de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400225e3  nop
0x1400225e4  cmp     [rbp+arg_0], rsi
0x1400225e8  jz      short loc_1400225F3
0x1400225ea  lea     rcx, [rbp+arg_0]
0x1400225ee  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400225f3  mov     rax, rbx
0x1400225f6  mov     rbx, [rsp+50h+arg_8]
0x1400225fb  add     rsp, 50h
0x1400225ff  pop     rdi
0x140022600  pop     rsi
0x140022601  pop     rbp
0x140022602  retn
```
