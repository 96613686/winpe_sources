# CscInitializeCertChainStore(void *)

- ea: `0x140001920`
- end: `0x140001ab1`
- name: `?CscInitializeCertChainStore@@YAKPEAX@Z`
- size: `401`
- prototype: `__int64 __fastcall(HCERTSTORE hCertStore)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140001fa0`

## callees

- `0x140001920`
- `0x140001ab8`
- `0x140002d60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001a94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001a94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000198d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000198d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001a70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001a70`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140001a4b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140001a4b`
- `CRYPT32!CertFreeCertificateContext` at `0x1400019fc`
- `CRYPT32!CertFreeCertificateContext` at `0x140001aa9`
- `CRYPT32!CertFreeCertificateContext` at `0x1400019fc`
- `CRYPT32!CertFreeCertificateContext` at `0x140001aa9`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1400019e9`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1400019e9`

## pseudocode

```c
__int64 __fastcall CscInitializeCertChainStore(HCERTSTORE hCertStore)
{
  unsigned int LastError; // ebx
  DWORD v3; // esi
  DWORD i; // edx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  cchName = 0;
  ftLastWriteTime = 0;
  pCertContext = 0;
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Control\\AppID\\CertChainStore\\",
                0,
                0x20019u,
                &hKey);
  if ( !LastError )
  {
    v3 = 0;
    for ( i = 0; ; i = v3 )
    {
      cchName = 260;
      LastError = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( LastError )
      {
        if ( LastError == 259 )
          LastError = 0;
        goto LABEL_9;
      }
      LastError = CscReadCertFromStore(hKey, Name, &pCertContext);
      if ( LastError )
        break;
      if ( !CertAddCertificateContextToStore(hCertStore, pCertContext, 1u, 0) )
      {
        LastError = GetLastError();
        break;
      }
      CertFreeCertificateContext(pCertContext);
      pCertContext = 0;
      ++v3;
    }
    if ( pCertContext )
      CertFreeCertificateContext(pCertContext);
  }
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
  return LastError;
}

```

## disassembly

```asm
0x140001920  push    rbp
0x140001922  push    rbx
0x140001923  push    rsi
0x140001924  push    r14
0x140001926  lea     rbp, [rsp-188h]
0x14000192e  sub     rsp, 288h
0x140001935  mov     rax, cs:__security_cookie
0x14000193c  xor     rax, rsp
0x14000193f  mov     [rbp+1A0h+var_30], rax
0x140001946  mov     r14, rcx
0x140001949  mov     [rsp+2A0h+hKey], 0
0x140001952  lea     rax, [rsp+2A0h+hKey]
0x140001957  mov     [rsp+2A0h+cchName], 0
0x14000195f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140001966  mov     [rsp+2A0h+phkResult], rax; phkResult
0x14000196b  mov     r9d, 20019h; samDesired
0x140001971  mov     qword ptr [rsp+2A0h+ftLastWriteTime.dwLowDateTime], 0
0x14000197a  xor     r8d, r8d; ulOptions
0x14000197d  mov     [rsp+2A0h+pCertContext], 0
0x140001986  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\App"...
0x14000198d  call    cs:__imp_RegOpenKeyExW
0x140001993  mov     ebx, eax
0x140001995  test    eax, eax
0x140001997  jnz     loc_140001A66
0x14000199d  xor     esi, esi
0x14000199f  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x1400019a4  mov     [rsp+2A0h+lpftLastWriteTime], rax
0x1400019a9  xor     edx, edx
0x1400019ab  mov     [rsp+2A0h+lpcchClass], rsi
0x1400019b0  mov     [rsp+2A0h+lpClass], rsi
0x1400019b5  mov     [rsp+2A0h+phkResult], rsi
0x1400019ba  jmp     short loc_140001A34
0x1400019bc  mov     rcx, [rsp+2A0h+hKey]; HKEY
0x1400019c1  lea     r8, [rsp+2A0h+pCertContext]; struct _CERT_CONTEXT **
0x1400019c6  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x1400019cb  call    ?CscReadCertFromStore@@YAKPEAUHKEY__@@PEBGPEAPEBU_CERT_CONTEXT@@@Z; CscReadCertFromStore(HKEY__ *,ushort const *,_CERT_CONTEXT const * *)
0x1400019d0  mov     ebx, eax
0x1400019d2  test    eax, eax
0x1400019d4  jnz     loc_140001A9C
0x1400019da  mov     rdx, [rsp+2A0h+pCertContext]; pCertContext
0x1400019df  lea     r8d, [rax+1]; dwAddDisposition
0x1400019e3  xor     r9d, r9d; ppStoreContext
0x1400019e6  mov     rcx, r14; hCertStore
0x1400019e9  call    cs:__imp_CertAddCertificateContextToStore
0x1400019ef  test    eax, eax
0x1400019f1  jz      loc_140001A94
0x1400019f7  mov     rcx, [rsp+2A0h+pCertContext]; pCertContext
0x1400019fc  call    cs:__imp_CertFreeCertificateContext
0x140001a02  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x140001a07  mov     [rsp+2A0h+pCertContext], 0
0x140001a10  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140001a15  inc     esi
0x140001a17  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x140001a20  mov     edx, esi; dwIndex
0x140001a22  mov     [rsp+2A0h+lpClass], 0; lpClass
0x140001a2b  mov     [rsp+2A0h+phkResult], 0; lpReserved
0x140001a34  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140001a39  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x140001a3e  lea     r8, [rsp+2A0h+Name]; lpName
0x140001a43  mov     [rsp+2A0h+cchName], 104h
0x140001a4b  call    cs:__imp_RegEnumKeyExW
0x140001a51  mov     ebx, eax
0x140001a53  test    eax, eax
0x140001a55  jz      loc_1400019BC
0x140001a5b  xor     eax, eax
0x140001a5d  cmp     ebx, 103h
0x140001a63  cmovz   ebx, eax
0x140001a66  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140001a6b  test    rcx, rcx
0x140001a6e  jz      short loc_140001A76
0x140001a70  call    cs:__imp_RegCloseKey
0x140001a76  mov     eax, ebx
0x140001a78  mov     rcx, [rbp+1A0h+var_30]
0x140001a7f  xor     rcx, rsp; StackCookie
0x140001a82  call    __security_check_cookie
0x140001a87  add     rsp, 288h
0x140001a8e  pop     r14
0x140001a90  pop     rsi
0x140001a91  pop     rbx
0x140001a92  pop     rbp
0x140001a93  retn
0x140001a94  call    cs:__imp_GetLastError
0x140001a9a  mov     ebx, eax
0x140001a9c  cmp     [rsp+2A0h+pCertContext], 0
0x140001aa2  jz      short loc_140001A66
0x140001aa4  mov     rcx, [rsp+2A0h+pCertContext]; pCertContext
0x140001aa9  call    cs:__imp_CertFreeCertificateContext
0x140001aaf  jmp     short loc_140001A66
```
