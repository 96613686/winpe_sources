# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::GetUupUri(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18001e7d0`
- end: `0x18001eaff`
- name: `?GetUupUri@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@CA?AUUri@Foundation@46@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `815`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800027d0`
- `0x180003db0`
- `0x180004810`
- `0x180010320`
- `0x180014230`
- `0x1800145d0`
- `0x180014650`
- `0x180019470`
- `0x180019d50`
- `0x18001e7d0`
- `0x180032dd0`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001ea3d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001ea3d`

## pseudocode

```c
_QWORD *__fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::GetUupUri(_QWORD *a1)
{
  __int128 *p_Src; // rdi
  char *v3; // rbx
  __int64 v4; // rax
  wchar_t *v5; // rdx
  char *v6; // rbx
  __int64 v7; // rax
  __int128 *v8; // rdi
  char *v9; // rbx
  __int64 v10; // rax
  __int128 *v11; // rdi
  char *v12; // rbx
  __int64 v13; // rax
  __int128 *v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  _DWORD *v18; // [rsp+38h] [rbp-11h] BYREF
  _DWORD v19[4]; // [rsp+40h] [rbp-9h] BYREF
  __int128 *v20; // [rsp+50h] [rbp+7h]
  __int64 *v21; // [rsp+58h] [rbp+Fh]
  _QWORD *v22; // [rsp+60h] [rbp+17h] BYREF
  __int128 Src; // [rsp+68h] [rbp+1Fh] BYREF
  unsigned __int64 v24; // [rsp+78h] [rbp+2Fh]
  unsigned __int64 v25; // [rsp+80h] [rbp+37h]

  v22 = a1;
  Src = 0;
  v24 = 0;
  v25 = 7;
  LOWORD(Src) = 0;
  std::wstring::assign(&Src, L"uup://Product/");
  std::wstring::append(&Src);
  p_Src = &Src;
  if ( IsRunningOnArm64() )
  {
    if ( v25 > 7 )
      p_Src = (__int128 *)Src;
    if ( v24 >= 4 )
    {
      _mm_lfence();
      v3 = (char *)p_Src + 2 * v24;
      v4 = _std_search_2(p_Src, v3, L".Qnn", 4);
      if ( (char *)v4 != v3 && (v4 - (__int64)p_Src) >> 1 != -1 )
        std::wstring::replace(&Src, 4);
    }
    v5 = L".arm64";
  }
  else
  {
    if ( v25 > 7 )
      p_Src = (__int128 *)Src;
    if ( v24 >= 4 )
    {
      _mm_lfence();
      v6 = (char *)p_Src + 2 * v24;
      v7 = _std_search_2(p_Src, v6, L".Stx", 4);
      if ( (char *)v7 != v6 && (v7 - (__int64)p_Src) >> 1 != -1 )
        std::wstring::replace(&Src, 4);
    }
    v8 = &Src;
    if ( v25 > 7 )
      v8 = (__int128 *)Src;
    if ( v24 >= 4 )
    {
      _mm_lfence();
      v9 = (char *)v8 + 2 * v24;
      v10 = _std_search_2(v8, v9, L".Lnl", 4);
      if ( (char *)v10 != v9 && (v10 - (__int64)v8) >> 1 != -1 )
        std::wstring::replace(&Src, 4);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57003568>::GetImpl'::`2'::impl) )
    {
      v11 = &Src;
      if ( v25 > 7 )
        v11 = (__int128 *)Src;
      if ( v24 >= 4 )
      {
        _mm_lfence();
        v12 = (char *)v11 + 2 * v24;
        v13 = _std_search_2(v11, v12, L".365", 4);
        if ( (char *)v13 != v12 && (v13 - (__int64)v11) >> 1 != -1 )
          std::wstring::replace(&Src, 4);
      }
    }
    v5 = L".amd64";
  }
  std::wstring::append(&Src, v5);
  v14 = &Src;
  if ( v25 > 7 )
    v14 = (__int128 *)Src;
  v15 = -1;
  do
    ++v15;
  while ( *((_WORD *)v14 + v15) );
  if ( (_DWORD)v15 )
  {
    if ( *((_WORD *)v14 + (unsigned int)v15) )
      abort();
    v19[0] = 1;
    v19[1] = v15;
    v20 = v14;
    v18 = v19;
  }
  else
  {
    v18 = 0;
  }
  v22 = &v18;
  v21 = &qword_180059E78;
  _InterlockedIncrement64(&qword_180059E78);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> )
  {
    v22 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
                                                                  + 48LL))(
            winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
            v18,
            &v22);
    if ( v16 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v16);
    }
    *a1 = v22;
    _InterlockedDecrement64(&qword_180059E78);
  }
  else
  {
    _InterlockedDecrement64(&qword_180059E78);
    winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::call<_lambda_0a61d549bec6c444b35123f4c9509ca7_ &>(
      0,
      a1,
      &v22);
  }
  std::wstring::_Tidy_deallocate((__int64)&Src);
  return a1;
}

```

## disassembly

```asm
0x18001e7d0  mov     [rsp-8+arg_10], rbx
0x18001e7d5  mov     [rsp-8+arg_18], rsi
0x18001e7da  push    rbp
0x18001e7db  push    rdi
0x18001e7dc  push    r14
0x18001e7de  lea     rbp, [rsp-47h]
0x18001e7e3  sub     rsp, 90h
0x18001e7ea  mov     rax, cs:__security_cookie
0x18001e7f1  xor     rax, rsp
0x18001e7f4  mov     [rbp+57h+var_18], rax
0x18001e7f8  mov     rbx, rdx
0x18001e7fb  mov     rsi, rcx
0x18001e7fe  mov     [rbp+57h+var_40], rcx
0x18001e802  xor     r14d, r14d
0x18001e805  xorps   xmm0, xmm0
0x18001e808  movups  [rbp+57h+Src], xmm0
0x18001e80c  mov     [rbp+57h+var_28], r14
0x18001e810  mov     [rbp+57h+var_20], 7
0x18001e818  mov     word ptr [rbp+57h+Src], r14w
0x18001e81d  mov     r8d, 0Eh
0x18001e823  lea     rdx, aUupProduct; "uup://Product/"
0x18001e82a  lea     rcx, [rbp+57h+Src]; void *
0x18001e82e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18001e833  mov     r8, [rbx+8]
0x18001e837  mov     rdx, [rbx]
0x18001e83a  lea     rcx, [rbp+57h+Src]; Src
0x18001e83e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18001e843  call    ?IsRunningOnArm64@@YA_NXZ; IsRunningOnArm64(void)
0x18001e848  lea     rdi, [rbp+57h+Src]
0x18001e84c  test    al, al
0x18001e84e  jz      short loc_18001E8BD
0x18001e850  cmp     [rbp+57h+var_20], 7
0x18001e855  cmova   rdi, qword ptr [rbp+57h+Src]
0x18001e85a  cmp     [rbp+57h+var_28], 4
0x18001e85f  jb      short loc_18001E8B1
0x18001e861  lfence
0x18001e864  mov     rax, [rbp+57h+var_28]
0x18001e868  lea     rbx, [rdi+rax*2]
0x18001e86c  mov     r9d, 4
0x18001e872  lea     r8, aQnn; ".Qnn"
0x18001e879  mov     rdx, rbx
0x18001e87c  mov     rcx, rdi
0x18001e87f  call    __std_search_2
0x18001e884  cmp     rax, rbx
0x18001e887  jz      short loc_18001E8B1
0x18001e889  sub     rax, rdi
0x18001e88c  sar     rax, 1
0x18001e88f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e893  jz      short loc_18001E8B1
0x18001e895  mov     [rsp+0A0h+var_80], 4; __int64
0x18001e89e  lea     r9, aK95; ".K95"
0x18001e8a5  mov     rdx, rax
0x18001e8a8  lea     rcx, [rbp+57h+Src]; Src
0x18001e8ac  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_KQEB_W0@Z; std::wstring::replace(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18001e8b1  lea     rdx, aArm64; ".arm64"
0x18001e8b8  jmp     loc_18001E9FF
0x18001e8bd  cmp     [rbp+57h+var_20], 7
0x18001e8c2  cmova   rdi, qword ptr [rbp+57h+Src]
0x18001e8c7  cmp     [rbp+57h+var_28], 4
0x18001e8cc  jb      short loc_18001E91E
0x18001e8ce  lfence
0x18001e8d1  mov     rax, [rbp+57h+var_28]
0x18001e8d5  lea     rbx, [rdi+rax*2]
0x18001e8d9  mov     r9d, 4
0x18001e8df  lea     r8, aStx_1; ".Stx"
0x18001e8e6  mov     rdx, rbx
0x18001e8e9  mov     rcx, rdi
0x18001e8ec  call    __std_search_2
0x18001e8f1  cmp     rax, rbx
0x18001e8f4  jz      short loc_18001E91E
0x18001e8f6  sub     rax, rdi
0x18001e8f9  sar     rax, 1
0x18001e8fc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e900  jz      short loc_18001E91E
0x18001e902  mov     [rsp+0A0h+var_80], 4; __int64
0x18001e90b  lea     r9, aStx; ".STX"
0x18001e912  mov     rdx, rax
0x18001e915  lea     rcx, [rbp+57h+Src]; Src
0x18001e919  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_KQEB_W0@Z; std::wstring::replace(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18001e91e  lea     rdi, [rbp+57h+Src]
0x18001e922  cmp     [rbp+57h+var_20], 7
0x18001e927  cmova   rdi, qword ptr [rbp+57h+Src]
0x18001e92c  cmp     [rbp+57h+var_28], 4
0x18001e931  jb      short loc_18001E983
0x18001e933  lfence
0x18001e936  mov     rax, [rbp+57h+var_28]
0x18001e93a  lea     rbx, [rdi+rax*2]
0x18001e93e  mov     r9d, 4
0x18001e944  lea     r8, aLnl; ".Lnl"
0x18001e94b  mov     rdx, rbx
0x18001e94e  mov     rcx, rdi
0x18001e951  call    __std_search_2
0x18001e956  cmp     rax, rbx
0x18001e959  jz      short loc_18001E983
0x18001e95b  sub     rax, rdi
0x18001e95e  sar     rax, 1
0x18001e961  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e965  jz      short loc_18001E983
0x18001e967  mov     [rsp+0A0h+var_80], 4; __int64
0x18001e970  lea     r9, aLnl_1; ".LNL"
0x18001e977  mov     rdx, rax
0x18001e97a  lea     rcx, [rbp+57h+Src]; Src
0x18001e97e  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_KQEB_W0@Z; std::wstring::replace(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18001e983  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57003568@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57003568@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568> `wil::Feature<__WilFeatureTraits_Feature_57003568>::GetImpl(void)'::`2'::impl
0x18001e98a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57003568@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568>::__private_IsEnabled(void)
0x18001e98f  test    al, al
0x18001e991  jz      short loc_18001E9F8
0x18001e993  lea     rdi, [rbp+57h+Src]
0x18001e997  cmp     [rbp+57h+var_20], 7
0x18001e99c  cmova   rdi, qword ptr [rbp+57h+Src]
0x18001e9a1  cmp     [rbp+57h+var_28], 4
0x18001e9a6  jb      short loc_18001E9F8
0x18001e9a8  lfence
0x18001e9ab  mov     rax, [rbp+57h+var_28]
0x18001e9af  lea     rbx, [rdi+rax*2]
0x18001e9b3  mov     r9d, 4
0x18001e9b9  lea     r8, a365; ".365"
0x18001e9c0  mov     rdx, rbx
0x18001e9c3  mov     rcx, rdi
0x18001e9c6  call    __std_search_2
0x18001e9cb  cmp     rax, rbx
0x18001e9ce  jz      short loc_18001E9F8
0x18001e9d0  sub     rax, rdi
0x18001e9d3  sar     rax, 1
0x18001e9d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e9da  jz      short loc_18001E9F8
0x18001e9dc  mov     [rsp+0A0h+var_80], 4; __int64
0x18001e9e5  lea     r9, a365; ".365"
0x18001e9ec  mov     rdx, rax
0x18001e9ef  lea     rcx, [rbp+57h+Src]; Src
0x18001e9f3  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_KQEB_W0@Z; std::wstring::replace(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18001e9f8  lea     rdx, aAmd64; ".amd64"
0x18001e9ff  lea     rcx, [rbp+57h+Src]; Src
0x18001ea03  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18001ea08  lea     rdx, [rbp+57h+Src]
0x18001ea0c  cmp     [rbp+57h+var_20], 7
0x18001ea11  cmova   rdx, qword ptr [rbp+57h+Src]
0x18001ea16  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ea1d  nop     dword ptr [rax]
0x18001ea20  inc     rcx
0x18001ea23  cmp     word ptr [rdx+rcx*2], 0
0x18001ea28  jnz     short loc_18001EA20
0x18001ea2a  test    ecx, ecx
0x18001ea2c  jnz     short loc_18001EA34
0x18001ea2e  mov     [rbp+57h+var_68], r14
0x18001ea32  jmp     short loc_18001EA5A
0x18001ea34  mov     eax, ecx
0x18001ea36  cmp     word ptr [rdx+rax*2], 0
0x18001ea3b  jz      short loc_18001EA44
0x18001ea3d  call    cs:__imp_abort
0x18001ea44  mov     [rbp+57h+var_60], 1
0x18001ea4b  mov     [rbp+57h+var_5C], ecx
0x18001ea4e  mov     [rbp+57h+var_50], rdx
0x18001ea52  lea     rax, [rbp+57h+var_60]
0x18001ea56  mov     [rbp+57h+var_68], rax
0x18001ea5a  lea     rax, [rbp+57h+var_68]
0x18001ea5e  mov     [rbp+57h+var_40], rax
0x18001ea62  lea     rax, qword_180059E78
0x18001ea69  mov     [rbp+57h+var_48], rax
0x18001ea6d  lock inc cs:qword_180059E78
0x18001ea75  mov     rcx, cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18001ea7c  test    rcx, rcx
0x18001ea7f  jz      short loc_18001EAAF
0x18001ea81  mov     [rbp+57h+var_40], r14
0x18001ea85  mov     rax, [rcx]
0x18001ea88  lea     r8, [rbp+57h+var_40]
0x18001ea8c  mov     rdx, [rbp+57h+var_68]
0x18001ea90  mov     rax, [rax+30h]
0x18001ea94  call    cs:__guard_dispatch_icall_fptr
0x18001ea9a  test    eax, eax
0x18001ea9c  js      short loc_18001EAF4
0x18001ea9e  mov     rax, [rbp+57h+var_40]
0x18001eaa2  mov     [rsi], rax
0x18001eaa5  lock dec cs:qword_180059E78
0x18001eaad  jmp     short loc_18001EAC4
0x18001eaaf  lock dec cs:qword_180059E78
0x18001eab7  lea     r8, [rbp+57h+var_40]
0x18001eabb  mov     rdx, rsi
0x18001eabe  call    ??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z
0x18001eac3  nop
0x18001eac4  lea     rcx, [rbp+57h+Src]
0x18001eac8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eacd  mov     rax, rsi
0x18001ead0  mov     rcx, [rbp+57h+var_18]
0x18001ead4  xor     rcx, rsp; StackCookie
0x18001ead7  call    __security_check_cookie
0x18001eadc  lea     r11, [rsp+0A0h+var_10]
0x18001eae4  mov     rbx, [r11+30h]
0x18001eae8  mov     rsi, [r11+38h]
0x18001eaec  mov     rsp, r11
0x18001eaef  pop     r14
0x18001eaf1  pop     rdi
0x18001eaf2  pop     rbp
0x18001eaf3  retn
0x18001eaf4  lfence
0x18001eaf7  mov     ecx, eax
0x18001eaf9  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
