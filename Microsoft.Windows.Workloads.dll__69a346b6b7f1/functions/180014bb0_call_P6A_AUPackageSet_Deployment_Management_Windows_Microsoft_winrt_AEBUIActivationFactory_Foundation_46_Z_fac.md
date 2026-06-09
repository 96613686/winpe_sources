# ??$call@P6A?AUPackageSet@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageSet@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x180014bb0`
- end: `0x180014d05`
- name: `??$call@P6A?AUPackageSet@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageSet@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006110`
- `0x180014df0`
- `0x180015e40`
- `0x180016760`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180014870`
- `0x180014bb0`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::Management::Deployment::PackageSet (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
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
  v9[1] = 50;
  v10 = L"Microsoft.Windows.Management.Deployment.PackageSet";
  v8 = v9;
  v11 = 0;
  winrt::impl::get_runtime_activation_factory_impl<1>(&v7, &v8, "5", &v11);
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
    v11 = &qword_180059E98;
    _InterlockedIncrement64(&qword_180059E98);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v12,
            0) )
    {
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180059EA0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180059E98);
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
0x180014bb0  mov     [rsp-18h+arg_0], rbx
0x180014bb5  push    rbp
0x180014bb6  push    rsi
0x180014bb7  push    rdi
0x180014bb8  mov     rbp, rsp
0x180014bbb  sub     rsp, 60h
0x180014bbf  mov     rax, cs:__security_cookie
0x180014bc6  xor     rax, rsp
0x180014bc9  mov     [rbp+var_8], rax
0x180014bcd  mov     rdi, r8
0x180014bd0  mov     rbx, rdx
0x180014bd3  mov     [rbp+var_18], rdx
0x180014bd7  xor     esi, esi
0x180014bd9  mov     [rbp+var_30], 1
0x180014be0  mov     [rbp+var_2C], 32h ; '2'
0x180014be7  lea     rax, aMicrosoftWindo_6; "Microsoft.Windows.Management.Deployment"...
0x180014bee  mov     [rbp+var_20], rax
0x180014bf2  lea     rax, [rbp+var_30]
0x180014bf6  mov     [rbp+var_38], rax
0x180014bfa  mov     [rbp+var_18], rsi
0x180014bfe  lea     r9, [rbp+var_18]
0x180014c02  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; "5"
0x180014c09  lea     rdx, [rbp+var_38]
0x180014c0d  lea     rcx, [rbp+var_40]
0x180014c11  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180014c16  mov     ecx, [rbp+var_40]
0x180014c19  test    ecx, ecx
0x180014c1b  js      loc_180014CFC
0x180014c21  mov     rcx, [rbp+var_18]
0x180014c25  mov     [rbp+var_10], rcx
0x180014c29  test    rcx, rcx
0x180014c2c  jz      loc_180014CBC
0x180014c32  mov     [rbp+var_18], rsi
0x180014c36  mov     rax, [rcx]
0x180014c39  lea     r8, [rbp+var_18]
0x180014c3d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180014c44  mov     rax, [rax]
0x180014c47  call    cs:__guard_dispatch_icall_fptr
0x180014c4d  mov     rax, [rbp+var_18]
0x180014c51  mov     [rbp+var_18], rax
0x180014c55  test    rax, rax
0x180014c58  jz      short loc_180014CBC
0x180014c5a  lea     rcx, [rbp+var_18]
0x180014c5e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180014c63  lea     rax, qword_180059E98
0x180014c6a  mov     [rbp+var_18], rax
0x180014c6e  lock inc cs:qword_180059E98
0x180014c76  mov     rcx, [rbp+var_10]
0x180014c7a  xor     eax, eax
0x180014c7c  lock cmpxchg cs:??$factory_cache_entry_v@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>
0x180014c85  jnz     short loc_180014C9E
0x180014c87  mov     [rbp+var_10], rsi
0x180014c8b  lea     rdx, stru_180059EA0; ListEntry
0x180014c92  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180014c99  call    WINRT_IMPL_InterlockedPushEntrySList
0x180014c9e  lea     rdx, ??$factory_cache_entry_v@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>
0x180014ca5  mov     rcx, rbx
0x180014ca8  mov     rax, [rdi]
0x180014cab  call    cs:__guard_dispatch_icall_fptr
0x180014cb1  nop
0x180014cb2  lock dec cs:qword_180059E98
0x180014cba  jmp     short loc_180014CCD
0x180014cbc  lea     rdx, [rbp+var_10]
0x180014cc0  mov     rcx, rbx
0x180014cc3  mov     rax, [rdi]
0x180014cc6  call    cs:__guard_dispatch_icall_fptr
0x180014ccc  nop
0x180014ccd  cmp     [rbp+var_10], 0
0x180014cd2  jz      short loc_180014CDD
0x180014cd4  lea     rcx, [rbp+var_10]
0x180014cd8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180014cdd  mov     rax, rbx
0x180014ce0  mov     rcx, [rbp+var_8]
0x180014ce4  xor     rcx, rsp; StackCookie
0x180014ce7  call    __security_check_cookie
0x180014cec  mov     rbx, [rsp+60h+arg_0]
0x180014cf4  add     rsp, 60h
0x180014cf8  pop     rdi
0x180014cf9  pop     rsi
0x180014cfa  pop     rbp
0x180014cfb  retn
0x180014cfc  lfence
0x180014cff  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
