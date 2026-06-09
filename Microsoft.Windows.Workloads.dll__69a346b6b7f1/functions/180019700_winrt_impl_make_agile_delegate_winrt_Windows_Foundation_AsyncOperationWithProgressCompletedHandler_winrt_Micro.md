# winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>(winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &)

- ea: `0x180019700`
- end: `0x180019857`
- name: `??$make_agile_delegate@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBU2341@@Z`
- size: `343`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018910`

## callees

- `0x1800040a0`
- `0x180019700`
- `0x180034ef0`
- `0x180035060`
- `0x1800398b1`
- `0x18003bed0`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>(
        _QWORD *a1,
        _QWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, __int128 *); // rcx
  bool v5; // si
  void (__fastcall ***v6)(_QWORD, __int64 *, __int128 *); // rcx
  __int64 v7; // rsi
  char *v8; // rax
  __int64 v9; // rcx
  __int128 v11; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  __int128 v13; // [rsp+38h] [rbp-20h] BYREF

  v4 = (void (__fastcall ***)(_QWORD, __int64 *, __int128 *))*a2;
  if ( !*a2 )
    goto LABEL_7;
  *(_QWORD *)&v11 = 0;
  (**v4)(v4, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v11);
  v5 = (_QWORD)v11 != 0;
  if ( (_QWORD)v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  if ( v5 )
  {
    v6 = (void (__fastcall ***)(_QWORD, __int64 *, __int128 *))*a2;
    *a1 = *a2;
    if ( v6 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64 *, __int128 *)))(*v6)[1])(v6);
  }
  else
  {
LABEL_7:
    v13 = winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>;
    v12 = 0;
    WINRT_IMPL_RoGetAgileReference(0, &v13, *a2, &v12);
    v7 = v12;
    if ( v12 )
    {
      v12 = 0;
      v11 = v13;
      v8 = (char *)operator new(0x28u);
      *((_DWORD *)v8 + 2) = 1;
      *((_QWORD *)v8 + 2) = v7;
      *(_OWORD *)(v8 + 24) = v11;
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *(_QWORD *)v8 = &winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,_lambda_43563adb7f255c0f3f40f9d370b6f4b6_>::`vftable';
      *a1 = v8;
    }
    else
    {
      v9 = *a2;
      *a1 = *a2;
      if ( !v9 )
        return a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    }
    if ( v12 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  }
  return a1;
}

```

## disassembly

```asm
0x180019700  mov     [rsp+arg_10], rbx
0x180019705  mov     [rsp+arg_18], rsi
0x18001970a  push    rdi
0x18001970b  sub     rsp, 50h
0x18001970f  mov     rax, cs:__security_cookie
0x180019716  xor     rax, rsp
0x180019719  mov     [rsp+58h+var_10], rax
0x18001971e  mov     rdi, rdx
0x180019721  mov     rbx, rcx
0x180019724  mov     rcx, [rdx]
0x180019727  test    rcx, rcx
0x18001972a  jz      short loc_180019793
0x18001972c  mov     qword ptr [rsp+58h+var_38], 0
0x180019735  mov     rax, [rcx]
0x180019738  lea     r8, [rsp+58h+var_38]
0x18001973d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180019744  mov     rax, [rax]
0x180019747  call    cs:__guard_dispatch_icall_fptr
0x18001974d  mov     rax, qword ptr [rsp+58h+var_38]
0x180019752  mov     qword ptr [rsp+58h+var_38], rax
0x180019757  test    rax, rax
0x18001975a  setnz   sil
0x18001975e  test    rax, rax
0x180019761  jz      short loc_18001976D
0x180019763  lea     rcx, [rsp+58h+var_38]
0x180019768  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001976d  test    sil, sil
0x180019770  jz      short loc_180019793
0x180019772  mov     rcx, [rdi]
0x180019775  mov     [rbx], rcx
0x180019778  test    rcx, rcx
0x18001977b  jz      loc_180019837
0x180019781  mov     rdx, [rcx]
0x180019784  mov     rax, [rdx+8]
0x180019788  call    cs:__guard_dispatch_icall_fptr
0x18001978e  jmp     loc_180019837
0x180019793  movups  xmm0, cs:??$guid_v@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>
0x18001979a  movups  [rsp+58h+var_20], xmm0
0x18001979f  mov     [rsp+58h+var_28], 0
0x1800197a8  lea     r9, [rsp+58h+var_28]
0x1800197ad  mov     r8, [rdi]
0x1800197b0  lea     rdx, [rsp+58h+var_20]
0x1800197b5  xor     ecx, ecx
0x1800197b7  call    WINRT_IMPL_RoGetAgileReference
0x1800197bc  mov     rsi, [rsp+58h+var_28]
0x1800197c1  test    rsi, rsi
0x1800197c4  jz      short loc_18001980D
0x1800197c6  mov     [rsp+58h+var_28], 0
0x1800197cf  movups  xmm0, [rsp+58h+var_20]
0x1800197d4  movups  [rsp+58h+var_38], xmm0
0x1800197d9  mov     ecx, 28h ; '('; Size
0x1800197de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800197e3  mov     dword ptr [rax+8], 1
0x1800197ea  mov     [rax+10h], rsi
0x1800197ee  movups  xmm0, [rsp+58h+var_38]
0x1800197f3  movups  xmmword ptr [rax+18h], xmm0
0x1800197f7  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800197fe  lea     rcx, ??_7?$delegate@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@V_lambda_43563adb7f255c0f3f40f9d370b6f4b6_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,_lambda_43563adb7f255c0f3f40f9d370b6f4b6_>::`vftable'
0x180019805  mov     [rax], rcx
0x180019808  mov     [rbx], rax
0x18001980b  jmp     short loc_180019825
0x18001980d  mov     rcx, [rdi]
0x180019810  mov     [rbx], rcx
0x180019813  test    rcx, rcx
0x180019816  jz      short loc_180019837
0x180019818  mov     rax, [rcx]
0x18001981b  mov     rax, [rax+8]
0x18001981f  call    cs:__guard_dispatch_icall_fptr
0x180019825  cmp     [rsp+58h+var_28], 0
0x18001982b  jz      short loc_180019837
0x18001982d  lea     rcx, [rsp+58h+var_28]
0x180019832  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180019837  mov     rax, rbx
0x18001983a  mov     rcx, [rsp+58h+var_10]
0x18001983f  xor     rcx, rsp; StackCookie
0x180019842  call    __security_check_cookie
0x180019847  mov     rbx, [rsp+58h+arg_10]
0x18001984c  mov     rsi, [rsp+58h+arg_18]
0x180019851  add     rsp, 50h
0x180019855  pop     rdi
0x180019856  retn
```
