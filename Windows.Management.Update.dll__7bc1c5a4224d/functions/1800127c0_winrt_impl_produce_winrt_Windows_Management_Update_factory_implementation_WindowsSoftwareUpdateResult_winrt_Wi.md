# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance2(bool,uint,unsigned __int64,void * *)

- ea: `0x1800127c0`
- end: `0x1800128b3`
- name: `?CreateInstance2@?$produce@UWindowsSoftwareUpdateResult@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResultFactory@3456@@impl@winrt@@UEAAH_NI_KPEAPEAX@Z`
- size: `243`
- prototype: `__int64 __fastcall(__int64, char, int, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800114a8`
- `0x1800127c0`
- `0x180014eb4`
- `0x18001c8a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResultFactory>::CreateInstance2(
        __int64 a1,
        char a2,
        int a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD *v8; // rdi
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v12; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v14[64]; // [rsp+38h] [rbp-40h] BYREF
  int v15; // [rsp+88h] [rbp+10h] BYREF

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
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v14, v10);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v12);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v9 + 24) = a2;
    *((_DWORD *)v9 + 7) = a3;
    v9[4] = a4;
    *v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable';
    *v8 = v9 + 2;
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
0x1800127c0  mov     [rsp+arg_10], rbx
0x1800127c5  mov     [rsp+arg_0], rcx
0x1800127ca  push    rsi
0x1800127cb  push    rdi
0x1800127cc  push    r12
0x1800127ce  push    r14
0x1800127d0  push    r15
0x1800127d2  sub     rsp, 50h
0x1800127d6  mov     rsi, r9
0x1800127d9  mov     r14d, r8d
0x1800127dc  mov     r15b, dl
0x1800127df  mov     rdi, [rsp+78h+arg_20]
0x1800127e7  mov     qword ptr [rdi], 0
0x1800127ee  mov     ecx, 28h ; '('; Size
0x1800127f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800127f8  mov     rbx, rax
0x1800127fb  mov     [rsp+78h+arg_0], rax
0x180012803  lea     r12, [rax+10h]
0x180012807  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateResult>::`vftable'
0x18001280e  mov     [r12], rax
0x180012812  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180012819  mov     qword ptr [rbx+8], 1
0x180012821  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x180012828  mov     [rbx], rax
0x18001282b  mov     word ptr [rbx+18h], 1
0x180012831  mov     dword ptr [rbx+1Ch], 0
0x180012838  mov     qword ptr [rbx+20h], 0
0x180012840  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180012847  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001284c  test    al, al
0x18001284e  jz      short loc_180012889
0x180012850  mov     [rbx+18h], r15b
0x180012854  mov     [rbx+1Ch], r14d
0x180012858  mov     [rbx+20h], rsi
0x18001285c  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult>::`vftable'
0x180012863  mov     [rbx], rax
0x180012866  mov     [rdi], r12
0x180012869  xor     eax, eax
0x18001286b  jmp     short loc_180012874
0x18001286d  mov     eax, [rsp+78h+arg_8]
0x180012874  mov     rbx, [rsp+78h+arg_10]
0x18001287c  add     rsp, 50h
0x180012880  pop     r15
0x180012882  pop     r14
0x180012884  pop     r12
0x180012886  pop     rdi
0x180012887  pop     rsi
0x180012888  retn
0x180012889  lea     rcx, [rsp+78h+var_40]
0x18001288e  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012893  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180012896  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001289b  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800128a0  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800128a7  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800128ac  call    _CxxThrowException_0
```
