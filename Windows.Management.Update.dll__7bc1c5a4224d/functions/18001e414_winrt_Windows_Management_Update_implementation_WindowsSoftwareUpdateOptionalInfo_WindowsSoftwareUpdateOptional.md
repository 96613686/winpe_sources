# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::WindowsSoftwareUpdateOptionalInfo(winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo> const &,winrt::Windows::Foundation::IReference<int> const &,winrt::Windows::Foundation::IReference<int> const &)

- ea: `0x18001e414`
- end: `0x18001e69f`
- name: `??0WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@QEAA@AEBU?$IIterable@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@45@AEBU?$IReference@H@845@1@Z`
- size: `651`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012740`

## callees

- `0x18000340c`
- `0x1800114a8`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001c8a0`
- `0x18001d50c`
- `0x18001dd28`
- `0x18001e360`
- `0x18001e414`
- `0x18001e75c`
- `0x18001f178`
- `0x18001faf4`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::WindowsSoftwareUpdateOptionalInfo(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
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
  int v17; // eax
  __int64 v18; // rbx
  const struct winrt::impl::slim_source_location *v20; // rax
  _BYTE v21[8]; // [rsp+20h] [rbp-59h] BYREF
  __int64 v22; // [rsp+28h] [rbp-51h] BYREF
  unsigned int v23; // [rsp+30h] [rbp-49h]
  __int64 v24; // [rsp+38h] [rbp-41h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v26; // [rsp+58h] [rbp-21h] BYREF
  __int64 v27; // [rsp+60h] [rbp-19h] BYREF
  __int64 v28; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v29[96]; // [rsp+70h] [rbp-9h] BYREF

  v8 = 0;
  v23 = 0;
  a1[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable';
  v9 = a1 + 3;
  a1[3] = 0;
  a1[4] = 0;
  a1[5] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v20 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v29, v10);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v20);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>(
    &v27,
    (__int64 *)pExceptionObject);
  std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(pExceptionObject);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(
    a2,
    &v24);
  v28 = 0;
  v11 = v27;
  v12 = v24;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v24, &v28) )
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
  v22 = 0;
  *(_DWORD *)pExceptionObject = 0;
  *(_OWORD *)&pExceptionObject[8] = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 64LL))(v11, &v22);
  if ( v17 < 0 )
    winrt::throw_hresult((unsigned int)v17, pExceptionObject);
  v18 = v22;
  v26 = v22;
  if ( v9 == &v26 )
  {
    if ( v22 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
  }
  else
  {
    if ( *v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
    *v9 = v18;
  }
  winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(
    a1,
    a3,
    a4);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
  return a1;
}

```

## disassembly

```asm
0x18001e414  mov     [rsp-8+arg_0], rcx
0x18001e419  push    rbp
0x18001e41a  push    rbx
0x18001e41b  push    rsi
0x18001e41c  push    rdi
0x18001e41d  push    r12
0x18001e41f  push    r13
0x18001e421  push    r14
0x18001e423  push    r15
0x18001e425  lea     rbp, [rsp-1Fh]
0x18001e42a  sub     rsp, 98h
0x18001e431  mov     r12, r9
0x18001e434  mov     r13, r8
0x18001e437  mov     rbx, rdx
0x18001e43a  mov     rdi, rcx
0x18001e43d  xor     r15d, r15d
0x18001e440  mov     r14d, r15d
0x18001e443  mov     [rbp+57h+var_A0], r15d
0x18001e447  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::`vftable'
0x18001e44e  mov     [rcx+10h], rax
0x18001e452  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001e459  mov     qword ptr [rcx+8], 1
0x18001e461  lea     rax, ??_7WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable'
0x18001e468  mov     [rcx], rax
0x18001e46b  lea     rsi, [rcx+18h]
0x18001e46f  mov     [rsi], r15
0x18001e472  mov     [rcx+20h], r15
0x18001e476  mov     [rcx+28h], r15
0x18001e47a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001e481  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001e486  test    al, al
0x18001e488  jz      loc_18001E655
0x18001e48e  xorps   xmm0, xmm0
0x18001e491  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18001e496  mov     [rbp+57h+var_80], r15
0x18001e49a  lea     rdx, [rbp+57h+pExceptionObject]
0x18001e49e  lea     rcx, [rbp+57h+var_70]
0x18001e4a2  call    ??$single_threaded_vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>(std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo> &&)
0x18001e4a7  nop
0x18001e4a8  lea     rcx, [rbp+57h+pExceptionObject]
0x18001e4ac  call    ??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(void)
0x18001e4b1  lea     rdx, [rbp+57h+var_98]
0x18001e4b5  mov     rcx, rbx
0x18001e4b8  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UWindowsSoftwareUpdate@Update@Management@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(void)
0x18001e4bd  nop
0x18001e4be  mov     [rbp+57h+var_68], r15
0x18001e4c2  mov     r15, [rbp+57h+var_70]
0x18001e4c6  mov     rbx, [rbp+57h+var_98]
0x18001e4ca  lea     rdx, [rbp+57h+var_68]
0x18001e4ce  lea     rcx, [rbp+57h+var_98]
0x18001e4d2  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001e4d7  test    al, al
0x18001e4d9  jnz     loc_18001E5B0
0x18001e4df  mov     [rbp+57h+var_A8], 0
0x18001e4e7  or      r14d, 2
0x18001e4eb  mov     [rbp+57h+var_A0], r14d
0x18001e4ef  mov     dword ptr [rbp+57h+pExceptionObject], 0
0x18001e4f6  xorps   xmm0, xmm0
0x18001e4f9  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001e4fe  mov     rax, [rbx]
0x18001e501  lea     rdx, [rbp+57h+var_A8]
0x18001e505  mov     rcx, rbx
0x18001e508  mov     rax, [rax+30h]
0x18001e50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e511  test    eax, eax
0x18001e513  js      loc_18001E693
0x18001e519  and     r14d, 0FFFFFFFDh
0x18001e51d  mov     [rbp+57h+var_A0], r14d
0x18001e521  or      r14d, 1
0x18001e525  mov     dword ptr [rbp+57h+pExceptionObject], 0
0x18001e52c  xorps   xmm0, xmm0
0x18001e52f  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001e534  mov     rax, [r15]
0x18001e537  mov     rdx, [rbp+57h+var_A8]
0x18001e53b  mov     rcx, r15
0x18001e53e  mov     rax, [rax+68h]
0x18001e542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e547  test    eax, eax
0x18001e549  js      loc_18001E687
0x18001e54f  cmp     [rbp+57h+var_A8], 0
0x18001e554  jz      short loc_18001E55F
0x18001e556  lea     rcx, [rbp+57h+var_A8]
0x18001e55a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e55f  mov     [rbp+57h+var_B0], 0
0x18001e563  mov     dword ptr [rbp+57h+pExceptionObject], 0
0x18001e56a  xorps   xmm0, xmm0
0x18001e56d  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001e572  mov     rax, [rbx]
0x18001e575  lea     rdx, [rbp+57h+var_B0]
0x18001e579  mov     rcx, rbx
0x18001e57c  mov     rax, [rax+40h]
0x18001e580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e585  test    eax, eax
0x18001e587  js      loc_18001E67B
0x18001e58d  cmp     [rbp+57h+var_B0], 0
0x18001e591  jnz     loc_18001E4CA
0x18001e597  test    rbx, rbx
0x18001e59a  jz      short loc_18001E5A5
0x18001e59c  lea     rcx, [rbp+57h+var_98]
0x18001e5a0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e5a5  xor     ebx, ebx
0x18001e5a7  mov     [rbp+57h+var_98], rbx
0x18001e5ab  jmp     loc_18001E4CA
0x18001e5b0  xor     r14d, r14d
0x18001e5b3  test    rbx, rbx
0x18001e5b6  jz      short loc_18001E5C1
0x18001e5b8  lea     rcx, [rbp+57h+var_98]
0x18001e5bc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e5c1  mov     [rbp+57h+var_A8], r14
0x18001e5c5  mov     dword ptr [rbp+57h+pExceptionObject], r14d
0x18001e5c9  xorps   xmm0, xmm0
0x18001e5cc  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001e5d1  mov     rax, [r15]
0x18001e5d4  lea     rdx, [rbp+57h+var_A8]
0x18001e5d8  mov     rcx, r15
0x18001e5db  mov     rax, [rax+40h]
0x18001e5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5e4  test    eax, eax
0x18001e5e6  js      short loc_18001E649
0x18001e5e8  mov     rbx, [rbp+57h+var_A8]
0x18001e5ec  mov     [rbp+57h+var_78], rbx
0x18001e5f0  lea     rax, [rbp+57h+var_78]
0x18001e5f4  cmp     rsi, rax
0x18001e5f7  jz      short loc_18001E60B
0x18001e5f9  cmp     [rsi], r14
0x18001e5fc  jz      short loc_18001E606
0x18001e5fe  mov     rcx, rsi
0x18001e601  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e606  mov     [rsi], rbx
0x18001e609  jmp     short loc_18001E619
0x18001e60b  test    rbx, rbx
0x18001e60e  jz      short loc_18001E619
0x18001e610  lea     rcx, [rbp+57h+var_78]
0x18001e614  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e619  mov     r8, r12
0x18001e61c  mov     rdx, r13
0x18001e61f  mov     rcx, rdi
0x18001e622  call    ?InitializeComplianceParameters@WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@AEAAXAEBU?$IReference@H@Foundation@56@0@Z; winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(winrt::Windows::Foundation::IReference<int> const &,winrt::Windows::Foundation::IReference<int> const &)
0x18001e627  nop
0x18001e628  lea     rcx, [rbp+57h+var_70]
0x18001e62c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e631  nop
0x18001e632  mov     rax, rdi
0x18001e635  add     rsp, 98h
0x18001e63c  pop     r15
0x18001e63e  pop     r14
0x18001e640  pop     r13
0x18001e642  pop     r12
0x18001e644  pop     rdi
0x18001e645  pop     rsi
0x18001e646  pop     rbx
0x18001e647  pop     rbp
0x18001e648  retn
0x18001e649  lea     rdx, [rbp+57h+pExceptionObject]
0x18001e64d  mov     ecx, eax
0x18001e64f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001e655  lea     rcx, [rbp+57h+var_60]
0x18001e659  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001e65e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001e661  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001e665  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001e66a  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001e671  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001e675  call    _CxxThrowException_0
0x18001e67b  lea     rdx, [rbp+57h+pExceptionObject]
0x18001e67f  mov     ecx, eax
0x18001e681  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001e687  lea     rdx, [rbp+57h+pExceptionObject]
0x18001e68b  mov     ecx, eax
0x18001e68d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001e693  lea     rdx, [rbp+57h+pExceptionObject]
0x18001e697  mov     ecx, eax
0x18001e699  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
