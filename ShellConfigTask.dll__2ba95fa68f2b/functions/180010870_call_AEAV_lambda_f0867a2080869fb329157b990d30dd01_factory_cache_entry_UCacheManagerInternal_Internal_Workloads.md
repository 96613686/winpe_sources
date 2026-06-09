# ??$call@AEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@Z

- ea: `0x180010870`
- end: `0x180010a33`
- name: `??$call@AEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@Z`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014efc`

## callees

- `0x180003bb1`
- `0x180010870`
- `0x180011f78`
- `0x180024b4c`
- `0x180024f28`
- `0x180033010`

## string_xrefs

- `0x180010898`: `Microsoft.Windows.Workloads.Internal.CacheManagerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed __int64 *__fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>::call<_lambda_f0867a2080869fb329157b990d30dd01_ &>(
        signed __int64 a1,
        signed __int64 *a2,
        unsigned int **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  signed __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  signed __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  v12[0] = 1;
  v12[1] = 57;
  v13 = L"Microsoft.Windows.Workloads.Internal.CacheManagerInternal";
  v11 = v12;
  v15 = 0;
  v9 = 0;
  v10 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v11,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>,
    (__int64)&v15);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v9);
  v5 = v15;
  v14 = v15;
  if ( !v15
    || (v15 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, signed __int64 *))v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, signed __int64 *))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_180041EE8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>,
          v5,
          0) )
  {
    v5 = 0;
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180041EF0);
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>
                                                                    + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_180041EE8);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x180010870  mov     [rsp-18h+arg_8], rbx
0x180010875  mov     [rsp-18h+arg_0], rcx
0x18001087a  push    rbp
0x18001087b  push    rsi
0x18001087c  push    rdi
0x18001087d  mov     rbp, rsp
0x180010880  sub     rsp, 70h
0x180010884  mov     rsi, r8
0x180010887  mov     rdi, rdx
0x18001088a  mov     [rbp+var_20], 1
0x180010891  mov     [rbp+var_1C], 39h ; '9'
0x180010898  lea     rax, aMicrosoftWindo; "Microsoft.Windows.Workloads.Internal.Ca"...
0x18001089f  mov     [rbp+var_10], rax
0x1800108a3  lea     rax, [rbp+var_20]
0x1800108a7  mov     [rbp+var_28], rax
0x1800108ab  mov     [rbp+arg_18], 0
0x1800108b3  mov     [rbp+var_40], 0
0x1800108ba  xorps   xmm0, xmm0
0x1800108bd  movdqu  [rbp+var_38], xmm0
0x1800108c2  lea     r9, [rbp+arg_18]
0x1800108c6  lea     r8, ??$guid_v@UICacheManagerInternalStatics@Internal@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>
0x1800108cd  lea     rdx, [rbp+var_28]
0x1800108d1  lea     rcx, [rbp+arg_0]
0x1800108d5  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x1800108da  mov     ecx, dword ptr [rbp+arg_0]
0x1800108dd  test    ecx, ecx
0x1800108df  js      loc_180010A1D
0x1800108e5  mov     rbx, [rbp+arg_18]
0x1800108e9  mov     [rbp+arg_0], rbx
0x1800108ed  test    rbx, rbx
0x1800108f0  jz      loc_1800109BB
0x1800108f6  mov     [rbp+arg_18], 0
0x1800108fe  mov     rax, [rbx]
0x180010901  lea     r8, [rbp+arg_18]
0x180010905  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001090c  mov     rcx, rbx
0x18001090f  mov     rax, [rax]
0x180010912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010917  mov     rax, [rbp+arg_18]
0x18001091b  mov     [rbp+arg_18], rax
0x18001091f  test    rax, rax
0x180010922  jz      loc_1800109BB
0x180010928  lea     rcx, [rbp+arg_18]
0x18001092c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010931  lea     rax, qword_180041EE8
0x180010938  mov     [rbp+var_48], rax
0x18001093c  lock inc cs:qword_180041EE8
0x180010944  xor     eax, eax
0x180010946  lock cmpxchg cs:??$factory_cache_entry_v@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@12@A, rbx; factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>
0x18001094f  jnz     short loc_18001096A
0x180010951  xor     ebx, ebx
0x180010953  mov     [rbp+arg_0], rbx
0x180010957  lea     rdx, stru_180041EF0; ListEntry
0x18001095e  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180010965  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001096a  mov     [rbp+arg_18], 0
0x180010972  mov     rcx, cs:??$factory_cache_entry_v@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>
0x180010979  mov     [rbp+var_40], 0
0x180010980  xorps   xmm0, xmm0
0x180010983  movdqu  [rbp+var_38], xmm0
0x180010988  mov     rax, [rcx]
0x18001098b  mov     rdx, [rsi]
0x18001098e  lea     r8, [rbp+arg_18]
0x180010992  mov     edx, [rdx]
0x180010994  mov     rax, [rax+30h]
0x180010998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001099d  test    eax, eax
0x18001099f  js      loc_180010A27
0x1800109a5  mov     rax, [rbp+arg_18]
0x1800109a9  mov     [rdi], rax
0x1800109ac  lock dec cs:qword_180041EE8
0x1800109b4  test    rbx, rbx
0x1800109b7  jz      short loc_1800109FE
0x1800109b9  jmp     short loc_1800109F5
0x1800109bb  mov     [rbp+arg_18], 0
0x1800109c3  mov     [rbp+var_40], 0
0x1800109ca  xorps   xmm0, xmm0
0x1800109cd  movdqu  [rbp+var_38], xmm0
0x1800109d2  mov     rax, [rbx]
0x1800109d5  mov     rdx, [rsi]
0x1800109d8  lea     r8, [rbp+arg_18]
0x1800109dc  mov     edx, [rdx]
0x1800109de  mov     rcx, rbx
0x1800109e1  mov     rax, [rax+30h]
0x1800109e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ea  test    eax, eax
0x1800109ec  js      short loc_180010A11
0x1800109ee  mov     rax, [rbp+arg_18]
0x1800109f2  mov     [rdi], rax
0x1800109f5  lea     rcx, [rbp+arg_0]
0x1800109f9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800109fe  mov     rax, rdi
0x180010a01  mov     rbx, [rsp+70h+arg_8]
0x180010a09  add     rsp, 70h
0x180010a0d  pop     rdi
0x180010a0e  pop     rsi
0x180010a0f  pop     rbp
0x180010a10  retn
0x180010a11  lea     rdx, [rbp+var_40]
0x180010a15  mov     ecx, eax
0x180010a17  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180010a1d  lea     rdx, [rbp+var_40]
0x180010a21  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180010a27  lea     rdx, [rbp+var_40]
0x180010a2b  mov     ecx, eax
0x180010a2d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
