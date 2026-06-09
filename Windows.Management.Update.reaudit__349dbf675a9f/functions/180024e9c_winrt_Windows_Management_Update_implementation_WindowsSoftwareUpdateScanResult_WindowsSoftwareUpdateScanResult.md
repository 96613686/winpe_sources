# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::WindowsSoftwareUpdateScanResult(bool,uint,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate> const &)

- ea: `0x180024e9c`
- end: `0x1800250e9`
- name: `??0WindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@QEAA@_NIAEBU?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@45@@Z`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013f30`

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
- `0x180024e9c`
- `0x1800254a0`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::WindowsSoftwareUpdateScanResult(
        __int64 a1,
        char a2,
        int a3,
        __int64 a4)
{
  __int64 *v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // rbx
  unsigned int v11; // r15d
  int v12; // r15d
  signed int v13; // eax
  __int64 v14; // r8
  signed int v15; // eax
  __int64 v16; // r8
  signed int v17; // eax
  __int64 v18; // r8
  __int64 *v19; // rbx
  __int64 v20; // rcx
  const struct winrt::impl::slim_source_location *v22; // rax
  _BYTE v23[4]; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v24; // [rsp+24h] [rbp-5Ch]
  __int64 v25; // [rsp+28h] [rbp-58h] BYREF
  __int64 v26; // [rsp+30h] [rbp-50h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v28; // [rsp+50h] [rbp-30h] BYREF
  __int64 v29; // [rsp+58h] [rbp-28h] BYREF
  __int64 v30; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v31[24]; // [rsp+68h] [rbp-18h] BYREF

  v24 = 0;
  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateScanResult>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::`vftable';
  v8 = (__int64 *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v22 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v31);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v22);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  *(_BYTE *)(a1 + 24) = a2;
  *(_DWORD *)(a1 + 28) = a3;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>(
    &v28,
    pExceptionObject);
  std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(pExceptionObject);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(
    a4,
    &v25);
  v30 = 0;
  v9 = v28;
  v10 = v25;
  v11 = v24;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v25, &v30) )
  {
    v26 = 0;
    v12 = v11 | 2;
    v24 = v12;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 48LL))(v10, &v26);
    if ( v13 < 0 )
      winrt::throw_hresult(v13, (unsigned int *)pExceptionObject, v14);
    v11 = v12 & 0xFFFFFFFC | 1;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 104LL))(v9, v26);
    if ( v15 < 0 )
      winrt::throw_hresult(v15, (unsigned int *)pExceptionObject, v16);
    if ( v26 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
    v23[0] = 0;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v10 + 64LL))(v10, v23);
    if ( v17 < 0 )
      winrt::throw_hresult(v17, (unsigned int *)pExceptionObject, v18);
    if ( !v23[0] )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
      v10 = 0;
      v25 = 0;
    }
  }
  if ( v10 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
  v19 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                     &v28,
                     &v29);
  if ( v8 != v19 )
  {
    if ( *v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
    v20 = *v19;
    *v19 = 0;
    *v8 = v20;
  }
  if ( v29 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
  if ( v9 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
  return a1;
}

```

## disassembly

```asm
0x180024e9c  mov     [rsp-28h+arg_8], rbx
0x180024ea1  mov     [rsp-28h+arg_10], rsi
0x180024ea6  mov     [rsp-28h+arg_0], rcx
0x180024eab  push    rbp
0x180024eac  push    rdi
0x180024ead  push    r12
0x180024eaf  push    r14
0x180024eb1  push    r15
0x180024eb3  mov     rbp, rsp
0x180024eb6  sub     rsp, 80h
0x180024ebd  mov     rbx, r9
0x180024ec0  mov     edi, r8d
0x180024ec3  mov     r15b, dl
0x180024ec6  mov     r14, rcx
0x180024ec9  xor     r12d, r12d
0x180024ecc  mov     [rbp+var_5C], r12d
0x180024ed0  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateScanResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateScanResult>::`vftable'
0x180024ed7  mov     [rcx+10h], rax
0x180024edb  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180024ee2  mov     qword ptr [rcx+8], 1
0x180024eea  lea     rax, ??_7WindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult::`vftable'
0x180024ef1  mov     [rcx], rax
0x180024ef4  lea     rsi, [rcx+28h]
0x180024ef8  mov     [rsi], r12
0x180024efb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180024f02  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180024f07  test    al, al
0x180024f09  jz      loc_1800250AB
0x180024f0f  mov     [r14+18h], r15b
0x180024f13  mov     [r14+1Ch], edi
0x180024f17  xorps   xmm0, xmm0
0x180024f1a  movdqu  [rbp+pExceptionObject], xmm0
0x180024f1f  mov     [rbp+var_38], r12
0x180024f23  lea     rdx, [rbp+pExceptionObject]
0x180024f27  lea     rcx, [rbp+var_30]
0x180024f2b  call    ??$single_threaded_vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>(std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate> &&)
0x180024f30  nop
0x180024f31  lea     rcx, [rbp+pExceptionObject]
0x180024f35  call    ??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(void)
0x180024f3a  lea     rdx, [rbp+var_58]
0x180024f3e  mov     rcx, rbx
0x180024f41  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UWindowsSoftwareUpdate@Update@Management@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(void)
0x180024f46  nop
0x180024f47  mov     [rbp+var_20], r12
0x180024f4b  mov     rdi, [rbp+var_30]
0x180024f4f  mov     rbx, [rbp+var_58]
0x180024f53  mov     r15d, [rbp+var_5C]
0x180024f57  lea     rdx, [rbp+var_20]
0x180024f5b  lea     rcx, [rbp+var_58]
0x180024f5f  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180024f64  test    al, al
0x180024f66  jnz     loc_180025027
0x180024f6c  mov     [rbp+var_50], r12
0x180024f70  or      r15d, 2
0x180024f74  mov     [rbp+var_5C], r15d
0x180024f78  mov     dword ptr [rbp+pExceptionObject], r12d
0x180024f7c  xorps   xmm0, xmm0
0x180024f7f  movdqu  [rbp+pExceptionObject+8], xmm0
0x180024f84  mov     rax, [rbx]
0x180024f87  lea     rdx, [rbp+var_50]
0x180024f8b  mov     rcx, rbx
0x180024f8e  mov     rax, [rax+30h]
0x180024f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f97  test    eax, eax
0x180024f99  js      loc_18002509F
0x180024f9f  and     r15d, 0FFFFFFFDh
0x180024fa3  or      r15d, 1
0x180024fa7  mov     dword ptr [rbp+pExceptionObject], r12d
0x180024fab  xorps   xmm0, xmm0
0x180024fae  movdqu  [rbp+pExceptionObject+8], xmm0
0x180024fb3  mov     rax, [rdi]
0x180024fb6  mov     rdx, [rbp+var_50]
0x180024fba  mov     rcx, rdi
0x180024fbd  mov     rax, [rax+68h]
0x180024fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fc6  test    eax, eax
0x180024fc8  js      loc_1800250DD
0x180024fce  cmp     [rbp+var_50], r12
0x180024fd2  jz      short loc_180024FDD
0x180024fd4  lea     rcx, [rbp+var_50]
0x180024fd8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024fdd  mov     [rbp+var_60], r12b
0x180024fe1  mov     dword ptr [rbp+pExceptionObject], r12d
0x180024fe5  xorps   xmm0, xmm0
0x180024fe8  movdqu  [rbp+pExceptionObject+8], xmm0
0x180024fed  mov     rax, [rbx]
0x180024ff0  lea     rdx, [rbp+var_60]
0x180024ff4  mov     rcx, rbx
0x180024ff7  mov     rax, [rax+40h]
0x180024ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025000  test    eax, eax
0x180025002  js      loc_1800250D1
0x180025008  cmp     [rbp+var_60], r12b
0x18002500c  jnz     loc_180024F57
0x180025012  lea     rcx, [rbp+var_58]
0x180025016  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002501b  mov     rbx, r12
0x18002501e  mov     [rbp+var_58], rbx
0x180025022  jmp     loc_180024F57
0x180025027  test    rbx, rbx
0x18002502a  jz      short loc_180025035
0x18002502c  lea     rcx, [rbp+var_58]
0x180025030  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025035  lea     rdx, [rbp+var_28]
0x180025039  lea     rcx, [rbp+var_30]
0x18002503d  call    ?DeployInfo@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo@UIWindowsSoftwareUpdateExecutionInfo@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(void)
0x180025042  mov     rbx, rax
0x180025045  cmp     rsi, rax
0x180025048  jz      short loc_180025060
0x18002504a  cmp     [rsi], r12
0x18002504d  jz      short loc_180025057
0x18002504f  mov     rcx, rsi
0x180025052  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025057  mov     rcx, [rbx]
0x18002505a  mov     [rbx], r12
0x18002505d  mov     [rsi], rcx
0x180025060  cmp     [rbp+var_28], r12
0x180025064  jz      short loc_180025070
0x180025066  lea     rcx, [rbp+var_28]
0x18002506a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002506f  nop
0x180025070  test    rdi, rdi
0x180025073  jz      short loc_18002507F
0x180025075  lea     rcx, [rbp+var_30]
0x180025079  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002507e  nop
0x18002507f  mov     rax, r14
0x180025082  lea     r11, [rsp+80h+var_s0]
0x18002508a  mov     rbx, [r11+38h]
0x18002508e  mov     rsi, [r11+40h]
0x180025092  mov     rsp, r11
0x180025095  pop     r15
0x180025097  pop     r14
0x180025099  pop     r12
0x18002509b  pop     rdi
0x18002509c  pop     rbp
0x18002509d  retn
0x18002509f  lea     rdx, [rbp+pExceptionObject]
0x1800250a3  mov     ecx, eax
0x1800250a5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800250ab  lea     rcx, [rbp+var_18]
0x1800250af  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800250b4  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800250b7  lea     rcx, [rbp+pExceptionObject]; this
0x1800250bb  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800250c0  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800250c7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800250cb  call    _CxxThrowException_0
0x1800250d1  lea     rdx, [rbp+pExceptionObject]
0x1800250d5  mov     ecx, eax
0x1800250d7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800250dd  lea     rdx, [rbp+pExceptionObject]
0x1800250e1  mov     ecx, eax
0x1800250e3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
