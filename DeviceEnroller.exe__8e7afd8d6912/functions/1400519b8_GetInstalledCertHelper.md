# GetInstalledCertHelper

- ea: `0x1400519b8`
- end: `0x140051a41`
- name: `GetInstalledCertHelper`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14005187c`

## callees

- `0x1400519b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400519f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400519f3`
- `CRYPT32!CertFindCertificateInStore` at `0x140051a26`
- `CRYPT32!CertFindCertificateInStore` at `0x140051a26`
- `CRYPT32!CertOpenStore` at `0x1400519e2`
- `CRYPT32!CertOpenStore` at `0x1400519e2`

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
0x1400519b8  mov     [rsp+arg_0], rbx
0x1400519bd  push    rdi
0x1400519be  sub     rsp, 30h
0x1400519c2  or      edx, 1
0x1400519c5  lea     rax, aMy; "MY"
0x1400519cc  mov     rbx, r9
0x1400519cf  mov     [rsp+38h+pvPara], rax; pvPara
0x1400519d4  mov     r9d, edx; dwFlags
0x1400519d7  mov     rdi, r8
0x1400519da  xor     edx, edx; dwEncodingType
0x1400519dc  xor     r8d, r8d; hCryptProv
0x1400519df  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x1400519e2  call    cs:__imp_CertOpenStore
0x1400519e8  mov     [rbx], rax
0x1400519eb  mov     rcx, rax; hCertStore
0x1400519ee  test    rax, rax
0x1400519f1  jnz     short loc_140051A07
0x1400519f3  call    cs:__imp_GetLastError
0x1400519f9  test    eax, eax
0x1400519fb  jle     short loc_140051A36
0x1400519fd  movzx   eax, ax
0x140051a00  or      eax, 80070000h
0x140051a05  jmp     short loc_140051A36
0x140051a07  mov     rbx, [rsp+38h+arg_20]
0x140051a0c  xor     r8d, r8d; dwFindFlags
0x140051a0f  mov     r9d, 10000h; dwFindType
0x140051a15  mov     rax, [rbx]
0x140051a18  lea     edx, [r8+1]; dwCertEncodingType
0x140051a1c  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x140051a21  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x140051a26  call    cs:__imp_CertFindCertificateInStore
0x140051a2c  mov     [rbx], rax
0x140051a2f  test    rax, rax
0x140051a32  jz      short loc_1400519F3
0x140051a34  xor     eax, eax
0x140051a36  mov     rbx, [rsp+38h+arg_0]
0x140051a3b  add     rsp, 30h
0x140051a3f  pop     rdi
0x140051a40  retn
```
