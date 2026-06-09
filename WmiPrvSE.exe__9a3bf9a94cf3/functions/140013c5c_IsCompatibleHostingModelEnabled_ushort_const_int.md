# IsCompatibleHostingModelEnabled(ushort const *,int &)

- ea: `0x140013c5c`
- end: `0x140013f58`
- name: `?IsCompatibleHostingModelEnabled@@YAJPEBGAEAH@Z`
- size: `764`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013548`
- `0x140015130`

## callees

- `0x140013c5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013cdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013d44`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013e32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013e9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013edd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013cdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013d44`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013e32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013e9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013edd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013cab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013d1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013d9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013dc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013df0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013cab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013d1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013d9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013dc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013df0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013ceb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013d50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013e3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013ea8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013ee9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013ceb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013d50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013e3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013ea8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013ee9`

## string_xrefs

- `0x140013d92`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`
- `0x140013dbc`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsCompatibleHostingModelEnabled(LPCWSTR lpValueName, int *a2)
{
  BOOL v4; // edi
  LSTATUS v5; // ebx
  LSTATUS v6; // ebx
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  LSTATUS v10; // esi
  LSTATUS v11; // ebx
  LSTATUS v12; // ebx
  int v13; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+50h] BYREF
  DWORD Type; // [rsp+98h] [rbp+58h] BYREF

  Type = 0;
  hKey = 0;
  cbData = 0;
  v4 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20019u, &hKey)
    && ((cbData = 0, v5 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v5) || v5 == 234)
    && Type == 1
    || !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20219u, &hKey)
    && ((cbData = 0, v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v6) || v6 == 234)
    && Type == 1 )
  {
    *a2 = 0;
    return 0;
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20019u,
          &hKey)
    && ((cbData = 0, v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v11)
     || v11 == 234)
    && Type == 1
    || !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20219u,
          &hKey)
    && ((cbData = 0, v12 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v12)
     || v12 == 234)
    && Type == 1 )
  {
    *a2 = 1;
    return 0;
  }
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 <= 0 )
      return v9;
    v13 = (unsigned __int16)v8;
    return v13 | 0x80070000;
  }
  *(_DWORD *)Data = 0;
  cbData = 4;
  v9 = 0;
  v10 = RegQueryValueExW(hKey, L"DefaultSecuredHost", 0, &Type, Data, &cbData);
  RegCloseKey(hKey);
  if ( !v10 )
  {
    if ( Type == 4 )
      v4 = *(_DWORD *)Data == 0;
    goto LABEL_15;
  }
  if ( v10 != 2 )
  {
    if ( v10 <= 0 )
      return (unsigned int)v10;
    v13 = (unsigned __int16)v10;
    return v13 | 0x80070000;
  }
LABEL_15:
  *a2 = v4;
  return v9;
}

```

## disassembly

```asm
0x140013c5c  mov     [rsp-38h+arg_0], rbx
0x140013c61  push    rbp
0x140013c62  push    rsi
0x140013c63  push    rdi
0x140013c64  push    r12
0x140013c66  push    r13
0x140013c68  push    r14
0x140013c6a  push    r15
0x140013c6c  mov     rbp, rsp
0x140013c6f  sub     rsp, 40h
0x140013c73  xor     r15d, r15d
0x140013c76  lea     rax, [rbp+hKey]
0x140013c7a  mov     r14, rdx
0x140013c7d  mov     [rbp+Type], r15d
0x140013c81  mov     rsi, rcx
0x140013c84  mov     [rbp+hKey], r15
0x140013c88  mov     r13, 0FFFFFFFF80000002h
0x140013c8f  mov     [rbp+cbData], r15d
0x140013c93  mov     rcx, r13; hKey
0x140013c96  mov     [rsp+40h+phkResult], rax; phkResult
0x140013c9b  mov     r9d, 20019h; samDesired
0x140013ca1  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x140013ca8  xor     r8d, r8d; ulOptions
0x140013cab  call    cs:__imp_RegOpenKeyExW
0x140013cb1  lea     edi, [r15+1]
0x140013cb5  mov     r12d, 0EAh
0x140013cbb  test    eax, eax
0x140013cbd  jnz     short loc_140013CFE
0x140013cbf  mov     rcx, [rbp+hKey]; hKey
0x140013cc3  lea     rax, [rbp+cbData]
0x140013cc7  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140013ccc  lea     r9, [rbp+Type]; lpType
0x140013cd0  xor     r8d, r8d; lpReserved
0x140013cd3  mov     [rsp+40h+phkResult], r15; lpData
0x140013cd8  mov     rdx, rsi; lpValueName
0x140013cdb  mov     [rbp+cbData], r15d
0x140013cdf  call    cs:__imp_RegQueryValueExW
0x140013ce5  mov     rcx, [rbp+hKey]; hKey
0x140013ce9  mov     ebx, eax
0x140013ceb  call    cs:__imp_RegCloseKey
0x140013cf1  test    ebx, ebx
0x140013cf3  jnz     loc_140013E6E
0x140013cf9  cmp     [rbp+Type], edi
0x140013cfc  jz      short loc_140013D63
0x140013cfe  lea     rax, [rbp+hKey]
0x140013d02  mov     r9d, 20219h; samDesired
0x140013d08  xor     r8d, r8d; ulOptions
0x140013d0b  mov     [rsp+40h+phkResult], rax; phkResult
0x140013d10  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x140013d17  mov     rcx, r13; hKey
0x140013d1a  call    cs:__imp_RegOpenKeyExW
0x140013d20  test    eax, eax
0x140013d22  jnz     short loc_140013D80
0x140013d24  mov     rcx, [rbp+hKey]; hKey
0x140013d28  lea     rax, [rbp+cbData]
0x140013d2c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140013d31  lea     r9, [rbp+Type]; lpType
0x140013d35  xor     r8d, r8d; lpReserved
0x140013d38  mov     [rsp+40h+phkResult], r15; lpData
0x140013d3d  mov     rdx, rsi; lpValueName
0x140013d40  mov     [rbp+cbData], r15d
0x140013d44  call    cs:__imp_RegQueryValueExW
0x140013d4a  mov     rcx, [rbp+hKey]; hKey
0x140013d4e  mov     ebx, eax
0x140013d50  call    cs:__imp_RegCloseKey
0x140013d56  test    ebx, ebx
0x140013d58  jnz     loc_140013E60
0x140013d5e  cmp     [rbp+Type], edi
0x140013d61  jnz     short loc_140013D80
0x140013d63  mov     [r14], r15d
0x140013d66  xor     eax, eax
0x140013d68  mov     rbx, [rsp+40h+arg_0]
0x140013d70  add     rsp, 40h
0x140013d74  pop     r15
0x140013d76  pop     r14
0x140013d78  pop     r13
0x140013d7a  pop     r12
0x140013d7c  pop     rdi
0x140013d7d  pop     rsi
0x140013d7e  pop     rbp
0x140013d7f  retn
0x140013d80  lea     rax, [rbp+hKey]
0x140013d84  mov     r9d, 20019h; samDesired
0x140013d8a  xor     r8d, r8d; ulOptions
0x140013d8d  mov     [rsp+40h+phkResult], rax; phkResult
0x140013d92  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x140013d99  mov     rcx, r13; hKey
0x140013d9c  call    cs:__imp_RegOpenKeyExW
0x140013da2  test    eax, eax
0x140013da4  jz      loc_140013E7C
0x140013daa  lea     rax, [rbp+hKey]
0x140013dae  mov     r9d, 20219h; samDesired
0x140013db4  xor     r8d, r8d; ulOptions
0x140013db7  mov     [rsp+40h+phkResult], rax; phkResult
0x140013dbc  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x140013dc3  mov     rcx, r13; hKey
0x140013dc6  call    cs:__imp_RegOpenKeyExW
0x140013dcc  test    eax, eax
0x140013dce  jz      loc_140013EBD
0x140013dd4  lea     rax, [rbp+hKey]
0x140013dd8  mov     r9d, 20019h; samDesired
0x140013dde  xor     r8d, r8d; ulOptions
0x140013de1  mov     [rsp+40h+phkResult], rax; phkResult
0x140013de6  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\WBEM\\CIMOM"
0x140013ded  mov     rcx, r13; hKey
0x140013df0  call    cs:__imp_RegOpenKeyExW
0x140013df6  mov     ebx, eax
0x140013df8  test    eax, eax
0x140013dfa  jnz     loc_140013F2A
0x140013e00  mov     rcx, [rbp+hKey]; hKey
0x140013e04  lea     rax, [rbp+cbData]
0x140013e08  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140013e0d  lea     r9, [rbp+Type]; lpType
0x140013e11  lea     rax, [rbp+Data]
0x140013e15  mov     dword ptr [rbp+Data], r15d
0x140013e19  xor     r8d, r8d; lpReserved
0x140013e1c  mov     [rsp+40h+phkResult], rax; lpData
0x140013e21  lea     rdx, aDefaultsecured; "DefaultSecuredHost"
0x140013e28  mov     [rbp+cbData], 4
0x140013e2f  mov     ebx, r15d
0x140013e32  call    cs:__imp_RegQueryValueExW
0x140013e38  mov     rcx, [rbp+hKey]; hKey
0x140013e3c  mov     esi, eax
0x140013e3e  call    cs:__imp_RegCloseKey
0x140013e44  test    esi, esi
0x140013e46  jnz     loc_140013F4E
0x140013e4c  cmp     [rbp+Type], 4
0x140013e50  jz      loc_140013F1A
0x140013e56  mov     [r14], edi
0x140013e59  mov     eax, ebx
0x140013e5b  jmp     loc_140013D68
0x140013e60  cmp     ebx, r12d
0x140013e63  jz      loc_140013D5E
0x140013e69  jmp     loc_140013D80
0x140013e6e  cmp     ebx, r12d
0x140013e71  jz      loc_140013CF9
0x140013e77  jmp     loc_140013CFE
0x140013e7c  mov     rcx, [rbp+hKey]; hKey
0x140013e80  lea     rax, [rbp+cbData]
0x140013e84  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140013e89  lea     r9, [rbp+Type]; lpType
0x140013e8d  xor     r8d, r8d; lpReserved
0x140013e90  mov     [rsp+40h+phkResult], r15; lpData
0x140013e95  mov     rdx, rsi; lpValueName
0x140013e98  mov     [rbp+cbData], r15d
0x140013e9c  call    cs:__imp_RegQueryValueExW
0x140013ea2  mov     rcx, [rbp+hKey]; hKey
0x140013ea6  mov     ebx, eax
0x140013ea8  call    cs:__imp_RegCloseKey
0x140013eae  test    ebx, ebx
0x140013eb0  jnz     short loc_140013F04
0x140013eb2  cmp     [rbp+Type], edi
0x140013eb5  jnz     loc_140013DAA
0x140013ebb  jmp     short loc_140013EFC
0x140013ebd  mov     rcx, [rbp+hKey]; hKey
0x140013ec1  lea     rax, [rbp+cbData]
0x140013ec5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140013eca  lea     r9, [rbp+Type]; lpType
0x140013ece  xor     r8d, r8d; lpReserved
0x140013ed1  mov     [rsp+40h+phkResult], r15; lpData
0x140013ed6  mov     rdx, rsi; lpValueName
0x140013ed9  mov     [rbp+cbData], r15d
0x140013edd  call    cs:__imp_RegQueryValueExW
0x140013ee3  mov     rcx, [rbp+hKey]; hKey
0x140013ee7  mov     ebx, eax
0x140013ee9  call    cs:__imp_RegCloseKey
0x140013eef  test    ebx, ebx
0x140013ef1  jnz     short loc_140013F0F
0x140013ef3  cmp     [rbp+Type], edi
0x140013ef6  jnz     loc_140013DD4
0x140013efc  mov     [r14], edi
0x140013eff  jmp     loc_140013D66
0x140013f04  cmp     ebx, r12d
0x140013f07  jnz     loc_140013DAA
0x140013f0d  jmp     short loc_140013EB2
0x140013f0f  cmp     ebx, r12d
0x140013f12  jnz     loc_140013DD4
0x140013f18  jmp     short loc_140013EF3
0x140013f1a  cmp     dword ptr [rbp+Data], r15d
0x140013f1e  mov     edi, r15d
0x140013f21  setz    dil
0x140013f25  jmp     loc_140013E56
0x140013f2a  jle     loc_140013E59
0x140013f30  movzx   ebx, ax
0x140013f33  or      ebx, 80070000h
0x140013f39  jmp     loc_140013E59
0x140013f3e  test    esi, esi
0x140013f40  jg      short loc_140013F49
0x140013f42  mov     ebx, esi
0x140013f44  jmp     loc_140013E59
0x140013f49  movzx   ebx, si
0x140013f4c  jmp     short loc_140013F33
0x140013f4e  cmp     esi, 2
0x140013f51  jnz     short loc_140013F3E
0x140013f53  jmp     loc_140013E56
```
