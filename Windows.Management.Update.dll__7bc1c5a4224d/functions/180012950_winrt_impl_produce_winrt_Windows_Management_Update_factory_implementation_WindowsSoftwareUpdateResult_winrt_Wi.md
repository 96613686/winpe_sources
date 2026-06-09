# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance3(bool,bool,uint,unsigned __int64,void * *)

- ea: `0x180012950`
- end: `0x180012a4e`
- name: `?CreateInstance3@?$produce@UWindowsSoftwareUpdateResult@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResultFactory@3456@@impl@winrt@@UEAAH_N0I_KPEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(__int64, char, char, int, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800114a8`
- `0x180012950`
- `0x180014eb4`
- `0x18001c8a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance3(
        __int64 a1,
        char a2,
        char a3,
        int a4,
        __int64 a5,
        _QWORD *a6)
{
  _QWORD *v9; // rdi
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v13; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v15[64]; // [rsp+38h] [rbp-40h] BYREF
  int v16; // [rsp+88h] [rbp+10h] BYREF

  v9 = a6;
  *a6 = 0;
  try
  {
    v10 = operator new(0x28u);
    v10[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v10[1] = 1;
    *v10 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
    *((_WORD *)v10 + 12) = 1;
    *((_DWORD *)v10 + 7) = 0;
    v10[4] = 0;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v15, v11);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v13);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v10 + 24) = a2;
    *((_BYTE *)v10 + 25) = a3;
    *((_DWORD *)v10 + 7) = a4;
    v10[4] = a5;
    *v10 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
    *v9 = v10 + 2;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v16);
  }
  return result;
}

```

## disassembly

```asm
0x180012950  mov     [rsp+arg_10], rbx
0x180012955  mov     [rsp+arg_0], rcx
0x18001295a  push    rsi
0x18001295b  push    rdi
0x18001295c  push    r12
0x18001295e  push    r14
0x180012960  push    r15
0x180012962  sub     rsp, 50h
0x180012966  mov     esi, r9d
0x180012969  mov     r14b, r8b
0x18001296c  mov     r15b, dl
0x18001296f  mov     rdi, [rsp+78h+arg_28]
0x180012977  mov     qword ptr [rdi], 0
0x18001297e  mov     ecx, 28h ; '('; Size
0x180012983  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012988  mov     rbx, rax
0x18001298b  mov     [rsp+78h+arg_0], rax
0x180012993  lea     r12, [rax+10h]
0x180012997  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable'
0x18001299e  mov     [r12], rax
0x1800129a2  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800129a9  mov     qword ptr [rbx+8], 1
0x1800129b1  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x1800129b8  mov     [rbx], rax
0x1800129bb  mov     word ptr [rbx+18h], 1
0x1800129c1  mov     dword ptr [rbx+1Ch], 0
0x1800129c8  mov     qword ptr [rbx+20h], 0
0x1800129d0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800129d7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800129dc  test    al, al
0x1800129de  jz      short loc_180012A24
0x1800129e0  mov     [rbx+18h], r15b
0x1800129e4  mov     [rbx+19h], r14b
0x1800129e8  mov     [rbx+1Ch], esi
0x1800129eb  mov     rax, [rsp+78h+arg_20]
0x1800129f3  mov     [rbx+20h], rax
0x1800129f7  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x1800129fe  mov     [rbx], rax
0x180012a01  mov     [rdi], r12
0x180012a04  xor     eax, eax
0x180012a06  jmp     short loc_180012A0F
0x180012a08  mov     eax, [rsp+78h+arg_8]
0x180012a0f  mov     rbx, [rsp+78h+arg_10]
0x180012a17  add     rsp, 50h
0x180012a1b  pop     r15
0x180012a1d  pop     r14
0x180012a1f  pop     r12
0x180012a21  pop     rdi
0x180012a22  pop     rsi
0x180012a23  retn
0x180012a24  lea     rcx, [rsp+78h+var_40]
0x180012a29  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012a2e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180012a31  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180012a36  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180012a3b  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180012a42  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180012a47  call    _CxxThrowException_0
```
