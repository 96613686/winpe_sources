# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::WindowsSoftwareUpdateAppPackageInfo(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateArchitecture const &,winrt::Windows::Foundation::Uri const &)

- ea: `0x18001ede0`
- end: `0x18001efb5`
- name: `??0WindowsSoftwareUpdateAppPackageInfo@implementation@Update@Management@Windows@winrt@@QEAA@AEBUhstring@5@AEBW4WindowsSoftwareUpdateArchitecture@2345@AEBUUri@Foundation@45@@Z`
- size: `469`
- prototype: `__int64 __fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *__hidden this, const struct winrt::hstring *, const enum winrt::Windows::Management::Update::WindowsSoftwareUpdateArchitecture *, const struct winrt::Windows::Foundation::Uri *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800137d0`

## callees

- `0x1800035f0`
- `0x180008bf4`
- `0x180008c0c`
- `0x180011ffc`
- `0x18001203c`
- `0x180015ac0`
- `0x180015ae8`
- `0x180017c3c`
- `0x180018f10`
- `0x18001db60`
- `0x18001ede0`
- `0x18001efbc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ef08`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ef08`

## string_xrefs

- `0x18001ef84`: `PackageFamilyName for InstallationType AppPackage cannot be empty.`
- `0x18001ef21`: `InstallUri for InstallationType AppPackage cannot be null.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::WindowsSoftwareUpdateAppPackageInfo(
        winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *this,
        winrt::impl **a2,
        const enum winrt::Windows::Management::Update::WindowsSoftwareUpdateArchitecture *a3,
        const struct winrt::Windows::Foundation::Uri *a4)
{
  const struct winrt::Windows::Foundation::Uri *v8; // rdi
  struct winrt::impl::hstring_header *v9; // rdx
  struct winrt::impl::hstring_header *v10; // r15
  volatile signed __int32 *v11; // rsi
  int v12; // ecx
  HANDLE ProcessHeap; // rax
  __int64 v14; // rcx
  const struct winrt::impl::slim_source_location *v16; // rbx
  const struct winrt::impl::slim_source_location *v17; // rax
  const struct winrt::impl::slim_source_location *v18; // rbx
  __int64 v19; // [rsp+20h] [rbp-60h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v21[24]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v22[40]; // [rsp+58h] [rbp-28h] BYREF

  *((_QWORD *)this + 2) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateAppPackageInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::`vftable';
  *((_QWORD *)this + 3) = 0;
  v8 = (winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v17 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v21);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v17);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  if ( !*a2 )
  {
    v18 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v21);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)v22,
      L"PackageFamilyName for InstallationType AppPackage cannot be empty.");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v22,
      v18);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  v19 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a4, &v19) )
  {
    v16 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v21);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)v22,
      L"InstallUri for InstallationType AppPackage cannot be null.");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v22,
      v16);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  v10 = winrt::impl::duplicate_hstring(*a2, v9);
  v11 = (volatile signed __int32 *)*((_QWORD *)this + 3);
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
    *((_QWORD *)this + 3) = 0;
  }
  *((_QWORD *)this + 3) = v10;
  *((_DWORD *)this + 8) = *(_DWORD *)a3;
  if ( v8 != a4 )
  {
    if ( *(_QWORD *)v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
    v14 = *(_QWORD *)a4;
    *(_QWORD *)v8 = *(_QWORD *)a4;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  }
  return this;
}

```

## disassembly

```asm
0x18001ede0  mov     [rsp-28h+arg_8], rbx
0x18001ede5  mov     [rsp-28h+arg_10], rsi
0x18001edea  mov     [rsp-28h+arg_0], rcx
0x18001edef  push    rbp
0x18001edf0  push    rdi
0x18001edf1  push    r12
0x18001edf3  push    r14
0x18001edf5  push    r15
0x18001edf7  mov     rbp, rsp
0x18001edfa  sub     rsp, 80h
0x18001ee01  mov     r14, r9
0x18001ee04  mov     r12, r8
0x18001ee07  mov     rsi, rdx
0x18001ee0a  mov     rbx, rcx
0x18001ee0d  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateAppPackageInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateAppPackageInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateAppPackageInfo>::`vftable'
0x18001ee14  mov     [rcx+10h], rax
0x18001ee18  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001ee1f  mov     qword ptr [rcx+8], 1
0x18001ee27  lea     rax, ??_7WindowsSoftwareUpdateAppPackageInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::`vftable'
0x18001ee2e  mov     [rcx], rax
0x18001ee31  and     qword ptr [rcx+18h], 0
0x18001ee36  lea     rdi, [rcx+28h]
0x18001ee3a  and     qword ptr [rdi], 0
0x18001ee3e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001ee45  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001ee4a  test    al, al
0x18001ee4c  jz      loc_18001EF52
0x18001ee52  cmp     qword ptr [rsi], 0
0x18001ee56  jz      loc_18001EF78
0x18001ee5c  and     [rbp+var_60], 0
0x18001ee61  lea     rdx, [rbp+var_60]
0x18001ee65  mov     rcx, r14
0x18001ee68  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001ee6d  test    al, al
0x18001ee6f  jnz     loc_18001EF15
0x18001ee75  mov     rcx, [rsi]; this
0x18001ee78  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001ee7d  mov     r15, rax
0x18001ee80  mov     rsi, [rbx+18h]
0x18001ee84  test    rsi, rsi
0x18001ee87  jz      short loc_18001EEAE
0x18001ee89  or      ecx, 0FFFFFFFFh
0x18001ee8c  lock xadd [rsi+18h], ecx
0x18001ee91  sub     ecx, 1
0x18001ee94  jnz     short loc_18001EF04
0x18001ee96  nop
0x18001ee97  call    WINRT_IMPL_GetProcessHeap
0x18001ee9c  mov     rcx, rax; hHeap
0x18001ee9f  mov     r8, rsi; lpMem
0x18001eea2  xor     edx, edx; dwFlags
0x18001eea4  call    WINRT_IMPL_HeapFree
0x18001eea9  and     qword ptr [rbx+18h], 0
0x18001eeae  mov     [rbx+18h], r15
0x18001eeb2  mov     eax, [r12]
0x18001eeb6  mov     [rbx+20h], eax
0x18001eeb9  cmp     rdi, r14
0x18001eebc  jz      short loc_18001EEE4
0x18001eebe  cmp     qword ptr [rdi], 0
0x18001eec2  jz      short loc_18001EECC
0x18001eec4  mov     rcx, rdi
0x18001eec7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001eecc  mov     rcx, [r14]
0x18001eecf  mov     [rdi], rcx
0x18001eed2  test    rcx, rcx
0x18001eed5  jz      short loc_18001EEE4
0x18001eed7  mov     rax, [rcx]
0x18001eeda  mov     rax, [rax+8]
0x18001eede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eee3  nop
0x18001eee4  mov     rax, rbx
0x18001eee7  lea     r11, [rsp+80h+var_s0]
0x18001eeef  mov     rbx, [r11+38h]
0x18001eef3  mov     rsi, [r11+40h]
0x18001eef7  mov     rsp, r11
0x18001eefa  pop     r15
0x18001eefc  pop     r14
0x18001eefe  pop     r12
0x18001ef00  pop     rdi
0x18001ef01  pop     rbp
0x18001ef02  retn
0x18001ef04  test    ecx, ecx
0x18001ef06  jns     short loc_18001EEA9
0x18001ef08  call    cs:__imp_abort
0x18001ef15  lea     rcx, [rbp+var_40]
0x18001ef19  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001ef1e  mov     rbx, rax
0x18001ef21  lea     rdx, aInstalluriForI; "InstallUri for InstallationType AppPack"...
0x18001ef28  lea     rcx, [rbp+var_28]; this
0x18001ef2c  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001ef31  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x18001ef34  lea     rdx, [rbp+var_28]; struct winrt::param::hstring *
0x18001ef38  lea     rcx, [rbp+pExceptionObject]; this
0x18001ef3c  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18001ef41  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001ef48  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001ef4c  call    _CxxThrowException_0
0x18001ef52  lea     rcx, [rbp+var_40]
0x18001ef56  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001ef5b  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001ef5e  lea     rcx, [rbp+pExceptionObject]; this
0x18001ef62  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001ef67  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001ef6e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001ef72  call    _CxxThrowException_0
0x18001ef78  lea     rcx, [rbp+var_40]
0x18001ef7c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001ef81  mov     rbx, rax
0x18001ef84  lea     rdx, aPackagefamilyn; "PackageFamilyName for InstallationType "...
0x18001ef8b  lea     rcx, [rbp+var_28]; this
0x18001ef8f  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001ef94  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x18001ef97  lea     rdx, [rbp+var_28]; struct winrt::param::hstring *
0x18001ef9b  lea     rcx, [rbp+pExceptionObject]; this
0x18001ef9f  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18001efa4  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001efab  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001efaf  call    _CxxThrowException_0
```
