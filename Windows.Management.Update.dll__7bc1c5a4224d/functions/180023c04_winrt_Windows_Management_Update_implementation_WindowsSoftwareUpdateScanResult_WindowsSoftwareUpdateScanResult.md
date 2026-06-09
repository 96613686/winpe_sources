# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::WindowsSoftwareUpdateScanResult(bool,uint,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate> const &)

- ea: `0x180023c04`
- end: `0x180023e4c`
- name: `??0WindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@QEAA@_NIAEBU?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@45@@Z`
- size: `584`
- prototype: `__int64 __fastcall(__int64, char, int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013350`

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
- `0x180023c04`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::WindowsSoftwareUpdateScanResult(
        __int64 a1,
        char a2,
        int a3,
        __int64 a4)
{
  unsigned int v8; // r14d
  __int64 *v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // r15
  __int64 v12; // rbx
  int v13; // r14d
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 *v17; // rbx
  __int64 v18; // rcx
  const struct winrt::impl::slim_source_location *v20; // rax
  _BYTE v21[8]; // [rsp+20h] [rbp-49h] BYREF
  __int64 v22; // [rsp+28h] [rbp-41h] BYREF
  unsigned int v23; // [rsp+30h] [rbp-39h]
  __int64 v24; // [rsp+38h] [rbp-31h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v26; // [rsp+58h] [rbp-11h] BYREF
  __int64 v27; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v28[88]; // [rsp+68h] [rbp-1h] BYREF

  v8 = 0;
  v23 = 0;
  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateScanResult>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::`vftable';
  v9 = (__int64 *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v20 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v28, v10);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v20);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  *(_BYTE *)(a1 + 24) = a2;
  *(_DWORD *)(a1 + 28) = a3;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>(
    &v26,
    (__int64 *)pExceptionObject);
  std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(pExceptionObject);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(
    a4,
    &v24);
  v27 = 0;
  v11 = v26;
  v12 = v24;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v24, &v27) )
  {
    v22 = 0;
    v13 = v8 | 2;
    v23 = v13;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 48LL))(v12, &v22);
    if ( v14 < 0 )
      winrt::throw_hresult((unsigned int)v14, pExceptionObject);
    v23 = v13 & 0xFFFFFFFD;
    v8 = v13 & 0xFFFFFFFC | 1;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 104LL))(v11, v22);
    if ( v15 < 0 )
      winrt::throw_hresult((unsigned int)v15, pExceptionObject);
    if ( v22 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
    v21[0] = 0;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v12 + 64LL))(v12, v21);
    if ( v16 < 0 )
      winrt::throw_hresult((unsigned int)v16, pExceptionObject);
    if ( !v21[0] )
    {
      if ( v12 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
      v12 = 0;
      v24 = 0;
    }
  }
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
  v17 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                     &v26,
                     &v22);
  if ( v9 != v17 )
  {
    if ( *v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
    v18 = *v17;
    *v17 = 0;
    *v9 = v18;
  }
  if ( v22 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
  if ( v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
  return a1;
}

```

## disassembly

```asm
0x180023c04  mov     [rsp-8+arg_0], rcx
0x180023c09  push    rbp
0x180023c0a  push    rbx
0x180023c0b  push    rsi
0x180023c0c  push    rdi
0x180023c0d  push    r12
0x180023c0f  push    r13
0x180023c11  push    r14
0x180023c13  push    r15
0x180023c15  lea     rbp, [rsp-1Fh]
0x180023c1a  sub     rsp, 88h
0x180023c21  mov     rbx, r9
0x180023c24  mov     r15d, r8d
0x180023c27  mov     r12b, dl
0x180023c2a  mov     rdi, rcx
0x180023c2d  xor     r13d, r13d
0x180023c30  mov     r14d, r13d
0x180023c33  mov     [rbp+57h+var_90], r13d
0x180023c37  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateScanResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateScanResult>::`vftable'
0x180023c3e  mov     [rcx+10h], rax
0x180023c42  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180023c49  mov     qword ptr [rcx+8], 1
0x180023c51  lea     rax, ??_7WindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::`vftable'
0x180023c58  mov     [rcx], rax
0x180023c5b  lea     rsi, [rcx+28h]
0x180023c5f  mov     [rsi], r13
0x180023c62  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180023c69  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180023c6e  test    al, al
0x180023c70  jz      loc_180023E0E
0x180023c76  mov     [rdi+18h], r12b
0x180023c7a  mov     [rdi+1Ch], r15d
0x180023c7e  xorps   xmm0, xmm0
0x180023c81  movdqu  [rbp+57h+pExceptionObject], xmm0
0x180023c86  mov     [rbp+57h+var_70], r13
0x180023c8a  lea     rdx, [rbp+57h+pExceptionObject]
0x180023c8e  lea     rcx, [rbp+57h+var_68]
0x180023c92  call    ??$single_threaded_vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>(std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate> &&)
0x180023c97  nop
0x180023c98  lea     rcx, [rbp+57h+pExceptionObject]
0x180023c9c  call    ??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(void)
0x180023ca1  lea     rdx, [rbp+57h+var_88]
0x180023ca5  mov     rcx, rbx
0x180023ca8  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UWindowsSoftwareUpdate@Update@Management@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(void)
0x180023cad  nop
0x180023cae  mov     [rbp+57h+var_60], r13
0x180023cb2  mov     r15, [rbp+57h+var_68]
0x180023cb6  mov     rbx, [rbp+57h+var_88]
0x180023cba  lea     rdx, [rbp+57h+var_60]
0x180023cbe  lea     rcx, [rbp+57h+var_88]
0x180023cc2  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180023cc7  test    al, al
0x180023cc9  jnz     loc_180023D93
0x180023ccf  mov     [rbp+57h+var_98], r13
0x180023cd3  or      r14d, 2
0x180023cd7  mov     [rbp+57h+var_90], r14d
0x180023cdb  mov     dword ptr [rbp+57h+pExceptionObject], r13d
0x180023cdf  xorps   xmm0, xmm0
0x180023ce2  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x180023ce7  mov     rax, [rbx]
0x180023cea  lea     rdx, [rbp+57h+var_98]
0x180023cee  mov     rcx, rbx
0x180023cf1  mov     rax, [rax+30h]
0x180023cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cfa  test    eax, eax
0x180023cfc  js      loc_180023E02
0x180023d02  and     r14d, 0FFFFFFFDh
0x180023d06  mov     [rbp+57h+var_90], r14d
0x180023d0a  or      r14d, 1
0x180023d0e  mov     dword ptr [rbp+57h+pExceptionObject], r13d
0x180023d12  xorps   xmm0, xmm0
0x180023d15  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x180023d1a  mov     rax, [r15]
0x180023d1d  mov     rdx, [rbp+57h+var_98]
0x180023d21  mov     rcx, r15
0x180023d24  mov     rax, [rax+68h]
0x180023d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d2d  test    eax, eax
0x180023d2f  js      loc_180023E40
0x180023d35  cmp     [rbp+57h+var_98], r13
0x180023d39  jz      short loc_180023D44
0x180023d3b  lea     rcx, [rbp+57h+var_98]
0x180023d3f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023d44  mov     [rbp+57h+var_A0], r13b
0x180023d48  mov     dword ptr [rbp+57h+pExceptionObject], r13d
0x180023d4c  xorps   xmm0, xmm0
0x180023d4f  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x180023d54  mov     rax, [rbx]
0x180023d57  lea     rdx, [rbp+57h+var_A0]
0x180023d5b  mov     rcx, rbx
0x180023d5e  mov     rax, [rax+40h]
0x180023d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d67  test    eax, eax
0x180023d69  js      loc_180023E34
0x180023d6f  cmp     [rbp+57h+var_A0], r13b
0x180023d73  jnz     loc_180023CBA
0x180023d79  test    rbx, rbx
0x180023d7c  jz      short loc_180023D87
0x180023d7e  lea     rcx, [rbp+57h+var_88]
0x180023d82  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023d87  mov     rbx, r13
0x180023d8a  mov     [rbp+57h+var_88], rbx
0x180023d8e  jmp     loc_180023CBA
0x180023d93  test    rbx, rbx
0x180023d96  jz      short loc_180023DA1
0x180023d98  lea     rcx, [rbp+57h+var_88]
0x180023d9c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023da1  lea     rdx, [rbp+57h+var_98]
0x180023da5  lea     rcx, [rbp+57h+var_68]
0x180023da9  call    ?Description@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo@UIWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(void)
0x180023dae  mov     rbx, rax
0x180023db1  cmp     rsi, rax
0x180023db4  jz      short loc_180023DCC
0x180023db6  cmp     [rsi], r13
0x180023db9  jz      short loc_180023DC3
0x180023dbb  mov     rcx, rsi
0x180023dbe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023dc3  mov     rcx, [rbx]
0x180023dc6  mov     [rbx], r13
0x180023dc9  mov     [rsi], rcx
0x180023dcc  cmp     [rbp+57h+var_98], r13
0x180023dd0  jz      short loc_180023DDC
0x180023dd2  lea     rcx, [rbp+57h+var_98]
0x180023dd6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023ddb  nop
0x180023ddc  test    r15, r15
0x180023ddf  jz      short loc_180023DEB
0x180023de1  lea     rcx, [rbp+57h+var_68]
0x180023de5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023dea  nop
0x180023deb  mov     rax, rdi
0x180023dee  add     rsp, 88h
0x180023df5  pop     r15
0x180023df7  pop     r14
0x180023df9  pop     r13
0x180023dfb  pop     r12
0x180023dfd  pop     rdi
0x180023dfe  pop     rsi
0x180023dff  pop     rbx
0x180023e00  pop     rbp
0x180023e01  retn
0x180023e02  lea     rdx, [rbp+57h+pExceptionObject]
0x180023e06  mov     ecx, eax
0x180023e08  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023e0e  lea     rcx, [rbp+57h+var_58]
0x180023e12  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180023e17  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180023e1a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180023e1e  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180023e23  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180023e2a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180023e2e  call    _CxxThrowException_0
0x180023e34  lea     rdx, [rbp+57h+pExceptionObject]
0x180023e38  mov     ecx, eax
0x180023e3a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023e40  lea     rdx, [rbp+57h+pExceptionObject]
0x180023e44  mov     ecx, eax
0x180023e46  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
