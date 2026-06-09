# CtapPluginInternal::IncrementPluginUvCount(void * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18003a734`
- end: `0x18003a9e2`
- name: `?IncrementPluginUvCount@CtapPluginInternal@@YAJQEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033970`

## callees

- `0x1800328b8`
- `0x180036da4`
- `0x180037f6c`
- `0x18003a734`
- `0x18003a9e8`
- `0x18004349c`
- `0x18011c42c`
- `0x180121b94`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a8bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a8bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a8e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a94c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a8e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a94c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a7dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a7dd`

## string_xrefs

- `0x18003a77c`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18003a7ef`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18003a842`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18003a8f4`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18003a95e`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CtapPluginInternal::IncrementPluginUvCount(HANDLE token, _QWORD *lpSubKey)
{
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v5; // edi
  __int64 result; // rax
  HKEY *v7; // rax
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  HKEY v10; // r8
  unsigned int v11; // edi
  int ShouldAllowPluginOperation; // eax
  unsigned int v13; // edi
  const char *v14; // r9
  unsigned int v15; // eax
  unsigned int v16; // edi
  unsigned int v17; // eax
  unsigned int v18; // edi
  int phkResult; // [rsp+20h] [rbp-58h]
  unsigned int phkResulta; // [rsp+20h] [rbp-58h]
  unsigned int phkResultb; // [rsp+20h] [rbp-58h]
  unsigned int phkResultc; // [rsp+20h] [rbp-58h]
  BYTE Data[8]; // [rsp+40h] [rbp-38h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-20h] BYREF
  _QWORD *v27; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v27 = lpSubKey;
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey((__int64)token, (__int64)&hKey);
  v5 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey >= 0 )
  {
    hkey = 0;
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
    if ( lpSubKey[3] <= 7u )
      v8 = (const WCHAR *)lpSubKey;
    else
      v8 = (const WCHAR *)*lpSubKey;
    v9 = RegOpenKeyExW(hKey, v8, 0, 0xF003Fu, v7);
    if ( v9 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xEF3,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)v9,
              phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::_Tidy_deallocate(lpSubKey);
      return v11;
    }
    else
    {
      try
      {
        ShouldAllowPluginOperation = CtapPluginInternal::ShouldAllowPluginOperation(token, hkey, v10);
        v13 = ShouldAllowPluginOperation;
        if ( ShouldAllowPluginOperation >= 0 )
        {
          *(_DWORD *)Data = 0;
          pcbData = 4;
          if ( RegGetValueW(hkey, 0, L"UvCount", 0x10u, 0, Data, &pcbData) < 0
            && (v15 = RegSetValueExW(hkey, L"UvCount", 0, 4u, Data, 4u)) != 0 )
          {
            v16 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xEFD,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    (const char *)v15,
                    phkResultb);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            std::wstring::_Tidy_deallocate(lpSubKey);
            result = v16;
          }
          else
          {
            ++*(_DWORD *)Data;
            v17 = RegSetValueExW(hkey, L"UvCount", 0, 4u, Data, 4u);
            if ( v17 )
            {
              v18 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0xF03,
                      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                      (const char *)v17,
                      phkResultc);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              std::wstring::_Tidy_deallocate(lpSubKey);
              result = v18;
            }
            else
            {
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              std::wstring::_Tidy_deallocate(lpSubKey);
              result = 0;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEF4,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)ShouldAllowPluginOperation,
            phkResulta);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::wstring::_Tidy_deallocate(lpSubKey);
          result = v13;
        }
      }
      catch ( ... )
      {
        pcbData = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0xF07,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    v14);
        std::wstring::_Tidy_deallocate(v27);
        return pcbData;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF0,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(lpSubKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18003a734  mov     r11, rsp
0x18003a737  mov     [r11+18h], rbx
0x18003a73b  mov     [r11+20h], rsi
0x18003a73f  push    rdi
0x18003a740  sub     rsp, 70h
0x18003a744  mov     rax, cs:__security_cookie
0x18003a74b  xor     rax, rsp
0x18003a74e  mov     [rsp+78h+var_10], rax
0x18003a753  mov     rbx, rdx
0x18003a756  mov     rsi, rcx
0x18003a759  mov     [r11-18h], rdx
0x18003a75d  mov     qword ptr [r11-28h], 0
0x18003a765  lea     rdx, [r11-28h]
0x18003a769  call    GetUserPluginAuthenticatorsRegKey
0x18003a76e  mov     edi, eax
0x18003a770  test    eax, eax
0x18003a772  jns     short loc_18003A7A8
0x18003a774  mov     rcx, [rsp+78h]; this
0x18003a779  mov     r9d, eax; char *
0x18003a77c  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003a783  mov     edx, 0EF0h; void *
0x18003a788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a78d  nop
0x18003a78e  lea     rcx, [rsp+78h+hKey]
0x18003a793  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a798  nop
0x18003a799  mov     rcx, rbx
0x18003a79c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a7a1  mov     eax, edi
0x18003a7a3  jmp     loc_18003A9C3
0x18003a7a8  mov     [rsp+78h+hkey], 0
0x18003a7b1  lea     rcx, [rsp+78h+hkey]
0x18003a7b6  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18003a7bb  cmp     qword ptr [rbx+18h], 7
0x18003a7c0  jbe     short loc_18003A7C7
0x18003a7c2  mov     rdx, [rbx]
0x18003a7c5  jmp     short loc_18003A7CA
0x18003a7c7  mov     rdx, rbx; lpSubKey
0x18003a7ca  mov     [rsp+78h+phkResult], rax; int
0x18003a7cf  mov     r9d, 0F003Fh; samDesired
0x18003a7d5  xor     r8d, r8d; ulOptions
0x18003a7d8  mov     rcx, [rsp+78h+hKey]; hKey
0x18003a7dd  call    cs:__imp_RegOpenKeyExW
0x18003a7e3  test    eax, eax
0x18003a7e5  jz      short loc_18003A827
0x18003a7e7  mov     rcx, [rsp+78h]; this
0x18003a7ec  mov     r9d, eax; char *
0x18003a7ef  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003a7f6  mov     edx, 0EF3h; void *
0x18003a7fb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003a800  mov     edi, eax
0x18003a802  lea     rcx, [rsp+78h+hkey]
0x18003a807  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a80c  nop
0x18003a80d  lea     rcx, [rsp+78h+hKey]
0x18003a812  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a817  nop
0x18003a818  mov     rcx, rbx
0x18003a81b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a820  mov     eax, edi
0x18003a822  jmp     loc_18003A9C3
0x18003a827  mov     rdx, [rsp+78h+hkey]; void *
0x18003a82c  mov     rcx, rsi; token
0x18003a82f  call    ?ShouldAllowPluginOperation@CtapPluginInternal@@YAJQEAXQEAUHKEY__@@@Z; CtapPluginInternal::ShouldAllowPluginOperation(void * const,HKEY__ * const)
0x18003a834  mov     edi, eax
0x18003a836  test    eax, eax
0x18003a838  jns     short loc_18003A879
0x18003a83a  mov     rcx, [rsp+78h]; this
0x18003a83f  mov     r9d, eax; char *
0x18003a842  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003a849  mov     edx, 0EF4h; void *
0x18003a84e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a853  nop
0x18003a854  lea     rcx, [rsp+78h+hkey]
0x18003a859  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a85e  nop
0x18003a85f  lea     rcx, [rsp+78h+hKey]
0x18003a864  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a869  nop
0x18003a86a  mov     rcx, rbx
0x18003a86d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a872  mov     eax, edi
0x18003a874  jmp     loc_18003A9C3
0x18003a879  mov     dword ptr [rsp+78h+Data], 0
0x18003a881  mov     edi, 4
0x18003a886  mov     [rsp+78h+var_20], edi
0x18003a88a  lea     rax, [rsp+78h+var_20]
0x18003a88f  mov     [rsp+78h+pcbData], rax; pcbData
0x18003a894  lea     rax, [rsp+78h+Data]
0x18003a899  mov     [rsp+78h+pvData], rax; pvData
0x18003a89e  mov     [rsp+78h+phkResult], 0; pdwType
0x18003a8a7  lea     r9d, [rdi+0Ch]; dwFlags
0x18003a8ab  lea     rsi, Value; "UvCount"
0x18003a8b2  mov     r8, rsi; lpValue
0x18003a8b5  xor     edx, edx; lpSubKey
0x18003a8b7  mov     rcx, [rsp+78h+hkey]; hkey
0x18003a8bc  call    cs:__imp_RegGetValueW
0x18003a8c2  test    eax, eax
0x18003a8c4  jns     short loc_18003A92C
0x18003a8c6  mov     dword ptr [rsp+78h+pvData], edi; cbData
0x18003a8ca  lea     rax, [rsp+78h+Data]
0x18003a8cf  mov     [rsp+78h+phkResult], rax; unsigned int
0x18003a8d4  mov     r9d, edi; dwType
0x18003a8d7  xor     r8d, r8d; Reserved
0x18003a8da  mov     rdx, rsi; lpValueName
0x18003a8dd  mov     rcx, [rsp+78h+hkey]; hKey
0x18003a8e2  call    cs:__imp_RegSetValueExW
0x18003a8e8  test    eax, eax
0x18003a8ea  jz      short loc_18003A92C
0x18003a8ec  mov     rcx, [rsp+78h]; this
0x18003a8f1  mov     r9d, eax; char *
0x18003a8f4  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003a8fb  mov     edx, 0EFDh; void *
0x18003a900  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003a905  mov     edi, eax
0x18003a907  lea     rcx, [rsp+78h+hkey]
0x18003a90c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a911  nop
0x18003a912  lea     rcx, [rsp+78h+hKey]
0x18003a917  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a91c  nop
0x18003a91d  mov     rcx, rbx
0x18003a920  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a925  mov     eax, edi
0x18003a927  jmp     loc_18003A9C3
0x18003a92c  inc     dword ptr [rsp+78h+Data]
0x18003a930  mov     dword ptr [rsp+78h+pvData], edi; cbData
0x18003a934  lea     rax, [rsp+78h+Data]
0x18003a939  mov     [rsp+78h+phkResult], rax; unsigned int
0x18003a93e  mov     r9d, edi; dwType
0x18003a941  xor     r8d, r8d; Reserved
0x18003a944  mov     rdx, rsi; lpValueName
0x18003a947  mov     rcx, [rsp+78h+hkey]; hKey
0x18003a94c  call    cs:__imp_RegSetValueExW
0x18003a952  test    eax, eax
0x18003a954  jz      short loc_18003A993
0x18003a956  mov     rcx, [rsp+78h]; this
0x18003a95b  mov     r9d, eax; char *
0x18003a95e  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003a965  mov     edx, 0F03h; void *
0x18003a96a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003a96f  mov     edi, eax
0x18003a971  lea     rcx, [rsp+78h+hkey]
0x18003a976  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a97b  nop
0x18003a97c  lea     rcx, [rsp+78h+hKey]
0x18003a981  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a986  nop
0x18003a987  mov     rcx, rbx
0x18003a98a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a98f  mov     eax, edi
0x18003a991  jmp     short loc_18003A9C3
0x18003a993  lea     rcx, [rsp+78h+hkey]
0x18003a998  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a99d  nop
0x18003a99e  lea     rcx, [rsp+78h+hKey]
0x18003a9a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a9a8  nop
0x18003a9a9  mov     rcx, rbx
0x18003a9ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a9b1  xor     eax, eax
0x18003a9b3  jmp     short loc_18003A9C3
0x18003a9b5  mov     rcx, [rsp+78h+var_18]
0x18003a9ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a9bf  mov     eax, [rsp+78h+var_20]
0x18003a9c3  mov     rcx, [rsp+78h+var_10]
0x18003a9c8  xor     rcx, rsp; StackCookie
0x18003a9cb  call    __security_check_cookie
0x18003a9d0  lea     r11, [rsp+78h+var_8]
0x18003a9d5  mov     rbx, [r11+20h]
0x18003a9d9  mov     rsi, [r11+28h]
0x18003a9dd  mov     rsp, r11
0x18003a9e0  pop     rdi
0x18003a9e1  retn
```
