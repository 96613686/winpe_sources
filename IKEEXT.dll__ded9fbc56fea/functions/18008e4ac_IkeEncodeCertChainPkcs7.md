# IkeEncodeCertChainPkcs7

- ea: `0x18008e4ac`
- end: `0x18008e699`
- name: `IkeEncodeCertChainPkcs7`
- size: `493`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004ab64`

## callees

- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180050850`
- `0x18008e4ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e5de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e5de`
- `CRYPT32!CertOpenStore` at `0x18008e506`
- `CRYPT32!CertOpenStore` at `0x18008e506`
- `CRYPT32!CertCloseStore` at `0x18008e641`
- `CRYPT32!CertCloseStore` at `0x18008e641`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18008e571`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18008e571`
- `CRYPT32!CertSaveStore` at `0x18008e5d4`
- `CRYPT32!CertSaveStore` at `0x18008e622`
- `CRYPT32!CertSaveStore` at `0x18008e5d4`
- `CRYPT32!CertSaveStore` at `0x18008e622`

## string_xrefs

- `0x18008e51d`: `CertOpenStore`

## pseudocode

```c
__int64 __fastcall IkeEncodeCertChainPkcs7(__int64 a1, __int64 a2)
{
  HCERTSTORE v4; // rsi
  DWORD LastError; // eax
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rbx
  unsigned int v9; // edx
  __int64 v10; // r13
  unsigned int v11; // ebp
  __int64 i; // rdi
  DWORD v13; // eax
  __int64 v14; // rcx
  const char *v15; // rdx
  __int128 pvSaveToPara; // [rsp+30h] [rbp-48h] BYREF

  pvSaveToPara = 0;
  TraceLogHelper("IkeEncodeCertChainPkcs7", 1);
  v4 = CertOpenStore((LPCSTR)2, 0, 0, 1u, 0);
  if ( !v4 )
  {
    LastError = GetLastError();
    v7 = WfpReportSysErrorAsWinError(v6, "CertOpenStore", LastError, 1);
    goto LABEL_20;
  }
  v8 = 0;
LABEL_4:
  v9 = *(_DWORD *)(a1 + 12);
  if ( (unsigned int)v8 >= v9 )
  {
    if ( CertSaveStore(v4, 0x10001u, 2u, 2u, &pvSaveToPara, 0) )
    {
      v7 = WfpMemAlloc((unsigned int)pvSaveToPara, 0);
      if ( v7 )
        goto LABEL_19;
      if ( CertSaveStore(v4, 0x10001u, 2u, 2u, &pvSaveToPara, 0) )
      {
        *(_QWORD *)(a2 + 8) = *((_QWORD *)&pvSaveToPara + 1);
        *(_DWORD *)a2 = pvSaveToPara;
        goto LABEL_19;
      }
    }
    v13 = GetLastError();
    v15 = "CertSaveStore";
  }
  else
  {
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v8);
    v11 = *(_DWORD *)(v10 + 12) - 1;
    if ( (_DWORD)v8 != v9 - 1 )
      v11 = *(_DWORD *)(v10 + 12);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v11 )
      {
        v8 = (unsigned int)(v8 + 1);
        goto LABEL_4;
      }
      if ( !CertAddCertificateContextToStore(
              v4,
              *(PCCERT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v10 + 16) + 8 * i) + 8LL),
              3u,
              0) )
        break;
    }
    v13 = GetLastError();
    v15 = "CertAddCertificateContextToStore";
  }
  v7 = WfpReportSysErrorAsWinError(v14, v15, v13, 1);
LABEL_19:
  CertCloseStore(v4, 0);
LABEL_20:
  if ( v7 )
    WfpMemFree((char *)&pvSaveToPara + 8);
  TraceLogHelper("IkeEncodeCertChainPkcs7", 0);
  return IkeReturnError(v7, "IkeEncodeCertChainPkcs7");
}

```

## disassembly

```asm
0x18008e4ac  mov     [rsp+arg_10], rbx
0x18008e4b1  mov     [rsp+arg_18], rbp
0x18008e4b6  push    rsi
0x18008e4b7  push    rdi
0x18008e4b8  push    r13
0x18008e4ba  push    r14
0x18008e4bc  push    r15
0x18008e4be  sub     rsp, 50h
0x18008e4c2  mov     rax, cs:__security_cookie
0x18008e4c9  xor     rax, rsp
0x18008e4cc  mov     [rsp+78h+var_38], rax
0x18008e4d1  mov     r14, rdx
0x18008e4d4  mov     r15, rcx
0x18008e4d7  xorps   xmm0, xmm0
0x18008e4da  lea     rcx, aIkeencodecertc_0; "IkeEncodeCertChainPkcs7"
0x18008e4e1  mov     edi, 1
0x18008e4e6  mov     edx, edi
0x18008e4e8  movups  [rsp+78h+pvSaveToPara], xmm0
0x18008e4ed  call    TraceLogHelper
0x18008e4f2  mov     r9d, edi; dwFlags
0x18008e4f5  mov     [rsp+78h+pvPara], 0; pvPara
0x18008e4fe  xor     r8d, r8d; hCryptProv
0x18008e501  lea     ecx, [rdi+1]; lpszStoreProvider
0x18008e504  xor     edx, edx; dwEncodingType
0x18008e506  call    cs:__imp_CertOpenStore
0x18008e50c  mov     rsi, rax
0x18008e50f  test    rax, rax
0x18008e512  jnz     short loc_18008E534
0x18008e514  call    cs:__imp_GetLastError
0x18008e51a  mov     r9d, edi
0x18008e51d  lea     rdx, aCertopenstore_0; "CertOpenStore"
0x18008e524  mov     r8d, eax
0x18008e527  call    WfpReportSysErrorAsWinError
0x18008e52c  mov     rbx, rax
0x18008e52f  jmp     loc_18008E647
0x18008e534  xor     ebx, ebx
0x18008e536  mov     edx, [r15+0Ch]
0x18008e53a  cmp     ebx, edx
0x18008e53c  jnb     short loc_18008E5AB
0x18008e53e  mov     rax, [r15+10h]
0x18008e542  mov     r13, [rax+rbx*8]
0x18008e546  lea     eax, [rdx-1]
0x18008e549  cmp     ebx, eax
0x18008e54b  mov     ecx, [r13+0Ch]
0x18008e54f  lea     ebp, [rcx-1]
0x18008e552  cmovnz  ebp, ecx
0x18008e555  xor     edi, edi
0x18008e557  cmp     edi, ebp
0x18008e559  jnb     short loc_18008E57F
0x18008e55b  mov     rax, [r13+10h]
0x18008e55f  xor     r9d, r9d; ppStoreContext
0x18008e562  mov     rcx, rsi; hCertStore
0x18008e565  mov     rdx, [rax+rdi*8]
0x18008e569  lea     r8d, [r9+3]; dwAddDisposition
0x18008e56d  mov     rdx, [rdx+8]; pCertContext
0x18008e571  call    cs:__imp_CertAddCertificateContextToStore
0x18008e577  test    eax, eax
0x18008e579  jz      short loc_18008E588
0x18008e57b  inc     edi
0x18008e57d  jmp     short loc_18008E557
0x18008e57f  mov     edi, 1
0x18008e584  add     ebx, edi
0x18008e586  jmp     short loc_18008E536
0x18008e588  call    cs:__imp_GetLastError
0x18008e58e  mov     r9d, 1
0x18008e594  lea     rdx, aCertaddcertifi_0; "CertAddCertificateContextToStore"
0x18008e59b  mov     r8d, eax
0x18008e59e  call    WfpReportSysErrorAsWinError
0x18008e5a3  mov     rbx, rax
0x18008e5a6  jmp     loc_18008E63C
0x18008e5ab  mov     ebp, 2
0x18008e5b0  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18008e5b8  lea     rax, [rsp+78h+pvSaveToPara]
0x18008e5bd  mov     r15d, 10001h
0x18008e5c3  mov     r9d, ebp; dwSaveTo
0x18008e5c6  mov     [rsp+78h+pvPara], rax; pvSaveToPara
0x18008e5cb  mov     r8d, ebp; dwSaveAs
0x18008e5ce  mov     edx, r15d; dwEncodingType
0x18008e5d1  mov     rcx, rsi; hCertStore
0x18008e5d4  call    cs:__imp_CertSaveStore
0x18008e5da  test    eax, eax
0x18008e5dc  jnz     short loc_18008E5F0
0x18008e5de  call    cs:__imp_GetLastError
0x18008e5e4  mov     r9d, edi
0x18008e5e7  lea     rdx, aCertsavestore_0; "CertSaveStore"
0x18008e5ee  jmp     short loc_18008E59B
0x18008e5f0  mov     ecx, dword ptr [rsp+78h+pvSaveToPara]; dwBytes
0x18008e5f4  lea     r8, [rsp+78h+pvSaveToPara+8]
0x18008e5f9  xor     edx, edx; dwFlags
0x18008e5fb  call    WfpMemAlloc
0x18008e600  mov     rbx, rax
0x18008e603  test    rax, rax
0x18008e606  jnz     short loc_18008E63C
0x18008e608  mov     [rsp+78h+dwFlags], eax; dwFlags
0x18008e60c  mov     r9d, ebp; dwSaveTo
0x18008e60f  lea     rax, [rsp+78h+pvSaveToPara]
0x18008e614  mov     r8d, ebp; dwSaveAs
0x18008e617  mov     edx, r15d; dwEncodingType
0x18008e61a  mov     [rsp+78h+pvPara], rax; pvSaveToPara
0x18008e61f  mov     rcx, rsi; hCertStore
0x18008e622  call    cs:__imp_CertSaveStore
0x18008e628  test    eax, eax
0x18008e62a  jz      short loc_18008E5DE
0x18008e62c  mov     rax, qword ptr [rsp+78h+pvSaveToPara+8]
0x18008e631  mov     [r14+8], rax
0x18008e635  mov     eax, dword ptr [rsp+78h+pvSaveToPara]
0x18008e639  mov     [r14], eax
0x18008e63c  xor     edx, edx; dwFlags
0x18008e63e  mov     rcx, rsi; hCertStore
0x18008e641  call    cs:__imp_CertCloseStore
0x18008e647  test    rbx, rbx
0x18008e64a  jz      short loc_18008E656
0x18008e64c  lea     rcx, [rsp+78h+pvSaveToPara+8]
0x18008e651  call    WfpMemFree
0x18008e656  xor     edx, edx
0x18008e658  lea     rcx, aIkeencodecertc_0; "IkeEncodeCertChainPkcs7"
0x18008e65f  call    TraceLogHelper
0x18008e664  lea     rdx, aIkeencodecertc_0; "IkeEncodeCertChainPkcs7"
0x18008e66b  mov     rcx, rbx
0x18008e66e  call    IkeReturnError
0x18008e673  mov     rcx, [rsp+78h+var_38]
0x18008e678  xor     rcx, rsp; StackCookie
0x18008e67b  call    __security_check_cookie
0x18008e680  lea     r11, [rsp+78h+var_28]
0x18008e685  mov     rbx, [r11+40h]
0x18008e689  mov     rbp, [r11+48h]
0x18008e68d  mov     rsp, r11
0x18008e690  pop     r15
0x18008e692  pop     r14
0x18008e694  pop     r13
0x18008e696  pop     rdi
0x18008e697  pop     rsi
0x18008e698  retn
```
