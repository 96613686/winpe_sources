# _lambda_715f26a8cf03ec1bdf3d6747fabae5e9_::operator()

- ea: `0x18001a734`
- end: `0x18001a8d6`
- name: `_lambda_715f26a8cf03ec1bdf3d6747fabae5e9_::operator()`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a490`

## callees

- `0x18001a734`
- `0x18001ab34`
- `0x18001ad64`
- `0x180025db0`
- `0x1800272f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a84c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a84c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a82a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a82a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a85e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a866`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a881`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a8a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a8c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a85e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a866`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a881`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a8a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a8c1`

## string_xrefs

- `0x18001a765`: `Configs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_715f26a8cf03ec1bdf3d6747fabae5e9_::operator()(_BYTE **a1)
{
  unsigned int v2; // ebx
  HKEY v3; // rbx
  LSTATUS v4; // eax
  HKEY v5; // rcx
  LSTATUS v7; // eax
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  char v12; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  memset(lpSubKey, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *((_QWORD *)*a1 + 1),
         L"Configs");
  if ( (v2 & 0x80000000) != 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  v3 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
    RegCloseKey(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
  }
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
  v2 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    if ( lpSubKey[0] )
      CoTaskMemFree((LPVOID)lpSubKey[0]);
    v5 = hKey;
    if ( !hKey )
      return v2;
    goto LABEL_10;
  }
  Type = 0;
  cbData = 0;
  v7 = RegQueryValueExW(hKey, L"GlobalProfileId", 0, &Type, 0, &cbData);
  v2 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v2 = (unsigned __int16)v7 | 0x80070000;
    if ( lpSubKey[0] )
      CoTaskMemFree((LPVOID)lpSubKey[0]);
    v5 = hKey;
    if ( !hKey )
      return v2;
LABEL_10:
    RegCloseKey(v5);
    return v2;
  }
  *a1[1] = 1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001a734  push    rbp
0x18001a736  push    rbx
0x18001a737  push    rsi
0x18001a738  mov     rbp, rsp
0x18001a73b  sub     rsp, 50h
0x18001a73f  mov     rsi, rcx
0x18001a742  mov     [rbp+hKey], 0
0x18001a74a  mov     [rbp+lpSubKey], 0
0x18001a752  mov     [rbp+var_18], 0
0x18001a75a  mov     [rbp+var_10], 0
0x18001a762  mov     r8, [rcx]
0x18001a765  lea     r9, aConfigs; "Configs"
0x18001a76c  mov     r8, [r8+8]
0x18001a770  lea     rdx, aSS; "%s\\%s"
0x18001a777  lea     rcx, [rbp+lpSubKey]
0x18001a77b  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001a780  mov     ebx, eax
0x18001a782  test    eax, eax
0x18001a784  js      loc_18001A86E
0x18001a78a  mov     rbx, [rbp+hKey]
0x18001a78e  test    rbx, rbx
0x18001a791  jnz     loc_18001A8B5
0x18001a797  mov     [rbp+hKey], 0
0x18001a79f  lea     rax, [rbp+hKey]
0x18001a7a3  mov     [rsp+50h+phkResult], rax; phkResult
0x18001a7a8  mov     r9d, 20019h; samDesired
0x18001a7ae  xor     r8d, r8d; ulOptions
0x18001a7b1  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001a7b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a7bc  call    cs:__imp_RegOpenKeyExW
0x18001a7c2  mov     ebx, eax
0x18001a7c4  test    eax, eax
0x18001a7c6  jz      short loc_18001A7F8
0x18001a7c8  jle     short loc_18001A7D3
0x18001a7ca  movzx   ebx, ax
0x18001a7cd  or      ebx, 80070000h
0x18001a7d3  cmp     [rbp+lpSubKey], 0
0x18001a7d8  jz      short loc_18001A7E5
0x18001a7da  mov     rcx, [rbp+lpSubKey]; pv
0x18001a7de  call    cs:__imp_CoTaskMemFree
0x18001a7e4  nop
0x18001a7e5  mov     rcx, [rbp+hKey]; hKey
0x18001a7e9  test    rcx, rcx
0x18001a7ec  jnz     short loc_18001A85E
0x18001a7ee  mov     eax, ebx
0x18001a7f0  add     rsp, 50h
0x18001a7f4  pop     rsi
0x18001a7f5  pop     rbx
0x18001a7f6  pop     rbp
0x18001a7f7  retn
0x18001a7f8  mov     [rbp+Type], 0
0x18001a7ff  mov     [rbp+cbData], 0
0x18001a806  lea     rax, [rbp+cbData]
0x18001a80a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18001a80f  mov     [rsp+50h+phkResult], 0; lpData
0x18001a818  lea     r9, [rbp+Type]; lpType
0x18001a81c  xor     r8d, r8d; lpReserved
0x18001a81f  lea     rdx, aGlobalprofilei; "GlobalProfileId"
0x18001a826  mov     rcx, [rbp+hKey]; hKey
0x18001a82a  call    cs:__imp_RegQueryValueExW
0x18001a830  mov     ebx, eax
0x18001a832  test    eax, eax
0x18001a834  jz      short loc_18001A88D
0x18001a836  jle     short loc_18001A841
0x18001a838  movzx   ebx, ax
0x18001a83b  or      ebx, 80070000h
0x18001a841  cmp     [rbp+lpSubKey], 0
0x18001a846  jz      short loc_18001A853
0x18001a848  mov     rcx, [rbp+lpSubKey]; pv
0x18001a84c  call    cs:__imp_CoTaskMemFree
0x18001a852  nop
0x18001a853  mov     rcx, [rbp+hKey]; hKey
0x18001a857  test    rcx, rcx
0x18001a85a  jnz     short loc_18001A866
0x18001a85c  jmp     short loc_18001A7EE
0x18001a85e  call    cs:__imp_RegCloseKey
0x18001a864  jmp     short loc_18001A7EE
0x18001a866  call    cs:__imp_RegCloseKey
0x18001a86c  jmp     short loc_18001A85C
0x18001a86e  lea     rcx, [rbp+lpSubKey]
0x18001a872  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001a877  nop
0x18001a878  mov     rcx, [rbp+hKey]; hKey
0x18001a87c  test    rcx, rcx
0x18001a87f  jz      short loc_18001A888
0x18001a881  call    cs:__imp_RegCloseKey
0x18001a887  nop
0x18001a888  jmp     loc_18001A7EE
0x18001a88d  mov     rax, [rsi+8]
0x18001a891  mov     byte ptr [rax], 1
0x18001a894  lea     rcx, [rbp+lpSubKey]
0x18001a898  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001a89d  nop
0x18001a89e  mov     rcx, [rbp+hKey]; hKey
0x18001a8a2  test    rcx, rcx
0x18001a8a5  jz      short loc_18001A8AE
0x18001a8a7  call    cs:__imp_RegCloseKey
0x18001a8ad  nop
0x18001a8ae  xor     eax, eax
0x18001a8b0  jmp     loc_18001A7F0
0x18001a8b5  lea     rcx, [rbp+arg_18]; this
0x18001a8b9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a8be  mov     rcx, rbx; hKey
0x18001a8c1  call    cs:__imp_RegCloseKey
0x18001a8c7  lea     rcx, [rbp+arg_18]; this
0x18001a8cb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a8d0  nop
0x18001a8d1  jmp     loc_18001A797
```
