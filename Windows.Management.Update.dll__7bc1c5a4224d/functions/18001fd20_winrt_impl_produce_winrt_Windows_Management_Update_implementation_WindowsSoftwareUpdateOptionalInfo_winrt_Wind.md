# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::get_ComplianceGracePeriodInDays(void * *)

- ea: `0x18001fd20`
- end: `0x18001fdae`
- name: `?get_ComplianceGracePeriodInDays@?$produce@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfo@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
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
- `0x18001fd20`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::get_ComplianceGracePeriodInDays(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
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
  v4 = a1 + 24;
  if ( !a1 )
    v4 = 40;
  v5 = *(_QWORD *)v4;
  if ( *(_QWORD *)v4 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 8LL))(*(_QWORD *)v4);
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001fd20  mov     [rsp+arg_8], rbx
0x18001fd25  push    rdi
0x18001fd26  sub     rsp, 50h
0x18001fd2a  mov     rdi, rdx
0x18001fd2d  mov     rbx, rcx
0x18001fd30  mov     qword ptr [rdx], 0
0x18001fd37  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001fd3e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001fd43  test    al, al
0x18001fd45  jz      short loc_18001FD84
0x18001fd47  lea     rax, [rbx+18h]
0x18001fd4b  mov     ecx, 28h ; '('
0x18001fd50  test    rbx, rbx
0x18001fd53  cmovz   rax, rcx
0x18001fd57  mov     rbx, [rax]
0x18001fd5a  test    rbx, rbx
0x18001fd5d  jz      short loc_18001FD6E
0x18001fd5f  mov     rax, [rbx]
0x18001fd62  mov     rcx, rbx
0x18001fd65  mov     rax, [rax+8]
0x18001fd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd6e  mov     [rdi], rbx
0x18001fd71  xor     eax, eax
0x18001fd73  jmp     short loc_18001FD79
0x18001fd75  mov     eax, [rsp+58h+arg_0]
0x18001fd79  mov     rbx, [rsp+58h+arg_8]
0x18001fd7e  add     rsp, 50h
0x18001fd82  pop     rdi
0x18001fd83  retn
0x18001fd84  lea     rcx, [rsp+58h+var_20]
0x18001fd89  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001fd8e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001fd91  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001fd96  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001fd9b  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001fda2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001fda7  call    _CxxThrowException_0
```
