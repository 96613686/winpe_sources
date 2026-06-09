# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::WindowsSoftwareUpdateScanResult(bool,uint,unsigned __int64,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate> const &)

- ea: `0x1800250f0`
- end: `0x180025342`
- name: `??0WindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@QEAA@_NI_KAEBU?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@45@@Z`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013490`

## callees

- `0x1800035f0`
- `0x18001203c`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001cb80`
- `0x18001db60`
- `0x18001e7a4`
- `0x18001efbc`
- `0x18001fa3c`
- `0x180024df0`
- `0x1800250f0`
- `0x1800254a0`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::WindowsSoftwareUpdateScanResult(
        __int64 a1,
        char a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  __int64 *v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  unsigned int v12; // r15d
  int v13; // r15d
  signed int v14; // eax
  __int64 v15; // r8
  signed int v16; // eax
  __int64 v17; // r8
  signed int v18; // eax
  __int64 v19; // r8
  __int64 *v20; // rbx
  __int64 v21; // rcx
  const struct winrt::impl::slim_source_location *v23; // rax
  _BYTE v24[4]; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v25; // [rsp+24h] [rbp-5Ch]
  __int64 v26; // [rsp+28h] [rbp-58h] BYREF
  __int64 v27; // [rsp+30h] [rbp-50h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v29; // [rsp+50h] [rbp-30h] BYREF
  __int64 v30; // [rsp+58h] [rbp-28h] BYREF
  __int64 v31; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v32[24]; // [rsp+68h] [rbp-18h] BYREF

  v25 = 0;
  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateScanResult>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::`vftable';
  v9 = (__int64 *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v23 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v32);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v23);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  *(_BYTE *)(a1 + 24) = a2;
  *(_DWORD *)(a1 + 28) = a3;
  *(_QWORD *)(a1 + 32) = a4;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>(
    &v29,
    pExceptionObject);
  std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(pExceptionObject);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(
    a5,
    &v26);
  v31 = 0;
  v10 = v29;
  v11 = v26;
  v12 = v25;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v26, &v31) )
  {
    v27 = 0;
    v13 = v12 | 2;
    v25 = v13;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 48LL))(v11, &v27);
    if ( v14 < 0 )
      winrt::throw_hresult(v14, (unsigned int *)pExceptionObject, v15);
    v12 = v13 & 0xFFFFFFFC | 1;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 104LL))(v10, v27);
    if ( v16 < 0 )
      winrt::throw_hresult(v16, (unsigned int *)pExceptionObject, v17);
    if ( v27 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
    v24[0] = 0;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v11 + 64LL))(v11, v24);
    if ( v18 < 0 )
      winrt::throw_hresult(v18, (unsigned int *)pExceptionObject, v19);
    if ( !v24[0] )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
      v11 = 0;
      v26 = 0;
    }
  }
  if ( v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
  v20 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                     &v29,
                     &v30);
  if ( v9 != v20 )
  {
    if ( *v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
    v21 = *v20;
    *v20 = 0;
    *v9 = v21;
  }
  if ( v30 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v30);
  if ( v10 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
  return a1;
}

```

## disassembly

```asm
0x1800250f0  mov     [rsp-28h+arg_8], rbx
0x1800250f5  mov     [rsp-28h+arg_10], rsi
0x1800250fa  mov     [rsp-28h+arg_0], rcx
0x1800250ff  push    rbp
0x180025100  push    rdi
0x180025101  push    r12
0x180025103  push    r14
0x180025105  push    r15
0x180025107  mov     rbp, rsp
0x18002510a  sub     rsp, 80h
0x180025111  mov     rbx, r9
0x180025114  mov     edi, r8d
0x180025117  mov     r15b, dl
0x18002511a  mov     r14, rcx
0x18002511d  xor     r12d, r12d
0x180025120  mov     [rbp+var_5C], r12d
0x180025124  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateScanResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateScanResult>::`vftable'
0x18002512b  mov     [rcx+10h], rax
0x18002512f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180025136  mov     qword ptr [rcx+8], 1
0x18002513e  lea     rax, ??_7WindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::`vftable'
0x180025145  mov     [rcx], rax
0x180025148  lea     rsi, [rcx+28h]
0x18002514c  mov     [rsi], r12
0x18002514f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180025156  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18002515b  test    al, al
0x18002515d  jz      loc_180025304
0x180025163  mov     [r14+18h], r15b
0x180025167  mov     [r14+1Ch], edi
0x18002516b  mov     [r14+20h], rbx
0x18002516f  xorps   xmm0, xmm0
0x180025172  movdqu  [rbp+pExceptionObject], xmm0
0x180025177  mov     [rbp+var_38], r12
0x18002517b  lea     rdx, [rbp+pExceptionObject]
0x18002517f  lea     rcx, [rbp+var_30]
0x180025183  call    ??$single_threaded_vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>(std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate> &&)
0x180025188  nop
0x180025189  lea     rcx, [rbp+pExceptionObject]
0x18002518d  call    ??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(void)
0x180025192  lea     rdx, [rbp+var_58]
0x180025196  mov     rcx, [rbp+arg_20]
0x18002519a  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UWindowsSoftwareUpdate@Update@Management@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(void)
0x18002519f  nop
0x1800251a0  mov     [rbp+var_20], r12
0x1800251a4  mov     rdi, [rbp+var_30]
0x1800251a8  mov     rbx, [rbp+var_58]
0x1800251ac  mov     r15d, [rbp+var_5C]
0x1800251b0  lea     rdx, [rbp+var_20]
0x1800251b4  lea     rcx, [rbp+var_58]
0x1800251b8  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800251bd  test    al, al
0x1800251bf  jnz     loc_180025280
0x1800251c5  mov     [rbp+var_50], r12
0x1800251c9  or      r15d, 2
0x1800251cd  mov     [rbp+var_5C], r15d
0x1800251d1  mov     dword ptr [rbp+pExceptionObject], r12d
0x1800251d5  xorps   xmm0, xmm0
0x1800251d8  movdqu  [rbp+pExceptionObject+8], xmm0
0x1800251dd  mov     rax, [rbx]
0x1800251e0  lea     rdx, [rbp+var_50]
0x1800251e4  mov     rcx, rbx
0x1800251e7  mov     rax, [rax+30h]
0x1800251eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251f0  test    eax, eax
0x1800251f2  js      loc_1800252F8
0x1800251f8  and     r15d, 0FFFFFFFDh
0x1800251fc  or      r15d, 1
0x180025200  mov     dword ptr [rbp+pExceptionObject], r12d
0x180025204  xorps   xmm0, xmm0
0x180025207  movdqu  [rbp+pExceptionObject+8], xmm0
0x18002520c  mov     rax, [rdi]
0x18002520f  mov     rdx, [rbp+var_50]
0x180025213  mov     rcx, rdi
0x180025216  mov     rax, [rax+68h]
0x18002521a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002521f  test    eax, eax
0x180025221  js      loc_180025336
0x180025227  cmp     [rbp+var_50], r12
0x18002522b  jz      short loc_180025236
0x18002522d  lea     rcx, [rbp+var_50]
0x180025231  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025236  mov     [rbp+var_60], r12b
0x18002523a  mov     dword ptr [rbp+pExceptionObject], r12d
0x18002523e  xorps   xmm0, xmm0
0x180025241  movdqu  [rbp+pExceptionObject+8], xmm0
0x180025246  mov     rax, [rbx]
0x180025249  lea     rdx, [rbp+var_60]
0x18002524d  mov     rcx, rbx
0x180025250  mov     rax, [rax+40h]
0x180025254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025259  test    eax, eax
0x18002525b  js      loc_18002532A
0x180025261  cmp     [rbp+var_60], r12b
0x180025265  jnz     loc_1800251B0
0x18002526b  lea     rcx, [rbp+var_58]
0x18002526f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025274  mov     rbx, r12
0x180025277  mov     [rbp+var_58], rbx
0x18002527b  jmp     loc_1800251B0
0x180025280  test    rbx, rbx
0x180025283  jz      short loc_18002528E
0x180025285  lea     rcx, [rbp+var_58]
0x180025289  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002528e  lea     rdx, [rbp+var_28]
0x180025292  lea     rcx, [rbp+var_30]
0x180025296  call    ?DeployInfo@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo@UIWindowsSoftwareUpdateExecutionInfo@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(void)
0x18002529b  mov     rbx, rax
0x18002529e  cmp     rsi, rax
0x1800252a1  jz      short loc_1800252B9
0x1800252a3  cmp     [rsi], r12
0x1800252a6  jz      short loc_1800252B0
0x1800252a8  mov     rcx, rsi
0x1800252ab  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800252b0  mov     rcx, [rbx]
0x1800252b3  mov     [rbx], r12
0x1800252b6  mov     [rsi], rcx
0x1800252b9  cmp     [rbp+var_28], r12
0x1800252bd  jz      short loc_1800252C9
0x1800252bf  lea     rcx, [rbp+var_28]
0x1800252c3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800252c8  nop
0x1800252c9  test    rdi, rdi
0x1800252cc  jz      short loc_1800252D8
0x1800252ce  lea     rcx, [rbp+var_30]
0x1800252d2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800252d7  nop
0x1800252d8  mov     rax, r14
0x1800252db  lea     r11, [rsp+80h+var_s0]
0x1800252e3  mov     rbx, [r11+38h]
0x1800252e7  mov     rsi, [r11+40h]
0x1800252eb  mov     rsp, r11
0x1800252ee  pop     r15
0x1800252f0  pop     r14
0x1800252f2  pop     r12
0x1800252f4  pop     rdi
0x1800252f5  pop     rbp
0x1800252f6  retn
0x1800252f8  lea     rdx, [rbp+pExceptionObject]
0x1800252fc  mov     ecx, eax
0x1800252fe  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180025304  lea     rcx, [rbp+var_18]
0x180025308  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002530d  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180025310  lea     rcx, [rbp+pExceptionObject]; this
0x180025314  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180025319  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180025320  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025324  call    _CxxThrowException_0
0x18002532a  lea     rdx, [rbp+pExceptionObject]
0x18002532e  mov     ecx, eax
0x180025330  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180025336  lea     rdx, [rbp+pExceptionObject]
0x18002533a  mov     ecx, eax
0x18002533c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
