# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>(uint,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &)

- ea: `0x180011c34`
- end: `0x180011dd3`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@IAEBUhstring@2@0AEBUUri@Foundation@Windows@2@@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800139c0`

## callees

- `0x1800035f0`
- `0x180008bf4`
- `0x180008c0c`
- `0x180011c34`
- `0x18001203c`
- `0x180015ac0`
- `0x180015ae8`
- `0x180017c3c`
- `0x18001db60`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011d8c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011d9d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011d8c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011d9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>(
        __int64 a1,
        int a2,
        winrt::impl **a3,
        winrt::impl **a4,
        __int64 *a5)
{
  __int64 *v9; // rdi
  struct winrt::impl::hstring_header *v10; // rdx
  struct winrt::impl::hstring_header *v11; // rdx
  struct winrt::impl::hstring_header *v12; // r14
  volatile signed __int32 *v13; // rsi
  int v14; // ecx
  HANDLE ProcessHeap; // rax
  struct winrt::impl::hstring_header *v16; // r14
  volatile signed __int32 *v17; // rsi
  int v18; // ebp
  HANDLE v19; // rax
  __int64 v20; // rcx
  const struct winrt::impl::slim_source_location *v22; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v24[24]; // [rsp+38h] [rbp-30h] BYREF

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable';
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  v9 = (__int64 *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v22 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v24);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v22);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  *(_DWORD *)(a1 + 24) = a2;
  v12 = winrt::impl::duplicate_hstring(*a3, v10);
  v13 = *(volatile signed __int32 **)(a1 + 32);
  if ( v13 )
  {
    v14 = _InterlockedDecrement(v13 + 6);
    if ( v14 )
    {
      if ( v14 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v13);
    }
    *(_QWORD *)(a1 + 32) = 0;
  }
  *(_QWORD *)(a1 + 32) = v12;
  v16 = winrt::impl::duplicate_hstring(*a4, v11);
  v17 = *(volatile signed __int32 **)(a1 + 40);
  if ( v17 )
  {
    v18 = _InterlockedDecrement(v17 + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        abort();
    }
    else
    {
      v19 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
  *(_QWORD *)(a1 + 40) = v16;
  if ( v9 != a5 )
  {
    if ( *v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
    v20 = *a5;
    *v9 = *a5;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  }
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180011c34  mov     rax, rsp
0x180011c37  mov     [rax+10h], rbx
0x180011c3b  mov     [rax+18h], rbp
0x180011c3f  mov     [rax+20h], rsi
0x180011c43  mov     [rax+8], rcx
0x180011c47  push    rdi
0x180011c48  push    r14
0x180011c4a  push    r15
0x180011c4c  sub     rsp, 50h
0x180011c50  mov     r15, r9
0x180011c53  mov     rsi, r8
0x180011c56  mov     ebp, edx
0x180011c58  mov     rbx, rcx
0x180011c5b  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateLocalizationInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::`vftable'
0x180011c62  mov     [rcx+10h], rax
0x180011c66  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011c6d  mov     qword ptr [rcx+8], 1
0x180011c75  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable'
0x180011c7c  mov     [rcx], rax
0x180011c7f  and     qword ptr [rcx+20h], 0
0x180011c84  and     qword ptr [rcx+28h], 0
0x180011c89  lea     rdi, [rcx+30h]
0x180011c8d  and     qword ptr [rdi], 0
0x180011c91  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180011c98  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180011c9d  test    al, al
0x180011c9f  jz      loc_180011DAA
0x180011ca5  mov     [rbx+18h], ebp
0x180011ca8  mov     rcx, [rsi]; this
0x180011cab  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180011cb0  mov     r14, rax
0x180011cb3  mov     rsi, [rbx+20h]
0x180011cb7  or      ebp, 0FFFFFFFFh
0x180011cba  test    rsi, rsi
0x180011cbd  jz      short loc_180011CE7
0x180011cbf  mov     ecx, ebp
0x180011cc1  lock xadd [rsi+18h], ecx
0x180011cc6  sub     ecx, 1
0x180011cc9  jnz     loc_180011D84
0x180011ccf  nop
0x180011cd0  call    WINRT_IMPL_GetProcessHeap
0x180011cd5  mov     rcx, rax; hHeap
0x180011cd8  mov     r8, rsi; lpMem
0x180011cdb  xor     edx, edx; dwFlags
0x180011cdd  call    WINRT_IMPL_HeapFree
0x180011ce2  and     qword ptr [rbx+20h], 0
0x180011ce7  mov     [rbx+20h], r14
0x180011ceb  mov     rcx, [r15]; this
0x180011cee  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180011cf3  mov     r14, rax
0x180011cf6  mov     rsi, [rbx+28h]
0x180011cfa  test    rsi, rsi
0x180011cfd  jz      short loc_180011D25
0x180011cff  lock xadd [rsi+18h], ebp
0x180011d04  sub     ebp, 1
0x180011d07  jnz     loc_180011D99
0x180011d0d  nop
0x180011d0e  call    WINRT_IMPL_GetProcessHeap
0x180011d13  mov     rcx, rax; hHeap
0x180011d16  mov     r8, rsi; lpMem
0x180011d19  xor     edx, edx; dwFlags
0x180011d1b  call    WINRT_IMPL_HeapFree
0x180011d20  and     qword ptr [rbx+28h], 0
0x180011d25  mov     [rbx+28h], r14
0x180011d29  mov     rsi, [rsp+68h+arg_20]
0x180011d31  cmp     rdi, rsi
0x180011d34  jz      short loc_180011D5C
0x180011d36  cmp     qword ptr [rdi], 0
0x180011d3a  jz      short loc_180011D44
0x180011d3c  mov     rcx, rdi
0x180011d3f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011d44  mov     rcx, [rsi]
0x180011d47  mov     [rdi], rcx
0x180011d4a  test    rcx, rcx
0x180011d4d  jz      short loc_180011D5C
0x180011d4f  mov     rax, [rcx]
0x180011d52  mov     rax, [rax+8]
0x180011d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d5b  nop
0x180011d5c  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable'
0x180011d63  mov     [rbx], rax
0x180011d66  mov     rax, rbx
0x180011d69  lea     r11, [rsp+68h+var_18]
0x180011d6e  mov     rbx, [r11+28h]
0x180011d72  mov     rbp, [r11+30h]
0x180011d76  mov     rsi, [r11+38h]
0x180011d7a  mov     rsp, r11
0x180011d7d  pop     r15
0x180011d7f  pop     r14
0x180011d81  pop     rdi
0x180011d82  retn
0x180011d84  test    ecx, ecx
0x180011d86  jns     loc_180011CE2
0x180011d8c  call    cs:__imp_abort
0x180011d99  test    ebp, ebp
0x180011d9b  jns     short loc_180011D20
0x180011d9d  call    cs:__imp_abort
0x180011daa  lea     rcx, [rsp+68h+var_30]
0x180011daf  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180011db4  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180011db7  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180011dbc  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180011dc1  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180011dc8  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180011dcd  call    _CxxThrowException_0
```
