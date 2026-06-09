# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::WindowsSoftwareUpdateOptionalInfo(winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo> const &,winrt::Windows::Foundation::IReference<int> const &,winrt::Windows::Foundation::IReference<int> const &)

- ea: `0x18001f628`
- end: `0x18001f98d`
- name: `??0WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@QEAA@AEBU?$IIterable@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@45@AEBU?$IReference@H@845@1@Z`
- size: `869`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013310`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x18001203c`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001db60`
- `0x18001e7a4`
- `0x18001efbc`
- `0x18001f628`
- `0x18001fa3c`
- `0x180020464`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_QWORD *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::WindowsSoftwareUpdateOptionalInfo(
        _QWORD *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v8; // r15
  _QWORD *v9; // rax
  char *v10; // rsi
  __int64 v11; // rcx
  signed int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rdi
  __int64 v15; // rbx
  signed int v16; // eax
  __int64 v17; // r8
  unsigned int v18; // edi
  int v19; // edi
  signed int v20; // eax
  __int64 v21; // r8
  signed int v22; // eax
  __int64 v23; // r8
  signed int v24; // eax
  __int64 v25; // r8
  signed int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rbx
  const struct winrt::impl::slim_source_location *v30; // rax
  char v31[8]; // [rsp+28h] [rbp-39h] BYREF
  __int64 v32; // [rsp+30h] [rbp-31h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-29h] BYREF
  __int64 v34; // [rsp+50h] [rbp-11h] BYREF
  int v35; // [rsp+58h] [rbp-9h]
  __int64 v36; // [rsp+60h] [rbp-1h] BYREF
  __int64 v37; // [rsp+68h] [rbp+7h] BYREF
  _QWORD *v38; // [rsp+70h] [rbp+Fh] BYREF
  char v39[32]; // [rsp+78h] [rbp+17h] BYREF

  v35 = 0;
  a1[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable';
  v8 = a1 + 3;
  a1[3] = 0;
  a1[4] = 0;
  a1[5] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v30 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v39);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v30);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  v9 = operator new(0x48u);
  v10 = (char *)(v9 + 2);
  v9[2] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::`vftable';
  v9[3] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::`vftable';
  v9[4] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v9[1] = 1;
  *((_DWORD *)v9 + 10) = 0;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  v9[6] = 0;
  v9[7] = 0;
  v9[8] = 0;
  *v9 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>>::`vftable';
  v38 = v9 + 2;
  std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(pExceptionObject);
  v32 = 0;
  v11 = *a2;
  *(_DWORD *)pExceptionObject = 0;
  *(_OWORD *)&pExceptionObject[8] = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 48LL))(v11, &v32);
  if ( v12 < 0 )
    winrt::throw_hresult(v12, (unsigned int *)pExceptionObject, v13);
  v14 = v32;
  v36 = v32;
  v15 = 0;
  v31[0] = 0;
  *(_DWORD *)pExceptionObject = 0;
  *(_OWORD *)&pExceptionObject[8] = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v32 + 56LL))(v32, v31);
  if ( v16 < 0 )
    winrt::throw_hresult(v16, (unsigned int *)pExceptionObject, v17);
  if ( v31[0] )
  {
    v15 = v14;
    v34 = v14;
  }
  else
  {
    v34 = 0;
    if ( v14 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
  }
  v18 = 31;
  v36 = 0;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v34, &v36) )
  {
    v32 = 0;
    v19 = v18 | 0x40;
    v35 = v19;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 48LL))(v15, &v32);
    if ( v20 < 0 )
      winrt::throw_hresult(v20, (unsigned int *)pExceptionObject, v21);
    v18 = v19 & 0xFFFFFF9F | 0x20;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v22 = (*(__int64 (__fastcall **)(char *, __int64))(*(_QWORD *)v10 + 104LL))(v10, v32);
    if ( v22 < 0 )
      winrt::throw_hresult(v22, (unsigned int *)pExceptionObject, v23);
    if ( v32 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v32);
    v31[0] = 0;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v15 + 64LL))(v15, v31);
    if ( v24 < 0 )
      winrt::throw_hresult(v24, (unsigned int *)pExceptionObject, v25);
    if ( !v31[0] )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v34);
      v15 = 0;
      v34 = 0;
    }
  }
  if ( v15 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v34);
  v32 = 0;
  *(_DWORD *)pExceptionObject = 0;
  *(_OWORD *)&pExceptionObject[8] = 0;
  v26 = (*(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v10 + 64LL))(v10, &v32);
  if ( v26 < 0 )
    winrt::throw_hresult(v26, (unsigned int *)pExceptionObject, v27);
  v28 = v32;
  v37 = v32;
  if ( v8 == &v37 )
  {
    if ( v32 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
  }
  else
  {
    if ( *v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
    *v8 = v28;
  }
  winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(
    (__int64)a1,
    a3,
    a4);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v38);
  return a1;
}

```

## disassembly

```asm
0x18001f628  mov     rax, rsp
0x18001f62b  mov     [rax+10h], rbx
0x18001f62f  mov     [rax+18h], rsi
0x18001f633  mov     [rax+20h], rdi
0x18001f637  mov     [rax+8], rcx
0x18001f63b  push    rbp
0x18001f63c  push    r12
0x18001f63e  push    r13
0x18001f640  push    r14
0x18001f642  push    r15
0x18001f644  lea     rbp, [rax-5Fh]
0x18001f648  sub     rsp, 90h
0x18001f64f  mov     r12, r9
0x18001f652  mov     r13, r8
0x18001f655  mov     rbx, rdx
0x18001f658  mov     r14, rcx
0x18001f65b  xor     edi, edi
0x18001f65d  mov     [rbp+57h+var_60], edi
0x18001f660  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::`vftable'
0x18001f667  mov     [rcx+10h], rax
0x18001f66b  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f672  mov     qword ptr [rcx+8], 1
0x18001f67a  lea     rax, ??_7WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::`vftable'
0x18001f681  mov     [rcx], rax
0x18001f684  lea     r15, [rcx+18h]
0x18001f688  mov     [r15], rdi
0x18001f68b  mov     [rcx+20h], rdi
0x18001f68f  mov     [rcx+28h], rdi
0x18001f693  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001f69a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001f69f  test    al, al
0x18001f6a1  jz      loc_18001F92B
0x18001f6a7  xorps   xmm0, xmm0
0x18001f6aa  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18001f6af  mov     [rbp+57h+var_70], rdi
0x18001f6b3  lea     ecx, [rdi+48h]; Size
0x18001f6b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f6bb  mov     [rbp+57h+var_48], rax
0x18001f6bf  lea     rsi, [rax+10h]
0x18001f6c3  lea     rcx, ??_7?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::`vftable'
0x18001f6ca  mov     [rsi], rcx
0x18001f6cd  lea     rcx, ??_7?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVectorView@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::`vftable'
0x18001f6d4  mov     [rsi+8], rcx
0x18001f6d8  lea     rcx, ??_7?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IIterable@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::`vftable'
0x18001f6df  mov     [rsi+10h], rcx
0x18001f6e3  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f6ea  mov     qword ptr [rax+8], 1
0x18001f6f2  xor     ecx, ecx
0x18001f6f4  mov     [rax+28h], ecx
0x18001f6f7  mov     [rbp+57h+var_70], rdi
0x18001f6fb  mov     qword ptr [rbp+57h+pExceptionObject+8], rdi
0x18001f6ff  mov     qword ptr [rbp+57h+pExceptionObject], rdi
0x18001f703  mov     [rax+30h], rdi
0x18001f707  mov     [rax+38h], rdi
0x18001f70b  mov     [rax+40h], rdi
0x18001f70f  lea     rcx, ??_7?$heap_implements@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>>::`vftable'
0x18001f716  mov     [rax], rcx
0x18001f719  mov     [rbp+57h+var_48], rsi
0x18001f71d  lea     rcx, [rbp+57h+pExceptionObject]
0x18001f721  call    ??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(void)
0x18001f726  mov     [rbp+57h+var_88], rdi
0x18001f72a  mov     rcx, [rbx]
0x18001f72d  mov     dword ptr [rbp+57h+pExceptionObject], edi
0x18001f730  xorps   xmm0, xmm0
0x18001f733  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001f738  mov     rax, [rcx]
0x18001f73b  lea     rdx, [rbp+57h+var_88]
0x18001f73f  mov     rax, [rax+30h]
0x18001f743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f748  test    eax, eax
0x18001f74a  js      loc_18001F951
0x18001f750  mov     rdi, [rbp+57h+var_88]
0x18001f754  mov     [rbp+57h+var_58], rdi
0x18001f758  xor     ebx, ebx
0x18001f75a  mov     [rbp+57h+var_90], bl
0x18001f75d  mov     dword ptr [rbp+57h+pExceptionObject], ebx
0x18001f760  xorps   xmm0, xmm0
0x18001f763  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001f768  mov     rax, [rdi]
0x18001f76b  lea     rdx, [rbp+57h+var_90]
0x18001f76f  mov     rcx, rdi
0x18001f772  mov     rax, [rax+38h]
0x18001f776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f77b  test    eax, eax
0x18001f77d  js      loc_18001F95D
0x18001f783  cmp     [rbp+57h+var_90], bl
0x18001f786  jnz     short loc_18001F79C
0x18001f788  mov     [rbp+57h+var_68], rbx
0x18001f78c  test    rdi, rdi
0x18001f78f  jz      short loc_18001F7A3
0x18001f791  lea     rcx, [rbp+57h+var_58]
0x18001f795  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f79a  jmp     short loc_18001F7A3
0x18001f79c  mov     rbx, rdi
0x18001f79f  mov     [rbp+57h+var_68], rbx
0x18001f7a3  mov     edi, 1Fh
0x18001f7a8  and     [rbp+57h+var_58], 0
0x18001f7ad  lea     rdx, [rbp+57h+var_58]
0x18001f7b1  lea     rcx, [rbp+57h+var_68]
0x18001f7b5  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001f7ba  test    al, al
0x18001f7bc  jnz     loc_18001F87A
0x18001f7c2  and     [rbp+57h+var_88], 0
0x18001f7c7  or      edi, 40h
0x18001f7ca  mov     [rbp+57h+var_60], edi
0x18001f7cd  and     dword ptr [rbp+57h+pExceptionObject], 0
0x18001f7d1  xorps   xmm0, xmm0
0x18001f7d4  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001f7d9  mov     rax, [rbx]
0x18001f7dc  lea     rdx, [rbp+57h+var_88]
0x18001f7e0  mov     rcx, rbx
0x18001f7e3  mov     rax, [rax+30h]
0x18001f7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7ec  test    eax, eax
0x18001f7ee  js      loc_18001F981
0x18001f7f4  and     edi, 0FFFFFFBFh
0x18001f7f7  or      edi, 20h
0x18001f7fa  and     dword ptr [rbp+57h+pExceptionObject], 0
0x18001f7fe  xorps   xmm0, xmm0
0x18001f801  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001f806  mov     rax, [rsi]
0x18001f809  mov     rdx, [rbp+57h+var_88]
0x18001f80d  mov     rcx, rsi
0x18001f810  mov     rax, [rax+68h]
0x18001f814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f819  test    eax, eax
0x18001f81b  js      loc_18001F975
0x18001f821  cmp     [rbp+57h+var_88], 0
0x18001f826  jz      short loc_18001F831
0x18001f828  lea     rcx, [rbp+57h+var_88]
0x18001f82c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f831  mov     [rbp+57h+var_90], 0
0x18001f835  and     dword ptr [rbp+57h+pExceptionObject], 0
0x18001f839  xorps   xmm0, xmm0
0x18001f83c  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001f841  mov     rax, [rbx]
0x18001f844  lea     rdx, [rbp+57h+var_90]
0x18001f848  mov     rcx, rbx
0x18001f84b  mov     rax, [rax+40h]
0x18001f84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f854  test    eax, eax
0x18001f856  js      loc_18001F969
0x18001f85c  cmp     [rbp+57h+var_90], 0
0x18001f860  jnz     loc_18001F7AD
0x18001f866  lea     rcx, [rbp+57h+var_68]
0x18001f86a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f86f  xor     ebx, ebx
0x18001f871  mov     [rbp+57h+var_68], rbx
0x18001f875  jmp     loc_18001F7AD
0x18001f87a  xor     edi, edi
0x18001f87c  test    rbx, rbx
0x18001f87f  jz      short loc_18001F88A
0x18001f881  lea     rcx, [rbp+57h+var_68]
0x18001f885  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f88a  mov     [rbp+57h+var_88], rdi
0x18001f88e  mov     dword ptr [rbp+57h+pExceptionObject], edi
0x18001f891  xorps   xmm0, xmm0
0x18001f894  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x18001f899  mov     rax, [rsi]
0x18001f89c  lea     rdx, [rbp+57h+var_88]
0x18001f8a0  mov     rcx, rsi
0x18001f8a3  mov     rax, [rax+40h]
0x18001f8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8ac  test    eax, eax
0x18001f8ae  js      short loc_18001F91F
0x18001f8b0  mov     rbx, [rbp+57h+var_88]
0x18001f8b4  mov     [rbp+57h+var_50], rbx
0x18001f8b8  lea     rax, [rbp+57h+var_50]
0x18001f8bc  cmp     r15, rax
0x18001f8bf  jz      short loc_18001F8D3
0x18001f8c1  cmp     [r15], rdi
0x18001f8c4  jz      short loc_18001F8CE
0x18001f8c6  mov     rcx, r15
0x18001f8c9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f8ce  mov     [r15], rbx
0x18001f8d1  jmp     short loc_18001F8E1
0x18001f8d3  test    rbx, rbx
0x18001f8d6  jz      short loc_18001F8E1
0x18001f8d8  lea     rcx, [rbp+57h+var_50]
0x18001f8dc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f8e1  mov     r8, r12
0x18001f8e4  mov     rdx, r13
0x18001f8e7  mov     rcx, r14
0x18001f8ea  call    ?InitializeComplianceParameters@WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@AEAAXAEBU?$IReference@H@Foundation@56@0@Z; winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(winrt::Windows::Foundation::IReference<int> const &,winrt::Windows::Foundation::IReference<int> const &)
0x18001f8ef  nop
0x18001f8f0  lea     rcx, [rbp+57h+var_48]
0x18001f8f4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f8f9  nop
0x18001f8fa  mov     rax, r14
0x18001f8fd  lea     r11, [rsp+0B0h+var_20]
0x18001f905  mov     rbx, [r11+38h]
0x18001f909  mov     rsi, [r11+40h]
0x18001f90d  mov     rdi, [r11+48h]
0x18001f911  mov     rsp, r11
0x18001f914  pop     r15
0x18001f916  pop     r14
0x18001f918  pop     r13
0x18001f91a  pop     r12
0x18001f91c  pop     rbp
0x18001f91d  retn
0x18001f91f  lea     rdx, [rbp+57h+pExceptionObject]
0x18001f923  mov     ecx, eax
0x18001f925  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f92b  lea     rcx, [rbp+57h+var_40]
0x18001f92f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001f934  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001f937  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001f93b  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001f940  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001f947  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001f94b  call    _CxxThrowException_0
0x18001f951  lea     rdx, [rbp+57h+pExceptionObject]
0x18001f955  mov     ecx, eax
0x18001f957  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f95d  lea     rdx, [rbp+57h+pExceptionObject]
0x18001f961  mov     ecx, eax
0x18001f963  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f969  lea     rdx, [rbp+57h+pExceptionObject]
0x18001f96d  mov     ecx, eax
0x18001f96f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f975  lea     rdx, [rbp+57h+pExceptionObject]
0x18001f979  mov     ecx, eax
0x18001f97b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f981  lea     rdx, [rbp+57h+pExceptionObject]
0x18001f985  mov     ecx, eax
0x18001f987  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
