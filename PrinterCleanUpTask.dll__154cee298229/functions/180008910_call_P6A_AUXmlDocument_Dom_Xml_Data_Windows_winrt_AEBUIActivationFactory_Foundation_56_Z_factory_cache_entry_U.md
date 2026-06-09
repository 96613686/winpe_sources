# ??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z

- ea: `0x180008910`
- end: `0x180008a26`
- name: `??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z`
- size: `278`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c84`

## callees

- `0x180003495`
- `0x18000750c`
- `0x180008910`
- `0x180008c20`
- `0x18000a2b0`
- `0x18000a360`
- `0x180018010`

## string_xrefs

- `0x18000892d`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Xml::Dom::XmlDocument (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.Data.Xml.Dom.XmlDocument";
  v6[1] = 32;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    v9 = &qword_1800227D8;
    _InterlockedIncrement64(&qword_1800227D8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800227E0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_1800227D8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v8);
  return a2;
}

```

## disassembly

```asm
0x180008910  mov     [rsp-8+arg_8], rbx
0x180008915  mov     [rsp-8+arg_10], rdi
0x18000891a  mov     [rsp-8+arg_0], rcx
0x18000891f  push    rbp
0x180008920  mov     rbp, rsp
0x180008923  sub     rsp, 60h
0x180008927  mov     rdi, r8
0x18000892a  mov     rbx, rdx
0x18000892d  lea     rax, aWindowsDataXml; "Windows.Data.Xml.Dom.XmlDocument"
0x180008934  mov     [rbp+var_38], rax
0x180008938  mov     [rbp+var_30], 20h ; ' '
0x180008940  lea     rdx, [rbp+var_38]
0x180008944  lea     rcx, [rbp+var_28]
0x180008948  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000894d  lea     rdx, [rbp+var_28]
0x180008951  lea     rcx, [rbp+arg_0]
0x180008955  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18000895a  nop
0x18000895b  mov     rcx, [rbp+arg_0]
0x18000895f  test    rcx, rcx
0x180008962  jz      loc_1800089F8
0x180008968  mov     [rbp+arg_18], 0
0x180008970  mov     rax, [rcx]
0x180008973  lea     r8, [rbp+arg_18]
0x180008977  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000897e  mov     rax, [rax]
0x180008981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008986  mov     rax, [rbp+arg_18]
0x18000898a  mov     [rbp+arg_18], rax
0x18000898e  test    rax, rax
0x180008991  jz      short loc_1800089F8
0x180008993  lea     rcx, [rbp+arg_18]
0x180008997  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000899c  lea     rax, qword_1800227D8
0x1800089a3  mov     [rbp+arg_18], rax
0x1800089a7  lock inc cs:qword_1800227D8
0x1800089af  mov     rcx, [rbp+arg_0]
0x1800089b3  xor     eax, eax
0x1800089b5  lock cmpxchg cs:??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x1800089be  jnz     short loc_1800089DB
0x1800089c0  mov     [rbp+arg_0], 0
0x1800089c8  lea     rdx, stru_1800227E0; ListEntry
0x1800089cf  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800089d6  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800089db  lea     rdx, ??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x1800089e2  mov     rcx, rbx
0x1800089e5  mov     rax, [rdi]
0x1800089e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ed  nop
0x1800089ee  lock dec cs:qword_1800227D8
0x1800089f6  jmp     short loc_180008A08
0x1800089f8  lea     rdx, [rbp+arg_0]
0x1800089fc  mov     rcx, rbx
0x1800089ff  mov     rax, [rdi]
0x180008a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a07  nop
0x180008a08  lea     rcx, [rbp+arg_0]; this
0x180008a0c  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180008a11  mov     rax, rbx
0x180008a14  lea     r11, [rsp+60h+var_s0]
0x180008a19  mov     rbx, [r11+18h]
0x180008a1d  mov     rdi, [r11+20h]
0x180008a21  mov     rsp, r11
0x180008a24  pop     rbp
0x180008a25  retn
```
