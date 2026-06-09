# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::get_Description(void * *)

- ea: `0x18001def0`
- end: `0x18001df6f`
- name: `?get_Description@?$produce@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateLocalizationInfo@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
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
- `0x18001def0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::get_Description(
        __int64 a1,
        _QWORD *a2)
{
  struct winrt::impl::hstring_header *v4; // rdx
  __int64 v5; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF
  int v10; // [rsp+60h] [rbp+8h] BYREF

  try
  {
    *a2 = 0;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v9);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v7);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    v5 = a1 + 24;
    if ( !a1 )
      v5 = 40;
    *a2 = winrt::impl::duplicate_hstring(*(winrt::impl **)v5, v4);
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
0x18001def0  mov     [rsp+arg_8], rbx
0x18001def5  push    rdi
0x18001def6  sub     rsp, 50h
0x18001defa  mov     rbx, rdx
0x18001defd  mov     rdi, rcx
0x18001df00  mov     qword ptr [rdx], 0
0x18001df07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001df0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001df13  test    al, al
0x18001df15  jz      short loc_18001DF45
0x18001df17  lea     rcx, [rdi+18h]
0x18001df1b  mov     eax, 28h ; '('
0x18001df20  test    rdi, rdi
0x18001df23  cmovz   rcx, rax
0x18001df27  mov     rcx, [rcx]; this
0x18001df2a  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001df2f  mov     [rbx], rax
0x18001df32  xor     eax, eax
0x18001df34  jmp     short loc_18001DF3A
0x18001df36  mov     eax, [rsp+58h+arg_0]
0x18001df3a  mov     rbx, [rsp+58h+arg_8]
0x18001df3f  add     rsp, 50h
0x18001df43  pop     rdi
0x18001df44  retn
0x18001df45  lea     rcx, [rsp+58h+var_20]
0x18001df4a  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001df4f  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001df52  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001df57  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001df5c  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001df63  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001df68  call    _CxxThrowException_0
```
