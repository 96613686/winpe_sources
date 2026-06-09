# ??$call@P6A?AUguid@winrt@@AEBUIGuidHelperStatics@Foundation@Windows@2@@Z@?$factory_cache_entry@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@impl@winrt@@QEAA?A_P$$QEAP6A?AUguid@2@AEBUIGuidHelperStatics@Foundation@Windows@2@@Z@Z

- ea: `0x18001c250`
- end: `0x18001c3b3`
- name: `??$call@P6A?AUguid@winrt@@AEBUIGuidHelperStatics@Foundation@Windows@2@@Z@?$factory_cache_entry@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@impl@winrt@@QEAA?A_P$$QEAP6A?AUguid@2@AEBUIGuidHelperStatics@Foundation@Windows@2@@Z@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001cc70`

## callees

- `0x1800047ed`
- `0x1800130d0`
- `0x18001a3fc`
- `0x18001a798`
- `0x18001c250`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>::call<winrt::guid (*)(winrt::Windows::Foundation::IGuidHelperStatics const &)>(
        __int64 *a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  __int64 v5; // r8
  void (__fastcall ***v7)(_QWORD, __int64 *, __int64 **); // [rsp+20h] [rbp-40h] BYREF
  unsigned int v8; // [rsp+28h] [rbp-38h] BYREF
  const char *v9; // [rsp+30h] [rbp-30h]
  __int64 v10; // [rsp+38h] [rbp-28h]
  _DWORD *v11; // [rsp+40h] [rbp-20h] BYREF
  _DWORD v12[4]; // [rsp+48h] [rbp-18h] BYREF
  const wchar_t *v13; // [rsp+58h] [rbp-8h]
  __int64 *v14; // [rsp+70h] [rbp+10h] BYREF
  void (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // [rsp+88h] [rbp+28h] BYREF

  v14 = a1;
  v12[0] = 1;
  v12[1] = 29;
  v13 = L"Windows.Foundation.GuidHelper";
  v11 = v12;
  v7 = 0;
  v8 = 6172;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/base.h";
  v10 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v11,
    (__int64)winrt::impl::guid_v<winrt::Windows::Foundation::IGuidHelperStatics>,
    (__int64)&v7);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v8, v5);
  v15 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v7;
  if ( v7 && (v14 = 0, (**v7)(v7, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v14), v14) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v14);
    v14 = &qword_18002DA08;
    _InterlockedIncrement64(&qword_18002DA08);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>,
            (signed __int64)v15,
            0) )
    {
      v15 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002DA10);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>);
    _InterlockedDecrement64(&qword_18002DA08);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v15);
  }
  if ( v15 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v15);
  return a2;
}

```

## disassembly

```asm
0x18001c250  mov     [rsp-8+arg_8], rbx
0x18001c255  mov     [rsp-8+arg_10], rdi
0x18001c25a  mov     [rsp-8+arg_0], rcx
0x18001c25f  push    rbp
0x18001c260  mov     rbp, rsp
0x18001c263  sub     rsp, 60h
0x18001c267  mov     rdi, r8
0x18001c26a  mov     rbx, rdx
0x18001c26d  mov     [rbp+var_18], 1
0x18001c274  mov     [rbp+var_14], 1Dh
0x18001c27b  lea     rax, aWindowsFoundat; "Windows.Foundation.GuidHelper"
0x18001c282  mov     [rbp+var_8], rax
0x18001c286  lea     rax, [rbp+var_18]
0x18001c28a  mov     [rbp+var_20], rax
0x18001c28e  mov     [rbp+var_40], 0
0x18001c296  mov     [rbp+var_38], 181Ch
0x18001c29d  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001c2a4  mov     [rbp+var_30], rax
0x18001c2a8  mov     [rbp+var_28], 0
0x18001c2b0  lea     r9, [rbp+var_40]
0x18001c2b4  lea     r8, ??$guid_v@UIGuidHelperStatics@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IGuidHelperStatics>
0x18001c2bb  lea     rdx, [rbp+var_20]
0x18001c2bf  lea     rcx, [rbp+arg_0]
0x18001c2c3  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001c2c8  mov     ecx, dword ptr [rbp+arg_0]
0x18001c2cb  test    ecx, ecx
0x18001c2cd  js      loc_18001C3A9
0x18001c2d3  mov     rcx, [rbp+var_40]
0x18001c2d7  mov     [rbp+arg_18], rcx
0x18001c2db  test    rcx, rcx
0x18001c2de  jz      loc_18001C374
0x18001c2e4  mov     [rbp+arg_0], 0
0x18001c2ec  mov     rax, [rcx]
0x18001c2ef  lea     r8, [rbp+arg_0]
0x18001c2f3  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c2fa  mov     rax, [rax]
0x18001c2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c302  mov     rax, [rbp+arg_0]
0x18001c306  mov     [rbp+arg_0], rax
0x18001c30a  test    rax, rax
0x18001c30d  jz      short loc_18001C374
0x18001c30f  lea     rcx, [rbp+arg_0]
0x18001c313  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c318  lea     rax, qword_18002DA08
0x18001c31f  mov     [rbp+arg_0], rax
0x18001c323  lock inc cs:qword_18002DA08
0x18001c32b  mov     rcx, [rbp+arg_18]
0x18001c32f  xor     eax, eax
0x18001c331  lock cmpxchg cs:??$factory_cache_entry_v@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@impl@winrt@@3U?$factory_cache_entry@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@12@A, rcx; factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>
0x18001c33a  jnz     short loc_18001C357
0x18001c33c  mov     [rbp+arg_18], 0
0x18001c344  lea     rdx, stru_18002DA10; ListEntry
0x18001c34b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c352  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c357  lea     rdx, ??$factory_cache_entry_v@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@impl@winrt@@3U?$factory_cache_entry@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>
0x18001c35e  mov     rcx, rbx
0x18001c361  mov     rax, [rdi]
0x18001c364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c369  nop
0x18001c36a  lock dec cs:qword_18002DA08
0x18001c372  jmp     short loc_18001C384
0x18001c374  lea     rdx, [rbp+arg_18]
0x18001c378  mov     rcx, rbx
0x18001c37b  mov     rax, [rdi]
0x18001c37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c383  nop
0x18001c384  cmp     [rbp+arg_18], 0
0x18001c389  jz      short loc_18001C394
0x18001c38b  lea     rcx, [rbp+arg_18]
0x18001c38f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c394  mov     rax, rbx
0x18001c397  lea     r11, [rsp+60h+var_s0]
0x18001c39c  mov     rbx, [r11+18h]
0x18001c3a0  mov     rdi, [r11+20h]
0x18001c3a4  mov     rsp, r11
0x18001c3a7  pop     rbp
0x18001c3a8  retn
0x18001c3a9  lea     rdx, [rbp+var_38]
0x18001c3ad  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
