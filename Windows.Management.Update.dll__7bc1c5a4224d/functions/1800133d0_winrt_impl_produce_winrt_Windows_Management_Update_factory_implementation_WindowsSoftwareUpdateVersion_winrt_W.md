# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersionFactory>::CreateInstance(uint,uint,uint,uint,void * *)

- ea: `0x1800133d0`
- end: `0x1800134c7`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateVersion@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateVersionFactory@3456@@impl@winrt@@UEAAHIIIIPEAPEAX@Z`
- size: `247`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800114a8`
- `0x1800133d0`
- `0x180014eb4`
- `0x18001c8a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersionFactory>::CreateInstance(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        _QWORD *a6)
{
  _QWORD *v9; // rdi
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v13; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v15[64]; // [rsp+38h] [rbp-40h] BYREF

  v9 = a6;
  *a6 = 0;
  try
  {
    v10 = operator new(0x28u);
    v10[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v10[1] = 1;
    *v10 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion::`vftable';
    v10[3] = 0;
    v10[4] = 0;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v15, v11);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v13);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_DWORD *)v10 + 6) = a2;
    *((_DWORD *)v10 + 7) = a3;
    *((_DWORD *)v10 + 8) = a4;
    *((_DWORD *)v10 + 9) = a5;
    *v10 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion::`vftable';
    *v9 = v10 + 2;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&a5);
  }
  return result;
}

```

## disassembly

```asm
0x1800133d0  mov     [rsp+arg_10], rbx
0x1800133d5  mov     [rsp+arg_0], rcx
0x1800133da  push    rsi
0x1800133db  push    rdi
0x1800133dc  push    r12
0x1800133de  push    r14
0x1800133e0  push    r15
0x1800133e2  sub     rsp, 50h
0x1800133e6  mov     esi, r9d
0x1800133e9  mov     r14d, r8d
0x1800133ec  mov     r15d, edx
0x1800133ef  mov     rdi, [rsp+78h+arg_28]
0x1800133f7  mov     qword ptr [rdi], 0
0x1800133fe  mov     ecx, 28h ; '('; Size
0x180013403  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013408  mov     rbx, rax
0x18001340b  mov     [rsp+78h+arg_0], rax
0x180013413  lea     r12, [rax+10h]
0x180013417  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateVersion@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::`vftable'
0x18001341e  mov     [r12], rax
0x180013422  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013429  mov     qword ptr [rbx+8], 1
0x180013431  lea     rax, ??_7WindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion::`vftable'
0x180013438  mov     [rbx], rax
0x18001343b  mov     qword ptr [rbx+18h], 0
0x180013443  mov     qword ptr [rbx+20h], 0
0x18001344b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180013452  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180013457  test    al, al
0x180013459  jz      short loc_18001349D
0x18001345b  mov     [rbx+18h], r15d
0x18001345f  mov     [rbx+1Ch], r14d
0x180013463  mov     [rbx+20h], esi
0x180013466  mov     eax, [rsp+78h+arg_20]
0x18001346d  mov     [rbx+24h], eax
0x180013470  lea     rax, ??_7WindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion::`vftable'
0x180013477  mov     [rbx], rax
0x18001347a  mov     [rdi], r12
0x18001347d  xor     eax, eax
0x18001347f  jmp     short loc_180013488
0x180013481  mov     eax, [rsp+78h+arg_20]
0x180013488  mov     rbx, [rsp+78h+arg_10]
0x180013490  add     rsp, 50h
0x180013494  pop     r15
0x180013496  pop     r14
0x180013498  pop     r12
0x18001349a  pop     rdi
0x18001349b  pop     rsi
0x18001349c  retn
0x18001349d  lea     rcx, [rsp+78h+var_40]
0x1800134a2  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800134a7  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800134aa  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800134af  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800134b4  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800134bb  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800134c0  call    _CxxThrowException_0
```
