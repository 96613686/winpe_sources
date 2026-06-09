# GetInstalledCertHelper

- ea: `0x180093094`
- end: `0x18009311d`
- name: `GetInstalledCertHelper`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180092f44`

## callees

- `0x180093094`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800930cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800930cf`
- `CRYPT32!CertOpenStore` at `0x1800930be`
- `CRYPT32!CertOpenStore` at `0x1800930be`
- `CRYPT32!CertFindCertificateInStore` at `0x180093102`
- `CRYPT32!CertFindCertificateInStore` at `0x180093102`

## pseudocode

```c
signed int __fastcall GetInstalledCertHelper(__int64 a1, int a2, const void *a3, _QWORD *a4, PCCERT_CONTEXT *a5)
{
  HCERTSTORE v7; // rax
  signed int result; // eax
  PCCERT_CONTEXT CertificateInStore; // rax

  v7 = CertOpenStore((LPCSTR)0xD, 0, 0, a2 | 1u, L"MY");
  *a4 = v7;
  if ( v7 )
  {
    CertificateInStore = CertFindCertificateInStore(v7, 1u, 0, 0x10000u, a3, *a5);
    *a5 = CertificateInStore;
    if ( CertificateInStore )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180093094  mov     [rsp+arg_0], rbx
0x180093099  push    rdi
0x18009309a  sub     rsp, 30h
0x18009309e  or      edx, 1
0x1800930a1  lea     rax, aMy; "MY"
0x1800930a8  mov     rbx, r9
0x1800930ab  mov     [rsp+38h+pvPara], rax; pvPara
0x1800930b0  mov     r9d, edx; dwFlags
0x1800930b3  mov     rdi, r8
0x1800930b6  xor     edx, edx; dwEncodingType
0x1800930b8  xor     r8d, r8d; hCryptProv
0x1800930bb  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x1800930be  call    cs:__imp_CertOpenStore
0x1800930c4  mov     [rbx], rax
0x1800930c7  mov     rcx, rax; hCertStore
0x1800930ca  test    rax, rax
0x1800930cd  jnz     short loc_1800930E3
0x1800930cf  call    cs:__imp_GetLastError
0x1800930d5  test    eax, eax
0x1800930d7  jle     short loc_180093112
0x1800930d9  movzx   eax, ax
0x1800930dc  or      eax, 80070000h
0x1800930e1  jmp     short loc_180093112
0x1800930e3  mov     rbx, [rsp+38h+arg_20]
0x1800930e8  xor     r8d, r8d; dwFindFlags
0x1800930eb  mov     r9d, 10000h; dwFindType
0x1800930f1  mov     rax, [rbx]
0x1800930f4  lea     edx, [r8+1]; dwCertEncodingType
0x1800930f8  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x1800930fd  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x180093102  call    cs:__imp_CertFindCertificateInStore
0x180093108  mov     [rbx], rax
0x18009310b  test    rax, rax
0x18009310e  jz      short loc_1800930CF
0x180093110  xor     eax, eax
0x180093112  mov     rbx, [rsp+38h+arg_0]
0x180093117  add     rsp, 30h
0x18009311b  pop     rdi
0x18009311c  retn
```
