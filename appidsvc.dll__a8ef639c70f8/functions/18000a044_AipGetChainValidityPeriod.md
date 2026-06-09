# AipGetChainValidityPeriod

- ea: `0x18000a044`
- end: `0x18000a0f0`
- name: `AipGetChainValidityPeriod`
- size: `172`
- prototype: `__int64 __fastcall(CRYPT_PROVIDER_SGNR *pSgnr, FILETIME *lpFileTime2, FILETIME *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000944c`

## callees

- `0x18000a044`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a092`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a0ba`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a092`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a0ba`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18000a075`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18000a075`

## pseudocode

```c
__int64 __fastcall AipGetChainValidityPeriod(CRYPT_PROVIDER_SGNR *pSgnr, FILETIME *lpFileTime2, FILETIME *a3)
{
  unsigned int v3; // esi
  DWORD v4; // ebx
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  CRYPT_PROVIDER_CERT *v9; // rdi

  v3 = 0;
  *lpFileTime2 = 0;
  v4 = 0;
  a3->dwLowDateTime = -1;
  a3->dwHighDateTime = -1;
  if ( pSgnr->csCertChain )
  {
    while ( 1 )
    {
      ProvCertFromChain = WTHelperGetProvCertFromChain(pSgnr, v4);
      v9 = ProvCertFromChain;
      if ( !ProvCertFromChain )
        break;
      if ( CompareFileTime(&ProvCertFromChain->pCert->pCertInfo->NotBefore, lpFileTime2) > 0 )
        *lpFileTime2 = v9->pCert->pCertInfo->NotBefore;
      if ( CompareFileTime(&v9->pCert->pCertInfo->NotAfter, a3) < 0 )
        *a3 = v9->pCert->pCertInfo->NotAfter;
      if ( ++v4 >= pSgnr->csCertChain )
        return v3;
    }
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x18000a044  push    rbx
0x18000a046  push    rbp
0x18000a047  push    rsi
0x18000a048  push    rdi
0x18000a049  push    r14
0x18000a04b  push    r15
0x18000a04d  sub     rsp, 28h
0x18000a051  or      eax, 0FFFFFFFFh
0x18000a054  xor     esi, esi
0x18000a056  mov     [rdx], rsi
0x18000a059  xor     ebx, ebx
0x18000a05b  mov     [r8], eax
0x18000a05e  mov     r14, r8
0x18000a061  mov     [r8+4], eax
0x18000a065  mov     r15, rdx
0x18000a068  mov     rbp, rcx
0x18000a06b  cmp     [rcx+0Ch], ebx
0x18000a06e  jbe     short loc_18000A0E1
0x18000a070  mov     edx, ebx; idxCert
0x18000a072  mov     rcx, rbp; pSgnr
0x18000a075  call    cs:__imp_WTHelperGetProvCertFromChain
0x18000a07b  mov     rdi, rax
0x18000a07e  test    rax, rax
0x18000a081  jz      short loc_18000A0DC
0x18000a083  mov     rax, [rax+8]
0x18000a087  mov     rdx, r15; lpFileTime2
0x18000a08a  mov     rcx, [rax+18h]
0x18000a08e  add     rcx, 40h ; '@'; lpFileTime1
0x18000a092  call    cs:__imp_CompareFileTime
0x18000a098  test    eax, eax
0x18000a09a  jle     short loc_18000A0AB
0x18000a09c  mov     rax, [rdi+8]
0x18000a0a0  mov     rcx, [rax+18h]
0x18000a0a4  mov     rax, [rcx+40h]
0x18000a0a8  mov     [r15], rax
0x18000a0ab  mov     rax, [rdi+8]
0x18000a0af  mov     rdx, r14; lpFileTime2
0x18000a0b2  mov     rcx, [rax+18h]
0x18000a0b6  add     rcx, 48h ; 'H'; lpFileTime1
0x18000a0ba  call    cs:__imp_CompareFileTime
0x18000a0c0  test    eax, eax
0x18000a0c2  jns     short loc_18000A0D3
0x18000a0c4  mov     rax, [rdi+8]
0x18000a0c8  mov     rcx, [rax+18h]
0x18000a0cc  mov     rax, [rcx+48h]
0x18000a0d0  mov     [r14], rax
0x18000a0d3  inc     ebx
0x18000a0d5  cmp     ebx, [rbp+0Ch]
0x18000a0d8  jb      short loc_18000A070
0x18000a0da  jmp     short loc_18000A0E1
0x18000a0dc  mov     esi, 57h ; 'W'
0x18000a0e1  mov     eax, esi
0x18000a0e3  add     rsp, 28h
0x18000a0e7  pop     r15
0x18000a0e9  pop     r14
0x18000a0eb  pop     rdi
0x18000a0ec  pop     rsi
0x18000a0ed  pop     rbp
0x18000a0ee  pop     rbx
0x18000a0ef  retn
```
