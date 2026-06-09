# ThemeAppModelWrapper::FlagThemeInRegistry(Windows::Internal::StateRepository::IAppExtension *,ushort const *,ulong)

- ea: `0x18026a520`
- end: `0x18026a813`
- name: `?FlagThemeInRegistry@ThemeAppModelWrapper@@SAJPEAUIAppExtension@StateRepository@Internal@Windows@@PEBGK@Z`
- size: `755`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IAppExtension *, const unsigned __int16 *, unsigned int)`
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
- `0x18026a520`
- `0x18026a9e8`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18026a763`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18026a763`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026a6c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026a6c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a5d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a63f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a71d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a7af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a7dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a5d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a63f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a71d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a7af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a7dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026a737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026a737`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ThemeAppModelWrapper::FlagThemeInRegistry(
        struct Windows::Internal::StateRepository::IAppExtension *a1,
        const unsigned __int16 *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Internal::StateRepository::IAppExtension *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int ExtensionKey; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  const WCHAR *v13; // rax
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  const WCHAR *StringRawBuffer; // rax
  unsigned int v17; // eax
  unsigned int v18; // ebx
  int dwOptions; // [rsp+20h] [rbp-A8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-A8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-A8h]
  HSTRING string[2]; // [rsp+50h] [rbp-78h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-58h] BYREF
  HKEY *p_hKey; // [rsp+78h] [rbp-50h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-48h] BYREF
  char v27; // [rsp+88h] [rbp-40h]
  _BYTE v28[32]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_DWORD *)Data = 0;
  if ( a1 )
  {
    string[0] = 0;
    v4 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IAppExtension *, HSTRING *))(*(_QWORD *)a1 + 104LL);
    WindowsDeleteString(0);
    string[0] = 0;
    v5 = v4(a1, string);
    v6 = v5;
    if ( v5 >= 0 )
    {
      std::wstring::wstring(v28);
      ExtensionKey = GetExtensionKey(v7, string, v28);
      v12 = ExtensionKey;
      if ( ExtensionKey >= 0 )
      {
        hKey = 0;
        p_hKey = &hKey;
        phkResult = 0;
        v27 = 1;
        v13 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28, v9, v10, v11);
        v14 = RegCreateKeyExW(HKEY_CURRENT_USER, v13, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
        if ( v14 )
        {
          v15 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x210,
                  (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeap"
                                "pmodelwrapper.cpp",
                  (const char *)v14,
                  dwOptionsa);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::wstring::_Tidy_deallocate(v28);
          WindowsDeleteString(string[0]);
          return v15;
        }
        else
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
          v17 = RegSetValueExW(hKey, StringRawBuffer, 0, 4u, Data, 4u);
          if ( v17 )
          {
            v18 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x212,
                    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\theme"
                                  "appmodelwrapper.cpp",
                    (const char *)v17,
                    dwOptionsb);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            std::wstring::_Tidy_deallocate(v28);
            WindowsDeleteString(string[0]);
            return v18;
          }
          else
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            std::wstring::_Tidy_deallocate(v28);
            WindowsDeleteString(string[0]);
            return 0;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20C,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
          (const char *)(unsigned int)ExtensionKey,
          dwOptions);
        std::wstring::_Tidy_deallocate(v28);
        WindowsDeleteString(string[0]);
        return v12;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x209,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)v5,
        dwOptions);
      WindowsDeleteString(string[0]);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x205,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
      (const char *)0x80070057LL,
      dwOptions);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18026a520  mov     [rsp+arg_8], rbx
0x18026a525  push    rdi
0x18026a526  sub     rsp, 0C0h
0x18026a52d  mov     rax, cs:__security_cookie
0x18026a534  xor     rax, rsp
0x18026a537  mov     [rsp+0C8h+var_18], rax
0x18026a53f  mov     rdi, rcx
0x18026a542  mov     dword ptr [rsp+0C8h+Data], 0
0x18026a54a  test    rcx, rcx
0x18026a54d  jnz     short loc_18026A577
0x18026a54f  mov     rcx, [rsp+0C8h]; this
0x18026a557  mov     ebx, 80070057h
0x18026a55c  mov     r9d, ebx; char *
0x18026a55f  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a566  mov     edx, 205h; void *
0x18026a56b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026a570  mov     eax, ebx
0x18026a572  jmp     loc_18026A7F1
0x18026a577  mov     [rsp+0C8h+string], 0
0x18026a580  mov     rax, [rcx]
0x18026a583  mov     rbx, [rax+68h]
0x18026a587  xor     ecx, ecx; string
0x18026a589  call    cs:__imp_WindowsDeleteString
0x18026a590  nop     dword ptr [rax+rax+00h]
0x18026a595  mov     [rsp+0C8h+string], 0
0x18026a59e  lea     rdx, [rsp+0C8h+string]
0x18026a5a3  mov     rcx, rdi
0x18026a5a6  mov     rax, rbx
0x18026a5a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026a5ae  mov     ebx, eax
0x18026a5b0  test    eax, eax
0x18026a5b2  jns     short loc_18026A5E9
0x18026a5b4  mov     rcx, [rsp+0C8h]; this
0x18026a5bc  mov     r9d, eax; char *
0x18026a5bf  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a5c6  mov     edx, 209h; void *
0x18026a5cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026a5d0  nop
0x18026a5d1  mov     rcx, [rsp+0C8h+string]; string
0x18026a5d6  call    cs:__imp_WindowsDeleteString
0x18026a5dd  nop     dword ptr [rax+rax+00h]
0x18026a5e2  mov     eax, ebx
0x18026a5e4  jmp     loc_18026A7F1
0x18026a5e9  lea     rcx, [rsp+0C8h+var_38]; void *
0x18026a5f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18026a5f6  nop
0x18026a5f7  lea     r8, [rsp+0C8h+var_38]
0x18026a5ff  lea     rdx, [rsp+0C8h+string]
0x18026a604  call    ?GetExtensionKey@@YAJPEBGAEAVHString@Wrappers@WRL@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetExtensionKey(ushort const *,Microsoft::WRL::Wrappers::HString &,std::wstring &)
0x18026a609  mov     ebx, eax
0x18026a60b  test    eax, eax
0x18026a60d  jns     short loc_18026A652
0x18026a60f  mov     rcx, [rsp+0C8h]; this
0x18026a617  mov     r9d, eax; char *
0x18026a61a  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a621  mov     edx, 20Ch; void *
0x18026a626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026a62b  nop
0x18026a62c  lea     rcx, [rsp+0C8h+var_38]
0x18026a634  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026a639  nop
0x18026a63a  mov     rcx, [rsp+0C8h+string]; string
0x18026a63f  call    cs:__imp_WindowsDeleteString
0x18026a646  nop     dword ptr [rax+rax+00h]
0x18026a64b  mov     eax, ebx
0x18026a64d  jmp     loc_18026A7F1
0x18026a652  mov     [rsp+0C8h+hKey], 0
0x18026a65b  lea     rax, [rsp+0C8h+hKey]
0x18026a660  mov     [rsp+0C8h+var_50], rax
0x18026a665  mov     [rsp+0C8h+var_48], 0
0x18026a671  mov     [rsp+0C8h+var_40], 1
0x18026a679  lea     rcx, [rsp+0C8h+var_38]
0x18026a681  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18026a686  mov     rdx, rax; lpSubKey
0x18026a689  mov     [rsp+0C8h+lpdwDisposition], 0; lpdwDisposition
0x18026a692  lea     rax, [rsp+0C8h+var_48]
0x18026a69a  mov     [rsp+0C8h+phkResult], rax; phkResult
0x18026a69f  mov     [rsp+0C8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18026a6a8  mov     [rsp+0C8h+samDesired], 0F003Fh; samDesired
0x18026a6b0  mov     [rsp+0C8h+dwOptions], 0; unsigned int
0x18026a6b8  xor     r9d, r9d; lpClass
0x18026a6bb  xor     r8d, r8d; Reserved
0x18026a6be  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18026a6c5  call    cs:__imp_RegCreateKeyExW
0x18026a6cc  nop     dword ptr [rax+rax+00h]
0x18026a6d1  mov     ebx, eax
0x18026a6d3  lea     rcx, [rsp+0C8h+var_50]
0x18026a6d8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18026a6dd  test    ebx, ebx
0x18026a6df  jz      short loc_18026A730
0x18026a6e1  mov     rcx, [rsp+0C8h]; this
0x18026a6e9  mov     r9d, ebx; char *
0x18026a6ec  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a6f3  mov     edx, 210h; void *
0x18026a6f8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18026a6fd  mov     ebx, eax
0x18026a6ff  lea     rcx, [rsp+0C8h+hKey]
0x18026a704  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a709  nop
0x18026a70a  lea     rcx, [rsp+0C8h+var_38]
0x18026a712  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026a717  nop
0x18026a718  mov     rcx, [rsp+0C8h+string]; string
0x18026a71d  call    cs:__imp_WindowsDeleteString
0x18026a724  nop     dword ptr [rax+rax+00h]
0x18026a729  mov     eax, ebx
0x18026a72b  jmp     loc_18026A7F1
0x18026a730  xor     edx, edx; length
0x18026a732  mov     rcx, [rsp+0C8h+string]; string
0x18026a737  call    cs:__imp_WindowsGetStringRawBuffer
0x18026a73e  nop     dword ptr [rax+rax+00h]
0x18026a743  mov     r9d, 4; dwType
0x18026a749  mov     [rsp+0C8h+samDesired], r9d; cbData
0x18026a74e  lea     rcx, [rsp+0C8h+Data]
0x18026a753  mov     qword ptr [rsp+0C8h+dwOptions], rcx; unsigned int
0x18026a758  xor     r8d, r8d; Reserved
0x18026a75b  mov     rdx, rax; lpValueName
0x18026a75e  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18026a763  call    cs:__imp_RegSetValueExW
0x18026a76a  nop     dword ptr [rax+rax+00h]
0x18026a76f  test    eax, eax
0x18026a771  jz      short loc_18026A7BF
0x18026a773  mov     rcx, [rsp+0C8h]; this
0x18026a77b  mov     r9d, eax; char *
0x18026a77e  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a785  mov     edx, 212h; void *
0x18026a78a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18026a78f  mov     ebx, eax
0x18026a791  lea     rcx, [rsp+0C8h+hKey]
0x18026a796  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a79b  nop
0x18026a79c  lea     rcx, [rsp+0C8h+var_38]
0x18026a7a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026a7a9  nop
0x18026a7aa  mov     rcx, [rsp+0C8h+string]; string
0x18026a7af  call    cs:__imp_WindowsDeleteString
0x18026a7b6  nop     dword ptr [rax+rax+00h]
0x18026a7bb  mov     eax, ebx
0x18026a7bd  jmp     short loc_18026A7F1
0x18026a7bf  lea     rcx, [rsp+0C8h+hKey]
0x18026a7c4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a7c9  nop
0x18026a7ca  lea     rcx, [rsp+0C8h+var_38]
0x18026a7d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026a7d7  nop
0x18026a7d8  mov     rcx, [rsp+0C8h+string]; string
0x18026a7dd  call    cs:__imp_WindowsDeleteString
0x18026a7e4  nop     dword ptr [rax+rax+00h]
0x18026a7e9  xor     eax, eax
0x18026a7eb  jmp     short loc_18026A7F1
0x18026a7ed  mov     eax, dword ptr [rsp+0C8h+Data]
0x18026a7f1  mov     rcx, [rsp+0C8h+var_18]
0x18026a7f9  xor     rcx, rsp; StackCookie
0x18026a7fc  call    __security_check_cookie
0x18026a801  mov     rbx, [rsp+0C8h+arg_8]
0x18026a809  add     rsp, 0C0h
0x18026a810  pop     rdi
0x18026a811  retn
```
