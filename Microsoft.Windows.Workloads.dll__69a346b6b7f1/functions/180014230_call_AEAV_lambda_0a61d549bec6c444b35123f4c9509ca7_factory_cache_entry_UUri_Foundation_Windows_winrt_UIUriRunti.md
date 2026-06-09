# ??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z

- ea: `0x180014230`
- end: `0x1800143e4`
- name: `??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z`
- size: `436`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006110`
- `0x180016760`
- `0x18001e7d0`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180013ed0`
- `0x180014230`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

## string_xrefs

- `0x18001426e`: `Windows.Foundation.Uri`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::call<_lambda_0a61d549bec6c444b35123f4c9509ca7_ &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3)
{
  void (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  int v6; // eax
  int v7; // eax
  int v9[4]; // [rsp+20h] [rbp-50h] BYREF
  _DWORD *v10; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v11[4]; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v12; // [rsp+48h] [rbp-28h]
  __int64 *v13; // [rsp+50h] [rbp-20h]
  _QWORD *v14; // [rsp+58h] [rbp-18h] BYREF
  void (__fastcall ***v15)(_QWORD, __int64 *, _QWORD **); // [rsp+60h] [rbp-10h] BYREF

  v14 = a2;
  v11[0] = 1;
  v11[1] = 22;
  v12 = L"Windows.Foundation.Uri";
  v10 = v11;
  v15 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    v9,
    &v10,
    winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>,
    &v15);
  if ( v9[0] < 0 )
  {
    _mm_lfence();
    ((void (__noreturn *)(void))winrt::throw_hresult)();
  }
  v5 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v15;
  *(_QWORD *)v9 = v15;
  if ( !v15 || (v14 = 0, (**v15)(v15, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v14), !v14) )
  {
    v14 = 0;
    v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD **))(*v5)[6])(v5, **a3, &v14);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7);
    }
    *a2 = v14;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  v13 = &qword_180059E78;
  _InterlockedIncrement64(&qword_180059E78);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
          (signed __int64)v15,
          0) )
  {
    *(_QWORD *)v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180059E80);
    v5 = 0;
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
                                                             + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
         **a3,
         &v14);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6);
  }
  *a2 = v14;
  _InterlockedDecrement64(&qword_180059E78);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
  return a2;
}

```

## disassembly

```asm
0x180014230  mov     [rsp-18h+arg_0], rbx
0x180014235  mov     [rsp-18h+arg_18], rsi
0x18001423a  push    rbp
0x18001423b  push    rdi
0x18001423c  push    r14
0x18001423e  mov     rbp, rsp
0x180014241  sub     rsp, 70h
0x180014245  mov     rax, cs:__security_cookie
0x18001424c  xor     rax, rsp
0x18001424f  mov     [rbp+var_8], rax
0x180014253  mov     rsi, r8
0x180014256  mov     rdi, rdx
0x180014259  mov     [rbp+var_18], rdx
0x18001425d  xor     r14d, r14d
0x180014260  mov     [rbp+var_38], 1
0x180014267  mov     [rbp+var_34], 16h
0x18001426e  lea     rax, aWindowsFoundat_0; "Windows.Foundation.Uri"
0x180014275  mov     [rbp+var_28], rax
0x180014279  lea     rax, [rbp+var_38]
0x18001427d  mov     [rbp+var_40], rax
0x180014281  mov     [rbp+var_10], r14
0x180014285  lea     r9, [rbp+var_10]
0x180014289  lea     r8, ??$guid_v@UIUriRuntimeClassFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x180014290  lea     rdx, [rbp+var_40]
0x180014294  lea     rcx, [rbp+var_50]
0x180014298  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001429d  mov     ecx, [rbp+var_50]
0x1800142a0  test    ecx, ecx
0x1800142a2  js      loc_1800143D0
0x1800142a8  mov     rbx, [rbp+var_10]
0x1800142ac  mov     qword ptr [rbp+var_50], rbx
0x1800142b0  test    rbx, rbx
0x1800142b3  jz      loc_18001436F
0x1800142b9  mov     [rbp+var_18], r14
0x1800142bd  mov     rax, [rbx]
0x1800142c0  lea     r8, [rbp+var_18]
0x1800142c4  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800142cb  mov     rcx, rbx
0x1800142ce  mov     rax, [rax]
0x1800142d1  call    cs:__guard_dispatch_icall_fptr
0x1800142d7  mov     rax, [rbp+var_18]
0x1800142db  mov     [rbp+var_18], rax
0x1800142df  test    rax, rax
0x1800142e2  jz      loc_18001436F
0x1800142e8  lea     rcx, [rbp+var_18]
0x1800142ec  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800142f1  lea     rax, qword_180059E78
0x1800142f8  mov     [rbp+var_20], rax
0x1800142fc  lock inc cs:qword_180059E78
0x180014304  mov     rcx, [rbp+var_10]
0x180014308  xor     eax, eax
0x18001430a  lock cmpxchg cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A, rcx; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x180014313  jnz     short loc_18001432F
0x180014315  mov     qword ptr [rbp+var_50], r14
0x180014319  lea     rdx, stru_180059E80; ListEntry
0x180014320  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180014327  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001432c  mov     ebx, r14d
0x18001432f  mov     [rbp+var_18], r14
0x180014333  mov     rcx, cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18001433a  mov     rdx, [rsi]
0x18001433d  mov     rax, [rcx]
0x180014340  lea     r8, [rbp+var_18]
0x180014344  mov     rdx, [rdx]
0x180014347  mov     rax, [rax+30h]
0x18001434b  call    cs:__guard_dispatch_icall_fptr
0x180014351  test    eax, eax
0x180014353  js      loc_1800143D9
0x180014359  mov     rcx, [rbp+var_18]
0x18001435d  mov     [rdi], rcx
0x180014360  lock dec cs:qword_180059E78
0x180014368  test    rbx, rbx
0x18001436b  jz      short loc_1800143A1
0x18001436d  jmp     short loc_180014398
0x18001436f  mov     [rbp+var_18], r14
0x180014373  mov     rdx, [rsi]
0x180014376  mov     rax, [rbx]
0x180014379  lea     r8, [rbp+var_18]
0x18001437d  mov     rdx, [rdx]
0x180014380  mov     rcx, rbx
0x180014383  mov     rax, [rax+30h]
0x180014387  call    cs:__guard_dispatch_icall_fptr
0x18001438d  test    eax, eax
0x18001438f  js      short loc_1800143C5
0x180014391  mov     rax, [rbp+var_18]
0x180014395  mov     [rdi], rax
0x180014398  lea     rcx, [rbp+var_50]
0x18001439c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800143a1  mov     rax, rdi
0x1800143a4  mov     rcx, [rbp+var_8]
0x1800143a8  xor     rcx, rsp; StackCookie
0x1800143ab  call    __security_check_cookie
0x1800143b0  lea     r11, [rsp+70h+var_s0]
0x1800143b5  mov     rbx, [r11+20h]
0x1800143b9  mov     rsi, [r11+38h]
0x1800143bd  mov     rsp, r11
0x1800143c0  pop     r14
0x1800143c2  pop     rdi
0x1800143c3  pop     rbp
0x1800143c4  retn
0x1800143c5  lfence
0x1800143c8  mov     ecx, eax
0x1800143ca  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x1800143d0  lfence
0x1800143d3  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x1800143d9  lfence
0x1800143dc  mov     ecx, eax
0x1800143de  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
