# IsAuthenticodePublisherTrusted(_CERT_CONTEXT const *,void * *)

- ea: `0x180013330`
- end: `0x180013458`
- name: `?IsAuthenticodePublisherTrusted@@YAHPEBU_CERT_CONTEXT@@PEAPEAX@Z`
- size: `296`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013460`

## callees

- `0x180001720`
- `0x18000725c`
- `0x180013330`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18001340b`
- `CRYPT32!CertFreeCertificateContext` at `0x18001340b`
- `CRYPT32!CertCloseStore` at `0x180013416`
- `CRYPT32!CertCloseStore` at `0x180013416`
- `CRYPT32!CertControlStore` at `0x1800133d3`
- `CRYPT32!CertControlStore` at `0x1800133d3`
- `CRYPT32!CertOpenStore` at `0x18001339d`
- `CRYPT32!CertOpenStore` at `0x18001339d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180013368`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180013368`
- `CRYPT32!CertFindCertificateInStore` at `0x1800133f6`
- `CRYPT32!CertFindCertificateInStore` at `0x1800133f6`

## string_xrefs

- `0x1800133ab`: `Failed to Open Cert Store`

## pseudocode

```c
__int64 __fastcall IsAuthenticodePublisherTrusted(const struct _CERT_CONTEXT *a1, void **a2)
{
  unsigned int v2; // edi
  HCERTSTORE v3; // rax
  void *v4; // rbx
  const CERT_CONTEXT *CertificateInStore; // rax
  _QWORD pvFindPara[2]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[24]; // [rsp+40h] [rbp-28h] BYREF

  pvFindPara[0] = 20;
  v2 = 0;
  pvFindPara[1] = v8;
  if ( CertGetCertificateContextProperty(a1, 0xFu, v8, (DWORD *)pvFindPara) && LODWORD(pvFindPara[0]) >= 0x10 )
  {
    v3 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x21080u, L"TrustedPublisher");
    v4 = v3;
    if ( v3 )
    {
      CertControlStore(v3, 0, 4u, 0);
      CertificateInStore = CertFindCertificateInStore(v4, 0, 0, 0xE0000u, pvFindPara, 0);
      LOBYTE(v2) = CertificateInStore != 0;
      if ( CertificateInStore )
        CertFreeCertificateContext(CertificateInStore);
      CertCloseStore(v4, 0);
    }
    else
    {
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 1u, 2u, L"Failed to Open Cert Store");
    }
  }
  else
  {
    AxISEvents::DebugMsg(
      (AxISEvents *)&qword_180021AD8,
      1u,
      2u,
      L"Failed to get HashProp, length is %d",
      LODWORD(pvFindPara[0]));
  }
  return v2;
}

```

## disassembly

```asm
0x180013330  mov     r11, rsp
0x180013333  mov     [r11+10h], rbx
0x180013337  push    rdi
0x180013338  sub     rsp, 60h
0x18001333c  mov     rax, cs:__security_cookie
0x180013343  xor     rax, rsp
0x180013346  mov     [rsp+68h+var_10], rax
0x18001334b  lea     rax, [r11-28h]
0x18001334f  mov     qword ptr [r11-38h], 14h
0x180013357  xor     edi, edi
0x180013359  mov     [r11-30h], rax
0x18001335d  lea     r9, [r11-38h]; pcbData
0x180013361  lea     r8, [r11-28h]; pvData
0x180013365  lea     edx, [rdi+0Fh]; dwPropId
0x180013368  call    cs:__imp_CertGetCertificateContextProperty
0x18001336e  mov     ecx, [rsp+68h+pvFindPara]
0x180013372  test    eax, eax
0x180013374  jz      loc_18001341E
0x18001337a  cmp     ecx, 10h
0x18001337d  jb      loc_18001341E
0x180013383  lea     rax, aTrustedpublish; "TrustedPublisher"
0x18001338a  mov     r9d, 21080h; dwFlags
0x180013390  xor     r8d, r8d; hCryptProv
0x180013393  mov     [rsp+68h+pvPara], rax; pvPara
0x180013398  xor     edx, edx; dwEncodingType
0x18001339a  lea     ecx, [rdi+0Ah]; lpszStoreProvider
0x18001339d  call    cs:__imp_CertOpenStore
0x1800133a3  mov     rbx, rax
0x1800133a6  test    rax, rax
0x1800133a9  jnz     short loc_1800133C7
0x1800133ab  lea     r9, aFailedToOpenCe; "Failed to Open Cert Store"
0x1800133b2  lea     edx, [rdi+1]; unsigned int
0x1800133b5  lea     r8d, [rdi+2]; unsigned __int8
0x1800133b9  lea     rcx, qword_180021AD8; this
0x1800133c0  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800133c5  jmp     short loc_18001343E
0x1800133c7  xor     r9d, r9d; pvCtrlPara
0x1800133ca  xor     edx, edx; dwFlags
0x1800133cc  mov     rcx, rbx; hCertStore
0x1800133cf  lea     r8d, [r9+4]; dwCtrlType
0x1800133d3  call    cs:__imp_CertControlStore
0x1800133d9  lea     rax, [rsp+68h+pvFindPara]
0x1800133de  mov     [rsp+68h+pPrevCertContext], rdi; pPrevCertContext
0x1800133e3  mov     r9d, 0E0000h; dwFindType
0x1800133e9  mov     [rsp+68h+pvPara], rax; pvFindPara
0x1800133ee  xor     r8d, r8d; dwFindFlags
0x1800133f1  xor     edx, edx; dwCertEncodingType
0x1800133f3  mov     rcx, rbx; hCertStore
0x1800133f6  call    cs:__imp_CertFindCertificateInStore
0x1800133fc  test    rax, rax
0x1800133ff  setnz   dil
0x180013403  test    rax, rax
0x180013406  jz      short loc_180013411
0x180013408  mov     rcx, rax; pCertContext
0x18001340b  call    cs:__imp_CertFreeCertificateContext
0x180013411  xor     edx, edx; dwFlags
0x180013413  mov     rcx, rbx; hCertStore
0x180013416  call    cs:__imp_CertCloseStore
0x18001341c  jmp     short loc_18001343E
0x18001341e  mov     edx, 1; unsigned int
0x180013423  mov     dword ptr [rsp+68h+pvPara], ecx
0x180013427  lea     r9, aFailedToGetHas; "Failed to get HashProp, length is %d"
0x18001342e  lea     rcx, qword_180021AD8; this
0x180013435  lea     r8d, [rdx+1]; unsigned __int8
0x180013439  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18001343e  mov     eax, edi
0x180013440  mov     rcx, [rsp+68h+var_10]
0x180013445  xor     rcx, rsp; StackCookie
0x180013448  call    __security_check_cookie
0x18001344d  mov     rbx, [rsp+68h+arg_8]
0x180013452  add     rsp, 60h
0x180013456  pop     rdi
0x180013457  retn
```
