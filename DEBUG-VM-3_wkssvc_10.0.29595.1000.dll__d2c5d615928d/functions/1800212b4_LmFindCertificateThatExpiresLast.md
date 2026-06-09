# LmFindCertificateThatExpiresLast

- ea: `0x1800212b4`
- end: `0x180021391`
- name: `LmFindCertificateThatExpiresLast`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180020d14`
- `0x180021ff0`

## callees

- `0x1800212b4`
- `0x180021398`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002134c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002134c`
- `CRYPT32!CertOpenStore` at `0x1800212ec`
- `CRYPT32!CertOpenStore` at `0x1800212ec`
- `CRYPT32!CertFindCertificateInStore` at `0x180021328`
- `CRYPT32!CertFindCertificateInStore` at `0x180021328`

## pseudocode

```c
__int64 __fastcall LmFindCertificateThatExpiresLast(const void *a1, const void *a2, _QWORD *a3)
{
  HCERTSTORE v5; // r15
  unsigned int Thumbprint; // ebx
  const CERT_CONTEXT *pPrevCertContext; // rsi
  FILETIME NotAfter; // rbp
  PCCERT_CONTEXT CertificateInStore; // rax
  PCERT_INFO pCertInfo; // rdx

  v5 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, a1);
  if ( v5 )
  {
    pPrevCertContext = 0;
    Thumbprint = 1168;
    NotAfter = 0;
    while ( 1 )
    {
      CertificateInStore = CertFindCertificateInStore(v5, 0x10001u, 0, 0x80004u, a2, pPrevCertContext);
      pPrevCertContext = CertificateInStore;
      if ( !CertificateInStore )
        break;
      pCertInfo = CertificateInStore->pCertInfo;
      if ( *(_QWORD *)&pCertInfo->NotAfter > *(unsigned __int64 *)&NotAfter )
      {
        NotAfter = pCertInfo->NotAfter;
        Thumbprint = LmGetThumbprint(CertificateInStore);
        if ( Thumbprint )
          return Thumbprint;
      }
    }
    *a3 = 0;
  }
  else
  {
    return GetLastError();
  }
  return Thumbprint;
}

```

## disassembly

```asm
0x1800212b4  mov     rax, rsp
0x1800212b7  mov     [rax+8], rbx
0x1800212bb  mov     [rax+10h], rbp
0x1800212bf  push    rsi
0x1800212c0  push    rdi
0x1800212c1  push    r12
0x1800212c3  push    r14
0x1800212c5  push    r15
0x1800212c7  sub     rsp, 30h
0x1800212cb  xor     edi, edi
0x1800212cd  mov     [rax-38h], rcx
0x1800212d1  mov     r14, r8
0x1800212d4  mov     [rax+20h], rdi
0x1800212d8  mov     r12, rdx
0x1800212db  mov     r9d, 28000h; dwFlags
0x1800212e1  xor     r8d, r8d; hCryptProv
0x1800212e4  mov     edx, 10001h; dwEncodingType
0x1800212e9  lea     ecx, [rdi+0Ah]; lpszStoreProvider
0x1800212ec  call    cs:__imp_CertOpenStore
0x1800212f2  mov     r15, rax
0x1800212f5  test    rax, rax
0x1800212f8  jnz     short loc_180021304
0x1800212fa  call    cs:__imp_GetLastError
0x180021300  mov     ebx, eax
0x180021302  jmp     short loc_180021378
0x180021304  xor     esi, esi
0x180021306  mov     ebx, 490h
0x18002130b  xor     ebp, ebp
0x18002130d  mov     [rsp+58h+pPrevCertContext], rsi; pPrevCertContext
0x180021312  mov     r9d, 80004h; dwFindType
0x180021318  xor     r8d, r8d; dwFindFlags
0x18002131b  mov     [rsp+58h+pvFindPara], r12; pvFindPara
0x180021320  mov     edx, 10001h; dwCertEncodingType
0x180021325  mov     rcx, r15; hCertStore
0x180021328  call    cs:__imp_CertFindCertificateInStore
0x18002132e  mov     rsi, rax
0x180021331  test    rax, rax
0x180021334  jz      short loc_180021375
0x180021336  mov     rdx, [rax+18h]
0x18002133a  cmp     [rdx+48h], rbp
0x18002133e  jbe     short loc_18002130D
0x180021340  mov     rbp, [rdx+48h]
0x180021344  test    rdi, rdi
0x180021347  jz      short loc_18002135B
0x180021349  mov     rcx, rdi; hMem
0x18002134c  call    cs:__imp_LocalFree
0x180021352  mov     [rsp+58h+arg_18], 0
0x18002135b  lea     rdx, [rsp+58h+arg_18]
0x180021360  mov     rcx, rsi; pCertContext
0x180021363  call    LmGetThumbprint
0x180021368  mov     ebx, eax
0x18002136a  test    eax, eax
0x18002136c  jnz     short loc_180021378
0x18002136e  mov     rdi, [rsp+58h+arg_18]
0x180021373  jmp     short loc_18002130D
0x180021375  mov     [r14], rdi
0x180021378  mov     rbp, [rsp+58h+arg_8]
0x18002137d  mov     eax, ebx
0x18002137f  mov     rbx, [rsp+58h+arg_0]
0x180021384  add     rsp, 30h
0x180021388  pop     r15
0x18002138a  pop     r14
0x18002138c  pop     r12
0x18002138e  pop     rdi
0x18002138f  pop     rsi
0x180021390  retn
```
