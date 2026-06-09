# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance(bool,uint,void * *)

- ea: `0x180013e40`
- end: `0x180013f23`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateResult@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResultFactory@3456@@impl@winrt@@UEAAH_NIPEAPEAX@Z`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180013e40`
- `0x180015ac0`
- `0x18001db60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance(
        __int64 a1,
        char a2,
        int a3,
        unsigned __int64 *a4)
{
  _QWORD *v7; // rbx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v9; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v11[24]; // [rsp+38h] [rbp-30h] BYREF
  int v12; // [rsp+78h] [rbp+10h] BYREF

  *a4 = 0;
  try
  {
    v7 = operator new(0x28u);
    v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v7[1] = 1;
    *v7 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
    *((_WORD *)v7 + 12) = 1;
    *((_DWORD *)v7 + 7) = 0;
    v7[4] = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v11);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v9);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v7 + 24) = a2;
    *((_DWORD *)v7 + 7) = a3;
    *v7 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
    *a4 = (unsigned __int64)(v7 + 2) & -(__int64)(v7 != 0);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v12);
  }
  return result;
}

```

## disassembly

```asm
0x180013e40  mov     [rsp+arg_10], rbx
0x180013e45  mov     [rsp+arg_18], rsi
0x180013e4a  mov     [rsp+arg_0], rcx
0x180013e4f  push    rdi
0x180013e50  push    r14
0x180013e52  push    r15
0x180013e54  sub     rsp, 50h
0x180013e58  mov     rdi, r9
0x180013e5b  mov     esi, r8d
0x180013e5e  mov     r14b, dl
0x180013e61  and     qword ptr [r9], 0
0x180013e65  mov     ecx, 28h ; '('; Size
0x180013e6a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013e6f  mov     rbx, rax
0x180013e72  mov     [rsp+68h+arg_0], rax
0x180013e77  lea     r15, [rax+10h]
0x180013e7b  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable'
0x180013e82  mov     [r15], rax
0x180013e85  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013e8c  mov     qword ptr [rbx+8], 1
0x180013e94  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x180013e9b  mov     [rbx], rax
0x180013e9e  mov     word ptr [rbx+18h], 1
0x180013ea4  and     dword ptr [rbx+1Ch], 0
0x180013ea8  and     qword ptr [rbx+20h], 0
0x180013ead  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180013eb4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180013eb9  test    al, al
0x180013ebb  jz      short loc_180013EF9
0x180013ebd  mov     [rbx+18h], r14b
0x180013ec1  mov     [rbx+1Ch], esi
0x180013ec4  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x180013ecb  mov     [rbx], rax
0x180013ece  neg     rbx
0x180013ed1  sbb     rax, rax
0x180013ed4  and     rax, r15
0x180013ed7  mov     [rdi], rax
0x180013eda  xor     eax, eax
0x180013edc  jmp     short loc_180013EE2
0x180013ede  mov     eax, [rsp+68h+arg_8]
0x180013ee2  lea     r11, [rsp+68h+var_18]
0x180013ee7  mov     rbx, [r11+30h]
0x180013eeb  mov     rsi, [r11+38h]
0x180013eef  mov     rsp, r11
0x180013ef2  pop     r15
0x180013ef4  pop     r14
0x180013ef6  pop     rdi
0x180013ef7  retn
0x180013ef9  lea     rcx, [rsp+68h+var_30]
0x180013efe  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180013f03  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180013f06  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180013f0b  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180013f10  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180013f17  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180013f1c  call    _CxxThrowException_0
```
