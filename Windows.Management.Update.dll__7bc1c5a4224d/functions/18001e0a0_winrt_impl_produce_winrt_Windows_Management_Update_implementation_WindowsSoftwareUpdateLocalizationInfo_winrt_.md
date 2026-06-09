# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::get_Title(void * *)

- ea: `0x18001e0a0`
- end: `0x18001e11f`
- name: `?get_Title@?$produce@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateLocalizationInfo@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000340c`
- `0x1800114a8`
- `0x180014eb4`
- `0x180014ee0`
- `0x18001c8a0`
- `0x18001e0a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::get_Title(
        __int64 a1,
        _QWORD *a2)
{
  struct winrt::impl::hstring_header *v4; // rdx
  __int64 v5; // rcx
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF

  *a2 = 0;
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v9);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v7);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  v5 = a1 + 16;
  if ( !a1 )
    v5 = 32;
  *a2 = winrt::impl::duplicate_hstring(*(winrt::impl **)v5, v4);
  return 0;
}

```

## disassembly

```asm
0x18001e0a0  mov     [rsp+arg_8], rbx
0x18001e0a5  push    rdi
0x18001e0a6  sub     rsp, 50h
0x18001e0aa  mov     rbx, rdx
0x18001e0ad  mov     rdi, rcx
0x18001e0b0  mov     qword ptr [rdx], 0
0x18001e0b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001e0be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001e0c3  test    al, al
0x18001e0c5  jz      short loc_18001E0F5
0x18001e0c7  lea     rcx, [rdi+10h]
0x18001e0cb  mov     eax, 20h ; ' '
0x18001e0d0  test    rdi, rdi
0x18001e0d3  cmovz   rcx, rax
0x18001e0d7  mov     rcx, [rcx]; this
0x18001e0da  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001e0df  mov     [rbx], rax
0x18001e0e2  xor     eax, eax
0x18001e0e4  jmp     short loc_18001E0EA
0x18001e0e6  mov     eax, [rsp+58h+arg_0]
0x18001e0ea  mov     rbx, [rsp+58h+arg_8]
0x18001e0ef  add     rsp, 50h
0x18001e0f3  pop     rdi
0x18001e0f4  retn
0x18001e0f5  lea     rcx, [rsp+58h+var_20]
0x18001e0fa  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001e0ff  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001e102  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001e107  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001e10c  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001e113  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001e118  call    _CxxThrowException_0
```
