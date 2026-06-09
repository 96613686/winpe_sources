# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResultFactory>::CreateInstance(int,int,uint,unsigned __int64,void * *)

- ea: `0x1800130e0`
- end: `0x1800131e0`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateProviderActionResult@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderActionResultFactory@3456@@impl@winrt@@UEAAHHHI_KPEAPEAX@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800114a8`
- `0x1800130e0`
- `0x180014eb4`
- `0x18001c8a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResultFactory>::CreateInstance(
        __int64 a1,
        int a2,
        int a3,
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
  int v16; // [rsp+98h] [rbp+20h] BYREF

  v9 = a6;
  *a6 = 0;
  try
  {
    v10 = operator new(0x30u);
    v10[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v10[1] = 1;
    *v10 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable';
    v10[3] = 0;
    *((_DWORD *)v10 + 8) = 0;
    v10[5] = 0;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v15, v11);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v13);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_DWORD *)v10 + 6) = a2;
    *((_DWORD *)v10 + 7) = a3;
    *((_DWORD *)v10 + 8) = a4;
    v10[5] = a5;
    *v10 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable';
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
0x1800130e0  mov     [rsp+arg_8], rbx
0x1800130e5  mov     [rsp+arg_0], rcx
0x1800130ea  push    rsi
0x1800130eb  push    rdi
0x1800130ec  push    r12
0x1800130ee  push    r14
0x1800130f0  push    r15
0x1800130f2  sub     rsp, 50h
0x1800130f6  mov     esi, r9d
0x1800130f9  mov     r14d, r8d
0x1800130fc  mov     r15d, edx
0x1800130ff  mov     rdi, [rsp+78h+arg_28]
0x180013107  mov     qword ptr [rdi], 0
0x18001310e  mov     ecx, 30h ; '0'; Size
0x180013113  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013118  mov     rbx, rax
0x18001311b  mov     [rsp+78h+arg_0], rax
0x180013123  lea     r12, [rax+10h]
0x180013127  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateProviderActionResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderActionResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResult>::`vftable'
0x18001312e  mov     [r12], rax
0x180013132  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013139  mov     qword ptr [rbx+8], 1
0x180013141  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateProviderActionResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable'
0x180013148  mov     [rbx], rax
0x18001314b  mov     qword ptr [rbx+18h], 0
0x180013153  mov     dword ptr [rbx+20h], 0
0x18001315a  mov     qword ptr [rbx+28h], 0
0x180013162  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180013169  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001316e  test    al, al
0x180013170  jz      short loc_1800131B6
0x180013172  mov     [rbx+18h], r15d
0x180013176  mov     [rbx+1Ch], r14d
0x18001317a  mov     [rbx+20h], esi
0x18001317d  mov     rax, [rsp+78h+arg_20]
0x180013185  mov     [rbx+28h], rax
0x180013189  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateProviderActionResult@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable'
0x180013190  mov     [rbx], rax
0x180013193  mov     [rdi], r12
0x180013196  xor     eax, eax
0x180013198  jmp     short loc_1800131A1
0x18001319a  mov     eax, [rsp+78h+arg_18]
0x1800131a1  mov     rbx, [rsp+78h+arg_8]
0x1800131a9  add     rsp, 50h
0x1800131ad  pop     r15
0x1800131af  pop     r14
0x1800131b1  pop     r12
0x1800131b3  pop     rdi
0x1800131b4  pop     rsi
0x1800131b5  retn
0x1800131b6  lea     rcx, [rsp+78h+var_40]
0x1800131bb  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800131c0  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800131c3  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800131c8  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800131cd  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800131d4  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800131d9  call    _CxxThrowException_0
```
