# ??$call@AEAV_lambda_24__@?0???0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@5@@Z@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_24__@?0???0Uri@Foundation@Windows@2@QEAA@AEBUhstring@param@2@@Z@@Z

- ea: `0x18000c218`
- end: `0x18000c3c1`
- name: `??$call@AEAV_lambda_24__@?0???0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@5@@Z@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_24__@?0???0Uri@Foundation@Windows@2@QEAA@AEBUhstring@param@2@@Z@@Z`
- size: `425`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000fd78`

## callees

- `0x18000c218`
- `0x18002d1a4`
- `0x18002d6a4`
- `0x180035a50`
- `0x180056500`
- `0x18005c27a`
- `0x18005c5e0`

## string_xrefs

- `0x18000c24d`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ___call_AEAV_lambda_24____0___0Uri_Foundation_Windows_winrt__QEAA_AEBUhstring_param_5__Z____factory_cache_entry_UUri_Foundation_Windows_winrt__UIUriRuntimeClassFactory_234__impl_winrt__QEAA_A_PAEAV_lambda_24____0___0Uri_Foundation_Windows_2_QEAA_AEBUhstring_param_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3)
{
  void (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  int v6; // eax
  int v7; // eax
  unsigned int v9[4]; // [rsp+20h] [rbp-50h] BYREF
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
    (__int64)winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>,
    (__int64)&v15);
  if ( (v9[0] & 0x80000000) != 0 )
    winrt::throw_hresult(v9[0]);
  v5 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v15;
  *(_QWORD *)v9 = v15;
  if ( !v15 || (v14 = 0, (**v15)(v15, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v14), !v14) )
  {
    v14 = 0;
    v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD **))(*v5)[6])(v5, **a3, &v14);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7);
    *a2 = v14;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  v13 = &qword_18009F808;
  _InterlockedIncrement64(&qword_18009F808);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
          (signed __int64)v15,
          0) )
  {
    *(_QWORD *)v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18009F810);
    v5 = 0;
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
                                                             + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
         **a3,
         &v14);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6);
  *a2 = v14;
  _InterlockedDecrement64(&qword_18009F808);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
  return a2;
}

```

## disassembly

```asm
0x18000c218  mov     [rsp-18h+arg_0], rbx
0x18000c21d  push    rbp
0x18000c21e  push    rsi
0x18000c21f  push    rdi
0x18000c220  mov     rbp, rsp
0x18000c223  sub     rsp, 70h
0x18000c227  mov     rax, cs:__security_cookie
0x18000c22e  xor     rax, rsp
0x18000c231  mov     [rbp+var_8], rax
0x18000c235  mov     rsi, r8
0x18000c238  mov     rdi, rdx
0x18000c23b  mov     [rbp+var_18], rdx
0x18000c23f  mov     [rbp+var_38], 1
0x18000c246  mov     [rbp+var_34], 16h
0x18000c24d  lea     rax, aWindowsFoundat; "Windows.Foundation.Uri"
0x18000c254  mov     [rbp+var_28], rax
0x18000c258  lea     rax, [rbp+var_38]
0x18000c25c  mov     [rbp+var_40], rax
0x18000c260  mov     [rbp+var_10], 0
0x18000c268  lea     r9, [rbp+var_10]
0x18000c26c  lea     r8, ??$guid_v@UIUriRuntimeClassFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18000c273  lea     rdx, [rbp+var_40]
0x18000c277  lea     rcx, [rbp+var_50]
0x18000c27b  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000c280  mov     ecx, [rbp+var_50]
0x18000c283  test    ecx, ecx
0x18000c285  js      loc_18000C3B3
0x18000c28b  mov     rbx, [rbp+var_10]
0x18000c28f  mov     qword ptr [rbp+var_50], rbx
0x18000c293  test    rbx, rbx
0x18000c296  jz      loc_18000C357
0x18000c29c  mov     [rbp+var_18], 0
0x18000c2a4  mov     rax, [rbx]
0x18000c2a7  lea     r8, [rbp+var_18]
0x18000c2ab  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000c2b2  mov     rcx, rbx
0x18000c2b5  mov     rax, [rax]
0x18000c2b8  call    _guard_dispatch_icall
0x18000c2bd  mov     rax, [rbp+var_18]
0x18000c2c1  mov     [rbp+var_18], rax
0x18000c2c5  test    rax, rax
0x18000c2c8  jz      loc_18000C357
0x18000c2ce  lea     rcx, [rbp+var_18]
0x18000c2d2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000c2d7  lea     rax, qword_18009F808
0x18000c2de  mov     [rbp+var_20], rax
0x18000c2e2  lock inc cs:qword_18009F808
0x18000c2ea  mov     rcx, [rbp+var_10]
0x18000c2ee  xor     eax, eax
0x18000c2f0  lock cmpxchg cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A, rcx; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18000c2f9  jnz     short loc_18000C318
0x18000c2fb  mov     qword ptr [rbp+var_50], 0
0x18000c303  lea     rdx, stru_18009F810; ListEntry
0x18000c30a  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000c311  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000c316  xor     ebx, ebx
0x18000c318  mov     [rbp+var_18], 0
0x18000c320  mov     rcx, cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18000c327  mov     rdx, [rsi]
0x18000c32a  mov     rax, [rcx]
0x18000c32d  lea     r8, [rbp+var_18]
0x18000c331  mov     rdx, [rdx]
0x18000c334  mov     rax, [rax+30h]
0x18000c338  call    _guard_dispatch_icall
0x18000c33d  test    eax, eax
0x18000c33f  js      short loc_18000C3B9
0x18000c341  mov     rcx, [rbp+var_18]
0x18000c345  mov     [rdi], rcx
0x18000c348  lock dec cs:qword_18009F808
0x18000c350  test    rbx, rbx
0x18000c353  jz      short loc_18000C38C
0x18000c355  jmp     short loc_18000C383
0x18000c357  mov     [rbp+var_18], 0
0x18000c35f  mov     rdx, [rsi]
0x18000c362  mov     rax, [rbx]
0x18000c365  lea     r8, [rbp+var_18]
0x18000c369  mov     rdx, [rdx]
0x18000c36c  mov     rcx, rbx
0x18000c36f  mov     rax, [rax+30h]
0x18000c373  call    _guard_dispatch_icall
0x18000c378  test    eax, eax
0x18000c37a  js      short loc_18000C3AB
0x18000c37c  mov     rax, [rbp+var_18]
0x18000c380  mov     [rdi], rax
0x18000c383  lea     rcx, [rbp+var_50]
0x18000c387  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000c38c  mov     rax, rdi
0x18000c38f  mov     rcx, [rbp+var_8]
0x18000c393  xor     rcx, rsp; StackCookie
0x18000c396  call    __security_check_cookie
0x18000c39b  mov     rbx, [rsp+70h+arg_0]
0x18000c3a3  add     rsp, 70h
0x18000c3a7  pop     rdi
0x18000c3a8  pop     rsi
0x18000c3a9  pop     rbp
0x18000c3aa  retn
0x18000c3ab  mov     ecx, eax
0x18000c3ad  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18000c3b3  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18000c3b9  mov     ecx, eax
0x18000c3bb  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
