# ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x1800152f8`
- end: `0x18001545b`
- name: `??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `355`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800167c4`
- `0x180018090`
- `0x180018710`

## callees

- `0x1800051fd`
- `0x1800145d8`
- `0x180014974`
- `0x1800152f8`
- `0x180015efc`
- `0x180032010`

## string_xrefs

- `0x180015323`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        __int64 *a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 **); // [rsp+28h] [rbp-48h] BYREF
  int v7; // [rsp+30h] [rbp-40h] BYREF
  const char *v8; // [rsp+38h] [rbp-38h]
  __int64 v9; // [rsp+40h] [rbp-30h]
  _DWORD *v10; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v11[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v12; // [rsp+60h] [rbp-10h]
  __int64 *v13; // [rsp+80h] [rbp+10h] BYREF
  void (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // [rsp+98h] [rbp+28h] BYREF

  v13 = a1;
  v11[0] = 1;
  v11[1] = 28;
  v12 = L"Windows.Data.Json.JsonObject";
  v10 = v11;
  v6 = 0;
  v7 = 6172;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/base.h";
  v9 = 0;
  winrt::impl::get_runtime_activation_factory_impl<1>(
    &v13,
    &v10,
    (__int64)winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>,
    &v6);
  if ( (int)v13 < 0 )
    winrt::throw_hresult((unsigned int)v13, &v7);
  v14 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v6;
  if ( v6 && (v13 = 0, (**v6)(v6, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v13), v13) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
    v13 = &qword_18005FA88;
    _InterlockedIncrement64(&qword_18005FA88);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v14,
            0) )
    {
      v14 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18005FA90);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18005FA88);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v14);
  }
  if ( v14 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x1800152f8  mov     [rsp-8+arg_8], rbx
0x1800152fd  mov     [rsp-8+arg_10], rdi
0x180015302  mov     [rsp-8+arg_0], rcx
0x180015307  push    rbp
0x180015308  mov     rbp, rsp
0x18001530b  sub     rsp, 70h
0x18001530f  mov     rdi, r8
0x180015312  mov     rbx, rdx
0x180015315  mov     [rbp+var_20], 1
0x18001531c  mov     [rbp+var_1C], 1Ch
0x180015323  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x18001532a  mov     [rbp+var_10], rax
0x18001532e  lea     rax, [rbp+var_20]
0x180015332  mov     [rbp+var_28], rax
0x180015336  mov     [rbp+var_48], 0
0x18001533e  mov     [rbp+var_40], 181Ch
0x180015345  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001534c  mov     [rbp+var_38], rax
0x180015350  mov     [rbp+var_30], 0
0x180015358  lea     r9, [rbp+var_48]
0x18001535c  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>
0x180015363  lea     rdx, [rbp+var_28]
0x180015367  lea     rcx, [rbp+arg_0]
0x18001536b  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180015370  mov     ecx, dword ptr [rbp+arg_0]
0x180015373  test    ecx, ecx
0x180015375  js      loc_180015451
0x18001537b  mov     rcx, [rbp+var_48]
0x18001537f  mov     [rbp+arg_18], rcx
0x180015383  test    rcx, rcx
0x180015386  jz      loc_18001541C
0x18001538c  mov     [rbp+arg_0], 0
0x180015394  mov     rax, [rcx]
0x180015397  lea     r8, [rbp+arg_0]
0x18001539b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800153a2  mov     rax, [rax]
0x1800153a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153aa  mov     rax, [rbp+arg_0]
0x1800153ae  mov     [rbp+arg_0], rax
0x1800153b2  test    rax, rax
0x1800153b5  jz      short loc_18001541C
0x1800153b7  lea     rcx, [rbp+arg_0]
0x1800153bb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800153c0  lea     rax, qword_18005FA88
0x1800153c7  mov     [rbp+arg_0], rax
0x1800153cb  lock inc cs:qword_18005FA88
0x1800153d3  mov     rcx, [rbp+arg_18]
0x1800153d7  xor     eax, eax
0x1800153d9  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x1800153e2  jnz     short loc_1800153FF
0x1800153e4  mov     [rbp+arg_18], 0
0x1800153ec  lea     rdx, stru_18005FA90; ListEntry
0x1800153f3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800153fa  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800153ff  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x180015406  mov     rcx, rbx
0x180015409  mov     rax, [rdi]
0x18001540c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015411  nop
0x180015412  lock dec cs:qword_18005FA88
0x18001541a  jmp     short loc_18001542C
0x18001541c  lea     rdx, [rbp+arg_18]
0x180015420  mov     rcx, rbx
0x180015423  mov     rax, [rdi]
0x180015426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001542b  nop
0x18001542c  cmp     [rbp+arg_18], 0
0x180015431  jz      short loc_18001543C
0x180015433  lea     rcx, [rbp+arg_18]
0x180015437  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001543c  mov     rax, rbx
0x18001543f  lea     r11, [rsp+70h+var_s0]
0x180015444  mov     rbx, [r11+18h]
0x180015448  mov     rdi, [r11+20h]
0x18001544c  mov     rsp, r11
0x18001544f  pop     rbp
0x180015450  retn
0x180015451  lea     rdx, [rbp+var_40]
0x180015455  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
