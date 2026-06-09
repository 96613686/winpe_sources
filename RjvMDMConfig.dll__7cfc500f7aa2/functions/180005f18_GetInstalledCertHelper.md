# GetInstalledCertHelper

- ea: `0x180005f18`
- end: `0x180005fb4`
- name: `GetInstalledCertHelper`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180005dc4`

## callees

- `0x180005f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f59`
- `CRYPT32!CertOpenStore` at `0x180005f42`
- `CRYPT32!CertOpenStore` at `0x180005f42`
- `CRYPT32!CertFindCertificateInStore` at `0x180005f92`
- `CRYPT32!CertFindCertificateInStore` at `0x180005f92`

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
0x180005f18  mov     [rsp+arg_0], rbx
0x180005f1d  push    rdi
0x180005f1e  sub     rsp, 30h
0x180005f22  or      edx, 1
0x180005f25  lea     rax, aMy_0; "MY"
0x180005f2c  mov     rbx, r9
0x180005f2f  mov     [rsp+38h+pvPara], rax; pvPara
0x180005f34  mov     r9d, edx; dwFlags
0x180005f37  mov     rdi, r8
0x180005f3a  xor     edx, edx; dwEncodingType
0x180005f3c  xor     r8d, r8d; hCryptProv
0x180005f3f  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x180005f42  call    cs:__imp_CertOpenStore
0x180005f49  nop     dword ptr [rax+rax+00h]
0x180005f4e  mov     [rbx], rax
0x180005f51  mov     rcx, rax; hCertStore
0x180005f54  test    rax, rax
0x180005f57  jnz     short loc_180005F73
0x180005f59  call    cs:__imp_GetLastError
0x180005f60  nop     dword ptr [rax+rax+00h]
0x180005f65  test    eax, eax
0x180005f67  jle     short loc_180005FA8
0x180005f69  movzx   eax, ax
0x180005f6c  or      eax, 80070000h
0x180005f71  jmp     short loc_180005FA8
0x180005f73  mov     rbx, [rsp+38h+arg_20]
0x180005f78  xor     r8d, r8d; dwFindFlags
0x180005f7b  mov     r9d, 10000h; dwFindType
0x180005f81  mov     rax, [rbx]
0x180005f84  lea     edx, [r8+1]; dwCertEncodingType
0x180005f88  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x180005f8d  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x180005f92  call    cs:__imp_CertFindCertificateInStore
0x180005f99  nop     dword ptr [rax+rax+00h]
0x180005f9e  mov     [rbx], rax
0x180005fa1  test    rax, rax
0x180005fa4  jz      short loc_180005F59
0x180005fa6  xor     eax, eax
0x180005fa8  mov     rbx, [rsp+38h+arg_0]
0x180005fad  add     rsp, 30h
0x180005fb1  pop     rdi
0x180005fb2  retn
```
