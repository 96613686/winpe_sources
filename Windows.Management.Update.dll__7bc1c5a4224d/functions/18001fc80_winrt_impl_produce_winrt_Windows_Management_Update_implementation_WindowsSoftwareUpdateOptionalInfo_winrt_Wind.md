# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::get_ComplianceDeadlineInDays(void * *)

- ea: `0x18001fc80`
- end: `0x18001fd0e`
- name: `?get_ComplianceDeadlineInDays@?$produce@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfo@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
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
- `0x18001fc80`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::get_ComplianceDeadlineInDays(
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
  v4 = a1 + 16;
  if ( !a1 )
    v4 = 32;
  v5 = *(_QWORD *)v4;
  if ( *(_QWORD *)v4 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 8LL))(*(_QWORD *)v4);
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001fc80  mov     [rsp+arg_8], rbx
0x18001fc85  push    rdi
0x18001fc86  sub     rsp, 50h
0x18001fc8a  mov     rdi, rdx
0x18001fc8d  mov     rbx, rcx
0x18001fc90  mov     qword ptr [rdx], 0
0x18001fc97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001fc9e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001fca3  test    al, al
0x18001fca5  jz      short loc_18001FCE4
0x18001fca7  lea     rax, [rbx+10h]
0x18001fcab  mov     ecx, 20h ; ' '
0x18001fcb0  test    rbx, rbx
0x18001fcb3  cmovz   rax, rcx
0x18001fcb7  mov     rbx, [rax]
0x18001fcba  test    rbx, rbx
0x18001fcbd  jz      short loc_18001FCCE
0x18001fcbf  mov     rax, [rbx]
0x18001fcc2  mov     rcx, rbx
0x18001fcc5  mov     rax, [rax+8]
0x18001fcc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcce  mov     [rdi], rbx
0x18001fcd1  xor     eax, eax
0x18001fcd3  jmp     short loc_18001FCD9
0x18001fcd5  mov     eax, [rsp+58h+arg_0]
0x18001fcd9  mov     rbx, [rsp+58h+arg_8]
0x18001fcde  add     rsp, 50h
0x18001fce2  pop     rdi
0x18001fce3  retn
0x18001fce4  lea     rcx, [rsp+58h+var_20]
0x18001fce9  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001fcee  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001fcf1  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001fcf6  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001fcfb  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001fd02  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001fd07  call    _CxxThrowException_0
```
