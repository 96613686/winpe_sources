# Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)

- ea: `0x18002f4c8`
- end: `0x18002f687`
- name: `?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z`
- size: `447`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180029960`
- `0x18002a438`
- `0x18002bd90`
- `0x180034dfc`
- `0x180035308`

## callees

- `0x180003c80`
- `0x18000f9e4`
- `0x18001b444`
- `0x1800205b8`
- `0x180020a80`
- `0x180021348`
- `0x180021550`
- `0x1800236ac`
- `0x180023b38`
- `0x180023bc0`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002f58a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002f58a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f539`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f539`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f615`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f615`

## string_xrefs

- `0x18002f59b`: `onecore\base\devices\cam\core\registryhelpers.cpp`
- `0x18002f5bd`: `onecore\base\devices\cam\core\registryhelpers.cpp`
- `0x18002f675`: `onecore\base\devices\cam\core\registryhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(_QWORD *a1, HKEY a2, const WCHAR *a3)
{
  __int64 v6; // r8
  unsigned int v7; // eax
  unsigned int v8; // eax
  DWORD i; // edi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  WCHAR *v13; // rax
  unsigned int v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  unsigned int phkResultb; // [rsp+20h] [rbp-59h]
  DWORD cSubKeys; // [rsp+60h] [rbp-19h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-15h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-11h] BYREF
  HKEY v22; // [rsp+70h] [rbp-9h] BYREF
  int v23; // [rsp+78h] [rbp-1h]
  _QWORD *v24; // [rsp+80h] [rbp+7h]
  _BYTE v25[32]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v24 = a1;
  v22 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>(a1);
  v23 = 1;
  if ( !v6 )
    goto LABEL_4;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v22,
    0);
  v7 = RegOpenKeyExW(a2, a3, 0, 0x20119u, &v22);
  if ( !v7 )
  {
    a2 = v22;
LABEL_4:
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v8 = RegQueryInfoKeyW(a2, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\registryhelpers.cpp",
        (const char *)v8,
        phkResulta);
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = cbMaxSubKeyLen + 1;
      std::wstring::wstring(v25, cbMaxSubKeyLen + 1);
      v13 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25, v10, v11, v12);
      v14 = RegEnumKeyExW(a2, i, v13, &cchName, 0, 0, 0, 0);
      if ( v14 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x5A,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\registryhelpers.cpp",
          (const char *)v14,
          phkResultb);
      std::wstring::resize(v25, cchName);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a1, v25);
      std::wstring::_Tidy_deallocate(v25);
    }
    goto LABEL_11;
  }
  if ( v7 != 2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\registryhelpers.cpp",
      (const char *)v7,
      phkResult);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
  return a1;
}

```

## disassembly

```asm
0x18002f4c8  push    rbp
0x18002f4ca  push    rbx
0x18002f4cb  push    rsi
0x18002f4cc  push    rdi
0x18002f4cd  push    r14
0x18002f4cf  lea     rbp, [rsp-37h]
0x18002f4d4  sub     rsp, 0B0h
0x18002f4db  mov     rax, cs:__security_cookie
0x18002f4e2  xor     rax, rsp
0x18002f4e5  mov     [rbp+57h+var_28], rax
0x18002f4e9  mov     rdi, r8
0x18002f4ec  mov     rsi, rdx
0x18002f4ef  mov     rbx, rcx
0x18002f4f2  mov     [rbp+57h+var_50], rcx
0x18002f4f6  mov     [rbp+57h+var_58], 1
0x18002f4fd  xor     r14d, r14d
0x18002f500  mov     [rbp+57h+var_60], r14
0x18002f504  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>(std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>> const &)
0x18002f509  nop
0x18002f50a  mov     [rbp+57h+var_58], 1
0x18002f511  test    r8, r8
0x18002f514  jz      short loc_18002F547
0x18002f516  xor     edx, edx
0x18002f518  lea     rcx, [rbp+57h+var_60]
0x18002f51c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002f521  lea     rax, [rbp+57h+var_60]
0x18002f525  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18002f52a  mov     r9d, 20119h; samDesired
0x18002f530  xor     r8d, r8d; ulOptions
0x18002f533  mov     rdx, rdi; lpSubKey
0x18002f536  mov     rcx, rsi; hKey
0x18002f539  call    cs:__imp_RegOpenKeyExW
0x18002f53f  test    eax, eax
0x18002f541  jnz     short loc_18002F5AD
0x18002f543  mov     rsi, [rbp+57h+var_60]
0x18002f547  mov     [rbp+57h+cSubKeys], r14d
0x18002f54b  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x18002f54f  mov     [rsp+0D0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18002f554  mov     [rsp+0D0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18002f559  mov     [rsp+0D0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18002f55e  mov     [rsp+0D0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18002f563  mov     [rsp+0D0h+lpcValues], r14; lpcValues
0x18002f568  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18002f56d  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18002f571  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18002f576  lea     rax, [rbp+57h+cSubKeys]
0x18002f57a  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18002f57f  xor     r9d, r9d; lpReserved
0x18002f582  xor     r8d, r8d; lpcchClass
0x18002f585  xor     edx, edx; lpClass
0x18002f587  mov     rcx, rsi; hKey
0x18002f58a  call    cs:__imp_RegQueryInfoKeyW
0x18002f590  mov     rcx, [rbp+5Fh]; this
0x18002f594  test    eax, eax
0x18002f596  jz      short loc_18002F5CF
0x18002f598  mov     r9d, eax; char *
0x18002f59b  lea     r8, aOnecoreBaseDev_7; "onecore\\base\\devices\\cam\\core\\regi"...
0x18002f5a2  mov     edx, 49h ; 'I'; void *
0x18002f5a7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002f5ad  cmp     eax, 2
0x18002f5b0  jz      loc_18002F64C
0x18002f5b6  mov     rcx, [rbp+5Fh]; this
0x18002f5ba  mov     r9d, eax; char *
0x18002f5bd  lea     r8, aOnecoreBaseDev_7; "onecore\\base\\devices\\cam\\core\\regi"...
0x18002f5c4  mov     edx, 31h ; '1'; void *
0x18002f5c9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002f5cf  mov     edi, r14d
0x18002f5d2  cmp     [rbp+57h+cSubKeys], r14d
0x18002f5d6  jbe     short loc_18002F64C
0x18002f5d8  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18002f5db  inc     eax
0x18002f5dd  mov     [rbp+57h+cchName], eax
0x18002f5e0  mov     edx, eax
0x18002f5e2  lea     rcx, [rbp+57h+var_48]
0x18002f5e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18002f5eb  nop
0x18002f5ec  lea     rcx, [rbp+57h+var_48]
0x18002f5f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f5f5  mov     r8, rax; lpName
0x18002f5f8  mov     [rsp+0D0h+lpcValues], r14; lpftLastWriteTime
0x18002f5fd  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpcchClass
0x18002f602  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r14; lpClass
0x18002f607  mov     [rsp+0D0h+phkResult], r14; unsigned int
0x18002f60c  lea     r9, [rbp+57h+cchName]; lpcchName
0x18002f610  mov     edx, edi; dwIndex
0x18002f612  mov     rcx, rsi; hKey
0x18002f615  call    cs:__imp_RegEnumKeyExW
0x18002f61b  mov     rcx, [rbp+5Fh]; this
0x18002f61f  test    eax, eax
0x18002f621  jnz     short loc_18002F672
0x18002f623  mov     edx, [rbp+57h+cchName]
0x18002f626  lea     rcx, [rbp+57h+var_48]
0x18002f62a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002f62f  lea     rdx, [rbp+57h+var_48]
0x18002f633  mov     rcx, rbx
0x18002f636  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18002f63b  nop
0x18002f63c  lea     rcx, [rbp+57h+var_48]
0x18002f640  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f645  inc     edi
0x18002f647  cmp     edi, [rbp+57h+cSubKeys]
0x18002f64a  jb      short loc_18002F5D8
0x18002f64c  lea     rcx, [rbp+57h+var_60]
0x18002f650  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002f655  mov     rax, rbx
0x18002f658  mov     rcx, [rbp+57h+var_28]
0x18002f65c  xor     rcx, rsp; StackCookie
0x18002f65f  call    __security_check_cookie
0x18002f664  add     rsp, 0B0h
0x18002f66b  pop     r14
0x18002f66d  pop     rdi
0x18002f66e  pop     rsi
0x18002f66f  pop     rbx
0x18002f670  pop     rbp
0x18002f671  retn
0x18002f672  mov     r9d, eax; char *
0x18002f675  lea     r8, aOnecoreBaseDev_7; "onecore\\base\\devices\\cam\\core\\regi"...
0x18002f67c  mov     edx, 5Ah ; 'Z'; void *
0x18002f681  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
