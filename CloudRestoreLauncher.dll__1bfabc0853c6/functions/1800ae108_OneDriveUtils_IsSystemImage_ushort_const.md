# OneDriveUtils::IsSystemImage(ushort const *)

- ea: `0x1800ae108`
- end: `0x1800ae272`
- name: `?IsSystemImage@OneDriveUtils@@YA_NPEBG@Z`
- size: `362`
- prototype: `bool __fastcall(OneDriveUtils *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a96f0`
- `0x1800bca00`

## callees

- `0x18000c6e0`
- `0x18001409c`
- `0x18001666c`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001da4c`
- `0x18001faa8`
- `0x18004712c`
- `0x180066ce8`
- `0x1800a442c`
- `0x1800ae108`
- `0x1800b1498`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800ae1f7`
- `KERNEL32!CompareStringOrdinal` at `0x1800ae1f7`
- `SHELL32!SHGetKnownFolderPath` at `0x1800ae160`
- `SHELL32!SHGetKnownFolderPath` at `0x1800ae160`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall OneDriveUtils::IsSystemImage(WCHAR *this, const unsigned __int16 *a2)
{
  HRESULT v2; // eax
  __int64 v3; // rax
  const WCHAR *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-79h]
  PWSTR ppszPath; // [rsp+30h] [rbp-69h] BYREF
  PWSTR v11; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v13[16]; // [rsp+60h] [rbp-39h] BYREF
  int cchCount1; // [rsp+70h] [rbp-29h]
  _BYTE v15[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v16[32]; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v17[32]; // [rsp+C0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v11 = this;
  std::filesystem::path::path((__int64)v15, &v11);
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v2 = SHGetKnownFolderPath(&FOLDERID_Windows, 0x4000u, 0, &ppszPath);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
      (const char *)(unsigned int)v2,
      bIgnoreCase);
  v11 = ppszPath;
  std::filesystem::path::path((__int64)v12, &v11);
  std::wstring::_Append<unsigned short>(v12, L"\\Web\\", 5);
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  std::wstring::wstring(v13, v3);
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  v5 = std::filesystem::path::parent_path(v15, v17);
  v6 = std::filesystem::path::wstring(v5, v16);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
  LOBYTE(v4) = CompareStringOrdinal(v7, cchCount1, v4, cchCount1, 1) == 2;
  std::wstring::_Tidy_deallocate(v16);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::_Tidy_deallocate(v13);
  std::wstring::_Tidy_deallocate(v12);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  std::wstring::_Tidy_deallocate(v15);
  return (char)v4;
}

```

## disassembly

```asm
0x1800ae108  mov     [rsp-8+arg_8], rbx
0x1800ae10d  push    rbp
0x1800ae10e  lea     rbp, [rsp-57h]
0x1800ae113  sub     rsp, 0F0h
0x1800ae11a  mov     rax, cs:__security_cookie
0x1800ae121  xor     rax, rsp
0x1800ae124  mov     [rbp+57h+var_10], rax
0x1800ae128  mov     [rbp+57h+var_B8], rcx
0x1800ae12c  lea     rdx, [rbp+57h+var_B8]
0x1800ae130  lea     rcx, [rbp+57h+var_70]
0x1800ae134  call    ??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z; std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)
0x1800ae139  nop
0x1800ae13a  mov     [rbp+57h+ppszPath], 0
0x1800ae142  xor     edx, edx
0x1800ae144  lea     rcx, [rbp+57h+ppszPath]
0x1800ae148  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800ae14d  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x1800ae151  xor     r8d, r8d; hToken
0x1800ae154  mov     edx, 4000h; dwFlags
0x1800ae159  lea     rcx, FOLDERID_Windows; rfid
0x1800ae160  call    cs:__imp_SHGetKnownFolderPath
0x1800ae166  mov     rcx, [rbp+5Fh]; this
0x1800ae16a  test    eax, eax
0x1800ae16c  js      loc_1800AE25D
0x1800ae172  mov     rax, [rbp+57h+ppszPath]
0x1800ae176  mov     [rbp+57h+var_B8], rax
0x1800ae17a  lea     rdx, [rbp+57h+var_B8]
0x1800ae17e  lea     rcx, [rbp+57h+var_B0]
0x1800ae182  call    ??$?0PEAG$0A@@path@filesystem@std@@QEAA@AEBQEAGW4format@012@@Z; std::filesystem::path::path(ushort * const &,std::filesystem::path::format)
0x1800ae187  nop
0x1800ae188  mov     r8d, 5
0x1800ae18e  lea     rdx, aWeb; "\\Web\\"
0x1800ae195  lea     rcx, [rbp+57h+var_B0]
0x1800ae199  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ae19e  lea     rcx, [rbp+57h+var_B0]
0x1800ae1a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ae1a7  mov     rdx, rax
0x1800ae1aa  lea     rcx, [rbp+57h+var_90]
0x1800ae1ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ae1b3  nop
0x1800ae1b4  lea     rcx, [rbp+57h+var_B0]
0x1800ae1b8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ae1bd  mov     rbx, rax
0x1800ae1c0  lea     rdx, [rbp+57h+var_30]
0x1800ae1c4  lea     rcx, [rbp+57h+var_70]
0x1800ae1c8  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x1800ae1cd  nop
0x1800ae1ce  lea     rdx, [rbp+57h+var_50]
0x1800ae1d2  mov     rcx, rax
0x1800ae1d5  call    ?wstring@path@filesystem@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::filesystem::path::wstring(void)
0x1800ae1da  mov     rcx, rax
0x1800ae1dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ae1e2  mov     [rsp+0F0h+bIgnoreCase], 1; bIgnoreCase
0x1800ae1ea  mov     r9d, [rbp+57h+cchCount1]; cchCount2
0x1800ae1ee  mov     r8, rbx; lpString2
0x1800ae1f1  mov     edx, r9d; cchCount1
0x1800ae1f4  mov     rcx, rax; lpString1
0x1800ae1f7  call    cs:__imp_CompareStringOrdinal
0x1800ae1fd  cmp     eax, 2
0x1800ae200  setz    bl
0x1800ae203  lea     rcx, [rbp+57h+var_50]
0x1800ae207  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae20c  nop
0x1800ae20d  lea     rcx, [rbp+57h+var_30]
0x1800ae211  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae216  nop
0x1800ae217  lea     rcx, [rbp+57h+var_90]
0x1800ae21b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae220  nop
0x1800ae221  lea     rcx, [rbp+57h+var_B0]
0x1800ae225  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae22a  nop
0x1800ae22b  lea     rcx, [rbp+57h+ppszPath]
0x1800ae22f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ae234  nop
0x1800ae235  lea     rcx, [rbp+57h+var_70]
0x1800ae239  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae23e  mov     al, bl
0x1800ae240  mov     rcx, [rbp+57h+var_10]
0x1800ae244  xor     rcx, rsp; StackCookie
0x1800ae247  call    __security_check_cookie
0x1800ae24c  mov     rbx, [rsp+0F0h+arg_8]
0x1800ae254  add     rsp, 0F0h
0x1800ae25b  pop     rbp
0x1800ae25c  retn
0x1800ae25d  mov     r9d, eax; char *
0x1800ae260  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ae267  mov     edx, 15Dh; void *
0x1800ae26c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
