# ??$call@AEAV_lambda_1_@?1??CreateBoolean@PropertyValue@Foundation@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBoolean@PropertyValue@Foundation@Windows@2@SA@_N@Z@@Z

- ea: `0x18001c0a0`
- end: `0x18001c22f`
- name: `??$call@AEAV_lambda_1_@?1??CreateBoolean@PropertyValue@Foundation@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBoolean@PropertyValue@Foundation@Windows@2@SA@_N@Z@@Z`
- size: `399`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _BYTE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c758`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000e2c4`
- `0x18001c0a0`
- `0x18002d010`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateBoolean_PropertyValue_Foundation_Windows_winrt__SA__N_Z____factory_cache_entry_UPropertyValue_Foundation_Windows_winrt__UIPropertyValueStatics_234__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateBoolean_PropertyValue_Foundation_Windows_2_SA__N_Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _BYTE **a3)
{
  signed __int64 v5; // rdi
  _BYTE *v6; // rdx
  int v7; // eax
  _BYTE *v8; // rdx
  int v9; // eax
  int v11; // [rsp+30h] [rbp-40h] BYREF
  __int128 v12; // [rsp+38h] [rbp-38h]
  _DWORD *v13; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v14[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v15; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v16)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  v16 = a1;
  v14[0] = 1;
  v14[1] = 32;
  v15 = L"Windows.Foundation.PropertyValue";
  v13 = v14;
  winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(&v16, &v13);
  v5 = (signed __int64)v16;
  if ( !v16 || (v17 = 0, (**v16)(v16, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v17), !v17) )
  {
    v17 = 0;
    v11 = 0;
    v12 = 0;
    v8 = *a3;
    LOBYTE(v8) = **a3;
    v9 = (*(__int64 (__fastcall **)(signed __int64, _BYTE *, __int64 *))(*(_QWORD *)v5 + 136LL))(v5, v8, &v17);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v11);
    *a2 = v17;
    goto LABEL_10;
  }
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v17);
  _InterlockedIncrement64(&qword_18003C1D8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>,
          v5,
          0) )
  {
    v16 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C1E0);
    v5 = 0;
  }
  v17 = 0;
  v11 = 0;
  v12 = 0;
  v6 = *a3;
  LOBYTE(v6) = **a3;
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
                                                              + 136LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>,
         v6,
         &v17);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v11);
  *a2 = v17;
  _InterlockedDecrement64(&qword_18003C1D8);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v16);
  return a2;
}

```

## disassembly

```asm
0x18001c0a0  mov     [rsp-18h+arg_8], rbx
0x18001c0a5  mov     [rsp-18h+arg_0], rcx
0x18001c0aa  push    rbp
0x18001c0ab  push    rsi
0x18001c0ac  push    rdi
0x18001c0ad  mov     rbp, rsp
0x18001c0b0  sub     rsp, 70h
0x18001c0b4  mov     rsi, r8
0x18001c0b7  mov     rbx, rdx
0x18001c0ba  mov     [rbp+var_20], 1
0x18001c0c1  mov     [rbp+var_1C], 20h ; ' '
0x18001c0c8  lea     rax, aWindowsFoundat; "Windows.Foundation.PropertyValue"
0x18001c0cf  mov     [rbp+var_10], rax
0x18001c0d3  lea     rax, [rbp+var_20]
0x18001c0d7  mov     [rbp+var_28], rax
0x18001c0db  lea     rdx, [rbp+var_28]
0x18001c0df  lea     rcx, [rbp+arg_0]
0x18001c0e3  call    ??$get_activation_factory@UIPropertyValueStatics@Foundation@Windows@winrt@@@winrt@@YA?AUIPropertyValueStatics@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(winrt::param::hstring const &)
0x18001c0e8  nop
0x18001c0e9  mov     rdi, [rbp+arg_0]
0x18001c0ed  test    rdi, rdi
0x18001c0f0  jz      loc_18001C1BE
0x18001c0f6  mov     [rbp+arg_18], 0
0x18001c0fe  mov     rax, [rdi]
0x18001c101  lea     r8, [rbp+arg_18]
0x18001c105  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c10c  mov     rcx, rdi
0x18001c10f  mov     rax, [rax]
0x18001c112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c117  mov     rax, [rbp+arg_18]
0x18001c11b  mov     [rbp+arg_18], rax
0x18001c11f  test    rax, rax
0x18001c122  jz      loc_18001C1BE
0x18001c128  lea     rcx, [rbp+arg_18]
0x18001c12c  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c131  lea     rax, qword_18003C1D8
0x18001c138  mov     [rbp+var_48], rax
0x18001c13c  lock inc cs:qword_18003C1D8
0x18001c144  xor     eax, eax
0x18001c146  lock cmpxchg cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x18001c14f  jnz     short loc_18001C16E
0x18001c151  mov     [rbp+arg_0], 0
0x18001c159  lea     rdx, stru_18003C1E0; ListEntry
0x18001c160  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c167  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c16c  xor     edi, edi
0x18001c16e  mov     [rbp+arg_18], 0
0x18001c176  mov     rcx, cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x18001c17d  mov     [rbp+var_40], 0
0x18001c184  xorps   xmm0, xmm0
0x18001c187  movdqu  [rbp+var_38], xmm0
0x18001c18c  mov     rax, [rcx]
0x18001c18f  mov     rdx, [rsi]
0x18001c192  lea     r8, [rbp+arg_18]
0x18001c196  mov     dl, [rdx]
0x18001c198  mov     rax, [rax+88h]
0x18001c19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1a4  test    eax, eax
0x18001c1a6  js      short loc_18001C223
0x18001c1a8  mov     rax, [rbp+arg_18]
0x18001c1ac  mov     [rbx], rax
0x18001c1af  lock dec cs:qword_18003C1D8
0x18001c1b7  test    rdi, rdi
0x18001c1ba  jz      short loc_18001C204
0x18001c1bc  jmp     short loc_18001C1FB
0x18001c1be  mov     [rbp+arg_18], 0
0x18001c1c6  mov     [rbp+var_40], 0
0x18001c1cd  xorps   xmm0, xmm0
0x18001c1d0  movdqu  [rbp+var_38], xmm0
0x18001c1d5  mov     rax, [rdi]
0x18001c1d8  mov     rdx, [rsi]
0x18001c1db  lea     r8, [rbp+arg_18]
0x18001c1df  mov     dl, [rdx]
0x18001c1e1  mov     rcx, rdi
0x18001c1e4  mov     rax, [rax+88h]
0x18001c1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1f0  test    eax, eax
0x18001c1f2  js      short loc_18001C217
0x18001c1f4  mov     rax, [rbp+arg_18]
0x18001c1f8  mov     [rbx], rax
0x18001c1fb  lea     rcx, [rbp+arg_0]
0x18001c1ff  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c204  mov     rax, rbx
0x18001c207  mov     rbx, [rsp+70h+arg_8]
0x18001c20f  add     rsp, 70h
0x18001c213  pop     rdi
0x18001c214  pop     rsi
0x18001c215  pop     rbp
0x18001c216  retn
0x18001c217  lea     rdx, [rbp+var_40]
0x18001c21b  mov     ecx, eax
0x18001c21d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001c223  lea     rdx, [rbp+var_40]
0x18001c227  mov     ecx, eax
0x18001c229  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
