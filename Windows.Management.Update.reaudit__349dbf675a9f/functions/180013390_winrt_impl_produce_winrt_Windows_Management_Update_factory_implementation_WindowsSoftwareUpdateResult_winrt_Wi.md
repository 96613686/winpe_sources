# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance2(bool,uint,unsigned __int64,void * *)

- ea: `0x180013390`
- end: `0x180013484`
- name: `?CreateInstance2@?$produce@UWindowsSoftwareUpdateResult@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResultFactory@3456@@impl@winrt@@UEAAH_NI_KPEAPEAX@Z`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180013390`
- `0x180015ac0`
- `0x18001db60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance2(
        __int64 a1,
        char a2,
        int a3,
        __int64 a4,
        unsigned __int64 *a5)
{
  unsigned __int64 *v8; // rdi
  _QWORD *v9; // rbx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v11; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  char v13[64]; // [rsp+38h] [rbp-40h] BYREF
  int v14; // [rsp+88h] [rbp+10h] BYREF

  v8 = a5;
  *a5 = 0;
  try
  {
    v9 = operator new(0x28u);
    v9[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v9[1] = 1;
    *v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
    *((_WORD *)v9 + 12) = 1;
    *((_DWORD *)v9 + 7) = 0;
    v9[4] = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v11 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v13);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v11);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v9 + 24) = a2;
    *((_DWORD *)v9 + 7) = a3;
    v9[4] = a4;
    *v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
    *v8 = (unsigned __int64)(v9 + 2) & -(__int64)(v9 != 0);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v14);
  }
  return result;
}

```

## disassembly

```asm
0x180013390  mov     [rsp+arg_10], rbx
0x180013395  mov     [rsp+arg_0], rcx
0x18001339a  push    rsi
0x18001339b  push    rdi
0x18001339c  push    r12
0x18001339e  push    r14
0x1800133a0  push    r15
0x1800133a2  sub     rsp, 50h
0x1800133a6  mov     rsi, r9
0x1800133a9  mov     r14d, r8d
0x1800133ac  mov     r15b, dl
0x1800133af  mov     rdi, [rsp+78h+arg_20]
0x1800133b7  and     qword ptr [rdi], 0
0x1800133bb  mov     ecx, 28h ; '('; Size
0x1800133c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800133c5  mov     rbx, rax
0x1800133c8  mov     [rsp+78h+arg_0], rax
0x1800133d0  lea     r12, [rax+10h]
0x1800133d4  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable'
0x1800133db  mov     [r12], rax
0x1800133df  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800133e6  mov     qword ptr [rbx+8], 1
0x1800133ee  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x1800133f5  mov     [rbx], rax
0x1800133f8  mov     word ptr [rbx+18h], 1
0x1800133fe  and     dword ptr [rbx+1Ch], 0
0x180013402  and     qword ptr [rbx+20h], 0
0x180013407  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001340e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180013413  test    al, al
0x180013415  jz      short loc_18001345A
0x180013417  mov     [rbx+18h], r15b
0x18001341b  mov     [rbx+1Ch], r14d
0x18001341f  mov     [rbx+20h], rsi
0x180013423  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x18001342a  mov     [rbx], rax
0x18001342d  neg     rbx
0x180013430  sbb     rax, rax
0x180013433  and     rax, r12
0x180013436  mov     [rdi], rax
0x180013439  xor     eax, eax
0x18001343b  jmp     short loc_180013444
0x18001343d  mov     eax, [rsp+78h+arg_8]
0x180013444  mov     rbx, [rsp+78h+arg_10]
0x18001344c  add     rsp, 50h
0x180013450  pop     r15
0x180013452  pop     r14
0x180013454  pop     r12
0x180013456  pop     rdi
0x180013457  pop     rsi
0x180013458  retn
0x18001345a  lea     rcx, [rsp+78h+var_40]
0x18001345f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180013464  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180013467  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001346c  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180013471  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180013478  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001347d  call    _CxxThrowException_0
```
