# ??$call@P6A?AU?$IAsyncOperation@_N@Foundation@Windows@winrt@@AEBUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@4@@Z@?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperation@_N@Foundation@Windows@2@AEBUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@2@@Z@Z

- ea: `0x180047c14`
- end: `0x180047d4b`
- name: `??$call@P6A?AU?$IAsyncOperation@_N@Foundation@Windows@winrt@@AEBUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@4@@Z@?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperation@_N@Foundation@Windows@2@AEBUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@2@@Z@Z`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180047d54`

## callees

- `0x18002d1a4`
- `0x180047c14`
- `0x180047e08`
- `0x180056500`
- `0x18005c27a`
- `0x18005c5e0`

## string_xrefs

- `0x180047c4c`: `WindowsUdk.Management.Update.FeatureStagingManager`

## pseudocode

```c
__int64 *__fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>::call<winrt::Windows::Foundation::IAsyncOperation<bool> (*)(winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics const &)>(
        __int64 a1,
        __int64 *a2,
        void (__fastcall **a3)(__int64 *, __int64 *))
{
  _DWORD *v6; // [rsp+28h] [rbp-38h] BYREF
  _DWORD v7[4]; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-20h]
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+48h] [rbp-18h] BYREF
  __int64 *v10; // [rsp+50h] [rbp-10h] BYREF

  v10 = a2;
  v7[0] = 1;
  v7[1] = 50;
  v8 = L"WindowsUdk.Management.Update.FeatureStagingManager";
  v6 = v7;
  winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_18009FB18;
    _InterlockedIncrement64(&qword_18009FB18);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18009FB20);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>);
    _InterlockedDecrement64(&qword_18009FB18);
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
0x180047c14  mov     [rsp-8+arg_0], rbx
0x180047c19  mov     [rsp-8+arg_18], rdi
0x180047c1e  push    rbp
0x180047c1f  mov     rbp, rsp
0x180047c22  sub     rsp, 60h
0x180047c26  mov     rax, cs:__security_cookie
0x180047c2d  xor     rax, rsp
0x180047c30  mov     [rbp+var_8], rax
0x180047c34  mov     rdi, r8
0x180047c37  mov     rbx, rdx
0x180047c3a  mov     [rbp+var_10], rdx
0x180047c3e  mov     [rbp+var_30], 1
0x180047c45  mov     [rbp+var_2C], 32h ; '2'
0x180047c4c  lea     rax, aWindowsudkMana; "WindowsUdk.Management.Update.FeatureSta"...
0x180047c53  mov     [rbp+var_20], rax
0x180047c57  lea     rax, [rbp+var_30]
0x180047c5b  mov     [rbp+var_38], rax
0x180047c5f  lea     rdx, [rbp+var_38]
0x180047c63  lea     rcx, [rbp+var_18]
0x180047c67  call    ??$get_activation_factory@UIFeatureStagingManagerStatics@Update@Management@WindowsUdk@winrt@@@winrt@@YA?AUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>(winrt::param::hstring const &)
0x180047c6c  nop
0x180047c6d  mov     rcx, [rbp+var_18]
0x180047c71  test    rcx, rcx
0x180047c74  jz      loc_180047D0A
0x180047c7a  mov     [rbp+var_10], 0
0x180047c82  mov     rax, [rcx]
0x180047c85  lea     r8, [rbp+var_10]
0x180047c89  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180047c90  mov     rax, [rax]
0x180047c93  call    _guard_dispatch_icall
0x180047c98  mov     rax, [rbp+var_10]
0x180047c9c  mov     [rbp+var_10], rax
0x180047ca0  test    rax, rax
0x180047ca3  jz      short loc_180047D0A
0x180047ca5  lea     rcx, [rbp+var_10]
0x180047ca9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180047cae  lea     rax, qword_18009FB18
0x180047cb5  mov     [rbp+var_10], rax
0x180047cb9  lock inc cs:qword_18009FB18
0x180047cc1  mov     rcx, [rbp+var_18]
0x180047cc5  xor     eax, eax
0x180047cc7  lock cmpxchg cs:??$factory_cache_entry_v@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@12@A, rcx; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>
0x180047cd0  jnz     short loc_180047CED
0x180047cd2  mov     [rbp+var_18], 0
0x180047cda  lea     rdx, stru_18009FB20; ListEntry
0x180047ce1  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180047ce8  call    WINRT_IMPL_InterlockedPushEntrySList
0x180047ced  lea     rdx, ??$factory_cache_entry_v@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>
0x180047cf4  mov     rcx, rbx
0x180047cf7  mov     rax, [rdi]
0x180047cfa  call    _guard_dispatch_icall
0x180047cff  nop
0x180047d00  lock dec cs:qword_18009FB18
0x180047d08  jmp     short loc_180047D1A
0x180047d0a  lea     rdx, [rbp+var_18]
0x180047d0e  mov     rcx, rbx
0x180047d11  mov     rax, [rdi]
0x180047d14  call    _guard_dispatch_icall
0x180047d19  nop
0x180047d1a  cmp     [rbp+var_18], 0
0x180047d1f  jz      short loc_180047D2A
0x180047d21  lea     rcx, [rbp+var_18]
0x180047d25  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180047d2a  mov     rax, rbx
0x180047d2d  mov     rcx, [rbp+var_8]
0x180047d31  xor     rcx, rsp; StackCookie
0x180047d34  call    __security_check_cookie
0x180047d39  lea     r11, [rsp+60h+var_s0]
0x180047d3e  mov     rbx, [r11+10h]
0x180047d42  mov     rdi, [r11+28h]
0x180047d46  mov     rsp, r11
0x180047d49  pop     rbp
0x180047d4a  retn
```
