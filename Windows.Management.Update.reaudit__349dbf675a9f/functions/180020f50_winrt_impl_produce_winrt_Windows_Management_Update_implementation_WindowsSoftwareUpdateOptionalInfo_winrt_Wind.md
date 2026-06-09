# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::get_ComplianceDeadlineInDays(void * *)

- ea: `0x180020f50`
- end: `0x180020fe6`
- name: `?get_ComplianceDeadlineInDays@?$produce@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfo@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800035f0`
- `0x18001203c`
- `0x180015ac0`
- `0x18001db60`
- `0x180020f50`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::get_ComplianceDeadlineInDays(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rbx
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF

  *a2 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v9);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v7);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  v4 = a1 + 16;
  if ( !a1 )
    v4 = 32;
  v5 = *(_QWORD *)v4;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180020f50  mov     [rsp+arg_8], rbx
0x180020f55  mov     [rsp+arg_10], rsi
0x180020f5a  push    rdi
0x180020f5b  sub     rsp, 50h
0x180020f5f  mov     rdi, rdx
0x180020f62  mov     rsi, rcx
0x180020f65  and     qword ptr [rdx], 0
0x180020f69  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180020f70  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180020f75  test    al, al
0x180020f77  jz      short loc_180020FBC
0x180020f79  lea     rbx, [rsi+10h]
0x180020f7d  mov     eax, 20h ; ' '
0x180020f82  test    rsi, rsi
0x180020f85  cmovz   rbx, rax
0x180020f89  mov     rbx, [rbx]
0x180020f8c  test    rbx, rbx
0x180020f8f  jz      short loc_180020FA0
0x180020f91  mov     rax, [rbx]
0x180020f94  mov     rcx, rbx
0x180020f97  mov     rax, [rax+8]
0x180020f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fa0  mov     [rdi], rbx
0x180020fa3  xor     eax, eax
0x180020fa5  jmp     short loc_180020FAB
0x180020fa7  mov     eax, [rsp+58h+arg_0]
0x180020fab  mov     rbx, [rsp+58h+arg_8]
0x180020fb0  mov     rsi, [rsp+58h+arg_10]
0x180020fb5  add     rsp, 50h
0x180020fb9  pop     rdi
0x180020fba  retn
0x180020fbc  lea     rcx, [rsp+58h+var_20]
0x180020fc1  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180020fc6  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180020fc9  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180020fce  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180020fd3  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180020fda  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180020fdf  call    _CxxThrowException_0
```
