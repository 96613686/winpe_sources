# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersionFactory>::CreateInstance(uint,uint,uint,uint,void * *)

- ea: `0x180013fc0`
- end: `0x1800140be`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateVersion@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateVersionFactory@3456@@impl@winrt@@UEAAHIIIIPEAPEAX@Z`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180013fc0`
- `0x180015ac0`
- `0x18001db60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersionFactory>::CreateInstance(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        unsigned __int64 *a6)
{
  unsigned __int64 *v9; // rdi
  _QWORD *v10; // rbx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v12; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  char v14[64]; // [rsp+38h] [rbp-40h] BYREF

  v9 = a6;
  *a6 = 0;
  try
  {
    v10 = operator new(0x28u);
    v10[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v10[1] = 1;
    *v10 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion::`vftable';
    *((_DWORD *)v10 + 6) = 0;
    *((_DWORD *)v10 + 7) = 0;
    *((_DWORD *)v10 + 8) = 0;
    *((_DWORD *)v10 + 9) = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v14);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v12);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_DWORD *)v10 + 6) = a2;
    *((_DWORD *)v10 + 7) = a3;
    *((_DWORD *)v10 + 8) = a4;
    *((_DWORD *)v10 + 9) = a5;
    *v10 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion::`vftable';
    *v9 = (unsigned __int64)(v10 + 2) & -(__int64)(v10 != 0);
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
0x180013fc0  mov     [rsp+arg_10], rbx
0x180013fc5  mov     [rsp+arg_0], rcx
0x180013fca  push    rsi
0x180013fcb  push    rdi
0x180013fcc  push    r12
0x180013fce  push    r14
0x180013fd0  push    r15
0x180013fd2  sub     rsp, 50h
0x180013fd6  mov     esi, r9d
0x180013fd9  mov     r14d, r8d
0x180013fdc  mov     r15d, edx
0x180013fdf  mov     rdi, [rsp+78h+arg_28]
0x180013fe7  and     qword ptr [rdi], 0
0x180013feb  mov     ecx, 28h ; '('; Size
0x180013ff0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013ff5  mov     rbx, rax
0x180013ff8  mov     [rsp+78h+arg_0], rax
0x180014000  lea     r12, [rax+10h]
0x180014004  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateVersion@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::`vftable'
0x18001400b  mov     [r12], rax
0x18001400f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180014016  mov     qword ptr [rbx+8], 1
0x18001401e  lea     rax, ??_7WindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion::`vftable'
0x180014025  mov     [rbx], rax
0x180014028  and     dword ptr [rbx+18h], 0
0x18001402c  and     dword ptr [rbx+1Ch], 0
0x180014030  and     dword ptr [rbx+20h], 0
0x180014034  and     dword ptr [rbx+24h], 0
0x180014038  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001403f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180014044  test    al, al
0x180014046  jz      short loc_180014094
0x180014048  mov     [rbx+18h], r15d
0x18001404c  mov     [rbx+1Ch], r14d
0x180014050  mov     [rbx+20h], esi
0x180014053  mov     eax, [rsp+78h+arg_20]
0x18001405a  mov     [rbx+24h], eax
0x18001405d  lea     rax, ??_7WindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion::`vftable'
0x180014064  mov     [rbx], rax
0x180014067  neg     rbx
0x18001406a  sbb     rax, rax
0x18001406d  and     rax, r12
0x180014070  mov     [rdi], rax
0x180014073  xor     eax, eax
0x180014075  jmp     short loc_18001407E
0x180014077  mov     eax, [rsp+78h+arg_20]
0x18001407e  mov     rbx, [rsp+78h+arg_10]
0x180014086  add     rsp, 50h
0x18001408a  pop     r15
0x18001408c  pop     r14
0x18001408e  pop     r12
0x180014090  pop     rdi
0x180014091  pop     rsi
0x180014092  retn
0x180014094  lea     rcx, [rsp+78h+var_40]
0x180014099  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001409e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800140a1  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800140a6  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800140ab  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800140b2  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800140b7  call    _CxxThrowException_0
```
