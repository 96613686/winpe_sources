# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>(winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalActionInfo const &)

- ea: `0x180011ad0`
- end: `0x180011c2b`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUWindowsSoftwareUpdateActionInfo@Update@Management@Windows@2@AEBUWindowsSoftwareUpdateOptionalActionInfo@4562@@Z`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800132a0`

## callees

- `0x1800035f0`
- `0x180011ad0`
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
        __int64 *a3)
{
  __int64 *v6; // rdi
  __int64 *v7; // rsi
  __int64 *v8; // r14
  __int64 *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  const struct winrt::impl::slim_source_location *v13; // rax
  char v14; // [rsp+20h] [rbp-68h] BYREF
  char v15; // [rsp+28h] [rbp-60h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v17[24]; // [rsp+48h] [rbp-40h] BYREF

  a1[2] = (__int64)&winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = (__int64)&winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
  v6 = a1 + 3;
  a1[3] = 0;
  v7 = a1 + 4;
  a1[4] = 0;
  v8 = a1 + 5;
  a1[5] = 0;
  v9 = a1 + 6;
  a1[6] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v17);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v13);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  if ( v6 != (__int64 *)&v14 )
  {
    if ( *v6 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v6);
    *v6 = 0;
  }
  if ( v7 != (__int64 *)&v15 )
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
    *v7 = 0;
  }
  if ( v8 != a2 )
  {
    if ( *v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
    v10 = *a2;
    *v8 = *a2;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  }
  if ( v9 != a3 )
  {
    if ( *v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
    v11 = *a3;
    *v9 = *a3;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  }
  *a1 = (__int64)&winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180011ad0  mov     [rsp+arg_8], rbx
0x180011ad5  mov     [rsp+arg_10], rbp
0x180011ada  mov     [rsp+arg_0], rcx
0x180011adf  push    rsi
0x180011ae0  push    rdi
0x180011ae1  push    r12
0x180011ae3  push    r14
0x180011ae5  push    r15
0x180011ae7  sub     rsp, 60h
0x180011aeb  mov     r12, r8
0x180011aee  mov     rbp, rdx
0x180011af1  mov     r15, rcx
0x180011af4  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateExecutionInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180011afb  mov     [rcx+10h], rax
0x180011aff  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011b06  mov     qword ptr [rcx+8], 1
0x180011b0e  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180011b15  mov     [rcx], rax
0x180011b18  lea     rdi, [rcx+18h]
0x180011b1c  and     qword ptr [rdi], 0
0x180011b20  lea     rsi, [rcx+20h]
0x180011b24  and     qword ptr [rsi], 0
0x180011b28  lea     r14, [rcx+28h]
0x180011b2c  and     qword ptr [r14], 0
0x180011b30  lea     rbx, [rcx+30h]
0x180011b34  and     qword ptr [rbx], 0
0x180011b38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180011b3f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180011b44  test    al, al
0x180011b46  jz      loc_180011C02
0x180011b4c  lea     rax, [rsp+88h+var_68]
0x180011b51  cmp     rdi, rax
0x180011b54  jz      short loc_180011B68
0x180011b56  cmp     qword ptr [rdi], 0
0x180011b5a  jz      short loc_180011B64
0x180011b5c  mov     rcx, rdi
0x180011b5f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011b64  and     qword ptr [rdi], 0
0x180011b68  lea     rax, [rsp+88h+var_60]
0x180011b6d  cmp     rsi, rax
0x180011b70  jz      short loc_180011B84
0x180011b72  cmp     qword ptr [rsi], 0
0x180011b76  jz      short loc_180011B80
0x180011b78  mov     rcx, rsi
0x180011b7b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011b80  and     qword ptr [rsi], 0
0x180011b84  cmp     r14, rbp
0x180011b87  jz      short loc_180011BAF
0x180011b89  cmp     qword ptr [r14], 0
0x180011b8d  jz      short loc_180011B97
0x180011b8f  mov     rcx, r14
0x180011b92  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011b97  mov     rcx, [rbp+0]
0x180011b9b  mov     [r14], rcx
0x180011b9e  test    rcx, rcx
0x180011ba1  jz      short loc_180011BAF
0x180011ba3  mov     rax, [rcx]
0x180011ba6  mov     rax, [rax+8]
0x180011baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011baf  cmp     rbx, r12
0x180011bb2  jz      short loc_180011BDB
0x180011bb4  cmp     qword ptr [rbx], 0
0x180011bb8  jz      short loc_180011BC2
0x180011bba  mov     rcx, rbx
0x180011bbd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011bc2  mov     rcx, [r12]
0x180011bc6  mov     [rbx], rcx
0x180011bc9  test    rcx, rcx
0x180011bcc  jz      short loc_180011BDB
0x180011bce  mov     rax, [rcx]
0x180011bd1  mov     rax, [rax+8]
0x180011bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bda  nop
0x180011bdb  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180011be2  mov     [r15], rax
0x180011be5  mov     rax, r15
0x180011be8  lea     r11, [rsp+88h+var_28]
0x180011bed  mov     rbx, [r11+38h]
0x180011bf1  mov     rbp, [r11+40h]
0x180011bf5  mov     rsp, r11
0x180011bf8  pop     r15
0x180011bfa  pop     r14
0x180011bfc  pop     r12
0x180011bfe  pop     rdi
0x180011bff  pop     rsi
0x180011c00  retn
0x180011c02  lea     rcx, [rsp+88h+var_40]
0x180011c07  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180011c0c  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180011c0f  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180011c14  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180011c19  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180011c20  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180011c25  call    _CxxThrowException_0
```
