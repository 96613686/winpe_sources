# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::IWindowsUpdateManagerScanOptionsFactory>::CreateInstance(bool,void * *)

- ea: `0x180014250`
- end: `0x18001431c`
- name: `?CreateInstance@?$produce@UWindowsUpdateManagerScanOptions@factory_implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManagerScanOptionsFactory@3456@@impl@winrt@@UEAAH_NPEAPEAX@Z`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180014250`
- `0x180015ac0`
- `0x18001db60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::IWindowsUpdateManagerScanOptionsFactory>::CreateInstance(
        __int64 a1,
        char a2,
        unsigned __int64 *a3)
{
  _QWORD *v5; // rbx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v9[48]; // [rsp+38h] [rbp-30h] BYREF
  int v10; // [rsp+78h] [rbp+10h] BYREF

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
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v9);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v7);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    *((_BYTE *)v5 + 24) = a2;
    *v5 = &winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions::`vftable';
    *a3 = (unsigned __int64)(v5 + 2) & -(__int64)(v5 != 0);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v10);
  }
  return result;
}

```

## disassembly

```asm
0x180014250  mov     [rsp+arg_10], rbx
0x180014255  mov     [rsp+arg_0], rcx
0x18001425a  push    rsi
0x18001425b  push    rdi
0x18001425c  push    r14
0x18001425e  sub     rsp, 50h
0x180014262  mov     rdi, r8
0x180014265  mov     sil, dl
0x180014268  and     qword ptr [r8], 0
0x18001426c  mov     ecx, 20h ; ' '; Size
0x180014271  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014276  mov     rbx, rax
0x180014279  mov     [rsp+68h+arg_0], rax
0x18001427e  lea     r14, [rax+10h]
0x180014282  lea     rax, ??_7?$produce@UWindowsUpdateManagerScanOptions@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManagerScanOptions@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::IWindowsUpdateManagerScanOptions>::`vftable'
0x180014289  mov     [r14], rax
0x18001428c  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180014293  mov     qword ptr [rbx+8], 1
0x18001429b  lea     rax, ??_7WindowsUpdateManagerScanOptions@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions::`vftable'
0x1800142a2  mov     [rbx], rax
0x1800142a5  and     word ptr [rbx+18h], 0
0x1800142aa  mov     byte ptr [rbx+1Ah], 1
0x1800142ae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800142b5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800142ba  test    al, al
0x1800142bc  jz      short loc_1800142F2
0x1800142be  mov     [rbx+18h], sil
0x1800142c2  lea     rax, ??_7WindowsUpdateManagerScanOptions@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions::`vftable'
0x1800142c9  mov     [rbx], rax
0x1800142cc  neg     rbx
0x1800142cf  sbb     rax, rax
0x1800142d2  and     rax, r14
0x1800142d5  mov     [rdi], rax
0x1800142d8  xor     eax, eax
0x1800142da  jmp     short loc_1800142E0
0x1800142dc  mov     eax, [rsp+68h+arg_8]
0x1800142e0  mov     rbx, [rsp+68h+arg_10]
0x1800142e8  add     rsp, 50h
0x1800142ec  pop     r14
0x1800142ee  pop     rdi
0x1800142ef  pop     rsi
0x1800142f0  retn
0x1800142f2  lea     rcx, [rsp+68h+var_30]
0x1800142f7  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800142fc  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800142ff  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180014304  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180014309  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180014310  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180014315  call    _CxxThrowException_0
```
