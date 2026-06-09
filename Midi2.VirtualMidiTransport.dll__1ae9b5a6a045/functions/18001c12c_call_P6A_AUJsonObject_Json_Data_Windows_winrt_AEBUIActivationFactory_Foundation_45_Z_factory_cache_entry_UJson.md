# ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x18001c12c`
- end: `0x18001c248`
- name: `??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `284`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d184`
- `0x18001d680`

## callees

- `0x1800047ed`
- `0x18001a798`
- `0x18001c12c`
- `0x18001c3bc`
- `0x180021010`

## string_xrefs

- `0x18001c157`: `Windows.Data.Json.JsonObject`

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
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+60h] [rbp+10h] BYREF
  __int64 *v10; // [rsp+78h] [rbp+28h] BYREF

  v9 = a1;
  v7[0] = 1;
  v7[1] = 28;
  v8 = L"Windows.Data.Json.JsonObject";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_18002DA68;
    _InterlockedIncrement64(&qword_18002DA68);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002DA70);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18002DA68);
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
0x18001c12c  mov     [rsp-8+arg_8], rbx
0x18001c131  mov     [rsp-8+arg_10], rdi
0x18001c136  mov     [rsp-8+arg_0], rcx
0x18001c13b  push    rbp
0x18001c13c  mov     rbp, rsp
0x18001c13f  sub     rsp, 50h
0x18001c143  mov     rdi, r8
0x18001c146  mov     rbx, rdx
0x18001c149  mov     [rbp+var_20], 1
0x18001c150  mov     [rbp+var_1C], 1Ch
0x18001c157  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x18001c15e  mov     [rbp+var_10], rax
0x18001c162  lea     rax, [rbp+var_20]
0x18001c166  mov     [rbp+var_28], rax
0x18001c16a  lea     rdx, [rbp+var_28]
0x18001c16e  lea     rcx, [rbp+arg_0]
0x18001c172  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18001c177  nop
0x18001c178  mov     rcx, [rbp+arg_0]
0x18001c17c  test    rcx, rcx
0x18001c17f  jz      loc_18001C215
0x18001c185  mov     [rbp+arg_18], 0
0x18001c18d  mov     rax, [rcx]
0x18001c190  lea     r8, [rbp+arg_18]
0x18001c194  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c19b  mov     rax, [rax]
0x18001c19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1a3  mov     rax, [rbp+arg_18]
0x18001c1a7  mov     [rbp+arg_18], rax
0x18001c1ab  test    rax, rax
0x18001c1ae  jz      short loc_18001C215
0x18001c1b0  lea     rcx, [rbp+arg_18]
0x18001c1b4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c1b9  lea     rax, qword_18002DA68
0x18001c1c0  mov     [rbp+arg_18], rax
0x18001c1c4  lock inc cs:qword_18002DA68
0x18001c1cc  mov     rcx, [rbp+arg_0]
0x18001c1d0  xor     eax, eax
0x18001c1d2  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001c1db  jnz     short loc_18001C1F8
0x18001c1dd  mov     [rbp+arg_0], 0
0x18001c1e5  lea     rdx, stru_18002DA70; ListEntry
0x18001c1ec  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c1f3  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c1f8  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001c1ff  mov     rcx, rbx
0x18001c202  mov     rax, [rdi]
0x18001c205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c20a  nop
0x18001c20b  lock dec cs:qword_18002DA68
0x18001c213  jmp     short loc_18001C225
0x18001c215  lea     rdx, [rbp+arg_0]
0x18001c219  mov     rcx, rbx
0x18001c21c  mov     rax, [rdi]
0x18001c21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c224  nop
0x18001c225  cmp     [rbp+arg_0], 0
0x18001c22a  jz      short loc_18001C235
0x18001c22c  lea     rcx, [rbp+arg_0]
0x18001c230  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c235  mov     rax, rbx
0x18001c238  mov     rbx, [rsp+50h+arg_8]
0x18001c23d  mov     rdi, [rsp+50h+arg_10]
0x18001c242  add     rsp, 50h
0x18001c246  pop     rbp
0x18001c247  retn
```
