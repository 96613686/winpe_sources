# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::get_LocalizationInfo(void * *)

- ea: `0x180021230`
- end: `0x1800212c6`
- name: `?get_LocalizationInfo@?$produce@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfo@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800035f0`
- `0x18001203c`
- `0x180015ac0`
- `0x18001db60`
- `0x180021230`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::get_LocalizationInfo(
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
  v4 = a1 + 8;
  if ( !a1 )
    v4 = 24;
  v5 = *(_QWORD *)v4;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180021230  mov     [rsp+arg_8], rbx
0x180021235  mov     [rsp+arg_10], rsi
0x18002123a  push    rdi
0x18002123b  sub     rsp, 50h
0x18002123f  mov     rdi, rdx
0x180021242  mov     rsi, rcx
0x180021245  and     qword ptr [rdx], 0
0x180021249  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180021250  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180021255  test    al, al
0x180021257  jz      short loc_18002129C
0x180021259  lea     rbx, [rsi+8]
0x18002125d  mov     eax, 18h
0x180021262  test    rsi, rsi
0x180021265  cmovz   rbx, rax
0x180021269  mov     rbx, [rbx]
0x18002126c  test    rbx, rbx
0x18002126f  jz      short loc_180021280
0x180021271  mov     rax, [rbx]
0x180021274  mov     rcx, rbx
0x180021277  mov     rax, [rax+8]
0x18002127b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021280  mov     [rdi], rbx
0x180021283  xor     eax, eax
0x180021285  jmp     short loc_18002128B
0x180021287  mov     eax, [rsp+58h+arg_0]
0x18002128b  mov     rbx, [rsp+58h+arg_8]
0x180021290  mov     rsi, [rsp+58h+arg_10]
0x180021295  add     rsp, 50h
0x180021299  pop     rdi
0x18002129a  retn
0x18002129c  lea     rcx, [rsp+58h+var_20]
0x1800212a1  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800212a6  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800212a9  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800212ae  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800212b3  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800212ba  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800212bf  call    _CxxThrowException_0
```
