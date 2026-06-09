# GetCertChainContext

- ea: `0x18000bfac`
- end: `0x18000c21e`
- name: `GetCertChainContext`
- size: `626`
- prototype: `__int64 __fastcall(__int64, PCCERT_CHAIN_CONTEXT **, DWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000c788`
- `0x18000da90`

## callees

- `0x1800014b0`
- `0x18000bf64`
- `0x18000bfac`
- `0x18000e2d4`
- `0x18000ea2c`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c142`
- `CRYPT32!CertFreeCertificateChainList` at `0x18000c1aa`
- `CRYPT32!CertFreeCertificateChainList` at `0x18000c1aa`
- `CRYPT32!CertOpenStore` at `0x18000c130`
- `CRYPT32!CertOpenStore` at `0x18000c130`
- `CRYPT32!CertSelectCertificateChains` at `0x18000c175`
- `CRYPT32!CertSelectCertificateChains` at `0x18000c175`
- `CRYPT32!CertCloseStore` at `0x18000c1ef`
- `CRYPT32!CertCloseStore` at `0x18000c1ef`

## pseudocode

```c
__int64 __fastcall GetCertChainContext(__int64 a1, PCCERT_CHAIN_CONTEXT **a2, DWORD *a3)
{
  CERT_SELECT_CRITERIA *v3; // rsi
  LPVOID *v4; // r15
  __int64 v5; // r14
  DWORD LastError; // edi
  __int64 v9; // rax
  __int64 v10; // r12
  DWORD v11; // eax
  __int64 v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // rax
  DWORD *v15; // rcx
  __int64 i; // r12
  unsigned int v18; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-3Ch]
  HCERTSTORE hCertStore; // [rsp+48h] [rbp-38h]
  DWORD *v21; // [rsp+50h] [rbp-30h]
  PCCERT_CHAIN_CONTEXT *prgpSelection; // [rsp+58h] [rbp-28h] BYREF
  DWORD pcSelection; // [rsp+60h] [rbp-20h] BYREF
  const char *v24; // [rsp+68h] [rbp-18h] BYREF

  v3 = 0;
  v21 = a3;
  v4 = 0;
  prgpSelection = 0;
  LODWORD(v5) = 0;
  pcSelection = 0;
  hCertStore = 0;
  v18 = 0;
  v24 = "1.3.6.1.5.5.7.3.2";
  if ( a2 )
    *a2 = 0;
  if ( a1 && a2 )
  {
    v5 = *(unsigned int *)(a1 + 40);
    v9 = Dns_Allocate(16LL * (unsigned int)(v5 + 1));
    v3 = (CERT_SELECT_CRITERIA *)v9;
    if ( v9
      && ((*(_DWORD *)v9 = 1, *(_DWORD *)(v9 + 4) = 1, *(_QWORD *)(v9 + 8) = &v24, !(_DWORD)v5)
       || (v4 = (LPVOID *)Dns_Allocate(8 * v5)) != 0) )
    {
      v19 = 1;
      v10 = 0;
      while ( 1 )
      {
        if ( (unsigned int)v10 >= (unsigned int)v5 )
        {
          hCertStore = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"my");
          if ( hCertStore && CertSelectCertificateChains(0, 8u, 0, v5 + 1, v3, hCertStore, &pcSelection, &prgpSelection) )
          {
            LastError = 0;
            v15 = v21;
            *a2 = prgpSelection;
            prgpSelection = 0;
            *v15 = pcSelection;
          }
          else
          {
            LastError = GetLastError();
          }
          goto LABEL_21;
        }
        v11 = Dns_CheckedStringLength(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * v10), 256, 1, &v18);
        LastError = v11;
        if ( v11 )
          break;
        v12 = Dns_StringCopyAllocate(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * v10), v18, 1, 3);
        v13 = (__int64 *)&v4[v10];
        *v13 = v12;
        if ( !v12 )
          goto LABEL_4;
        v14 = v19++;
        v10 = (unsigned int)(v10 + 1);
        v3[v14].dwType = 1;
        v3[v14].cPara = 1;
        v3[v14].ppPara = (void **)v13;
      }
      if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
        WPP_SF_d(1035, 55, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, v11);
    }
    else
    {
      LastError = 14;
    }
  }
  else
  {
LABEL_4:
    LastError = 87;
  }
LABEL_21:
  FreeCertChain(prgpSelection, pcSelection);
  if ( prgpSelection )
    CertFreeCertificateChainList(prgpSelection);
  if ( v4 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v5; i = (unsigned int)(i + 1) )
    {
      Dns_Free(v4[i]);
      v4[i] = 0;
    }
    Dns_Free(v4);
  }
  Dns_Free(v3);
  CertCloseStore(hCertStore, 2u);
  return LastError;
}

```

## disassembly

```asm
0x18000bfac  mov     [rsp-38h+arg_18], rbx
0x18000bfb1  push    rbp
0x18000bfb2  push    rsi
0x18000bfb3  push    rdi
0x18000bfb4  push    r12
0x18000bfb6  push    r13
0x18000bfb8  push    r14
0x18000bfba  push    r15
0x18000bfbc  mov     rbp, rsp
0x18000bfbf  sub     rsp, 80h
0x18000bfc6  mov     rax, cs:__security_cookie
0x18000bfcd  xor     rax, rsp
0x18000bfd0  mov     [rbp+var_10], rax
0x18000bfd4  xor     esi, esi
0x18000bfd6  mov     [rbp+var_30], r8
0x18000bfda  xor     r15d, r15d
0x18000bfdd  mov     [rbp+prgpSelection], 0
0x18000bfe5  xor     r14d, r14d
0x18000bfe8  mov     [rbp+var_20], 0
0x18000bfef  mov     [rbp+hCertStore], 0
0x18000bff7  lea     rax, a136155732; "1.3.6.1.5.5.7.3.2"
0x18000bffe  mov     [rbp+var_40], esi
0x18000c001  mov     rbx, rdx
0x18000c004  mov     [rbp+var_18], rax
0x18000c008  mov     r13, rcx
0x18000c00b  test    rdx, rdx
0x18000c00e  jz      short loc_18000C013
0x18000c010  mov     [rdx], rsi
0x18000c013  test    r13, r13
0x18000c016  jnz     short loc_18000C022
0x18000c018  mov     edi, 57h ; 'W'
0x18000c01d  jmp     loc_18000C195
0x18000c022  test    rbx, rbx
0x18000c025  jz      short loc_18000C018
0x18000c027  mov     r14d, [rcx+28h]
0x18000c02b  lea     ecx, [r14+1]
0x18000c02f  shl     rcx, 4
0x18000c033  call    Dns_Allocate
0x18000c038  mov     rsi, rax
0x18000c03b  test    rax, rax
0x18000c03e  jnz     short loc_18000C04A
0x18000c040  mov     edi, 0Eh
0x18000c045  jmp     loc_18000C195
0x18000c04a  mov     edi, 1
0x18000c04f  mov     [rax], edi
0x18000c051  mov     [rax+4], edi
0x18000c054  lea     rax, [rbp+var_18]
0x18000c058  mov     [rsi+8], rax
0x18000c05c  test    r14d, r14d
0x18000c05f  jz      short loc_18000C075
0x18000c061  mov     rcx, r14
0x18000c064  shl     rcx, 3
0x18000c068  call    Dns_Allocate
0x18000c06d  mov     r15, rax
0x18000c070  test    rax, rax
0x18000c073  jz      short loc_18000C040
0x18000c075  mov     [rbp+var_3C], edi
0x18000c078  xor     r12d, r12d
0x18000c07b  cmp     r12d, r14d
0x18000c07e  jnb     loc_18000C116
0x18000c084  mov     rcx, [r13+20h]
0x18000c088  lea     r9, [rbp+var_40]
0x18000c08c  mov     r8d, edi
0x18000c08f  mov     edx, 100h
0x18000c094  mov     rcx, [rcx+r12*8]
0x18000c098  call    Dns_CheckedStringLength
0x18000c09d  mov     edi, eax
0x18000c09f  test    eax, eax
0x18000c0a1  jnz     short loc_18000C0EE
0x18000c0a3  mov     rcx, [r13+20h]
0x18000c0a7  lea     r9d, [rax+3]
0x18000c0ab  mov     edx, [rbp+var_40]
0x18000c0ae  lea     r8d, [rax+1]
0x18000c0b2  mov     rcx, [rcx+r12*8]
0x18000c0b6  call    Dns_StringCopyAllocate
0x18000c0bb  lea     rdx, [r15+r12*8]
0x18000c0bf  mov     [rdx], rax
0x18000c0c2  test    rax, rax
0x18000c0c5  jz      loc_18000C018
0x18000c0cb  mov     ecx, [rbp+var_3C]
0x18000c0ce  mov     edi, 1
0x18000c0d3  mov     eax, ecx
0x18000c0d5  add     ecx, edi
0x18000c0d7  add     rax, rax
0x18000c0da  mov     [rbp+var_3C], ecx
0x18000c0dd  add     r12d, edi
0x18000c0e0  mov     [rsi+rax*8], edi
0x18000c0e3  mov     [rsi+rax*8+4], edi
0x18000c0e7  mov     [rsi+rax*8+8], rdx
0x18000c0ec  jmp     short loc_18000C07B
0x18000c0ee  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000c0f5  jz      loc_18000C195
0x18000c0fb  mov     edx, 37h ; '7'
0x18000c100  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000c107  mov     ecx, 40Bh
0x18000c10c  mov     r9d, eax
0x18000c10f  call    WPP_SF_d
0x18000c114  jmp     short loc_18000C195
0x18000c116  xor     edx, edx; dwEncodingType
0x18000c118  lea     rax, aMy; "my"
0x18000c11f  mov     r9d, 28000h; dwFlags
0x18000c125  mov     [rsp+80h+pvPara], rax; pvPara
0x18000c12a  xor     r8d, r8d; hCryptProv
0x18000c12d  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18000c130  call    cs:__imp_CertOpenStore
0x18000c136  mov     [rbp+hCertStore], rax
0x18000c13a  mov     r12, rax
0x18000c13d  test    rax, rax
0x18000c140  jnz     short loc_18000C14C
0x18000c142  call    cs:__imp_GetLastError
0x18000c148  mov     edi, eax
0x18000c14a  jmp     short loc_18000C195
0x18000c14c  lea     rax, [rbp+prgpSelection]
0x18000c150  xor     r8d, r8d; pChainParameters
0x18000c153  mov     [rsp+80h+pprgpSelection], rax; pprgpSelection
0x18000c158  lea     r9d, [r14+1]; cCriteria
0x18000c15c  lea     rax, [rbp+var_20]
0x18000c160  xor     ecx, ecx; pSelectionContext
0x18000c162  mov     [rsp+80h+pcSelection], rax; pcSelection
0x18000c167  mov     [rsp+80h+hStore], r12; hStore
0x18000c16c  lea     edx, [r8+8]; dwFlags
0x18000c170  mov     [rsp+80h+pvPara], rsi; rgpCriteria
0x18000c175  call    cs:__imp_CertSelectCertificateChains
0x18000c17b  test    eax, eax
0x18000c17d  jz      short loc_18000C142
0x18000c17f  mov     rax, [rbp+prgpSelection]
0x18000c183  xor     edi, edi
0x18000c185  mov     rcx, [rbp+var_30]
0x18000c189  mov     [rbx], rax
0x18000c18c  mov     eax, [rbp+var_20]
0x18000c18f  mov     [rbp+prgpSelection], rdi
0x18000c193  mov     [rcx], eax
0x18000c195  mov     edx, [rbp+var_20]
0x18000c198  mov     rcx, [rbp+prgpSelection]
0x18000c19c  call    FreeCertChain
0x18000c1a1  mov     rcx, [rbp+prgpSelection]; prgpSelection
0x18000c1a5  test    rcx, rcx
0x18000c1a8  jz      short loc_18000C1B0
0x18000c1aa  call    cs:__imp_CertFreeCertificateChainList
0x18000c1b0  test    r15, r15
0x18000c1b3  jz      short loc_18000C1DE
0x18000c1b5  xor     r12d, r12d
0x18000c1b8  test    r14d, r14d
0x18000c1bb  jz      short loc_18000C1D6
0x18000c1bd  mov     rcx, [r15+r12*8]; lpMem
0x18000c1c1  call    Dns_Free
0x18000c1c6  mov     qword ptr [r15+r12*8], 0
0x18000c1ce  inc     r12d
0x18000c1d1  cmp     r12d, r14d
0x18000c1d4  jb      short loc_18000C1BD
0x18000c1d6  mov     rcx, r15; lpMem
0x18000c1d9  call    Dns_Free
0x18000c1de  mov     rcx, rsi; lpMem
0x18000c1e1  call    Dns_Free
0x18000c1e6  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000c1ea  mov     edx, 2; dwFlags
0x18000c1ef  call    cs:__imp_CertCloseStore
0x18000c1f5  mov     eax, edi
0x18000c1f7  mov     rcx, [rbp+var_10]
0x18000c1fb  xor     rcx, rsp; StackCookie
0x18000c1fe  call    __security_check_cookie
0x18000c203  mov     rbx, [rsp+80h+arg_18]
0x18000c20b  add     rsp, 80h
0x18000c212  pop     r15
0x18000c214  pop     r14
0x18000c216  pop     r13
0x18000c218  pop     r12
0x18000c21a  pop     rdi
0x18000c21b  pop     rsi
0x18000c21c  pop     rbp
0x18000c21d  retn
```
