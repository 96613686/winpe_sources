# Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::CreatePathUnderAppDataAndReturnFullFilePathWithLongPath(winrt::hstring const &,winrt::hstring const &)

- ea: `0x1800c50d0`
- end: `0x1800c537a`
- name: `?CreatePathUnderAppDataAndReturnFullFilePathWithLongPath@DownloaderUtils@Utils@Downloader@Cloud@Storage@Internal@Windows@@SA?AUhstring@winrt@@AEBU89@0@Z`
- size: `682`
- prototype: `static struct winrt::hstring __high(const struct winrt::hstring *, const struct winrt::hstring *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task`

## callers

- `0x1800c69f8`
- `0x180142390`

## callees

- `0x180016cf4`
- `0x180031e70`
- `0x18003b254`
- `0x18003b488`
- `0x18003f11c`
- `0x180047904`
- `0x180062040`
- `0x180079cdc`
- `0x1800ac3a4`
- `0x1800c50d0`
- `0x1800c67cc`
- `0x1800c68ac`
- `0x1800c6ff0`
- `0x1800c7044`
- `0x1800c7234`
- `0x1800e9484`
- `0x180128e9c`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800c51ae`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800c52aa`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800c51ae`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800c52aa`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800c5114`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800c5114`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::CreatePathUnderAppDataAndReturnFullFilePathWithLongPath(
        _QWORD *a1,
        winrt::hstring *a2,
        winrt::hstring *a3)
{
  HRESULT v6; // eax
  winrt::hstring *v7; // rcx
  const unsigned __int16 *v8; // rax
  const wchar_t *v9; // rcx
  _WORD *v10; // rdx
  HRESULT v11; // eax
  const unsigned __int16 *v12; // rdx
  int DirectoryDeepNoThrow; // eax
  const unsigned __int16 *v14; // rax
  __int64 v15; // rax
  void *p_pszPathIn; // rcx
  const WCHAR *v17; // rax
  HRESULT v18; // eax
  const unsigned __int16 *v19; // rdx
  int v20; // eax
  __int64 v21; // rax
  int v23; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v24; // [rsp+28h] [rbp-50h] BYREF
  __int64 v25; // [rsp+30h] [rbp-48h] BYREF
  PCWSTR pszPathIn; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v27[8]; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v28[8]; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int16 **v29; // [rsp+50h] [rbp-28h] BYREF
  PWSTR ppszPath; // [rsp+58h] [rbp-20h] BYREF
  char v31; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]
  PWSTR ppszPathOut; // [rsp+B8h] [rbp+40h] BYREF

  v24 = 0;
  v29 = &v24;
  ppszPath = 0;
  v31 = 1;
  v6 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x1C000u, 0, &ppszPath);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
      (const char *)(unsigned int)v6,
      v23);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v29);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AadAssetsRestore>::GetImpl'::`2'::impl) )
  {
    winrt::hstring::c_str(a2);
    v8 = winrt::hstring::c_str(v7);
    v9 = L"%ls\\%ls";
    if ( *v10 == 92 )
      v9 = L"%ls%ls";
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszPathIn,
      v9,
      v24,
      v8);
    ppszPathOut = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v11 = PathAllocCanonicalize(pszPathIn, 0x10u, &ppszPathOut);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
        (const char *)(unsigned int)v11,
        v23);
    DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)ppszPathOut, v12);
    if ( DirectoryDeepNoThrow < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
        (const char *)(unsigned int)DirectoryDeepNoThrow,
        v23);
    v14 = winrt::hstring::c_str(a3);
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v25,
      L"%ls\\%ls",
      ppszPathOut,
      v14);
    v15 = v25;
    v25 = 0;
    *a1 = v15;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v25);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    p_pszPathIn = &pszPathIn;
  }
  else
  {
    ppszPathOut = 0;
    winrt::hstring::hstring((winrt::hstring *)&v25, v24);
    winrt::hstring::hstring((winrt::hstring *)&pszPathIn, (const struct winrt::hstring *)&v25);
    winrt::operator+(v27, &pszPathIn, a2);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&pszPathIn);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v25);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v17 = winrt::hstring::c_str((winrt::hstring *)v27);
    v18 = PathAllocCanonicalize(v17, 0x10u, &ppszPathOut);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
        (const char *)(unsigned int)v18,
        v23);
    v20 = wil::CreateDirectoryDeepNoThrow((wil *)ppszPathOut, v19);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
        (const char *)(unsigned int)v20,
        v23);
    winrt::hstring::hstring((winrt::hstring *)&v25, ppszPathOut);
    winrt::hstring::hstring((winrt::hstring *)&pszPathIn, (const struct winrt::hstring *)&v25);
    v21 = winrt::operator+(v28, &pszPathIn, L"\\");
    winrt::operator+(a1, v21, a3);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v28);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&pszPathIn);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v25);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v27);
    p_pszPathIn = &ppszPathOut;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(p_pszPathIn);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
  return a1;
}

```

## disassembly

```asm
0x1800c50d0  push    rbp
0x1800c50d2  push    rbx
0x1800c50d3  push    rsi
0x1800c50d4  push    rdi
0x1800c50d5  mov     rbp, rsp
0x1800c50d8  sub     rsp, 78h
0x1800c50dc  mov     rdi, r8
0x1800c50df  mov     rsi, rdx
0x1800c50e2  mov     rbx, rcx
0x1800c50e5  mov     [rbp+var_50], 0
0x1800c50ed  lea     rax, [rbp+var_50]
0x1800c50f1  mov     [rbp+var_28], rax
0x1800c50f5  mov     [rbp+ppszPath], 0
0x1800c50fd  mov     [rbp+var_18], 1
0x1800c5101  lea     r9, [rbp+ppszPath]; ppszPath
0x1800c5105  xor     r8d, r8d; hToken
0x1800c5108  mov     edx, 1C000h; dwFlags
0x1800c510d  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800c5114  call    cs:__imp_SHGetKnownFolderPath
0x1800c511a  mov     rcx, [rbp+20h]; this
0x1800c511e  test    eax, eax
0x1800c5120  jns     short loc_1800C5137
0x1800c5122  mov     r9d, eax; char *
0x1800c5125  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1800c512c  mov     edx, 130h; void *
0x1800c5131  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c5137  lea     rcx, [rbp+var_28]
0x1800c513b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800c5140  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AadAssetsRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssetsRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore> `wil::Feature<__WilFeatureTraits_Feature_AadAssetsRestore>::GetImpl(void)'::`2'::impl
0x1800c5147  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssetsRestore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore>::__private_IsEnabled(void)
0x1800c514c  test    al, al
0x1800c514e  jz      loc_1800C5242
0x1800c5154  mov     rcx, rsi; this
0x1800c5157  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800c515c  mov     rdx, rax
0x1800c515f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800c5164  lea     r8, aLsLs_0; "%ls%ls"
0x1800c516b  lea     rcx, aLsLs; "%ls\\%ls"
0x1800c5172  cmp     word ptr [rdx], 5Ch ; '\'
0x1800c5176  cmovz   rcx, r8
0x1800c517a  mov     r9, rax
0x1800c517d  mov     r8, [rbp+var_50]
0x1800c5181  mov     rdx, rcx
0x1800c5184  lea     rcx, [rbp+pszPathIn]
0x1800c5188  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x1800c518d  nop
0x1800c518e  mov     [rbp+ppszPathOut], 0
0x1800c5196  xor     edx, edx
0x1800c5198  lea     rcx, [rbp+ppszPathOut]
0x1800c519c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c51a1  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x1800c51a5  mov     edx, 10h; dwFlags
0x1800c51aa  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x1800c51ae  call    cs:__imp_PathAllocCanonicalize
0x1800c51b4  mov     rcx, [rbp+20h]; this
0x1800c51b8  test    eax, eax
0x1800c51ba  jns     short loc_1800C51D1
0x1800c51bc  mov     r9d, eax; char *
0x1800c51bf  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1800c51c6  mov     edx, 13Fh; void *
0x1800c51cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c51d1  mov     rcx, [rbp+ppszPathOut]; this
0x1800c51d5  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800c51da  mov     rcx, [rbp+20h]; this
0x1800c51de  test    eax, eax
0x1800c51e0  jns     short loc_1800C51F7
0x1800c51e2  mov     r9d, eax; char *
0x1800c51e5  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1800c51ec  mov     edx, 141h; void *
0x1800c51f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c51f7  mov     rcx, rdi; this
0x1800c51fa  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800c51ff  mov     r9, rax
0x1800c5202  mov     r8, [rbp+ppszPathOut]
0x1800c5206  lea     rdx, aLsLs; "%ls\\%ls"
0x1800c520d  lea     rcx, [rbp+var_48]
0x1800c5211  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,...)
0x1800c5216  mov     rax, [rbp+var_48]
0x1800c521a  mov     [rbp+var_48], 0
0x1800c5222  mov     [rbx], rax
0x1800c5225  lea     rcx, [rbp+var_48]
0x1800c5229  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800c522e  nop
0x1800c522f  lea     rcx, [rbp+ppszPathOut]
0x1800c5233  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c5238  nop
0x1800c5239  lea     rcx, [rbp+pszPathIn]
0x1800c523d  jmp     loc_1800C535F
0x1800c5242  mov     [rbp+ppszPathOut], 0
0x1800c524a  mov     rdx, [rbp+var_50]; unsigned __int16 *
0x1800c524e  lea     rcx, [rbp+var_48]; this
0x1800c5252  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800c5257  nop
0x1800c5258  lea     rdx, [rbp+var_48]; struct winrt::hstring *
0x1800c525c  lea     rcx, [rbp+pszPathIn]; this
0x1800c5260  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800c5265  nop
0x1800c5266  mov     r8, rsi
0x1800c5269  lea     rdx, [rbp+pszPathIn]
0x1800c526d  lea     rcx, [rbp+var_38]
0x1800c5271  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x1800c5276  nop
0x1800c5277  lea     rcx, [rbp+pszPathIn]
0x1800c527b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c5280  nop
0x1800c5281  lea     rcx, [rbp+var_48]
0x1800c5285  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c528a  xor     edx, edx
0x1800c528c  lea     rcx, [rbp+ppszPathOut]
0x1800c5290  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c5295  lea     rcx, [rbp+var_38]; this
0x1800c5299  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800c529e  mov     rcx, rax; pszPathIn
0x1800c52a1  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x1800c52a5  mov     edx, 10h; dwFlags
0x1800c52aa  call    cs:__imp_PathAllocCanonicalize
0x1800c52b0  mov     rcx, [rbp+20h]; this
0x1800c52b4  test    eax, eax
0x1800c52b6  jns     short loc_1800C52CD
0x1800c52b8  mov     r9d, eax; char *
0x1800c52bb  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1800c52c2  mov     edx, 14Ah; void *
0x1800c52c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c52cd  mov     rcx, [rbp+ppszPathOut]; this
0x1800c52d1  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800c52d6  mov     rcx, [rbp+20h]; this
0x1800c52da  test    eax, eax
0x1800c52dc  jns     short loc_1800C52F3
0x1800c52de  mov     r9d, eax; char *
0x1800c52e1  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1800c52e8  mov     edx, 14Bh; void *
0x1800c52ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c52f3  mov     rdx, [rbp+ppszPathOut]; unsigned __int16 *
0x1800c52f7  lea     rcx, [rbp+var_48]; this
0x1800c52fb  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800c5300  nop
0x1800c5301  lea     rdx, [rbp+var_48]; struct winrt::hstring *
0x1800c5305  lea     rcx, [rbp+pszPathIn]; this
0x1800c5309  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800c530e  nop
0x1800c530f  lea     r8, asc_1802285AC; "\\"
0x1800c5316  lea     rdx, [rbp+pszPathIn]
0x1800c531a  lea     rcx, [rbp+var_30]
0x1800c531e  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@PEBG@Z; winrt::operator+(winrt::hstring const &,ushort const *)
0x1800c5323  nop
0x1800c5324  mov     r8, rdi
0x1800c5327  mov     rdx, rax
0x1800c532a  mov     rcx, rbx
0x1800c532d  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x1800c5332  nop
0x1800c5333  lea     rcx, [rbp+var_30]
0x1800c5337  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c533c  nop
0x1800c533d  lea     rcx, [rbp+pszPathIn]
0x1800c5341  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c5346  nop
0x1800c5347  lea     rcx, [rbp+var_48]
0x1800c534b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c5350  nop
0x1800c5351  lea     rcx, [rbp+var_38]
0x1800c5355  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c535a  nop
0x1800c535b  lea     rcx, [rbp+ppszPathOut]
0x1800c535f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c5364  nop
0x1800c5365  lea     rcx, [rbp+var_50]
0x1800c5369  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800c536e  mov     rax, rbx
0x1800c5371  add     rsp, 78h
0x1800c5375  pop     rdi
0x1800c5376  pop     rsi
0x1800c5377  pop     rbx
0x1800c5378  pop     rbp
0x1800c5379  retn
```
