# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>(uint,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &)

- ea: `0x1800110c0`
- end: `0x18001122c`
- name: `??0?$heap_implements@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@IAEBUhstring@2@0AEBUUri@Foundation@Windows@2@@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64, int, winrt::impl **, winrt::impl **, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012de0`

## callees

- `0x18000340c`
- `0x180008653`
- `0x18000866b`
- `0x1800110c0`
- `0x1800114a8`
- `0x180014eb4`
- `0x180014ee0`
- `0x180016fe4`
- `0x18001c8a0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800111fc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800111fc`

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
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v24[80]; // [rsp+38h] [rbp-50h] BYREF

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
    v22 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v24, v10);
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
        goto LABEL_16;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v13);
    }
  }
  *(_QWORD *)(a1 + 32) = v12;
  v16 = winrt::impl::duplicate_hstring(*a4, v11);
  v17 = *(volatile signed __int32 **)(a1 + 40);
  if ( !v17 )
    goto LABEL_9;
  v18 = _InterlockedDecrement(v17 + 6);
  if ( !v18 )
  {
    v19 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
    goto LABEL_9;
  }
  if ( v18 < 0 )
LABEL_16:
    abort();
LABEL_9:
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
0x1800110c0  mov     [rsp+arg_0], rcx
0x1800110c5  push    rbx
0x1800110c6  push    rbp
0x1800110c7  push    rsi
0x1800110c8  push    rdi
0x1800110c9  push    r14
0x1800110cb  push    r15
0x1800110cd  sub     rsp, 58h
0x1800110d1  mov     r15, r9
0x1800110d4  mov     rsi, r8
0x1800110d7  mov     ebp, edx
0x1800110d9  mov     rbx, rcx
0x1800110dc  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateLocalizationInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::`vftable'
0x1800110e3  mov     [rcx+10h], rax
0x1800110e7  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800110ee  mov     qword ptr [rcx+8], 1
0x1800110f6  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable'
0x1800110fd  mov     [rcx], rax
0x180011100  mov     qword ptr [rcx+20h], 0
0x180011108  mov     qword ptr [rcx+28h], 0
0x180011110  lea     rdi, [rcx+30h]
0x180011114  mov     qword ptr [rdi], 0
0x18001111b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180011122  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180011127  test    al, al
0x180011129  jz      loc_180011203
0x18001112f  mov     [rbx+18h], ebp
0x180011132  mov     rcx, [rsi]; this
0x180011135  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001113a  mov     r14, rax
0x18001113d  mov     rsi, [rbx+20h]
0x180011141  or      ebp, 0FFFFFFFFh
0x180011144  test    rsi, rsi
0x180011147  jz      short loc_180011172
0x180011149  mov     ecx, ebp
0x18001114b  lock xadd [rsi+18h], ecx
0x180011150  sub     ecx, 1
0x180011153  jnz     short loc_18001116A
0x180011155  nop
0x180011156  call    WINRT_IMPL_GetProcessHeap
0x18001115b  mov     rcx, rax; hHeap
0x18001115e  mov     r8, rsi; lpMem
0x180011161  xor     edx, edx; dwFlags
0x180011163  call    WINRT_IMPL_HeapFree
0x180011168  jmp     short loc_180011172
0x18001116a  test    ecx, ecx
0x18001116c  js      loc_1800111FC
0x180011172  mov     [rbx+20h], r14
0x180011176  mov     rcx, [r15]; this
0x180011179  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001117e  mov     r14, rax
0x180011181  mov     rsi, [rbx+28h]
0x180011185  test    rsi, rsi
0x180011188  jz      short loc_1800111A7
0x18001118a  lock xadd [rsi+18h], ebp
0x18001118f  sub     ebp, 1
0x180011192  jnz     short loc_1800111F8
0x180011194  nop
0x180011195  call    WINRT_IMPL_GetProcessHeap
0x18001119a  mov     rcx, rax; hHeap
0x18001119d  mov     r8, rsi; lpMem
0x1800111a0  xor     edx, edx; dwFlags
0x1800111a2  call    WINRT_IMPL_HeapFree
0x1800111a7  mov     [rbx+28h], r14
0x1800111ab  mov     rsi, [rsp+88h+arg_20]
0x1800111b3  cmp     rdi, rsi
0x1800111b6  jz      short loc_1800111DE
0x1800111b8  cmp     qword ptr [rdi], 0
0x1800111bc  jz      short loc_1800111C6
0x1800111be  mov     rcx, rdi
0x1800111c1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800111c6  mov     rcx, [rsi]
0x1800111c9  mov     [rdi], rcx
0x1800111cc  test    rcx, rcx
0x1800111cf  jz      short loc_1800111DE
0x1800111d1  mov     rax, [rcx]
0x1800111d4  mov     rax, [rax+8]
0x1800111d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111dd  nop
0x1800111de  lea     rax, ??_7?$heap_implements@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable'
0x1800111e5  mov     [rbx], rax
0x1800111e8  mov     rax, rbx
0x1800111eb  add     rsp, 58h
0x1800111ef  pop     r15
0x1800111f1  pop     r14
0x1800111f3  pop     rdi
0x1800111f4  pop     rsi
0x1800111f5  pop     rbp
0x1800111f6  pop     rbx
0x1800111f7  retn
0x1800111f8  test    ebp, ebp
0x1800111fa  jns     short loc_1800111A7
0x1800111fc  call    cs:__imp_abort
0x180011203  lea     rcx, [rsp+88h+var_50]
0x180011208  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001120d  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180011210  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180011215  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001121a  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180011221  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180011226  call    _CxxThrowException_0
```
