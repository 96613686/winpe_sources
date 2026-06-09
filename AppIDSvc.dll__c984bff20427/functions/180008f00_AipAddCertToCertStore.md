# AipAddCertToCertStore

- ea: `0x180008f00`
- end: `0x180009098`
- name: `AipAddCertToCertStore`
- size: `408`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, HKEY *, DWORD *, HANDLE hTransaction)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800090a0`
- `0x18000944c`

## callees

- `0x180008f00`
- `0x18000aa84`
- `0x18000c0e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009074`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009074`
- `CRYPT32!CryptHashCertificate` at `0x180008f72`
- `CRYPT32!CryptHashCertificate` at `0x180008f72`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x18000902c`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x18000902c`

## pseudocode

```c
__int64 __fastcall AipAddCertToCertStore(HKEY hKey, __int64 a2, HKEY *a3, DWORD *a4, HANDLE hTransaction)
{
  const BYTE *v6; // r9
  DWORD cbEncoded; // eax
  DWORD LastError; // ebx
  HKEY v12; // rcx
  __int64 i; // rbx
  DWORD pcbComputedHash; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-98h] BYREF
  BYTE pbComputedHash[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[80]; // [rsp+90h] [rbp-70h] BYREF

  v6 = *(const BYTE **)(a2 + 8);
  cbEncoded = *(_DWORD *)(a2 + 16);
  hKeya = 0;
  pcbComputedHash = 32;
  if ( !CryptHashCertificate(0, 0x8004u, 0, v6, cbEncoded, pbComputedHash, &pcbComputedHash) )
  {
    LastError = GetLastError();
LABEL_3:
    v12 = hKeya;
    goto LABEL_4;
  }
  for ( i = 0; (unsigned int)i < pcbComputedHash; i = (unsigned int)(i + 1) )
    RtlStringCchPrintfW(&SubKey[(unsigned int)(2 * i)], 80LL - (unsigned int)(2 * i), L"%2.2x", pbComputedHash[i]);
  LastError = RegCreateKeyTransactedW(hKey, SubKey, 0, 0, 0, 0x20006u, 0, &hKeya, a4, hTransaction, 0);
  if ( LastError )
    goto LABEL_3;
  if ( *a4 == 2 )
  {
    *a3 = hKeya;
    return LastError;
  }
  LastError = RegSetValueExW(hKeya, L"CertData", 0, 3u, *(const BYTE **)(a2 + 8), *(_DWORD *)(a2 + 16));
  if ( LastError )
    goto LABEL_3;
  v12 = 0;
  *a3 = hKeya;
  hKeya = 0;
LABEL_4:
  if ( v12 )
    RegCloseKey(v12);
  return LastError;
}

```

## disassembly

```asm
0x180008f00  push    rbp
0x180008f02  push    rbx
0x180008f03  push    rsi
0x180008f04  push    rdi
0x180008f05  push    r12
0x180008f07  push    r14
0x180008f09  push    r15
0x180008f0b  lea     rbp, [rsp-40h]
0x180008f10  sub     rsp, 140h
0x180008f17  mov     rax, cs:__security_cookie
0x180008f1e  xor     rax, rsp
0x180008f21  mov     [rbp+70h+var_40], rax
0x180008f25  mov     r12, [rbp+70h+arg_20]
0x180008f2c  lea     rax, [rsp+170h+var_110]
0x180008f31  mov     [rsp+170h+pcbComputedHash], rax; pcbComputedHash
0x180008f36  mov     r14, r9
0x180008f39  mov     r9, [rdx+8]; pbEncoded
0x180008f3d  lea     rax, [rsp+170h+var_100]
0x180008f42  mov     [rsp+170h+pbComputedHash], rax; pbComputedHash
0x180008f47  mov     rdi, r8
0x180008f4a  mov     eax, [rdx+10h]
0x180008f4d  mov     rsi, rdx
0x180008f50  mov     r15, rcx
0x180008f53  mov     [rsp+170h+hKey], 0
0x180008f5c  mov     edx, 8004h; Algid
0x180008f61  mov     [rsp+170h+var_110], 20h ; ' '
0x180008f69  xor     r8d, r8d; dwFlags
0x180008f6c  mov     [rsp+170h+cbEncoded], eax; cbEncoded
0x180008f70  xor     ecx, ecx; hCryptProv
0x180008f72  call    cs:__imp_CryptHashCertificate
0x180008f78  test    eax, eax
0x180008f7a  jnz     short loc_180008FB4
0x180008f7c  call    cs:__imp_GetLastError
0x180008f82  mov     ebx, eax
0x180008f84  mov     rcx, [rsp+170h+hKey]; hKey
0x180008f89  test    rcx, rcx
0x180008f8c  jz      short loc_180008F94
0x180008f8e  call    cs:__imp_RegCloseKey
0x180008f94  mov     eax, ebx
0x180008f96  mov     rcx, [rbp+70h+var_40]
0x180008f9a  xor     rcx, rsp; StackCookie
0x180008f9d  call    __security_check_cookie
0x180008fa2  add     rsp, 140h
0x180008fa9  pop     r15
0x180008fab  pop     r14
0x180008fad  pop     r12
0x180008faf  pop     rdi
0x180008fb0  pop     rsi
0x180008fb1  pop     rbx
0x180008fb2  pop     rbp
0x180008fb3  retn
0x180008fb4  xor     ebx, ebx
0x180008fb6  cmp     [rsp+170h+var_110], ebx
0x180008fba  jbe     short loc_180008FE9
0x180008fbc  movzx   r9d, [rsp+rbx+170h+var_100]
0x180008fc2  lea     ecx, [rbx+rbx]
0x180008fc5  lea     rax, [rbp+70h+SubKey]
0x180008fc9  mov     edx, 50h ; 'P'
0x180008fce  sub     rdx, rcx
0x180008fd1  lea     r8, a22x; "%2.2x"
0x180008fd8  lea     rcx, [rax+rcx*2]
0x180008fdc  call    RtlStringCchPrintfW
0x180008fe1  inc     ebx
0x180008fe3  cmp     ebx, [rsp+170h+var_110]
0x180008fe7  jb      short loc_180008FBC
0x180008fe9  mov     [rsp+170h+pExtendedParemeter], 0; pExtendedParemeter
0x180008ff2  lea     rax, [rsp+170h+hKey]
0x180008ff7  mov     [rsp+170h+hTransaction], r12; hTransaction
0x180008ffc  lea     rdx, [rbp+70h+SubKey]; lpSubKey
0x180009000  mov     [rsp+170h+lpdwDisposition], r14; lpdwDisposition
0x180009005  xor     r9d, r9d; lpClass
0x180009008  mov     [rsp+170h+phkResult], rax; phkResult
0x18000900d  xor     r8d, r8d; Reserved
0x180009010  mov     [rsp+170h+pcbComputedHash], 0; lpSecurityAttributes
0x180009019  mov     rcx, r15; hKey
0x18000901c  mov     dword ptr [rsp+170h+pbComputedHash], 20006h; samDesired
0x180009024  mov     [rsp+170h+cbEncoded], 0; dwOptions
0x18000902c  call    cs:__imp_RegCreateKeyTransactedW
0x180009032  mov     ebx, eax
0x180009034  test    eax, eax
0x180009036  jnz     loc_180008F84
0x18000903c  cmp     dword ptr [r14], 2
0x180009040  jnz     short loc_18000904F
0x180009042  mov     rax, [rsp+170h+hKey]
0x180009047  mov     [rdi], rax
0x18000904a  jmp     loc_180008F94
0x18000904f  mov     eax, [rsi+10h]
0x180009052  lea     rdx, aCertdata; "CertData"
0x180009059  mov     rcx, [rsp+170h+hKey]; hKey
0x18000905e  mov     r9d, 3; dwType
0x180009064  mov     dword ptr [rsp+170h+pbComputedHash], eax; cbData
0x180009068  xor     r8d, r8d; Reserved
0x18000906b  mov     rax, [rsi+8]
0x18000906f  mov     qword ptr [rsp+170h+cbEncoded], rax; lpData
0x180009074  call    cs:__imp_RegSetValueExW
0x18000907a  mov     ebx, eax
0x18000907c  test    eax, eax
0x18000907e  jnz     loc_180008F84
0x180009084  mov     rax, [rsp+170h+hKey]
0x180009089  xor     ecx, ecx
0x18000908b  mov     [rdi], rax
0x18000908e  mov     [rsp+170h+hKey], rcx
0x180009093  jmp     loc_180008F89
```
