# GenerateCertificatesList

- ea: `0x18009d8e8`
- end: `0x18009d9d7`
- name: `GenerateCertificatesList`
- size: `239`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18009b5e0`
- `0x18009bdb4`

## callees

- `0x18009d8e8`
- `0x18009d9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d939`
- `CRYPT32!CertFreeCertificateContext` at `0x18009d9a3`
- `CRYPT32!CertFreeCertificateContext` at `0x18009d9a3`
- `CRYPT32!CertCloseStore` at `0x18009d9b0`
- `CRYPT32!CertCloseStore` at `0x18009d9c0`
- `CRYPT32!CertCloseStore` at `0x18009d9b0`
- `CRYPT32!CertCloseStore` at `0x18009d9c0`
- `CRYPT32!CertOpenStore` at `0x18009d92b`
- `CRYPT32!CertOpenStore` at `0x18009d980`
- `CRYPT32!CertOpenStore` at `0x18009d92b`
- `CRYPT32!CertOpenStore` at `0x18009d980`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18009d993`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18009d993`

## pseudocode

```c
__int64 __fastcall GenerateCertificatesList(unsigned int a1, __int64 a2, __int64 a3, int *a4)
{
  int v8; // edi
  HCERTSTORE v9; // rax
  void *v10; // r14
  unsigned int v11; // ebp
  void *v12; // rsi
  HCERTSTORE v13; // rax
  const CERT_CONTEXT *v14; // rax

  v8 = 1;
  if ( a4 )
    *a4 = 1;
  v9 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20000u, L"My");
  v10 = v9;
  if ( v9 )
  {
    v12 = 0;
    v11 = ListCertChainsInStore(a1, v9, a2, a3);
    if ( !v11 )
    {
      if ( a4 )
      {
        *a4 = 0;
        v13 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20000u, L"MY");
        v12 = v13;
        if ( v13 )
        {
          v14 = CertEnumCertificatesInStore(v13, 0);
          if ( v14 )
          {
            v8 = 0;
            CertFreeCertificateContext(v14);
          }
          *a4 = v8;
        }
      }
    }
    CertCloseStore(v10, 0);
    if ( v12 )
      CertCloseStore(v12, 0);
  }
  else
  {
    return GetLastError();
  }
  return v11;
}

```

## disassembly

```asm
0x18009d8e8  push    rbx
0x18009d8ea  push    rbp
0x18009d8eb  push    rsi
0x18009d8ec  push    rdi
0x18009d8ed  push    r12
0x18009d8ef  push    r14
0x18009d8f1  push    r15
0x18009d8f3  sub     rsp, 30h
0x18009d8f7  mov     rbx, r9
0x18009d8fa  mov     rbp, r8
0x18009d8fd  mov     r15, rdx
0x18009d900  mov     r12d, ecx
0x18009d903  mov     edi, 1
0x18009d908  test    r9, r9
0x18009d90b  jz      short loc_18009D910
0x18009d90d  mov     [r9], edi
0x18009d910  xor     r8d, r8d; hCryptProv
0x18009d913  lea     rax, aMy; "My"
0x18009d91a  mov     r9d, 20000h; dwFlags
0x18009d920  mov     [rsp+68h+pvPara], rax; pvPara
0x18009d925  mov     edx, edi; dwEncodingType
0x18009d927  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18009d92b  call    cs:__imp_CertOpenStore
0x18009d931  mov     r14, rax
0x18009d934  test    rax, rax
0x18009d937  jnz     short loc_18009D946
0x18009d939  call    cs:__imp_GetLastError
0x18009d93f  mov     ebp, eax
0x18009d941  jmp     loc_18009D9C6
0x18009d946  mov     r9, rbp
0x18009d949  mov     r8, r15
0x18009d94c  mov     rdx, r14
0x18009d94f  mov     ecx, r12d
0x18009d952  xor     esi, esi
0x18009d954  call    ListCertChainsInStore
0x18009d959  mov     ebp, eax
0x18009d95b  test    eax, eax
0x18009d95d  jnz     short loc_18009D9AB
0x18009d95f  test    rbx, rbx
0x18009d962  jz      short loc_18009D9AB
0x18009d964  lea     rax, aMy_0; "MY"
0x18009d96b  mov     [rbx], esi
0x18009d96d  mov     r9d, 20000h; dwFlags
0x18009d973  mov     [rsp+68h+pvPara], rax; pvPara
0x18009d978  xor     r8d, r8d; hCryptProv
0x18009d97b  lea     ecx, [rsi+0Ah]; lpszStoreProvider
0x18009d97e  mov     edx, edi; dwEncodingType
0x18009d980  call    cs:__imp_CertOpenStore
0x18009d986  mov     rsi, rax
0x18009d989  test    rax, rax
0x18009d98c  jz      short loc_18009D9AB
0x18009d98e  xor     edx, edx; pPrevCertContext
0x18009d990  mov     rcx, rax; hCertStore
0x18009d993  call    cs:__imp_CertEnumCertificatesInStore
0x18009d999  test    rax, rax
0x18009d99c  jz      short loc_18009D9A9
0x18009d99e  xor     edi, edi
0x18009d9a0  mov     rcx, rax; pCertContext
0x18009d9a3  call    cs:__imp_CertFreeCertificateContext
0x18009d9a9  mov     [rbx], edi
0x18009d9ab  xor     edx, edx; dwFlags
0x18009d9ad  mov     rcx, r14; hCertStore
0x18009d9b0  call    cs:__imp_CertCloseStore
0x18009d9b6  test    rsi, rsi
0x18009d9b9  jz      short loc_18009D9C6
0x18009d9bb  xor     edx, edx; dwFlags
0x18009d9bd  mov     rcx, rsi; hCertStore
0x18009d9c0  call    cs:__imp_CertCloseStore
0x18009d9c6  mov     eax, ebp
0x18009d9c8  add     rsp, 30h
0x18009d9cc  pop     r15
0x18009d9ce  pop     r14
0x18009d9d0  pop     r12
0x18009d9d2  pop     rdi
0x18009d9d3  pop     rsi
0x18009d9d4  pop     rbp
0x18009d9d5  pop     rbx
0x18009d9d6  retn
```
