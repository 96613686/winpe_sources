# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::WindowsSoftwareUpdateScanResult(bool,uint,unsigned __int64,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate> const &)

- ea: `0x180023e54`
- end: `0x1800240a1`
- name: `??0WindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@QEAA@_NI_KAEBU?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@45@@Z`
- size: `589`
- prototype: `__int64 __fastcall(__int64, char, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800128c0`

## callees

- `0x18000340c`
- `0x1800114a8`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001b924`
- `0x18001c8a0`
- `0x18001d50c`
- `0x18001dd28`
- `0x18001e75c`
- `0x18001faf4`
- `0x180023b50`
- `0x180023e54`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::WindowsSoftwareUpdateScanResult(
        __int64 a1,
        char a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v9; // r14d
  __int64 *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // r15
  __int64 v13; // rbx
  int v14; // r14d
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 *v18; // rbx
  __int64 v19; // rcx
  const struct winrt::impl::slim_source_location *v21; // rax
  _BYTE v22[8]; // [rsp+20h] [rbp-51h] BYREF
  __int64 v23; // [rsp+28h] [rbp-49h] BYREF
  unsigned int v24; // [rsp+30h] [rbp-41h]
  __int64 v25; // [rsp+38h] [rbp-39h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-31h] BYREF
  __int64 v27; // [rsp+58h] [rbp-19h] BYREF
  __int64 v28; // [rsp+60h] [rbp-11h] BYREF
  _BYTE v29[88]; // [rsp+68h] [rbp-9h] BYREF

  v9 = 0;
  v24 = 0;
  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateScanResult>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::`vftable';
  v10 = (__int64 *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v21 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v29, v11);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v21);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  *(_BYTE *)(a1 + 24) = a2;
  *(_DWORD *)(a1 + 28) = a3;
  *(_QWORD *)(a1 + 32) = a4;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>(
    &v27,
    (__int64 *)pExceptionObject);
  std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(pExceptionObject);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(
    a5,
    &v25);
  v28 = 0;
  v12 = v27;
  v13 = v25;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v25, &v28) )
  {
    v23 = 0;
    v14 = v9 | 2;
    v24 = v14;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 48LL))(v13, &v23);
    if ( v15 < 0 )
      winrt::throw_hresult((unsigned int)v15, pExceptionObject);
    v24 = v14 & 0xFFFFFFFD;
    v9 = v14 & 0xFFFFFFFC | 1;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 104LL))(v12, v23);
    if ( v16 < 0 )
      winrt::throw_hresult((unsigned int)v16, pExceptionObject);
    if ( v23 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    v22[0] = 0;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v13 + 64LL))(v13, v22);
    if ( v17 < 0 )
      winrt::throw_hresult((unsigned int)v17, pExceptionObject);
    if ( !v22[0] )
    {
      if ( v13 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
      v13 = 0;
      v25 = 0;
    }
  }
  if ( v13 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
  v18 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                     &v27,
                     &v23);
  if ( v10 != v18 )
  {
    if ( *v10 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
    v19 = *v18;
    *v18 = 0;
    *v10 = v19;
  }
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
  return a1;
}

```

## disassembly

```asm
0x180023e54  mov     [rsp-8+arg_0], rcx
0x180023e59  push    rbp
0x180023e5a  push    rbx
0x180023e5b  push    rsi
0x180023e5c  push    rdi
0x180023e5d  push    r12
0x180023e5f  push    r13
0x180023e61  push    r14
0x180023e63  push    r15
0x180023e65  lea     rbp, [rsp-17h]
0x180023e6a  sub     rsp, 88h
0x180023e71  mov     rbx, r9
0x180023e74  mov     r15d, r8d
0x180023e77  mov     r12b, dl
0x180023e7a  mov     rdi, rcx
0x180023e7d  xor     r13d, r13d
0x180023e80  mov     r14d, r13d
0x180023e83  mov     [rbp+4Fh+var_90], r13d
0x180023e87  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateScanResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateScanResult>::`vftable'
0x180023e8e  mov     [rcx+10h], rax
0x180023e92  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180023e99  mov     qword ptr [rcx+8], 1
0x180023ea1  lea     rax, ??_7WindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::`vftable'
0x180023ea8  mov     [rcx], rax
0x180023eab  lea     rsi, [rcx+28h]
0x180023eaf  mov     [rsi], r13
0x180023eb2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180023eb9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180023ebe  test    al, al
0x180023ec0  jz      loc_180024063
0x180023ec6  mov     [rdi+18h], r12b
0x180023eca  mov     [rdi+1Ch], r15d
0x180023ece  mov     [rdi+20h], rbx
0x180023ed2  xorps   xmm0, xmm0
0x180023ed5  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x180023eda  mov     [rbp+4Fh+var_70], r13
0x180023ede  lea     rdx, [rbp+4Fh+pExceptionObject]
0x180023ee2  lea     rcx, [rbp+4Fh+var_68]
0x180023ee6  call    ??$single_threaded_vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>(std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate> &&)
0x180023eeb  nop
0x180023eec  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180023ef0  call    ??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(void)
0x180023ef5  lea     rdx, [rbp+4Fh+var_88]
0x180023ef9  mov     rcx, [rbp+4Fh+arg_20]
0x180023efd  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UWindowsSoftwareUpdate@Update@Management@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(void)
0x180023f02  nop
0x180023f03  mov     [rbp+4Fh+var_60], r13
0x180023f07  mov     r15, [rbp+4Fh+var_68]
0x180023f0b  mov     rbx, [rbp+4Fh+var_88]
0x180023f0f  lea     rdx, [rbp+4Fh+var_60]
0x180023f13  lea     rcx, [rbp+4Fh+var_88]
0x180023f17  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180023f1c  test    al, al
0x180023f1e  jnz     loc_180023FE8
0x180023f24  mov     [rbp+4Fh+var_98], r13
0x180023f28  or      r14d, 2
0x180023f2c  mov     [rbp+4Fh+var_90], r14d
0x180023f30  mov     dword ptr [rbp+4Fh+pExceptionObject], r13d
0x180023f34  xorps   xmm0, xmm0
0x180023f37  movdqu  [rbp+4Fh+pExceptionObject+8], xmm0
0x180023f3c  mov     rax, [rbx]
0x180023f3f  lea     rdx, [rbp+4Fh+var_98]
0x180023f43  mov     rcx, rbx
0x180023f46  mov     rax, [rax+30h]
0x180023f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f4f  test    eax, eax
0x180023f51  js      loc_180024057
0x180023f57  and     r14d, 0FFFFFFFDh
0x180023f5b  mov     [rbp+4Fh+var_90], r14d
0x180023f5f  or      r14d, 1
0x180023f63  mov     dword ptr [rbp+4Fh+pExceptionObject], r13d
0x180023f67  xorps   xmm0, xmm0
0x180023f6a  movdqu  [rbp+4Fh+pExceptionObject+8], xmm0
0x180023f6f  mov     rax, [r15]
0x180023f72  mov     rdx, [rbp+4Fh+var_98]
0x180023f76  mov     rcx, r15
0x180023f79  mov     rax, [rax+68h]
0x180023f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f82  test    eax, eax
0x180023f84  js      loc_180024095
0x180023f8a  cmp     [rbp+4Fh+var_98], r13
0x180023f8e  jz      short loc_180023F99
0x180023f90  lea     rcx, [rbp+4Fh+var_98]
0x180023f94  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023f99  mov     [rbp+4Fh+var_A0], r13b
0x180023f9d  mov     dword ptr [rbp+4Fh+pExceptionObject], r13d
0x180023fa1  xorps   xmm0, xmm0
0x180023fa4  movdqu  [rbp+4Fh+pExceptionObject+8], xmm0
0x180023fa9  mov     rax, [rbx]
0x180023fac  lea     rdx, [rbp+4Fh+var_A0]
0x180023fb0  mov     rcx, rbx
0x180023fb3  mov     rax, [rax+40h]
0x180023fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fbc  test    eax, eax
0x180023fbe  js      loc_180024089
0x180023fc4  cmp     [rbp+4Fh+var_A0], r13b
0x180023fc8  jnz     loc_180023F0F
0x180023fce  test    rbx, rbx
0x180023fd1  jz      short loc_180023FDC
0x180023fd3  lea     rcx, [rbp+4Fh+var_88]
0x180023fd7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023fdc  mov     rbx, r13
0x180023fdf  mov     [rbp+4Fh+var_88], rbx
0x180023fe3  jmp     loc_180023F0F
0x180023fe8  test    rbx, rbx
0x180023feb  jz      short loc_180023FF6
0x180023fed  lea     rcx, [rbp+4Fh+var_88]
0x180023ff1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023ff6  lea     rdx, [rbp+4Fh+var_98]
0x180023ffa  lea     rcx, [rbp+4Fh+var_68]
0x180023ffe  call    ?Description@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo@UIWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(void)
0x180024003  mov     rbx, rax
0x180024006  cmp     rsi, rax
0x180024009  jz      short loc_180024021
0x18002400b  cmp     [rsi], r13
0x18002400e  jz      short loc_180024018
0x180024010  mov     rcx, rsi
0x180024013  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024018  mov     rcx, [rbx]
0x18002401b  mov     [rbx], r13
0x18002401e  mov     [rsi], rcx
0x180024021  cmp     [rbp+4Fh+var_98], r13
0x180024025  jz      short loc_180024031
0x180024027  lea     rcx, [rbp+4Fh+var_98]
0x18002402b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024030  nop
0x180024031  test    r15, r15
0x180024034  jz      short loc_180024040
0x180024036  lea     rcx, [rbp+4Fh+var_68]
0x18002403a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002403f  nop
0x180024040  mov     rax, rdi
0x180024043  add     rsp, 88h
0x18002404a  pop     r15
0x18002404c  pop     r14
0x18002404e  pop     r13
0x180024050  pop     r12
0x180024052  pop     rdi
0x180024053  pop     rsi
0x180024054  pop     rbx
0x180024055  pop     rbp
0x180024056  retn
0x180024057  lea     rdx, [rbp+4Fh+pExceptionObject]
0x18002405b  mov     ecx, eax
0x18002405d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024063  lea     rcx, [rbp+4Fh+var_58]
0x180024067  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002406c  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18002406f  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180024073  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180024078  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18002407f  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180024083  call    _CxxThrowException_0
0x180024089  lea     rdx, [rbp+4Fh+pExceptionObject]
0x18002408d  mov     ecx, eax
0x18002408f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024095  lea     rdx, [rbp+4Fh+pExceptionObject]
0x180024099  mov     ecx, eax
0x18002409b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
