# BfeConnectionSerializeCertBlobEventParam

- ea: `0x18006a418`
- end: `0x18006a52c`
- name: `BfeConnectionSerializeCertBlobEventParam`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001df50`

## callees

- `0x1800197d0`
- `0x18004afc8`
- `0x18005aa60`
- `0x18006a000`
- `0x18006a418`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x18006a4c0`
- `CRYPT32!CertCreateCertificateContext` at `0x18006a4c0`
- `CRYPT32!CertFreeCertificateContext` at `0x18006a4e7`
- `CRYPT32!CertFreeCertificateContext` at `0x18006a4e7`
- `CRYPT32!CertNameToStrW` at `0x18006a475`
- `CRYPT32!CertNameToStrW` at `0x18006a475`

## pseudocode

```c
int __fastcall BfeConnectionSerializeCertBlobEventParam(__int64 a1, __int64 a2, WCHAR *a3)
{
  WCHAR *v3; // rbx
  BYTE *v4; // rax
  int v7; // edi
  DWORD v8; // eax
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v10; // rsi
  int v12; // [rsp+30h] [rbp-48h]
  int v13; // [rsp+34h] [rbp-44h] BYREF
  _CRYPTOAPI_BLOB pName; // [rsp+38h] [rbp-40h] BYREF

  pName.cbData = *(_DWORD *)a2;
  v3 = a3;
  v4 = *(BYTE **)(a2 + 8);
  *a3 = 0;
  *(&pName.cbData + 1) = 0;
  pName.pbData = v4;
  v13 = 0;
  v12 = 0;
  v7 = 0;
  v8 = CertNameToStrW(1u, &pName, 1u, a3, 0x1F4u);
  CertificateContext = (const CERT_CONTEXT *)WfpUINT32Multiply(v8, 2, &v13);
  if ( CertificateContext )
  {
    LODWORD(CertificateContext) = WfpReportError(CertificateContext, "BfeConnectionCertNameToStr");
  }
  else
  {
    v7 = v13;
    v12 = v13;
  }
  if ( !*v3 )
  {
    CertificateContext = CertCreateCertificateContext(0x10001u, *(const BYTE **)(a2 + 48), *(_DWORD *)(a2 + 40));
    v10 = CertificateContext;
    if ( CertificateContext )
    {
      BfeConnectionGetDisplayNameFromCert(CertificateContext, v3);
      LODWORD(CertificateContext) = CertFreeCertificateContext(v10);
      v7 = v12;
    }
    if ( !*v3 )
    {
      v3 = (WCHAR *)&qword_1800B6990;
      v7 = 1;
    }
  }
  *(_QWORD *)a1 = v3;
  *(_DWORD *)(a1 + 8) = v7;
  *(_DWORD *)(a1 + 12) = 0;
  return (int)CertificateContext;
}

```

## disassembly

```asm
0x18006a418  push    rbx
0x18006a41a  push    rbp
0x18006a41b  push    rsi
0x18006a41c  push    rdi
0x18006a41d  push    r14
0x18006a41f  sub     rsp, 50h
0x18006a423  mov     rax, cs:__security_cookie
0x18006a42a  xor     rax, rsp
0x18006a42d  mov     [rsp+78h+var_30], rax
0x18006a432  mov     eax, [rdx]
0x18006a434  xor     ebp, ebp
0x18006a436  mov     [rsp+78h+pName.cbData], eax
0x18006a43a  mov     rbx, r8
0x18006a43d  mov     rax, [rdx+8]
0x18006a441  mov     r9, r8; psz
0x18006a444  mov     [r8], bp
0x18006a448  mov     rsi, rdx
0x18006a44b  lea     r8d, [rbp+1]; dwStrType
0x18006a44f  mov     dword ptr [rsp+78h+pName+4], ebp
0x18006a453  mov     r14, rcx
0x18006a456  mov     [rsp+78h+pName.pbData], rax
0x18006a45b  mov     ecx, r8d; dwCertEncodingType
0x18006a45e  mov     [rsp+78h+var_44], ebp
0x18006a462  lea     rdx, [rsp+78h+pName]; pName
0x18006a467  mov     [rsp+78h+var_48], ebp
0x18006a46b  mov     edi, ebp
0x18006a46d  mov     [rsp+78h+csz], 1F4h; csz
0x18006a475  call    cs:__imp_CertNameToStrW
0x18006a47c  nop     dword ptr [rax+rax+00h]
0x18006a481  mov     ecx, eax
0x18006a483  lea     r8, [rsp+78h+var_44]
0x18006a488  lea     edx, [rbp+2]
0x18006a48b  call    WfpUINT32Multiply
0x18006a490  test    rax, rax
0x18006a493  jnz     short loc_18006A49F
0x18006a495  mov     edi, [rsp+78h+var_44]
0x18006a499  mov     [rsp+78h+var_48], edi
0x18006a49d  jmp     short loc_18006A4AE
0x18006a49f  lea     rdx, aBfeconnectionc_1; "BfeConnectionCertNameToStr"
0x18006a4a6  mov     rcx, rax
0x18006a4a9  call    WfpReportError
0x18006a4ae  cmp     [rbx], bp
0x18006a4b1  jnz     short loc_18006A508
0x18006a4b3  mov     r8d, [rsi+28h]; cbCertEncoded
0x18006a4b7  mov     ecx, 10001h; dwCertEncodingType
0x18006a4bc  mov     rdx, [rsi+30h]; pbCertEncoded
0x18006a4c0  call    cs:__imp_CertCreateCertificateContext
0x18006a4c7  nop     dword ptr [rax+rax+00h]
0x18006a4cc  mov     rsi, rax
0x18006a4cf  test    rax, rax
0x18006a4d2  jz      short loc_18006A4F7
0x18006a4d4  lea     r8, [rsp+78h+var_48]
0x18006a4d9  mov     rdx, rbx; pszNameString
0x18006a4dc  mov     rcx, rax; pCertContext
0x18006a4df  call    BfeConnectionGetDisplayNameFromCert
0x18006a4e4  mov     rcx, rsi; pCertContext
0x18006a4e7  call    cs:__imp_CertFreeCertificateContext
0x18006a4ee  nop     dword ptr [rax+rax+00h]
0x18006a4f3  mov     edi, [rsp+78h+var_48]
0x18006a4f7  cmp     [rbx], bp
0x18006a4fa  jnz     short loc_18006A508
0x18006a4fc  lea     rbx, qword_1800B6990
0x18006a503  mov     edi, 1
0x18006a508  mov     [r14], rbx
0x18006a50b  mov     [r14+8], edi
0x18006a50f  mov     [r14+0Ch], ebp
0x18006a513  mov     rcx, [rsp+78h+var_30]
0x18006a518  xor     rcx, rsp; StackCookie
0x18006a51b  call    __security_check_cookie
0x18006a520  add     rsp, 50h
0x18006a524  pop     r14
0x18006a526  pop     rdi
0x18006a527  pop     rsi
0x18006a528  pop     rbp
0x18006a529  pop     rbx
0x18006a52a  retn
```
