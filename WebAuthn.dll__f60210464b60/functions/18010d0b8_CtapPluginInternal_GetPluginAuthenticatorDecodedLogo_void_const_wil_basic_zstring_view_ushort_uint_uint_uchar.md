# CtapPluginInternal::GetPluginAuthenticatorDecodedLogo(void * const,wil::basic_zstring_view<ushort>,uint,uint *,uchar * *)

- ea: `0x18010d0b8`
- end: `0x18010d428`
- name: `?GetPluginAuthenticatorDecodedLogo@CtapPluginInternal@@YAJQEAXV?$basic_zstring_view@G@wil@@IPEAIPEAPEAE@Z`
- size: `880`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180033970`
- `0x1800a1d08`
- `0x1800a5de4`
- `0x1800a645c`

## callees

- `0x1800328b8`
- `0x180036da4`
- `0x18003a9e8`
- `0x180042df8`
- `0x18004349c`
- `0x18009b620`
- `0x18010bfa8`
- `0x18010c484`
- `0x18010d0b8`
- `0x18011c42c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d1ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d26a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d2d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d384`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d1ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d26a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d2d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d384`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010d13b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010d13b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d23a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d2a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d354`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d3bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d23a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d2a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d354`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d3bf`

## string_xrefs

- `0x18010d0f3`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010d150`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010d1cf`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010d27f`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010d2e9`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010d399`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CtapPluginInternal::GetPluginAuthenticatorDecodedLogo(
        __int64 a1,
        LPCWSTR *a2,
        int a3,
        DWORD *a4,
        _QWORD *a5)
{
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  HKEY *v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int ValueW; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  __int64 unique; // rax
  void *v18; // rcx
  PVOID v19; // rbx
  unsigned int v20; // eax
  unsigned int v21; // edi
  unsigned int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rax
  void *v25; // rcx
  unsigned int v26; // eax
  int phkResult; // [rsp+20h] [rbp-88h]
  unsigned int phkResulta; // [rsp+20h] [rbp-88h]
  unsigned int phkResultb; // [rsp+20h] [rbp-88h]
  unsigned int phkResultc; // [rsp+20h] [rbp-88h]
  unsigned int phkResultd; // [rsp+20h] [rbp-88h]
  unsigned int phkResulte; // [rsp+20h] [rbp-88h]
  DWORD pcbData; // [rsp+40h] [rbp-68h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-58h] BYREF
  PVOID pvData; // [rsp+58h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-48h] BYREF
  _BYTE v38[64]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, (__int64)&hKey);
  v9 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9E,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v9;
  }
  hkey = 0;
  v11 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  v12 = RegOpenKeyExW(hKey, *a2, 0, 0xF003Fu, v11);
  if ( v12 )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xEA2,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)v12,
            phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v13;
  }
  try
  {
    pcbData = 0;
    pvData = 0;
    if ( a3 == 1 )
    {
      ValueW = RegGetValueW(hkey, 0, L"DecodedUtf8LightLogo", 8u, 0, 0, &pcbData);
      if ( ValueW )
      {
        v15 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xEA9,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)ValueW,
                phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v15;
      }
      std::vector<unsigned short>::vector<unsigned short>(v38, (unsigned __int64)pcbData >> 1);
      unique = wil::make_unique_cotaskmem<unsigned char [0]>(&pv, pcbData);
      wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
        &pvData,
        unique);
      v18 = pv;
      pv = 0;
      if ( v18 )
        CoTaskMemFree(v18);
      v19 = pvData;
      v20 = RegGetValueW(hkey, 0, L"DecodedUtf8LightLogo", 8u, 0, pvData, &pcbData);
      if ( v20 )
      {
        v21 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xEAD,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)v20,
                phkResultc);
        std::vector<unsigned short>::_Tidy(v38);
        if ( v19 )
          CoTaskMemFree(v19);
LABEL_13:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v21;
      }
    }
    else
    {
      v22 = RegGetValueW(hkey, 0, L"DecodedUftf8DarkLogo", 8u, 0, 0, &pcbData);
      if ( v22 )
      {
        v23 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xEB2,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)v22,
                phkResultd);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v23;
      }
      std::vector<unsigned short>::vector<unsigned short>(v38, (unsigned __int64)pcbData >> 1);
      v24 = wil::make_unique_cotaskmem<unsigned char [0]>(&pv, pcbData);
      wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
        &pvData,
        v24);
      v25 = pv;
      pv = 0;
      if ( v25 )
        CoTaskMemFree(v25);
      v19 = pvData;
      v26 = RegGetValueW(hkey, 0, L"DecodedUftf8DarkLogo", 8u, 0, pvData, &pcbData);
      if ( v26 )
      {
        v21 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xEB6,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)v26,
                phkResulte);
        std::vector<unsigned short>::_Tidy(v38);
        if ( v19 )
          CoTaskMemFree(v19);
        goto LABEL_13;
      }
    }
    std::vector<unsigned short>::_Tidy(v38);
    *a5 = v19;
    *a4 = pcbData;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xEBD,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18010d0b8  push    rbx
0x18010d0ba  push    rsi
0x18010d0bb  push    rdi
0x18010d0bc  push    r14
0x18010d0be  push    r15
0x18010d0c0  sub     rsp, 80h
0x18010d0c7  mov     r14, r9
0x18010d0ca  mov     edi, r8d
0x18010d0cd  mov     rsi, rdx
0x18010d0d0  xor     r15d, r15d
0x18010d0d3  mov     [rsp+0A8h+hKey], r15
0x18010d0d8  lea     rdx, [rsp+0A8h+hKey]
0x18010d0dd  call    GetUserPluginAuthenticatorsRegKey
0x18010d0e2  mov     ebx, eax
0x18010d0e4  test    eax, eax
0x18010d0e6  jns     short loc_18010D116
0x18010d0e8  mov     rcx, [rsp+0A8h]; this
0x18010d0f0  mov     r9d, eax; char *
0x18010d0f3  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d0fa  mov     edx, 0E9Eh; void *
0x18010d0ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d104  nop
0x18010d105  lea     rcx, [rsp+0A8h+hKey]
0x18010d10a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d10f  mov     eax, ebx
0x18010d111  jmp     loc_18010D418
0x18010d116  mov     [rsp+0A8h+hkey], r15
0x18010d11b  lea     rcx, [rsp+0A8h+hkey]
0x18010d120  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18010d125  mov     [rsp+0A8h+phkResult], rax; unsigned int
0x18010d12a  mov     r9d, 0F003Fh; samDesired
0x18010d130  xor     r8d, r8d; ulOptions
0x18010d133  mov     rdx, [rsi]; lpSubKey
0x18010d136  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18010d13b  call    cs:__imp_RegOpenKeyExW
0x18010d141  test    eax, eax
0x18010d143  jz      short loc_18010D17F
0x18010d145  mov     rcx, [rsp+0A8h]; this
0x18010d14d  mov     r9d, eax; char *
0x18010d150  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d157  mov     edx, 0EA2h; void *
0x18010d15c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010d161  mov     ebx, eax
0x18010d163  lea     rcx, [rsp+0A8h+hkey]
0x18010d168  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d16d  nop
0x18010d16e  lea     rcx, [rsp+0A8h+hKey]
0x18010d173  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d178  mov     eax, ebx
0x18010d17a  jmp     loc_18010D418
0x18010d17f  mov     [rsp+0A8h+var_68], r15d
0x18010d184  mov     [rsp+0A8h+var_50], r15
0x18010d189  lea     rax, [rsp+0A8h+var_68]
0x18010d18e  xor     edx, edx; lpSubKey
0x18010d190  mov     rcx, [rsp+0A8h+hkey]; hkey
0x18010d195  mov     [rsp+0A8h+pcbData], rax; pcbData
0x18010d19a  mov     [rsp+0A8h+pvData], r15; pvData
0x18010d19f  mov     [rsp+0A8h+phkResult], r15; unsigned int
0x18010d1a4  cmp     edi, 1
0x18010d1a7  lea     edi, [rdx+8]
0x18010d1aa  mov     r9d, edi; dwFlags
0x18010d1ad  jnz     loc_18010D2CD
0x18010d1b3  lea     r8, aDecodedutf8lig; "DecodedUtf8LightLogo"
0x18010d1ba  call    cs:__imp_RegGetValueW
0x18010d1c0  test    eax, eax
0x18010d1c2  jz      short loc_18010D1FE
0x18010d1c4  mov     rcx, [rsp+0A8h]; this
0x18010d1cc  mov     r9d, eax; char *
0x18010d1cf  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d1d6  mov     edx, 0EA9h; void *
0x18010d1db  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010d1e0  mov     ebx, eax
0x18010d1e2  lea     rcx, [rsp+0A8h+hkey]
0x18010d1e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d1ec  nop
0x18010d1ed  lea     rcx, [rsp+0A8h+hKey]
0x18010d1f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d1f7  mov     eax, ebx
0x18010d1f9  jmp     loc_18010D418
0x18010d1fe  mov     edx, [rsp+0A8h+var_68]
0x18010d202  shr     rdx, 1
0x18010d205  lea     rcx, [rsp+0A8h+var_40]
0x18010d20a  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18010d20f  nop
0x18010d210  mov     edx, [rsp+0A8h+var_68]
0x18010d214  lea     rcx, [rsp+0A8h+pv]
0x18010d219  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x18010d21e  mov     rdx, rax
0x18010d221  lea     rcx, [rsp+0A8h+var_50]
0x18010d226  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18010d22b  mov     rcx, [rsp+0A8h+pv]; pv
0x18010d230  mov     [rsp+0A8h+pv], r15
0x18010d235  test    rcx, rcx
0x18010d238  jz      short loc_18010D240
0x18010d23a  call    cs:__imp_CoTaskMemFree
0x18010d240  lea     rax, [rsp+0A8h+var_68]
0x18010d245  mov     [rsp+0A8h+pcbData], rax; pcbData
0x18010d24a  mov     rbx, [rsp+0A8h+var_50]
0x18010d24f  mov     [rsp+0A8h+pvData], rbx; pvData
0x18010d254  mov     [rsp+0A8h+phkResult], r15; unsigned int
0x18010d259  mov     r9d, edi; dwFlags
0x18010d25c  lea     r8, aDecodedutf8lig; "DecodedUtf8LightLogo"
0x18010d263  xor     edx, edx; lpSubKey
0x18010d265  mov     rcx, [rsp+0A8h+hkey]; hkey
0x18010d26a  call    cs:__imp_RegGetValueW
0x18010d270  test    eax, eax
0x18010d272  jz      short loc_18010D2C8
0x18010d274  mov     rcx, [rsp+0A8h]; this
0x18010d27c  mov     r9d, eax; char *
0x18010d27f  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d286  mov     edx, 0EADh; void *
0x18010d28b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010d290  mov     edi, eax
0x18010d292  lea     rcx, [rsp+0A8h+var_40]
0x18010d297  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18010d29c  nop
0x18010d29d  test    rbx, rbx
0x18010d2a0  jz      short loc_18010D2AC
0x18010d2a2  mov     rcx, rbx; pv
0x18010d2a5  call    cs:__imp_CoTaskMemFree
0x18010d2ab  nop
0x18010d2ac  lea     rcx, [rsp+0A8h+hkey]
0x18010d2b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d2b6  nop
0x18010d2b7  lea     rcx, [rsp+0A8h+hKey]
0x18010d2bc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d2c1  mov     eax, edi
0x18010d2c3  jmp     loc_18010D418
0x18010d2c8  jmp     loc_18010D3DF
0x18010d2cd  lea     r8, aDecodeduftf8da; "DecodedUftf8DarkLogo"
0x18010d2d4  call    cs:__imp_RegGetValueW
0x18010d2da  test    eax, eax
0x18010d2dc  jz      short loc_18010D318
0x18010d2de  mov     rcx, [rsp+0A8h]; this
0x18010d2e6  mov     r9d, eax; char *
0x18010d2e9  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d2f0  mov     edx, 0EB2h; void *
0x18010d2f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010d2fa  mov     ebx, eax
0x18010d2fc  lea     rcx, [rsp+0A8h+hkey]
0x18010d301  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d306  nop
0x18010d307  lea     rcx, [rsp+0A8h+hKey]
0x18010d30c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d311  mov     eax, ebx
0x18010d313  jmp     loc_18010D418
0x18010d318  mov     edx, [rsp+0A8h+var_68]
0x18010d31c  shr     rdx, 1
0x18010d31f  lea     rcx, [rsp+0A8h+var_40]
0x18010d324  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18010d329  nop
0x18010d32a  mov     edx, [rsp+0A8h+var_68]
0x18010d32e  lea     rcx, [rsp+0A8h+pv]
0x18010d333  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x18010d338  mov     rdx, rax
0x18010d33b  lea     rcx, [rsp+0A8h+var_50]
0x18010d340  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18010d345  mov     rcx, [rsp+0A8h+pv]; pv
0x18010d34a  mov     [rsp+0A8h+pv], r15
0x18010d34f  test    rcx, rcx
0x18010d352  jz      short loc_18010D35A
0x18010d354  call    cs:__imp_CoTaskMemFree
0x18010d35a  lea     rax, [rsp+0A8h+var_68]
0x18010d35f  mov     [rsp+0A8h+pcbData], rax; pcbData
0x18010d364  mov     rbx, [rsp+0A8h+var_50]
0x18010d369  mov     [rsp+0A8h+pvData], rbx; pvData
0x18010d36e  mov     [rsp+0A8h+phkResult], r15; unsigned int
0x18010d373  mov     r9d, edi; dwFlags
0x18010d376  lea     r8, aDecodeduftf8da; "DecodedUftf8DarkLogo"
0x18010d37d  xor     edx, edx; lpSubKey
0x18010d37f  mov     rcx, [rsp+0A8h+hkey]; hkey
0x18010d384  call    cs:__imp_RegGetValueW
0x18010d38a  test    eax, eax
0x18010d38c  jz      short loc_18010D3DF
0x18010d38e  mov     rcx, [rsp+0A8h]; this
0x18010d396  mov     r9d, eax; char *
0x18010d399  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d3a0  mov     edx, 0EB6h; void *
0x18010d3a5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010d3aa  mov     edi, eax
0x18010d3ac  lea     rcx, [rsp+0A8h+var_40]
0x18010d3b1  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18010d3b6  nop
0x18010d3b7  test    rbx, rbx
0x18010d3ba  jz      short loc_18010D3C6
0x18010d3bc  mov     rcx, rbx; pv
0x18010d3bf  call    cs:__imp_CoTaskMemFree
0x18010d3c5  nop
0x18010d3c6  lea     rcx, [rsp+0A8h+hkey]
0x18010d3cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d3d0  nop
0x18010d3d1  lea     rcx, [rsp+0A8h+hKey]
0x18010d3d6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d3db  mov     eax, edi
0x18010d3dd  jmp     short loc_18010D418
0x18010d3df  lea     rcx, [rsp+0A8h+var_40]
0x18010d3e4  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18010d3e9  mov     rax, [rsp+0A8h+arg_20]
0x18010d3f1  mov     [rax], rbx
0x18010d3f4  mov     eax, [rsp+0A8h+var_68]
0x18010d3f8  mov     [r14], eax
0x18010d3fb  lea     rcx, [rsp+0A8h+hkey]
0x18010d400  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d405  nop
0x18010d406  lea     rcx, [rsp+0A8h+hKey]
0x18010d40b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d410  xor     eax, eax
0x18010d412  jmp     short loc_18010D418
0x18010d414  mov     eax, [rsp+0A8h+var_68]
0x18010d418  add     rsp, 80h
0x18010d41f  pop     r15
0x18010d421  pop     r14
0x18010d423  pop     rdi
0x18010d424  pop     rsi
0x18010d425  pop     rbx
0x18010d426  retn
```
