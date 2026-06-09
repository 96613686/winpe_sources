# ThemeAppModelWrapper::CheckIfThemeFlaggedInRegistry(Windows::Internal::StateRepository::IAppExtension *,ushort const *,bool &,ulong &)

- ea: `0x180269a60`
- end: `0x180269d61`
- name: `?CheckIfThemeFlaggedInRegistry@ThemeAppModelWrapper@@SAJPEAUIAppExtension@StateRepository@Internal@Windows@@PEBGAEA_NAEAK@Z`
- size: `769`
- prototype: `static int(struct Windows::Internal::StateRepository::IAppExtension *, const unsigned __int16 *, bool *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180112930`
- `0x180115490`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x1800234f8`
- `0x18002373c`
- `0x18002b9f0`
- `0x18002e1f4`
- `0x180041004`
- `0x180228318`
- `0x180269a60`
- `0x18026a9e8`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180269c01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180269c01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180269ca4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180269ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269b84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269cfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269b84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269cfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180269d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180269c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180269c7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ThemeAppModelWrapper::CheckIfThemeFlaggedInRegistry(
        struct Windows::Internal::StateRepository::IAppExtension *a1,
        const unsigned __int16 *a2,
        bool *a3,
        BYTE *a4)
{
  __int64 (__fastcall *v8)(struct Windows::Internal::StateRepository::IAppExtension *, HSTRING *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  int ExtensionKey; // eax
  unsigned int v13; // ebx
  const WCHAR *v14; // rax
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  const WCHAR *StringRawBuffer; // rax
  unsigned int v18; // eax
  unsigned int v19; // ebx
  int dwOptions; // [rsp+20h] [rbp-A8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-A8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-A8h]
  HSTRING string; // [rsp+50h] [rbp-78h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-68h] BYREF
  HKEY *p_hKey; // [rsp+68h] [rbp-60h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-58h] BYREF
  char v28; // [rsp+78h] [rbp-50h]
  _BYTE v29[32]; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *a3 = 0;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
      (const char *)0x80070057LL,
      dwOptions);
    return 2147942487LL;
  }
  string = 0;
  v8 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IAppExtension *, HSTRING *))(*(_QWORD *)a1 + 104LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(a1, &string);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
      (const char *)(unsigned int)v9,
      dwOptions);
    WindowsDeleteString(string);
    return v10;
  }
  std::wstring::wstring(v29);
  ExtensionKey = GetExtensionKey(v11, &string, v29);
  v13 = ExtensionKey;
  if ( ExtensionKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
      (const char *)(unsigned int)ExtensionKey,
      dwOptions);
    std::wstring::_Tidy_deallocate(v29);
    WindowsDeleteString(string);
    return v13;
  }
  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v28 = 1;
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v29);
  v15 = RegCreateKeyExW(HKEY_CURRENT_USER, v14, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v15 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1F3,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
            (const char *)v15,
            dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v29);
    WindowsDeleteString(string);
    return v16;
  }
  cbData = 4;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v18 = RegQueryValueExW(hKey, StringRawBuffer, 0, 0, a4, &cbData);
  if ( v18 )
  {
    if ( v18 != 2 )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1FD,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
              (const char *)v18,
              dwOptionsb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::_Tidy_deallocate(v29);
      WindowsDeleteString(string);
      return v19;
    }
  }
  else
  {
    *a3 = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v29);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180269a60  mov     [rsp+arg_8], rbx
0x180269a65  push    rsi
0x180269a66  push    rdi
0x180269a67  push    r14
0x180269a69  sub     rsp, 0B0h
0x180269a70  mov     rax, cs:__security_cookie
0x180269a77  xor     rax, rsp
0x180269a7a  mov     [rsp+0C8h+var_28], rax
0x180269a82  mov     r14, r9
0x180269a85  mov     rsi, r8
0x180269a88  mov     rdi, rcx
0x180269a8b  mov     byte ptr [r8], 0
0x180269a8f  test    rcx, rcx
0x180269a92  jnz     short loc_180269ABC
0x180269a94  mov     rcx, [rsp+0C8h]; this
0x180269a9c  mov     ebx, 80070057h
0x180269aa1  mov     r9d, ebx; char *
0x180269aa4  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269aab  mov     edx, 1E7h; void *
0x180269ab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180269ab5  mov     eax, ebx
0x180269ab7  jmp     loc_180269D3C
0x180269abc  mov     [rsp+0C8h+string], 0
0x180269ac5  mov     rax, [rcx]
0x180269ac8  mov     rbx, [rax+68h]
0x180269acc  xor     ecx, ecx; string
0x180269ace  call    cs:__imp_WindowsDeleteString
0x180269ad5  nop     dword ptr [rax+rax+00h]
0x180269ada  mov     [rsp+0C8h+string], 0
0x180269ae3  lea     rdx, [rsp+0C8h+string]
0x180269ae8  mov     rcx, rdi
0x180269aeb  mov     rax, rbx
0x180269aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269af3  mov     ebx, eax
0x180269af5  test    eax, eax
0x180269af7  jns     short loc_180269B2E
0x180269af9  mov     rcx, [rsp+0C8h]; this
0x180269b01  mov     r9d, eax; char *
0x180269b04  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269b0b  mov     edx, 1EBh; void *
0x180269b10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180269b15  nop
0x180269b16  mov     rcx, [rsp+0C8h+string]; string
0x180269b1b  call    cs:__imp_WindowsDeleteString
0x180269b22  nop     dword ptr [rax+rax+00h]
0x180269b27  mov     eax, ebx
0x180269b29  jmp     loc_180269D3C
0x180269b2e  lea     rcx, [rsp+0C8h+var_48]; void *
0x180269b36  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180269b3b  nop
0x180269b3c  lea     r8, [rsp+0C8h+var_48]
0x180269b44  lea     rdx, [rsp+0C8h+string]
0x180269b49  call    ?GetExtensionKey@@YAJPEBGAEAVHString@Wrappers@WRL@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetExtensionKey(ushort const *,Microsoft::WRL::Wrappers::HString &,std::wstring &)
0x180269b4e  mov     ebx, eax
0x180269b50  test    eax, eax
0x180269b52  jns     short loc_180269B97
0x180269b54  mov     rcx, [rsp+0C8h]; this
0x180269b5c  mov     r9d, eax; char *
0x180269b5f  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269b66  mov     edx, 1EEh; void *
0x180269b6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180269b70  nop
0x180269b71  lea     rcx, [rsp+0C8h+var_48]
0x180269b79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180269b7e  nop
0x180269b7f  mov     rcx, [rsp+0C8h+string]; string
0x180269b84  call    cs:__imp_WindowsDeleteString
0x180269b8b  nop     dword ptr [rax+rax+00h]
0x180269b90  mov     eax, ebx
0x180269b92  jmp     loc_180269D3C
0x180269b97  mov     [rsp+0C8h+hKey], 0
0x180269ba0  lea     rax, [rsp+0C8h+hKey]
0x180269ba5  mov     [rsp+0C8h+var_60], rax
0x180269baa  mov     [rsp+0C8h+var_58], 0
0x180269bb3  mov     [rsp+0C8h+var_50], 1
0x180269bb8  lea     rcx, [rsp+0C8h+var_48]
0x180269bc0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180269bc5  mov     rdx, rax; lpSubKey
0x180269bc8  mov     [rsp+0C8h+lpdwDisposition], 0; lpdwDisposition
0x180269bd1  lea     rax, [rsp+0C8h+var_58]
0x180269bd6  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180269bdb  mov     [rsp+0C8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180269be4  mov     [rsp+0C8h+samDesired], 0F003Fh; samDesired
0x180269bec  mov     [rsp+0C8h+dwOptions], 0; unsigned int
0x180269bf4  xor     r9d, r9d; lpClass
0x180269bf7  xor     r8d, r8d; Reserved
0x180269bfa  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180269c01  call    cs:__imp_RegCreateKeyExW
0x180269c08  nop     dword ptr [rax+rax+00h]
0x180269c0d  mov     ebx, eax
0x180269c0f  lea     rcx, [rsp+0C8h+var_60]
0x180269c14  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180269c19  test    ebx, ebx
0x180269c1b  jz      short loc_180269C6C
0x180269c1d  mov     rcx, [rsp+0C8h]; this
0x180269c25  mov     r9d, ebx; char *
0x180269c28  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269c2f  mov     edx, 1F3h; void *
0x180269c34  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180269c39  mov     ebx, eax
0x180269c3b  lea     rcx, [rsp+0C8h+hKey]
0x180269c40  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180269c45  nop
0x180269c46  lea     rcx, [rsp+0C8h+var_48]
0x180269c4e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180269c53  nop
0x180269c54  mov     rcx, [rsp+0C8h+string]; string
0x180269c59  call    cs:__imp_WindowsDeleteString
0x180269c60  nop     dword ptr [rax+rax+00h]
0x180269c65  mov     eax, ebx
0x180269c67  jmp     loc_180269D3C
0x180269c6c  mov     [rsp+0C8h+cbData], 4
0x180269c74  xor     edx, edx; length
0x180269c76  mov     rcx, [rsp+0C8h+string]; string
0x180269c7b  call    cs:__imp_WindowsGetStringRawBuffer
0x180269c82  nop     dword ptr [rax+rax+00h]
0x180269c87  lea     rcx, [rsp+0C8h+cbData]
0x180269c8c  mov     qword ptr [rsp+0C8h+samDesired], rcx; lpcbData
0x180269c91  mov     qword ptr [rsp+0C8h+dwOptions], r14; unsigned int
0x180269c96  xor     r9d, r9d; lpType
0x180269c99  xor     r8d, r8d; lpReserved
0x180269c9c  mov     rdx, rax; lpValueName
0x180269c9f  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180269ca4  call    cs:__imp_RegQueryValueExW
0x180269cab  nop     dword ptr [rax+rax+00h]
0x180269cb0  test    eax, eax
0x180269cb2  jnz     short loc_180269CB9
0x180269cb4  mov     byte ptr [rsi], 1
0x180269cb7  jmp     short loc_180269D0A
0x180269cb9  cmp     eax, 2
0x180269cbc  jz      short loc_180269D0A
0x180269cbe  mov     rcx, [rsp+0C8h]; this
0x180269cc6  mov     r9d, eax; char *
0x180269cc9  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269cd0  mov     edx, 1FDh; void *
0x180269cd5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180269cda  mov     ebx, eax
0x180269cdc  lea     rcx, [rsp+0C8h+hKey]
0x180269ce1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180269ce6  nop
0x180269ce7  lea     rcx, [rsp+0C8h+var_48]
0x180269cef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180269cf4  nop
0x180269cf5  mov     rcx, [rsp+0C8h+string]; string
0x180269cfa  call    cs:__imp_WindowsDeleteString
0x180269d01  nop     dword ptr [rax+rax+00h]
0x180269d06  mov     eax, ebx
0x180269d08  jmp     short loc_180269D3C
0x180269d0a  lea     rcx, [rsp+0C8h+hKey]
0x180269d0f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180269d14  nop
0x180269d15  lea     rcx, [rsp+0C8h+var_48]
0x180269d1d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180269d22  nop
0x180269d23  mov     rcx, [rsp+0C8h+string]; string
0x180269d28  call    cs:__imp_WindowsDeleteString
0x180269d2f  nop     dword ptr [rax+rax+00h]
0x180269d34  xor     eax, eax
0x180269d36  jmp     short loc_180269D3C
0x180269d38  mov     eax, [rsp+0C8h+cbData]
0x180269d3c  mov     rcx, [rsp+0C8h+var_28]
0x180269d44  xor     rcx, rsp; StackCookie
0x180269d47  call    __security_check_cookie
0x180269d4c  mov     rbx, [rsp+0C8h+arg_8]
0x180269d54  add     rsp, 0B0h
0x180269d5b  pop     r14
0x180269d5d  pop     rdi
0x180269d5e  pop     rsi
0x180269d5f  retn
```
