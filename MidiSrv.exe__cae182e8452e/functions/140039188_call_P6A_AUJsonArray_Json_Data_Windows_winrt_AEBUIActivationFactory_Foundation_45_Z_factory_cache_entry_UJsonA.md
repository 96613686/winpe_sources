# ??$call@P6A?AUJsonArray@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonArray@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x140039188`
- end: `0x1400392a7`
- name: `??$call@P6A?AUJsonArray@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonArray@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `287`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003a960`

## callees

- `0x140006310`
- `0x14000cc2c`
- `0x14002260c`
- `0x140039188`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400391ad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400391ad`

## string_xrefs

- `0x1400391c2`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonArray (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
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
  if ( aWindowsDataJso_1[27] )
    abort();
  v7[0] = 1;
  v7[1] = 27;
  v8 = L"Windows.Data.Json.JsonArray";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_140096A58;
    _InterlockedIncrement64(&qword_140096A58);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140096A60);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_140096A58);
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
0x140039188  mov     [rsp-18h+arg_8], rbx
0x14003918d  mov     [rsp-18h+arg_0], rcx
0x140039192  push    rbp
0x140039193  push    rsi
0x140039194  push    rdi
0x140039195  mov     rbp, rsp
0x140039198  sub     rsp, 50h
0x14003919c  mov     rdi, r8
0x14003919f  mov     rbx, rdx
0x1400391a2  xor     esi, esi
0x1400391a4  cmp     word ptr cs:aWindowsDataJso_1+36h, si; ""
0x1400391ab  jz      short loc_1400391B4
0x1400391ad  call    cs:__imp_abort
0x1400391b4  mov     [rbp+var_20], 1
0x1400391bb  mov     [rbp+var_1C], 1Bh
0x1400391c2  lea     rax, aWindowsDataJso_1; "Windows.Data.Json.JsonArray"
0x1400391c9  mov     [rbp+var_10], rax
0x1400391cd  lea     rax, [rbp+var_20]
0x1400391d1  mov     [rbp+var_28], rax
0x1400391d5  lea     rdx, [rbp+var_28]
0x1400391d9  lea     rcx, [rbp+arg_0]
0x1400391dd  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x1400391e2  nop
0x1400391e3  mov     rcx, [rbp+arg_0]
0x1400391e7  test    rcx, rcx
0x1400391ea  jz      loc_140039278
0x1400391f0  mov     [rbp+arg_18], rsi
0x1400391f4  mov     rax, [rcx]
0x1400391f7  lea     r8, [rbp+arg_18]
0x1400391fb  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140039202  mov     rax, [rax]
0x140039205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003920a  mov     rax, [rbp+arg_18]
0x14003920e  mov     [rbp+arg_18], rax
0x140039212  test    rax, rax
0x140039215  jz      short loc_140039278
0x140039217  lea     rcx, [rbp+arg_18]
0x14003921b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140039220  lea     rax, qword_140096A58
0x140039227  mov     [rbp+arg_18], rax
0x14003922b  lock inc cs:qword_140096A58
0x140039233  mov     rcx, [rbp+arg_0]
0x140039237  xor     eax, eax
0x140039239  lock cmpxchg cs:??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x140039242  jnz     short loc_14003925B
0x140039244  mov     [rbp+arg_0], rsi
0x140039248  lea     rdx, stru_140096A60; ListEntry
0x14003924f  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x140039256  call    WINRT_IMPL_InterlockedPushEntrySList
0x14003925b  lea     rdx, ??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x140039262  mov     rcx, rbx
0x140039265  mov     rax, [rdi]
0x140039268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003926d  nop
0x14003926e  lock dec cs:qword_140096A58
0x140039276  jmp     short loc_140039288
0x140039278  lea     rdx, [rbp+arg_0]
0x14003927c  mov     rcx, rbx
0x14003927f  mov     rax, [rdi]
0x140039282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039287  nop
0x140039288  cmp     [rbp+arg_0], rsi
0x14003928c  jz      short loc_140039297
0x14003928e  lea     rcx, [rbp+arg_0]
0x140039292  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140039297  mov     rax, rbx
0x14003929a  mov     rbx, [rsp+50h+arg_8]
0x14003929f  add     rsp, 50h
0x1400392a3  pop     rdi
0x1400392a4  pop     rsi
0x1400392a5  pop     rbp
0x1400392a6  retn
```
