# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfoFactory>::CreateInstance(bool,bool,bool,bool,void * *)

- ea: `0x180013850`
- end: `0x180013943`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateApprovalInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateApprovalInfoFactory@3456@@impl@winrt@@UEAAH_N000PEAPEAX@Z`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180013850`
- `0x180015ac0`
- `0x18001db60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfoFactory>::CreateInstance(
        __int64 a1,
        char a2,
        char a3,
        char a4,
        char a5,
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
    v10 = operator new(0x20u);
    v10[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfo>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v10[1] = 1;
    *v10 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo::`vftable';
    *((_DWORD *)v10 + 6) = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v14);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v12);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v10 + 24) = a2;
    *((_BYTE *)v10 + 25) = a3;
    *((_BYTE *)v10 + 26) = a4;
    *((_BYTE *)v10 + 27) = a5;
    *v10 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo::`vftable';
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
0x180013850  mov     [rsp+arg_10], rbx
0x180013855  mov     [rsp+arg_0], rcx
0x18001385a  push    rsi
0x18001385b  push    rdi
0x18001385c  push    r12
0x18001385e  push    r14
0x180013860  push    r15
0x180013862  sub     rsp, 50h
0x180013866  mov     sil, r9b
0x180013869  mov     r14b, r8b
0x18001386c  mov     r15b, dl
0x18001386f  mov     rdi, [rsp+78h+arg_28]
0x180013877  and     qword ptr [rdi], 0
0x18001387b  mov     ecx, 20h ; ' '; Size
0x180013880  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013885  mov     rbx, rax
0x180013888  mov     [rsp+78h+arg_0], rax
0x180013890  lea     r12, [rax+10h]
0x180013894  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateApprovalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateApprovalInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfo>::`vftable'
0x18001389b  mov     [r12], rax
0x18001389f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800138a6  mov     qword ptr [rbx+8], 1
0x1800138ae  lea     rax, ??_7WindowsSoftwareUpdateApprovalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo::`vftable'
0x1800138b5  mov     [rbx], rax
0x1800138b8  and     dword ptr [rbx+18h], 0
0x1800138bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800138c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800138c8  test    al, al
0x1800138ca  jz      short loc_180013919
0x1800138cc  mov     [rbx+18h], r15b
0x1800138d0  mov     [rbx+19h], r14b
0x1800138d4  mov     [rbx+1Ah], sil
0x1800138d8  mov     al, [rsp+78h+arg_20]
0x1800138df  mov     [rbx+1Bh], al
0x1800138e2  lea     rax, ??_7WindowsSoftwareUpdateApprovalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo::`vftable'
0x1800138e9  mov     [rbx], rax
0x1800138ec  neg     rbx
0x1800138ef  sbb     rax, rax
0x1800138f2  and     rax, r12
0x1800138f5  mov     [rdi], rax
0x1800138f8  xor     eax, eax
0x1800138fa  jmp     short loc_180013903
0x1800138fc  mov     eax, dword ptr [rsp+78h+arg_20]
0x180013903  mov     rbx, [rsp+78h+arg_10]
0x18001390b  add     rsp, 50h
0x18001390f  pop     r15
0x180013911  pop     r14
0x180013913  pop     r12
0x180013915  pop     rdi
0x180013916  pop     rsi
0x180013917  retn
0x180013919  lea     rcx, [rsp+78h+var_40]
0x18001391e  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180013923  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180013926  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001392b  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180013930  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180013937  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001393c  call    _CxxThrowException_0
```
