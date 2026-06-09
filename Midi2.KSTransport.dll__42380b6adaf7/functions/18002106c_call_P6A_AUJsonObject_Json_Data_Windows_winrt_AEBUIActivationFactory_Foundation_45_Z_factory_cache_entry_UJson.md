# ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x18002106c`
- end: `0x180021188`
- name: `??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021c3c`

## callees

- `0x1800054a9`
- `0x18000d1c0`
- `0x18002106c`
- `0x1800218f4`
- `0x180041010`

## string_xrefs

- `0x180021097`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    v10 = &qword_180071CA8;
    _InterlockedIncrement64(&qword_180071CA8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180071CB0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180071CA8);
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
0x18002106c  mov     [rsp-8+arg_8], rbx
0x180021071  mov     [rsp-8+arg_10], rdi
0x180021076  mov     [rsp-8+arg_0], rcx
0x18002107b  push    rbp
0x18002107c  mov     rbp, rsp
0x18002107f  sub     rsp, 50h
0x180021083  mov     rdi, r8
0x180021086  mov     rbx, rdx
0x180021089  mov     [rbp+var_20], 1
0x180021090  mov     [rbp+var_1C], 1Ch
0x180021097  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x18002109e  mov     [rbp+var_10], rax
0x1800210a2  lea     rax, [rbp+var_20]
0x1800210a6  mov     [rbp+var_28], rax
0x1800210aa  lea     rdx, [rbp+var_28]
0x1800210ae  lea     rcx, [rbp+arg_0]
0x1800210b2  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x1800210b7  nop
0x1800210b8  mov     rcx, [rbp+arg_0]
0x1800210bc  test    rcx, rcx
0x1800210bf  jz      loc_180021155
0x1800210c5  mov     [rbp+arg_18], 0
0x1800210cd  mov     rax, [rcx]
0x1800210d0  lea     r8, [rbp+arg_18]
0x1800210d4  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800210db  mov     rax, [rax]
0x1800210de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210e3  mov     rax, [rbp+arg_18]
0x1800210e7  mov     [rbp+arg_18], rax
0x1800210eb  test    rax, rax
0x1800210ee  jz      short loc_180021155
0x1800210f0  lea     rcx, [rbp+arg_18]
0x1800210f4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800210f9  lea     rax, qword_180071CA8
0x180021100  mov     [rbp+arg_18], rax
0x180021104  lock inc cs:qword_180071CA8
0x18002110c  mov     rcx, [rbp+arg_0]
0x180021110  xor     eax, eax
0x180021112  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18002111b  jnz     short loc_180021138
0x18002111d  mov     [rbp+arg_0], 0
0x180021125  lea     rdx, stru_180071CB0; ListEntry
0x18002112c  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180021133  call    WINRT_IMPL_InterlockedPushEntrySList
0x180021138  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18002113f  mov     rcx, rbx
0x180021142  mov     rax, [rdi]
0x180021145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002114a  nop
0x18002114b  lock dec cs:qword_180071CA8
0x180021153  jmp     short loc_180021165
0x180021155  lea     rdx, [rbp+arg_0]
0x180021159  mov     rcx, rbx
0x18002115c  mov     rax, [rdi]
0x18002115f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021164  nop
0x180021165  cmp     [rbp+arg_0], 0
0x18002116a  jz      short loc_180021175
0x18002116c  lea     rcx, [rbp+arg_0]
0x180021170  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021175  mov     rax, rbx
0x180021178  mov     rbx, [rsp+50h+arg_8]
0x18002117d  mov     rdi, [rsp+50h+arg_10]
0x180021182  add     rsp, 50h
0x180021186  pop     rbp
0x180021187  retn
```
