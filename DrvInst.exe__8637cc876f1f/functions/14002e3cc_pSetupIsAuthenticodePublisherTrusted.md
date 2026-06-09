# pSetupIsAuthenticodePublisherTrusted

- ea: `0x14002e3cc`
- end: `0x14002e553`
- name: `pSetupIsAuthenticodePublisherTrusted`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14002ccdc`

## callees

- `0x14000a614`
- `0x14000a630`
- `0x14002e3cc`
- `0x140045f30`

## import_xrefs

- `CRYPT32!CertFindCertificateInStore` at `0x14002e4ca`
- `CRYPT32!CertFindCertificateInStore` at `0x14002e4ca`
- `CRYPT32!CertGetCertificateContextProperty` at `0x14002e435`
- `CRYPT32!CertGetCertificateContextProperty` at `0x14002e435`
- `CRYPT32!CertControlStore` at `0x14002e49b`
- `CRYPT32!CertControlStore` at `0x14002e49b`
- `CRYPT32!CertFreeCertificateContext` at `0x14002e511`
- `CRYPT32!CertFreeCertificateContext` at `0x14002e511`
- `CRYPT32!CertCloseStore` at `0x14002e526`
- `CRYPT32!CertCloseStore` at `0x14002e526`
- `CRYPT32!CertOpenStore` at `0x14002e47c`
- `CRYPT32!CertOpenStore` at `0x14002e47c`

## pseudocode

```c
__int64 __fastcall pSetupIsAuthenticodePublisherTrusted(const CERT_CONTEXT *a1, void **a2)
{
  const CERT_CONTEXT *CertificateInStore; // rsi
  unsigned int v4; // r14d
  void *v5; // rbx
  HCERTSTORE v6; // rax
  DWORD pcbData[2]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE *v9; // [rsp+48h] [rbp-80h]
  const CERT_CONTEXT *v10; // [rsp+50h] [rbp-78h]
  void **v11; // [rsp+58h] [rbp-70h]
  _BYTE v12[64]; // [rsp+60h] [rbp-68h] BYREF

  v11 = a2;
  pcbData[1] = 0;
  CertificateInStore = 0;
  v10 = 0;
  v4 = 0;
  v5 = 0;
  v9 = v12;
  pcbData[0] = 64;
  if ( CertGetCertificateContextProperty(a1, 0xFu, v12, pcbData) && pcbData[0] >= 0x10 )
  {
    if ( !a2 || (v5 = *a2) == 0 )
    {
      v6 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x21080u, L"TrustedPublisher");
      v5 = v6;
      if ( !v6 )
        goto LABEL_10;
      CertControlStore(v6, 0, 4u, 0);
      if ( a2 )
        *a2 = v5;
    }
    CertificateInStore = CertFindCertificateInStore(v5, 0, 0, 0xE0000u, pcbData, 0);
    v10 = CertificateInStore;
    if ( CertificateInStore )
      v4 = 1;
  }
LABEL_10:
  if ( CertificateInStore )
    CertFreeCertificateContext(CertificateInStore);
  if ( !a2 && v5 )
    CertCloseStore(v5, 0);
  return v4;
}

```

## disassembly

```asm
0x14002e3cc  mov     r11, rsp
0x14002e3cf  mov     [r11+18h], rbx
0x14002e3d3  push    rsi
0x14002e3d4  push    rdi
0x14002e3d5  push    r14
0x14002e3d7  sub     rsp, 0B0h
0x14002e3de  mov     rax, cs:__security_cookie
0x14002e3e5  xor     rax, rsp
0x14002e3e8  mov     [rsp+0C8h+var_28], rax
0x14002e3f0  mov     rdi, rdx
0x14002e3f3  mov     [rsp+0C8h+var_70], rdx
0x14002e3f8  xor     eax, eax
0x14002e3fa  mov     qword ptr [rsp+0C8h+var_84], rax
0x14002e3ff  mov     [rsp+40h], rax
0x14002e404  xor     esi, esi
0x14002e406  mov     [r11-78h], rsi
0x14002e40a  xor     r14d, r14d
0x14002e40d  mov     [rsp+0C8h+var_98], r14d
0x14002e412  xor     ebx, ebx
0x14002e414  mov     [rsp+0C8h+var_90], rbx
0x14002e419  lea     rax, [r11-68h]
0x14002e41d  mov     [r11-80h], rax
0x14002e421  mov     [rsp+0C8h+pcbData], 40h ; '@'
0x14002e429  lea     r9, [rsp+0C8h+pcbData]; pcbData
0x14002e42e  lea     r8, [r11-68h]; pvData
0x14002e432  lea     edx, [rsi+0Fh]; dwPropId
0x14002e435  call    cs:__imp_CertGetCertificateContextProperty
0x14002e43b  test    eax, eax
0x14002e43d  jz      loc_14002E4E9
0x14002e443  cmp     [rsp+0C8h+pcbData], 10h
0x14002e448  jb      loc_14002E4E9
0x14002e44e  test    rdi, rdi
0x14002e451  jz      short loc_14002E462
0x14002e453  mov     rbx, [rdi]
0x14002e456  test    rbx, rbx
0x14002e459  jz      short loc_14002E462
0x14002e45b  mov     [rsp+0C8h+var_90], rbx
0x14002e460  jmp     short loc_14002E4A9
0x14002e462  lea     rax, aTrustedpublish; "TrustedPublisher"
0x14002e469  mov     [rsp+0C8h+pvPara], rax; pvPara
0x14002e46e  mov     r9d, 21080h; dwFlags
0x14002e474  xor     r8d, r8d; hCryptProv
0x14002e477  xor     edx, edx; dwEncodingType
0x14002e479  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x14002e47c  call    cs:__imp_CertOpenStore
0x14002e482  mov     rbx, rax
0x14002e485  mov     [rsp+0C8h+var_90], rax
0x14002e48a  test    rax, rax
0x14002e48d  jz      short loc_14002E4E9
0x14002e48f  xor     r9d, r9d; pvCtrlPara
0x14002e492  xor     edx, edx; dwFlags
0x14002e494  lea     r8d, [r9+4]; dwCtrlType
0x14002e498  mov     rcx, rax; hCertStore
0x14002e49b  call    cs:__imp_CertControlStore
0x14002e4a1  test    rdi, rdi
0x14002e4a4  jz      short loc_14002E4A9
0x14002e4a6  mov     [rdi], rbx
0x14002e4a9  mov     [rsp+0C8h+pPrevCertContext], 0; pPrevCertContext
0x14002e4b2  lea     rax, [rsp+0C8h+pcbData]
0x14002e4b7  mov     [rsp+0C8h+pvPara], rax; pvFindPara
0x14002e4bc  mov     r9d, 0E0000h; dwFindType
0x14002e4c2  xor     r8d, r8d; dwFindFlags
0x14002e4c5  xor     edx, edx; dwCertEncodingType
0x14002e4c7  mov     rcx, rbx; hCertStore
0x14002e4ca  call    cs:__imp_CertFindCertificateInStore
0x14002e4d0  mov     rsi, rax
0x14002e4d3  mov     [rsp+0C8h+var_78], rax
0x14002e4d8  mov     eax, 1
0x14002e4dd  test    rsi, rsi
0x14002e4e0  cmovnz  r14d, eax
0x14002e4e4  mov     [rsp+0C8h+var_98], r14d
0x14002e4e9  jmp     short loc_14002E509
0x14002e4eb  mov     ecx, eax
0x14002e4ed  xor     r8d, r8d
0x14002e4f0  call    pSetupExceptionHandler
0x14002e4f5  mov     rsi, [rsp+0C8h+var_78]
0x14002e4fa  mov     r14d, [rsp+0C8h+var_98]
0x14002e4ff  mov     rbx, [rsp+0C8h+var_90]
0x14002e504  mov     rdi, [rsp+0C8h+var_70]
0x14002e509  test    rsi, rsi
0x14002e50c  jz      short loc_14002E517
0x14002e50e  mov     rcx, rsi; pCertContext
0x14002e511  call    cs:__imp_CertFreeCertificateContext
0x14002e517  test    rdi, rdi
0x14002e51a  jnz     short loc_14002E52C
0x14002e51c  test    rbx, rbx
0x14002e51f  jz      short loc_14002E52C
0x14002e521  xor     edx, edx; dwFlags
0x14002e523  mov     rcx, rbx; hCertStore
0x14002e526  call    cs:__imp_CertCloseStore
0x14002e52c  mov     eax, r14d
0x14002e52f  mov     rcx, [rsp+0C8h+var_28]
0x14002e537  xor     rcx, rsp; StackCookie
0x14002e53a  call    __security_check_cookie
0x14002e53f  mov     rbx, [rsp+0C8h+arg_10]
0x14002e547  add     rsp, 0B0h
0x14002e54e  pop     r14
0x14002e550  pop     rdi
0x14002e551  pop     rsi
0x14002e552  retn
0x1400460d7  push    rbp
0x1400460d9  sub     rsp, 30h
0x1400460dd  mov     rbp, rdx
0x1400460e0  mov     rcx, [rcx]
0x1400460e3  mov     ecx, [rcx]
0x1400460e5  call    pSetupExceptionFilter
0x1400460ea  nop
0x1400460eb  add     rsp, 30h
0x1400460ef  pop     rbp
0x1400460f0  retn
```
