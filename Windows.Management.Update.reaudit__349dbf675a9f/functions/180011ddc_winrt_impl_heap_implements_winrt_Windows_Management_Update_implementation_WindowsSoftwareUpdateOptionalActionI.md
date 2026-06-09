# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo>(winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &)

- ea: `0x180011ddc`
- end: `0x180011f24`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUWindowsSoftwareUpdateActionInfo@Update@Management@Windows@2@00@Z`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013a40`

## callees

- `0x1800035f0`
- `0x180011ddc`
- `0x18001203c`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001db60`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo>(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v8; // rsi
  __int64 *v9; // rdi
  __int64 *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  const struct winrt::impl::slim_source_location *v15; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v17[24]; // [rsp+38h] [rbp-40h] BYREF

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
    v15 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v17);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v15);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  if ( v8 != a2 )
  {
    if ( *v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
    v11 = *a2;
    *v8 = *a2;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  }
  if ( v9 != a3 )
  {
    if ( *v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
    v12 = *a3;
    *v9 = *a3;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  if ( v10 != a4 )
  {
    if ( *v10 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
    v13 = *a4;
    *v10 = *a4;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  }
  *a1 = (__int64)&winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180011ddc  mov     [rsp+arg_8], rbx
0x180011de1  mov     [rsp+arg_10], rbp
0x180011de6  mov     [rsp+arg_0], rcx
0x180011deb  push    rsi
0x180011dec  push    rdi
0x180011ded  push    r12
0x180011def  push    r14
0x180011df1  push    r15
0x180011df3  sub     rsp, 50h
0x180011df7  mov     r12, r9
0x180011dfa  mov     rbp, r8
0x180011dfd  mov     r15, rdx
0x180011e00  mov     r14, rcx
0x180011e03  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalActionInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalActionInfo>::`vftable'
0x180011e0a  mov     [rcx+10h], rax
0x180011e0e  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011e15  mov     qword ptr [rcx+8], 1
0x180011e1d  lea     rax, ??_7WindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo::`vftable'
0x180011e24  mov     [rcx], rax
0x180011e27  lea     rsi, [rcx+18h]
0x180011e2b  and     qword ptr [rsi], 0
0x180011e2f  lea     rdi, [rcx+20h]
0x180011e33  and     qword ptr [rdi], 0
0x180011e37  lea     rbx, [rcx+28h]
0x180011e3b  and     qword ptr [rbx], 0
0x180011e3f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180011e46  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180011e4b  test    al, al
0x180011e4d  jz      loc_180011EFB
0x180011e53  cmp     rsi, r15
0x180011e56  jz      short loc_180011E7D
0x180011e58  cmp     qword ptr [rsi], 0
0x180011e5c  jz      short loc_180011E66
0x180011e5e  mov     rcx, rsi
0x180011e61  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011e66  mov     rcx, [r15]
0x180011e69  mov     [rsi], rcx
0x180011e6c  test    rcx, rcx
0x180011e6f  jz      short loc_180011E7D
0x180011e71  mov     rax, [rcx]
0x180011e74  mov     rax, [rax+8]
0x180011e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e7d  cmp     rdi, rbp
0x180011e80  jz      short loc_180011EA8
0x180011e82  cmp     qword ptr [rdi], 0
0x180011e86  jz      short loc_180011E90
0x180011e88  mov     rcx, rdi
0x180011e8b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011e90  mov     rcx, [rbp+0]
0x180011e94  mov     [rdi], rcx
0x180011e97  test    rcx, rcx
0x180011e9a  jz      short loc_180011EA8
0x180011e9c  mov     rax, [rcx]
0x180011e9f  mov     rax, [rax+8]
0x180011ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ea8  cmp     rbx, r12
0x180011eab  jz      short loc_180011ED4
0x180011ead  cmp     qword ptr [rbx], 0
0x180011eb1  jz      short loc_180011EBB
0x180011eb3  mov     rcx, rbx
0x180011eb6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011ebb  mov     rcx, [r12]
0x180011ebf  mov     [rbx], rcx
0x180011ec2  test    rcx, rcx
0x180011ec5  jz      short loc_180011ED4
0x180011ec7  mov     rax, [rcx]
0x180011eca  mov     rax, [rax+8]
0x180011ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed3  nop
0x180011ed4  lea     rax, ??_7WindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo::`vftable'
0x180011edb  mov     [r14], rax
0x180011ede  mov     rax, r14
0x180011ee1  lea     r11, [rsp+78h+var_28]
0x180011ee6  mov     rbx, [r11+38h]
0x180011eea  mov     rbp, [r11+40h]
0x180011eee  mov     rsp, r11
0x180011ef1  pop     r15
0x180011ef3  pop     r14
0x180011ef5  pop     r12
0x180011ef7  pop     rdi
0x180011ef8  pop     rsi
0x180011ef9  retn
0x180011efb  lea     rcx, [rsp+78h+var_40]
0x180011f00  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180011f05  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180011f08  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180011f0d  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180011f12  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180011f19  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180011f1e  call    _CxxThrowException_0
```
