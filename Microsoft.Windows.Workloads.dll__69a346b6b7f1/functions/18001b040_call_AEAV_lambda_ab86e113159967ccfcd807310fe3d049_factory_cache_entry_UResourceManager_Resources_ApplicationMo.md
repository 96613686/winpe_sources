# ??$call@AEAV_lambda_ab86e113159967ccfcd807310fe3d049_@@@?$factory_cache_entry@UResourceManager@Resources@ApplicationModel@Windows@Microsoft@winrt@@UIResourceManagerFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_ab86e113159967ccfcd807310fe3d049_@@@Z

- ea: `0x18001b040`
- end: `0x18001b1f4`
- name: `??$call@AEAV_lambda_ab86e113159967ccfcd807310fe3d049_@@@?$factory_cache_entry@UResourceManager@Resources@ApplicationModel@Windows@Microsoft@winrt@@UIResourceManagerFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_ab86e113159967ccfcd807310fe3d049_@@@Z`
- size: `436`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180017340`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180013ed0`
- `0x18001b040`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>::call<_lambda_ab86e113159967ccfcd807310fe3d049_ &>(
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
  v11[1] = 60;
  v12 = L"Microsoft.Windows.ApplicationModel.Resources.ResourceManager";
  v10 = v11;
  v15 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    v9,
    &v10,
    winrt::impl::guid_v<winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>,
    &v15);
  if ( (v9[0] & 0x80000000) != 0 )
  {
    _mm_lfence();
    winrt::throw_hresult(v9[0]);
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
  v13 = &qword_180059F08;
  _InterlockedIncrement64(&qword_180059F08);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>,
          (signed __int64)v15,
          0) )
  {
    *(_QWORD *)v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180059F10);
    v5 = 0;
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>
                                                             + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>,
         **a3,
         &v14);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6);
  }
  *a2 = v14;
  _InterlockedDecrement64(&qword_180059F08);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
  return a2;
}

```

## disassembly

```asm
0x18001b040  mov     [rsp-18h+arg_0], rbx
0x18001b045  mov     [rsp-18h+arg_18], rsi
0x18001b04a  push    rbp
0x18001b04b  push    rdi
0x18001b04c  push    r14
0x18001b04e  mov     rbp, rsp
0x18001b051  sub     rsp, 70h
0x18001b055  mov     rax, cs:__security_cookie
0x18001b05c  xor     rax, rsp
0x18001b05f  mov     [rbp+var_8], rax
0x18001b063  mov     rsi, r8
0x18001b066  mov     rdi, rdx
0x18001b069  mov     [rbp+var_18], rdx
0x18001b06d  xor     r14d, r14d
0x18001b070  mov     [rbp+var_38], 1
0x18001b077  mov     [rbp+var_34], 3Ch ; '<'
0x18001b07e  lea     rax, aMicrosoftWindo_5; "Microsoft.Windows.ApplicationModel.Reso"...
0x18001b085  mov     [rbp+var_28], rax
0x18001b089  lea     rax, [rbp+var_38]
0x18001b08d  mov     [rbp+var_40], rax
0x18001b091  mov     [rbp+var_10], r14
0x18001b095  lea     r9, [rbp+var_10]
0x18001b099  lea     r8, ??$guid_v@UIResourceManagerFactory@Resources@ApplicationModel@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>
0x18001b0a0  lea     rdx, [rbp+var_40]
0x18001b0a4  lea     rcx, [rbp+var_50]
0x18001b0a8  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001b0ad  mov     ecx, [rbp+var_50]
0x18001b0b0  test    ecx, ecx
0x18001b0b2  js      loc_18001B1E0
0x18001b0b8  mov     rbx, [rbp+var_10]
0x18001b0bc  mov     qword ptr [rbp+var_50], rbx
0x18001b0c0  test    rbx, rbx
0x18001b0c3  jz      loc_18001B17F
0x18001b0c9  mov     [rbp+var_18], r14
0x18001b0cd  mov     rax, [rbx]
0x18001b0d0  lea     r8, [rbp+var_18]
0x18001b0d4  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001b0db  mov     rcx, rbx
0x18001b0de  mov     rax, [rax]
0x18001b0e1  call    cs:__guard_dispatch_icall_fptr
0x18001b0e7  mov     rax, [rbp+var_18]
0x18001b0eb  mov     [rbp+var_18], rax
0x18001b0ef  test    rax, rax
0x18001b0f2  jz      loc_18001B17F
0x18001b0f8  lea     rcx, [rbp+var_18]
0x18001b0fc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b101  lea     rax, qword_180059F08
0x18001b108  mov     [rbp+var_20], rax
0x18001b10c  lock inc cs:qword_180059F08
0x18001b114  mov     rcx, [rbp+var_10]
0x18001b118  xor     eax, eax
0x18001b11a  lock cmpxchg cs:??$factory_cache_entry_v@UResourceManager@Resources@ApplicationModel@Windows@Microsoft@winrt@@UIResourceManagerFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UResourceManager@Resources@ApplicationModel@Windows@Microsoft@winrt@@UIResourceManagerFactory@23456@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>
0x18001b123  jnz     short loc_18001B13F
0x18001b125  mov     qword ptr [rbp+var_50], r14
0x18001b129  lea     rdx, stru_180059F10; ListEntry
0x18001b130  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001b137  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001b13c  mov     ebx, r14d
0x18001b13f  mov     [rbp+var_18], r14
0x18001b143  mov     rcx, cs:??$factory_cache_entry_v@UResourceManager@Resources@ApplicationModel@Windows@Microsoft@winrt@@UIResourceManagerFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UResourceManager@Resources@ApplicationModel@Windows@Microsoft@winrt@@UIResourceManagerFactory@23456@@12@A; factory_cache_entry<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>
0x18001b14a  mov     rdx, [rsi]
0x18001b14d  mov     rax, [rcx]
0x18001b150  lea     r8, [rbp+var_18]
0x18001b154  mov     rdx, [rdx]
0x18001b157  mov     rax, [rax+30h]
0x18001b15b  call    cs:__guard_dispatch_icall_fptr
0x18001b161  test    eax, eax
0x18001b163  js      loc_18001B1E9
0x18001b169  mov     rcx, [rbp+var_18]
0x18001b16d  mov     [rdi], rcx
0x18001b170  lock dec cs:qword_180059F08
0x18001b178  test    rbx, rbx
0x18001b17b  jz      short loc_18001B1B1
0x18001b17d  jmp     short loc_18001B1A8
0x18001b17f  mov     [rbp+var_18], r14
0x18001b183  mov     rdx, [rsi]
0x18001b186  mov     rax, [rbx]
0x18001b189  lea     r8, [rbp+var_18]
0x18001b18d  mov     rdx, [rdx]
0x18001b190  mov     rcx, rbx
0x18001b193  mov     rax, [rax+30h]
0x18001b197  call    cs:__guard_dispatch_icall_fptr
0x18001b19d  test    eax, eax
0x18001b19f  js      short loc_18001B1D5
0x18001b1a1  mov     rax, [rbp+var_18]
0x18001b1a5  mov     [rdi], rax
0x18001b1a8  lea     rcx, [rbp+var_50]
0x18001b1ac  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b1b1  mov     rax, rdi
0x18001b1b4  mov     rcx, [rbp+var_8]
0x18001b1b8  xor     rcx, rsp; StackCookie
0x18001b1bb  call    __security_check_cookie
0x18001b1c0  lea     r11, [rsp+70h+var_s0]
0x18001b1c5  mov     rbx, [r11+20h]
0x18001b1c9  mov     rsi, [r11+38h]
0x18001b1cd  mov     rsp, r11
0x18001b1d0  pop     r14
0x18001b1d2  pop     rdi
0x18001b1d3  pop     rbp
0x18001b1d4  retn
0x18001b1d5  lfence
0x18001b1d8  mov     ecx, eax
0x18001b1da  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18001b1e0  lfence
0x18001b1e3  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18001b1e9  lfence
0x18001b1ec  mov     ecx, eax
0x18001b1ee  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
