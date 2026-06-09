# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfoFactory>::CreateInstance(void *,void *,void * *)

- ea: `0x180013ab0`
- end: `0x180013b8f`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateOptionalInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfoFactory@3456@@impl@winrt@@UEAAHPEAX0PEAPEAX@Z`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180013ab0`
- `0x180015ac0`
- `0x18001db60`
- `0x180020464`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfoFactory>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 *a4)
{
  _QWORD *v5; // rbx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v9[48]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v10; // [rsp+70h] [rbp+8h] BYREF
  __int64 v11; // [rsp+78h] [rbp+10h] BYREF
  __int64 v12; // [rsp+80h] [rbp+18h] BYREF
  _QWORD *v13; // [rsp+88h] [rbp+20h]

  v12 = a3;
  v11 = a2;
  v10 = a1;
  *a4 = 0;
  try
  {
    v5 = operator new(0x30u);
    v13 = v5;
    v5[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v5[1] = 1;
    *v5 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable';
    v5[3] = 0;
    v5[4] = 0;
    v5[5] = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v9);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v7);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(
      (__int64)v5,
      &v11,
      &v12);
    *v5 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable';
    *a4 = (unsigned __int64)(v5 + 2) & -(__int64)(v5 != 0);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v10);
  }
  return result;
}

```

## disassembly

```asm
0x180013ab0  mov     [rsp+arg_10], r8
0x180013ab5  mov     [rsp+arg_8], rdx
0x180013aba  mov     [rsp+arg_0], rcx
0x180013abf  push    rbx
0x180013ac0  push    rsi
0x180013ac1  push    rdi
0x180013ac2  sub     rsp, 50h
0x180013ac6  mov     rdi, r9
0x180013ac9  and     qword ptr [r9], 0
0x180013acd  mov     ecx, 30h ; '0'; Size
0x180013ad2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013ad7  mov     rbx, rax
0x180013ada  mov     [rsp+68h+arg_18], rax
0x180013ae2  lea     rsi, [rax+10h]
0x180013ae6  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::`vftable'
0x180013aed  mov     [rsi], rax
0x180013af0  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013af7  mov     qword ptr [rbx+8], 1
0x180013aff  lea     rax, ??_7WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable'
0x180013b06  mov     [rbx], rax
0x180013b09  and     qword ptr [rbx+18h], 0
0x180013b0e  and     qword ptr [rbx+20h], 0
0x180013b13  and     qword ptr [rbx+28h], 0
0x180013b18  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180013b1f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180013b24  test    al, al
0x180013b26  jz      short loc_180013B65
0x180013b28  lea     r8, [rsp+68h+arg_10]
0x180013b30  lea     rdx, [rsp+68h+arg_8]
0x180013b35  mov     rcx, rbx
0x180013b38  call    ?InitializeComplianceParameters@WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@AEAAXAEBU?$IReference@H@Foundation@56@0@Z; winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(winrt::Windows::Foundation::IReference<int> const &,winrt::Windows::Foundation::IReference<int> const &)
0x180013b3d  nop
0x180013b3e  lea     rax, ??_7WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable'
0x180013b45  mov     [rbx], rax
0x180013b48  neg     rbx
0x180013b4b  sbb     rax, rax
0x180013b4e  and     rax, rsi
0x180013b51  mov     [rdi], rax
0x180013b54  xor     eax, eax
0x180013b56  jmp     short loc_180013B5C
0x180013b58  mov     eax, dword ptr [rsp+68h+arg_0]
0x180013b5c  add     rsp, 50h
0x180013b60  pop     rdi
0x180013b61  pop     rsi
0x180013b62  pop     rbx
0x180013b63  retn
0x180013b65  lea     rcx, [rsp+68h+var_30]
0x180013b6a  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180013b6f  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180013b72  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180013b77  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180013b7c  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180013b83  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180013b88  call    _CxxThrowException_0
```
