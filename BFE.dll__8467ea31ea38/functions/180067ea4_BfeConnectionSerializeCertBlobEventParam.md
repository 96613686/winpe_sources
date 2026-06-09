# BfeConnectionSerializeCertBlobEventParam

- ea: `0x180067ea4`
- end: `0x180067fa5`
- name: `BfeConnectionSerializeCertBlobEventParam`
- size: `257`
- prototype: `int __fastcall(__int64, __int64, WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001d118`

## callees

- `0x180018b74`
- `0x1800490bc`
- `0x180058b30`
- `0x180067aac`
- `0x180067ea4`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180067f46`
- `CRYPT32!CertCreateCertificateContext` at `0x180067f46`
- `CRYPT32!CertFreeCertificateContext` at `0x180067f67`
- `CRYPT32!CertFreeCertificateContext` at `0x180067f67`
- `CRYPT32!CertNameToStrW` at `0x180067f01`
- `CRYPT32!CertNameToStrW` at `0x180067f01`

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
      v3 = (WCHAR *)&qword_1800B3918;
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
0x180067ea4  push    rbx
0x180067ea6  push    rbp
0x180067ea7  push    rsi
0x180067ea8  push    rdi
0x180067ea9  push    r14
0x180067eab  sub     rsp, 50h
0x180067eaf  mov     rax, cs:__security_cookie
0x180067eb6  xor     rax, rsp
0x180067eb9  mov     [rsp+78h+var_30], rax
0x180067ebe  mov     eax, [rdx]
0x180067ec0  xor     ebp, ebp
0x180067ec2  mov     [rsp+78h+pName.cbData], eax
0x180067ec6  mov     rbx, r8
0x180067ec9  mov     rax, [rdx+8]
0x180067ecd  mov     r9, r8; psz
0x180067ed0  mov     [r8], bp
0x180067ed4  mov     rsi, rdx
0x180067ed7  lea     r8d, [rbp+1]; dwStrType
0x180067edb  mov     dword ptr [rsp+78h+pName+4], ebp
0x180067edf  mov     r14, rcx
0x180067ee2  mov     [rsp+78h+pName.pbData], rax
0x180067ee7  mov     ecx, r8d; dwCertEncodingType
0x180067eea  mov     [rsp+78h+var_44], ebp
0x180067eee  lea     rdx, [rsp+78h+pName]; pName
0x180067ef3  mov     [rsp+78h+var_48], ebp
0x180067ef7  mov     edi, ebp
0x180067ef9  mov     [rsp+78h+csz], 1F4h; csz
0x180067f01  call    cs:__imp_CertNameToStrW
0x180067f07  mov     ecx, eax
0x180067f09  lea     r8, [rsp+78h+var_44]
0x180067f0e  lea     edx, [rbp+2]
0x180067f11  call    WfpUINT32Multiply
0x180067f16  test    rax, rax
0x180067f19  jnz     short loc_180067F25
0x180067f1b  mov     edi, [rsp+78h+var_44]
0x180067f1f  mov     [rsp+78h+var_48], edi
0x180067f23  jmp     short loc_180067F34
0x180067f25  lea     rdx, aBfeconnectionc_1; "BfeConnectionCertNameToStr"
0x180067f2c  mov     rcx, rax
0x180067f2f  call    WfpReportError
0x180067f34  cmp     [rbx], bp
0x180067f37  jnz     short loc_180067F82
0x180067f39  mov     r8d, [rsi+28h]; cbCertEncoded
0x180067f3d  mov     ecx, 10001h; dwCertEncodingType
0x180067f42  mov     rdx, [rsi+30h]; pbCertEncoded
0x180067f46  call    cs:__imp_CertCreateCertificateContext
0x180067f4c  mov     rsi, rax
0x180067f4f  test    rax, rax
0x180067f52  jz      short loc_180067F71
0x180067f54  lea     r8, [rsp+78h+var_48]
0x180067f59  mov     rdx, rbx; pszNameString
0x180067f5c  mov     rcx, rax; pCertContext
0x180067f5f  call    BfeConnectionGetDisplayNameFromCert
0x180067f64  mov     rcx, rsi; pCertContext
0x180067f67  call    cs:__imp_CertFreeCertificateContext
0x180067f6d  mov     edi, [rsp+78h+var_48]
0x180067f71  cmp     [rbx], bp
0x180067f74  jnz     short loc_180067F82
0x180067f76  lea     rbx, qword_1800B3918
0x180067f7d  mov     edi, 1
0x180067f82  mov     [r14], rbx
0x180067f85  mov     [r14+8], edi
0x180067f89  mov     [r14+0Ch], ebp
0x180067f8d  mov     rcx, [rsp+78h+var_30]
0x180067f92  xor     rcx, rsp; StackCookie
0x180067f95  call    __security_check_cookie
0x180067f9a  add     rsp, 50h
0x180067f9e  pop     r14
0x180067fa0  pop     rdi
0x180067fa1  pop     rsi
0x180067fa2  pop     rbp
0x180067fa3  pop     rbx
0x180067fa4  retn
```
