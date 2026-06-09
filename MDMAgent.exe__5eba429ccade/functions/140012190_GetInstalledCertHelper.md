# GetInstalledCertHelper

- ea: `0x140012190`
- end: `0x140012219`
- name: `GetInstalledCertHelper`
- size: `137`
- prototype: `signed int __fastcall(__int64, int, const void *, _QWORD *, PCCERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140012054`

## callees

- `0x140012190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400121cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400121cb`
- `CRYPT32!CertFindCertificateInStore` at `0x1400121fe`
- `CRYPT32!CertFindCertificateInStore` at `0x1400121fe`
- `CRYPT32!CertOpenStore` at `0x1400121ba`
- `CRYPT32!CertOpenStore` at `0x1400121ba`

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
0x140012190  mov     [rsp+arg_0], rbx
0x140012195  push    rdi
0x140012196  sub     rsp, 30h
0x14001219a  or      edx, 1
0x14001219d  lea     rax, aMy; "MY"
0x1400121a4  mov     rbx, r9
0x1400121a7  mov     [rsp+38h+pvPara], rax; pvPara
0x1400121ac  mov     r9d, edx; dwFlags
0x1400121af  mov     rdi, r8
0x1400121b2  xor     edx, edx; dwEncodingType
0x1400121b4  xor     r8d, r8d; hCryptProv
0x1400121b7  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x1400121ba  call    cs:__imp_CertOpenStore
0x1400121c0  mov     [rbx], rax
0x1400121c3  mov     rcx, rax; hCertStore
0x1400121c6  test    rax, rax
0x1400121c9  jnz     short loc_1400121DF
0x1400121cb  call    cs:__imp_GetLastError
0x1400121d1  test    eax, eax
0x1400121d3  jle     short loc_14001220E
0x1400121d5  movzx   eax, ax
0x1400121d8  or      eax, 80070000h
0x1400121dd  jmp     short loc_14001220E
0x1400121df  mov     rbx, [rsp+38h+arg_20]
0x1400121e4  xor     r8d, r8d; dwFindFlags
0x1400121e7  mov     r9d, 10000h; dwFindType
0x1400121ed  mov     rax, [rbx]
0x1400121f0  lea     edx, [r8+1]; dwCertEncodingType
0x1400121f4  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x1400121f9  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x1400121fe  call    cs:__imp_CertFindCertificateInStore
0x140012204  mov     [rbx], rax
0x140012207  test    rax, rax
0x14001220a  jz      short loc_1400121CB
0x14001220c  xor     eax, eax
0x14001220e  mov     rbx, [rsp+38h+arg_0]
0x140012213  add     rsp, 30h
0x140012217  pop     rdi
0x140012218  retn
```
