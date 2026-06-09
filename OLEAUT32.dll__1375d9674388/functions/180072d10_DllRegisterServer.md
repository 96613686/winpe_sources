# DllRegisterServer

- ea: `0x180072d10`
- end: `0x180072ff7`
- name: `DllRegisterServer`
- size: `743`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012750`
- `0x180012b70`
- `0x180040d20`
- `0x18004d900`
- `0x18004e87c`
- `0x180072d10`
- `0x180085eec`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180072fa4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180072fa4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072e1d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072eae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072e1d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072eae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072e5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072eec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072e5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072eec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072ef9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072ef9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072fea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180072f8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180072f8e`
- `ext-ms-win-ole32-oleautomation-l1-1-0!StdTypesRegisterServer` at `0x180072f69`
- `ext-ms-win-ole32-oleautomation-l1-1-0!StdTypesRegisterServer` at `0x180072f69`

## string_xrefs

- `0x180072d4e`: `ProxyStubClsid32`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT v0; // ebx
  LPCWSTR *v1; // rdi
  int i; // r14d
  const BYTE *v3; // rcx
  __int64 v4; // rax
  int j; // esi
  const BYTE *v6; // rcx
  __int64 v7; // rax
  int v9; // edx
  HRESULT v10; // edi
  ITypeLib *v11; // rbx
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v14; // [rsp+60h] [rbp-A0h] BYREF
  ITypeLib *pptlib; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v16[12]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+D0h] [rbp-30h] BYREF

  v16[2] = L"NumMethods";
  v16[5] = L"{00020420-0000-0000-C000-000000000046}";
  v16[8] = L"NumMethods";
  v16[0] = L"{00020412-0000-0000-C000-000000000046}";
  v16[11] = L"{00020420-0000-0000-C000-000000000046}";
  v16[1] = L"ITypeInfo2";
  hKey = 0;
  v16[3] = L"32";
  v16[6] = L"{00020411-0000-0000-C000-000000000046}";
  v16[7] = L"ITypeLib2";
  v16[9] = L"16";
  phkResult = 0;
  v14 = 0;
  pptlib = 0;
  v16[4] = L"ProxyStubClsid32";
  v16[10] = L"ProxyStubClsid32";
  v0 = OpenClassesRootKeyExW(L"Interface", (int)L"ProxyStubClsid32", &hKey);
  if ( v0 )
  {
LABEL_18:
    if ( v0 > 0 )
      return (unsigned __int16)v0 | 0x80070000;
    return v0;
  }
  else
  {
    v1 = (LPCWSTR *)v16;
    for ( i = 0; i < 2; ++i )
    {
      v0 = RegCreateKeyExW(hKey, *v1, 0, 0, 0, 0x2000000u, 0, &phkResult, 0);
      if ( v0 )
        goto LABEL_17;
      v3 = (const BYTE *)v1[1];
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)&v3[2 * v4] );
      v0 = RegSetValueExW(phkResult, 0, 0, 1u, v3, 2 * v4 + 2);
      if ( v0 )
      {
LABEL_16:
        RegCloseKey(phkResult);
LABEL_17:
        RegCloseKey(hKey);
        goto LABEL_18;
      }
      v1 += 2;
      for ( j = 0; j < 2; ++j )
      {
        v0 = RegCreateKeyExW(phkResult, *v1, 0, 0, 0, 0x2000000u, 0, &v14, 0);
        if ( v0 )
          goto LABEL_16;
        v6 = (const BYTE *)v1[1];
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)&v6[2 * v7] );
        v0 = RegSetValueExW(v14, 0, 0, 1u, v6, 2 * v7 + 2);
        RegCloseKey(v14);
        if ( v0 )
          goto LABEL_16;
        v1 += 2;
      }
      RegCloseKey(phkResult);
    }
    if ( !(unsigned __int8)IsMonikerLoadTypeLibPresent() || (v10 = StdTypesRegisterServer(), v10 >= 0) )
    {
      v10 = OcxDllRegisterServer(hKey, v9);
      if ( v10 >= 0 )
      {
        GetSystemDirectoryW(Buffer, 0xF0u);
        _o_wcscat_s(Buffer, 260, L"\\stdole2.tlb");
        v10 = LoadTypeLibEx(Buffer, REGKIND_DEFAULT, &pptlib);
        if ( v10 >= 0 )
        {
          v11 = pptlib;
          v10 = RegisterTypeLib(pptlib, Buffer, 0);
          ((void (__fastcall *)(ITypeLib *))v11->lpVtbl->Release)(v11);
        }
      }
    }
    RegCloseKey(hKey);
    return v10;
  }
}

```

## disassembly

```asm
0x180072d10  push    rbp
0x180072d12  push    rbx
0x180072d13  push    rsi
0x180072d14  push    rdi
0x180072d15  push    r14
0x180072d17  push    r15
0x180072d19  lea     rbp, [rsp-1F8h]
0x180072d21  sub     rsp, 2F8h
0x180072d28  mov     rax, cs:__security_cookie
0x180072d2f  xor     rax, rsp
0x180072d32  mov     [rbp+220h+var_40], rax
0x180072d39  xor     r15d, r15d
0x180072d3c  lea     r8, aNummethods; "NumMethods"
0x180072d43  lea     rcx, a00020420000000; "{00020420-0000-0000-C000-000000000046}"
0x180072d4a  mov     [rbp+220h+var_2A0], r8
0x180072d4e  lea     rdx, ?ProxyStubClsid32@Constants@Catalog@Com@@3QBGB; "ProxyStubClsid32"
0x180072d55  mov     [rbp+220h+var_288], rcx
0x180072d59  lea     rax, a00020412000000; "{00020412-0000-0000-C000-000000000046}"
0x180072d60  mov     [rbp+220h+var_270], r8
0x180072d64  mov     [rsp+320h+var_2B0], rax
0x180072d69  lea     r8, [rsp+320h+hKey]
0x180072d6e  lea     rax, aItypeinfo2; "ITypeInfo2"
0x180072d75  mov     [rbp+220h+var_258], rcx
0x180072d79  mov     [rsp+320h+var_2A8], rax
0x180072d7e  lea     rcx, ?Interface@Constants@Catalog@Com@@3QBGB; "Interface"
0x180072d85  lea     rax, a32; "32"
0x180072d8c  mov     [rsp+320h+hKey], r15
0x180072d91  mov     [rbp+220h+var_298], rax
0x180072d95  lea     rax, a00020411000000; "{00020411-0000-0000-C000-000000000046}"
0x180072d9c  mov     [rbp+220h+var_280], rax
0x180072da0  lea     rax, aItypelib2_0; "ITypeLib2"
0x180072da7  mov     [rbp+220h+var_278], rax
0x180072dab  lea     rax, a16; "16"
0x180072db2  mov     [rbp+220h+var_268], rax
0x180072db6  mov     [rsp+320h+var_2D0], r15
0x180072dbb  mov     [rsp+320h+var_2C0], r15
0x180072dc0  mov     [rsp+320h+pptlib], r15
0x180072dc5  mov     [rbp+220h+var_290], rdx
0x180072dc9  mov     [rbp+220h+var_260], rdx
0x180072dcd  call    OpenClassesRootKeyExW
0x180072dd2  mov     ebx, eax
0x180072dd4  test    eax, eax
0x180072dd6  jnz     loc_180072F32
0x180072ddc  lea     rdi, [rsp+320h+var_2B0]
0x180072de1  mov     r14d, r15d
0x180072de4  cmp     r14d, 2
0x180072de8  jge     loc_180072F60
0x180072dee  mov     rdx, [rdi]; lpSubKey
0x180072df1  lea     rax, [rsp+320h+var_2D0]
0x180072df6  mov     rcx, [rsp+320h+hKey]; hKey
0x180072dfb  xor     r9d, r9d; lpClass
0x180072dfe  mov     [rsp+320h+lpdwDisposition], r15; lpdwDisposition
0x180072e03  xor     r8d, r8d; Reserved
0x180072e06  mov     [rsp+320h+phkResult], rax; phkResult
0x180072e0b  mov     [rsp+320h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180072e10  mov     [rsp+320h+samDesired], 2000000h; samDesired
0x180072e18  mov     [rsp+320h+dwOptions], r15d; dwOptions
0x180072e1d  call    cs:__imp_RegCreateKeyExW
0x180072e23  mov     ebx, eax
0x180072e25  test    eax, eax
0x180072e27  jnz     loc_180072F27
0x180072e2d  mov     rcx, [rdi+8]
0x180072e31  or      rax, 0FFFFFFFFFFFFFFFFh
0x180072e35  inc     rax
0x180072e38  cmp     [rcx+rax*2], r15w
0x180072e3d  jnz     short loc_180072E35
0x180072e3f  lea     eax, ds:2[rax*2]
0x180072e46  mov     r9d, 1; dwType
0x180072e4c  mov     [rsp+320h+samDesired], eax; cbData
0x180072e50  xor     r8d, r8d; Reserved
0x180072e53  mov     qword ptr [rsp+320h+dwOptions], rcx; lpData
0x180072e58  xor     edx, edx; lpValueName
0x180072e5a  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180072e5f  call    cs:__imp_RegSetValueExW
0x180072e65  mov     ebx, eax
0x180072e67  test    eax, eax
0x180072e69  jnz     loc_180072F1C
0x180072e6f  add     rdi, 10h
0x180072e73  mov     esi, r15d
0x180072e76  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180072e7b  cmp     esi, 2
0x180072e7e  jge     loc_180072F0E
0x180072e84  mov     rdx, [rdi]; lpSubKey
0x180072e87  lea     rax, [rsp+320h+var_2C0]
0x180072e8c  mov     [rsp+320h+lpdwDisposition], r15; lpdwDisposition
0x180072e91  xor     r9d, r9d; lpClass
0x180072e94  mov     [rsp+320h+phkResult], rax; phkResult
0x180072e99  xor     r8d, r8d; Reserved
0x180072e9c  mov     [rsp+320h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180072ea1  mov     [rsp+320h+samDesired], 2000000h; samDesired
0x180072ea9  mov     [rsp+320h+dwOptions], r15d; dwOptions
0x180072eae  call    cs:__imp_RegCreateKeyExW
0x180072eb4  mov     ebx, eax
0x180072eb6  test    eax, eax
0x180072eb8  jnz     short loc_180072F1C
0x180072eba  mov     rcx, [rdi+8]
0x180072ebe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180072ec2  inc     rax
0x180072ec5  cmp     [rcx+rax*2], r15w
0x180072eca  jnz     short loc_180072EC2
0x180072ecc  lea     eax, ds:2[rax*2]
0x180072ed3  mov     r9d, 1; dwType
0x180072ed9  mov     [rsp+320h+samDesired], eax; cbData
0x180072edd  xor     r8d, r8d; Reserved
0x180072ee0  mov     qword ptr [rsp+320h+dwOptions], rcx; lpData
0x180072ee5  xor     edx, edx; lpValueName
0x180072ee7  mov     rcx, [rsp+320h+var_2C0]; hKey
0x180072eec  call    cs:__imp_RegSetValueExW
0x180072ef2  mov     rcx, [rsp+320h+var_2C0]; hKey
0x180072ef7  mov     ebx, eax
0x180072ef9  call    cs:__imp_RegCloseKey
0x180072eff  test    ebx, ebx
0x180072f01  jnz     short loc_180072F1C
0x180072f03  add     rdi, 10h
0x180072f07  inc     esi
0x180072f09  jmp     loc_180072E76
0x180072f0e  call    cs:__imp_RegCloseKey
0x180072f14  inc     r14d
0x180072f17  jmp     loc_180072DE4
0x180072f1c  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180072f21  call    cs:__imp_RegCloseKey
0x180072f27  mov     rcx, [rsp+320h+hKey]; hKey
0x180072f2c  call    cs:__imp_RegCloseKey
0x180072f32  test    ebx, ebx
0x180072f34  jle     short loc_180072F3F
0x180072f36  movzx   ebx, bx
0x180072f39  or      ebx, 80070000h
0x180072f3f  mov     eax, ebx
0x180072f41  mov     rcx, [rbp+220h+var_40]
0x180072f48  xor     rcx, rsp; StackCookie
0x180072f4b  call    __security_check_cookie
0x180072f50  add     rsp, 2F8h
0x180072f57  pop     r15
0x180072f59  pop     r14
0x180072f5b  pop     rdi
0x180072f5c  pop     rsi
0x180072f5d  pop     rbx
0x180072f5e  pop     rbp
0x180072f5f  retn
0x180072f60  call    IsMonikerLoadTypeLibPresent
0x180072f65  test    al, al
0x180072f67  jz      short loc_180072F75
0x180072f69  call    cs:__imp_StdTypesRegisterServer
0x180072f6f  mov     edi, eax
0x180072f71  test    eax, eax
0x180072f73  js      short loc_180072FE5
0x180072f75  mov     rcx, [rsp+320h+hKey]
0x180072f7a  call    OcxDllRegisterServer
0x180072f7f  mov     edi, eax
0x180072f81  test    eax, eax
0x180072f83  js      short loc_180072FE5
0x180072f85  mov     edx, 0F0h; uSize
0x180072f8a  lea     rcx, [rbp+220h+Buffer]; lpBuffer
0x180072f8e  call    cs:__imp_GetSystemDirectoryW
0x180072f94  lea     r8, aStdole2Tlb_0; "\\stdole2.tlb"
0x180072f9b  mov     edx, 104h
0x180072fa0  lea     rcx, [rbp+220h+Buffer]
0x180072fa4  call    cs:__imp__o_wcscat_s
0x180072faa  lea     r8, [rsp+320h+pptlib]; pptlib
0x180072faf  xor     edx, edx; regkind
0x180072fb1  lea     rcx, [rbp+220h+Buffer]; szFile
0x180072fb5  call    LoadTypeLibEx
0x180072fba  mov     edi, eax
0x180072fbc  test    eax, eax
0x180072fbe  js      short loc_180072FE5
0x180072fc0  mov     rbx, [rsp+320h+pptlib]
0x180072fc5  lea     rdx, [rbp+220h+Buffer]; szFullPath
0x180072fc9  mov     rcx, rbx; ptlib
0x180072fcc  xor     r8d, r8d; szHelpDir
0x180072fcf  call    RegisterTypeLib
0x180072fd4  mov     edi, eax
0x180072fd6  mov     rcx, rbx
0x180072fd9  mov     rax, [rbx]
0x180072fdc  mov     rax, [rax+10h]
0x180072fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072fe5  mov     rcx, [rsp+320h+hKey]; hKey
0x180072fea  call    cs:__imp_RegCloseKey
0x180072ff0  mov     eax, edi
0x180072ff2  jmp     loc_180072F41
```
