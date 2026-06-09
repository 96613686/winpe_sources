# IsAuthenticodePublisherTrusted(_CERT_CONTEXT const *,void * *)

- ea: `0x140001a08`
- end: `0x140001aea`
- name: `?IsAuthenticodePublisherTrusted@@YAHPEBU_CERT_CONTEXT@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001af0`

## callees

- `0x140001a08`
- `0x140001d90`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x140001abf`
- `CRYPT32!CertFreeCertificateContext` at `0x140001abf`
- `CRYPT32!CertFindCertificateInStore` at `0x140001aac`
- `CRYPT32!CertFindCertificateInStore` at `0x140001aac`
- `CRYPT32!CertControlStore` at `0x140001a89`
- `CRYPT32!CertControlStore` at `0x140001a89`
- `CRYPT32!CertGetCertificateContextProperty` at `0x140001a40`
- `CRYPT32!CertGetCertificateContextProperty` at `0x140001a40`
- `CRYPT32!CertOpenStore` at `0x140001a6f`
- `CRYPT32!CertOpenStore` at `0x140001a6f`
- `CRYPT32!CertCloseStore` at `0x140001aca`
- `CRYPT32!CertCloseStore` at `0x140001aca`

## pseudocode

```c
__int64 __fastcall IsAuthenticodePublisherTrusted(const struct _CERT_CONTEXT *a1, void **a2)
{
  unsigned int v2; // ebx
  HCERTSTORE v3; // rax
  void *v4; // rdi
  const CERT_CONTEXT *CertificateInStore; // rax
  _QWORD pvFindPara[2]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[24]; // [rsp+40h] [rbp-28h] BYREF

  pvFindPara[0] = 20;
  v2 = 0;
  pvFindPara[1] = v8;
  if ( CertGetCertificateContextProperty(a1, 0xFu, v8, (DWORD *)pvFindPara) )
  {
    if ( LODWORD(pvFindPara[0]) >= 0x10 )
    {
      v3 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x21080u, L"TrustedPublisher");
      v4 = v3;
      if ( v3 )
      {
        CertControlStore(v3, 0, 4u, 0);
        CertificateInStore = CertFindCertificateInStore(v4, 0, 0, 0xE0000u, pvFindPara, 0);
        if ( CertificateInStore )
        {
          v2 = 1;
          CertFreeCertificateContext(CertificateInStore);
        }
        CertCloseStore(v4, 0);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140001a08  mov     r11, rsp
0x140001a0b  mov     [r11+10h], rbx
0x140001a0f  push    rdi
0x140001a10  sub     rsp, 60h
0x140001a14  mov     rax, cs:__security_cookie
0x140001a1b  xor     rax, rsp
0x140001a1e  mov     [rsp+68h+var_10], rax
0x140001a23  lea     rax, [r11-28h]
0x140001a27  mov     qword ptr [r11-38h], 14h
0x140001a2f  xor     ebx, ebx
0x140001a31  mov     [r11-30h], rax
0x140001a35  lea     r9, [r11-38h]; pcbData
0x140001a39  lea     r8, [r11-28h]; pvData
0x140001a3d  lea     edx, [rbx+0Fh]; dwPropId
0x140001a40  call    cs:__imp_CertGetCertificateContextProperty
0x140001a46  test    eax, eax
0x140001a48  jz      loc_140001AD0
0x140001a4e  cmp     [rsp+68h+pvFindPara], 10h
0x140001a53  jb      short loc_140001AD0
0x140001a55  lea     rax, aTrustedpublish; "TrustedPublisher"
0x140001a5c  mov     r9d, 21080h; dwFlags
0x140001a62  xor     r8d, r8d; hCryptProv
0x140001a65  mov     [rsp+68h+pvPara], rax; pvPara
0x140001a6a  xor     edx, edx; dwEncodingType
0x140001a6c  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x140001a6f  call    cs:__imp_CertOpenStore
0x140001a75  mov     rdi, rax
0x140001a78  test    rax, rax
0x140001a7b  jz      short loc_140001AD0
0x140001a7d  xor     r9d, r9d; pvCtrlPara
0x140001a80  lea     r8d, [rbx+4]; dwCtrlType
0x140001a84  xor     edx, edx; dwFlags
0x140001a86  mov     rcx, rax; hCertStore
0x140001a89  call    cs:__imp_CertControlStore
0x140001a8f  lea     rax, [rsp+68h+pvFindPara]
0x140001a94  mov     [rsp+68h+pPrevCertContext], rbx; pPrevCertContext
0x140001a99  mov     r9d, 0E0000h; dwFindType
0x140001a9f  mov     [rsp+68h+pvPara], rax; pvFindPara
0x140001aa4  xor     r8d, r8d; dwFindFlags
0x140001aa7  xor     edx, edx; dwCertEncodingType
0x140001aa9  mov     rcx, rdi; hCertStore
0x140001aac  call    cs:__imp_CertFindCertificateInStore
0x140001ab2  test    rax, rax
0x140001ab5  jz      short loc_140001AC5
0x140001ab7  mov     ebx, 1
0x140001abc  mov     rcx, rax; pCertContext
0x140001abf  call    cs:__imp_CertFreeCertificateContext
0x140001ac5  xor     edx, edx; dwFlags
0x140001ac7  mov     rcx, rdi; hCertStore
0x140001aca  call    cs:__imp_CertCloseStore
0x140001ad0  mov     eax, ebx
0x140001ad2  mov     rcx, [rsp+68h+var_10]
0x140001ad7  xor     rcx, rsp; StackCookie
0x140001ada  call    __security_check_cookie
0x140001adf  mov     rbx, [rsp+68h+arg_8]
0x140001ae4  add     rsp, 60h
0x140001ae8  pop     rdi
0x140001ae9  retn
```
