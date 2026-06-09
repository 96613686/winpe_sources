# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::IWindowsUpdateManagerScanOptionsFactory>::CreateInstance(bool,void * *)

- ea: `0x180013660`
- end: `0x180013726`
- name: `?CreateInstance@?$produce@UWindowsUpdateManagerScanOptions@factory_implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManagerScanOptionsFactory@3456@@impl@winrt@@UEAAH_NPEAPEAX@Z`
- size: `198`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800114a8`
- `0x180013660`
- `0x180014eb4`
- `0x18001c8a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::IWindowsUpdateManagerScanOptionsFactory>::CreateInstance(
        __int64 a1,
        char a2,
        _QWORD *a3)
{
  _QWORD *v5; // rbx
  __int64 v6; // rdx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v8; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v10[48]; // [rsp+38h] [rbp-30h] BYREF
  int v11; // [rsp+78h] [rbp+10h] BYREF

  *a3 = 0;
  try
  {
    v5 = operator new(0x20u);
    v5[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::IWindowsUpdateManagerScanOptions>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v5[1] = 1;
    *v5 = &winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions::`vftable';
    *((_WORD *)v5 + 12) = 0;
    *((_BYTE *)v5 + 26) = 1;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v10, v6);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v8);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v5 + 24) = a2;
    *v5 = &winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions::`vftable';
    *a3 = v5 + 2;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x180013660  mov     [rsp+arg_10], rbx
0x180013665  mov     [rsp+arg_0], rcx
0x18001366a  push    rsi
0x18001366b  push    rdi
0x18001366c  push    r14
0x18001366e  sub     rsp, 50h
0x180013672  mov     rdi, r8
0x180013675  mov     sil, dl
0x180013678  mov     qword ptr [r8], 0
0x18001367f  mov     ecx, 20h ; ' '; Size
0x180013684  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013689  mov     rbx, rax
0x18001368c  mov     [rsp+68h+arg_0], rax
0x180013691  lea     r14, [rax+10h]
0x180013695  lea     rax, ??_7?$produce@UWindowsUpdateManagerScanOptions@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManagerScanOptions@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::IWindowsUpdateManagerScanOptions>::`vftable'
0x18001369c  mov     [r14], rax
0x18001369f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800136a6  mov     qword ptr [rbx+8], 1
0x1800136ae  lea     rax, ??_7WindowsUpdateManagerScanOptions@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions::`vftable'
0x1800136b5  mov     [rbx], rax
0x1800136b8  mov     word ptr [rbx+18h], 0
0x1800136be  mov     byte ptr [rbx+1Ah], 1
0x1800136c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800136c9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800136ce  test    al, al
0x1800136d0  jz      short loc_1800136FC
0x1800136d2  mov     [rbx+18h], sil
0x1800136d6  lea     rax, ??_7WindowsUpdateManagerScanOptions@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions::`vftable'
0x1800136dd  mov     [rbx], rax
0x1800136e0  mov     [rdi], r14
0x1800136e3  xor     eax, eax
0x1800136e5  jmp     short loc_1800136EB
0x1800136e7  mov     eax, [rsp+68h+arg_8]
0x1800136eb  mov     rbx, [rsp+68h+arg_10]
0x1800136f3  add     rsp, 50h
0x1800136f7  pop     r14
0x1800136f9  pop     rdi
0x1800136fa  pop     rsi
0x1800136fb  retn
0x1800136fc  lea     rcx, [rsp+68h+var_30]
0x180013701  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180013706  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180013709  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18001370e  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180013713  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001371a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001371f  call    _CxxThrowException_0
```
