# GetSignersFromCertContext

- ea: `0x180027f2c`
- end: `0x18002814f`
- name: `GetSignersFromCertContext`
- size: `547`
- prototype: `__int64 __fastcall(void *pvPara, PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800279a8`

## callees

- `0x180027a30`
- `0x180027f2c`
- `0x180028ef4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028025`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002812b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002812b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002807c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002807c`
- `CRYPT32!CertOpenStore` at `0x180027f94`
- `CRYPT32!CertOpenStore` at `0x180027f94`
- `CRYPT32!CertGetCertificateChain` at `0x18002801b`
- `CRYPT32!CertGetCertificateChain` at `0x18002801b`
- `CRYPT32!CertCloseStore` at `0x18002810e`
- `CRYPT32!CertCloseStore` at `0x18002810e`
- `CRYPT32!CertFreeCertificateChain` at `0x18002811d`
- `CRYPT32!CertFreeCertificateChain` at `0x18002811d`

## pseudocode

```c
__int64 __fastcall GetSignersFromCertContext(void *pvPara, PCCERT_CONTEXT pCertContext, __int64 a3, __int64 a4)
{
  signed int v8; // ebx
  HCERTSTORE v9; // r14
  signed int v10; // eax
  unsigned int v11; // ebx
  signed int LastError; // eax
  unsigned int v13; // ebx
  PCERT_SIMPLE_CHAIN *rgpChain; // rcx
  PCERT_SIMPLE_CHAIN v15; // rax
  HLOCAL v16; // rax
  PCCERT_CHAIN_CONTEXT v17; // r9
  __int64 v18; // rsi
  DWORD cElement; // eax
  _CERT_CHAIN_PARA pChainPara; // [rsp+40h] [rbp-28h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+B0h] [rbp+48h] BYREF

  pChainContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  if ( a3 && (*(_DWORD *)(a3 + 4) & 0xFFFFFFFE) != 0 )
    return 3221225474LL;
  if ( a4 )
  {
    v9 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, pvPara);
    if ( v9 )
    {
      pChainPara.cbSize = 32;
      pChainPara.RequestedUsage.dwType = 0;
      if ( a3 && (*(_BYTE *)(a3 + 4) & 1) != 0 )
      {
        pChainPara.RequestedUsage.Usage.cUsageIdentifier = *(_DWORD *)(a3 + 8);
        pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)(a3 + 16);
      }
      if ( CertGetCertificateChain(
             (HCERTCHAINENGINE)1,
             pCertContext,
             0,
             v9,
             &pChainPara,
             0x400000C0u,
             0,
             &pChainContext) )
      {
        rgpChain = pChainContext->rgpChain;
        v15 = *rgpChain;
        if ( (*rgpChain)->cElement )
        {
          if ( (v15->TrustStatus.dwErrorStatus & 0x1C) != 0 )
          {
            v8 = -1073740760;
          }
          else
          {
            v16 = LocalAlloc(0x40u, 48LL * v15->cElement);
            *(_QWORD *)(a4 + 24) = v16;
            if ( v16 )
            {
              v17 = pChainContext;
              v18 = 0;
              cElement = (*pChainContext->rgpChain)->cElement;
              *(_DWORD *)(a4 + 32) = cElement;
              if ( cElement )
              {
                while ( 1 )
                {
                  v8 = FillSignerInfoFromCert((*v17->rgpChain)->rgpElement[v18]->pCertContext);
                  if ( v8 < 0 )
                    break;
                  cElement = *(_DWORD *)(a4 + 32);
                  v18 = (unsigned int)(v18 + 1);
                  if ( (unsigned int)v18 >= cElement )
                    goto LABEL_27;
                  v17 = pChainContext;
                }
              }
              else
              {
                v8 = 0;
LABEL_27:
                *(_DWORD *)(a4 + 36) = SIPolicyRootCertHashToKnownRoot(
                                         *(void **)(*(_QWORD *)(a4 + 24) + 48LL * (cElement - 1) + 8),
                                         *(unsigned int *)(*(_QWORD *)(a4 + 24) + 48LL * (cElement - 1) + 4));
              }
            }
            else
            {
              v8 = -1073741801;
            }
          }
        }
        else
        {
          v8 = -1073741823;
        }
      }
      else
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        v8 = v13 & 0xAFFFFFFF | 0x40000000;
      }
      CertCloseStore(v9, 0);
    }
    else
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      v8 = v11 & 0xAFFFFFFF | 0x40000000;
    }
    if ( pChainContext )
      CertFreeCertificateChain(pChainContext);
    if ( v8 >= 0 )
      return (unsigned int)v8;
  }
  else
  {
    v8 = -1073741583;
  }
  LocalFree(*(HLOCAL *)(a4 + 24));
  *(_QWORD *)(a4 + 24) = 0;
  *(_DWORD *)(a4 + 32) = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180027f2c  push    rbp
0x180027f2e  push    rbx
0x180027f2f  push    rsi
0x180027f30  push    rdi
0x180027f31  push    r14
0x180027f33  push    r15
0x180027f35  mov     rbp, rsp
0x180027f38  sub     rsp, 68h
0x180027f3c  mov     [rbp+pChainContext], 0
0x180027f44  xorps   xmm0, xmm0
0x180027f47  mov     rdi, r9
0x180027f4a  mov     rbx, r8
0x180027f4d  mov     r15, rdx
0x180027f50  movups  xmmword ptr [rbp+pChainPara.cbSize], xmm0
0x180027f54  movups  xmmword ptr [rbp+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180027f58  test    r8, r8
0x180027f5b  jz      short loc_180027F71
0x180027f5d  test    dword ptr [r8+4], 0FFFFFFFEh
0x180027f65  jz      short loc_180027F71
0x180027f67  mov     eax, 0C0000002h
0x180027f6c  jmp     loc_180028142
0x180027f71  test    rdi, rdi
0x180027f74  jnz     short loc_180027F80
0x180027f76  mov     ebx, 0C00000F1h
0x180027f7b  jmp     loc_180028127
0x180027f80  xor     r9d, r9d; dwFlags
0x180027f83  mov     [rsp+68h+pvPara], rcx; pvPara
0x180027f88  xor     r8d, r8d; hCryptProv
0x180027f8b  mov     edx, 10001h; dwEncodingType
0x180027f90  lea     ecx, [r9+1]; lpszStoreProvider
0x180027f94  call    cs:__imp_CertOpenStore
0x180027f9a  mov     r14, rax
0x180027f9d  test    rax, rax
0x180027fa0  jnz     short loc_180027FC4
0x180027fa2  call    cs:__imp_GetLastError
0x180027fa8  mov     ebx, eax
0x180027faa  test    eax, eax
0x180027fac  jle     short loc_180027FB7
0x180027fae  movzx   ebx, ax
0x180027fb1  or      ebx, 80070000h
0x180027fb7  btr     ebx, 1Ch
0x180027fbb  bts     ebx, 1Eh
0x180027fbf  jmp     loc_180028114
0x180027fc4  mov     [rbp+pChainPara.cbSize], 20h ; ' '
0x180027fcb  mov     [rbp+pChainPara.RequestedUsage.dwType], 0
0x180027fd2  test    rbx, rbx
0x180027fd5  jz      short loc_180027FEB
0x180027fd7  test    byte ptr [rbx+4], 1
0x180027fdb  jz      short loc_180027FEB
0x180027fdd  mov     eax, [rbx+8]
0x180027fe0  mov     [rbp+pChainPara.RequestedUsage.Usage.cUsageIdentifier], eax
0x180027fe3  lea     rax, [rbx+10h]
0x180027fe7  mov     [rbp+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x180027feb  xor     r8d, r8d; pTime
0x180027fee  lea     rax, [rbp+pChainContext]
0x180027ff2  mov     [rsp+68h+ppChainContext], rax; ppChainContext
0x180027ff7  mov     r9, r14; hAdditionalStore
0x180027ffa  mov     [rsp+68h+pvReserved], 0; pvReserved
0x180028003  lea     rax, [rbp+pChainPara]
0x180028007  mov     [rsp+68h+dwFlags], 400000C0h; dwFlags
0x18002800f  mov     rdx, r15; pCertContext
0x180028012  lea     ecx, [r8+1]; hChainEngine
0x180028016  mov     [rsp+68h+pvPara], rax; pChainPara
0x18002801b  call    cs:__imp_CertGetCertificateChain
0x180028021  test    eax, eax
0x180028023  jnz     short loc_180028047
0x180028025  call    cs:__imp_GetLastError
0x18002802b  mov     ebx, eax
0x18002802d  test    eax, eax
0x18002802f  jle     short loc_18002803A
0x180028031  movzx   ebx, ax
0x180028034  or      ebx, 80070000h
0x18002803a  btr     ebx, 1Ch
0x18002803e  bts     ebx, 1Eh
0x180028042  jmp     loc_180028109
0x180028047  mov     rax, [rbp+pChainContext]
0x18002804b  mov     rcx, [rax+10h]
0x18002804f  mov     rax, [rcx]
0x180028052  cmp     dword ptr [rax+0Ch], 0
0x180028056  jnz     short loc_180028062
0x180028058  mov     ebx, 0C0000001h
0x18002805d  jmp     loc_180028109
0x180028062  test    byte ptr [rax+4], 1Ch
0x180028066  jnz     loc_180028104
0x18002806c  mov     eax, [rax+0Ch]
0x18002806f  mov     ecx, 40h ; '@'; uFlags
0x180028074  lea     rdx, [rax+rax*2]
0x180028078  shl     rdx, 4; uBytes
0x18002807c  call    cs:__imp_LocalAlloc
0x180028082  mov     [rdi+18h], rax
0x180028086  test    rax, rax
0x180028089  jnz     short loc_180028092
0x18002808b  mov     ebx, 0C0000017h
0x180028090  jmp     short loc_180028109
0x180028092  mov     r9, [rbp+pChainContext]
0x180028096  xor     esi, esi
0x180028098  mov     rax, [r9+10h]
0x18002809c  mov     rcx, [rax]
0x18002809f  mov     eax, [rcx+0Ch]
0x1800280a2  mov     [rdi+20h], eax
0x1800280a5  test    eax, eax
0x1800280a7  jz      short loc_1800280E2
0x1800280a9  mov     rax, [r9+10h]
0x1800280ad  lea     rdx, [rsi+rsi*2]
0x1800280b1  shl     rdx, 4
0x1800280b5  add     rdx, [rdi+18h]
0x1800280b9  mov     rcx, [rax]
0x1800280bc  mov     rax, [rcx+10h]
0x1800280c0  mov     rcx, [rax+rsi*8]
0x1800280c4  mov     rcx, [rcx+8]; pCertContext
0x1800280c8  call    FillSignerInfoFromCert
0x1800280cd  mov     ebx, eax
0x1800280cf  test    eax, eax
0x1800280d1  js      short loc_180028109
0x1800280d3  mov     eax, [rdi+20h]
0x1800280d6  inc     esi
0x1800280d8  cmp     esi, eax
0x1800280da  jnb     short loc_1800280E4
0x1800280dc  mov     r9, [rbp+pChainContext]
0x1800280e0  jmp     short loc_1800280A9
0x1800280e2  xor     ebx, ebx
0x1800280e4  mov     rcx, [rdi+18h]
0x1800280e8  dec     eax
0x1800280ea  lea     rax, [rax+rax*2]
0x1800280ee  add     rax, rax
0x1800280f1  mov     edx, [rcx+rax*8+4]; Size
0x1800280f5  mov     rcx, [rcx+rax*8+8]; Buf2
0x1800280fa  call    SIPolicyRootCertHashToKnownRoot
0x1800280ff  mov     [rdi+24h], eax
0x180028102  jmp     short loc_180028109
0x180028104  mov     ebx, 0C0000428h
0x180028109  xor     edx, edx; dwFlags
0x18002810b  mov     rcx, r14; hCertStore
0x18002810e  call    cs:__imp_CertCloseStore
0x180028114  mov     rcx, [rbp+pChainContext]; pChainContext
0x180028118  test    rcx, rcx
0x18002811b  jz      short loc_180028123
0x18002811d  call    cs:__imp_CertFreeCertificateChain
0x180028123  test    ebx, ebx
0x180028125  jns     short loc_180028140
0x180028127  mov     rcx, [rdi+18h]; hMem
0x18002812b  call    cs:__imp_LocalFree
0x180028131  mov     qword ptr [rdi+18h], 0
0x180028139  mov     dword ptr [rdi+20h], 0
0x180028140  mov     eax, ebx
0x180028142  add     rsp, 68h
0x180028146  pop     r15
0x180028148  pop     r14
0x18002814a  pop     rdi
0x18002814b  pop     rsi
0x18002814c  pop     rbx
0x18002814d  pop     rbp
0x18002814e  retn
```
