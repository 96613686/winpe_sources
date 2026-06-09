# ??$call@P6A?AUPackageManager@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManager@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x180011aa0`
- end: `0x180011bf5`
- name: `??$call@P6A?AUPackageManager@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManager@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007410`

## callees

- `0x180003840`
- `0x180003ee0`
- `0x180011aa0`
- `0x1800132d0`
- `0x1800181b0`
- `0x18001c567`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Management::Deployment::PackageManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        __int64 a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  __int64 *v5; // rcx
  int v7; // [rsp+20h] [rbp-40h] BYREF
  _DWORD *v8; // [rsp+28h] [rbp-38h] BYREF
  _DWORD v9[4]; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v10; // [rsp+40h] [rbp-20h]
  __int64 *v11; // [rsp+48h] [rbp-18h] BYREF
  __int64 *v12; // [rsp+50h] [rbp-10h] BYREF

  v9[0] = 1;
  v9[1] = 44;
  v10 = L"Windows.Management.Deployment.PackageManager";
  v8 = v9;
  v11 = 0;
  winrt::impl::get_runtime_activation_factory_impl<1>(
    &v7,
    &v8,
    &winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>,
    &v11);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7);
  }
  v5 = v11;
  v12 = v11;
  if ( v11
    && (v11 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
    v11 = &qword_18002E6F8;
    _InterlockedIncrement64(&qword_18002E6F8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v12,
            0) )
    {
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002E700);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18002E6F8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v12);
  }
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  return a2;
}

```

## disassembly

```asm
0x180011aa0  mov     [rsp-18h+arg_0], rbx
0x180011aa5  push    rbp
0x180011aa6  push    rsi
0x180011aa7  push    rdi
0x180011aa8  mov     rbp, rsp
0x180011aab  sub     rsp, 60h
0x180011aaf  mov     rax, cs:__security_cookie
0x180011ab6  xor     rax, rsp
0x180011ab9  mov     [rbp+var_8], rax
0x180011abd  mov     rdi, r8
0x180011ac0  mov     rbx, rdx
0x180011ac3  mov     [rbp+var_18], rdx
0x180011ac7  xor     esi, esi
0x180011ac9  mov     [rbp+var_30], 1
0x180011ad0  mov     [rbp+var_2C], 2Ch ; ','
0x180011ad7  lea     rax, aWindowsManagem; "Windows.Management.Deployment.PackageMa"...
0x180011ade  mov     [rbp+var_20], rax
0x180011ae2  lea     rax, [rbp+var_30]
0x180011ae6  mov     [rbp+var_38], rax
0x180011aea  mov     [rbp+var_18], rsi
0x180011aee  lea     r9, [rbp+var_18]
0x180011af2  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>
0x180011af9  lea     rdx, [rbp+var_38]
0x180011afd  lea     rcx, [rbp+var_40]
0x180011b01  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180011b06  mov     ecx, [rbp+var_40]
0x180011b09  test    ecx, ecx
0x180011b0b  js      loc_180011BEC
0x180011b11  mov     rcx, [rbp+var_18]
0x180011b15  mov     [rbp+var_10], rcx
0x180011b19  test    rcx, rcx
0x180011b1c  jz      loc_180011BAC
0x180011b22  mov     [rbp+var_18], rsi
0x180011b26  mov     rax, [rcx]
0x180011b29  lea     r8, [rbp+var_18]
0x180011b2d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180011b34  mov     rax, [rax]
0x180011b37  call    cs:__guard_dispatch_icall_fptr
0x180011b3d  mov     rax, [rbp+var_18]
0x180011b41  mov     [rbp+var_18], rax
0x180011b45  test    rax, rax
0x180011b48  jz      short loc_180011BAC
0x180011b4a  lea     rcx, [rbp+var_18]
0x180011b4e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011b53  lea     rax, qword_18002E6F8
0x180011b5a  mov     [rbp+var_18], rax
0x180011b5e  lock inc cs:qword_18002E6F8
0x180011b66  mov     rcx, [rbp+var_10]
0x180011b6a  xor     eax, eax
0x180011b6c  lock cmpxchg cs:??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x180011b75  jnz     short loc_180011B8E
0x180011b77  mov     [rbp+var_10], rsi
0x180011b7b  lea     rdx, stru_18002E700; ListEntry
0x180011b82  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180011b89  call    WINRT_IMPL_InterlockedPushEntrySList
0x180011b8e  lea     rdx, ??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x180011b95  mov     rcx, rbx
0x180011b98  mov     rax, [rdi]
0x180011b9b  call    cs:__guard_dispatch_icall_fptr
0x180011ba1  nop
0x180011ba2  lock dec cs:qword_18002E6F8
0x180011baa  jmp     short loc_180011BBD
0x180011bac  lea     rdx, [rbp+var_10]
0x180011bb0  mov     rcx, rbx
0x180011bb3  mov     rax, [rdi]
0x180011bb6  call    cs:__guard_dispatch_icall_fptr
0x180011bbc  nop
0x180011bbd  cmp     [rbp+var_10], 0
0x180011bc2  jz      short loc_180011BCD
0x180011bc4  lea     rcx, [rbp+var_10]
0x180011bc8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011bcd  mov     rax, rbx
0x180011bd0  mov     rcx, [rbp+var_8]
0x180011bd4  xor     rcx, rsp; StackCookie
0x180011bd7  call    __security_check_cookie
0x180011bdc  mov     rbx, [rsp+60h+arg_0]
0x180011be4  add     rsp, 60h
0x180011be8  pop     rdi
0x180011be9  pop     rsi
0x180011bea  pop     rbp
0x180011beb  retn
0x180011bec  lfence
0x180011bef  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
