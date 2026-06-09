# KdcCheckLegacyKeyUsage(_CERT_CONTEXT const *)

- ea: `0x180050bf8`
- end: `0x180050e6f`
- name: `?KdcCheckLegacyKeyUsage@@YAHPEBU_CERT_CONTEXT@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800509ac`

## callees

- `0x18000a814`
- `0x18000a84c`
- `0x18000a900`
- `0x1800101ec`
- `0x180050bf8`
- `0x18005a060`
- `0x180099c34`
- `0x180099c4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050d2f`
- `CRYPT32!CertFindExtension` at `0x180050c5e`
- `CRYPT32!CertFindExtension` at `0x180050dad`
- `CRYPT32!CertFindExtension` at `0x180050c5e`
- `CRYPT32!CertFindExtension` at `0x180050dad`
- `CRYPT32!CryptDecodeObject` at `0x180050ca1`
- `CRYPT32!CryptDecodeObject` at `0x180050d0c`
- `CRYPT32!CryptDecodeObject` at `0x180050dee`
- `CRYPT32!CryptDecodeObject` at `0x180050e34`
- `CRYPT32!CryptDecodeObject` at `0x180050ca1`
- `CRYPT32!CryptDecodeObject` at `0x180050d0c`
- `CRYPT32!CryptDecodeObject` at `0x180050dee`
- `CRYPT32!CryptDecodeObject` at `0x180050e34`

## pseudocode

```c
__int64 __fastcall KdcCheckLegacyKeyUsage(const struct _CERT_CONTEXT *a1)
{
  __int64 v2; // rax
  PCERT_INFO pCertInfo; // rdx
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v5; // rbx
  DWORD LastError; // eax
  __int64 v7; // rdx
  _QWORD *pvStructInfo; // rax
  _QWORD *v10; // rdi
  __int64 i; // rbx
  PCERT_EXTENSION v12; // rbx
  const wchar_t **v13; // rax
  char v14[16]; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-20h] BYREF
  DWORD pcbStructInfo; // [rsp+A0h] [rbp+30h] BYREF
  _QWORD *v17; // [rsp+A8h] [rbp+38h] BYREF
  const wchar_t **v18; // [rsp+B0h] [rbp+40h] BYREF

  pcbStructInfo = 0;
  v18 = 0;
  v17 = 0;
  v2 = lambda_14fd01bcd5a8d1a80ee3c701b30d75de_::_lambda_14fd01bcd5a8d1a80ee3c701b30d75de_(v14, &v17, &v18);
  wil::scope_exit__lambda_14fd01bcd5a8d1a80ee3c701b30d75de___(v15, v2);
  pCertInfo = a1->pCertInfo;
  if ( !pCertInfo )
    goto LABEL_13;
  Extension = CertFindExtension("2.5.29.37", pCertInfo->cExtension, pCertInfo->rgExtension);
  v5 = Extension;
  if ( Extension )
  {
    if ( !CryptDecodeObject(1u, (LPCSTR)0x24, Extension->Value.pbData, Extension->Value.cbData, 0, 0, &pcbStructInfo) )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      LastError = GetLastError();
      v7 = 21;
      goto LABEL_12;
    }
    pvStructInfo = MIDL_user_allocate(pcbStructInfo);
    v17 = pvStructInfo;
    if ( !pvStructInfo )
    {
LABEL_13:
      wil::details::lambda_call__lambda_acb9db33a011330cd07a1f9499712094___::_lambda_call__lambda_acb9db33a011330cd07a1f9499712094___(v15);
      return 0;
    }
    if ( !CryptDecodeObject(1u, (LPCSTR)0x24, v5->Value.pbData, v5->Value.cbData, 0, pvStructInfo, &pcbStructInfo) )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      LastError = GetLastError();
      v7 = 22;
LABEL_12:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, LastError);
      goto LABEL_13;
    }
    v10 = v17;
    for ( i = 0; (unsigned int)i < *(_DWORD *)v10; i = (unsigned int)(i + 1) )
    {
      if ( !strcmp_0("1.3.6.1.4.1.311.20.2.2", *(const char **)(v10[1] + 8 * i)) )
        goto LABEL_23;
    }
  }
  v12 = CertFindExtension("1.3.6.1.4.1.311.20.2", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
  if ( !v12 )
    goto LABEL_13;
  pcbStructInfo = 0;
  if ( !CryptDecodeObject(1u, (LPCSTR)0x18, v12->Value.pbData, v12->Value.cbData, 0, 0, &pcbStructInfo) )
    goto LABEL_13;
  v13 = (const wchar_t **)MIDL_user_allocate(pcbStructInfo);
  v18 = v13;
  if ( !v13
    || !CryptDecodeObject(1u, (LPCSTR)0x18, v12->Value.pbData, v12->Value.cbData, 0, v13, &pcbStructInfo)
    || wcscmp_0(v18[2], L"DomainController") )
  {
    goto LABEL_13;
  }
LABEL_23:
  wil::details::lambda_call__lambda_acb9db33a011330cd07a1f9499712094___::_lambda_call__lambda_acb9db33a011330cd07a1f9499712094___(v15);
  return 1;
}

```

## disassembly

```asm
0x180050bf8  push    rbp
0x180050bfa  push    rbx
0x180050bfb  push    rsi
0x180050bfc  push    rdi
0x180050bfd  push    r15
0x180050bff  mov     rbp, rsp
0x180050c02  sub     rsp, 70h
0x180050c06  mov     rsi, rcx
0x180050c09  mov     [rbp+arg_0], 0
0x180050c10  lea     rcx, [rbp+var_30]
0x180050c14  mov     [rbp+arg_10], 0
0x180050c1c  lea     r8, [rbp+arg_10]
0x180050c20  mov     [rbp+arg_8], 0
0x180050c28  lea     rdx, [rbp+arg_8]
0x180050c2c  call    _lambda_14fd01bcd5a8d1a80ee3c701b30d75de____lambda_14fd01bcd5a8d1a80ee3c701b30d75de_
0x180050c31  mov     rdx, rax
0x180050c34  lea     rcx, [rbp+var_20]
0x180050c38  call    wil__scope_exit__lambda_14fd01bcd5a8d1a80ee3c701b30d75de___
0x180050c3d  mov     rdx, [rsi+18h]
0x180050c41  test    rdx, rdx
0x180050c44  jz      loc_180050D54
0x180050c4a  mov     r8, [rdx+0C8h]; rgExtensions
0x180050c51  lea     rcx, pszObjId; "2.5.29.37"
0x180050c58  mov     edx, [rdx+0C0h]; cExtensions
0x180050c5e  call    cs:__imp_CertFindExtension
0x180050c64  mov     rbx, rax
0x180050c67  mov     r15d, 1
0x180050c6d  test    rax, rax
0x180050c70  jz      loc_180050D95
0x180050c76  mov     r9d, [rbx+10h]; cbEncoded
0x180050c7a  lea     rax, [rbp+arg_0]
0x180050c7e  mov     r8, [rbx+18h]; pbEncoded
0x180050c82  lea     edi, [r15+23h]
0x180050c86  mov     [rsp+70h+pcbStructInfo], rax; pcbStructInfo
0x180050c8b  mov     edx, edi; lpszStructType
0x180050c8d  mov     [rsp+70h+pvStructInfo], 0; pvStructInfo
0x180050c96  mov     ecx, r15d; dwCertEncodingType
0x180050c99  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180050ca1  call    cs:__imp_CryptDecodeObject
0x180050ca7  test    eax, eax
0x180050ca9  jnz     short loc_180050CD7
0x180050cab  mov     rcx, cs:WPP_GLOBAL_Control
0x180050cb2  lea     rax, WPP_GLOBAL_Control
0x180050cb9  cmp     rcx, rax
0x180050cbc  jz      loc_180050D54
0x180050cc2  test    [rcx+1Ch], r15b
0x180050cc6  jz      loc_180050D54
0x180050ccc  call    cs:__imp_GetLastError
0x180050cd2  lea     edx, [rdi-0Fh]
0x180050cd5  jmp     short loc_180050D3A
0x180050cd7  mov     ecx, [rbp+arg_0]; size
0x180050cda  call    MIDL_user_allocate
0x180050cdf  mov     [rbp+arg_8], rax
0x180050ce3  test    rax, rax
0x180050ce6  jz      short loc_180050D54
0x180050ce8  mov     r9d, [rbx+10h]; cbEncoded
0x180050cec  lea     rcx, [rbp+arg_0]
0x180050cf0  mov     r8, [rbx+18h]; pbEncoded
0x180050cf4  mov     rdx, rdi; lpszStructType
0x180050cf7  mov     [rsp+70h+pcbStructInfo], rcx; pcbStructInfo
0x180050cfc  mov     ecx, r15d; dwCertEncodingType
0x180050cff  mov     [rsp+70h+pvStructInfo], rax; pvStructInfo
0x180050d04  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180050d0c  call    cs:__imp_CryptDecodeObject
0x180050d12  test    eax, eax
0x180050d14  jnz     short loc_180050D6A
0x180050d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180050d1d  lea     rax, WPP_GLOBAL_Control
0x180050d24  cmp     rcx, rax
0x180050d27  jz      short loc_180050D54
0x180050d29  test    [rcx+1Ch], r15b
0x180050d2d  jz      short loc_180050D54
0x180050d2f  call    cs:__imp_GetLastError
0x180050d35  mov     edx, 16h
0x180050d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050d41  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180050d48  mov     r9d, eax
0x180050d4b  mov     rcx, [rcx+10h]
0x180050d4f  call    WPP_SF_d
0x180050d54  lea     rcx, [rbp+var_20]
0x180050d58  call    wil__details__lambda_call__lambda_acb9db33a011330cd07a1f9499712094______lambda_call__lambda_acb9db33a011330cd07a1f9499712094___
0x180050d5d  xor     eax, eax
0x180050d5f  add     rsp, 70h
0x180050d63  pop     r15
0x180050d65  pop     rdi
0x180050d66  pop     rsi
0x180050d67  pop     rbx
0x180050d68  pop     rbp
0x180050d69  retn
0x180050d6a  mov     rdi, [rbp+arg_8]
0x180050d6e  xor     ebx, ebx
0x180050d70  cmp     ebx, [rdi]
0x180050d72  jnb     short loc_180050D95
0x180050d74  mov     rdx, [rdi+8]
0x180050d78  lea     rcx, a1361413112022; "1.3.6.1.4.1.311.20.2.2"
0x180050d7f  mov     rdx, [rdx+rbx*8]; Str2
0x180050d83  call    strcmp_0
0x180050d88  test    eax, eax
0x180050d8a  jz      loc_180050E5E
0x180050d90  add     ebx, r15d
0x180050d93  jmp     short loc_180050D70
0x180050d95  mov     rdx, [rsi+18h]
0x180050d99  lea     rcx, a136141311202; "1.3.6.1.4.1.311.20.2"
0x180050da0  mov     r8, [rdx+0C8h]; rgExtensions
0x180050da7  mov     edx, [rdx+0C0h]; cExtensions
0x180050dad  call    cs:__imp_CertFindExtension
0x180050db3  mov     rbx, rax
0x180050db6  test    rax, rax
0x180050db9  jz      short loc_180050D54
0x180050dbb  mov     [rbp+arg_0], 0
0x180050dc2  lea     rax, [rbp+arg_0]
0x180050dc6  mov     r9d, [rbx+10h]; cbEncoded
0x180050dca  mov     edi, 18h
0x180050dcf  mov     r8, [rbx+18h]; pbEncoded
0x180050dd3  mov     edx, edi; lpszStructType
0x180050dd5  mov     [rsp+70h+pcbStructInfo], rax; pcbStructInfo
0x180050dda  mov     ecx, r15d; dwCertEncodingType
0x180050ddd  mov     [rsp+70h+pvStructInfo], 0; pvStructInfo
0x180050de6  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180050dee  call    cs:__imp_CryptDecodeObject
0x180050df4  test    eax, eax
0x180050df6  jz      loc_180050D54
0x180050dfc  mov     ecx, [rbp+arg_0]; size
0x180050dff  call    MIDL_user_allocate
0x180050e04  mov     [rbp+arg_10], rax
0x180050e08  test    rax, rax
0x180050e0b  jz      loc_180050D54
0x180050e11  mov     r9d, [rbx+10h]; cbEncoded
0x180050e15  lea     rcx, [rbp+arg_0]
0x180050e19  mov     r8, [rbx+18h]; pbEncoded
0x180050e1d  mov     edx, edi; lpszStructType
0x180050e1f  mov     [rsp+70h+pcbStructInfo], rcx; pcbStructInfo
0x180050e24  mov     ecx, r15d; dwCertEncodingType
0x180050e27  mov     [rsp+70h+pvStructInfo], rax; pvStructInfo
0x180050e2c  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180050e34  call    cs:__imp_CryptDecodeObject
0x180050e3a  test    eax, eax
0x180050e3c  jz      loc_180050D54
0x180050e42  mov     rcx, [rbp+arg_10]
0x180050e46  lea     rdx, aDomaincontroll; "DomainController"
0x180050e4d  mov     rcx, [rcx+10h]; String1
0x180050e51  call    wcscmp_0
0x180050e56  test    eax, eax
0x180050e58  jnz     loc_180050D54
0x180050e5e  lea     rcx, [rbp+var_20]
0x180050e62  call    wil__details__lambda_call__lambda_acb9db33a011330cd07a1f9499712094______lambda_call__lambda_acb9db33a011330cd07a1f9499712094___
0x180050e67  mov     eax, r15d
0x180050e6a  jmp     loc_180050D5F
```
