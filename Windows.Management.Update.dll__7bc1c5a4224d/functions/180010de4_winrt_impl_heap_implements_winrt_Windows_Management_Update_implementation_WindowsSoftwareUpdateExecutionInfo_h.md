# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>(winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalActionInfo const &)

- ea: `0x180010de4`
- end: `0x180010f43`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUWindowsSoftwareUpdateActionInfo@Update@Management@Windows@2@0AEBUWindowsSoftwareUpdateOptionalActionInfo@4562@@Z`
- size: `351`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012d70`

## callees

- `0x18000340c`
- `0x180010de4`
- `0x1800114a8`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001c8a0`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>(
        _QWORD *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v8; // r15
  __int64 *v9; // rsi
  char *v10; // rdi
  __int64 *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  const struct winrt::impl::slim_source_location *v17; // rax
  char v18; // [rsp+20h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-80h] BYREF
  _BYTE v20[104]; // [rsp+40h] [rbp-68h] BYREF

  a1[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
  v8 = a1 + 3;
  a1[3] = 0;
  v9 = a1 + 4;
  a1[4] = 0;
  v10 = (char *)(a1 + 5);
  a1[5] = 0;
  v11 = a1 + 6;
  a1[6] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v17 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v20, v12);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v17);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  if ( v8 != a2 )
  {
    if ( *v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
    v13 = *a2;
    *v8 = *a2;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  }
  if ( v9 != a3 )
  {
    if ( *v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
    v14 = *a3;
    *v9 = *a3;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  }
  if ( v10 != &v18 )
  {
    if ( *(_QWORD *)v10 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
    *(_QWORD *)v10 = 0;
  }
  if ( v11 != a4 )
  {
    if ( *v11 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v11);
    v15 = *a4;
    *v11 = *a4;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  }
  *a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180010de4  mov     [rsp+arg_0], rcx
0x180010de9  push    rbx
0x180010dea  push    rbp
0x180010deb  push    rsi
0x180010dec  push    rdi
0x180010ded  push    r12
0x180010def  push    r13
0x180010df1  push    r14
0x180010df3  push    r15
0x180010df5  sub     rsp, 68h
0x180010df9  mov     r13, r9
0x180010dfc  mov     r12, r8
0x180010dff  mov     rbp, rdx
0x180010e02  mov     r14, rcx
0x180010e05  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateExecutionInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180010e0c  mov     [rcx+10h], rax
0x180010e10  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180010e17  mov     qword ptr [rcx+8], 1
0x180010e1f  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180010e26  mov     [rcx], rax
0x180010e29  lea     r15, [rcx+18h]
0x180010e2d  xor     eax, eax
0x180010e2f  mov     [r15], rax
0x180010e32  lea     rsi, [rcx+20h]
0x180010e36  mov     [rsi], rax
0x180010e39  lea     rdi, [rcx+28h]
0x180010e3d  mov     [rdi], rax
0x180010e40  lea     rbx, [rcx+30h]
0x180010e44  mov     [rbx], rax
0x180010e47  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180010e4e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180010e53  test    al, al
0x180010e55  jz      loc_180010F1A
0x180010e5b  cmp     r15, rbp
0x180010e5e  jz      short loc_180010E86
0x180010e60  cmp     qword ptr [r15], 0
0x180010e64  jz      short loc_180010E6E
0x180010e66  mov     rcx, r15
0x180010e69  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010e6e  mov     rcx, [rbp+0]
0x180010e72  mov     [r15], rcx
0x180010e75  test    rcx, rcx
0x180010e78  jz      short loc_180010E86
0x180010e7a  mov     rax, [rcx]
0x180010e7d  mov     rax, [rax+8]
0x180010e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e86  cmp     rsi, r12
0x180010e89  jz      short loc_180010EB1
0x180010e8b  cmp     qword ptr [rsi], 0
0x180010e8f  jz      short loc_180010E99
0x180010e91  mov     rcx, rsi
0x180010e94  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010e99  mov     rcx, [r12]
0x180010e9d  mov     [rsi], rcx
0x180010ea0  test    rcx, rcx
0x180010ea3  jz      short loc_180010EB1
0x180010ea5  mov     rax, [rcx]
0x180010ea8  mov     rax, [rax+8]
0x180010eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eb1  lea     rax, [rsp+0A8h+var_88]
0x180010eb6  cmp     rdi, rax
0x180010eb9  jz      short loc_180010ED0
0x180010ebb  cmp     qword ptr [rdi], 0
0x180010ebf  jz      short loc_180010EC9
0x180010ec1  mov     rcx, rdi
0x180010ec4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010ec9  mov     qword ptr [rdi], 0
0x180010ed0  cmp     rbx, r13
0x180010ed3  jz      short loc_180010EFC
0x180010ed5  cmp     qword ptr [rbx], 0
0x180010ed9  jz      short loc_180010EE3
0x180010edb  mov     rcx, rbx
0x180010ede  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010ee3  mov     rcx, [r13+0]
0x180010ee7  mov     [rbx], rcx
0x180010eea  test    rcx, rcx
0x180010eed  jz      short loc_180010EFC
0x180010eef  mov     rax, [rcx]
0x180010ef2  mov     rax, [rax+8]
0x180010ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010efb  nop
0x180010efc  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180010f03  mov     [r14], rax
0x180010f06  mov     rax, r14
0x180010f09  add     rsp, 68h
0x180010f0d  pop     r15
0x180010f0f  pop     r14
0x180010f11  pop     r13
0x180010f13  pop     r12
0x180010f15  pop     rdi
0x180010f16  pop     rsi
0x180010f17  pop     rbp
0x180010f18  pop     rbx
0x180010f19  retn
0x180010f1a  lea     rcx, [rsp+0A8h+var_68]
0x180010f1f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180010f24  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180010f27  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x180010f2c  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180010f31  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180010f38  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180010f3d  call    _CxxThrowException_0
```
