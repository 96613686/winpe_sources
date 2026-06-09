# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance3(bool,bool,uint,unsigned __int64,void * *)

- ea: `0x180013530`
- end: `0x18001362f`
- name: `?CreateInstance3@?$produce@UWindowsSoftwareUpdateResult@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResultFactory@3456@@impl@winrt@@UEAAH_N0I_KPEAPEAX@Z`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180013530`
- `0x180015ac0`
- `0x18001db60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance3(
        __int64 a1,
        char a2,
        char a3,
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
  int v15; // [rsp+88h] [rbp+10h] BYREF

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
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v14);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v12);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v10 + 24) = a2;
    *((_BYTE *)v10 + 25) = a3;
    *((_DWORD *)v10 + 7) = a4;
    v10[4] = a5;
    *v10 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
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
0x180013530  mov     [rsp+arg_10], rbx
0x180013535  mov     [rsp+arg_0], rcx
0x18001353a  push    rsi
0x18001353b  push    rdi
0x18001353c  push    r12
0x18001353e  push    r14
0x180013540  push    r15
0x180013542  sub     rsp, 50h
0x180013546  mov     esi, r9d
0x180013549  mov     r14b, r8b
0x18001354c  mov     r15b, dl
0x18001354f  mov     rdi, [rsp+78h+arg_28]
0x180013557  and     qword ptr [rdi], 0
0x18001355b  mov     ecx, 28h ; '('; Size
0x180013560  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013565  mov     rbx, rax
0x180013568  mov     [rsp+78h+arg_0], rax
0x180013570  lea     r12, [rax+10h]
0x180013574  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable'
0x18001357b  mov     [r12], rax
0x18001357f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013586  mov     qword ptr [rbx+8], 1
0x18001358e  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x180013595  mov     [rbx], rax
0x180013598  mov     word ptr [rbx+18h], 1
0x18001359e  and     dword ptr [rbx+1Ch], 0
0x1800135a2  and     qword ptr [rbx+20h], 0
0x1800135a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800135ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800135b3  test    al, al
0x1800135b5  jz      short loc_180013605
0x1800135b7  mov     [rbx+18h], r15b
0x1800135bb  mov     [rbx+19h], r14b
0x1800135bf  mov     [rbx+1Ch], esi
0x1800135c2  mov     rax, [rsp+78h+arg_20]
0x1800135ca  mov     [rbx+20h], rax
0x1800135ce  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x1800135d5  mov     [rbx], rax
0x1800135d8  neg     rbx
0x1800135db  sbb     rax, rax
0x1800135de  and     rax, r12
0x1800135e1  mov     [rdi], rax
0x1800135e4  xor     eax, eax
0x1800135e6  jmp     short loc_1800135EF
0x1800135e8  mov     eax, [rsp+78h+arg_8]
0x1800135ef  mov     rbx, [rsp+78h+arg_10]
0x1800135f7  add     rsp, 50h
0x1800135fb  pop     r15
0x1800135fd  pop     r14
0x1800135ff  pop     r12
0x180013601  pop     rdi
0x180013602  pop     rsi
0x180013603  retn
0x180013605  lea     rcx, [rsp+78h+var_40]
0x18001360a  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001360f  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180013612  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180013617  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001361c  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180013623  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180013628  call    _CxxThrowException_0
```
