# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>(winrt::Windows::Management::Update::WindowsSoftwareUpdateActionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalActionInfo const &)

- ea: `0x180010f4c`
- end: `0x1800110b8`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUWindowsSoftwareUpdateActionInfo@Update@Management@Windows@2@AEBUWindowsSoftwareUpdateOptionalActionInfo@4562@@Z`
- size: `364`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800126d0`

## callees

- `0x18000340c`
- `0x180010f4c`
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
        __int64 *a3)
{
  char *v6; // rsi
  char *v7; // r15
  __int64 *v8; // r14
  __int64 *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  const struct winrt::impl::slim_source_location *v14; // rax
  char v15; // [rsp+20h] [rbp-68h] BYREF
  char v16; // [rsp+28h] [rbp-60h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v18[24]; // [rsp+48h] [rbp-40h] BYREF

  a1[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
  v6 = (char *)(a1 + 3);
  a1[3] = 0;
  v7 = (char *)(a1 + 4);
  a1[4] = 0;
  v8 = a1 + 5;
  a1[5] = 0;
  v9 = a1 + 6;
  a1[6] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v14 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v18, v10);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v14);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  if ( v6 != &v15 )
  {
    if ( *(_QWORD *)v6 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v6);
    *(_QWORD *)v6 = 0;
  }
  if ( v7 != &v16 )
  {
    if ( *(_QWORD *)v7 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
    *(_QWORD *)v7 = 0;
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
  *a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180010f4c  mov     [rsp+arg_8], rbx
0x180010f51  mov     [rsp+arg_10], rbp
0x180010f56  mov     [rsp+arg_0], rcx
0x180010f5b  push    rsi
0x180010f5c  push    rdi
0x180010f5d  push    r12
0x180010f5f  push    r14
0x180010f61  push    r15
0x180010f63  sub     rsp, 60h
0x180010f67  mov     rbp, r8
0x180010f6a  mov     r12, rdx
0x180010f6d  mov     rdi, rcx
0x180010f70  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateExecutionInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180010f77  mov     [rcx+10h], rax
0x180010f7b  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180010f82  mov     qword ptr [rcx+8], 1
0x180010f8a  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180010f91  mov     [rcx], rax
0x180010f94  lea     rsi, [rcx+18h]
0x180010f98  mov     qword ptr [rsi], 0
0x180010f9f  lea     r15, [rcx+20h]
0x180010fa3  mov     qword ptr [r15], 0
0x180010faa  lea     r14, [rcx+28h]
0x180010fae  mov     qword ptr [r14], 0
0x180010fb5  lea     rbx, [rcx+30h]
0x180010fb9  mov     qword ptr [rbx], 0
0x180010fc0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180010fc7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180010fcc  test    al, al
0x180010fce  jz      loc_18001108F
0x180010fd4  lea     rax, [rsp+88h+var_68]
0x180010fd9  cmp     rsi, rax
0x180010fdc  jz      short loc_180010FF3
0x180010fde  cmp     qword ptr [rsi], 0
0x180010fe2  jz      short loc_180010FEC
0x180010fe4  mov     rcx, rsi
0x180010fe7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010fec  mov     qword ptr [rsi], 0
0x180010ff3  lea     rax, [rsp+88h+var_60]
0x180010ff8  cmp     r15, rax
0x180010ffb  jz      short loc_180011012
0x180010ffd  cmp     qword ptr [r15], 0
0x180011001  jz      short loc_18001100B
0x180011003  mov     rcx, r15
0x180011006  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001100b  mov     qword ptr [r15], 0
0x180011012  cmp     r14, r12
0x180011015  jz      short loc_18001103D
0x180011017  cmp     qword ptr [r14], 0
0x18001101b  jz      short loc_180011025
0x18001101d  mov     rcx, r14
0x180011020  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011025  mov     rcx, [r12]
0x180011029  mov     [r14], rcx
0x18001102c  test    rcx, rcx
0x18001102f  jz      short loc_18001103D
0x180011031  mov     rax, [rcx]
0x180011034  mov     rax, [rax+8]
0x180011038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001103d  cmp     rbx, rbp
0x180011040  jz      short loc_180011069
0x180011042  cmp     qword ptr [rbx], 0
0x180011046  jz      short loc_180011050
0x180011048  mov     rcx, rbx
0x18001104b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011050  mov     rcx, [rbp+0]
0x180011054  mov     [rbx], rcx
0x180011057  test    rcx, rcx
0x18001105a  jz      short loc_180011069
0x18001105c  mov     rax, [rcx]
0x18001105f  mov     rax, [rax+8]
0x180011063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011068  nop
0x180011069  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable'
0x180011070  mov     [rdi], rax
0x180011073  mov     rax, rdi
0x180011076  lea     r11, [rsp+88h+var_28]
0x18001107b  mov     rbx, [r11+38h]
0x18001107f  mov     rbp, [r11+40h]
0x180011083  mov     rsp, r11
0x180011086  pop     r15
0x180011088  pop     r14
0x18001108a  pop     r12
0x18001108c  pop     rdi
0x18001108d  pop     rsi
0x18001108e  retn
0x18001108f  lea     rcx, [rsp+88h+var_40]
0x180011094  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180011099  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001109c  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800110a1  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800110a6  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800110ad  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800110b2  call    _CxxThrowException_0
```
