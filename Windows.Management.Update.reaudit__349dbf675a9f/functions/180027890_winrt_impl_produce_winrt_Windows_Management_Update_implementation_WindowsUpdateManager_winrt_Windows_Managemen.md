# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::GetApplicableSoftwareUpdates(void * *)

- ea: `0x180027890`
- end: `0x180027914`
- name: `?GetApplicableSoftwareUpdates@?$produce@UWindowsUpdateManager@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManager2@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800035f0`
- `0x18001203c`
- `0x180015ac0`
- `0x18001db60`
- `0x1800277cc`
- `0x180027890`

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
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v6 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v8);
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
0x180027890  mov     [rsp+arg_8], rbx
0x180027895  push    rdi
0x180027896  sub     rsp, 50h
0x18002789a  mov     rbx, rdx
0x18002789d  mov     rdi, rcx
0x1800278a0  and     qword ptr [rdx], 0
0x1800278a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800278ab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800278b0  test    al, al
0x1800278b2  jz      short loc_1800278EA
0x1800278b4  lea     rcx, [rdi+8]
0x1800278b8  mov     eax, 20h ; ' '
0x1800278bd  test    rdi, rdi
0x1800278c0  cmovz   rcx, rax
0x1800278c4  lea     rdx, [rsp+58h+arg_0]
0x1800278c9  call    ?GetApplicableSoftwareUpdates@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetApplicableSoftwareUpdates(void)
0x1800278ce  mov     rax, [rsp+58h+arg_0]
0x1800278d3  mov     [rbx], rax
0x1800278d6  xor     eax, eax
0x1800278d8  jmp     short loc_1800278DE
0x1800278da  mov     eax, dword ptr [rsp+58h+arg_0]
0x1800278de  mov     rbx, [rsp+58h+arg_8]
0x1800278e3  add     rsp, 50h
0x1800278e7  pop     rdi
0x1800278e8  retn
0x1800278ea  lea     rcx, [rsp+58h+var_20]
0x1800278ef  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800278f4  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800278f7  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800278fc  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180027901  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180027908  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002790d  call    _CxxThrowException_0
```
