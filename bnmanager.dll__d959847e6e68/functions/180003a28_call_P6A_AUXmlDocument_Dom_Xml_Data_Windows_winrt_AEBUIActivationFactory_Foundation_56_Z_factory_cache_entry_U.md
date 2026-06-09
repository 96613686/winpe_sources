# ??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z

- ea: `0x180003a28`
- end: `0x180003b7c`
- name: `??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z`
- size: `340`
- prototype: `__int64 __fastcall(__int64 *, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007250`

## callees

- `0x1800023ad`
- `0x180003a28`
- `0x180003be4`
- `0x18000bde4`
- `0x18000c010`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180003a4d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180003a4d`

## string_xrefs

- `0x180003a62`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Xml::Dom::XmlDocument (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        __int64 *a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 **); // [rsp+28h] [rbp-48h] BYREF
  int v7; // [rsp+30h] [rbp-40h] BYREF
  __int128 v8; // [rsp+38h] [rbp-38h]
  _DWORD *v9; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v10[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v11; // [rsp+60h] [rbp-10h]
  __int64 *v12; // [rsp+90h] [rbp+20h] BYREF
  void (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // [rsp+A8h] [rbp+38h] BYREF

  v12 = a1;
  if ( aWindowsDataXml[32] )
    abort();
  v10[0] = 1;
  v10[1] = 32;
  v11 = L"Windows.Data.Xml.Dom.XmlDocument";
  v9 = v10;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<1>(
    &v12,
    &v9,
    winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>,
    &v6);
  if ( (int)v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v7);
  v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v6;
  if ( v6 && (v12 = 0, (**v6)(v6, winrt::impl::guid_v<winrt::impl::IAgileObject>, &v12), v12) )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v12);
    v12 = &qword_180014768;
    _InterlockedIncrement64(&qword_180014768);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v13,
            0) )
    {
      v13 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180014770);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180014768);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v13);
  }
  if ( v13 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v13);
  return a2;
}

```

## disassembly

```asm
0x180003a28  mov     [rsp-18h+arg_8], rbx
0x180003a2d  mov     [rsp-18h+arg_0], rcx
0x180003a32  push    rbp
0x180003a33  push    rsi
0x180003a34  push    rdi
0x180003a35  mov     rbp, rsp
0x180003a38  sub     rsp, 70h
0x180003a3c  mov     rdi, r8
0x180003a3f  mov     rbx, rdx
0x180003a42  xor     esi, esi
0x180003a44  cmp     word ptr cs:aWindowsDataXml+40h, si; ""
0x180003a4b  jz      short loc_180003A54
0x180003a4d  call    cs:__imp_abort
0x180003a54  mov     [rbp+var_20], 1
0x180003a5b  mov     [rbp+var_1C], 20h ; ' '
0x180003a62  lea     rax, aWindowsDataXml; "Windows.Data.Xml.Dom.XmlDocument"
0x180003a69  mov     [rbp+var_10], rax
0x180003a6d  lea     rax, [rbp+var_20]
0x180003a71  mov     [rbp+var_28], rax
0x180003a75  mov     [rbp+var_48], rsi
0x180003a79  mov     [rbp+var_40], esi
0x180003a7c  xorps   xmm0, xmm0
0x180003a7f  movdqu  [rbp+var_38], xmm0
0x180003a84  lea     r9, [rbp+var_48]
0x180003a88  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>
0x180003a8f  lea     rdx, [rbp+var_28]
0x180003a93  lea     rcx, [rbp+arg_0]
0x180003a97  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180003a9c  mov     ecx, dword ptr [rbp+arg_0]
0x180003a9f  test    ecx, ecx
0x180003aa1  js      loc_180003B72
0x180003aa7  mov     rcx, [rbp+var_48]
0x180003aab  mov     [rbp+arg_18], rcx
0x180003aaf  test    rcx, rcx
0x180003ab2  jz      loc_180003B40
0x180003ab8  mov     [rbp+arg_0], rsi
0x180003abc  mov     rax, [rcx]
0x180003abf  lea     r8, [rbp+arg_0]
0x180003ac3  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180003aca  mov     rax, [rax]
0x180003acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad2  mov     rax, [rbp+arg_0]
0x180003ad6  mov     [rbp+arg_0], rax
0x180003ada  test    rax, rax
0x180003add  jz      short loc_180003B40
0x180003adf  lea     rcx, [rbp+arg_0]
0x180003ae3  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180003ae8  lea     rax, qword_180014768
0x180003aef  mov     [rbp+arg_0], rax
0x180003af3  lock inc cs:qword_180014768
0x180003afb  mov     rcx, [rbp+arg_18]
0x180003aff  xor     eax, eax
0x180003b01  lock cmpxchg cs:??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x180003b0a  jnz     short loc_180003B23
0x180003b0c  mov     [rbp+arg_18], rsi
0x180003b10  lea     rdx, stru_180014770; ListEntry
0x180003b17  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180003b1e  call    WINRT_IMPL_InterlockedPushEntrySList
0x180003b23  lea     rdx, ??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x180003b2a  mov     rcx, rbx
0x180003b2d  mov     rax, [rdi]
0x180003b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b35  nop
0x180003b36  lock dec cs:qword_180014768
0x180003b3e  jmp     short loc_180003B50
0x180003b40  lea     rdx, [rbp+arg_18]
0x180003b44  mov     rcx, rbx
0x180003b47  mov     rax, [rdi]
0x180003b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b4f  nop
0x180003b50  cmp     [rbp+arg_18], rsi
0x180003b54  jz      short loc_180003B5F
0x180003b56  lea     rcx, [rbp+arg_18]
0x180003b5a  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180003b5f  mov     rax, rbx
0x180003b62  mov     rbx, [rsp+70h+arg_8]
0x180003b6a  add     rsp, 70h
0x180003b6e  pop     rdi
0x180003b6f  pop     rsi
0x180003b70  pop     rbp
0x180003b71  retn
0x180003b72  lea     rdx, [rbp+var_40]
0x180003b76  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
