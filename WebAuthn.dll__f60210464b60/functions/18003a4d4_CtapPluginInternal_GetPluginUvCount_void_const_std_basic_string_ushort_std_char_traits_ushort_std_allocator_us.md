# CtapPluginInternal::GetPluginUvCount(void * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong *)

- ea: `0x18003a4d4`
- end: `0x18003a72d`
- name: `?GetPluginUvCount@CtapPluginInternal@@YAJQEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAK@Z`
- size: `601`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033970`
- `0x1800db3b0`

## callees

- `0x1800328b8`
- `0x180036da4`
- `0x180037f6c`
- `0x18003a4d4`
- `0x18003a9e8`
- `0x18004349c`
- `0x18011c42c`
- `0x180121b94`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a664`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a664`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a68e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a68e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a582`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a582`

## string_xrefs

- `0x18003a521`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18003a597`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18003a5ed`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18003a6a3`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CtapPluginInternal::GetPluginUvCount(HANDLE token, _QWORD *lpSubKey, _DWORD *a3)
{
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v7; // edi
  __int64 result; // rax
  HKEY *v9; // rax
  const WCHAR *v10; // rdx
  unsigned int v11; // eax
  HKEY v12; // r8
  unsigned int v13; // edi
  int ShouldAllowPluginOperation; // eax
  unsigned int v15; // edi
  const char *v16; // r9
  unsigned int v17; // eax
  unsigned int v18; // edi
  int phkResult; // [rsp+20h] [rbp-68h]
  unsigned int phkResulta; // [rsp+20h] [rbp-68h]
  unsigned int phkResultb; // [rsp+20h] [rbp-68h]
  HKEY hkey; // [rsp+40h] [rbp-48h] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-3Ch] BYREF
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  _QWORD *v26; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v26 = lpSubKey;
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey((__int64)token, (__int64)&hKey);
  v7 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey >= 0 )
  {
    hkey = 0;
    v9 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
    if ( lpSubKey[3] <= 7u )
      v10 = (const WCHAR *)lpSubKey;
    else
      v10 = (const WCHAR *)*lpSubKey;
    v11 = RegOpenKeyExW(hKey, v10, 0, 0xF003Fu, v9);
    if ( v11 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xED7,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)v11,
              phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::_Tidy_deallocate(lpSubKey);
      return v13;
    }
    else
    {
      try
      {
        ShouldAllowPluginOperation = CtapPluginInternal::ShouldAllowPluginOperation(token, hkey, v12);
        v15 = ShouldAllowPluginOperation;
        if ( ShouldAllowPluginOperation >= 0 )
        {
          *(_DWORD *)Data = 0;
          pcbData = 4;
          if ( RegGetValueW(hkey, 0, L"UvCount", 0x10u, 0, Data, &pcbData) < 0
            && (v17 = RegSetValueExW(hkey, L"UvCount", 0, 4u, Data, 4u)) != 0 )
          {
            v18 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xEE1,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    (const char *)v17,
                    phkResultb);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            std::wstring::_Tidy_deallocate(lpSubKey);
            result = v18;
          }
          else
          {
            *a3 = *(_DWORD *)Data;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            std::wstring::_Tidy_deallocate(lpSubKey);
            result = 0;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xED8,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)ShouldAllowPluginOperation,
            phkResulta);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::wstring::_Tidy_deallocate(lpSubKey);
          result = v15;
        }
      }
      catch ( ... )
      {
        pcbData = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0xEE8,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    v16);
        std::wstring::_Tidy_deallocate(v26);
        return pcbData;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED4,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(lpSubKey);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18003a4d4  mov     r11, rsp
0x18003a4d7  mov     [r11+20h], rbx
0x18003a4db  push    rsi
0x18003a4dc  push    rdi
0x18003a4dd  push    r14
0x18003a4df  sub     rsp, 70h
0x18003a4e3  mov     rax, cs:__security_cookie
0x18003a4ea  xor     rax, rsp
0x18003a4ed  mov     [rsp+88h+var_28], rax
0x18003a4f2  mov     r14, r8
0x18003a4f5  mov     rbx, rdx
0x18003a4f8  mov     rsi, rcx
0x18003a4fb  mov     [r11-30h], rdx
0x18003a4ff  mov     qword ptr [r11-38h], 0
0x18003a507  lea     rdx, [r11-38h]
0x18003a50b  call    GetUserPluginAuthenticatorsRegKey
0x18003a510  mov     edi, eax
0x18003a512  test    eax, eax
0x18003a514  jns     short loc_18003A54D
0x18003a516  mov     rcx, [rsp+88h]; this
0x18003a51e  mov     r9d, eax; char *
0x18003a521  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003a528  mov     edx, 0ED4h; void *
0x18003a52d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a532  nop
0x18003a533  lea     rcx, [rsp+88h+hKey]
0x18003a538  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a53d  nop
0x18003a53e  mov     rcx, rbx
0x18003a541  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a546  mov     eax, edi
0x18003a548  jmp     loc_18003A70F
0x18003a54d  mov     [rsp+88h+hkey], 0
0x18003a556  lea     rcx, [rsp+88h+hkey]
0x18003a55b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18003a560  cmp     qword ptr [rbx+18h], 7
0x18003a565  jbe     short loc_18003A56C
0x18003a567  mov     rdx, [rbx]
0x18003a56a  jmp     short loc_18003A56F
0x18003a56c  mov     rdx, rbx; lpSubKey
0x18003a56f  mov     [rsp+88h+phkResult], rax; int
0x18003a574  mov     r9d, 0F003Fh; samDesired
0x18003a57a  xor     r8d, r8d; ulOptions
0x18003a57d  mov     rcx, [rsp+88h+hKey]; hKey
0x18003a582  call    cs:__imp_RegOpenKeyExW
0x18003a588  test    eax, eax
0x18003a58a  jz      short loc_18003A5CF
0x18003a58c  mov     rcx, [rsp+88h]; this
0x18003a594  mov     r9d, eax; char *
0x18003a597  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003a59e  mov     edx, 0ED7h; void *
0x18003a5a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003a5a8  mov     edi, eax
0x18003a5aa  lea     rcx, [rsp+88h+hkey]
0x18003a5af  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a5b4  nop
0x18003a5b5  lea     rcx, [rsp+88h+hKey]
0x18003a5ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a5bf  nop
0x18003a5c0  mov     rcx, rbx
0x18003a5c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a5c8  mov     eax, edi
0x18003a5ca  jmp     loc_18003A70F
0x18003a5cf  mov     rdx, [rsp+88h+hkey]; void *
0x18003a5d4  mov     rcx, rsi; token
0x18003a5d7  call    ?ShouldAllowPluginOperation@CtapPluginInternal@@YAJQEAXQEAUHKEY__@@@Z; CtapPluginInternal::ShouldAllowPluginOperation(void * const,HKEY__ * const)
0x18003a5dc  mov     edi, eax
0x18003a5de  test    eax, eax
0x18003a5e0  jns     short loc_18003A624
0x18003a5e2  mov     rcx, [rsp+88h]; this
0x18003a5ea  mov     r9d, eax; char *
0x18003a5ed  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003a5f4  mov     edx, 0ED8h; void *
0x18003a5f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a5fe  nop
0x18003a5ff  lea     rcx, [rsp+88h+hkey]
0x18003a604  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a609  nop
0x18003a60a  lea     rcx, [rsp+88h+hKey]
0x18003a60f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a614  nop
0x18003a615  mov     rcx, rbx
0x18003a618  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a61d  mov     eax, edi
0x18003a61f  jmp     loc_18003A70F
0x18003a624  mov     dword ptr [rsp+88h+Data], 0
0x18003a62c  mov     edi, 4
0x18003a631  mov     [rsp+88h+var_3C], edi
0x18003a635  lea     rax, [rsp+88h+var_3C]
0x18003a63a  mov     [rsp+88h+pcbData], rax; pcbData
0x18003a63f  lea     rax, [rsp+88h+Data]
0x18003a644  mov     [rsp+88h+pvData], rax; pvData
0x18003a649  mov     [rsp+88h+phkResult], 0; pdwType
0x18003a652  lea     r9d, [rdi+0Ch]; dwFlags
0x18003a656  lea     r8, Value; "UvCount"
0x18003a65d  xor     edx, edx; lpSubKey
0x18003a65f  mov     rcx, [rsp+88h+hkey]; hkey
0x18003a664  call    cs:__imp_RegGetValueW
0x18003a66a  test    eax, eax
0x18003a66c  jns     short loc_18003A6D8
0x18003a66e  mov     dword ptr [rsp+88h+pvData], edi; cbData
0x18003a672  lea     rax, [rsp+88h+Data]
0x18003a677  mov     [rsp+88h+phkResult], rax; unsigned int
0x18003a67c  mov     r9d, edi; dwType
0x18003a67f  xor     r8d, r8d; Reserved
0x18003a682  lea     rdx, Value; "UvCount"
0x18003a689  mov     rcx, [rsp+88h+hkey]; hKey
0x18003a68e  call    cs:__imp_RegSetValueExW
0x18003a694  test    eax, eax
0x18003a696  jz      short loc_18003A6D8
0x18003a698  mov     rcx, [rsp+88h]; this
0x18003a6a0  mov     r9d, eax; char *
0x18003a6a3  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003a6aa  mov     edx, 0EE1h; void *
0x18003a6af  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003a6b4  mov     edi, eax
0x18003a6b6  lea     rcx, [rsp+88h+hkey]
0x18003a6bb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a6c0  nop
0x18003a6c1  lea     rcx, [rsp+88h+hKey]
0x18003a6c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a6cb  nop
0x18003a6cc  mov     rcx, rbx
0x18003a6cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a6d4  mov     eax, edi
0x18003a6d6  jmp     short loc_18003A70F
0x18003a6d8  mov     eax, dword ptr [rsp+88h+Data]
0x18003a6dc  mov     [r14], eax
0x18003a6df  lea     rcx, [rsp+88h+hkey]
0x18003a6e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a6e9  nop
0x18003a6ea  lea     rcx, [rsp+88h+hKey]
0x18003a6ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a6f4  nop
0x18003a6f5  mov     rcx, rbx
0x18003a6f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a6fd  xor     eax, eax
0x18003a6ff  jmp     short loc_18003A70F
0x18003a701  mov     rcx, [rsp+88h+var_30]
0x18003a706  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a70b  mov     eax, [rsp+88h+var_3C]
0x18003a70f  mov     rcx, [rsp+88h+var_28]
0x18003a714  xor     rcx, rsp; StackCookie
0x18003a717  call    __security_check_cookie
0x18003a71c  mov     rbx, [rsp+88h+arg_18]
0x18003a724  add     rsp, 70h
0x18003a728  pop     r14
0x18003a72a  pop     rdi
0x18003a72b  pop     rsi
0x18003a72c  retn
```
