# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfoFactory>::CreateInstance(bool,bool,bool,bool,void * *)

- ea: `0x180012c70`
- end: `0x180012d5f`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateApprovalInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateApprovalInfoFactory@3456@@impl@winrt@@UEAAH_N000PEAPEAX@Z`
- size: `239`
- prototype: `__int64 __fastcall(__int64, char, char, char, char, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800114a8`
- `0x180012c70`
- `0x180014eb4`
- `0x18001c8a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfoFactory>::CreateInstance(
        __int64 a1,
        char a2,
        char a3,
        char a4,
        char a5,
        _QWORD *a6)
{
  _QWORD *v9; // rdi
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v13; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v15[64]; // [rsp+38h] [rbp-40h] BYREF

  v9 = a6;
  *a6 = 0;
  try
  {
    v10 = operator new(0x20u);
    v10[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfo>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v10[1] = 1;
    *v10 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo::`vftable';
    *((_DWORD *)v10 + 6) = 0;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v15, v11);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v13);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v10 + 24) = a2;
    *((_BYTE *)v10 + 25) = a3;
    *((_BYTE *)v10 + 26) = a4;
    *((_BYTE *)v10 + 27) = a5;
    *v10 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo::`vftable';
    *v9 = v10 + 2;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&a5);
  }
  return result;
}

```

## disassembly

```asm
0x180012c70  mov     [rsp+arg_10], rbx
0x180012c75  mov     [rsp+arg_0], rcx
0x180012c7a  push    rsi
0x180012c7b  push    rdi
0x180012c7c  push    r12
0x180012c7e  push    r14
0x180012c80  push    r15
0x180012c82  sub     rsp, 50h
0x180012c86  mov     sil, r9b
0x180012c89  mov     r14b, r8b
0x180012c8c  mov     r15b, dl
0x180012c8f  mov     rdi, [rsp+78h+arg_28]
0x180012c97  mov     qword ptr [rdi], 0
0x180012c9e  mov     ecx, 20h ; ' '; Size
0x180012ca3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012ca8  mov     rbx, rax
0x180012cab  mov     [rsp+78h+arg_0], rax
0x180012cb3  lea     r12, [rax+10h]
0x180012cb7  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateApprovalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateApprovalInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfo>::`vftable'
0x180012cbe  mov     [r12], rax
0x180012cc2  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180012cc9  mov     qword ptr [rbx+8], 1
0x180012cd1  lea     rax, ??_7WindowsSoftwareUpdateApprovalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo::`vftable'
0x180012cd8  mov     [rbx], rax
0x180012cdb  mov     dword ptr [rbx+18h], 0
0x180012ce2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180012ce9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180012cee  test    al, al
0x180012cf0  jz      short loc_180012D35
0x180012cf2  mov     [rbx+18h], r15b
0x180012cf6  mov     [rbx+19h], r14b
0x180012cfa  mov     [rbx+1Ah], sil
0x180012cfe  mov     al, [rsp+78h+arg_20]
0x180012d05  mov     [rbx+1Bh], al
0x180012d08  lea     rax, ??_7WindowsSoftwareUpdateApprovalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo::`vftable'
0x180012d0f  mov     [rbx], rax
0x180012d12  mov     [rdi], r12
0x180012d15  xor     eax, eax
0x180012d17  jmp     short loc_180012D20
0x180012d19  mov     eax, dword ptr [rsp+78h+arg_20]
0x180012d20  mov     rbx, [rsp+78h+arg_10]
0x180012d28  add     rsp, 50h
0x180012d2c  pop     r15
0x180012d2e  pop     r14
0x180012d30  pop     r12
0x180012d32  pop     rdi
0x180012d33  pop     rsi
0x180012d34  retn
0x180012d35  lea     rcx, [rsp+78h+var_40]
0x180012d3a  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012d3f  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180012d42  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180012d47  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180012d4c  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180012d53  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180012d58  call    _CxxThrowException_0
```
