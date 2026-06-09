# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResultFactory>::CreateInstance(int,int,uint,unsigned __int64,void * *)

- ea: `0x180013cc0`
- end: `0x180013dc1`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateProviderActionResult@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderActionResultFactory@3456@@impl@winrt@@UEAAHHHI_KPEAPEAX@Z`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180013cc0`
- `0x180015ac0`
- `0x18001db60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResultFactory>::CreateInstance(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned __int64 *a6)
{
  unsigned __int64 *v9; // rdi
  _QWORD *v10; // rbx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v12; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  char v14[64]; // [rsp+38h] [rbp-40h] BYREF
  int v15; // [rsp+98h] [rbp+20h] BYREF

  v9 = a6;
  *a6 = 0;
  try
  {
    v10 = operator new(0x30u);
    v10[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v10[1] = 1;
    *v10 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable';
    *((_DWORD *)v10 + 6) = 0;
    *((_DWORD *)v10 + 7) = 0;
    *((_DWORD *)v10 + 8) = 0;
    v10[5] = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v14);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v12);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_DWORD *)v10 + 6) = a2;
    *((_DWORD *)v10 + 7) = a3;
    *((_DWORD *)v10 + 8) = a4;
    v10[5] = a5;
    *v10 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable';
    *v9 = (unsigned __int64)(v10 + 2) & -(__int64)(v10 != 0);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v15);
  }
  return result;
}

```

## disassembly

```asm
0x180013cc0  mov     [rsp+arg_8], rbx
0x180013cc5  mov     [rsp+arg_0], rcx
0x180013cca  push    rsi
0x180013ccb  push    rdi
0x180013ccc  push    r12
0x180013cce  push    r14
0x180013cd0  push    r15
0x180013cd2  sub     rsp, 50h
0x180013cd6  mov     esi, r9d
0x180013cd9  mov     r14d, r8d
0x180013cdc  mov     r15d, edx
0x180013cdf  mov     rdi, [rsp+78h+arg_28]
0x180013ce7  and     qword ptr [rdi], 0
0x180013ceb  mov     ecx, 30h ; '0'; Size
0x180013cf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013cf5  mov     rbx, rax
0x180013cf8  mov     [rsp+78h+arg_0], rax
0x180013d00  lea     r12, [rax+10h]
0x180013d04  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateProviderActionResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderActionResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResult>::`vftable'
0x180013d0b  mov     [r12], rax
0x180013d0f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013d16  mov     qword ptr [rbx+8], 1
0x180013d1e  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateProviderActionResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable'
0x180013d25  mov     [rbx], rax
0x180013d28  and     dword ptr [rbx+18h], 0
0x180013d2c  and     dword ptr [rbx+1Ch], 0
0x180013d30  and     dword ptr [rbx+20h], 0
0x180013d34  and     qword ptr [rbx+28h], 0
0x180013d39  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180013d40  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180013d45  test    al, al
0x180013d47  jz      short loc_180013D97
0x180013d49  mov     [rbx+18h], r15d
0x180013d4d  mov     [rbx+1Ch], r14d
0x180013d51  mov     [rbx+20h], esi
0x180013d54  mov     rax, [rsp+78h+arg_20]
0x180013d5c  mov     [rbx+28h], rax
0x180013d60  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateProviderActionResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable'
0x180013d67  mov     [rbx], rax
0x180013d6a  neg     rbx
0x180013d6d  sbb     rax, rax
0x180013d70  and     rax, r12
0x180013d73  mov     [rdi], rax
0x180013d76  xor     eax, eax
0x180013d78  jmp     short loc_180013D81
0x180013d7a  mov     eax, [rsp+78h+arg_18]
0x180013d81  mov     rbx, [rsp+78h+arg_8]
0x180013d89  add     rsp, 50h
0x180013d8d  pop     r15
0x180013d8f  pop     r14
0x180013d91  pop     r12
0x180013d93  pop     rdi
0x180013d94  pop     rsi
0x180013d95  retn
0x180013d97  lea     rcx, [rsp+78h+var_40]
0x180013d9c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180013da1  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180013da4  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180013da9  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180013dae  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180013db5  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180013dba  call    _CxxThrowException_0
```
