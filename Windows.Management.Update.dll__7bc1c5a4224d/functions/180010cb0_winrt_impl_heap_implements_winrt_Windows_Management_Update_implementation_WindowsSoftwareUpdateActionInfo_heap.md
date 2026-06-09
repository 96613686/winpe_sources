# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>(winrt::hstring const &,winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateActionType)

- ea: `0x180010cb0`
- end: `0x180010ddc`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUhstring@2@0W4WindowsSoftwareUpdateActionType@Update@Management@Windows@2@@Z`
- size: `300`
- prototype: `__int64 __fastcall(__int64, winrt::impl **, winrt::impl **, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180012b70`

## callees

- `0x18000340c`
- `0x180008653`
- `0x18000866b`
- `0x180010cb0`
- `0x1800114a8`
- `0x180014eb4`
- `0x180014ee0`
- `0x18001c8a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010dac`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010dac`

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
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v21[80]; // [rsp+38h] [rbp-50h] BYREF

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::`vftable';
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v19 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v21, v8);
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
        goto LABEL_11;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
    }
  }
  *(_QWORD *)(a1 + 24) = v10;
  v14 = winrt::impl::duplicate_hstring(*a3, v9);
  v15 = *(volatile signed __int32 **)(a1 + 32);
  if ( v15 )
  {
    v16 = _InterlockedDecrement(v15 + 6);
    if ( !v16 )
    {
      v17 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v17, 0, (LPVOID)v15);
      goto LABEL_9;
    }
    if ( v16 >= 0 )
      goto LABEL_9;
LABEL_11:
    abort();
  }
LABEL_9:
  *(_QWORD *)(a1 + 32) = v14;
  *(_DWORD *)(a1 + 40) = a4;
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180010cb0  mov     [rsp+arg_0], rcx
0x180010cb5  push    rbx
0x180010cb6  push    rbp
0x180010cb7  push    rsi
0x180010cb8  push    rdi
0x180010cb9  push    r14
0x180010cbb  push    r15
0x180010cbd  sub     rsp, 58h
0x180010cc1  mov     r14d, r9d
0x180010cc4  mov     r15, r8
0x180010cc7  mov     rdi, rdx
0x180010cca  mov     rbx, rcx
0x180010ccd  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateActionInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::`vftable'
0x180010cd4  mov     [rcx+10h], rax
0x180010cd8  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180010cdf  mov     qword ptr [rcx+8], 1
0x180010ce7  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::`vftable'
0x180010cee  mov     [rcx], rax
0x180010cf1  mov     qword ptr [rcx+18h], 0
0x180010cf9  mov     qword ptr [rcx+20h], 0
0x180010d01  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180010d08  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180010d0d  test    al, al
0x180010d0f  jz      loc_180010DB3
0x180010d15  mov     rcx, [rdi]; this
0x180010d18  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180010d1d  mov     rbp, rax
0x180010d20  mov     rdi, [rbx+18h]
0x180010d24  or      esi, 0FFFFFFFFh
0x180010d27  test    rdi, rdi
0x180010d2a  jz      short loc_180010D51
0x180010d2c  mov     ecx, esi
0x180010d2e  lock xadd [rdi+18h], ecx
0x180010d33  sub     ecx, 1
0x180010d36  jnz     short loc_180010D4D
0x180010d38  nop
0x180010d39  call    WINRT_IMPL_GetProcessHeap
0x180010d3e  mov     rcx, rax; hHeap
0x180010d41  mov     r8, rdi; lpMem
0x180010d44  xor     edx, edx; dwFlags
0x180010d46  call    WINRT_IMPL_HeapFree
0x180010d4b  jmp     short loc_180010D51
0x180010d4d  test    ecx, ecx
0x180010d4f  js      short loc_180010DAC
0x180010d51  mov     [rbx+18h], rbp
0x180010d55  mov     rcx, [r15]; this
0x180010d58  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180010d5d  mov     rbp, rax
0x180010d60  mov     rdi, [rbx+20h]
0x180010d64  test    rdi, rdi
0x180010d67  jz      short loc_180010D86
0x180010d69  lock xadd [rdi+18h], esi
0x180010d6e  sub     esi, 1
0x180010d71  jnz     short loc_180010DA8
0x180010d73  nop
0x180010d74  call    WINRT_IMPL_GetProcessHeap
0x180010d79  mov     rcx, rax; hHeap
0x180010d7c  mov     r8, rdi; lpMem
0x180010d7f  xor     edx, edx; dwFlags
0x180010d81  call    WINRT_IMPL_HeapFree
0x180010d86  mov     [rbx+20h], rbp
0x180010d8a  mov     [rbx+28h], r14d
0x180010d8e  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo>::`vftable'
0x180010d95  mov     [rbx], rax
0x180010d98  mov     rax, rbx
0x180010d9b  add     rsp, 58h
0x180010d9f  pop     r15
0x180010da1  pop     r14
0x180010da3  pop     rdi
0x180010da4  pop     rsi
0x180010da5  pop     rbp
0x180010da6  pop     rbx
0x180010da7  retn
0x180010da8  test    esi, esi
0x180010daa  jns     short loc_180010D86
0x180010dac  call    cs:__imp_abort
0x180010db3  lea     rcx, [rsp+88h+var_50]
0x180010db8  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180010dbd  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180010dc0  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180010dc5  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180010dca  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180010dd1  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180010dd6  call    _CxxThrowException_0
```
