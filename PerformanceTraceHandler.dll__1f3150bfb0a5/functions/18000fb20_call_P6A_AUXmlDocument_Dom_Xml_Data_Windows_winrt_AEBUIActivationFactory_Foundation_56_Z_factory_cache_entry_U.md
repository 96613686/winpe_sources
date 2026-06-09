# ??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z

- ea: `0x18000fb20`
- end: `0x18000fc6b`
- name: `??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64 *, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800106e0`

## callees

- `0x1800038e9`
- `0x180009c74`
- `0x18000fb20`
- `0x18000fc74`
- `0x1800109e8`
- `0x180010a38`
- `0x180012e00`
- `0x18001c010`

## string_xrefs

- `0x18000fb3d`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Xml::Dom::XmlDocument (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        __int64 *a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-48h] BYREF
  int v7; // [rsp+38h] [rbp-38h] BYREF
  __int128 v8; // [rsp+40h] [rbp-30h]
  _BYTE v9[32]; // [rsp+50h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+80h] [rbp+10h] BYREF
  signed __int64 v11; // [rsp+98h] [rbp+28h] BYREF

  v10 = a1;
  v6[0] = L"Windows.Data.Xml.Dom.XmlDocument";
  v6[1] = 32;
  winrt::param::hstring::hstring(v9, v6);
  v6[0] = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<1>(&v10, v9, "5", v6);
  winrt::check_hresult(&v10, (unsigned int)v10, &v7);
  v11 = v6[0];
  if ( v6[0]
    && (v10 = 0,
        (**(void (__fastcall ***)(_QWORD, __int64 *, __int64 **))v6[0])(
          v6[0],
          winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v10),
        v10) )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v10);
    v10 = &qword_180027A58;
    _InterlockedIncrement64(&qword_180027A58);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>,
            v11,
            0) )
    {
      v11 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180027A60);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180027A58);
  }
  else
  {
    (*a3)(a2, &v11);
  }
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v11);
  return a2;
}

```

## disassembly

```asm
0x18000fb20  mov     [rsp-8+arg_8], rbx
0x18000fb25  mov     [rsp-8+arg_10], rdi
0x18000fb2a  mov     [rsp-8+arg_0], rcx
0x18000fb2f  push    rbp
0x18000fb30  mov     rbp, rsp
0x18000fb33  sub     rsp, 70h
0x18000fb37  mov     rdi, r8
0x18000fb3a  mov     rbx, rdx
0x18000fb3d  lea     rax, aWindowsDataXml; "Windows.Data.Xml.Dom.XmlDocument"
0x18000fb44  mov     [rbp+var_48], rax
0x18000fb48  mov     [rbp+var_40], 20h ; ' '
0x18000fb50  lea     rdx, [rbp+var_48]
0x18000fb54  lea     rcx, [rbp+var_20]
0x18000fb58  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000fb5d  mov     [rbp+var_48], 0
0x18000fb65  mov     [rbp+var_38], 0
0x18000fb6c  xorps   xmm0, xmm0
0x18000fb6f  movdqu  [rbp+var_30], xmm0
0x18000fb74  lea     r9, [rbp+var_48]
0x18000fb78  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; "5"
0x18000fb7f  lea     rdx, [rbp+var_20]
0x18000fb83  lea     rcx, [rbp+arg_0]
0x18000fb87  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000fb8c  lea     r8, [rbp+var_38]
0x18000fb90  mov     edx, dword ptr [rbp+arg_0]
0x18000fb93  lea     rcx, [rbp+arg_0]
0x18000fb97  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000fb9c  mov     rcx, [rbp+var_48]
0x18000fba0  mov     [rbp+arg_18], rcx
0x18000fba4  test    rcx, rcx
0x18000fba7  jz      loc_18000FC3D
0x18000fbad  mov     [rbp+arg_0], 0
0x18000fbb5  mov     rax, [rcx]
0x18000fbb8  lea     r8, [rbp+arg_0]
0x18000fbbc  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000fbc3  mov     rax, [rax]
0x18000fbc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbcb  mov     rax, [rbp+arg_0]
0x18000fbcf  mov     [rbp+arg_0], rax
0x18000fbd3  test    rax, rax
0x18000fbd6  jz      short loc_18000FC3D
0x18000fbd8  lea     rcx, [rbp+arg_0]
0x18000fbdc  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000fbe1  lea     rax, qword_180027A58
0x18000fbe8  mov     [rbp+arg_0], rax
0x18000fbec  lock inc cs:qword_180027A58
0x18000fbf4  mov     rcx, [rbp+arg_18]
0x18000fbf8  xor     eax, eax
0x18000fbfa  lock cmpxchg cs:??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x18000fc03  jnz     short loc_18000FC20
0x18000fc05  mov     [rbp+arg_18], 0
0x18000fc0d  lea     rdx, stru_180027A60; ListEntry
0x18000fc14  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000fc1b  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000fc20  lea     rdx, ??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x18000fc27  mov     rcx, rbx
0x18000fc2a  mov     rax, [rdi]
0x18000fc2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc32  nop
0x18000fc33  lock dec cs:qword_180027A58
0x18000fc3b  jmp     short loc_18000FC4D
0x18000fc3d  lea     rdx, [rbp+arg_18]
0x18000fc41  mov     rcx, rbx
0x18000fc44  mov     rax, [rdi]
0x18000fc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc4c  nop
0x18000fc4d  lea     rcx, [rbp+arg_18]
0x18000fc51  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x18000fc56  mov     rax, rbx
0x18000fc59  lea     r11, [rsp+70h+var_s0]
0x18000fc5e  mov     rbx, [r11+18h]
0x18000fc62  mov     rdi, [r11+20h]
0x18000fc66  mov     rsp, r11
0x18000fc69  pop     rbp
0x18000fc6a  retn
```
