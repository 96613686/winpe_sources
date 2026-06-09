# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo>(winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &)

- ea: `0x180011234`
- end: `0x180011384`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUWindowsSoftwareUpdateActionInfo@Update@Management@Windows@2@00@Z`
- size: `336`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012e60`

## callees

- `0x18000340c`
- `0x180011234`
- `0x1800114a8`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001c8a0`
- `0x18002a010`

## pseudocode

```c
__int64 *__fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo>(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v8; // rsi
  __int64 *v9; // rdi
  __int64 *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  const struct winrt::impl::slim_source_location *v16; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v18[24]; // [rsp+38h] [rbp-40h] BYREF

  a1[2] = (__int64)&winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalActionInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = (__int64)&winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo::`vftable';
  v8 = a1 + 3;
  a1[3] = 0;
  v9 = a1 + 4;
  a1[4] = 0;
  v10 = a1 + 5;
  a1[5] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v16 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v18, v11);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v16);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  if ( v8 != a2 )
  {
    if ( *v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
    v12 = *a2;
    *v8 = *a2;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  if ( v9 != a3 )
  {
    if ( *v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
    v13 = *a3;
    *v9 = *a3;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  }
  if ( v10 != a4 )
  {
    if ( *v10 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
    v14 = *a4;
    *v10 = *a4;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  }
  *a1 = (__int64)&winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180011234  mov     [rsp+arg_8], rbx
0x180011239  mov     [rsp+arg_10], rbp
0x18001123e  mov     [rsp+arg_0], rcx
0x180011243  push    rsi
0x180011244  push    rdi
0x180011245  push    r12
0x180011247  push    r14
0x180011249  push    r15
0x18001124b  sub     rsp, 50h
0x18001124f  mov     rbp, r9
0x180011252  mov     r12, r8
0x180011255  mov     r15, rdx
0x180011258  mov     r14, rcx
0x18001125b  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalActionInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalActionInfo>::`vftable'
0x180011262  mov     [rcx+10h], rax
0x180011266  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001126d  mov     qword ptr [rcx+8], 1
0x180011275  lea     rax, ??_7WindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo::`vftable'
0x18001127c  mov     [rcx], rax
0x18001127f  lea     rsi, [rcx+18h]
0x180011283  mov     qword ptr [rsi], 0
0x18001128a  lea     rdi, [rcx+20h]
0x18001128e  mov     qword ptr [rdi], 0
0x180011295  lea     rbx, [rcx+28h]
0x180011299  mov     qword ptr [rbx], 0
0x1800112a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800112a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800112ac  test    al, al
0x1800112ae  jz      loc_18001135B
0x1800112b4  cmp     rsi, r15
0x1800112b7  jz      short loc_1800112DE
0x1800112b9  cmp     qword ptr [rsi], 0
0x1800112bd  jz      short loc_1800112C7
0x1800112bf  mov     rcx, rsi
0x1800112c2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800112c7  mov     rcx, [r15]
0x1800112ca  mov     [rsi], rcx
0x1800112cd  test    rcx, rcx
0x1800112d0  jz      short loc_1800112DE
0x1800112d2  mov     rax, [rcx]
0x1800112d5  mov     rax, [rax+8]
0x1800112d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112de  cmp     rdi, r12
0x1800112e1  jz      short loc_180011309
0x1800112e3  cmp     qword ptr [rdi], 0
0x1800112e7  jz      short loc_1800112F1
0x1800112e9  mov     rcx, rdi
0x1800112ec  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800112f1  mov     rcx, [r12]
0x1800112f5  mov     [rdi], rcx
0x1800112f8  test    rcx, rcx
0x1800112fb  jz      short loc_180011309
0x1800112fd  mov     rax, [rcx]
0x180011300  mov     rax, [rax+8]
0x180011304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011309  cmp     rbx, rbp
0x18001130c  jz      short loc_180011335
0x18001130e  cmp     qword ptr [rbx], 0
0x180011312  jz      short loc_18001131C
0x180011314  mov     rcx, rbx
0x180011317  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001131c  mov     rcx, [rbp+0]
0x180011320  mov     [rbx], rcx
0x180011323  test    rcx, rcx
0x180011326  jz      short loc_180011335
0x180011328  mov     rax, [rcx]
0x18001132b  mov     rax, [rax+8]
0x18001132f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011334  nop
0x180011335  lea     rax, ??_7WindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo::`vftable'
0x18001133c  mov     [r14], rax
0x18001133f  mov     rax, r14
0x180011342  lea     r11, [rsp+78h+var_28]
0x180011347  mov     rbx, [r11+38h]
0x18001134b  mov     rbp, [r11+40h]
0x18001134f  mov     rsp, r11
0x180011352  pop     r15
0x180011354  pop     r14
0x180011356  pop     r12
0x180011358  pop     rdi
0x180011359  pop     rsi
0x18001135a  retn
0x18001135b  lea     rcx, [rsp+78h+var_40]
0x180011360  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180011365  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180011368  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001136d  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180011372  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180011379  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001137e  call    _CxxThrowException_0
```
