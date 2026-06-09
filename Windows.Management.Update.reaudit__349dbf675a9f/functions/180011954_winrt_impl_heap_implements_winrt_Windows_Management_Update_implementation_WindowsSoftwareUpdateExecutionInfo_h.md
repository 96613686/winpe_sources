# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>(winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalActionInfo const &)

- ea: `0x180011954`
- end: `0x180011ac9`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUWindowsSoftwareUpdateActionInfo@Update@Management@Windows@2@0AEBUWindowsSoftwareUpdateOptionalActionInfo@4562@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013950`

## callees

- `0x1800035f0`
- `0x180011954`
- `0x18001203c`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001db60`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 *__fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v8; // r14
  __int64 *v9; // rsi
  __int64 *v10; // rdi
  __int64 *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  const struct winrt::impl::slim_source_location *v16; // rax
  char v17; // [rsp+20h] [rbp-68h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v19[32]; // [rsp+40h] [rbp-48h] BYREF

  a1[2] = (__int64)&winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = (__int64)&winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
  v8 = a1 + 3;
  a1[3] = 0;
  v9 = a1 + 4;
  a1[4] = 0;
  v10 = a1 + 5;
  a1[5] = 0;
  v11 = a1 + 6;
  a1[6] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v16 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v19);
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
  if ( v10 != (__int64 *)&v17 )
  {
    if ( *v10 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
    *v10 = 0;
  }
  if ( v11 != a4 )
  {
    if ( *v11 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v11);
    v14 = *a4;
    *v11 = *a4;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  }
  *a1 = (__int64)&winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180011954  mov     rax, rsp
0x180011957  mov     [rax+10h], rbx
0x18001195b  mov     [rax+18h], rbp
0x18001195f  mov     [rax+20h], rsi
0x180011963  mov     [rax+8], rcx
0x180011967  push    rdi
0x180011968  push    r12
0x18001196a  push    r13
0x18001196c  push    r14
0x18001196e  push    r15
0x180011970  sub     rsp, 60h
0x180011974  mov     r13, r9
0x180011977  mov     r12, r8
0x18001197a  mov     rbp, rdx
0x18001197d  mov     r15, rcx
0x180011980  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateExecutionInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180011987  mov     [rcx+10h], rax
0x18001198b  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011992  mov     qword ptr [rcx+8], 1
0x18001199a  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable'
0x1800119a1  mov     [rcx], rax
0x1800119a4  lea     r14, [rcx+18h]
0x1800119a8  xor     eax, eax
0x1800119aa  mov     [r14], rax
0x1800119ad  lea     rsi, [rcx+20h]
0x1800119b1  mov     [rsi], rax
0x1800119b4  lea     rdi, [rcx+28h]
0x1800119b8  mov     [rdi], rax
0x1800119bb  lea     rbx, [rcx+30h]
0x1800119bf  mov     [rbx], rax
0x1800119c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800119c9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800119ce  test    al, al
0x1800119d0  jz      loc_180011AA0
0x1800119d6  cmp     r14, rbp
0x1800119d9  jz      short loc_180011A01
0x1800119db  cmp     qword ptr [r14], 0
0x1800119df  jz      short loc_1800119E9
0x1800119e1  mov     rcx, r14
0x1800119e4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800119e9  mov     rcx, [rbp+0]
0x1800119ed  mov     [r14], rcx
0x1800119f0  test    rcx, rcx
0x1800119f3  jz      short loc_180011A01
0x1800119f5  mov     rax, [rcx]
0x1800119f8  mov     rax, [rax+8]
0x1800119fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a01  cmp     rsi, r12
0x180011a04  jz      short loc_180011A2C
0x180011a06  cmp     qword ptr [rsi], 0
0x180011a0a  jz      short loc_180011A14
0x180011a0c  mov     rcx, rsi
0x180011a0f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011a14  mov     rcx, [r12]
0x180011a18  mov     [rsi], rcx
0x180011a1b  test    rcx, rcx
0x180011a1e  jz      short loc_180011A2C
0x180011a20  mov     rax, [rcx]
0x180011a23  mov     rax, [rax+8]
0x180011a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a2c  lea     rax, [rsp+88h+var_68]
0x180011a31  cmp     rdi, rax
0x180011a34  jz      short loc_180011A48
0x180011a36  cmp     qword ptr [rdi], 0
0x180011a3a  jz      short loc_180011A44
0x180011a3c  mov     rcx, rdi
0x180011a3f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011a44  and     qword ptr [rdi], 0
0x180011a48  cmp     rbx, r13
0x180011a4b  jz      short loc_180011A74
0x180011a4d  cmp     qword ptr [rbx], 0
0x180011a51  jz      short loc_180011A5B
0x180011a53  mov     rcx, rbx
0x180011a56  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011a5b  mov     rcx, [r13+0]
0x180011a5f  mov     [rbx], rcx
0x180011a62  test    rcx, rcx
0x180011a65  jz      short loc_180011A74
0x180011a67  mov     rax, [rcx]
0x180011a6a  mov     rax, [rax+8]
0x180011a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a73  nop
0x180011a74  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180011a7b  mov     [r15], rax
0x180011a7e  mov     rax, r15
0x180011a81  lea     r11, [rsp+88h+var_28]
0x180011a86  mov     rbx, [r11+38h]
0x180011a8a  mov     rbp, [r11+40h]
0x180011a8e  mov     rsi, [r11+48h]
0x180011a92  mov     rsp, r11
0x180011a95  pop     r15
0x180011a97  pop     r14
0x180011a99  pop     r13
0x180011a9b  pop     r12
0x180011a9d  pop     rdi
0x180011a9e  retn
0x180011aa0  lea     rcx, [rsp+88h+var_48]
0x180011aa5  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180011aaa  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180011aad  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180011ab2  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180011ab7  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180011abe  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180011ac3  call    _CxxThrowException_0
```
