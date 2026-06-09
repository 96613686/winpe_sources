# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus::WindowsSoftwareUpdateProviderStatus(winrt::hstring const &)

- ea: `0x18002333c`
- end: `0x18002356b`
- name: `??0WindowsSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@QEAA@AEBUhstring@5@@Z`
- size: `559`
- prototype: `winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus *__fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus *this, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800131f0`

## callees

- `0x1800028f0`
- `0x18000340c`
- `0x180008653`
- `0x18000866b`
- `0x180011464`
- `0x1800114a8`
- `0x1800114ec`
- `0x180014eb4`
- `0x180016fe4`
- `0x180017bec`
- `0x180018238`
- `0x18001c81c`
- `0x18001c8a0`
- `0x18002333c`
- `0x1800235a4`
- `0x1800236ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800234c4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800234c4`

## string_xrefs

- `0x1800233ca`: `USO_PROVIDERSTATUS_PROVIDERTOKEN`
- `0x1800234d7`: `providerToken cannot be empty`

## pseudocode

```c
winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus::WindowsSoftwareUpdateProviderStatus(
        winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus *this,
        const struct winrt::hstring *a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rdx
  _QWORD *EnvironmentVariableString; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 *SoftwareUpdateProviderStatus; // rdi
  __int64 v10; // rcx
  void *v11; // rbx
  int v12; // eax
  HANDLE ProcessHeap; // rax
  const struct winrt::impl::slim_source_location *v15; // rbx
  const struct winrt::impl::slim_source_location *v16; // rax
  const struct winrt::impl::slim_source_location *v17; // rbx
  LPVOID lpMem; // [rsp+20h] [rbp-69h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+28h] [rbp-61h] BYREF
  _BYTE v20[24]; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-29h] BYREF
  _OWORD v22[2]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v23[32]; // [rsp+A0h] [rbp+17h] BYREF

  pExceptionObject[3] = this;
  *((_QWORD *)this + 2) = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderStatus>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus::`vftable';
  v4 = (__int64 *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v16 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v20, v5);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v16);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  if ( !*(_QWORD *)a2 )
  {
    v17 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v20, v5);
    winrt::param::hstring::hstring((winrt::param::hstring *)v22, L"providerId cannot be empty");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v22,
      v17);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  memset(v22, 0, sizeof(v22));
  std::wstring::_Construct<1,unsigned short const *>(v22, L"USO_PROVIDERSTATUS_PROVIDERTOKEN", 0x20u);
  EnvironmentVariableString = (_QWORD *)GetEnvironmentVariableString(v23, v22);
  if ( EnvironmentVariableString[3] <= 7u )
    v7 = EnvironmentVariableString;
  else
    v7 = (_QWORD *)*EnvironmentVariableString;
  pExceptionObject[0] = v7;
  pExceptionObject[1] = EnvironmentVariableString[2];
  winrt::hstring::hstring((struct winrt::impl::shared_hstring_header **)&lpMem, (__int64)pExceptionObject);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v22);
  if ( !lpMem )
  {
    v15 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v20, v8);
    winrt::param::hstring::hstring((winrt::param::hstring *)v21, L"providerToken cannot be empty");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v21,
      v15);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  SoftwareUpdateProviderStatus = winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProviderStatus(
                                   pExceptionObject,
                                   (__int64)a2,
                                   (__int64)&lpMem);
  if ( v4 != SoftwareUpdateProviderStatus )
  {
    if ( *v4 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v4);
    v10 = *SoftwareUpdateProviderStatus;
    *SoftwareUpdateProviderStatus = 0;
    *v4 = v10;
  }
  if ( pExceptionObject[0] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(pExceptionObject);
  v11 = lpMem;
  if ( lpMem )
  {
    v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v11);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18002333c  mov     [rsp-8+arg_10], rbx
0x180023341  push    rbp
0x180023342  push    rsi
0x180023343  push    rdi
0x180023344  lea     rbp, [rsp-47h]
0x180023349  sub     rsp, 0D0h
0x180023350  mov     rax, cs:__security_cookie
0x180023357  xor     rax, rsp
0x18002335a  mov     [rbp+57h+var_20], rax
0x18002335e  mov     rdi, rdx
0x180023361  mov     rsi, rcx
0x180023364  mov     [rbp+57h+var_A0], rcx
0x180023368  lea     rax, ??_7?$produce@UWindowsSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderStatus@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderStatus>::`vftable'
0x18002336f  mov     [rcx+10h], rax
0x180023373  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002337a  mov     qword ptr [rcx+8], 1
0x180023382  lea     rax, ??_7WindowsSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus::`vftable'
0x180023389  mov     [rcx], rax
0x18002338c  lea     rbx, [rcx+18h]
0x180023390  mov     qword ptr [rbx], 0
0x180023397  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18002339e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800233a3  test    al, al
0x1800233a5  jz      loc_180023508
0x1800233ab  cmp     qword ptr [rdi], 0
0x1800233af  jz      loc_18002352E
0x1800233b5  xorps   xmm0, xmm0
0x1800233b8  movups  [rbp+57h+var_60], xmm0
0x1800233bc  xorps   xmm1, xmm1
0x1800233bf  movdqu  [rbp+57h+var_50], xmm1
0x1800233c4  mov     r8d, 20h ; ' '
0x1800233ca  lea     rdx, aUsoProvidersta; "USO_PROVIDERSTATUS_PROVIDERTOKEN"
0x1800233d1  lea     rcx, [rbp+57h+var_60]
0x1800233d5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800233da  nop
0x1800233db  lea     rdx, [rbp+57h+var_60]
0x1800233df  lea     rcx, [rbp+57h+var_40]
0x1800233e3  call    ?GetEnvironmentVariableString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; GetEnvironmentVariableString(std::wstring const &)
0x1800233e8  nop
0x1800233e9  cmp     qword ptr [rax+18h], 7
0x1800233ee  jbe     short loc_1800233F5
0x1800233f0  mov     rcx, [rax]
0x1800233f3  jmp     short loc_1800233F8
0x1800233f5  mov     rcx, rax
0x1800233f8  mov     [rbp+57h+pExceptionObject], rcx
0x1800233fc  mov     rax, [rax+10h]
0x180023400  mov     [rbp+57h+var_B0], rax
0x180023404  lea     rdx, [rbp+57h+pExceptionObject]
0x180023408  lea     rcx, [rbp+57h+lpMem]
0x18002340c  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180023411  nop
0x180023412  lea     rcx, [rbp+57h+var_40]
0x180023416  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002341b  nop
0x18002341c  lea     rcx, [rbp+57h+var_60]
0x180023420  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023425  cmp     [rbp+57h+lpMem], 0
0x18002342a  jz      loc_1800234CB
0x180023430  lea     r8, [rbp+57h+lpMem]
0x180023434  mov     rdx, rdi
0x180023437  lea     rcx, [rbp+57h+pExceptionObject]
0x18002343b  call    ?GetSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdateProviderStatus@2345@AEBUhstring@5@0@Z; winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProviderStatus(winrt::hstring const &,winrt::hstring const &)
0x180023440  mov     rdi, rax
0x180023443  cmp     rbx, rax
0x180023446  jz      short loc_180023463
0x180023448  cmp     qword ptr [rbx], 0
0x18002344c  jz      short loc_180023456
0x18002344e  mov     rcx, rbx
0x180023451  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023456  mov     rcx, [rdi]
0x180023459  mov     qword ptr [rdi], 0
0x180023460  mov     [rbx], rcx
0x180023463  cmp     [rbp+57h+pExceptionObject], 0
0x180023468  jz      short loc_180023474
0x18002346a  lea     rcx, [rbp+57h+pExceptionObject]
0x18002346e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023473  nop
0x180023474  mov     rbx, [rbp+57h+lpMem]
0x180023478  test    rbx, rbx
0x18002347b  jz      short loc_18002349E
0x18002347d  or      eax, 0FFFFFFFFh
0x180023480  lock xadd [rbx+18h], eax
0x180023485  sub     eax, 1
0x180023488  jnz     short loc_1800234C0
0x18002348a  nop
0x18002348b  call    WINRT_IMPL_GetProcessHeap
0x180023490  mov     rcx, rax; hHeap
0x180023493  mov     r8, rbx; lpMem
0x180023496  xor     edx, edx; dwFlags
0x180023498  call    WINRT_IMPL_HeapFree
0x18002349d  nop
0x18002349e  mov     rax, rsi
0x1800234a1  mov     rcx, [rbp+57h+var_20]
0x1800234a5  xor     rcx, rsp; StackCookie
0x1800234a8  call    __security_check_cookie
0x1800234ad  mov     rbx, [rsp+0E0h+arg_10]
0x1800234b5  add     rsp, 0D0h
0x1800234bc  pop     rdi
0x1800234bd  pop     rsi
0x1800234be  pop     rbp
0x1800234bf  retn
0x1800234c0  test    eax, eax
0x1800234c2  jns     short loc_18002349E
0x1800234c4  call    cs:__imp_abort
0x1800234cb  lea     rcx, [rbp+57h+var_98]
0x1800234cf  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800234d4  mov     rbx, rax
0x1800234d7  lea     rdx, aProvidertokenC; "providerToken cannot be empty"
0x1800234de  lea     rcx, [rbp+57h+var_80]; this
0x1800234e2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800234e7  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x1800234ea  lea     rdx, [rbp+57h+var_80]; struct winrt::param::hstring *
0x1800234ee  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800234f2  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800234f7  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800234fe  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180023502  call    _CxxThrowException_0
0x180023508  lea     rcx, [rbp+57h+var_98]
0x18002350c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180023511  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180023514  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180023518  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18002351d  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180023524  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180023528  call    _CxxThrowException_0
0x18002352e  lea     rcx, [rbp+57h+var_98]
0x180023532  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180023537  mov     rbx, rax
0x18002353a  lea     rdx, aProvideridCann; "providerId cannot be empty"
0x180023541  lea     rcx, [rbp+57h+var_60]; this
0x180023545  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002354a  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x18002354d  lea     rdx, [rbp+57h+var_60]; struct winrt::param::hstring *
0x180023551  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180023555  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18002355a  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180023561  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180023565  call    _CxxThrowException_0
```
