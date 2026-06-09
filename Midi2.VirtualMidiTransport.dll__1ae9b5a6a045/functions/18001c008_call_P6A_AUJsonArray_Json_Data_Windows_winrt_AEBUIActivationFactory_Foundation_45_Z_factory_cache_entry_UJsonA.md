# ??$call@P6A?AUJsonArray@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonArray@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x18001c008`
- end: `0x18001c124`
- name: `??$call@P6A?AUJsonArray@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonArray@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d680`

## callees

- `0x1800047ed`
- `0x18001a798`
- `0x18001c008`
- `0x18001c3bc`
- `0x180021010`

## string_xrefs

- `0x18001c033`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonArray (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _DWORD *v6; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-10h]
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+60h] [rbp+10h] BYREF
  __int64 *v10; // [rsp+78h] [rbp+28h] BYREF

  v9 = a1;
  v7[0] = 1;
  v7[1] = 27;
  v8 = L"Windows.Data.Json.JsonArray";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_18002DA48;
    _InterlockedIncrement64(&qword_18002DA48);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002DA50);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18002DA48);
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
0x18001c008  mov     [rsp-8+arg_8], rbx
0x18001c00d  mov     [rsp-8+arg_10], rdi
0x18001c012  mov     [rsp-8+arg_0], rcx
0x18001c017  push    rbp
0x18001c018  mov     rbp, rsp
0x18001c01b  sub     rsp, 50h
0x18001c01f  mov     rdi, r8
0x18001c022  mov     rbx, rdx
0x18001c025  mov     [rbp+var_20], 1
0x18001c02c  mov     [rbp+var_1C], 1Bh
0x18001c033  lea     rax, aWindowsDataJso_1; "Windows.Data.Json.JsonArray"
0x18001c03a  mov     [rbp+var_10], rax
0x18001c03e  lea     rax, [rbp+var_20]
0x18001c042  mov     [rbp+var_28], rax
0x18001c046  lea     rdx, [rbp+var_28]
0x18001c04a  lea     rcx, [rbp+arg_0]
0x18001c04e  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18001c053  nop
0x18001c054  mov     rcx, [rbp+arg_0]
0x18001c058  test    rcx, rcx
0x18001c05b  jz      loc_18001C0F1
0x18001c061  mov     [rbp+arg_18], 0
0x18001c069  mov     rax, [rcx]
0x18001c06c  lea     r8, [rbp+arg_18]
0x18001c070  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c077  mov     rax, [rax]
0x18001c07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c07f  mov     rax, [rbp+arg_18]
0x18001c083  mov     [rbp+arg_18], rax
0x18001c087  test    rax, rax
0x18001c08a  jz      short loc_18001C0F1
0x18001c08c  lea     rcx, [rbp+arg_18]
0x18001c090  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c095  lea     rax, qword_18002DA48
0x18001c09c  mov     [rbp+arg_18], rax
0x18001c0a0  lock inc cs:qword_18002DA48
0x18001c0a8  mov     rcx, [rbp+arg_0]
0x18001c0ac  xor     eax, eax
0x18001c0ae  lock cmpxchg cs:??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x18001c0b7  jnz     short loc_18001C0D4
0x18001c0b9  mov     [rbp+arg_0], 0
0x18001c0c1  lea     rdx, stru_18002DA50; ListEntry
0x18001c0c8  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c0cf  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c0d4  lea     rdx, ??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x18001c0db  mov     rcx, rbx
0x18001c0de  mov     rax, [rdi]
0x18001c0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0e6  nop
0x18001c0e7  lock dec cs:qword_18002DA48
0x18001c0ef  jmp     short loc_18001C101
0x18001c0f1  lea     rdx, [rbp+arg_0]
0x18001c0f5  mov     rcx, rbx
0x18001c0f8  mov     rax, [rdi]
0x18001c0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c100  nop
0x18001c101  cmp     [rbp+arg_0], 0
0x18001c106  jz      short loc_18001C111
0x18001c108  lea     rcx, [rbp+arg_0]
0x18001c10c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c111  mov     rax, rbx
0x18001c114  mov     rbx, [rsp+50h+arg_8]
0x18001c119  mov     rdi, [rsp+50h+arg_10]
0x18001c11e  add     rsp, 50h
0x18001c122  pop     rbp
0x18001c123  retn
```
