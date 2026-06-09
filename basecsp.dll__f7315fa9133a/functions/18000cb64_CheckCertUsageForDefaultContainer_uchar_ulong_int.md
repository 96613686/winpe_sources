# CheckCertUsageForDefaultContainer(uchar *,ulong,int *)

- ea: `0x18000cb64`
- end: `0x18000cc74`
- name: `?CheckCertUsageForDefaultContainer@@YAKPEAEKPEAH@Z`
- size: `272`
- prototype: `unsigned int __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012fa0`

## callees

- `0x18000cb64`
- `0x18000de80`
- `0x180019430`
- `0x18002cf5e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cba1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cba1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbff`
- `CRYPT32!CertCreateCertificateContext` at `0x18000cb93`
- `CRYPT32!CertCreateCertificateContext` at `0x18000cb93`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000cbbb`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000cbf5`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000cbbb`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000cbf5`
- `CRYPT32!CertFreeCertificateContext` at `0x18000cc59`
- `CRYPT32!CertFreeCertificateContext` at `0x18000cc59`

## pseudocode

```c
__int64 __fastcall CheckCertUsageForDefaultContainer(BYTE *pbCertEncoded, DWORD cbCertEncoded, int *a3)
{
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v5; // rsi
  DWORD LastError; // ebx
  struct _CTL_USAGE *v7; // rax
  struct _CTL_USAGE *v8; // rdi
  unsigned int v9; // eax
  const char *v10; // rbp
  DWORD pcbUsage; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  pcbUsage = 0;
  CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
  v5 = CertificateContext;
  if ( CertificateContext )
  {
    if ( CertGetEnhancedKeyUsage(CertificateContext, 0, 0, &pcbUsage) )
    {
      v7 = (struct _CTL_USAGE *)MIDL_user_allocate(pcbUsage);
      v8 = v7;
      if ( v7 )
      {
        if ( CertGetEnhancedKeyUsage(v5, 0, v7, &pcbUsage) )
        {
          LastError = 0;
          while ( v8->cUsageIdentifier )
          {
            v9 = v8->cUsageIdentifier - 1;
            v8->cUsageIdentifier = v9;
            v10 = v8->rgpszUsageIdentifier[v9];
            if ( !strcmp_0("1.3.6.1.4.1.311.20.2.2", v10) || !strcmp_0("1.3.6.1.4.1.311.20.2.1", v10) )
              *a3 = 1;
          }
        }
        else
        {
          LastError = GetLastError();
        }
        CspFreeH(v8);
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    CertFreeCertificateContext(v5);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18000cb64  mov     [rsp+arg_0], rbx
0x18000cb69  mov     [rsp+arg_8], rbp
0x18000cb6e  push    rsi
0x18000cb6f  push    rdi
0x18000cb70  push    r14
0x18000cb72  sub     rsp, 20h
0x18000cb76  mov     r14, r8
0x18000cb79  mov     dword ptr [r8], 0
0x18000cb80  mov     r8d, edx; cbCertEncoded
0x18000cb83  mov     [rsp+38h+pcbUsage], 0
0x18000cb8b  mov     rdx, rcx; pbCertEncoded
0x18000cb8e  mov     ecx, 10001h; dwCertEncodingType
0x18000cb93  call    cs:__imp_CertCreateCertificateContext
0x18000cb99  mov     rsi, rax
0x18000cb9c  test    rax, rax
0x18000cb9f  jnz     short loc_18000CBAE
0x18000cba1  call    cs:__imp_GetLastError
0x18000cba7  mov     ebx, eax
0x18000cba9  jmp     loc_18000CC5F
0x18000cbae  lea     r9, [rsp+38h+pcbUsage]; pcbUsage
0x18000cbb3  xor     r8d, r8d; pUsage
0x18000cbb6  xor     edx, edx; dwFlags
0x18000cbb8  mov     rcx, rsi; pCertContext
0x18000cbbb  call    cs:__imp_CertGetEnhancedKeyUsage
0x18000cbc1  test    eax, eax
0x18000cbc3  jnz     short loc_18000CBD2
0x18000cbc5  call    cs:__imp_GetLastError
0x18000cbcb  mov     ebx, eax
0x18000cbcd  jmp     loc_18000CC56
0x18000cbd2  mov     ecx, [rsp+38h+pcbUsage]; size
0x18000cbd6  call    MIDL_user_allocate
0x18000cbdb  mov     rdi, rax
0x18000cbde  test    rax, rax
0x18000cbe1  jnz     short loc_18000CBE8
0x18000cbe3  lea     ebx, [rax+8]
0x18000cbe6  jmp     short loc_18000CC56
0x18000cbe8  lea     r9, [rsp+38h+pcbUsage]; pcbUsage
0x18000cbed  mov     r8, rdi; pUsage
0x18000cbf0  xor     edx, edx; dwFlags
0x18000cbf2  mov     rcx, rsi; pCertContext
0x18000cbf5  call    cs:__imp_CertGetEnhancedKeyUsage
0x18000cbfb  test    eax, eax
0x18000cbfd  jnz     short loc_18000CC09
0x18000cbff  call    cs:__imp_GetLastError
0x18000cc05  mov     ebx, eax
0x18000cc07  jmp     short loc_18000CC4E
0x18000cc09  xor     ebx, ebx
0x18000cc0b  jmp     short loc_18000CC48
0x18000cc0d  dec     eax
0x18000cc0f  mov     ecx, eax
0x18000cc11  mov     [rdi], eax
0x18000cc13  mov     rax, [rdi+8]
0x18000cc17  mov     rbp, [rax+rcx*8]
0x18000cc1b  lea     rcx, Str1; "1.3.6.1.4.1.311.20.2.2"
0x18000cc22  mov     rdx, rbp; Str2
0x18000cc25  call    strcmp_0
0x18000cc2a  test    eax, eax
0x18000cc2c  jz      short loc_18000CC41
0x18000cc2e  mov     rdx, rbp; Str2
0x18000cc31  lea     rcx, a1361413112021; "1.3.6.1.4.1.311.20.2.1"
0x18000cc38  call    strcmp_0
0x18000cc3d  test    eax, eax
0x18000cc3f  jnz     short loc_18000CC48
0x18000cc41  mov     dword ptr [r14], 1
0x18000cc48  mov     eax, [rdi]
0x18000cc4a  test    eax, eax
0x18000cc4c  jnz     short loc_18000CC0D
0x18000cc4e  mov     rcx, rdi
0x18000cc51  call    CspFreeH
0x18000cc56  mov     rcx, rsi; pCertContext
0x18000cc59  call    cs:__imp_CertFreeCertificateContext
0x18000cc5f  mov     rbp, [rsp+38h+arg_8]
0x18000cc64  mov     eax, ebx
0x18000cc66  mov     rbx, [rsp+38h+arg_0]
0x18000cc6b  add     rsp, 20h
0x18000cc6f  pop     r14
0x18000cc71  pop     rdi
0x18000cc72  pop     rsi
0x18000cc73  retn
```
