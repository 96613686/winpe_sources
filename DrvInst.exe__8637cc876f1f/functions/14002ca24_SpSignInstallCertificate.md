# SpSignInstallCertificate

- ea: `0x14002ca24`
- end: `0x14002cac8`
- name: `SpSignInstallCertificate`
- size: `164`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14002ccdc`
- `0x14002e700`

## callees

- `0x14000a614`
- `0x14000a630`
- `0x14002ca24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ca69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ca88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ca69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ca88`
- `CRYPT32!CertAddCertificateContextToStore` at `0x14002ca7e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x14002ca7e`
- `CRYPT32!CertCloseStore` at `0x14002cab0`
- `CRYPT32!CertCloseStore` at `0x14002cab0`
- `CRYPT32!CertOpenStore` at `0x14002ca56`
- `CRYPT32!CertOpenStore` at `0x14002ca56`

## pseudocode

```c
DWORD __fastcall SpSignInstallCertificate(PCCERT_CONTEXT pCertContext)
{
  DWORD LastError; // ebx
  HCERTSTORE v3; // rax
  void *v4; // rdi

  LastError = 0;
  v3 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x24000u, L"TrustedPublisher");
  v4 = v3;
  if ( !v3 )
    return GetLastError();
  if ( !CertAddCertificateContextToStore(v3, pCertContext, 2u, 0) )
    LastError = GetLastError();
  CertCloseStore(v4, 0);
  return LastError;
}

```

## disassembly

```asm
0x14002ca24  mov     [rsp+arg_0], rbx
0x14002ca29  mov     [rsp+arg_18], rsi
0x14002ca2e  push    rdi
0x14002ca2f  sub     rsp, 30h
0x14002ca33  mov     rsi, rcx
0x14002ca36  xor     ebx, ebx
0x14002ca38  mov     [rsp+38h+arg_8], ebx
0x14002ca3c  lea     rax, aTrustedpublish; "TrustedPublisher"
0x14002ca43  mov     [rsp+38h+pvPara], rax; pvPara
0x14002ca48  mov     r9d, 24000h; dwFlags
0x14002ca4e  xor     r8d, r8d; hCryptProv
0x14002ca51  xor     edx, edx; dwEncodingType
0x14002ca53  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x14002ca56  call    cs:__imp_CertOpenStore
0x14002ca5c  mov     rdi, rax
0x14002ca5f  mov     [rsp+38h+arg_10], rax
0x14002ca64  test    rax, rax
0x14002ca67  jnz     short loc_14002CA71
0x14002ca69  call    cs:__imp_GetLastError
0x14002ca6f  jmp     short loc_14002CAB8
0x14002ca71  xor     r9d, r9d; ppStoreContext
0x14002ca74  lea     r8d, [r9+2]; dwAddDisposition
0x14002ca78  mov     rdx, rsi; pCertContext
0x14002ca7b  mov     rcx, rax; hCertStore
0x14002ca7e  call    cs:__imp_CertAddCertificateContextToStore
0x14002ca84  test    eax, eax
0x14002ca86  jnz     short loc_14002CA94
0x14002ca88  call    cs:__imp_GetLastError
0x14002ca8e  mov     ebx, eax
0x14002ca90  mov     [rsp+38h+arg_8], eax
0x14002ca94  jmp     short loc_14002CAAB
0x14002ca96  mov     ecx, eax
0x14002ca98  lea     r8, [rsp+38h+arg_8]
0x14002ca9d  call    pSetupExceptionHandler
0x14002caa2  mov     ebx, [rsp+38h+arg_8]
0x14002caa6  mov     rdi, [rsp+38h+arg_10]
0x14002caab  xor     edx, edx; dwFlags
0x14002caad  mov     rcx, rdi; hCertStore
0x14002cab0  call    cs:__imp_CertCloseStore
0x14002cab6  mov     eax, ebx
0x14002cab8  mov     rbx, [rsp+38h+arg_0]
0x14002cabd  mov     rsi, [rsp+38h+arg_18]
0x14002cac2  add     rsp, 30h
0x14002cac6  pop     rdi
0x14002cac7  retn
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
