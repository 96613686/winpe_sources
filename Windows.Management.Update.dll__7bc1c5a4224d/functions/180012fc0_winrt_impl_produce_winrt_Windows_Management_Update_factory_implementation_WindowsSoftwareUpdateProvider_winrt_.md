# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderFactory>::CreateInstance(void *,void * *)

- ea: `0x180012fc0`
- end: `0x1800130d5`
- name: `?CreateInstance@?$produce@UWindowsSoftwareUpdateProvider@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderFactory@3456@@impl@winrt@@UEAAHPEAXPEAPEAX@Z`
- size: `277`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800114a8`
- `0x180012fc0`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001c8a0`
- `0x180021e90`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderFactory>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v4; // rdi
  __int64 *v5; // rbx
  __int64 v6; // rdx
  __int64 *SoftwareUpdateProvider; // rsi
  __int64 v8; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v10; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v12[64]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF
  __int64 v14; // [rsp+88h] [rbp+10h] BYREF
  _QWORD *v15; // [rsp+90h] [rbp+18h]

  v14 = a2;
  v13 = a1;
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
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v12, v6);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v10);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    SoftwareUpdateProvider = winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProvider(
                               &v13,
                               (winrt::Windows::Management::Update::implementation *)&v14);
    if ( v5 != SoftwareUpdateProvider )
    {
      if ( *v5 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v4 + 3);
      v8 = *SoftwareUpdateProvider;
      *SoftwareUpdateProvider = 0;
      *v5 = v8;
    }
    if ( v13 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
    *v4 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider::`vftable';
    *a3 = v4 + 2;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v13);
  }
  return result;
}

```

## disassembly

```asm
0x180012fc0  mov     [rsp+arg_8], rdx
0x180012fc5  mov     [rsp+arg_0], rcx
0x180012fca  push    rbx
0x180012fcb  push    rsi
0x180012fcc  push    rdi
0x180012fcd  push    r14
0x180012fcf  push    r15
0x180012fd1  sub     rsp, 50h
0x180012fd5  mov     r14, r8
0x180012fd8  mov     qword ptr [r8], 0
0x180012fdf  mov     ecx, 20h ; ' '; Size
0x180012fe4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012fe9  mov     rdi, rax
0x180012fec  mov     [rsp+78h+arg_10], rax
0x180012ff4  lea     r15, [rax+10h]
0x180012ff8  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProvider@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider>::`vftable'
0x180012fff  mov     [r15], rax
0x180013002  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013009  mov     qword ptr [rdi+8], 1
0x180013011  lea     rax, ??_7WindowsSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider::`vftable'
0x180013018  mov     [rdi], rax
0x18001301b  lea     rbx, [rdi+18h]
0x18001301f  mov     qword ptr [rbx], 0
0x180013026  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001302d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180013032  test    al, al
0x180013034  jz      short loc_1800130AB
0x180013036  lea     rdx, [rsp+78h+arg_8]
0x18001303e  lea     rcx, [rsp+78h+arg_0]
0x180013046  call    ?GetSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdateProvider@2345@AEBUhstring@5@@Z; winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProvider(winrt::hstring const &)
0x18001304b  mov     rsi, rax
0x18001304e  cmp     rbx, rax
0x180013051  jz      short loc_18001306E
0x180013053  cmp     qword ptr [rbx], 0
0x180013057  jz      short loc_180013061
0x180013059  mov     rcx, rbx
0x18001305c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013061  mov     rcx, [rsi]
0x180013064  mov     qword ptr [rsi], 0
0x18001306b  mov     [rbx], rcx
0x18001306e  cmp     [rsp+78h+arg_0], 0
0x180013077  jz      short loc_180013087
0x180013079  lea     rcx, [rsp+78h+arg_0]
0x180013081  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013086  nop
0x180013087  lea     rax, ??_7WindowsSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider::`vftable'
0x18001308e  mov     [rdi], rax
0x180013091  mov     [r14], r15
0x180013094  xor     eax, eax
0x180013096  jmp     short loc_18001309F
0x180013098  mov     eax, dword ptr [rsp+78h+arg_0]
0x18001309f  add     rsp, 50h
0x1800130a3  pop     r15
0x1800130a5  pop     r14
0x1800130a7  pop     rdi
0x1800130a8  pop     rsi
0x1800130a9  pop     rbx
0x1800130aa  retn
0x1800130ab  lea     rcx, [rsp+78h+var_40]
0x1800130b0  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800130b5  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800130b8  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800130bd  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800130c2  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800130c9  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800130ce  call    _CxxThrowException_0
```
