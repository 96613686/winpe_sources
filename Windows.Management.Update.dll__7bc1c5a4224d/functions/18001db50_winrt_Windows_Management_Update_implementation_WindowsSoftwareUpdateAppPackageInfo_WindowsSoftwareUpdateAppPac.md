# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::WindowsSoftwareUpdateAppPackageInfo(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateArchitecture const &,winrt::Windows::Foundation::Uri const &)

- ea: `0x18001db50`
- end: `0x18001dd22`
- name: `??0WindowsSoftwareUpdateAppPackageInfo@implementation@Update@Management@Windows@winrt@@QEAA@AEBUhstring@5@AEBW4WindowsSoftwareUpdateArchitecture@2345@AEBUUri@Foundation@45@@Z`
- size: `466`
- prototype: `winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *__fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *this, winrt::impl **, const enum winrt::Windows::Management::Update::WindowsSoftwareUpdateArchitecture *, const struct winrt::Windows::Foundation::Uri *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012bf0`

## callees

- `0x18000340c`
- `0x180008653`
- `0x18000866b`
- `0x180011464`
- `0x1800114a8`
- `0x180014eb4`
- `0x180014ee0`
- `0x180016fe4`
- `0x180018238`
- `0x18001c8a0`
- `0x18001db50`
- `0x18001dd28`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001dc7b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001dc7b`

## string_xrefs

- `0x18001dcf1`: `PackageFamilyName for InstallationType AppPackage cannot be empty.`
- `0x18001dc8e`: `InstallUri for InstallationType AppPackage cannot be null.`

## pseudocode

```c
winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::WindowsSoftwareUpdateAppPackageInfo(
        winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *this,
        winrt::impl **a2,
        const enum winrt::Windows::Management::Update::WindowsSoftwareUpdateArchitecture *a3,
        const struct winrt::Windows::Foundation::Uri *a4)
{
  const struct winrt::Windows::Foundation::Uri *v8; // rdi
  __int64 v9; // rdx
  struct winrt::impl::hstring_header *v10; // rdx
  struct winrt::impl::hstring_header *v11; // r15
  volatile signed __int32 *v12; // rsi
  int v13; // ecx
  HANDLE ProcessHeap; // rax
  __int64 v15; // rcx
  const struct winrt::impl::slim_source_location *v17; // rbx
  const struct winrt::impl::slim_source_location *v18; // rax
  const struct winrt::impl::slim_source_location *v19; // rbx
  __int64 v20; // [rsp+20h] [rbp-60h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v22[24]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v23[40]; // [rsp+58h] [rbp-28h] BYREF

  *((_QWORD *)this + 2) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateAppPackageInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::`vftable';
  *((_QWORD *)this + 3) = 0;
  v8 = (winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v18 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v22, v9);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v18);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  if ( !*a2 )
  {
    v19 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v22, v9);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)v23,
      L"PackageFamilyName for InstallationType AppPackage cannot be empty.");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v23,
      v19);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  v20 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a4, &v20) )
  {
    v17 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v22, v10);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)v23,
      L"InstallUri for InstallationType AppPackage cannot be null.");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v23,
      v17);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  v11 = winrt::impl::duplicate_hstring(*a2, v10);
  v12 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v12 )
  {
    v13 = _InterlockedDecrement(v12 + 6);
    if ( v13 )
    {
      if ( v13 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v12);
    }
  }
  *((_QWORD *)this + 3) = v11;
  *((_DWORD *)this + 8) = *(_DWORD *)a3;
  if ( v8 != a4 )
  {
    if ( *(_QWORD *)v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
    v15 = *(_QWORD *)a4;
    *(_QWORD *)v8 = *(_QWORD *)a4;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  }
  return this;
}

```

## disassembly

```asm
0x18001db50  mov     [rsp-28h+arg_8], rbx
0x18001db55  mov     [rsp-28h+arg_10], rsi
0x18001db5a  mov     [rsp-28h+arg_0], rcx
0x18001db5f  push    rbp
0x18001db60  push    rdi
0x18001db61  push    r12
0x18001db63  push    r14
0x18001db65  push    r15
0x18001db67  mov     rbp, rsp
0x18001db6a  sub     rsp, 80h
0x18001db71  mov     r14, r9
0x18001db74  mov     r12, r8
0x18001db77  mov     rsi, rdx
0x18001db7a  mov     rbx, rcx
0x18001db7d  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateAppPackageInfo@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateAppPackageInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateAppPackageInfo>::`vftable'
0x18001db84  mov     [rcx+10h], rax
0x18001db88  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001db8f  mov     qword ptr [rcx+8], 1
0x18001db97  lea     rax, ??_7WindowsSoftwareUpdateAppPackageInfo@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::`vftable'
0x18001db9e  mov     [rcx], rax
0x18001dba1  mov     qword ptr [rcx+18h], 0
0x18001dba9  lea     rdi, [rcx+28h]
0x18001dbad  mov     qword ptr [rdi], 0
0x18001dbb4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18001dbbb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x18001dbc0  test    al, al
0x18001dbc2  jz      loc_18001DCBF
0x18001dbc8  cmp     qword ptr [rsi], 0
0x18001dbcc  jz      loc_18001DCE5
0x18001dbd2  mov     [rbp+var_60], 0
0x18001dbda  lea     rdx, [rbp+var_60]
0x18001dbde  mov     rcx, r14
0x18001dbe1  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001dbe6  test    al, al
0x18001dbe8  jnz     loc_18001DC82
0x18001dbee  mov     rcx, [rsi]; this
0x18001dbf1  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001dbf6  mov     r15, rax
0x18001dbf9  mov     rsi, [rbx+18h]
0x18001dbfd  test    rsi, rsi
0x18001dc00  jz      short loc_18001DC22
0x18001dc02  or      ecx, 0FFFFFFFFh
0x18001dc05  lock xadd [rsi+18h], ecx
0x18001dc0a  sub     ecx, 1
0x18001dc0d  jnz     short loc_18001DC77
0x18001dc0f  nop
0x18001dc10  call    WINRT_IMPL_GetProcessHeap
0x18001dc15  mov     rcx, rax; hHeap
0x18001dc18  mov     r8, rsi; lpMem
0x18001dc1b  xor     edx, edx; dwFlags
0x18001dc1d  call    WINRT_IMPL_HeapFree
0x18001dc22  mov     [rbx+18h], r15
0x18001dc26  mov     eax, [r12]
0x18001dc2a  mov     [rbx+20h], eax
0x18001dc2d  cmp     rdi, r14
0x18001dc30  jz      short loc_18001DC58
0x18001dc32  cmp     qword ptr [rdi], 0
0x18001dc36  jz      short loc_18001DC40
0x18001dc38  mov     rcx, rdi
0x18001dc3b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001dc40  mov     rcx, [r14]
0x18001dc43  mov     [rdi], rcx
0x18001dc46  test    rcx, rcx
0x18001dc49  jz      short loc_18001DC58
0x18001dc4b  mov     rax, [rcx]
0x18001dc4e  mov     rax, [rax+8]
0x18001dc52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc57  nop
0x18001dc58  mov     rax, rbx
0x18001dc5b  lea     r11, [rsp+80h+var_s0]
0x18001dc63  mov     rbx, [r11+38h]
0x18001dc67  mov     rsi, [r11+40h]
0x18001dc6b  mov     rsp, r11
0x18001dc6e  pop     r15
0x18001dc70  pop     r14
0x18001dc72  pop     r12
0x18001dc74  pop     rdi
0x18001dc75  pop     rbp
0x18001dc76  retn
0x18001dc77  test    ecx, ecx
0x18001dc79  jns     short loc_18001DC22
0x18001dc7b  call    cs:__imp_abort
0x18001dc82  lea     rcx, [rbp+var_40]
0x18001dc86  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001dc8b  mov     rbx, rax
0x18001dc8e  lea     rdx, aInstalluriForI; "InstallUri for InstallationType AppPack"...
0x18001dc95  lea     rcx, [rbp+var_28]; this
0x18001dc99  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001dc9e  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x18001dca1  lea     rdx, [rbp+var_28]; struct winrt::param::hstring *
0x18001dca5  lea     rcx, [rbp+pExceptionObject]; this
0x18001dca9  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18001dcae  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001dcb5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001dcb9  call    _CxxThrowException_0
0x18001dcbf  lea     rcx, [rbp+var_40]
0x18001dcc3  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001dcc8  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001dccb  lea     rcx, [rbp+pExceptionObject]; this
0x18001dccf  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18001dcd4  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001dcdb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001dcdf  call    _CxxThrowException_0
0x18001dce5  lea     rcx, [rbp+var_40]
0x18001dce9  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001dcee  mov     rbx, rax
0x18001dcf1  lea     rdx, aPackagefamilyn; "PackageFamilyName for InstallationType "...
0x18001dcf8  lea     rcx, [rbp+var_28]; this
0x18001dcfc  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001dd01  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x18001dd04  lea     rdx, [rbp+var_28]; struct winrt::param::hstring *
0x18001dd08  lea     rcx, [rbp+pExceptionObject]; this
0x18001dd0c  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18001dd11  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001dd18  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001dd1c  call    _CxxThrowException_0
```
