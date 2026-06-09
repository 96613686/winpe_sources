# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &)

- ea: `0x180011460`
- end: `0x180011609`
- name: `??0?$heap_implements@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUhstring@2@AEBW4WindowsSoftwareUpdateInstallationType@Update@Management@Windows@2@000AEBUUri@Foundation@72@_K3AEBU?$IReference@Uguid@winrt@@@972@0AEBUWindowsSoftwareUpdateVersion@5672@5AEBUWindowsSoftwareUpdateAppPackageInfo@5672@AEBUWindowsSoftwareUpdateExecutionInfo@5672@AEBUWindowsSoftwareUpdateOptionalInfo@5672@@Z`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013170`

## callees

- `0x1800035f0`
- `0x180011460`
- `0x18001203c`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001d150`
- `0x18001db60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        __int64 *a10,
        __int64 a11,
        _QWORD *a12,
        _QWORD *a13,
        __int64 *a14,
        _QWORD *a15,
        _QWORD *a16)
{
  __int64 *v20; // rdi
  __int64 *SoftwareUpdate; // rsi
  __int64 v22; // rcx
  const struct winrt::impl::slim_source_location *v24; // rax
  __int64 v25; // [rsp+80h] [rbp-58h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-50h] BYREF
  _BYTE v27[32]; // [rsp+A0h] [rbp-38h] BYREF

  a1[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable';
  v20 = a1 + 3;
  a1[3] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v24 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v27);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v24);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  SoftwareUpdate = winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(
                     &v25,
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
    v22 = *SoftwareUpdate;
    *SoftwareUpdate = 0;
    *v20 = v22;
  }
  if ( v25 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180011460  mov     [rsp+arg_8], rbx
0x180011465  mov     [rsp+arg_10], rbp
0x18001146a  mov     [rsp+arg_0], rcx
0x18001146f  push    rsi
0x180011470  push    rdi
0x180011471  push    r14
0x180011473  sub     rsp, 0C0h
0x18001147a  mov     rsi, r9
0x18001147d  mov     rbp, r8
0x180011480  mov     r14, rdx
0x180011483  mov     rbx, rcx
0x180011486  lea     rax, ??_7?$produce@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdate@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::`vftable'
0x18001148d  mov     [rcx+10h], rax
0x180011491  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011498  mov     qword ptr [rcx+8], 1
0x1800114a0  lea     rax, ??_7WindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable'
0x1800114a7  mov     [rcx], rax
0x1800114aa  lea     rdi, [rcx+18h]
0x1800114ae  and     qword ptr [rdi], 0
0x1800114b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800114b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800114be  test    al, al
0x1800114c0  jz      loc_1800115D7
0x1800114c6  mov     rax, [rsp+0D8h+arg_50]
0x1800114ce  mov     [rsp+0D8h+var_60], rax
0x1800114d3  mov     rax, [rsp+0D8h+arg_48]
0x1800114db  mov     [rsp+0D8h+var_68], rax
0x1800114e0  mov     rax, [rsp+0D8h+arg_78]
0x1800114e8  mov     [rsp+0D8h+var_70], rax
0x1800114ed  mov     rax, [rsp+0D8h+arg_70]
0x1800114f5  mov     [rsp+0D8h+var_78], rax
0x1800114fa  mov     rax, [rsp+0D8h+arg_68]
0x180011502  mov     [rsp+0D8h+var_80], rax
0x180011507  mov     rax, [rsp+0D8h+arg_60]
0x18001150f  mov     [rsp+0D8h+var_88], rax
0x180011514  mov     rax, [rsp+0D8h+arg_58]
0x18001151c  mov     [rsp+0D8h+var_90], rax
0x180011521  mov     rax, [rsp+0D8h+arg_40]
0x180011529  mov     [rsp+0D8h+var_98], rax
0x18001152e  mov     rax, [rsp+0D8h+arg_38]
0x180011536  mov     [rsp+0D8h+var_A0], rax
0x18001153b  mov     rax, [rsp+0D8h+arg_30]
0x180011543  mov     [rsp+0D8h+var_A8], rax
0x180011548  mov     rax, [rsp+0D8h+arg_28]
0x180011550  mov     [rsp+0D8h+var_B0], rax
0x180011555  mov     rax, [rsp+0D8h+arg_20]
0x18001155d  mov     [rsp+0D8h+var_B8], rax
0x180011562  mov     r9, rsi
0x180011565  mov     r8, rbp
0x180011568  mov     rdx, r14
0x18001156b  lea     rcx, [rsp+0D8h+var_58]
0x180011573  call    ?GetSoftwareUpdate@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdate@2345@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z; winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)
0x180011578  mov     rsi, rax
0x18001157b  cmp     rdi, rax
0x18001157e  jz      short loc_180011598
0x180011580  cmp     qword ptr [rdi], 0
0x180011584  jz      short loc_18001158E
0x180011586  mov     rcx, rdi
0x180011589  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001158e  mov     rcx, [rsi]
0x180011591  and     qword ptr [rsi], 0
0x180011595  mov     [rdi], rcx
0x180011598  cmp     [rsp+0D8h+var_58], 0
0x1800115a1  jz      short loc_1800115B1
0x1800115a3  lea     rcx, [rsp+0D8h+var_58]
0x1800115ab  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800115b0  nop
0x1800115b1  lea     rax, ??_7WindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable'
0x1800115b8  mov     [rbx], rax
0x1800115bb  mov     rax, rbx
0x1800115be  lea     r11, [rsp+0D8h+var_18]
0x1800115c6  mov     rbx, [r11+28h]
0x1800115ca  mov     rbp, [r11+30h]
0x1800115ce  mov     rsp, r11
0x1800115d1  pop     r14
0x1800115d3  pop     rdi
0x1800115d4  pop     rsi
0x1800115d5  retn
0x1800115d7  lea     rcx, [rsp+0D8h+var_38]
0x1800115df  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800115e4  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800115e7  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x1800115ef  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800115f4  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800115fb  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180011603  call    _CxxThrowException_0
```
