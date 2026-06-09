# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &)

- ea: `0x180010918`
- end: `0x180010ac6`
- name: `??0?$heap_implements@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUhstring@2@AEBW4WindowsSoftwareUpdateInstallationType@Update@Management@Windows@2@000AEBUUri@Foundation@72@_K3AEBU?$IReference@Uguid@winrt@@@972@0AEBUWindowsSoftwareUpdateVersion@5672@5AEBUWindowsSoftwareUpdateAppPackageInfo@5672@AEBUWindowsSoftwareUpdateExecutionInfo@5672@AEBUWindowsSoftwareUpdateOptionalInfo@5672@@Z`
- size: `430`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800125a0`

## callees

- `0x18000340c`
- `0x180010918`
- `0x1800114a8`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001bf00`
- `0x18001c8a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16)
{
  __int64 *v20; // rdi
  __int64 v21; // rdx
  __int64 *SoftwareUpdate; // rsi
  __int64 v23; // rcx
  const struct winrt::impl::slim_source_location *v25; // rax
  __int64 v26; // [rsp+80h] [rbp-58h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-50h] BYREF
  _BYTE v28[32]; // [rsp+A0h] [rbp-38h] BYREF

  a1[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable';
  v20 = a1 + 3;
  a1[3] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v25 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v28, v21);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v25);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  SoftwareUpdate = winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(
                     &v26,
                     a2,
                     a3,
                     a4,
                     a5,
                     a6,
                     a7,
                     a8,
                     a9,
                     a12,
                     a13,
                     a14,
                     a15,
                     a16,
                     a10,
                     a11);
  if ( v20 != SoftwareUpdate )
  {
    if ( *v20 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v20);
    v23 = *SoftwareUpdate;
    *SoftwareUpdate = 0;
    *v20 = v23;
  }
  if ( v26 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180010918  mov     [rsp+arg_8], rbx
0x18001091d  mov     [rsp+arg_10], rbp
0x180010922  mov     [rsp+arg_0], rcx
0x180010927  push    rsi
0x180010928  push    rdi
0x180010929  push    r14
0x18001092b  sub     rsp, 0C0h
0x180010932  mov     rsi, r9
0x180010935  mov     rbp, r8
0x180010938  mov     r14, rdx
0x18001093b  mov     rbx, rcx
0x18001093e  lea     rax, ??_7?$produce@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdate@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::`vftable'
0x180010945  mov     [rcx+10h], rax
0x180010949  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180010950  mov     qword ptr [rcx+8], 1
0x180010958  lea     rax, ??_7WindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable'
0x18001095f  mov     [rcx], rax
0x180010962  lea     rdi, [rcx+18h]
0x180010966  mov     qword ptr [rdi], 0
0x18001096d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180010974  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180010979  test    al, al
0x18001097b  jz      loc_180010A94
0x180010981  mov     rax, [rsp+0D8h+arg_50]
0x180010989  mov     [rsp+0D8h+var_60], rax
0x18001098e  mov     rax, [rsp+0D8h+arg_48]
0x180010996  mov     [rsp+0D8h+var_68], rax
0x18001099b  mov     rax, [rsp+0D8h+arg_78]
0x1800109a3  mov     [rsp+0D8h+var_70], rax
0x1800109a8  mov     rax, [rsp+0D8h+arg_70]
0x1800109b0  mov     [rsp+0D8h+var_78], rax
0x1800109b5  mov     rax, [rsp+0D8h+arg_68]
0x1800109bd  mov     [rsp+0D8h+var_80], rax
0x1800109c2  mov     rax, [rsp+0D8h+arg_60]
0x1800109ca  mov     [rsp+0D8h+var_88], rax
0x1800109cf  mov     rax, [rsp+0D8h+arg_58]
0x1800109d7  mov     [rsp+0D8h+var_90], rax
0x1800109dc  mov     rax, [rsp+0D8h+arg_40]
0x1800109e4  mov     [rsp+0D8h+var_98], rax
0x1800109e9  mov     rax, [rsp+0D8h+arg_38]
0x1800109f1  mov     [rsp+0D8h+var_A0], rax
0x1800109f6  mov     rax, [rsp+0D8h+arg_30]
0x1800109fe  mov     [rsp+0D8h+var_A8], rax
0x180010a03  mov     rax, [rsp+0D8h+arg_28]
0x180010a0b  mov     [rsp+0D8h+var_B0], rax
0x180010a10  mov     rax, [rsp+0D8h+arg_20]
0x180010a18  mov     [rsp+0D8h+var_B8], rax
0x180010a1d  mov     r9, rsi
0x180010a20  mov     r8, rbp
0x180010a23  mov     rdx, r14
0x180010a26  lea     rcx, [rsp+0D8h+var_58]
0x180010a2e  call    ?GetSoftwareUpdate@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdate@2345@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z; winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)
0x180010a33  mov     rsi, rax
0x180010a36  cmp     rdi, rax
0x180010a39  jz      short loc_180010A56
0x180010a3b  cmp     qword ptr [rdi], 0
0x180010a3f  jz      short loc_180010A49
0x180010a41  mov     rcx, rdi
0x180010a44  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010a49  mov     rcx, [rsi]
0x180010a4c  mov     qword ptr [rsi], 0
0x180010a53  mov     [rdi], rcx
0x180010a56  cmp     [rsp+0D8h+var_58], 0
0x180010a5f  jz      short loc_180010A6F
0x180010a61  lea     rcx, [rsp+0D8h+var_58]
0x180010a69  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010a6e  nop
0x180010a6f  lea     rax, ??_7WindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable'
0x180010a76  mov     [rbx], rax
0x180010a79  mov     rax, rbx
0x180010a7c  lea     r11, [rsp+0D8h+var_18]
0x180010a84  mov     rbx, [r11+28h]
0x180010a88  mov     rbp, [r11+30h]
0x180010a8c  mov     rsp, r11
0x180010a8f  pop     r14
0x180010a91  pop     rdi
0x180010a92  pop     rsi
0x180010a93  retn
0x180010a94  lea     rcx, [rsp+0D8h+var_38]
0x180010a9c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180010aa1  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180010aa4  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x180010aac  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180010ab1  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180010ab8  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180010ac0  call    _CxxThrowException_0
```
