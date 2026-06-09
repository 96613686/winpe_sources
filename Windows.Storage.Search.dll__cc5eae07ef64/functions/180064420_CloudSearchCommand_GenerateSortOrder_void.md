# CloudSearchCommand::GenerateSortOrder(void)

- ea: `0x180064420`
- end: `0x180064729`
- name: `?GenerateSortOrder@CloudSearchCommand@@AEAA?AU?$IVector@USortEntry@Search@Storage@Windows@winrt@@@Collections@Foundation@Windows@winrt@@XZ`
- size: `777`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d7e68`

## callees

- `0x180014e08`
- `0x180063f24`
- `0x1800641a8`
- `0x180064244`
- `0x180064420`
- `0x180064730`
- `0x180064790`
- `0x1800647b0`
- `0x180071dc0`
- `0x180092e40`
- `0x1800d49b0`
- `0x1800d5304`
- `0x1800d5608`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800644a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800644a6`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x180064636`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x180064636`

## string_xrefs

- `0x18006456f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800644b7`: `onecoreuap\shell\windows.storage.search\federatedcloudsearch\src\CloudSearchCommand.cpp`
- `0x18006451a`: `onecoreuap\shell\windows.storage.search\federatedcloudsearch\src\CloudSearchCommand.cpp`
- `0x1800645b0`: `onecoreuap\shell\windows.storage.search\federatedcloudsearch\src\CloudSearchCommand.cpp`
- `0x180064702`: `onecoreuap\shell\windows.storage.search\federatedcloudsearch\src\CloudSearchCommand.cpp`
- `0x180064717`: `onecoreuap\shell\windows.storage.search\federatedcloudsearch\src\CloudSearchCommand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
WCHAR *__fastcall CloudSearchCommand::GenerateSortOrder(__int64 a1, WCHAR *a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  HRESULT Instance; // eax
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  unsigned int i; // edi
  int v11; // eax
  bool v12; // si
  HRESULT v13; // eax
  int ppv; // [rsp+20h] [rbp-39h]
  PWSTR ppszCanonicalName; // [rsp+38h] [rbp-21h] BYREF
  __int64 v17; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v18; // [rsp+48h] [rbp-11h] BYREF
  _DWORD v19[2]; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int64 v20; // [rsp+58h] [rbp-1h]
  int v21; // [rsp+60h] [rbp+7h]
  int v22; // [rsp+64h] [rbp+Bh]
  _BYTE v23[24]; // [rsp+68h] [rbp+Fh] BYREF
  _BYTE propkey[24]; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  ppszCanonicalName = a2;
  v17 = 0;
  v3 = *(__int64 **)(a1 + 88);
  if ( !v3
    || (v4 = *v3,
        v17 = 0,
        (*(int (__fastcall **)(__int64 *, GUID *, __int64 *))(v4 + 80))(
          v3,
          &GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54,
          &v17) < 0) )
  {
    ppszCanonicalName = 0;
    Instance = CoCreateInstance(
                 &GUID_7df2cfcd_6c09_415a_ae9d_5263f4964cbb,
                 0,
                 1u,
                 &GUID_e70c4a71_a5a1_40f2_84eb_9a9081e246a9,
                 (LPVOID *)&ppszCanonicalName);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\federatedcloudsearch\\src\\CloudSearchCommand.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
    v19[0] = 1231625360;
    v19[1] = 270171671;
    v20 = 0xA9CD2E2B00081CA9uLL;
    v21 = 3;
    v22 = -1;
    v6 = (*(__int64 (__fastcall **)(PWSTR, _QWORD, _DWORD *, __int64))(*(_QWORD *)ppszCanonicalName + 24LL))(
           ppszCanonicalName,
           0,
           v19,
           1);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\federatedcloudsearch\\src\\CloudSearchCommand.cpp",
        (const char *)(unsigned int)v6,
        ppv);
    v7 = v17;
    v17 = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = (**(__int64 (__fastcall ***)(PWSTR, GUID *, __int64 *))ppszCanonicalName)(
           ppszCanonicalName,
           &GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54,
           &v17);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v8,
        ppv);
    wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&ppszCanonicalName);
  }
  v18 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 24LL))(v17, &v18);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\federatedcloudsearch\\src\\CloudSearchCommand.cpp",
      (const char *)(unsigned int)v9,
      ppv);
  memset(v23, 0, sizeof(v23));
  std::vector<std::wstring>::vector<std::wstring>(v23);
  for ( i = 0; i < v18; ++i )
  {
    memset(propkey, 0, sizeof(propkey));
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v17 + 32LL))(v17, i, propkey);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x105,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\federatedcloudsearch\\src\\CloudSearchCommand.cpp",
        (const char *)(unsigned int)v11,
        ppv);
    v12 = *(_DWORD *)&propkey[20] == 1;
    ppszCanonicalName = 0;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      &ppszCanonicalName,
      0);
    v13 = PSGetNameFromPropertyKey((const PROPERTYKEY *const)propkey, &ppszCanonicalName);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\federatedcloudsearch\\src\\CloudSearchCommand.cpp",
        (const char *)(unsigned int)v13,
        ppv);
    winrt::hstring::hstring((winrt::hstring *)v19, ppszCanonicalName);
    LOBYTE(v20) = v12;
    *(_DWORD *)((char *)&v20 + 1) = 0;
    *(_WORD *)((char *)&v20 + 5) = 0;
    HIBYTE(v20) = 0;
    std::vector<winrt::Windows::Storage::Search::SortEntry>::emplace_back<winrt::Windows::Storage::Search::SortEntry &>(
      v23,
      v19);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v19);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&ppszCanonicalName);
  }
  winrt::make<winrt::impl::vector_impl<winrt::Windows::Storage::Search::SortEntry,std::vector<winrt::Windows::Storage::Search::SortEntry>,winrt::impl::single_threaded_collection_base>,std::vector<winrt::Windows::Storage::Search::SortEntry>>(
    (unsigned __int64 *)a2,
    (__int64)v23);
  if ( *(_QWORD *)v23 )
  {
    std::_Destroy_range<std::allocator<winrt::Windows::Storage::Search::SortEntry>>(*(_QWORD *)v23, *(_QWORD *)&v23[8]);
    std::_Deallocate<16>(
      *(void **)v23,
      (struct std::nothrow_t *)((*(_QWORD *)&v23[16] - *(_QWORD *)v23) & 0xFFFFFFFFFFFFFFF0uLL));
    memset(v23, 0, sizeof(v23));
  }
  wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v17);
  return a2;
}

```

## disassembly

```asm
0x180064420  mov     [rsp-8+arg_10], rbx
0x180064425  push    rbp
0x180064426  push    rsi
0x180064427  push    rdi
0x180064428  lea     rbp, [rsp-47h]
0x18006442d  sub     rsp, 0A0h
0x180064434  mov     rax, cs:__security_cookie
0x18006443b  xor     rax, rsp
0x18006443e  mov     [rbp+57h+var_18], rax
0x180064442  mov     rbx, rdx
0x180064445  mov     [rbp+57h+ppszCanonicalName], rdx
0x180064449  mov     [rbp+57h+var_70], 0
0x180064451  mov     rcx, [rcx+58h]
0x180064455  test    rcx, rcx
0x180064458  jz      short loc_180064481
0x18006445a  mov     rax, [rcx]
0x18006445d  mov     [rbp+57h+var_70], 0
0x180064465  lea     r8, [rbp+57h+var_70]
0x180064469  lea     rdx, _GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54
0x180064470  mov     rax, [rax+50h]
0x180064474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064479  test    eax, eax
0x18006447b  jns     loc_18006458A
0x180064481  mov     [rbp+57h+ppszCanonicalName], 0
0x180064489  lea     rax, [rbp+57h+ppszCanonicalName]
0x18006448d  mov     qword ptr [rsp+0B0h+ppv], rax; int
0x180064492  lea     r9, _GUID_e70c4a71_a5a1_40f2_84eb_9a9081e246a9; riid
0x180064499  xor     edx, edx; pUnkOuter
0x18006449b  lea     r8d, [rdx+1]; dwClsContext
0x18006449f  lea     rcx, _GUID_7df2cfcd_6c09_415a_ae9d_5263f4964cbb; rclsid
0x1800644a6  call    cs:__imp_CoCreateInstance
0x1800644ac  mov     rcx, [rbp+5Fh]; this
0x1800644b0  test    eax, eax
0x1800644b2  jns     short loc_1800644C9
0x1800644b4  mov     r9d, eax; char *
0x1800644b7  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.storage.sear"...
0x1800644be  mov     edx, 0F6h; void *
0x1800644c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800644c9  mov     [rbp+57h+var_60], 49691C90h
0x1800644d0  mov     [rbp+57h+var_5C], 101A7E17h
0x1800644d7  mov     [rbp+57h+var_58], 81CA9h
0x1800644de  mov     [rbp+57h+var_54], 0A9CD2E2Bh
0x1800644e5  mov     [rbp+57h+var_50], 3
0x1800644ec  mov     [rbp+57h+var_4C], 0FFFFFFFFh
0x1800644f3  mov     rcx, [rbp+57h+ppszCanonicalName]
0x1800644f7  mov     rax, [rcx]
0x1800644fa  mov     r9d, 1
0x180064500  lea     r8, [rbp+57h+var_60]
0x180064504  xor     edx, edx
0x180064506  mov     rax, [rax+18h]
0x18006450a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006450f  mov     rcx, [rbp+5Fh]; this
0x180064513  test    eax, eax
0x180064515  jns     short loc_18006452C
0x180064517  mov     r9d, eax; char *
0x18006451a  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.storage.sear"...
0x180064521  mov     edx, 0FAh; void *
0x180064526  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006452c  mov     rcx, [rbp+57h+var_70]
0x180064530  mov     [rbp+57h+var_70], 0
0x180064538  test    rcx, rcx
0x18006453b  jz      short loc_18006454A
0x18006453d  mov     rax, [rcx]
0x180064540  mov     rax, [rax+10h]
0x180064544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064549  nop
0x18006454a  mov     rcx, [rbp+57h+ppszCanonicalName]
0x18006454e  mov     rax, [rcx]
0x180064551  lea     r8, [rbp+57h+var_70]
0x180064555  lea     rdx, _GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54
0x18006455c  mov     rax, [rax]
0x18006455f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064564  mov     rcx, [rbp+5Fh]; this
0x180064568  test    eax, eax
0x18006456a  jns     short loc_180064581
0x18006456c  mov     r9d, eax; char *
0x18006456f  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180064576  mov     edx, 1CBEh; void *
0x18006457b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064581  lea     rcx, [rbp+57h+ppszCanonicalName]
0x180064585  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x18006458a  mov     [rbp+57h+var_68], 0
0x180064591  mov     rcx, [rbp+57h+var_70]
0x180064595  mov     rax, [rcx]
0x180064598  lea     rdx, [rbp+57h+var_68]
0x18006459c  mov     rax, [rax+18h]
0x1800645a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645a5  mov     rcx, [rbp+5Fh]; this
0x1800645a9  test    eax, eax
0x1800645ab  jns     short loc_1800645C2
0x1800645ad  mov     r9d, eax; char *
0x1800645b0  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.storage.sear"...
0x1800645b7  mov     edx, 0FFh; void *
0x1800645bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800645c2  xorps   xmm0, xmm0
0x1800645c5  xor     eax, eax
0x1800645c7  movups  [rbp+57h+var_48], xmm0
0x1800645cb  mov     [rbp+57h+var_38], rax
0x1800645cf  lea     rcx, [rbp+57h+var_48]
0x1800645d3  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x1800645d8  nop
0x1800645d9  xor     edi, edi
0x1800645db  cmp     [rbp+57h+var_68], edi
0x1800645de  jbe     loc_180064691
0x1800645e4  xorps   xmm0, xmm0
0x1800645e7  xor     eax, eax
0x1800645e9  movups  xmmword ptr [rbp+57h+propkey], xmm0
0x1800645ed  mov     qword ptr [rbp+57h+propkey+10h], rax
0x1800645f1  mov     rcx, [rbp+57h+var_70]
0x1800645f5  mov     rax, [rcx]
0x1800645f8  lea     r8, [rbp+57h+propkey]
0x1800645fc  mov     edx, edi
0x1800645fe  mov     rax, [rax+20h]
0x180064602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064607  mov     rcx, [rbp+5Fh]; this
0x18006460b  test    eax, eax
0x18006460d  js      loc_180064714
0x180064613  cmp     dword ptr [rbp+57h+propkey+14h], 1
0x180064617  setz    sil
0x18006461b  mov     [rbp+57h+ppszCanonicalName], 0
0x180064623  xor     edx, edx
0x180064625  lea     rcx, [rbp+57h+ppszCanonicalName]
0x180064629  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18006462e  lea     rdx, [rbp+57h+ppszCanonicalName]; ppszCanonicalName
0x180064632  lea     rcx, [rbp+57h+propkey]; propkey
0x180064636  call    cs:__imp_PSGetNameFromPropertyKey
0x18006463c  mov     rcx, [rbp+5Fh]; this
0x180064640  test    eax, eax
0x180064642  js      loc_1800646FF
0x180064648  mov     rdx, [rbp+57h+ppszCanonicalName]; wchar_t *
0x18006464c  lea     rcx, [rbp+57h+var_60]; this
0x180064650  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180064655  mov     byte ptr [rbp+57h+var_58], sil
0x180064659  xor     eax, eax
0x18006465b  mov     [rbp+57h+var_58+1], eax
0x18006465e  mov     word ptr [rbp+57h+var_54+1], ax
0x180064662  mov     byte ptr [rbp+57h+var_54+3], al
0x180064665  lea     rdx, [rbp+57h+var_60]
0x180064669  lea     rcx, [rbp+57h+var_48]
0x18006466d  call    ??$emplace_back@AEAUSortEntry@Search@Storage@Windows@winrt@@@?$vector@USortEntry@Search@Storage@Windows@winrt@@V?$allocator@USortEntry@Search@Storage@Windows@winrt@@@std@@@std@@QEAAAEAUSortEntry@Search@Storage@Windows@winrt@@AEAU23456@@Z; std::vector<winrt::Windows::Storage::Search::SortEntry>::emplace_back<winrt::Windows::Storage::Search::SortEntry &>(winrt::Windows::Storage::Search::SortEntry &)
0x180064672  nop
0x180064673  lea     rcx, [rbp+57h+var_60]
0x180064677  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18006467c  nop
0x18006467d  lea     rcx, [rbp+57h+ppszCanonicalName]
0x180064681  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180064686  inc     edi
0x180064688  cmp     edi, [rbp+57h+var_68]
0x18006468b  jb      loc_1800645E4
0x180064691  lea     rdx, [rbp+57h+var_48]
0x180064695  mov     rcx, rbx
0x180064698  call    ??$make@U?$vector_impl@USortEntry@Search@Storage@Windows@winrt@@V?$vector@USortEntry@Search@Storage@Windows@winrt@@V?$allocator@USortEntry@Search@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@V?$vector@USortEntry@Search@Storage@Windows@winrt@@V?$allocator@USortEntry@Search@Storage@Windows@winrt@@@std@@@std@@@winrt@@YA?A_P$$QEAV?$vector@USortEntry@Search@Storage@Windows@winrt@@V?$allocator@USortEntry@Search@Storage@Windows@winrt@@@std@@@std@@@Z
0x18006469d  nop
0x18006469e  mov     rcx, qword ptr [rbp+57h+var_48]
0x1800646a2  test    rcx, rcx
0x1800646a5  jz      short loc_1800646D4
0x1800646a7  mov     rdx, qword ptr [rbp+57h+var_48+8]
0x1800646ab  call    ??$_Destroy_range@V?$allocator@USortEntry@Search@Storage@Windows@winrt@@@std@@@std@@YAXPEAUSortEntry@Search@Storage@Windows@winrt@@QEAU12345@AEAV?$allocator@USortEntry@Search@Storage@Windows@winrt@@@0@@Z; std::_Destroy_range<std::allocator<winrt::Windows::Storage::Search::SortEntry>>(winrt::Windows::Storage::Search::SortEntry *,winrt::Windows::Storage::Search::SortEntry * const,std::allocator<winrt::Windows::Storage::Search::SortEntry> &)
0x1800646b0  mov     rcx, qword ptr [rbp+57h+var_48]
0x1800646b4  mov     rdx, [rbp+57h+var_38]
0x1800646b8  sub     rdx, rcx
0x1800646bb  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800646bf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800646c4  mov     qword ptr [rbp+57h+var_48], 0
0x1800646cc  xorps   xmm0, xmm0
0x1800646cf  movdqu  [rbp+57h+var_48+8], xmm0
0x1800646d4  lea     rcx, [rbp+57h+var_70]
0x1800646d8  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x1800646dd  mov     rax, rbx
0x1800646e0  mov     rcx, [rbp+57h+var_18]
0x1800646e4  xor     rcx, rsp; StackCookie
0x1800646e7  call    __security_check_cookie
0x1800646ec  mov     rbx, [rsp+0B0h+arg_10]
0x1800646f4  add     rsp, 0A0h
0x1800646fb  pop     rdi
0x1800646fc  pop     rsi
0x1800646fd  pop     rbp
0x1800646fe  retn
0x1800646ff  mov     r9d, eax; char *
0x180064702  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.storage.sear"...
0x180064709  mov     edx, 108h; void *
0x18006470e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064714  mov     r9d, eax; char *
0x180064717  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.storage.sear"...
0x18006471e  mov     edx, 105h; void *
0x180064723  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
