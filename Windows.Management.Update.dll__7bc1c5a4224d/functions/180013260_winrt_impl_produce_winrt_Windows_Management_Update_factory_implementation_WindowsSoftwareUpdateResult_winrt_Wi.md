# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance(bool,uint,void * *)

- ea: `0x180013260`
- end: `0x180013342`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateResult@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResultFactory@3456@@impl@winrt@@UEAAH_NIPEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, char, int, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800114a8`
- `0x180013260`
- `0x180014eb4`
- `0x18001c8a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance(
        __int64 a1,
        char a2,
        int a3,
        _QWORD *a4)
{
  _QWORD *v7; // rbx
  __int64 v8; // rdx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v10; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v12[24]; // [rsp+38h] [rbp-30h] BYREF
  int v13; // [rsp+78h] [rbp+10h] BYREF

  *a4 = 0;
  try
  {
    v7 = operator new(0x28u);
    v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v7[1] = 1;
    *v7 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
    *((_WORD *)v7 + 12) = 1;
    *((_DWORD *)v7 + 7) = 0;
    v7[4] = 0;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v12, v8);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v10);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v7 + 24) = a2;
    *((_DWORD *)v7 + 7) = a3;
    *v7 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
    *a4 = v7 + 2;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v13);
  }
  return result;
}

```

## disassembly

```asm
0x180013260  mov     [rsp+arg_10], rbx
0x180013265  mov     [rsp+arg_18], rsi
0x18001326a  mov     [rsp+arg_0], rcx
0x18001326f  push    rdi
0x180013270  push    r14
0x180013272  push    r15
0x180013274  sub     rsp, 50h
0x180013278  mov     rdi, r9
0x18001327b  mov     esi, r8d
0x18001327e  mov     r14b, dl
0x180013281  mov     qword ptr [r9], 0
0x180013288  mov     ecx, 28h ; '('; Size
0x18001328d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013292  mov     rbx, rax
0x180013295  mov     [rsp+68h+arg_0], rax
0x18001329a  lea     r15, [rax+10h]
0x18001329e  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable'
0x1800132a5  mov     [r15], rax
0x1800132a8  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800132af  mov     qword ptr [rbx+8], 1
0x1800132b7  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x1800132be  mov     [rbx], rax
0x1800132c1  mov     word ptr [rbx+18h], 1
0x1800132c7  mov     dword ptr [rbx+1Ch], 0
0x1800132ce  mov     qword ptr [rbx+20h], 0
0x1800132d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800132dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800132e2  test    al, al
0x1800132e4  jz      short loc_180013318
0x1800132e6  mov     [rbx+18h], r14b
0x1800132ea  mov     [rbx+1Ch], esi
0x1800132ed  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x1800132f4  mov     [rbx], rax
0x1800132f7  mov     [rdi], r15
0x1800132fa  xor     eax, eax
0x1800132fc  jmp     short loc_180013302
0x1800132fe  mov     eax, [rsp+68h+arg_8]
0x180013302  lea     r11, [rsp+68h+var_18]
0x180013307  mov     rbx, [r11+30h]
0x18001330b  mov     rsi, [r11+38h]
0x18001330f  mov     rsp, r11
0x180013312  pop     r15
0x180013314  pop     r14
0x180013316  pop     rdi
0x180013317  retn
0x180013318  lea     rcx, [rsp+68h+var_30]
0x18001331d  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180013322  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180013325  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18001332a  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001332f  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180013336  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001333b  call    _CxxThrowException_0
```
