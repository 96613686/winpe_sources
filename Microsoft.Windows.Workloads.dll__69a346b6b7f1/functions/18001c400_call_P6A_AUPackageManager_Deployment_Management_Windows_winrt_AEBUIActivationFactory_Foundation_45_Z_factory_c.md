# ??$call@P6A?AUPackageManager@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManager@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x18001c400`
- end: `0x18001c555`
- name: `??$call@P6A?AUPackageManager@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManager@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015e40`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180014870`
- `0x18001c400`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

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
    v11 = &qword_180059F48;
    _InterlockedIncrement64(&qword_180059F48);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v12,
            0) )
    {
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180059F50);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180059F48);
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
0x18001c400  mov     [rsp-18h+arg_0], rbx
0x18001c405  push    rbp
0x18001c406  push    rsi
0x18001c407  push    rdi
0x18001c408  mov     rbp, rsp
0x18001c40b  sub     rsp, 60h
0x18001c40f  mov     rax, cs:__security_cookie
0x18001c416  xor     rax, rsp
0x18001c419  mov     [rbp+var_8], rax
0x18001c41d  mov     rdi, r8
0x18001c420  mov     rbx, rdx
0x18001c423  mov     [rbp+var_18], rdx
0x18001c427  xor     esi, esi
0x18001c429  mov     [rbp+var_30], 1
0x18001c430  mov     [rbp+var_2C], 2Ch ; ','
0x18001c437  lea     rax, aWindowsManagem; "Windows.Management.Deployment.PackageMa"...
0x18001c43e  mov     [rbp+var_20], rax
0x18001c442  lea     rax, [rbp+var_30]
0x18001c446  mov     [rbp+var_38], rax
0x18001c44a  mov     [rbp+var_18], rsi
0x18001c44e  lea     r9, [rbp+var_18]
0x18001c452  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; "5"
0x18001c459  lea     rdx, [rbp+var_38]
0x18001c45d  lea     rcx, [rbp+var_40]
0x18001c461  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001c466  mov     ecx, [rbp+var_40]
0x18001c469  test    ecx, ecx
0x18001c46b  js      loc_18001C54C
0x18001c471  mov     rcx, [rbp+var_18]
0x18001c475  mov     [rbp+var_10], rcx
0x18001c479  test    rcx, rcx
0x18001c47c  jz      loc_18001C50C
0x18001c482  mov     [rbp+var_18], rsi
0x18001c486  mov     rax, [rcx]
0x18001c489  lea     r8, [rbp+var_18]
0x18001c48d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c494  mov     rax, [rax]
0x18001c497  call    cs:__guard_dispatch_icall_fptr
0x18001c49d  mov     rax, [rbp+var_18]
0x18001c4a1  mov     [rbp+var_18], rax
0x18001c4a5  test    rax, rax
0x18001c4a8  jz      short loc_18001C50C
0x18001c4aa  lea     rcx, [rbp+var_18]
0x18001c4ae  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c4b3  lea     rax, qword_180059F48
0x18001c4ba  mov     [rbp+var_18], rax
0x18001c4be  lock inc cs:qword_180059F48
0x18001c4c6  mov     rcx, [rbp+var_10]
0x18001c4ca  xor     eax, eax
0x18001c4cc  lock cmpxchg cs:??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x18001c4d5  jnz     short loc_18001C4EE
0x18001c4d7  mov     [rbp+var_10], rsi
0x18001c4db  lea     rdx, stru_180059F50; ListEntry
0x18001c4e2  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c4e9  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c4ee  lea     rdx, ??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x18001c4f5  mov     rcx, rbx
0x18001c4f8  mov     rax, [rdi]
0x18001c4fb  call    cs:__guard_dispatch_icall_fptr
0x18001c501  nop
0x18001c502  lock dec cs:qword_180059F48
0x18001c50a  jmp     short loc_18001C51D
0x18001c50c  lea     rdx, [rbp+var_10]
0x18001c510  mov     rcx, rbx
0x18001c513  mov     rax, [rdi]
0x18001c516  call    cs:__guard_dispatch_icall_fptr
0x18001c51c  nop
0x18001c51d  cmp     [rbp+var_10], 0
0x18001c522  jz      short loc_18001C52D
0x18001c524  lea     rcx, [rbp+var_10]
0x18001c528  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c52d  mov     rax, rbx
0x18001c530  mov     rcx, [rbp+var_8]
0x18001c534  xor     rcx, rsp; StackCookie
0x18001c537  call    __security_check_cookie
0x18001c53c  mov     rbx, [rsp+60h+arg_0]
0x18001c544  add     rsp, 60h
0x18001c548  pop     rdi
0x18001c549  pop     rsi
0x18001c54a  pop     rbp
0x18001c54b  retn
0x18001c54c  lfence
0x18001c54f  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
