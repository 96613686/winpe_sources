# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::get_MoreInfoUrl(void * *)

- ea: `0x18001e000`
- end: `0x18001e08e`
- name: `?get_MoreInfoUrl@?$produce@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateLocalizationInfo@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000340c`
- `0x1800114a8`
- `0x180014eb4`
- `0x18001c8a0`
- `0x18001e000`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::get_MoreInfoUrl(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF
  int v10; // [rsp+60h] [rbp+8h] BYREF

  *a2 = 0;
  try
  {
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v9);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v7);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    v4 = a1 + 32;
    if ( !a1 )
      v4 = 48;
    v5 = *(_QWORD *)v4;
    if ( *(_QWORD *)v4 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 8LL))(*(_QWORD *)v4);
    *a2 = v5;
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
0x18001e000  mov     [rsp+arg_8], rbx
0x18001e005  push    rdi
0x18001e006  sub     rsp, 50h
0x18001e00a  mov     rdi, rdx
0x18001e00d  mov     rbx, rcx
0x18001e010  mov     qword ptr [rdx], 0
0x18001e017  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001e01e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001e023  test    al, al
0x18001e025  jz      short loc_18001E064
0x18001e027  lea     rax, [rbx+20h]
0x18001e02b  mov     ecx, 30h ; '0'
0x18001e030  test    rbx, rbx
0x18001e033  cmovz   rax, rcx
0x18001e037  mov     rbx, [rax]
0x18001e03a  test    rbx, rbx
0x18001e03d  jz      short loc_18001E04E
0x18001e03f  mov     rax, [rbx]
0x18001e042  mov     rcx, rbx
0x18001e045  mov     rax, [rax+8]
0x18001e049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e04e  mov     [rdi], rbx
0x18001e051  xor     eax, eax
0x18001e053  jmp     short loc_18001E059
0x18001e055  mov     eax, [rsp+58h+arg_0]
0x18001e059  mov     rbx, [rsp+58h+arg_8]
0x18001e05e  add     rsp, 50h
0x18001e062  pop     rdi
0x18001e063  retn
0x18001e064  lea     rcx, [rsp+58h+var_20]
0x18001e069  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001e06e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001e071  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001e076  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001e07b  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001e082  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001e087  call    _CxxThrowException_0
```
