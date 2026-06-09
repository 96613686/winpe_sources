# ??$call@AEAV_lambda_d87b56c9fee8963e2cb1aea67b29a52d_@@@?$factory_cache_entry@UEnterpriseFeatureControl@Update@Management@WindowsUdk@winrt@@UIEnterpriseFeatureControlStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_d87b56c9fee8963e2cb1aea67b29a52d_@@@Z

- ea: `0x180010524`
- end: `0x1800106cd`
- name: `??$call@AEAV_lambda_d87b56c9fee8963e2cb1aea67b29a52d_@@@?$factory_cache_entry@UEnterpriseFeatureControl@Update@Management@WindowsUdk@winrt@@UIEnterpriseFeatureControlStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_d87b56c9fee8963e2cb1aea67b29a52d_@@@Z`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001c550`

## callees

- `0x180003bb1`
- `0x180010524`
- `0x180011f78`
- `0x180024b4c`
- `0x180024f28`
- `0x180033010`

## string_xrefs

- `0x180010544`: `WindowsUdk.Management.Update.EnterpriseFeatureControl`

## pseudocode

```c
char __fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>::call<_lambda_d87b56c9fee8963e2cb1aea67b29a52d_ &>(
        __int64 a1,
        unsigned int **a2)
{
  signed __int64 v3; // rbx
  int v4; // eax
  char v5; // di
  int v7; // eax
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int128 v9; // [rsp+28h] [rbp-38h]
  _DWORD *v10; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v11[4]; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v12; // [rsp+50h] [rbp-10h]
  __int64 v13; // [rsp+80h] [rbp+20h] BYREF
  void (__fastcall ***v14)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+30h] BYREF
  __int64 *v15; // [rsp+98h] [rbp+38h]

  v13 = a1;
  v11[0] = 1;
  v11[1] = 53;
  v12 = L"WindowsUdk.Management.Update.EnterpriseFeatureControl";
  v10 = v11;
  v14 = 0;
  v8 = 0;
  v9 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v13,
    &v10,
    (__int64)winrt::impl::guid_v<winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>,
    (__int64)&v14);
  if ( (int)v13 < 0 )
    winrt::throw_hresult((unsigned int)v13, &v8);
  v3 = (signed __int64)v14;
  if ( v14 && (v13 = 0, (**v14)(v14, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v13), v13) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
    v15 = &qword_180041D28;
    _InterlockedIncrement64(&qword_180041D28);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>,
            v3,
            0) )
    {
      v3 = 0;
      v14 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180041D30);
    }
    LOBYTE(v13) = 0;
    v8 = 0;
    v9 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>
                                                               + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>,
           **a2,
           &v13);
    if ( v4 < 0 )
      winrt::throw_hresult((unsigned int)v4, &v8);
    v5 = v13;
    _InterlockedDecrement64(&qword_180041D28);
    if ( v3 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
    return v5;
  }
  else
  {
    LOBYTE(v13) = 0;
    v8 = 0;
    v9 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, **a2, &v13);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v8);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
    return v13;
  }
}

```

## disassembly

```asm
0x180010524  mov     [rsp-18h+arg_0], rcx
0x180010529  push    rbp
0x18001052a  push    rbx
0x18001052b  push    rdi
0x18001052c  mov     rbp, rsp
0x18001052f  sub     rsp, 60h
0x180010533  mov     rdi, rdx
0x180010536  mov     [rbp+var_20], 1
0x18001053d  mov     [rbp+var_1C], 35h ; '5'
0x180010544  lea     rax, aWindowsudkMana; "WindowsUdk.Management.Update.Enterprise"...
0x18001054b  mov     [rbp+var_10], rax
0x18001054f  lea     rax, [rbp+var_20]
0x180010553  mov     [rbp+var_28], rax
0x180010557  mov     [rbp+arg_10], 0
0x18001055f  mov     [rbp+var_40], 0
0x180010566  xorps   xmm0, xmm0
0x180010569  movdqu  [rbp+var_38], xmm0
0x18001056e  lea     r9, [rbp+arg_10]
0x180010572  lea     r8, ??$guid_v@UIEnterpriseFeatureControlStatics@Update@Management@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>
0x180010579  lea     rdx, [rbp+var_28]
0x18001057d  lea     rcx, [rbp+arg_0]
0x180010581  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180010586  mov     ecx, dword ptr [rbp+arg_0]
0x180010589  test    ecx, ecx
0x18001058b  js      loc_1800106B7
0x180010591  mov     rbx, [rbp+arg_10]
0x180010595  mov     [rbp+arg_10], rbx
0x180010599  test    rbx, rbx
0x18001059c  jz      loc_180010668
0x1800105a2  mov     [rbp+arg_0], 0
0x1800105aa  mov     rax, [rbx]
0x1800105ad  lea     r8, [rbp+arg_0]
0x1800105b1  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800105b8  mov     rcx, rbx
0x1800105bb  mov     rax, [rax]
0x1800105be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105c3  mov     rax, [rbp+arg_0]
0x1800105c7  mov     [rbp+arg_0], rax
0x1800105cb  test    rax, rax
0x1800105ce  jz      loc_180010668
0x1800105d4  lea     rcx, [rbp+arg_0]
0x1800105d8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800105dd  lea     rax, qword_180041D28
0x1800105e4  mov     [rbp+arg_18], rax
0x1800105e8  lock inc cs:qword_180041D28
0x1800105f0  xor     eax, eax
0x1800105f2  lock cmpxchg cs:??$factory_cache_entry_v@UEnterpriseFeatureControl@Update@Management@WindowsUdk@winrt@@UIEnterpriseFeatureControlStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UEnterpriseFeatureControl@Update@Management@WindowsUdk@winrt@@UIEnterpriseFeatureControlStatics@2345@@12@A, rbx; factory_cache_entry<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>
0x1800105fb  jnz     short loc_180010616
0x1800105fd  xor     ebx, ebx
0x1800105ff  mov     [rbp+arg_10], rbx
0x180010603  lea     rdx, stru_180041D30; ListEntry
0x18001060a  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180010611  call    WINRT_IMPL_InterlockedPushEntrySList
0x180010616  mov     byte ptr [rbp+arg_0], 0
0x18001061a  mov     rcx, cs:??$factory_cache_entry_v@UEnterpriseFeatureControl@Update@Management@WindowsUdk@winrt@@UIEnterpriseFeatureControlStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UEnterpriseFeatureControl@Update@Management@WindowsUdk@winrt@@UIEnterpriseFeatureControlStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::EnterpriseFeatureControl,winrt::WindowsUdk::Management::Update::IEnterpriseFeatureControlStatics>
0x180010621  mov     [rbp+var_40], 0
0x180010628  xorps   xmm0, xmm0
0x18001062b  movdqu  [rbp+var_38], xmm0
0x180010630  mov     rax, [rcx]
0x180010633  mov     rdx, [rdi]
0x180010636  lea     r8, [rbp+arg_0]
0x18001063a  mov     edx, [rdx]
0x18001063c  mov     rax, [rax+30h]
0x180010640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010645  test    eax, eax
0x180010647  js      short loc_1800106C1
0x180010649  mov     dil, byte ptr [rbp+arg_0]
0x18001064d  lock dec cs:qword_180041D28
0x180010655  test    rbx, rbx
0x180010658  jz      short loc_180010663
0x18001065a  lea     rcx, [rbp+arg_10]
0x18001065e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010663  mov     al, dil
0x180010666  jmp     short loc_1800106A3
0x180010668  mov     byte ptr [rbp+arg_0], 0
0x18001066c  mov     [rbp+var_40], 0
0x180010673  xorps   xmm0, xmm0
0x180010676  movdqu  [rbp+var_38], xmm0
0x18001067b  mov     rax, [rbx]
0x18001067e  mov     rdx, [rdi]
0x180010681  lea     r8, [rbp+arg_0]
0x180010685  mov     edx, [rdx]
0x180010687  mov     rcx, rbx
0x18001068a  mov     rax, [rax+30h]
0x18001068e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010693  test    eax, eax
0x180010695  js      short loc_1800106AB
0x180010697  lea     rcx, [rbp+arg_10]
0x18001069b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800106a0  mov     al, byte ptr [rbp+arg_0]
0x1800106a3  add     rsp, 60h
0x1800106a7  pop     rdi
0x1800106a8  pop     rbx
0x1800106a9  pop     rbp
0x1800106aa  retn
0x1800106ab  lea     rdx, [rbp+var_40]
0x1800106af  mov     ecx, eax
0x1800106b1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800106b7  lea     rdx, [rbp+var_40]
0x1800106bb  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800106c1  lea     rdx, [rbp+var_40]
0x1800106c5  mov     ecx, eax
0x1800106c7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
