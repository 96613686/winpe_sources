# ??$call@P6A?AUEnsureReadyOptions@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UEnsureReadyOptions@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUEnsureReadyOptions@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x18001c100`
- end: `0x18001c255`
- name: `??$call@P6A?AUEnsureReadyOptions@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UEnsureReadyOptions@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUEnsureReadyOptions@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800398d0`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180014870`
- `0x18001c100`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

## string_xrefs

- `0x18001c137`: `Microsoft.Windows.Management.Deployment.EnsureReadyOptions`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
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
  v9[1] = 58;
  v10 = L"Microsoft.Windows.Management.Deployment.EnsureReadyOptions";
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
    v11 = &qword_180059F28;
    _InterlockedIncrement64(&qword_180059F28);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v12,
            0) )
    {
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180059F30);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180059F28);
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
0x18001c100  mov     [rsp-18h+arg_0], rbx
0x18001c105  push    rbp
0x18001c106  push    rsi
0x18001c107  push    rdi
0x18001c108  mov     rbp, rsp
0x18001c10b  sub     rsp, 60h
0x18001c10f  mov     rax, cs:__security_cookie
0x18001c116  xor     rax, rsp
0x18001c119  mov     [rbp+var_8], rax
0x18001c11d  mov     rdi, r8
0x18001c120  mov     rbx, rdx
0x18001c123  mov     [rbp+var_18], rdx
0x18001c127  xor     esi, esi
0x18001c129  mov     [rbp+var_30], 1
0x18001c130  mov     [rbp+var_2C], 3Ah ; ':'
0x18001c137  lea     rax, aMicrosoftWindo_19; "Microsoft.Windows.Management.Deployment"...
0x18001c13e  mov     [rbp+var_20], rax
0x18001c142  lea     rax, [rbp+var_30]
0x18001c146  mov     [rbp+var_38], rax
0x18001c14a  mov     [rbp+var_18], rsi
0x18001c14e  lea     r9, [rbp+var_18]
0x18001c152  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; "5"
0x18001c159  lea     rdx, [rbp+var_38]
0x18001c15d  lea     rcx, [rbp+var_40]
0x18001c161  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001c166  mov     ecx, [rbp+var_40]
0x18001c169  test    ecx, ecx
0x18001c16b  js      loc_18001C24C
0x18001c171  mov     rcx, [rbp+var_18]
0x18001c175  mov     [rbp+var_10], rcx
0x18001c179  test    rcx, rcx
0x18001c17c  jz      loc_18001C20C
0x18001c182  mov     [rbp+var_18], rsi
0x18001c186  mov     rax, [rcx]
0x18001c189  lea     r8, [rbp+var_18]
0x18001c18d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c194  mov     rax, [rax]
0x18001c197  call    cs:__guard_dispatch_icall_fptr
0x18001c19d  mov     rax, [rbp+var_18]
0x18001c1a1  mov     [rbp+var_18], rax
0x18001c1a5  test    rax, rax
0x18001c1a8  jz      short loc_18001C20C
0x18001c1aa  lea     rcx, [rbp+var_18]
0x18001c1ae  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c1b3  lea     rax, qword_180059F28
0x18001c1ba  mov     [rbp+var_18], rax
0x18001c1be  lock inc cs:qword_180059F28
0x18001c1c6  mov     rcx, [rbp+var_10]
0x18001c1ca  xor     eax, eax
0x18001c1cc  lock cmpxchg cs:??$factory_cache_entry_v@UEnsureReadyOptions@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UEnsureReadyOptions@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions,winrt::Windows::Foundation::IActivationFactory>
0x18001c1d5  jnz     short loc_18001C1EE
0x18001c1d7  mov     [rbp+var_10], rsi
0x18001c1db  lea     rdx, stru_180059F30; ListEntry
0x18001c1e2  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c1e9  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c1ee  lea     rdx, ??$factory_cache_entry_v@UEnsureReadyOptions@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UEnsureReadyOptions@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::EnsureReadyOptions,winrt::Windows::Foundation::IActivationFactory>
0x18001c1f5  mov     rcx, rbx
0x18001c1f8  mov     rax, [rdi]
0x18001c1fb  call    cs:__guard_dispatch_icall_fptr
0x18001c201  nop
0x18001c202  lock dec cs:qword_180059F28
0x18001c20a  jmp     short loc_18001C21D
0x18001c20c  lea     rdx, [rbp+var_10]
0x18001c210  mov     rcx, rbx
0x18001c213  mov     rax, [rdi]
0x18001c216  call    cs:__guard_dispatch_icall_fptr
0x18001c21c  nop
0x18001c21d  cmp     [rbp+var_10], 0
0x18001c222  jz      short loc_18001C22D
0x18001c224  lea     rcx, [rbp+var_10]
0x18001c228  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c22d  mov     rax, rbx
0x18001c230  mov     rcx, [rbp+var_8]
0x18001c234  xor     rcx, rsp; StackCookie
0x18001c237  call    __security_check_cookie
0x18001c23c  mov     rbx, [rsp+60h+arg_0]
0x18001c244  add     rsp, 60h
0x18001c248  pop     rdi
0x18001c249  pop     rsi
0x18001c24a  pop     rbp
0x18001c24b  retn
0x18001c24c  lfence
0x18001c24f  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
