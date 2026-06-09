# CscReadCertFromStore(HKEY__ *,ushort const *,_CERT_CONTEXT const * *)

- ea: `0x140001ab8`
- end: `0x140001bbc`
- name: `?CscReadCertFromStore@@YAKPEAUHKEY__@@PEBGPEAPEBU_CERT_CONTEXT@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const struct _CERT_CONTEXT **)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140001920`
- `0x140001fa0`

## callees

- `0x140001ab8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001b91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001aef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001aef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001b26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001b6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001b26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001b6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001bab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001bab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001b9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001b9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140001b38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140001b38`
- `CRYPT32!CertCreateCertificateContext` at `0x140001b83`
- `CRYPT32!CertCreateCertificateContext` at `0x140001b83`

## pseudocode

```c
__int64 __fastcall CscReadCertFromStore(HKEY a1, const unsigned __int16 *a2, const struct _CERT_CONTEXT **a3)
{
  DWORD LastError; // ebx
  BYTE *v5; // rdi
  const struct _CERT_CONTEXT *CertificateContext; // rax
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+40h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  LastError = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( !LastError )
  {
    cbData = 0;
    LastError = RegQueryValueExW(hKey, L"CertData", 0, &Type, 0, &cbData);
    if ( !LastError )
    {
      v5 = (BYTE *)LocalAlloc(0x40u, cbData);
      if ( v5 )
      {
        LastError = RegQueryValueExW(hKey, L"CertData", 0, &Type, v5, &cbData);
        if ( !LastError )
        {
          CertificateContext = CertCreateCertificateContext(0x10001u, v5, cbData);
          *a3 = CertificateContext;
          if ( !CertificateContext )
            LastError = GetLastError();
        }
        LocalFree(v5);
      }
      else
      {
        LastError = 8;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return LastError;
}

```

## disassembly

```asm
0x140001ab8  push    rbp
0x140001aba  push    rbx
0x140001abb  push    rsi
0x140001abc  push    rdi
0x140001abd  mov     rbp, rsp
0x140001ac0  sub     rsp, 48h
0x140001ac4  mov     rsi, r8
0x140001ac7  mov     [rbp+hKey], 0
0x140001acf  lea     rax, [rbp+hKey]
0x140001ad3  mov     [rbp+cbData], 0
0x140001ada  xor     r8d, r8d; ulOptions
0x140001add  mov     [rsp+48h+phkResult], rax; phkResult
0x140001ae2  mov     r9d, 20019h; samDesired
0x140001ae8  mov     [rbp+Type], 0
0x140001aef  call    cs:__imp_RegOpenKeyExW
0x140001af5  mov     ebx, eax
0x140001af7  test    eax, eax
0x140001af9  jnz     loc_140001BA2
0x140001aff  mov     rcx, [rbp+hKey]; hKey
0x140001b03  lea     r9, [rbp+Type]; lpType
0x140001b07  mov     [rbp+cbData], eax
0x140001b0a  lea     rdx, ValueName; "CertData"
0x140001b11  lea     rax, [rbp+cbData]
0x140001b15  xor     r8d, r8d; lpReserved
0x140001b18  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140001b1d  mov     [rsp+48h+phkResult], 0; lpData
0x140001b26  call    cs:__imp_RegQueryValueExW
0x140001b2c  mov     ebx, eax
0x140001b2e  test    eax, eax
0x140001b30  jnz     short loc_140001BA2
0x140001b32  mov     edx, [rbp+cbData]; uBytes
0x140001b35  lea     ecx, [rax+40h]; uFlags
0x140001b38  call    cs:__imp_LocalAlloc
0x140001b3e  mov     rdi, rax
0x140001b41  test    rax, rax
0x140001b44  jnz     short loc_140001B4B
0x140001b46  lea     ebx, [rax+8]
0x140001b49  jmp     short loc_140001BA2
0x140001b4b  mov     rcx, [rbp+hKey]; hKey
0x140001b4f  lea     rax, [rbp+cbData]
0x140001b53  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140001b58  lea     r9, [rbp+Type]; lpType
0x140001b5c  xor     r8d, r8d; lpReserved
0x140001b5f  mov     [rsp+48h+phkResult], rdi; lpData
0x140001b64  lea     rdx, ValueName; "CertData"
0x140001b6b  call    cs:__imp_RegQueryValueExW
0x140001b71  mov     ebx, eax
0x140001b73  test    eax, eax
0x140001b75  jnz     short loc_140001B99
0x140001b77  mov     r8d, [rbp+cbData]; cbCertEncoded
0x140001b7b  mov     rdx, rdi; pbCertEncoded
0x140001b7e  mov     ecx, 10001h; dwCertEncodingType
0x140001b83  call    cs:__imp_CertCreateCertificateContext
0x140001b89  mov     [rsi], rax
0x140001b8c  test    rax, rax
0x140001b8f  jnz     short loc_140001B99
0x140001b91  call    cs:__imp_GetLastError
0x140001b97  mov     ebx, eax
0x140001b99  mov     rcx, rdi; hMem
0x140001b9c  call    cs:__imp_LocalFree
0x140001ba2  mov     rcx, [rbp+hKey]; hKey
0x140001ba6  test    rcx, rcx
0x140001ba9  jz      short loc_140001BB1
0x140001bab  call    cs:__imp_RegCloseKey
0x140001bb1  mov     eax, ebx
0x140001bb3  add     rsp, 48h
0x140001bb7  pop     rdi
0x140001bb8  pop     rsi
0x140001bb9  pop     rbx
0x140001bba  pop     rbp
0x140001bbb  retn
```
