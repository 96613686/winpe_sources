# _lambda_ccf5feeb3127fa5ed0b237b9fe5cead7_::operator()

- ea: `0x180061abc`
- end: `0x180061c53`
- name: `_lambda_ccf5feeb3127fa5ed0b237b9fe5cead7_::operator()`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180046040`

## callees

- `0x18000ba40`
- `0x18000baa4`
- `0x18002ba00`
- `0x18002bc20`
- `0x180061abc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061b10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061b74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061b74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061b20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061b43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061b9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061c0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061c37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061b20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061b43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061b9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061c0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061c37`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180061be2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180061be2`

## string_xrefs

- `0x180061ae6`: `GroupConfigs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_ccf5feeb3127fa5ed0b237b9fe5cead7_::operator()(_BYTE **a1)
{
  unsigned int v2; // ebx
  HKEY v4; // rbx
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LPVOID pv[4]; // [rsp+60h] [rbp-20h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+28h] BYREF
  char v10; // [rsp+B0h] [rbp+30h] BYREF

  hKey = 0;
  memset(pv, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         pv,
         L"%s\\%s",
         *((_QWORD *)*a1 + 1),
         L"GroupConfigs");
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  v4 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
    RegCloseKey(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
  }
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)pv[0], 0, 0x20019u, &hKey);
  v2 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  cSubKeys = 0;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v2 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  *a1[1] = cSubKeys != 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180061abc  mov     [rsp-18h+arg_18], rbx
0x180061ac1  push    rbp
0x180061ac2  push    rsi
0x180061ac3  push    rdi
0x180061ac4  mov     rbp, rsp
0x180061ac7  sub     rsp, 80h
0x180061ace  mov     rdi, rcx
0x180061ad1  xor     esi, esi
0x180061ad3  mov     [rbp+hKey], rsi
0x180061ad7  mov     [rbp+pv], rsi
0x180061adb  mov     [rbp+var_18], rsi
0x180061adf  mov     [rbp+var_10], rsi
0x180061ae3  mov     r8, [rcx]
0x180061ae6  lea     r9, aGroupconfigs; "GroupConfigs"
0x180061aed  mov     r8, [r8+8]
0x180061af1  lea     rdx, aSS_0; "%s\\%s"
0x180061af8  lea     rcx, [rbp+pv]
0x180061afc  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180061b01  mov     ebx, eax
0x180061b03  test    eax, eax
0x180061b05  jns     short loc_180061B2E
0x180061b07  mov     rcx, [rbp+pv]; pv
0x180061b0b  test    rcx, rcx
0x180061b0e  jz      short loc_180061B17
0x180061b10  call    cs:__imp_CoTaskMemFree
0x180061b16  nop
0x180061b17  mov     rcx, [rbp+hKey]; hKey
0x180061b1b  test    rcx, rcx
0x180061b1e  jz      short loc_180061B27
0x180061b20  call    cs:__imp_RegCloseKey
0x180061b26  nop
0x180061b27  mov     eax, ebx
0x180061b29  jmp     loc_180061C40
0x180061b2e  mov     rbx, [rbp+hKey]
0x180061b32  test    rbx, rbx
0x180061b35  jz      short loc_180061B53
0x180061b37  lea     rcx, [rbp+arg_10]; this
0x180061b3b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180061b40  mov     rcx, rbx; hKey
0x180061b43  call    cs:__imp_RegCloseKey
0x180061b49  lea     rcx, [rbp+arg_10]; this
0x180061b4d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180061b52  nop
0x180061b53  mov     [rbp+hKey], rsi
0x180061b57  lea     rax, [rbp+hKey]
0x180061b5b  mov     [rsp+80h+phkResult], rax; phkResult
0x180061b60  mov     r9d, 20019h; samDesired
0x180061b66  xor     r8d, r8d; ulOptions
0x180061b69  mov     rdx, [rbp+pv]; lpSubKey
0x180061b6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180061b74  call    cs:__imp_RegOpenKeyExW
0x180061b7a  mov     ebx, eax
0x180061b7c  test    eax, eax
0x180061b7e  jz      short loc_180061BA7
0x180061b80  jle     short loc_180061B8B
0x180061b82  movzx   ebx, ax
0x180061b85  or      ebx, 80070000h
0x180061b8b  lea     rcx, [rbp+pv]
0x180061b8f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180061b94  nop
0x180061b95  mov     rcx, [rbp+hKey]; hKey
0x180061b99  test    rcx, rcx
0x180061b9c  jz      short loc_180061BA5
0x180061b9e  call    cs:__imp_RegCloseKey
0x180061ba4  nop
0x180061ba5  jmp     short loc_180061B27
0x180061ba7  mov     [rbp+cSubKeys], esi
0x180061baa  mov     [rsp+80h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180061baf  mov     [rsp+80h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180061bb4  mov     [rsp+80h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180061bb9  mov     [rsp+80h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180061bbe  mov     [rsp+80h+lpcValues], rsi; lpcValues
0x180061bc3  mov     [rsp+80h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180061bc8  mov     [rsp+80h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180061bcd  lea     rax, [rbp+cSubKeys]
0x180061bd1  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x180061bd6  xor     r9d, r9d; lpReserved
0x180061bd9  xor     r8d, r8d; lpcchClass
0x180061bdc  xor     edx, edx; lpClass
0x180061bde  mov     rcx, [rbp+hKey]; hKey
0x180061be2  call    cs:__imp_RegQueryInfoKeyW
0x180061be8  mov     ebx, eax
0x180061bea  test    eax, eax
0x180061bec  jz      short loc_180061C18
0x180061bee  jle     short loc_180061BF9
0x180061bf0  movzx   ebx, ax
0x180061bf3  or      ebx, 80070000h
0x180061bf9  lea     rcx, [rbp+pv]
0x180061bfd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180061c02  nop
0x180061c03  mov     rcx, [rbp+hKey]; hKey
0x180061c07  test    rcx, rcx
0x180061c0a  jz      short loc_180061C13
0x180061c0c  call    cs:__imp_RegCloseKey
0x180061c12  nop
0x180061c13  jmp     loc_180061B27
0x180061c18  cmp     [rbp+cSubKeys], esi
0x180061c1b  setnz   cl
0x180061c1e  mov     rax, [rdi+8]
0x180061c22  mov     [rax], cl
0x180061c24  lea     rcx, [rbp+pv]
0x180061c28  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180061c2d  nop
0x180061c2e  mov     rcx, [rbp+hKey]; hKey
0x180061c32  test    rcx, rcx
0x180061c35  jz      short loc_180061C3E
0x180061c37  call    cs:__imp_RegCloseKey
0x180061c3d  nop
0x180061c3e  xor     eax, eax
0x180061c40  mov     rbx, [rsp+80h+arg_18]
0x180061c48  add     rsp, 80h
0x180061c4f  pop     rdi
0x180061c50  pop     rsi
0x180061c51  pop     rbp
0x180061c52  retn
```
