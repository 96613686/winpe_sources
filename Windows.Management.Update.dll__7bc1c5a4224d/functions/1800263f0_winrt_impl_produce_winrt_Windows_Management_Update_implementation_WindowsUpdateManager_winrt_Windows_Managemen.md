# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::GetApplicableSoftwareUpdates(void * *)

- ea: `0x1800263f0`
- end: `0x180026476`
- name: `?GetApplicableSoftwareUpdates@?$produce@UWindowsUpdateManager@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManager2@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000340c`
- `0x1800114a8`
- `0x180014eb4`
- `0x18001c8a0`
- `0x180026324`
- `0x1800263f0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::GetApplicableSoftwareUpdates(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v6; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  try
  {
    *a2 = 0;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v6 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v8);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v6);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    v4 = a1 + 8;
    if ( !a1 )
      v4 = 32;
    winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetApplicableSoftwareUpdates(
      v4,
      &v9);
    *a2 = v9;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800263f0  mov     [rsp+arg_8], rbx
0x1800263f5  push    rdi
0x1800263f6  sub     rsp, 50h
0x1800263fa  mov     rbx, rdx
0x1800263fd  mov     rdi, rcx
0x180026400  mov     qword ptr [rdx], 0
0x180026407  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18002640e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180026413  test    al, al
0x180026415  jz      short loc_18002644C
0x180026417  lea     rcx, [rdi+8]
0x18002641b  mov     eax, 20h ; ' '
0x180026420  test    rdi, rdi
0x180026423  cmovz   rcx, rax
0x180026427  lea     rdx, [rsp+58h+arg_0]
0x18002642c  call    ?GetApplicableSoftwareUpdates@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetApplicableSoftwareUpdates(void)
0x180026431  mov     rax, [rsp+58h+arg_0]
0x180026436  mov     [rbx], rax
0x180026439  xor     eax, eax
0x18002643b  jmp     short loc_180026441
0x18002643d  mov     eax, dword ptr [rsp+58h+arg_0]
0x180026441  mov     rbx, [rsp+58h+arg_8]
0x180026446  add     rsp, 50h
0x18002644a  pop     rdi
0x18002644b  retn
0x18002644c  lea     rcx, [rsp+58h+var_20]
0x180026451  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180026456  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180026459  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18002645e  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180026463  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18002646a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002646f  call    _CxxThrowException_0
```
