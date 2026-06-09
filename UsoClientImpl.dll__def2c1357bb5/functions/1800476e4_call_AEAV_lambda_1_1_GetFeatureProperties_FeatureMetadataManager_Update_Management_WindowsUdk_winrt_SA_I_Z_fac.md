# ??$call@AEAV_lambda_1_@?1??GetFeatureProperties@FeatureMetadataManager@Update@Management@WindowsUdk@winrt@@SA@I@Z@@?$factory_cache_entry@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetFeatureProperties@FeatureMetadataManager@Update@Management@WindowsUdk@2@SA@I@Z@@Z

- ea: `0x1800476e4`
- end: `0x18004785c`
- name: `??$call@AEAV_lambda_1_@?1??GetFeatureProperties@FeatureMetadataManager@Update@Management@WindowsUdk@winrt@@SA@I@Z@@?$factory_cache_entry@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetFeatureProperties@FeatureMetadataManager@Update@Management@WindowsUdk@2@SA@I@Z@@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180041d00`

## callees

- `0x18002d1a4`
- `0x180035a50`
- `0x1800476e4`
- `0x180047864`
- `0x180056500`
- `0x18005c27a`
- `0x18005c5e0`

## string_xrefs

- `0x180047719`: `WindowsUdk.Management.Update.FeatureMetadataManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ___call_AEAV_lambda_1___1__GetFeatureProperties_FeatureMetadataManager_Update_Management_WindowsUdk_winrt__SA_I_Z____factory_cache_entry_UFeatureMetadataManager_Update_Management_WindowsUdk_winrt__UIFeatureMetadataManagerStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__GetFeatureProperties_FeatureMetadataManager_Update_Management_WindowsUdk_2_SA_I_Z__Z(
        __int64 a1,
        _QWORD *a2,
        unsigned int **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  _QWORD v9[2]; // [rsp+20h] [rbp-50h] BYREF
  _DWORD *v10; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v11[4]; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v12; // [rsp+48h] [rbp-28h]
  __int64 *v13; // [rsp+50h] [rbp-20h]
  _QWORD *v14; // [rsp+58h] [rbp-18h] BYREF

  v14 = a2;
  v11[0] = 1;
  v11[1] = 51;
  v12 = L"WindowsUdk.Management.Update.FeatureMetadataManager";
  v10 = v11;
  winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>(v9, &v10);
  v5 = v9[0];
  if ( !v9[0]
    || (v14 = 0,
        (**(void (__fastcall ***)(_QWORD, __int64 *, _QWORD **))v9[0])(
          v9[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v14),
        !v14) )
  {
    v14 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD **))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v14);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7);
    *a2 = v14;
    goto LABEL_10;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  v13 = &qword_18009FAF8;
  _InterlockedIncrement64(&qword_18009FAF8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>,
          v5,
          0) )
  {
    v5 = 0;
    v9[0] = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18009FB00);
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>
                                                             + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>,
         **a3,
         &v14);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6);
  *a2 = v14;
  _InterlockedDecrement64(&qword_18009FAF8);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
  return a2;
}

```

## disassembly

```asm
0x1800476e4  mov     [rsp-18h+arg_0], rbx
0x1800476e9  push    rbp
0x1800476ea  push    rsi
0x1800476eb  push    rdi
0x1800476ec  mov     rbp, rsp
0x1800476ef  sub     rsp, 70h
0x1800476f3  mov     rax, cs:__security_cookie
0x1800476fa  xor     rax, rsp
0x1800476fd  mov     [rbp+var_10], rax
0x180047701  mov     rsi, r8
0x180047704  mov     rdi, rdx
0x180047707  mov     [rbp+var_18], rdx
0x18004770b  mov     [rbp+var_38], 1
0x180047712  mov     [rbp+var_34], 33h ; '3'
0x180047719  lea     rax, aWindowsudkMana_0; "WindowsUdk.Management.Update.FeatureMet"...
0x180047720  mov     [rbp+var_28], rax
0x180047724  lea     rax, [rbp+var_38]
0x180047728  mov     [rbp+var_40], rax
0x18004772c  lea     rdx, [rbp+var_40]
0x180047730  lea     rcx, [rbp+var_50]
0x180047734  call    ??$get_activation_factory@UIFeatureMetadataManagerStatics@Update@Management@WindowsUdk@winrt@@@winrt@@YA?AUIFeatureMetadataManagerStatics@Update@Management@WindowsUdk@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>(winrt::param::hstring const &)
0x180047739  nop
0x18004773a  mov     rbx, [rbp+var_50]
0x18004773e  test    rbx, rbx
0x180047741  jz      loc_1800477F9
0x180047747  mov     [rbp+var_18], 0
0x18004774f  mov     rax, [rbx]
0x180047752  lea     r8, [rbp+var_18]
0x180047756  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18004775d  mov     rcx, rbx
0x180047760  mov     rax, [rax]
0x180047763  call    _guard_dispatch_icall
0x180047768  mov     rax, [rbp+var_18]
0x18004776c  mov     [rbp+var_18], rax
0x180047770  test    rax, rax
0x180047773  jz      loc_1800477F9
0x180047779  lea     rcx, [rbp+var_18]
0x18004777d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180047782  lea     rax, qword_18009FAF8
0x180047789  mov     [rbp+var_20], rax
0x18004778d  lock inc cs:qword_18009FAF8
0x180047795  xor     eax, eax
0x180047797  lock cmpxchg cs:??$factory_cache_entry_v@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@12@A, rbx; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>
0x1800477a0  jnz     short loc_1800477BB
0x1800477a2  xor     ebx, ebx
0x1800477a4  mov     [rbp+var_50], rbx
0x1800477a8  lea     rdx, stru_18009FB00; ListEntry
0x1800477af  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800477b6  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800477bb  mov     [rbp+var_18], 0
0x1800477c3  mov     rcx, cs:??$factory_cache_entry_v@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>
0x1800477ca  mov     rdx, [rsi]
0x1800477cd  mov     rax, [rcx]
0x1800477d0  lea     r8, [rbp+var_18]
0x1800477d4  mov     edx, [rdx]
0x1800477d6  mov     rax, [rax+30h]
0x1800477da  call    _guard_dispatch_icall
0x1800477df  test    eax, eax
0x1800477e1  js      short loc_180047854
0x1800477e3  mov     rcx, [rbp+var_18]
0x1800477e7  mov     [rdi], rcx
0x1800477ea  lock dec cs:qword_18009FAF8
0x1800477f2  test    rbx, rbx
0x1800477f5  jz      short loc_18004782D
0x1800477f7  jmp     short loc_180047824
0x1800477f9  mov     [rbp+var_18], 0
0x180047801  mov     rdx, [rsi]
0x180047804  mov     rax, [rbx]
0x180047807  lea     r8, [rbp+var_18]
0x18004780b  mov     edx, [rdx]
0x18004780d  mov     rcx, rbx
0x180047810  mov     rax, [rax+30h]
0x180047814  call    _guard_dispatch_icall
0x180047819  test    eax, eax
0x18004781b  js      short loc_18004784C
0x18004781d  mov     rax, [rbp+var_18]
0x180047821  mov     [rdi], rax
0x180047824  lea     rcx, [rbp+var_50]
0x180047828  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004782d  mov     rax, rdi
0x180047830  mov     rcx, [rbp+var_10]
0x180047834  xor     rcx, rsp; StackCookie
0x180047837  call    __security_check_cookie
0x18004783c  mov     rbx, [rsp+70h+arg_0]
0x180047844  add     rsp, 70h
0x180047848  pop     rdi
0x180047849  pop     rsi
0x18004784a  pop     rbp
0x18004784b  retn
0x18004784c  mov     ecx, eax
0x18004784e  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180047854  mov     ecx, eax
0x180047856  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
