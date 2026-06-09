# BINDING_OBJECT_EXTENSION::DoesCertExists(ushort const *,ushort const *)

- ea: `0x18002c35c`
- end: `0x18002c458`
- name: `?DoesCertExists@BINDING_OBJECT_EXTENSION@@CAHPEBG0@Z`
- size: `252`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002c0a8`

## callees

- `0x180001fb0`
- `0x18002c268`
- `0x18002c35c`
- `0x180034d00`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18002c3d9`
- `CRYPT32!CertOpenStore` at `0x18002c3d9`
- `CRYPT32!CertCloseStore` at `0x18002c426`
- `CRYPT32!CertCloseStore` at `0x18002c426`
- `CRYPT32!CertFreeCertificateContext` at `0x18002c418`
- `CRYPT32!CertFreeCertificateContext` at `0x18002c418`
- `CRYPT32!CertFindCertificateInStore` at `0x18002c405`
- `CRYPT32!CertFindCertificateInStore` at `0x18002c405`

## pseudocode

```c
__int64 __fastcall BINDING_OBJECT_EXTENSION::DoesCertExists(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int v3; // edi
  HCERTSTORE v4; // rbx
  const CERT_CONTEXT *CertificateInStore; // rax
  unsigned int v7; // [rsp+30h] [rbp-50h] BYREF
  __int128 pvFindPara; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v9[4]; // [rsp+48h] [rbp-38h] BYREF
  _QWORD *v10; // [rsp+68h] [rbp-18h]
  int v11; // [rsp+70h] [rbp-10h]
  __int16 v12; // [rsp+74h] [rbp-Ch]

  v11 = 32;
  v3 = 0;
  v12 = 256;
  v9[0] = 0;
  v7 = 0;
  v10 = v9;
  pvFindPara = 0;
  if ( (int)BINDING_OBJECT_EXTENSION::ConvertStringToByteArray(a1, &v7, (struct BUFFER *)v9) >= 0 )
  {
    LODWORD(pvFindPara) = v7;
    *((_QWORD *)&pvFindPara + 1) = v10;
    v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x2C000u, a2);
    if ( v4 )
    {
      CertificateInStore = CertFindCertificateInStore(v4, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
      if ( CertificateInStore )
      {
        v3 = 1;
        CertFreeCertificateContext(CertificateInStore);
      }
      CertCloseStore(v4, 1u);
    }
  }
  BUFFER::~BUFFER((BUFFER *)v9);
  return v3;
}

```

## disassembly

```asm
0x18002c35c  mov     [rsp-8+arg_10], rbx
0x18002c361  mov     [rsp-8+arg_18], rdi
0x18002c366  push    rbp
0x18002c367  mov     rbp, rsp
0x18002c36a  sub     rsp, 80h
0x18002c371  mov     rax, cs:__security_cookie
0x18002c378  xor     rax, rsp
0x18002c37b  mov     [rbp+var_8], rax
0x18002c37f  mov     rbx, rdx
0x18002c382  mov     [rbp+var_10], 20h ; ' '
0x18002c389  xor     edi, edi
0x18002c38b  mov     [rbp+var_C], 100h
0x18002c391  xorps   xmm0, xmm0
0x18002c394  mov     [rbp+var_38], rdi
0x18002c398  lea     rax, [rbp+var_38]
0x18002c39c  mov     [rbp+var_50], edi
0x18002c39f  lea     rdx, [rbp+var_50]; unsigned int *
0x18002c3a3  mov     [rbp+var_18], rax
0x18002c3a7  lea     r8, [rbp+var_38]; struct BUFFER *
0x18002c3ab  movups  [rbp+pvFindPara], xmm0
0x18002c3af  call    ?ConvertStringToByteArray@BINDING_OBJECT_EXTENSION@@CAJPEBGPEAKPEAVBUFFER@@@Z; BINDING_OBJECT_EXTENSION::ConvertStringToByteArray(ushort const *,ulong *,BUFFER *)
0x18002c3b4  test    eax, eax
0x18002c3b6  js      short loc_18002C42C
0x18002c3b8  mov     eax, [rbp+var_50]
0x18002c3bb  lea     ecx, [rdi+0Ah]; lpszStoreProvider
0x18002c3be  mov     dword ptr [rbp+pvFindPara], eax
0x18002c3c1  mov     r9d, 2C000h; dwFlags
0x18002c3c7  mov     rax, [rbp+var_18]
0x18002c3cb  xor     r8d, r8d; hCryptProv
0x18002c3ce  xor     edx, edx; dwEncodingType
0x18002c3d0  mov     qword ptr [rbp+pvFindPara+8], rax
0x18002c3d4  mov     [rsp+80h+pvPara], rbx; pvPara
0x18002c3d9  call    cs:__imp_CertOpenStore
0x18002c3df  mov     rbx, rax
0x18002c3e2  test    rax, rax
0x18002c3e5  jz      short loc_18002C42C
0x18002c3e7  mov     r9d, 10000h; dwFindType
0x18002c3ed  mov     [rsp+80h+pPrevCertContext], rdi; pPrevCertContext
0x18002c3f2  lea     rax, [rbp+pvFindPara]
0x18002c3f6  xor     r8d, r8d; dwFindFlags
0x18002c3f9  mov     rcx, rbx; hCertStore
0x18002c3fc  mov     [rsp+80h+pvPara], rax; pvFindPara
0x18002c401  lea     edx, [r9+1]; dwCertEncodingType
0x18002c405  call    cs:__imp_CertFindCertificateInStore
0x18002c40b  test    rax, rax
0x18002c40e  jz      short loc_18002C41E
0x18002c410  mov     rcx, rax; pCertContext
0x18002c413  mov     edi, 1
0x18002c418  call    cs:__imp_CertFreeCertificateContext
0x18002c41e  mov     edx, 1; dwFlags
0x18002c423  mov     rcx, rbx; hCertStore
0x18002c426  call    cs:__imp_CertCloseStore
0x18002c42c  lea     rcx, [rbp+var_38]; this
0x18002c430  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002c435  mov     eax, edi
0x18002c437  mov     rcx, [rbp+var_8]
0x18002c43b  xor     rcx, rsp; StackCookie
0x18002c43e  call    __security_check_cookie
0x18002c443  lea     r11, [rsp+80h+var_s0]
0x18002c44b  mov     rbx, [r11+20h]
0x18002c44f  mov     rdi, [r11+28h]
0x18002c453  mov     rsp, r11
0x18002c456  pop     rbp
0x18002c457  retn
```
