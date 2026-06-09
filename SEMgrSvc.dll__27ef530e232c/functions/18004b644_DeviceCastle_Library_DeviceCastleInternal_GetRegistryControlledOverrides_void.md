# DeviceCastle::Library::DeviceCastleInternal::GetRegistryControlledOverrides(void)

- ea: `0x18004b644`
- end: `0x18004ba3e`
- name: `?GetRegistryControlledOverrides@DeviceCastleInternal@Library@DeviceCastle@@AEAA_NXZ`
- size: `1018`
- prototype: `bool __fastcall(DeviceCastle::Library::DeviceCastleInternal *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004c438`

## callees

- `0x1800049a0`
- `0x18004b644`
- `0x18005c6d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ba0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ba0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b6a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b6a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b6f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b742`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b795`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b7fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b84e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b8a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b8f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b947`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b99a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b9ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b6f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b742`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b795`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b7fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b84e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b8a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b8f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b947`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b99a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b9ea`

## pseudocode

```c
char __fastcall DeviceCastle::Library::DeviceCastleInternal::GetRegistryControlledOverrides(
        DeviceCastle::Library::DeviceCastleInternal *this)
{
  HKEY v2; // rdi
  char v3; // bl
  DWORD Type; // [rsp+30h] [rbp-49h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-45h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-39h] BYREF
  WCHAR SubKey[48]; // [rsp+50h] [rbp-29h] BYREF

  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800ABEA0);
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
    return 0;
  v2 = hKey;
  *(_DWORD *)Data = 0;
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800ABF60);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
    *((_DWORD *)this + 34) = *(_DWORD *)Data;
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800AC020);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
    *((_BYTE *)this + 145) = *(_DWORD *)Data != 0;
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800ABFC0);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
  {
    *(_QWORD *)cbData = 10000LL * *(unsigned int *)Data;
    *(_QWORD *)((char *)this + 148) = *(_QWORD *)cbData;
  }
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800ABBD0);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
    *((_BYTE *)this + 141) = *(_DWORD *)Data != 0;
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800ABC30);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
    *((_BYTE *)this + 142) = *(_DWORD *)Data != 0;
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800ABF00);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
    *((_BYTE *)this + 143) = *(_DWORD *)Data != 0;
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800AC0E0);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
    *((_BYTE *)this + 144) = *(_DWORD *)Data != 0;
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800AC080);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
    *((_BYTE *)this + 156) = *(_DWORD *)Data != 0;
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800ABE40);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
    *((_DWORD *)this + 40) = *(_DWORD *)Data;
  DeviceCastle::Library::Internal::RevealedString::Load(
    (DeviceCastle::Library::Internal::RevealedString *)SubKey,
    (const struct DeviceCastle::Library::Internal::ObscuredString *)qword_1800ABE40);
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v2, SubKey, 0, &Type, Data, cbData) && Type == 4 )
    *((_DWORD *)this + 41) = *(_DWORD *)Data;
  v3 = 1;
  if ( v2 )
    RegCloseKey(v2);
  return v3;
}

```

## disassembly

```asm
0x18004b644  mov     [rsp-8+arg_8], rbx
0x18004b649  mov     [rsp-8+arg_10], rsi
0x18004b64e  push    rbp
0x18004b64f  push    rdi
0x18004b650  push    r14
0x18004b652  lea     rbp, [rsp-47h]
0x18004b657  sub     rsp, 0C0h
0x18004b65e  mov     rax, cs:__security_cookie
0x18004b665  xor     rax, rsp
0x18004b668  mov     [rbp+57h+var_20], rax
0x18004b66c  mov     rbx, rcx
0x18004b66f  lea     rdx, qword_1800ABEA0; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b676  lea     rcx, [rbp+57h+SubKey]; this
0x18004b67a  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b67f  lea     rax, [rbp+57h+hKey]
0x18004b683  xor     esi, esi
0x18004b685  mov     r9d, 20019h; samDesired
0x18004b68b  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18004b690  xor     r8d, r8d; ulOptions
0x18004b693  mov     [rbp+57h+hKey], rsi
0x18004b697  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18004b69b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b6a2  call    cs:__imp_RegOpenKeyExW
0x18004b6a8  test    eax, eax
0x18004b6aa  jnz     loc_18004BA15
0x18004b6b0  mov     rdi, [rbp+57h+hKey]
0x18004b6b4  lea     rdx, qword_1800ABF60; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b6bb  lea     rcx, [rbp+57h+SubKey]; this
0x18004b6bf  mov     dword ptr [rbp+57h+Data], esi
0x18004b6c2  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b6c7  lea     rax, [rbp+57h+cbData]
0x18004b6cb  mov     [rbp+57h+Type], esi
0x18004b6ce  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b6d3  lea     r14d, [rsi+4]
0x18004b6d7  lea     rax, [rbp+57h+Data]
0x18004b6db  mov     [rbp+57h+cbData], r14d
0x18004b6df  lea     r9, [rbp+57h+Type]; lpType
0x18004b6e3  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b6e8  xor     r8d, r8d; lpReserved
0x18004b6eb  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b6ef  mov     rcx, rdi; hKey
0x18004b6f2  call    cs:__imp_RegQueryValueExW
0x18004b6f8  test    eax, eax
0x18004b6fa  jnz     short loc_18004B70B
0x18004b6fc  cmp     [rbp+57h+Type], r14d
0x18004b700  jnz     short loc_18004B70B
0x18004b702  mov     eax, dword ptr [rbp+57h+Data]
0x18004b705  mov     [rbx+88h], eax
0x18004b70b  lea     rdx, qword_1800AC020; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b712  lea     rcx, [rbp+57h+SubKey]; this
0x18004b716  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b71b  lea     rax, [rbp+57h+cbData]
0x18004b71f  mov     [rbp+57h+Type], esi
0x18004b722  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b727  lea     r9, [rbp+57h+Type]; lpType
0x18004b72b  lea     rax, [rbp+57h+Data]
0x18004b72f  mov     [rbp+57h+cbData], r14d
0x18004b733  xor     r8d, r8d; lpReserved
0x18004b736  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b73b  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b73f  mov     rcx, rdi; hKey
0x18004b742  call    cs:__imp_RegQueryValueExW
0x18004b748  test    eax, eax
0x18004b74a  jnz     short loc_18004B75E
0x18004b74c  cmp     [rbp+57h+Type], r14d
0x18004b750  jnz     short loc_18004B75E
0x18004b752  cmp     dword ptr [rbp+57h+Data], esi
0x18004b755  setnz   al
0x18004b758  mov     [rbx+91h], al
0x18004b75e  lea     rdx, qword_1800ABFC0; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b765  lea     rcx, [rbp+57h+SubKey]; this
0x18004b769  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b76e  lea     rax, [rbp+57h+cbData]
0x18004b772  mov     [rbp+57h+Type], esi
0x18004b775  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b77a  lea     r9, [rbp+57h+Type]; lpType
0x18004b77e  lea     rax, [rbp+57h+Data]
0x18004b782  mov     [rbp+57h+cbData], r14d
0x18004b786  xor     r8d, r8d; lpReserved
0x18004b789  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b78e  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b792  mov     rcx, rdi; hKey
0x18004b795  call    cs:__imp_RegQueryValueExW
0x18004b79b  test    eax, eax
0x18004b79d  jnz     short loc_18004B7C4
0x18004b79f  cmp     [rbp+57h+Type], r14d
0x18004b7a3  jnz     short loc_18004B7C4
0x18004b7a5  mov     eax, dword ptr [rbp+57h+Data]
0x18004b7a8  imul    rax, 2710h
0x18004b7af  mov     [rbp+57h+cbData], eax
0x18004b7b2  shr     rax, 20h
0x18004b7b6  mov     [rbp+57h+cbData+4], eax
0x18004b7b9  mov     rax, qword ptr [rbp+57h+cbData]
0x18004b7bd  mov     [rbx+94h], rax
0x18004b7c4  lea     rdx, qword_1800ABBD0; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b7cb  lea     rcx, [rbp+57h+SubKey]; this
0x18004b7cf  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b7d4  lea     rax, [rbp+57h+cbData]
0x18004b7d8  mov     [rbp+57h+Type], esi
0x18004b7db  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b7e0  lea     r9, [rbp+57h+Type]; lpType
0x18004b7e4  lea     rax, [rbp+57h+Data]
0x18004b7e8  mov     [rbp+57h+cbData], r14d
0x18004b7ec  xor     r8d, r8d; lpReserved
0x18004b7ef  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b7f4  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b7f8  mov     rcx, rdi; hKey
0x18004b7fb  call    cs:__imp_RegQueryValueExW
0x18004b801  test    eax, eax
0x18004b803  jnz     short loc_18004B817
0x18004b805  cmp     [rbp+57h+Type], r14d
0x18004b809  jnz     short loc_18004B817
0x18004b80b  cmp     dword ptr [rbp+57h+Data], esi
0x18004b80e  setnz   al
0x18004b811  mov     [rbx+8Dh], al
0x18004b817  lea     rdx, qword_1800ABC30; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b81e  lea     rcx, [rbp+57h+SubKey]; this
0x18004b822  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b827  lea     rax, [rbp+57h+cbData]
0x18004b82b  mov     [rbp+57h+Type], esi
0x18004b82e  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b833  lea     r9, [rbp+57h+Type]; lpType
0x18004b837  lea     rax, [rbp+57h+Data]
0x18004b83b  mov     [rbp+57h+cbData], r14d
0x18004b83f  xor     r8d, r8d; lpReserved
0x18004b842  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b847  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b84b  mov     rcx, rdi; hKey
0x18004b84e  call    cs:__imp_RegQueryValueExW
0x18004b854  test    eax, eax
0x18004b856  jnz     short loc_18004B86A
0x18004b858  cmp     [rbp+57h+Type], r14d
0x18004b85c  jnz     short loc_18004B86A
0x18004b85e  cmp     dword ptr [rbp+57h+Data], esi
0x18004b861  setnz   al
0x18004b864  mov     [rbx+8Eh], al
0x18004b86a  lea     rdx, qword_1800ABF00; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b871  lea     rcx, [rbp+57h+SubKey]; this
0x18004b875  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b87a  lea     rax, [rbp+57h+cbData]
0x18004b87e  mov     [rbp+57h+Type], esi
0x18004b881  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b886  lea     r9, [rbp+57h+Type]; lpType
0x18004b88a  lea     rax, [rbp+57h+Data]
0x18004b88e  mov     [rbp+57h+cbData], r14d
0x18004b892  xor     r8d, r8d; lpReserved
0x18004b895  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b89a  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b89e  mov     rcx, rdi; hKey
0x18004b8a1  call    cs:__imp_RegQueryValueExW
0x18004b8a7  test    eax, eax
0x18004b8a9  jnz     short loc_18004B8BD
0x18004b8ab  cmp     [rbp+57h+Type], r14d
0x18004b8af  jnz     short loc_18004B8BD
0x18004b8b1  cmp     dword ptr [rbp+57h+Data], esi
0x18004b8b4  setnz   al
0x18004b8b7  mov     [rbx+8Fh], al
0x18004b8bd  lea     rdx, qword_1800AC0E0; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b8c4  lea     rcx, [rbp+57h+SubKey]; this
0x18004b8c8  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b8cd  lea     rax, [rbp+57h+cbData]
0x18004b8d1  mov     [rbp+57h+Type], esi
0x18004b8d4  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b8d9  lea     r9, [rbp+57h+Type]; lpType
0x18004b8dd  lea     rax, [rbp+57h+Data]
0x18004b8e1  mov     [rbp+57h+cbData], r14d
0x18004b8e5  xor     r8d, r8d; lpReserved
0x18004b8e8  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b8ed  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b8f1  mov     rcx, rdi; hKey
0x18004b8f4  call    cs:__imp_RegQueryValueExW
0x18004b8fa  test    eax, eax
0x18004b8fc  jnz     short loc_18004B910
0x18004b8fe  cmp     [rbp+57h+Type], r14d
0x18004b902  jnz     short loc_18004B910
0x18004b904  cmp     dword ptr [rbp+57h+Data], esi
0x18004b907  setnz   al
0x18004b90a  mov     [rbx+90h], al
0x18004b910  lea     rdx, qword_1800AC080; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b917  lea     rcx, [rbp+57h+SubKey]; this
0x18004b91b  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b920  lea     rax, [rbp+57h+cbData]
0x18004b924  mov     [rbp+57h+Type], esi
0x18004b927  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b92c  lea     r9, [rbp+57h+Type]; lpType
0x18004b930  lea     rax, [rbp+57h+Data]
0x18004b934  mov     [rbp+57h+cbData], r14d
0x18004b938  xor     r8d, r8d; lpReserved
0x18004b93b  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b940  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b944  mov     rcx, rdi; hKey
0x18004b947  call    cs:__imp_RegQueryValueExW
0x18004b94d  test    eax, eax
0x18004b94f  jnz     short loc_18004B963
0x18004b951  cmp     [rbp+57h+Type], r14d
0x18004b955  jnz     short loc_18004B963
0x18004b957  cmp     dword ptr [rbp+57h+Data], esi
0x18004b95a  setnz   al
0x18004b95d  mov     [rbx+9Ch], al
0x18004b963  lea     rdx, qword_1800ABE40; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b96a  lea     rcx, [rbp+57h+SubKey]; this
0x18004b96e  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b973  lea     rax, [rbp+57h+cbData]
0x18004b977  mov     [rbp+57h+Type], esi
0x18004b97a  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b97f  lea     r9, [rbp+57h+Type]; lpType
0x18004b983  lea     rax, [rbp+57h+Data]
0x18004b987  mov     [rbp+57h+cbData], r14d
0x18004b98b  xor     r8d, r8d; lpReserved
0x18004b98e  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b993  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b997  mov     rcx, rdi; hKey
0x18004b99a  call    cs:__imp_RegQueryValueExW
0x18004b9a0  test    eax, eax
0x18004b9a2  jnz     short loc_18004B9B3
0x18004b9a4  cmp     [rbp+57h+Type], r14d
0x18004b9a8  jnz     short loc_18004B9B3
0x18004b9aa  mov     eax, dword ptr [rbp+57h+Data]
0x18004b9ad  mov     [rbx+0A0h], eax
0x18004b9b3  lea     rdx, qword_1800ABE40; struct DeviceCastle::Library::Internal::ObscuredString *
0x18004b9ba  lea     rcx, [rbp+57h+SubKey]; this
0x18004b9be  call    ?Load@RevealedString@Internal@Library@DeviceCastle@@QEAAXAEBVObscuredString@234@@Z; DeviceCastle::Library::Internal::RevealedString::Load(DeviceCastle::Library::Internal::ObscuredString const &)
0x18004b9c3  lea     rax, [rbp+57h+cbData]
0x18004b9c7  mov     [rbp+57h+Type], esi
0x18004b9ca  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004b9cf  lea     r9, [rbp+57h+Type]; lpType
0x18004b9d3  lea     rax, [rbp+57h+Data]
0x18004b9d7  mov     [rbp+57h+cbData], r14d
0x18004b9db  xor     r8d, r8d; lpReserved
0x18004b9de  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004b9e3  lea     rdx, [rbp+57h+SubKey]; lpValueName
0x18004b9e7  mov     rcx, rdi; hKey
0x18004b9ea  call    cs:__imp_RegQueryValueExW
0x18004b9f0  test    eax, eax
0x18004b9f2  jnz     short loc_18004BA03
0x18004b9f4  cmp     [rbp+57h+Type], r14d
0x18004b9f8  jnz     short loc_18004BA03
0x18004b9fa  mov     eax, dword ptr [rbp+57h+Data]
0x18004b9fd  mov     [rbx+0A4h], eax
0x18004ba03  mov     bl, 1
0x18004ba05  test    rdi, rdi
0x18004ba08  jz      short loc_18004BA18
0x18004ba0a  mov     rcx, rdi; hKey
0x18004ba0d  call    cs:__imp_RegCloseKey
0x18004ba13  jmp     short loc_18004BA18
0x18004ba15  mov     bl, sil
0x18004ba18  mov     al, bl
0x18004ba1a  mov     rcx, [rbp+57h+var_20]
0x18004ba1e  xor     rcx, rsp; StackCookie
0x18004ba21  call    __security_check_cookie
0x18004ba26  lea     r11, [rsp+0D0h+var_10]
0x18004ba2e  mov     rbx, [r11+28h]
0x18004ba32  mov     rsi, [r11+30h]
0x18004ba36  mov     rsp, r11
0x18004ba39  pop     r14
0x18004ba3b  pop     rdi
0x18004ba3c  pop     rbp
0x18004ba3d  retn
```
