# ??$call@P6A?AUPackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@AEBUIPackageDeploymentManagerStatics@23456@@Z@?$factory_cache_entry@UPackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@UIPackageDeploymentManagerStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageDeploymentManager@Deployment@Management@Windows@Microsoft@2@AEBUIPackageDeploymentManagerStatics@45672@@Z@Z

- ea: `0x18001c640`
- end: `0x18001c795`
- name: `??$call@P6A?AUPackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@AEBUIPackageDeploymentManagerStatics@23456@@Z@?$factory_cache_entry@UPackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@UIPackageDeploymentManagerStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageDeploymentManager@Deployment@Management@Windows@Microsoft@2@AEBUIPackageDeploymentManagerStatics@45672@@Z@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001c810`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180013ed0`
- `0x18001c640`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager,winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics>::call<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager (*)(winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics const &)>(
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
  v9[1] = 64;
  v10 = L"Microsoft.Windows.Management.Deployment.PackageDeploymentManager";
  v8 = v9;
  v11 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v7,
    &v8,
    winrt::impl::guid_v<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics>,
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
    v11 = &qword_180059F68;
    _InterlockedIncrement64(&qword_180059F68);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager,winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics>,
            (signed __int64)v12,
            0) )
    {
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180059F70);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager,winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics>);
    _InterlockedDecrement64(&qword_180059F68);
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
0x18001c640  mov     [rsp-18h+arg_0], rbx
0x18001c645  push    rbp
0x18001c646  push    rsi
0x18001c647  push    rdi
0x18001c648  mov     rbp, rsp
0x18001c64b  sub     rsp, 60h
0x18001c64f  mov     rax, cs:__security_cookie
0x18001c656  xor     rax, rsp
0x18001c659  mov     [rbp+var_8], rax
0x18001c65d  mov     rdi, r8
0x18001c660  mov     rbx, rdx
0x18001c663  mov     [rbp+var_18], rdx
0x18001c667  xor     esi, esi
0x18001c669  mov     [rbp+var_30], 1
0x18001c670  mov     [rbp+var_2C], 40h ; '@'
0x18001c677  lea     rax, aMicrosoftWindo_3; "Microsoft.Windows.Management.Deployment"...
0x18001c67e  mov     [rbp+var_20], rax
0x18001c682  lea     rax, [rbp+var_30]
0x18001c686  mov     [rbp+var_38], rax
0x18001c68a  mov     [rbp+var_18], rsi
0x18001c68e  lea     r9, [rbp+var_18]
0x18001c692  lea     r8, ??$guid_v@UIPackageDeploymentManagerStatics@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics>
0x18001c699  lea     rdx, [rbp+var_38]
0x18001c69d  lea     rcx, [rbp+var_40]
0x18001c6a1  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001c6a6  mov     ecx, [rbp+var_40]
0x18001c6a9  test    ecx, ecx
0x18001c6ab  js      loc_18001C78C
0x18001c6b1  mov     rcx, [rbp+var_18]
0x18001c6b5  mov     [rbp+var_10], rcx
0x18001c6b9  test    rcx, rcx
0x18001c6bc  jz      loc_18001C74C
0x18001c6c2  mov     [rbp+var_18], rsi
0x18001c6c6  mov     rax, [rcx]
0x18001c6c9  lea     r8, [rbp+var_18]
0x18001c6cd  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c6d4  mov     rax, [rax]
0x18001c6d7  call    cs:__guard_dispatch_icall_fptr
0x18001c6dd  mov     rax, [rbp+var_18]
0x18001c6e1  mov     [rbp+var_18], rax
0x18001c6e5  test    rax, rax
0x18001c6e8  jz      short loc_18001C74C
0x18001c6ea  lea     rcx, [rbp+var_18]
0x18001c6ee  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c6f3  lea     rax, qword_180059F68
0x18001c6fa  mov     [rbp+var_18], rax
0x18001c6fe  lock inc cs:qword_180059F68
0x18001c706  mov     rcx, [rbp+var_10]
0x18001c70a  xor     eax, eax
0x18001c70c  lock cmpxchg cs:??$factory_cache_entry_v@UPackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@UIPackageDeploymentManagerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UPackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@UIPackageDeploymentManagerStatics@23456@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager,winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager,winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager,winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics>
0x18001c715  jnz     short loc_18001C72E
0x18001c717  mov     [rbp+var_10], rsi
0x18001c71b  lea     rdx, stru_180059F70; ListEntry
0x18001c722  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c729  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c72e  lea     rdx, ??$factory_cache_entry_v@UPackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@UIPackageDeploymentManagerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UPackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@UIPackageDeploymentManagerStatics@23456@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager,winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager,winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager,winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManagerStatics>
0x18001c735  mov     rcx, rbx
0x18001c738  mov     rax, [rdi]
0x18001c73b  call    cs:__guard_dispatch_icall_fptr
0x18001c741  nop
0x18001c742  lock dec cs:qword_180059F68
0x18001c74a  jmp     short loc_18001C75D
0x18001c74c  lea     rdx, [rbp+var_10]
0x18001c750  mov     rcx, rbx
0x18001c753  mov     rax, [rdi]
0x18001c756  call    cs:__guard_dispatch_icall_fptr
0x18001c75c  nop
0x18001c75d  cmp     [rbp+var_10], 0
0x18001c762  jz      short loc_18001C76D
0x18001c764  lea     rcx, [rbp+var_10]
0x18001c768  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c76d  mov     rax, rbx
0x18001c770  mov     rcx, [rbp+var_8]
0x18001c774  xor     rcx, rsp; StackCookie
0x18001c777  call    __security_check_cookie
0x18001c77c  mov     rbx, [rsp+60h+arg_0]
0x18001c784  add     rsp, 60h
0x18001c788  pop     rdi
0x18001c789  pop     rsi
0x18001c78a  pop     rbp
0x18001c78b  retn
0x18001c78c  lfence
0x18001c78f  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
