# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus::WindowsSoftwareUpdateProviderStatus(winrt::hstring const &)

- ea: `0x180024600`
- end: `0x180024823`
- name: `??0WindowsSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@QEAA@AEBUhstring@5@@Z`
- size: `547`
- prototype: `winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus *__fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus *this, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013dd0`

## callees

- `0x180002880`
- `0x1800035f0`
- `0x180008bf4`
- `0x180008c0c`
- `0x180011ffc`
- `0x18001203c`
- `0x180012078`
- `0x180015ac0`
- `0x180017c3c`
- `0x1800188d4`
- `0x180018f10`
- `0x18001da30`
- `0x18001db60`
- `0x180024600`
- `0x18002485c`
- `0x18002499c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024776`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024776`

## string_xrefs

- `0x18002468b`: `USO_PROVIDERSTATUS_PROVIDERTOKEN`
- `0x18002478f`: `providerToken cannot be empty`

## pseudocode

```c
winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus::WindowsSoftwareUpdateProviderStatus(
        winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus *this,
        const struct winrt::hstring *a2)
{
  __int64 *v4; // rbx
  __int64 EnvironmentVariableString; // rax
  const unsigned __int16 *v6; // rdx
  __int64 *SoftwareUpdateProviderStatus; // rdi
  __int64 v8; // rcx
  int v9; // ecx
  HANDLE ProcessHeap; // rax
  const struct winrt::impl::slim_source_location *v12; // rbx
  const struct winrt::impl::slim_source_location *v13; // rax
  const struct winrt::impl::slim_source_location *v14; // rbx
  LPVOID lpMem; // [rsp+20h] [rbp-69h] BYREF
  __int64 v16; // [rsp+28h] [rbp-61h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-59h] BYREF
  winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus *v18; // [rsp+48h] [rbp-41h]
  _BYTE v19[24]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v20[32]; // [rsp+68h] [rbp-21h] BYREF
  _OWORD v21[2]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v22[32]; // [rsp+A8h] [rbp+1Fh] BYREF

  v18 = this;
  *((_QWORD *)this + 2) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderStatus>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus::`vftable';
  v4 = (__int64 *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v19);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v13);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  if ( !*(_QWORD *)a2 )
  {
    v14 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v19);
    winrt::param::hstring::hstring((winrt::param::hstring *)v20, L"providerId cannot be empty");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v20,
      v14);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  memset(v21, 0, sizeof(v21));
  std::wstring::_Construct<1,unsigned short const *>(v21, L"USO_PROVIDERSTATUS_PROVIDERTOKEN", 32);
  EnvironmentVariableString = GetEnvironmentVariableString((__int64)v22, (const WCHAR *)v21);
  v6 = (const unsigned __int16 *)EnvironmentVariableString;
  if ( *(_QWORD *)(EnvironmentVariableString + 24) > 7u )
    v6 = *(const unsigned __int16 **)EnvironmentVariableString;
  winrt::hstring::hstring((winrt::hstring *)&lpMem, v6, *(_DWORD *)(EnvironmentVariableString + 16));
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(v21);
  if ( !lpMem )
  {
    v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v19);
    winrt::param::hstring::hstring((winrt::param::hstring *)v20, L"providerToken cannot be empty");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v20,
      v12);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  SoftwareUpdateProviderStatus = (__int64 *)winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProviderStatus(
                                              &v16,
                                              a2,
                                              &lpMem);
  if ( v4 != SoftwareUpdateProviderStatus )
  {
    if ( *v4 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v4);
    v8 = *SoftwareUpdateProviderStatus;
    *SoftwareUpdateProviderStatus = 0;
    *v4 = v8;
  }
  if ( v16 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  if ( lpMem )
  {
    v9 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v9 )
    {
      if ( v9 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180024600  mov     [rsp-8+arg_10], rbx
0x180024605  push    rbp
0x180024606  push    rsi
0x180024607  push    rdi
0x180024608  lea     rbp, [rsp-47h]
0x18002460d  sub     rsp, 0D0h
0x180024614  mov     rax, cs:__security_cookie
0x18002461b  xor     rax, rsp
0x18002461e  mov     [rbp+57h+var_18], rax
0x180024622  mov     rdi, rdx
0x180024625  mov     rsi, rcx
0x180024628  mov     [rbp+57h+var_98], rcx
0x18002462c  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderStatus@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderStatus>::`vftable'
0x180024633  mov     [rcx+10h], rax
0x180024637  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002463e  mov     qword ptr [rcx+8], 1
0x180024646  lea     rax, ??_7WindowsSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus::`vftable'
0x18002464d  mov     [rcx], rax
0x180024650  lea     rbx, [rcx+18h]
0x180024654  and     qword ptr [rbx], 0
0x180024658  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18002465f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180024664  test    al, al
0x180024666  jz      loc_1800247C0
0x18002466c  cmp     qword ptr [rdi], 0
0x180024670  jz      loc_1800247E6
0x180024676  xorps   xmm0, xmm0
0x180024679  movups  [rbp+57h+var_58], xmm0
0x18002467d  xorps   xmm1, xmm1
0x180024680  movdqu  [rbp+57h+var_48], xmm1
0x180024685  mov     r8d, 20h ; ' '
0x18002468b  lea     rdx, aUsoProvidersta; "USO_PROVIDERSTATUS_PROVIDERTOKEN"
0x180024692  lea     rcx, [rbp+57h+var_58]
0x180024696  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002469b  nop
0x18002469c  lea     rdx, [rbp+57h+var_58]
0x1800246a0  lea     rcx, [rbp+57h+var_38]
0x1800246a4  call    ?GetEnvironmentVariableString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; GetEnvironmentVariableString(std::wstring const &)
0x1800246a9  nop
0x1800246aa  mov     rdx, rax
0x1800246ad  cmp     qword ptr [rax+18h], 7
0x1800246b2  jbe     short loc_1800246B7
0x1800246b4  mov     rdx, [rax]; unsigned __int16 *
0x1800246b7  mov     r8d, [rax+10h]; unsigned int
0x1800246bb  lea     rcx, [rbp+57h+lpMem]; this
0x1800246bf  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x1800246c4  nop
0x1800246c5  lea     rcx, [rbp+57h+var_38]
0x1800246c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800246ce  nop
0x1800246cf  lea     rcx, [rbp+57h+var_58]
0x1800246d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800246d8  cmp     [rbp+57h+lpMem], 0
0x1800246dd  jz      loc_180024783
0x1800246e3  lea     r8, [rbp+57h+lpMem]
0x1800246e7  mov     rdx, rdi
0x1800246ea  lea     rcx, [rbp+57h+var_B8]
0x1800246ee  call    ?GetSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdateProviderStatus@2345@AEBUhstring@5@0@Z; winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProviderStatus(winrt::hstring const &,winrt::hstring const &)
0x1800246f3  mov     rdi, rax
0x1800246f6  cmp     rbx, rax
0x1800246f9  jz      short loc_180024713
0x1800246fb  cmp     qword ptr [rbx], 0
0x1800246ff  jz      short loc_180024709
0x180024701  mov     rcx, rbx
0x180024704  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024709  mov     rcx, [rdi]
0x18002470c  and     qword ptr [rdi], 0
0x180024710  mov     [rbx], rcx
0x180024713  cmp     [rbp+57h+var_B8], 0
0x180024718  jz      short loc_180024724
0x18002471a  lea     rcx, [rbp+57h+var_B8]
0x18002471e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024723  nop
0x180024724  mov     rax, [rbp+57h+lpMem]
0x180024728  test    rax, rax
0x18002472b  jz      short loc_18002474F
0x18002472d  or      ecx, 0FFFFFFFFh
0x180024730  lock xadd [rax+18h], ecx
0x180024735  sub     ecx, 1
0x180024738  jnz     short loc_180024772
0x18002473a  nop
0x18002473b  call    WINRT_IMPL_GetProcessHeap
0x180024740  mov     rcx, rax; hHeap
0x180024743  mov     r8, [rbp+57h+lpMem]; lpMem
0x180024747  xor     edx, edx; dwFlags
0x180024749  call    WINRT_IMPL_HeapFree
0x18002474e  nop
0x18002474f  mov     rax, rsi
0x180024752  mov     rcx, [rbp+57h+var_18]
0x180024756  xor     rcx, rsp; StackCookie
0x180024759  call    __security_check_cookie
0x18002475e  mov     rbx, [rsp+0E0h+arg_10]
0x180024766  add     rsp, 0D0h
0x18002476d  pop     rdi
0x18002476e  pop     rsi
0x18002476f  pop     rbp
0x180024770  retn
0x180024772  test    ecx, ecx
0x180024774  jns     short loc_18002474F
0x180024776  call    cs:__imp_abort
0x180024783  lea     rcx, [rbp+57h+var_90]
0x180024787  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002478c  mov     rbx, rax
0x18002478f  lea     rdx, aProvidertokenC; "providerToken cannot be empty"
0x180024796  lea     rcx, [rbp+57h+var_78]; this
0x18002479a  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002479f  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x1800247a2  lea     rdx, [rbp+57h+var_78]; struct winrt::param::hstring *
0x1800247a6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800247aa  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800247af  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800247b6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800247ba  call    _CxxThrowException_0
0x1800247c0  lea     rcx, [rbp+57h+var_90]
0x1800247c4  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800247c9  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800247cc  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800247d0  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800247d5  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800247dc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800247e0  call    _CxxThrowException_0
0x1800247e6  lea     rcx, [rbp+57h+var_90]
0x1800247ea  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800247ef  mov     rbx, rax
0x1800247f2  lea     rdx, aProvideridCann; "providerId cannot be empty"
0x1800247f9  lea     rcx, [rbp+57h+var_78]; this
0x1800247fd  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180024802  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180024805  lea     rdx, [rbp+57h+var_78]; struct winrt::param::hstring *
0x180024809  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002480d  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180024812  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180024819  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002481d  call    _CxxThrowException_0
```
