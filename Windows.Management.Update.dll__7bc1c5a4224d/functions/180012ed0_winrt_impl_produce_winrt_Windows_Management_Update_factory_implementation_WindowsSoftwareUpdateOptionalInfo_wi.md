# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfoFactory>::CreateInstance(void *,void *,void * *)

- ea: `0x180012ed0`
- end: `0x180012fae`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateOptionalInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfoFactory@3456@@impl@winrt@@UEAAHPEAX0PEAPEAX@Z`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800114a8`
- `0x180012ed0`
- `0x180014eb4`
- `0x18001c8a0`
- `0x18001f178`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfoFactory>::CreateInstance(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v5; // rbx
  __int64 v6; // rdx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v8; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  char v10[48]; // [rsp+38h] [rbp-30h] BYREF
  _QWORD *v11; // [rsp+70h] [rbp+8h] BYREF
  __int64 v12; // [rsp+78h] [rbp+10h] BYREF
  __int64 v13; // [rsp+80h] [rbp+18h] BYREF

  v13 = a3;
  v12 = a2;
  v11 = a1;
  *a4 = 0;
  try
  {
    v5 = operator new(0x30u);
    v11 = v5;
    v5[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v5[1] = 1;
    *v5 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable';
    v5[3] = 0;
    v5[4] = 0;
    v5[5] = 0;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v10, v6);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v8);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(
      v5,
      &v12,
      &v13);
    *v5 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable';
    *a4 = v5 + 2;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x180012ed0  mov     [rsp+arg_10], r8
0x180012ed5  mov     [rsp+arg_8], rdx
0x180012eda  mov     [rsp+arg_0], rcx
0x180012edf  push    rbx
0x180012ee0  push    rsi
0x180012ee1  push    rdi
0x180012ee2  sub     rsp, 50h
0x180012ee6  mov     rdi, r9
0x180012ee9  mov     qword ptr [r9], 0
0x180012ef0  mov     ecx, 30h ; '0'; Size
0x180012ef5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012efa  mov     rbx, rax
0x180012efd  mov     [rsp+68h+arg_0], rax
0x180012f02  lea     rsi, [rax+10h]
0x180012f06  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::`vftable'
0x180012f0d  mov     [rsi], rax
0x180012f10  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180012f17  mov     qword ptr [rbx+8], 1
0x180012f1f  lea     rax, ??_7WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable'
0x180012f26  mov     [rbx], rax
0x180012f29  mov     qword ptr [rbx+18h], 0
0x180012f31  mov     qword ptr [rbx+20h], 0
0x180012f39  mov     qword ptr [rbx+28h], 0
0x180012f41  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180012f48  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180012f4d  test    al, al
0x180012f4f  jz      short loc_180012F84
0x180012f51  lea     r8, [rsp+68h+arg_10]
0x180012f59  lea     rdx, [rsp+68h+arg_8]
0x180012f5e  mov     rcx, rbx
0x180012f61  call    ?InitializeComplianceParameters@WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@AEAAXAEBU?$IReference@H@Foundation@56@0@Z; winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(winrt::Windows::Foundation::IReference<int> const &,winrt::Windows::Foundation::IReference<int> const &)
0x180012f66  nop
0x180012f67  lea     rax, ??_7WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable'
0x180012f6e  mov     [rbx], rax
0x180012f71  mov     [rdi], rsi
0x180012f74  xor     eax, eax
0x180012f76  jmp     short loc_180012F7C
0x180012f78  mov     eax, dword ptr [rsp+68h+arg_0]
0x180012f7c  add     rsp, 50h
0x180012f80  pop     rdi
0x180012f81  pop     rsi
0x180012f82  pop     rbx
0x180012f83  retn
0x180012f84  lea     rcx, [rsp+68h+var_30]
0x180012f89  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012f8e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180012f91  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180012f96  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180012f9b  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180012fa2  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180012fa7  call    _CxxThrowException_0
```
