# GetInstalledCertHelper

- ea: `0x140012a1c`
- end: `0x140012ab8`
- name: `GetInstalledCertHelper`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400128b0`

## callees

- `0x140012a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012a5d`
- `CRYPT32!CertFindCertificateInStore` at `0x140012a96`
- `CRYPT32!CertFindCertificateInStore` at `0x140012a96`
- `CRYPT32!CertOpenStore` at `0x140012a46`
- `CRYPT32!CertOpenStore` at `0x140012a46`

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
0x140012a1c  mov     [rsp+arg_0], rbx
0x140012a21  push    rdi
0x140012a22  sub     rsp, 30h
0x140012a26  or      edx, 1
0x140012a29  lea     rax, aMy; "MY"
0x140012a30  mov     rbx, r9
0x140012a33  mov     [rsp+38h+pvPara], rax; pvPara
0x140012a38  mov     r9d, edx; dwFlags
0x140012a3b  mov     rdi, r8
0x140012a3e  xor     edx, edx; dwEncodingType
0x140012a40  xor     r8d, r8d; hCryptProv
0x140012a43  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x140012a46  call    cs:__imp_CertOpenStore
0x140012a4d  nop     dword ptr [rax+rax+00h]
0x140012a52  mov     [rbx], rax
0x140012a55  mov     rcx, rax; hCertStore
0x140012a58  test    rax, rax
0x140012a5b  jnz     short loc_140012A77
0x140012a5d  call    cs:__imp_GetLastError
0x140012a64  nop     dword ptr [rax+rax+00h]
0x140012a69  test    eax, eax
0x140012a6b  jle     short loc_140012AAC
0x140012a6d  movzx   eax, ax
0x140012a70  or      eax, 80070000h
0x140012a75  jmp     short loc_140012AAC
0x140012a77  mov     rbx, [rsp+38h+arg_20]
0x140012a7c  xor     r8d, r8d; dwFindFlags
0x140012a7f  mov     r9d, 10000h; dwFindType
0x140012a85  mov     rax, [rbx]
0x140012a88  lea     edx, [r8+1]; dwCertEncodingType
0x140012a8c  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x140012a91  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x140012a96  call    cs:__imp_CertFindCertificateInStore
0x140012a9d  nop     dword ptr [rax+rax+00h]
0x140012aa2  mov     [rbx], rax
0x140012aa5  test    rax, rax
0x140012aa8  jz      short loc_140012A5D
0x140012aaa  xor     eax, eax
0x140012aac  mov     rbx, [rsp+38h+arg_0]
0x140012ab1  add     rsp, 30h
0x140012ab5  pop     rdi
0x140012ab6  retn
```
