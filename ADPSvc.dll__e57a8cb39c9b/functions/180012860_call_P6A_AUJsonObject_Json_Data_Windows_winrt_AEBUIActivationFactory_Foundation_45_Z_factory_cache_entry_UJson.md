# ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x180012860`
- end: `0x1800129c3`
- name: `??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `355`
- prototype: `__int64 __fastcall(__int64 *, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016ae4`

## callees

- `0x180003ab9`
- `0x180007b84`
- `0x180011c3c`
- `0x180012860`
- `0x1800129cc`
- `0x1800ca010`

## string_xrefs

- `0x18001288b`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
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
    &winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>,
    &v6);
  if ( (int)v13 < 0 )
    winrt::throw_hresult((unsigned int)v13, &v7);
  v14 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v6;
  if ( v6 && (v13 = 0, (**v6)(v6, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v13), v13) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
    v13 = &qword_18010F7B8;
    _InterlockedIncrement64(&qword_18010F7B8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v14,
            0) )
    {
      v14 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18010F7C0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18010F7B8);
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
0x180012860  mov     [rsp-8+arg_8], rbx
0x180012865  mov     [rsp-8+arg_10], rdi
0x18001286a  mov     [rsp-8+arg_0], rcx
0x18001286f  push    rbp
0x180012870  mov     rbp, rsp
0x180012873  sub     rsp, 70h
0x180012877  mov     rdi, r8
0x18001287a  mov     rbx, rdx
0x18001287d  mov     [rbp+var_20], 1
0x180012884  mov     [rbp+var_1C], 1Ch
0x18001288b  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x180012892  mov     [rbp+var_10], rax
0x180012896  lea     rax, [rbp+var_20]
0x18001289a  mov     [rbp+var_28], rax
0x18001289e  mov     [rbp+var_48], 0
0x1800128a6  mov     [rbp+var_40], 181Ch
0x1800128ad  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800128b4  mov     [rbp+var_38], rax
0x1800128b8  mov     [rbp+var_30], 0
0x1800128c0  lea     r9, [rbp+var_48]
0x1800128c4  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>
0x1800128cb  lea     rdx, [rbp+var_28]
0x1800128cf  lea     rcx, [rbp+arg_0]
0x1800128d3  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x1800128d8  mov     ecx, dword ptr [rbp+arg_0]
0x1800128db  test    ecx, ecx
0x1800128dd  js      loc_1800129B9
0x1800128e3  mov     rcx, [rbp+var_48]
0x1800128e7  mov     [rbp+arg_18], rcx
0x1800128eb  test    rcx, rcx
0x1800128ee  jz      loc_180012984
0x1800128f4  mov     [rbp+arg_0], 0
0x1800128fc  mov     rax, [rcx]
0x1800128ff  lea     r8, [rbp+arg_0]
0x180012903  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001290a  mov     rax, [rax]
0x18001290d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012912  mov     rax, [rbp+arg_0]
0x180012916  mov     [rbp+arg_0], rax
0x18001291a  test    rax, rax
0x18001291d  jz      short loc_180012984
0x18001291f  lea     rcx, [rbp+arg_0]
0x180012923  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012928  lea     rax, qword_18010F7B8
0x18001292f  mov     [rbp+arg_0], rax
0x180012933  lock inc cs:qword_18010F7B8
0x18001293b  mov     rcx, [rbp+arg_18]
0x18001293f  xor     eax, eax
0x180012941  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001294a  jnz     short loc_180012967
0x18001294c  mov     [rbp+arg_18], 0
0x180012954  lea     rdx, stru_18010F7C0; ListEntry
0x18001295b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180012962  call    WINRT_IMPL_InterlockedPushEntrySList
0x180012967  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001296e  mov     rcx, rbx
0x180012971  mov     rax, [rdi]
0x180012974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012979  nop
0x18001297a  lock dec cs:qword_18010F7B8
0x180012982  jmp     short loc_180012994
0x180012984  lea     rdx, [rbp+arg_18]
0x180012988  mov     rcx, rbx
0x18001298b  mov     rax, [rdi]
0x18001298e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012993  nop
0x180012994  cmp     [rbp+arg_18], 0
0x180012999  jz      short loc_1800129A4
0x18001299b  lea     rcx, [rbp+arg_18]
0x18001299f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800129a4  mov     rax, rbx
0x1800129a7  lea     r11, [rsp+70h+var_s0]
0x1800129ac  mov     rbx, [r11+18h]
0x1800129b0  mov     rdi, [r11+20h]
0x1800129b4  mov     rsp, r11
0x1800129b7  pop     rbp
0x1800129b8  retn
0x1800129b9  lea     rdx, [rbp+var_40]
0x1800129bd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
