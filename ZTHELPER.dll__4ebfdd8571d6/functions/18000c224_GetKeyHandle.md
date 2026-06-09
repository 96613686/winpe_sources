# GetKeyHandle

- ea: `0x18000c224`
- end: `0x18000c373`
- name: `GetKeyHandle`
- size: `335`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, NCRYPT_KEY_HANDLE *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c8a8`
- `0x18000da90`

## callees

- `0x1800014b0`
- `0x18000c224`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c284`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000c27a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000c2b2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000c27a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000c2b2`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000c2c7`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000c2c7`
- `ncrypt!NCryptFreeObject` at `0x18000c31a`
- `ncrypt!NCryptFreeObject` at `0x18000c329`
- `ncrypt!NCryptFreeObject` at `0x18000c31a`
- `ncrypt!NCryptFreeObject` at `0x18000c329`
- `ncrypt!NCryptOpenKey` at `0x18000c2e9`
- `ncrypt!NCryptOpenKey` at `0x18000c2e9`

## pseudocode

```c
__int64 __fastcall GetKeyHandle(PCCERT_CONTEXT pCertContext, NCRYPT_KEY_HANDLE *a2)
{
  LPCWSTR *v2; // rdi
  DWORD LastError; // ebx
  LPCWSTR *v6; // rax
  DWORD pcbData; // [rsp+30h] [rbp-20h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-18h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+40h] [rbp-10h] BYREF

  v2 = 0;
  pcbData = 0;
  phProvider = 0;
  phKey = 0;
  if ( a2 )
    *a2 = 0;
  if ( !pCertContext )
  {
    LastError = 87;
    goto LABEL_14;
  }
  if ( !CertGetCertificateContextProperty(pCertContext, 2u, 0, &pcbData) )
    goto LABEL_6;
  v6 = (LPCWSTR *)Dns_Allocate(pcbData);
  v2 = v6;
  if ( v6 )
  {
    if ( !CertGetCertificateContextProperty(pCertContext, 2u, v6, &pcbData) )
    {
LABEL_6:
      LastError = GetLastError();
      goto LABEL_14;
    }
    LastError = NCryptOpenStorageProvider(&phProvider, v2[1], 0);
    if ( !LastError )
    {
      LastError = NCryptOpenKey(phProvider, &phKey, *v2, 0, 0x60u);
      if ( !LastError )
      {
        if ( a2 )
        {
          *a2 = phKey;
          phKey = 0;
        }
      }
    }
  }
  else
  {
    LastError = 14;
  }
LABEL_14:
  Dns_Free(v2);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( LastError && (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 53, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000c224  mov     [rsp-18h+arg_10], rbx
0x18000c229  push    rbp
0x18000c22a  push    rsi
0x18000c22b  push    rdi
0x18000c22c  mov     rbp, rsp
0x18000c22f  sub     rsp, 50h
0x18000c233  mov     rax, cs:__security_cookie
0x18000c23a  xor     rax, rsp
0x18000c23d  mov     [rbp+var_8], rax
0x18000c241  xor     edi, edi
0x18000c243  mov     [rbp+pcbData], 0
0x18000c24a  mov     [rbp+phProvider], rdi
0x18000c24e  mov     rsi, rdx
0x18000c251  mov     [rbp+phKey], rdi
0x18000c255  mov     rbx, rcx
0x18000c258  test    rdx, rdx
0x18000c25b  jz      short loc_18000C260
0x18000c25d  mov     [rdx], rdi
0x18000c260  test    rbx, rbx
0x18000c263  jnz     short loc_18000C26F
0x18000c265  mov     ebx, 57h ; 'W'
0x18000c26a  jmp     loc_18000C309
0x18000c26f  xor     r8d, r8d; pvData
0x18000c272  lea     r9, [rbp+pcbData]; pcbData
0x18000c276  lea     edx, [r8+2]; dwPropId
0x18000c27a  call    cs:__imp_CertGetCertificateContextProperty
0x18000c280  test    eax, eax
0x18000c282  jnz     short loc_18000C28E
0x18000c284  call    cs:__imp_GetLastError
0x18000c28a  mov     ebx, eax
0x18000c28c  jmp     short loc_18000C309
0x18000c28e  mov     ecx, [rbp+pcbData]
0x18000c291  call    Dns_Allocate
0x18000c296  mov     rdi, rax
0x18000c299  test    rax, rax
0x18000c29c  jnz     short loc_18000C2A3
0x18000c29e  lea     ebx, [rax+0Eh]
0x18000c2a1  jmp     short loc_18000C309
0x18000c2a3  lea     r9, [rbp+pcbData]; pcbData
0x18000c2a7  mov     r8, rdi; pvData
0x18000c2aa  mov     edx, 2; dwPropId
0x18000c2af  mov     rcx, rbx; pCertContext
0x18000c2b2  call    cs:__imp_CertGetCertificateContextProperty
0x18000c2b8  test    eax, eax
0x18000c2ba  jz      short loc_18000C284
0x18000c2bc  mov     rdx, [rdi+8]; pszProviderName
0x18000c2c0  lea     rcx, [rbp+phProvider]; phProvider
0x18000c2c4  xor     r8d, r8d; dwFlags
0x18000c2c7  call    cs:__imp_NCryptOpenStorageProvider
0x18000c2cd  mov     ebx, eax
0x18000c2cf  test    eax, eax
0x18000c2d1  jnz     short loc_18000C309
0x18000c2d3  mov     r8, [rdi]; pszKeyName
0x18000c2d6  lea     rdx, [rbp+phKey]; phKey
0x18000c2da  mov     rcx, [rbp+phProvider]; hProvider
0x18000c2de  xor     r9d, r9d; dwLegacyKeySpec
0x18000c2e1  mov     [rsp+50h+dwFlags], 60h ; '`'; dwFlags
0x18000c2e9  call    cs:__imp_NCryptOpenKey
0x18000c2ef  mov     ebx, eax
0x18000c2f1  test    eax, eax
0x18000c2f3  jnz     short loc_18000C309
0x18000c2f5  test    rsi, rsi
0x18000c2f8  jz      short loc_18000C309
0x18000c2fa  mov     rax, [rbp+phKey]
0x18000c2fe  mov     [rsi], rax
0x18000c301  mov     [rbp+phKey], 0
0x18000c309  mov     rcx, rdi; lpMem
0x18000c30c  call    Dns_Free
0x18000c311  mov     rcx, [rbp+phKey]; hObject
0x18000c315  test    rcx, rcx
0x18000c318  jz      short loc_18000C320
0x18000c31a  call    cs:__imp_NCryptFreeObject
0x18000c320  mov     rcx, [rbp+phProvider]; hObject
0x18000c324  test    rcx, rcx
0x18000c327  jz      short loc_18000C32F
0x18000c329  call    cs:__imp_NCryptFreeObject
0x18000c32f  test    ebx, ebx
0x18000c331  jz      short loc_18000C355
0x18000c333  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000c33a  jz      short loc_18000C355
0x18000c33c  mov     edx, 35h ; '5'
0x18000c341  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000c348  mov     ecx, 40Bh
0x18000c34d  mov     r9d, ebx
0x18000c350  call    WPP_SF_d
0x18000c355  mov     eax, ebx
0x18000c357  mov     rcx, [rbp+var_8]
0x18000c35b  xor     rcx, rsp; StackCookie
0x18000c35e  call    __security_check_cookie
0x18000c363  mov     rbx, [rsp+50h+arg_10]
0x18000c36b  add     rsp, 50h
0x18000c36f  pop     rdi
0x18000c370  pop     rsi
0x18000c371  pop     rbp
0x18000c372  retn
```
