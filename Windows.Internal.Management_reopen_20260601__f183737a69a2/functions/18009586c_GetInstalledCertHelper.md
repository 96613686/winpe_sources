# GetInstalledCertHelper

- ea: `0x18009586c`
- end: `0x180095908`
- name: `GetInstalledCertHelper`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800956ec`

## callees

- `0x18009586c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800958ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800958ad`
- `CRYPT32!CertOpenStore` at `0x180095896`
- `CRYPT32!CertOpenStore` at `0x180095896`
- `CRYPT32!CertFindCertificateInStore` at `0x1800958e6`
- `CRYPT32!CertFindCertificateInStore` at `0x1800958e6`

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
0x18009586c  mov     [rsp+arg_0], rbx
0x180095871  push    rdi
0x180095872  sub     rsp, 30h
0x180095876  or      edx, 1
0x180095879  lea     rax, aMy; "MY"
0x180095880  mov     rbx, r9
0x180095883  mov     [rsp+38h+pvPara], rax; pvPara
0x180095888  mov     r9d, edx; dwFlags
0x18009588b  mov     rdi, r8
0x18009588e  xor     edx, edx; dwEncodingType
0x180095890  xor     r8d, r8d; hCryptProv
0x180095893  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x180095896  call    cs:__imp_CertOpenStore
0x18009589d  nop     dword ptr [rax+rax+00h]
0x1800958a2  mov     [rbx], rax
0x1800958a5  mov     rcx, rax; hCertStore
0x1800958a8  test    rax, rax
0x1800958ab  jnz     short loc_1800958C7
0x1800958ad  call    cs:__imp_GetLastError
0x1800958b4  nop     dword ptr [rax+rax+00h]
0x1800958b9  test    eax, eax
0x1800958bb  jle     short loc_1800958FC
0x1800958bd  movzx   eax, ax
0x1800958c0  or      eax, 80070000h
0x1800958c5  jmp     short loc_1800958FC
0x1800958c7  mov     rbx, [rsp+38h+arg_20]
0x1800958cc  xor     r8d, r8d; dwFindFlags
0x1800958cf  mov     r9d, 10000h; dwFindType
0x1800958d5  mov     rax, [rbx]
0x1800958d8  lea     edx, [r8+1]; dwCertEncodingType
0x1800958dc  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x1800958e1  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x1800958e6  call    cs:__imp_CertFindCertificateInStore
0x1800958ed  nop     dword ptr [rax+rax+00h]
0x1800958f2  mov     [rbx], rax
0x1800958f5  test    rax, rax
0x1800958f8  jz      short loc_1800958AD
0x1800958fa  xor     eax, eax
0x1800958fc  mov     rbx, [rsp+38h+arg_0]
0x180095901  add     rsp, 30h
0x180095905  pop     rdi
0x180095906  retn
```
