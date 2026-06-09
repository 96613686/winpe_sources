# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderFactory>::CreateInstance(void *,void * *)

- ea: `0x180013ba0`
- end: `0x180013cb6`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateProvider@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderFactory@3456@@impl@winrt@@UEAAHPEAXPEAPEAX@Z`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180013ba0`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001db60`
- `0x180023118`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderFactory>::CreateInstance(
        __int64 a1,
        __int64 a2,
        unsigned __int64 *a3)
{
  _QWORD *v4; // rbx
  __int64 *v5; // rdi
  __int64 *SoftwareUpdateProvider; // rsi
  __int64 v7; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v9; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v11[64]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v12; // [rsp+80h] [rbp+8h] BYREF
  __int64 v13; // [rsp+88h] [rbp+10h] BYREF
  __int64 v14; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v15; // [rsp+98h] [rbp+20h]

  v13 = a2;
  v12 = a1;
  *a3 = 0;
  try
  {
    v4 = operator new(0x20u);
    v15 = v4;
    v4[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v4[1] = 1;
    *v4 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider::`vftable';
    v5 = v4 + 3;
    v4[3] = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v11);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v9);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    SoftwareUpdateProvider = winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProvider(
                               &v14,
                               (winrt::Windows::Management::Update::implementation *)&v13);
    if ( v5 != SoftwareUpdateProvider )
    {
      if ( *v5 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v4 + 3);
      v7 = *SoftwareUpdateProvider;
      *SoftwareUpdateProvider = 0;
      *v5 = v7;
    }
    if ( v14 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
    *v4 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider::`vftable';
    *a3 = (unsigned __int64)(v4 + 2) & -(__int64)(v4 != 0);
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
0x180013ba0  mov     [rsp+arg_8], rdx
0x180013ba5  mov     [rsp+arg_0], rcx
0x180013baa  push    rbx
0x180013bab  push    rsi
0x180013bac  push    rdi
0x180013bad  push    r14
0x180013baf  push    r15
0x180013bb1  sub     rsp, 50h
0x180013bb5  mov     r14, r8
0x180013bb8  and     qword ptr [r8], 0
0x180013bbc  mov     ecx, 20h ; ' '; Size
0x180013bc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013bc6  mov     rbx, rax
0x180013bc9  mov     [rsp+78h+arg_18], rax
0x180013bd1  lea     r15, [rax+10h]
0x180013bd5  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProvider@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider>::`vftable'
0x180013bdc  mov     [r15], rax
0x180013bdf  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013be6  mov     qword ptr [rbx+8], 1
0x180013bee  lea     rax, ??_7WindowsSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider::`vftable'
0x180013bf5  mov     [rbx], rax
0x180013bf8  lea     rdi, [rbx+18h]
0x180013bfc  and     qword ptr [rdi], 0
0x180013c00  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180013c07  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180013c0c  test    al, al
0x180013c0e  jz      short loc_180013C8C
0x180013c10  lea     rdx, [rsp+78h+arg_8]
0x180013c18  lea     rcx, [rsp+78h+arg_10]
0x180013c20  call    ?GetSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdateProvider@2345@AEBUhstring@5@@Z; winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProvider(winrt::hstring const &)
0x180013c25  mov     rsi, rax
0x180013c28  cmp     rdi, rax
0x180013c2b  jz      short loc_180013C45
0x180013c2d  cmp     qword ptr [rdi], 0
0x180013c31  jz      short loc_180013C3B
0x180013c33  mov     rcx, rdi
0x180013c36  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013c3b  mov     rcx, [rsi]
0x180013c3e  and     qword ptr [rsi], 0
0x180013c42  mov     [rdi], rcx
0x180013c45  cmp     [rsp+78h+arg_10], 0
0x180013c4e  jz      short loc_180013C5E
0x180013c50  lea     rcx, [rsp+78h+arg_10]
0x180013c58  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013c5d  nop
0x180013c5e  lea     rax, ??_7WindowsSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider::`vftable'
0x180013c65  mov     [rbx], rax
0x180013c68  neg     rbx
0x180013c6b  sbb     rax, rax
0x180013c6e  and     rax, r15
0x180013c71  mov     [r14], rax
0x180013c74  xor     eax, eax
0x180013c76  jmp     short loc_180013C7F
0x180013c78  mov     eax, dword ptr [rsp+78h+arg_0]
0x180013c7f  add     rsp, 50h
0x180013c83  pop     r15
0x180013c85  pop     r14
0x180013c87  pop     rdi
0x180013c88  pop     rsi
0x180013c89  pop     rbx
0x180013c8a  retn
0x180013c8c  lea     rcx, [rsp+78h+var_40]
0x180013c91  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180013c96  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180013c99  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180013c9e  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180013ca3  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180013caa  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180013caf  call    _CxxThrowException_0
```
