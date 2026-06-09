# IsStandaloneHostingModelEnabled(ushort const *,int &,ulong &)

- ea: `0x140016d1c`
- end: `0x140017089`
- name: `?IsStandaloneHostingModelEnabled@@YAJPEBGAEAHAEAK@Z`
- size: `877`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, int *, BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015130`

## callees

- `0x140016d1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016daa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016e79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016f5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016fb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001700b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140017058`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016daa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016e79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016f5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016fb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001700b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140017058`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016d77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016df0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016e1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016e4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016ee3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016f11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016d77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016df0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016e1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016e4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016ee3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016f11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016db6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016e85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016fbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017017`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017064`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016db6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016e85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016fbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017017`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017064`

## string_xrefs

- `0x140016e10`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`
- `0x140016e3e`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsStandaloneHostingModelEnabled(LPCWSTR lpValueName, int *a2, BYTE *a3)
{
  LSTATUS v6; // ebx
  LSTATUS v7; // ebx
  LSTATUS v9; // ebx
  LSTATUS v10; // ebx
  LSTATUS v11; // ebx
  LSTATUS v12; // ebx
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  cbData = 4;
  Type = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20019u, &hKey) )
  {
    cbData = 0;
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    if ( (!v6 || v6 == 234) && Type == 1 )
      goto LABEL_11;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20219u, &hKey) )
  {
    cbData = 0;
    v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    if ( (!v11 || v11 == 234) && Type == 1 )
      goto LABEL_11;
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20019u,
          &hKey)
    && ((cbData = 0, v10 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v10)
     || v10 == 234)
    && Type == 1
    || !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20219u,
          &hKey)
    && ((cbData = 0, v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v7) || v7 == 234)
    && Type == 1 )
  {
LABEL_11:
    *a2 = 0;
    return 0;
  }
  Type = 1;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\StandaloneProviders", 0, 0x20019u, &hKey)
    && ((v12 = RegQueryValueExW(hKey, lpValueName, 0, &Type, a3, &cbData), RegCloseKey(hKey), !v12) || v12 == 234)
    && Type == 1
    || (v9 = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\StandaloneProviders",
               0,
               0x20219u,
               &hKey)) == 0
    && ((cbData = 0, v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, a3, &cbData), RegCloseKey(hKey), !v9)
     || v9 == 234)
    && Type == 1 )
  {
    *a2 = 1;
    return 0;
  }
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140016d1c  mov     [rsp-28h+arg_0], rbx
0x140016d21  mov     [rsp-28h+arg_8], rsi
0x140016d26  push    rbp
0x140016d27  push    rdi
0x140016d28  push    r12
0x140016d2a  push    r13
0x140016d2c  push    r14
0x140016d2e  mov     rbp, rsp
0x140016d31  sub     rsp, 40h
0x140016d35  mov     r14, r8
0x140016d38  mov     [rbp+hKey], 0
0x140016d40  mov     rsi, rdx
0x140016d43  mov     [rbp+cbData], 4
0x140016d4a  mov     rdi, rcx
0x140016d4d  lea     rax, [rbp+hKey]
0x140016d51  mov     r12d, 1
0x140016d57  mov     [rsp+40h+phkResult], rax; phkResult
0x140016d5c  xor     r8d, r8d; ulOptions
0x140016d5f  mov     [rbp+Type], r12d
0x140016d63  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x140016d6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140016d71  mov     r9d, 20019h; samDesired
0x140016d77  call    cs:__imp_RegOpenKeyExW
0x140016d7d  mov     r13d, 0EAh
0x140016d83  test    eax, eax
0x140016d85  jnz     short loc_140016DD0
0x140016d87  mov     rcx, [rbp+hKey]; hKey
0x140016d8b  lea     r9, [rbp+Type]; lpType
0x140016d8f  mov     [rbp+cbData], eax
0x140016d92  xor     r8d, r8d; lpReserved
0x140016d95  lea     rax, [rbp+cbData]
0x140016d99  mov     rdx, rdi; lpValueName
0x140016d9c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140016da1  mov     [rsp+40h+phkResult], 0; lpData
0x140016daa  call    cs:__imp_RegQueryValueExW
0x140016db0  mov     rcx, [rbp+hKey]; hKey
0x140016db4  mov     ebx, eax
0x140016db6  call    cs:__imp_RegCloseKey
0x140016dbc  test    ebx, ebx
0x140016dbe  jnz     short loc_140016DCB
0x140016dc0  cmp     [rbp+Type], r12d
0x140016dc4  jnz     short loc_140016DD0
0x140016dc6  jmp     loc_140016E99
0x140016dcb  cmp     ebx, r13d
0x140016dce  jz      short loc_140016DC0
0x140016dd0  lea     rax, [rbp+hKey]
0x140016dd4  mov     r9d, 20219h; samDesired
0x140016dda  xor     r8d, r8d; ulOptions
0x140016ddd  mov     [rsp+40h+phkResult], rax; phkResult
0x140016de2  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x140016de9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140016df0  call    cs:__imp_RegOpenKeyExW
0x140016df6  test    eax, eax
0x140016df8  jz      loc_140016F8A
0x140016dfe  lea     rax, [rbp+hKey]
0x140016e02  mov     r9d, 20019h; samDesired
0x140016e08  xor     r8d, r8d; ulOptions
0x140016e0b  mov     [rsp+40h+phkResult], rax; phkResult
0x140016e10  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x140016e17  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140016e1e  call    cs:__imp_RegOpenKeyExW
0x140016e24  test    eax, eax
0x140016e26  jz      loc_140016F35
0x140016e2c  lea     rax, [rbp+hKey]
0x140016e30  mov     r9d, 20219h; samDesired
0x140016e36  xor     r8d, r8d; ulOptions
0x140016e39  mov     [rsp+40h+phkResult], rax; phkResult
0x140016e3e  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x140016e45  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140016e4c  call    cs:__imp_RegOpenKeyExW
0x140016e52  test    eax, eax
0x140016e54  jnz     short loc_140016EB8
0x140016e56  mov     rcx, [rbp+hKey]; hKey
0x140016e5a  lea     r9, [rbp+Type]; lpType
0x140016e5e  mov     [rbp+cbData], eax
0x140016e61  xor     r8d, r8d; lpReserved
0x140016e64  lea     rax, [rbp+cbData]
0x140016e68  mov     rdx, rdi; lpValueName
0x140016e6b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140016e70  mov     [rsp+40h+phkResult], 0; lpData
0x140016e79  call    cs:__imp_RegQueryValueExW
0x140016e7f  mov     rcx, [rbp+hKey]; hKey
0x140016e83  mov     ebx, eax
0x140016e85  call    cs:__imp_RegCloseKey
0x140016e8b  test    ebx, ebx
0x140016e8d  jnz     loc_140016FD6
0x140016e93  cmp     [rbp+Type], r12d
0x140016e97  jnz     short loc_140016EB8
0x140016e99  mov     dword ptr [rsi], 0
0x140016e9f  xor     eax, eax
0x140016ea1  mov     rbx, [rsp+40h+arg_0]
0x140016ea6  mov     rsi, [rsp+40h+arg_8]
0x140016eab  add     rsp, 40h
0x140016eaf  pop     r14
0x140016eb1  pop     r13
0x140016eb3  pop     r12
0x140016eb5  pop     rdi
0x140016eb6  pop     rbp
0x140016eb7  retn
0x140016eb8  lea     rax, [rbp+hKey]
0x140016ebc  mov     [rbp+Type], r12d
0x140016ec0  mov     r9d, 20019h; samDesired
0x140016ec6  mov     [rsp+40h+phkResult], rax; phkResult
0x140016ecb  xor     r8d, r8d; ulOptions
0x140016ece  mov     [rbp+cbData], 4
0x140016ed5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Stand"...
0x140016edc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140016ee3  call    cs:__imp_RegOpenKeyExW
0x140016ee9  test    eax, eax
0x140016eeb  jz      loc_140016FEF
0x140016ef1  lea     rax, [rbp+hKey]
0x140016ef5  mov     r9d, 20219h; samDesired
0x140016efb  xor     r8d, r8d; ulOptions
0x140016efe  mov     [rsp+40h+phkResult], rax; phkResult
0x140016f03  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Stand"...
0x140016f0a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140016f11  call    cs:__imp_RegOpenKeyExW
0x140016f17  mov     ebx, eax
0x140016f19  test    eax, eax
0x140016f1b  jz      loc_140017035
0x140016f21  test    ebx, ebx
0x140016f23  jle     short loc_140016F2E
0x140016f25  movzx   ebx, bx
0x140016f28  or      ebx, 80070000h
0x140016f2e  mov     eax, ebx
0x140016f30  jmp     loc_140016EA1
0x140016f35  mov     rcx, [rbp+hKey]; hKey
0x140016f39  lea     rax, [rbp+cbData]
0x140016f3d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140016f42  lea     r9, [rbp+Type]; lpType
0x140016f46  xor     r8d, r8d; lpReserved
0x140016f49  mov     [rsp+40h+phkResult], 0; lpData
0x140016f52  mov     rdx, rdi; lpValueName
0x140016f55  mov     [rbp+cbData], 0
0x140016f5c  call    cs:__imp_RegQueryValueExW
0x140016f62  mov     rcx, [rbp+hKey]; hKey
0x140016f66  mov     ebx, eax
0x140016f68  call    cs:__imp_RegCloseKey
0x140016f6e  test    ebx, ebx
0x140016f70  jz      short loc_140016F7B
0x140016f72  cmp     ebx, r13d
0x140016f75  jnz     loc_140016E2C
0x140016f7b  cmp     [rbp+Type], r12d
0x140016f7f  jnz     loc_140016E2C
0x140016f85  jmp     loc_140016E99
0x140016f8a  mov     rcx, [rbp+hKey]; hKey
0x140016f8e  lea     rax, [rbp+cbData]
0x140016f92  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140016f97  lea     r9, [rbp+Type]; lpType
0x140016f9b  xor     r8d, r8d; lpReserved
0x140016f9e  mov     [rsp+40h+phkResult], 0; lpData
0x140016fa7  mov     rdx, rdi; lpValueName
0x140016faa  mov     [rbp+cbData], 0
0x140016fb1  call    cs:__imp_RegQueryValueExW
0x140016fb7  mov     rcx, [rbp+hKey]; hKey
0x140016fbb  mov     ebx, eax
0x140016fbd  call    cs:__imp_RegCloseKey
0x140016fc3  test    ebx, ebx
0x140016fc5  jnz     short loc_140016FE4
0x140016fc7  cmp     [rbp+Type], r12d
0x140016fcb  jnz     loc_140016DFE
0x140016fd1  jmp     loc_140016E99
0x140016fd6  cmp     ebx, r13d
0x140016fd9  jz      loc_140016E93
0x140016fdf  jmp     loc_140016EB8
0x140016fe4  cmp     ebx, r13d
0x140016fe7  jnz     loc_140016DFE
0x140016fed  jmp     short loc_140016FC7
0x140016fef  mov     rcx, [rbp+hKey]; hKey
0x140016ff3  lea     rax, [rbp+cbData]
0x140016ff7  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140016ffc  lea     r9, [rbp+Type]; lpType
0x140017000  xor     r8d, r8d; lpReserved
0x140017003  mov     [rsp+40h+phkResult], r14; lpData
0x140017008  mov     rdx, rdi; lpValueName
0x14001700b  call    cs:__imp_RegQueryValueExW
0x140017011  mov     rcx, [rbp+hKey]; hKey
0x140017015  mov     ebx, eax
0x140017017  call    cs:__imp_RegCloseKey
0x14001701d  test    ebx, ebx
0x14001701f  jz      short loc_14001702A
0x140017021  cmp     ebx, r13d
0x140017024  jnz     loc_140016EF1
0x14001702a  cmp     [rbp+Type], r12d
0x14001702e  jz      short loc_140017081
0x140017030  jmp     loc_140016EF1
0x140017035  mov     rcx, [rbp+hKey]; hKey
0x140017039  lea     rax, [rbp+cbData]
0x14001703d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140017042  lea     r9, [rbp+Type]; lpType
0x140017046  xor     r8d, r8d; lpReserved
0x140017049  mov     [rsp+40h+phkResult], r14; lpData
0x14001704e  mov     rdx, rdi; lpValueName
0x140017051  mov     [rbp+cbData], 0
0x140017058  call    cs:__imp_RegQueryValueExW
0x14001705e  mov     rcx, [rbp+hKey]; hKey
0x140017062  mov     ebx, eax
0x140017064  call    cs:__imp_RegCloseKey
0x14001706a  test    ebx, ebx
0x14001706c  jz      short loc_140017077
0x14001706e  cmp     ebx, r13d
0x140017071  jnz     loc_140016F21
0x140017077  cmp     [rbp+Type], r12d
0x14001707b  jnz     loc_140016F21
0x140017081  mov     [rsi], r12d
0x140017084  jmp     loc_140016E9F
```
