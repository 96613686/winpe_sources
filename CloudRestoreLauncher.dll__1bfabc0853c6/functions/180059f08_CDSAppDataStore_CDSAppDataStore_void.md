# CDSAppDataStore::CDSAppDataStore(void)

- ea: `0x180059f08`
- end: `0x18005a117`
- name: `??0CDSAppDataStore@@QEAA@XZ`
- size: `527`
- prototype: `CDSAppDataStore *__fastcall(CDSAppDataStore *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180051618`

## callees

- `0x18000c6e0`
- `0x180012c0c`
- `0x1800157f0`
- `0x1800162a4`
- `0x18001666c`
- `0x180016cec`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001d1f4`
- `0x18001da4c`
- `0x180027ec0`
- `0x180035c0c`
- `0x18004712c`
- `0x18004718c`
- `0x180059388`
- `0x180059628`
- `0x180059f08`
- `0x18006078c`
- `0x1800653e0`
- `0x180066660`
- `0x180066ce8`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x18005a02c`
- `SHELL32!SHGetKnownFolderPath` at `0x18005a02c`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
CDSAppDataStore *__fastcall CDSAppDataStore::CDSAppDataStore(CDSAppDataStore *this)
{
  char *v2; // rdi
  __int64 v3; // rcx
  __int64 Default; // rax
  HRESULT v5; // eax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  CDSAppDataStore *v9; // rax
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-69h]
  PWSTR v13; // [rsp+40h] [rbp-49h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v15[3]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v16[32]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v18[32]; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v15[2] = this;
  *(_QWORD *)this = &CDSAppDataStore::`vftable';
  *((_BYTE *)this + 8) = 0;
  v2 = (char *)this + 16;
  v13 = (PWSTR)((char *)this + 16);
  *((_DWORD *)this + 4) = 0;
  std::list<std::pair<winrt::hstring const,AppMetaData const>>::list<std::pair<winrt::hstring const,AppMetaData const>>((char *)this + 24);
  std::vector<bond::blob>::vector<bond::blob>(v2 + 24);
  *((_QWORD *)v2 + 6) = 7;
  *((_QWORD *)v2 + 7) = 8;
  *(_DWORD *)v2 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    v3,
    16,
    *((_QWORD *)v2 + 1));
  *((_QWORD *)this + 10) = 0;
  *((_BYTE *)this + 88) = 0;
  LODWORD(v13) = 0;
  std::_Hash<std::_Umap_traits<winrt::hstring,TileInfo const,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,TileInfo const>>,0>>::_Hash<std::_Umap_traits<winrt::hstring,TileInfo const,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,TileInfo const>>,0>>(
    (char *)this + 96,
    &v13);
  *((_QWORD *)this + 20) = 0;
  *((_BYTE *)this + 168) = 0;
  std::vector<bond::blob>::vector<bond::blob>((char *)this + 176);
  *((_QWORD *)this + 25) = 0;
  wil::cloud_store::cloud_store((char *)this + 208);
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  Default = winrt::WindowsUdk::Storage::CloudStore::GetDefault();
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 248, Default);
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v13);
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (void **)&ppszPath,
    0);
  v5 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x4000u, 0, &ppszPath);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\cdsappdatastore.cpp",
      (const char *)(unsigned int)v5,
      v12);
  v13 = ppszPath;
  std::filesystem::path::path((__int64)v16, &v13);
  std::filesystem::path::operator/=<unsigned short [26],0>((__int64)v16);
  v6 = std::filesystem::path::lexically_normal(v16, v18);
  v7 = std::filesystem::path::wstring(v6, v17);
  v15[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
  v15[1] = *(_QWORD *)(v8 + 16);
  v9 = (CDSAppDataStore *)winrt::hstring::hstring(&v13, v15);
  if ( (CDSAppDataStore *)((char *)this + 256) != v9 )
  {
    v10 = *(_QWORD *)v9;
    *(_QWORD *)v9 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach((char *)this + 256, v10);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v13);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::_Tidy_deallocate(v18);
  std::wstring::_Tidy_deallocate(v16);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&ppszPath);
  return this;
}

```

## disassembly

```asm
0x180059f08  mov     [rsp-8+arg_8], rbx
0x180059f0d  mov     [rsp-8+arg_10], rsi
0x180059f12  push    rbp
0x180059f13  push    rdi
0x180059f14  push    r14
0x180059f16  lea     rbp, [rsp-47h]
0x180059f1b  sub     rsp, 0D0h
0x180059f22  mov     rax, cs:__security_cookie
0x180059f29  xor     rax, rsp
0x180059f2c  mov     [rbp+57h+var_18], rax
0x180059f30  mov     rsi, rcx
0x180059f33  mov     [rbp+57h+var_80], rcx
0x180059f37  lea     rax, ??_7CDSAppDataStore@@6B@; const CDSAppDataStore::`vftable'
0x180059f3e  mov     [rcx], rax
0x180059f41  xor     r14d, r14d
0x180059f44  mov     [rcx+8], r14b
0x180059f48  lea     rdi, [rcx+10h]
0x180059f4c  mov     [rbp+57h+var_A0], rdi
0x180059f50  mov     [rdi], r14d
0x180059f53  lea     rcx, [rdi+8]
0x180059f57  call    ??0?$list@U?$pair@$$CBUhstring@winrt@@$$CBUAppMetaData@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@$$CBUAppMetaData@@@std@@@2@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUhstring@winrt@@$$CBUAppMetaData@@@std@@@1@@Z; std::list<std::pair<winrt::hstring const,AppMetaData const>>::list<std::pair<winrt::hstring const,AppMetaData const>>(std::allocator<std::pair<winrt::hstring const,AppMetaData const>> const &)
0x180059f5c  nop
0x180059f5d  lea     rcx, [rdi+18h]
0x180059f61  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x180059f66  nop
0x180059f67  mov     qword ptr [rdi+30h], 7
0x180059f6f  mov     qword ptr [rdi+38h], 8
0x180059f77  mov     dword ptr [rdi], 3F800000h
0x180059f7d  mov     r8, [rdi+8]
0x180059f81  lea     edx, [r14+10h]
0x180059f85  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180059f8a  nop
0x180059f8b  mov     [rsi+50h], r14
0x180059f8f  mov     [rsi+58h], r14b
0x180059f93  lea     rcx, [rsi+60h]
0x180059f97  mov     dword ptr [rbp+57h+var_A0], r14d
0x180059f9b  lea     rdx, [rbp+57h+var_A0]
0x180059f9f  call    ??0?$_Hash@V?$_Umap_traits@Uhstring@winrt@@$$CBUTileInfo@@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@$$CBUTileInfo@@@std@@@5@$0A@@std@@@std@@IEAA@AEBV?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@1@AEBV?$allocator@U?$pair@$$CBUhstring@winrt@@$$CBUTileInfo@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<winrt::hstring,TileInfo const,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,TileInfo const>>,0>>::_Hash<std::_Umap_traits<winrt::hstring,TileInfo const,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,TileInfo const>>,0>>(std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>> const &,std::allocator<std::pair<winrt::hstring const,TileInfo const>> const &)
0x180059fa4  nop
0x180059fa5  mov     [rsi+0A0h], r14
0x180059fac  mov     [rsi+0A8h], r14b
0x180059fb3  lea     rcx, [rsi+0B0h]
0x180059fba  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x180059fbf  nop
0x180059fc0  mov     [rsi+0C8h], r14
0x180059fc7  lea     rcx, [rsi+0D0h]
0x180059fce  mov     [rsp+0E0h+var_B0], r14d
0x180059fd3  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x180059fd8  nop
0x180059fd9  lea     rbx, [rsi+0F8h]
0x180059fe0  mov     [rbx], r14
0x180059fe3  lea     rdi, [rsi+100h]
0x180059fea  mov     [rdi], r14
0x180059fed  lea     rcx, [rbp+57h+var_A0]
0x180059ff1  call    ?GetDefault@CloudStore@Storage@WindowsUdk@winrt@@SA@XZ; winrt::WindowsUdk::Storage::CloudStore::GetDefault(void)
0x180059ff6  mov     rdx, rax
0x180059ff9  mov     rcx, rbx
0x180059ffc  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18005a001  lea     rcx, [rbp+57h+var_A0]; this
0x18005a005  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18005a00a  mov     [rbp+57h+ppszPath], r14
0x18005a00e  xor     edx, edx
0x18005a010  lea     rcx, [rbp+57h+ppszPath]
0x18005a014  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005a019  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x18005a01d  xor     r8d, r8d; hToken
0x18005a020  mov     edx, 4000h; dwFlags
0x18005a025  lea     rcx, FOLDERID_LocalAppData; rfid
0x18005a02c  call    cs:__imp_SHGetKnownFolderPath
0x18005a032  mov     rcx, [rbp+5Fh]; this
0x18005a036  test    eax, eax
0x18005a038  jns     short loc_18005A04E
0x18005a03a  mov     r9d, eax; char *
0x18005a03d  lea     r8, aPcshellShellCl_8; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x18005a044  lea     edx, [r14+4Eh]; void *
0x18005a048  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005a04e  mov     rax, [rbp+57h+ppszPath]
0x18005a052  mov     [rbp+57h+var_A0], rax
0x18005a056  lea     rdx, [rbp+57h+var_A0]
0x18005a05a  lea     rcx, [rbp+57h+var_78]
0x18005a05e  call    ??$?0PEAG$0A@@path@filesystem@std@@QEAA@AEBQEAGW4format@012@@Z; std::filesystem::path::path(ushort * const &,std::filesystem::path::format)
0x18005a063  nop
0x18005a064  lea     rcx, [rbp+57h+var_78]
0x18005a068  call    ??$?_0$$BY0BK@G$0A@@path@filesystem@std@@QEAAAEAV012@AEAY0BK@$$CBG@Z; std::filesystem::path::operator/=<ushort [26],0>(ushort const (&)[26])
0x18005a06d  lea     rdx, [rbp+57h+var_38]
0x18005a071  lea     rcx, [rbp+57h+var_78]
0x18005a075  call    ?lexically_normal@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::lexically_normal(void)
0x18005a07a  nop
0x18005a07b  lea     rdx, [rbp+57h+var_58]
0x18005a07f  mov     rcx, rax
0x18005a082  call    ?wstring@path@filesystem@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::filesystem::path::wstring(void)
0x18005a087  mov     rdx, rax
0x18005a08a  mov     rcx, rax
0x18005a08d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005a092  mov     [rbp+57h+var_90], rax
0x18005a096  mov     rax, [rdx+10h]
0x18005a09a  mov     [rbp+57h+var_88], rax
0x18005a09e  lea     rdx, [rbp+57h+var_90]
0x18005a0a2  lea     rcx, [rbp+57h+var_A0]
0x18005a0a6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18005a0ab  cmp     rdi, rax
0x18005a0ae  jz      short loc_18005A0BE
0x18005a0b0  mov     rdx, [rax]
0x18005a0b3  mov     [rax], r14
0x18005a0b6  mov     rcx, rdi
0x18005a0b9  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18005a0be  lea     rcx, [rbp+57h+var_A0]
0x18005a0c2  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18005a0c7  nop
0x18005a0c8  lea     rcx, [rbp+57h+var_58]
0x18005a0cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005a0d1  nop
0x18005a0d2  lea     rcx, [rbp+57h+var_38]
0x18005a0d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005a0db  nop
0x18005a0dc  lea     rcx, [rbp+57h+var_78]
0x18005a0e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005a0e5  nop
0x18005a0e6  lea     rcx, [rbp+57h+ppszPath]
0x18005a0ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005a0ef  nop
0x18005a0f0  mov     rax, rsi
0x18005a0f3  mov     rcx, [rbp+57h+var_18]
0x18005a0f7  xor     rcx, rsp; StackCookie
0x18005a0fa  call    __security_check_cookie
0x18005a0ff  lea     r11, [rsp+0E0h+var_10]
0x18005a107  mov     rbx, [r11+28h]
0x18005a10b  mov     rsi, [r11+30h]
0x18005a10f  mov     rsp, r11
0x18005a112  pop     r14
0x18005a114  pop     rdi
0x18005a115  pop     rbp
0x18005a116  retn
```
