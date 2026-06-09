# ??$call@P6A?AUPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageSetItem@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x180013c10`
- end: `0x180013d65`
- name: `??$call@P6A?AUPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageSetItem@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006110`
- `0x180013e50`
- `0x180016760`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180013c10`
- `0x180014870`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
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
  v9[1] = 54;
  v10 = L"Microsoft.Windows.Management.Deployment.PackageSetItem";
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
    v11 = &qword_180059E58;
    _InterlockedIncrement64(&qword_180059E58);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v12,
            0) )
    {
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180059E60);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180059E58);
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
0x180013c10  mov     [rsp-18h+arg_0], rbx
0x180013c15  push    rbp
0x180013c16  push    rsi
0x180013c17  push    rdi
0x180013c18  mov     rbp, rsp
0x180013c1b  sub     rsp, 60h
0x180013c1f  mov     rax, cs:__security_cookie
0x180013c26  xor     rax, rsp
0x180013c29  mov     [rbp+var_8], rax
0x180013c2d  mov     rdi, r8
0x180013c30  mov     rbx, rdx
0x180013c33  mov     [rbp+var_18], rdx
0x180013c37  xor     esi, esi
0x180013c39  mov     [rbp+var_30], 1
0x180013c40  mov     [rbp+var_2C], 36h ; '6'
0x180013c47  lea     rax, aMicrosoftWindo_22; "Microsoft.Windows.Management.Deployment"...
0x180013c4e  mov     [rbp+var_20], rax
0x180013c52  lea     rax, [rbp+var_30]
0x180013c56  mov     [rbp+var_38], rax
0x180013c5a  mov     [rbp+var_18], rsi
0x180013c5e  lea     r9, [rbp+var_18]
0x180013c62  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; "5"
0x180013c69  lea     rdx, [rbp+var_38]
0x180013c6d  lea     rcx, [rbp+var_40]
0x180013c71  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180013c76  mov     ecx, [rbp+var_40]
0x180013c79  test    ecx, ecx
0x180013c7b  js      loc_180013D5C
0x180013c81  mov     rcx, [rbp+var_18]
0x180013c85  mov     [rbp+var_10], rcx
0x180013c89  test    rcx, rcx
0x180013c8c  jz      loc_180013D1C
0x180013c92  mov     [rbp+var_18], rsi
0x180013c96  mov     rax, [rcx]
0x180013c99  lea     r8, [rbp+var_18]
0x180013c9d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180013ca4  mov     rax, [rax]
0x180013ca7  call    cs:__guard_dispatch_icall_fptr
0x180013cad  mov     rax, [rbp+var_18]
0x180013cb1  mov     [rbp+var_18], rax
0x180013cb5  test    rax, rax
0x180013cb8  jz      short loc_180013D1C
0x180013cba  lea     rcx, [rbp+var_18]
0x180013cbe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013cc3  lea     rax, qword_180059E58
0x180013cca  mov     [rbp+var_18], rax
0x180013cce  lock inc cs:qword_180059E58
0x180013cd6  mov     rcx, [rbp+var_10]
0x180013cda  xor     eax, eax
0x180013cdc  lock cmpxchg cs:??$factory_cache_entry_v@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>
0x180013ce5  jnz     short loc_180013CFE
0x180013ce7  mov     [rbp+var_10], rsi
0x180013ceb  lea     rdx, stru_180059E60; ListEntry
0x180013cf2  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180013cf9  call    WINRT_IMPL_InterlockedPushEntrySList
0x180013cfe  lea     rdx, ??$factory_cache_entry_v@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>
0x180013d05  mov     rcx, rbx
0x180013d08  mov     rax, [rdi]
0x180013d0b  call    cs:__guard_dispatch_icall_fptr
0x180013d11  nop
0x180013d12  lock dec cs:qword_180059E58
0x180013d1a  jmp     short loc_180013D2D
0x180013d1c  lea     rdx, [rbp+var_10]
0x180013d20  mov     rcx, rbx
0x180013d23  mov     rax, [rdi]
0x180013d26  call    cs:__guard_dispatch_icall_fptr
0x180013d2c  nop
0x180013d2d  cmp     [rbp+var_10], 0
0x180013d32  jz      short loc_180013D3D
0x180013d34  lea     rcx, [rbp+var_10]
0x180013d38  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013d3d  mov     rax, rbx
0x180013d40  mov     rcx, [rbp+var_8]
0x180013d44  xor     rcx, rsp; StackCookie
0x180013d47  call    __security_check_cookie
0x180013d4c  mov     rbx, [rsp+60h+arg_0]
0x180013d54  add     rsp, 60h
0x180013d58  pop     rdi
0x180013d59  pop     rsi
0x180013d5a  pop     rbp
0x180013d5b  retn
0x180013d5c  lfence
0x180013d5f  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
