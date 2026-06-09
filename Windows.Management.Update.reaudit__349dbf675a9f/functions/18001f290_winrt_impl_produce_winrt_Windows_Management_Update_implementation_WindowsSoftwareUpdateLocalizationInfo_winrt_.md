# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::get_MoreInfoUrl(void * *)

- ea: `0x18001f290`
- end: `0x18001f326`
- name: `?get_MoreInfoUrl@?$produce@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateLocalizationInfo@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
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
- `0x18001f290`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::get_MoreInfoUrl(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rbx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF
  int v10; // [rsp+60h] [rbp+8h] BYREF

  *a2 = 0;
  try
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v9);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v7);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    v4 = a1 + 32;
    if ( !a1 )
      v4 = 48;
    v5 = *(_QWORD *)v4;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
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
0x18001f290  mov     [rsp+arg_8], rbx
0x18001f295  mov     [rsp+arg_10], rsi
0x18001f29a  push    rdi
0x18001f29b  sub     rsp, 50h
0x18001f29f  mov     rdi, rdx
0x18001f2a2  mov     rsi, rcx
0x18001f2a5  and     qword ptr [rdx], 0
0x18001f2a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001f2b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001f2b5  test    al, al
0x18001f2b7  jz      short loc_18001F2FC
0x18001f2b9  lea     rbx, [rsi+20h]
0x18001f2bd  mov     eax, 30h ; '0'
0x18001f2c2  test    rsi, rsi
0x18001f2c5  cmovz   rbx, rax
0x18001f2c9  mov     rbx, [rbx]
0x18001f2cc  test    rbx, rbx
0x18001f2cf  jz      short loc_18001F2E0
0x18001f2d1  mov     rax, [rbx]
0x18001f2d4  mov     rcx, rbx
0x18001f2d7  mov     rax, [rax+8]
0x18001f2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2e0  mov     [rdi], rbx
0x18001f2e3  xor     eax, eax
0x18001f2e5  jmp     short loc_18001F2EB
0x18001f2e7  mov     eax, [rsp+58h+arg_0]
0x18001f2eb  mov     rbx, [rsp+58h+arg_8]
0x18001f2f0  mov     rsi, [rsp+58h+arg_10]
0x18001f2f5  add     rsp, 50h
0x18001f2f9  pop     rdi
0x18001f2fa  retn
0x18001f2fc  lea     rcx, [rsp+58h+var_20]
0x18001f301  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001f306  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001f309  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001f30e  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001f313  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001f31a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001f31f  call    _CxxThrowException_0
```
