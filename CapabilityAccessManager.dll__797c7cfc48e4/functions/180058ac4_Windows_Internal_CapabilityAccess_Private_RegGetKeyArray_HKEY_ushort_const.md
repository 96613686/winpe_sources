# Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)

- ea: `0x180058ac4`
- end: `0x180058c83`
- name: `?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z`
- size: `447`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18004a444`
- `0x18004c8e8`
- `0x18004cdac`
- `0x18004decc`
- `0x1800544c0`
- `0x1800553e8`
- `0x180056d40`
- `0x180085b18`
- `0x180086024`
- `0x1800b6dac`
- `0x1800b71cc`
- `0x1800b77c0`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18001d914`
- `0x180029408`
- `0x1800299c4`
- `0x18002aa28`
- `0x18002f280`
- `0x18003ce34`
- `0x18003cf4c`
- `0x18003f2d8`
- `0x180058ac4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180058c11`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180058c11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058b35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058b35`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180058b86`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180058b86`

## string_xrefs

- `0x180058b97`: `onecore\base\devices\cam\core\registryhelpers.cpp`
- `0x180058bb9`: `onecore\base\devices\cam\core\registryhelpers.cpp`
- `0x180058c71`: `onecore\base\devices\cam\core\registryhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(_QWORD *a1, HKEY a2, const WCHAR *a3)
{
  __int64 v6; // r8
  unsigned int v7; // eax
  unsigned int v8; // eax
  DWORD i; // edi
  WCHAR *v10; // rax
  unsigned int v11; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  unsigned int phkResultb; // [rsp+20h] [rbp-59h]
  DWORD cSubKeys; // [rsp+60h] [rbp-19h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-15h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-11h] BYREF
  HKEY v19; // [rsp+70h] [rbp-9h] BYREF
  int v20; // [rsp+78h] [rbp-1h]
  _QWORD *v21; // [rsp+80h] [rbp+7h]
  _BYTE v22[32]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v21 = a1;
  v19 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>(a1);
  v20 = 1;
  if ( !v6 )
    goto LABEL_4;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v19,
    0);
  v7 = RegOpenKeyExW(a2, a3, 0, 0x20119u, &v19);
  if ( !v7 )
  {
    a2 = v19;
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
      std::wstring::wstring(v22, cbMaxSubKeyLen + 1);
      v10 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
      v11 = RegEnumKeyExW(a2, i, v10, &cchName, 0, 0, 0, 0);
      if ( v11 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x5A,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\registryhelpers.cpp",
          (const char *)v11,
          phkResultb);
      std::wstring::resize(v22, cchName);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a1, v22);
      std::wstring::_Tidy_deallocate(v22);
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
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
  return a1;
}

```

## disassembly

```asm
0x180058ac4  push    rbp
0x180058ac6  push    rbx
0x180058ac7  push    rsi
0x180058ac8  push    rdi
0x180058ac9  push    r14
0x180058acb  lea     rbp, [rsp-37h]
0x180058ad0  sub     rsp, 0B0h
0x180058ad7  mov     rax, cs:__security_cookie
0x180058ade  xor     rax, rsp
0x180058ae1  mov     [rbp+57h+var_28], rax
0x180058ae5  mov     rdi, r8
0x180058ae8  mov     rsi, rdx
0x180058aeb  mov     rbx, rcx
0x180058aee  mov     [rbp+57h+var_50], rcx
0x180058af2  mov     [rbp+57h+var_58], 1
0x180058af9  xor     r14d, r14d
0x180058afc  mov     [rbp+57h+var_60], r14
0x180058b00  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>(std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>> const &)
0x180058b05  nop
0x180058b06  mov     [rbp+57h+var_58], 1
0x180058b0d  test    r8, r8
0x180058b10  jz      short loc_180058B43
0x180058b12  xor     edx, edx
0x180058b14  lea     rcx, [rbp+57h+var_60]
0x180058b18  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180058b1d  lea     rax, [rbp+57h+var_60]
0x180058b21  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x180058b26  mov     r9d, 20119h; samDesired
0x180058b2c  xor     r8d, r8d; ulOptions
0x180058b2f  mov     rdx, rdi; lpSubKey
0x180058b32  mov     rcx, rsi; hKey
0x180058b35  call    cs:__imp_RegOpenKeyExW
0x180058b3b  test    eax, eax
0x180058b3d  jnz     short loc_180058BA9
0x180058b3f  mov     rsi, [rbp+57h+var_60]
0x180058b43  mov     [rbp+57h+cSubKeys], r14d
0x180058b47  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x180058b4b  mov     [rsp+0D0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180058b50  mov     [rsp+0D0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180058b55  mov     [rsp+0D0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180058b5a  mov     [rsp+0D0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180058b5f  mov     [rsp+0D0h+lpcValues], r14; lpcValues
0x180058b64  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180058b69  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180058b6d  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180058b72  lea     rax, [rbp+57h+cSubKeys]
0x180058b76  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x180058b7b  xor     r9d, r9d; lpReserved
0x180058b7e  xor     r8d, r8d; lpcchClass
0x180058b81  xor     edx, edx; lpClass
0x180058b83  mov     rcx, rsi; hKey
0x180058b86  call    cs:__imp_RegQueryInfoKeyW
0x180058b8c  mov     rcx, [rbp+5Fh]; this
0x180058b90  test    eax, eax
0x180058b92  jz      short loc_180058BCB
0x180058b94  mov     r9d, eax; char *
0x180058b97  lea     r8, aOnecoreBaseDev_33; "onecore\\base\\devices\\cam\\core\\regi"...
0x180058b9e  mov     edx, 49h ; 'I'; void *
0x180058ba3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180058ba9  cmp     eax, 2
0x180058bac  jz      loc_180058C48
0x180058bb2  mov     rcx, [rbp+5Fh]; this
0x180058bb6  mov     r9d, eax; char *
0x180058bb9  lea     r8, aOnecoreBaseDev_33; "onecore\\base\\devices\\cam\\core\\regi"...
0x180058bc0  mov     edx, 31h ; '1'; void *
0x180058bc5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180058bcb  mov     edi, r14d
0x180058bce  cmp     [rbp+57h+cSubKeys], r14d
0x180058bd2  jbe     short loc_180058C48
0x180058bd4  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180058bd7  inc     eax
0x180058bd9  mov     [rbp+57h+cchName], eax
0x180058bdc  mov     edx, eax
0x180058bde  lea     rcx, [rbp+57h+var_48]
0x180058be2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180058be7  nop
0x180058be8  lea     rcx, [rbp+57h+var_48]
0x180058bec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180058bf1  mov     r8, rax; lpName
0x180058bf4  mov     [rsp+0D0h+lpcValues], r14; lpftLastWriteTime
0x180058bf9  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpcchClass
0x180058bfe  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r14; lpClass
0x180058c03  mov     [rsp+0D0h+phkResult], r14; unsigned int
0x180058c08  lea     r9, [rbp+57h+cchName]; lpcchName
0x180058c0c  mov     edx, edi; dwIndex
0x180058c0e  mov     rcx, rsi; hKey
0x180058c11  call    cs:__imp_RegEnumKeyExW
0x180058c17  mov     rcx, [rbp+5Fh]; this
0x180058c1b  test    eax, eax
0x180058c1d  jnz     short loc_180058C6E
0x180058c1f  mov     edx, [rbp+57h+cchName]
0x180058c22  lea     rcx, [rbp+57h+var_48]
0x180058c26  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180058c2b  lea     rdx, [rbp+57h+var_48]
0x180058c2f  mov     rcx, rbx
0x180058c32  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180058c37  nop
0x180058c38  lea     rcx, [rbp+57h+var_48]
0x180058c3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180058c41  inc     edi
0x180058c43  cmp     edi, [rbp+57h+cSubKeys]
0x180058c46  jb      short loc_180058BD4
0x180058c48  lea     rcx, [rbp+57h+var_60]
0x180058c4c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180058c51  mov     rax, rbx
0x180058c54  mov     rcx, [rbp+57h+var_28]
0x180058c58  xor     rcx, rsp; StackCookie
0x180058c5b  call    __security_check_cookie
0x180058c60  add     rsp, 0B0h
0x180058c67  pop     r14
0x180058c69  pop     rdi
0x180058c6a  pop     rsi
0x180058c6b  pop     rbx
0x180058c6c  pop     rbp
0x180058c6d  retn
0x180058c6e  mov     r9d, eax; char *
0x180058c71  lea     r8, aOnecoreBaseDev_33; "onecore\\base\\devices\\cam\\core\\regi"...
0x180058c78  mov     edx, 5Ah ; 'Z'; void *
0x180058c7d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
