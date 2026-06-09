# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>(winrt::hstring const &,winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateActionType)

- ea: `0x1800117f0`
- end: `0x18001194e`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUhstring@2@0W4WindowsSoftwareUpdateActionType@Update@Management@Windows@2@@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180013750`

## callees

- `0x1800035f0`
- `0x180008bf4`
- `0x180008c0c`
- `0x1800117f0`
- `0x18001203c`
- `0x180015ac0`
- `0x180015ae8`
- `0x18001db60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011907`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011918`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011907`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011918`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>(
        __int64 a1,
        winrt::impl **a2,
        winrt::impl **a3,
        int a4)
{
  struct winrt::impl::hstring_header *v8; // rdx
  struct winrt::impl::hstring_header *v9; // rdx
  struct winrt::impl::hstring_header *v10; // rbp
  volatile signed __int32 *v11; // rdi
  int v12; // ecx
  HANDLE ProcessHeap; // rax
  struct winrt::impl::hstring_header *v14; // rbp
  volatile signed __int32 *v15; // rdi
  int v16; // esi
  HANDLE v17; // rax
  const struct winrt::impl::slim_source_location *v19; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v21[24]; // [rsp+38h] [rbp-30h] BYREF

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::`vftable';
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v19 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v21);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v19);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  v10 = winrt::impl::duplicate_hstring(*a2, v8);
  v11 = *(volatile signed __int32 **)(a1 + 24);
  if ( v11 )
  {
    v12 = _InterlockedDecrement(v11 + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
    }
    *(_QWORD *)(a1 + 24) = 0;
  }
  *(_QWORD *)(a1 + 24) = v10;
  v14 = winrt::impl::duplicate_hstring(*a3, v9);
  v15 = *(volatile signed __int32 **)(a1 + 32);
  if ( v15 )
  {
    v16 = _InterlockedDecrement(v15 + 6);
    if ( v16 )
    {
      if ( v16 < 0 )
        abort();
    }
    else
    {
      v17 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v17, 0, (LPVOID)v15);
    }
    *(_QWORD *)(a1 + 32) = 0;
  }
  *(_QWORD *)(a1 + 32) = v14;
  *(_DWORD *)(a1 + 40) = a4;
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x1800117f0  mov     rax, rsp
0x1800117f3  mov     [rax+10h], rbx
0x1800117f7  mov     [rax+18h], rbp
0x1800117fb  mov     [rax+20h], rsi
0x1800117ff  mov     [rax+8], rcx
0x180011803  push    rdi
0x180011804  push    r14
0x180011806  push    r15
0x180011808  sub     rsp, 50h
0x18001180c  mov     r14d, r9d
0x18001180f  mov     r15, r8
0x180011812  mov     rdi, rdx
0x180011815  mov     rbx, rcx
0x180011818  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateActionInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::`vftable'
0x18001181f  mov     [rcx+10h], rax
0x180011823  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001182a  mov     qword ptr [rcx+8], 1
0x180011832  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::`vftable'
0x180011839  mov     [rcx], rax
0x18001183c  and     qword ptr [rcx+18h], 0
0x180011841  and     qword ptr [rcx+20h], 0
0x180011846  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001184d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180011852  test    al, al
0x180011854  jz      loc_180011925
0x18001185a  mov     rcx, [rdi]; this
0x18001185d  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180011862  mov     rbp, rax
0x180011865  mov     rdi, [rbx+18h]
0x180011869  or      esi, 0FFFFFFFFh
0x18001186c  test    rdi, rdi
0x18001186f  jz      short loc_180011899
0x180011871  mov     ecx, esi
0x180011873  lock xadd [rdi+18h], ecx
0x180011878  sub     ecx, 1
0x18001187b  jnz     loc_180011903
0x180011881  nop
0x180011882  call    WINRT_IMPL_GetProcessHeap
0x180011887  mov     rcx, rax; hHeap
0x18001188a  mov     r8, rdi; lpMem
0x18001188d  xor     edx, edx; dwFlags
0x18001188f  call    WINRT_IMPL_HeapFree
0x180011894  and     qword ptr [rbx+18h], 0
0x180011899  mov     [rbx+18h], rbp
0x18001189d  mov     rcx, [r15]; this
0x1800118a0  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800118a5  mov     rbp, rax
0x1800118a8  mov     rdi, [rbx+20h]
0x1800118ac  test    rdi, rdi
0x1800118af  jz      short loc_1800118D3
0x1800118b1  lock xadd [rdi+18h], esi
0x1800118b6  sub     esi, 1
0x1800118b9  jnz     short loc_180011914
0x1800118bb  nop
0x1800118bc  call    WINRT_IMPL_GetProcessHeap
0x1800118c1  mov     rcx, rax; hHeap
0x1800118c4  mov     r8, rdi; lpMem
0x1800118c7  xor     edx, edx; dwFlags
0x1800118c9  call    WINRT_IMPL_HeapFree
0x1800118ce  and     qword ptr [rbx+20h], 0
0x1800118d3  mov     [rbx+20h], rbp
0x1800118d7  mov     [rbx+28h], r14d
0x1800118db  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::`vftable'
0x1800118e2  mov     [rbx], rax
0x1800118e5  mov     rax, rbx
0x1800118e8  lea     r11, [rsp+68h+var_18]
0x1800118ed  mov     rbx, [r11+28h]
0x1800118f1  mov     rbp, [r11+30h]
0x1800118f5  mov     rsi, [r11+38h]
0x1800118f9  mov     rsp, r11
0x1800118fc  pop     r15
0x1800118fe  pop     r14
0x180011900  pop     rdi
0x180011901  retn
0x180011903  test    ecx, ecx
0x180011905  jns     short loc_180011894
0x180011907  call    cs:__imp_abort
0x180011914  test    esi, esi
0x180011916  jns     short loc_1800118CE
0x180011918  call    cs:__imp_abort
0x180011925  lea     rcx, [rsp+68h+var_30]
0x18001192a  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001192f  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180011932  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180011937  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001193c  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180011943  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180011948  call    _CxxThrowException_0
```
