# winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::register_completed_callback(std::experimental::coroutine_handle<void>)

- ea: `0x180019270`
- end: `0x1800193b8`
- name: `?register_completed_callback@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@AEAA_NU?$coroutine_handle@X@experimental@std@@@Z`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800182b0`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180019270`
- `0x18001a290`
- `0x180034ef0`
- `0x180035060`
- `0x1800398b7`
- `0x1800398bd`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::register_completed_callback(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v4; // r14
  HRESULT ApartmentType; // eax
  APTTYPE v6; // ecx
  _DWORD *v7; // rbx
  LPVOID v8; // rax
  __int64 v9; // rax
  signed int v10; // eax
  unsigned __int8 v11; // di
  LPVOID v13; // [rsp+20h] [rbp-40h] BYREF
  int v14; // [rsp+28h] [rbp-38h]
  __int64 v15; // [rsp+30h] [rbp-30h]
  __int64 v16; // [rsp+38h] [rbp-28h]
  LPVOID ppv; // [rsp+40h] [rbp-20h] BYREF
  APTTYPE pAptType; // [rsp+48h] [rbp-18h] BYREF

  v4 = *(_QWORD **)(a1 + 8);
  ppv = 0;
  WINRT_IMPL_CoGetObjectContext(&winrt::impl::guid_v<winrt::impl::IContextCallback>, &ppv);
  v13 = ppv;
  ApartmentType = WINRT_IMPL_CoGetApartmentType(&pAptType, (APTTYPEQUALIFIER *)&ppv);
  v6 = APTTYPE_MTA;
  if ( !ApartmentType )
    v6 = pAptType;
  v14 = v6;
  v15 = a1;
  v16 = a2;
  ppv = &v13;
  v7 = operator new(0x30u);
  v7[2] = 1;
  v8 = v13;
  v13 = 0;
  *((_QWORD *)v7 + 2) = v8;
  LODWORD(v8) = v14;
  v14 = -1;
  v7[6] = (_DWORD)v8;
  v9 = v15;
  v15 = 0;
  *((_QWORD *)v7 + 4) = v9;
  *((_QWORD *)v7 + 5) = v16;
  v16 = 0;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v7 = &winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>>::`vftable';
  ppv = v7;
  if ( v16 )
    winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>::Complete((__int64 *)&v13);
  if ( v13 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v13);
  v10 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)*v4 + 64LL))(*v4, v7);
  if ( v10 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult(v10);
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&ppv);
  v11 = *(_BYTE *)(a1 + 24);
  *(_BYTE *)(a1 + 24) = 0;
  return v11;
}

```

## disassembly

```asm
0x180019270  mov     [rsp-18h+arg_8], rbx
0x180019275  mov     [rsp-18h+arg_10], rsi
0x18001927a  push    rbp
0x18001927b  push    rdi
0x18001927c  push    r14
0x18001927e  mov     rbp, rsp
0x180019281  sub     rsp, 60h
0x180019285  mov     rax, cs:__security_cookie
0x18001928c  xor     rax, rsp
0x18001928f  mov     [rbp+var_10], rax
0x180019293  mov     rbx, rdx
0x180019296  mov     rsi, rcx
0x180019299  xor     edi, edi
0x18001929b  mov     r14, [rcx+8]
0x18001929f  mov     [rbp+ppv], rdi
0x1800192a3  lea     rdx, [rbp+ppv]; ppv
0x1800192a7  lea     rcx, ??$guid_v@UIContextCallback@impl@winrt@@@impl@winrt@@3Uguid@2@B; riid
0x1800192ae  call    WINRT_IMPL_CoGetObjectContext
0x1800192b3  mov     rax, [rbp+ppv]
0x1800192b7  mov     [rbp+var_40], rax
0x1800192bb  lea     rdx, [rbp+ppv]; pAptQualifier
0x1800192bf  lea     rcx, [rbp+pAptType]; pAptType
0x1800192c3  call    WINRT_IMPL_CoGetApartmentType
0x1800192c8  mov     ecx, 1
0x1800192cd  test    eax, eax
0x1800192cf  cmovz   ecx, [rbp+pAptType]
0x1800192d3  mov     [rbp+var_38], ecx
0x1800192d6  mov     [rbp+var_30], rsi
0x1800192da  mov     [rbp+var_28], rbx
0x1800192de  lea     rax, [rbp+var_40]
0x1800192e2  mov     [rbp+ppv], rax
0x1800192e6  mov     ecx, 30h ; '0'; Size
0x1800192eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800192f0  mov     rbx, rax
0x1800192f3  mov     [rbp+ppv], rax
0x1800192f7  mov     dword ptr [rax+8], 1
0x1800192fe  mov     rax, [rbp+var_40]
0x180019302  mov     [rbp+var_40], rdi
0x180019306  mov     [rbx+10h], rax
0x18001930a  mov     eax, [rbp+var_38]
0x18001930d  mov     [rbp+var_38], 0FFFFFFFFh
0x180019314  mov     [rbx+18h], eax
0x180019317  mov     rax, [rbp+var_30]
0x18001931b  mov     [rbp+var_30], rdi
0x18001931f  mov     [rbx+20h], rax
0x180019323  mov     rax, [rbp+var_28]
0x180019327  mov     [rbx+28h], rax
0x18001932b  mov     [rbp+var_28], rdi
0x18001932f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180019336  lea     rax, ??_7?$delegate@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@U?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@4@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>>::`vftable'
0x18001933d  mov     [rbx], rax
0x180019340  mov     [rbp+ppv], rbx
0x180019344  cmp     [rbp+var_28], rdi
0x180019348  jz      short loc_180019353
0x18001934a  lea     rcx, [rbp+var_40]
0x18001934e  call    ?Complete@?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@winrt@@AEAAXXZ; winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>::Complete(void)
0x180019353  cmp     [rbp+var_40], 0
0x180019358  jz      short loc_180019364
0x18001935a  lea     rcx, [rbp+var_40]
0x18001935e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180019363  nop
0x180019364  mov     rcx, [r14]
0x180019367  mov     rax, [rcx]
0x18001936a  mov     rdx, rbx
0x18001936d  mov     rax, [rax+40h]
0x180019371  call    cs:__guard_dispatch_icall_fptr
0x180019377  test    eax, eax
0x180019379  js      short loc_1800193AD
0x18001937b  lea     rcx, [rbp+ppv]
0x18001937f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180019384  xchg    dil, [rsi+18h]
0x180019388  movzx   eax, dil
0x18001938c  mov     rcx, [rbp+var_10]
0x180019390  xor     rcx, rsp; StackCookie
0x180019393  call    __security_check_cookie
0x180019398  lea     r11, [rsp+60h+var_s0]
0x18001939d  mov     rbx, [r11+28h]
0x1800193a1  mov     rsi, [r11+30h]
0x1800193a5  mov     rsp, r11
0x1800193a8  pop     r14
0x1800193aa  pop     rdi
0x1800193ab  pop     rbp
0x1800193ac  retn
0x1800193ad  lfence
0x1800193b0  mov     ecx, eax
0x1800193b2  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
