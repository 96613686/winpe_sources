# KerbGetCertificateTemplateName(_CERT_CONTEXT const *,_UNICODE_STRING *)

- ea: `0x180075e04`
- end: `0x180075f7e`
- name: `?KerbGetCertificateTemplateName@@YAJPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@@Z`
- size: `378`
- prototype: `int(const struct _CERT_CONTEXT *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800534a0`

## callees

- `0x180075e04`
- `0x18007c4d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075f57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075f66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075f57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075f66`
- `CRYPT32!CryptFindOIDInfo` at `0x180075ea5`
- `CRYPT32!CryptFindOIDInfo` at `0x180075ea5`
- `CRYPT32!CertFindExtension` at `0x180075e4b`
- `CRYPT32!CertFindExtension` at `0x180075edc`
- `CRYPT32!CertFindExtension` at `0x180075e4b`
- `CRYPT32!CertFindExtension` at `0x180075edc`
- `CRYPT32!CryptDecodeObjectEx` at `0x180075e83`
- `CRYPT32!CryptDecodeObjectEx` at `0x180075f16`
- `CRYPT32!CryptDecodeObjectEx` at `0x180075e83`
- `CRYPT32!CryptDecodeObjectEx` at `0x180075f16`
- `ntdll!RtlInitUnicodeString` at `0x180075ebc`
- `ntdll!RtlInitUnicodeString` at `0x180075ebc`

## pseudocode

```c
__int64 __fastcall KerbGetCertificateTemplateName(const struct _CERT_CONTEXT *a1, struct _UNICODE_STRING *a2)
{
  unsigned int v2; // ebx
  PCERT_INFO pCertInfo; // rdx
  PCERT_EXTENSION Extension; // rax
  PCCRYPT_OID_INFO OIDInfo; // rax
  unsigned __int8 v8; // r8
  PCERT_EXTENSION v9; // rax
  HLOCAL pvStructInfo; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  DWORD pcbStructInfo; // [rsp+80h] [rbp+20h] BYREF
  DWORD v14; // [rsp+90h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+38h] BYREF

  v2 = 0;
  *a2 = 0;
  pvStructInfo = 0;
  pCertInfo = a1->pCertInfo;
  pcbStructInfo = 0;
  DestinationString = 0;
  hMem = 0;
  v14 = 0;
  Extension = CertFindExtension("1.3.6.1.4.1.311.21.7", pCertInfo->cExtension, pCertInfo->rgExtension);
  if ( !Extension )
  {
    v9 = CertFindExtension("1.3.6.1.4.1.311.20.2", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
    if ( !v9 )
      goto LABEL_10;
    if ( !CryptDecodeObjectEx(1u, (LPCSTR)0x18, v9->Value.pbData, v9->Value.cbData, 0x8000u, 0, &hMem, &v14) )
      goto LABEL_3;
    DestinationString.Length = *((_WORD *)hMem + 4);
    DestinationString.MaximumLength = *((_WORD *)hMem + 4);
    DestinationString.Buffer = (PWSTR)*((_QWORD *)hMem + 2);
    goto LABEL_9;
  }
  if ( !CryptDecodeObjectEx(
          1u,
          (LPCSTR)0x40,
          Extension->Value.pbData,
          Extension->Value.cbData,
          0x8000u,
          0,
          &pvStructInfo,
          &pcbStructInfo) )
  {
LABEL_3:
    v2 = -1073741801;
    goto LABEL_10;
  }
  OIDInfo = CryptFindOIDInfo(1u, *(void **)pvStructInfo, 0);
  if ( OIDInfo )
  {
    RtlInitUnicodeString(&DestinationString, OIDInfo->pwszName);
LABEL_9:
    v2 = KerbDuplicateStringEx(a2, &DestinationString, v8);
  }
LABEL_10:
  if ( hMem )
    LocalFree(hMem);
  if ( pvStructInfo )
    LocalFree(pvStructInfo);
  return v2;
}

```

## disassembly

```asm
0x180075e04  mov     [rsp-18h+arg_8], rbx
0x180075e09  push    rbp
0x180075e0a  push    rsi
0x180075e0b  push    rdi
0x180075e0c  mov     rbp, rsp
0x180075e0f  sub     rsp, 60h
0x180075e13  xor     ebx, ebx
0x180075e15  xorps   xmm0, xmm0
0x180075e18  movups  xmmword ptr [rdx], xmm0
0x180075e1b  mov     rdi, rdx
0x180075e1e  mov     [rbp+var_20], rbx
0x180075e22  mov     rdx, [rcx+18h]
0x180075e26  mov     rsi, rcx
0x180075e29  mov     [rbp+arg_0], ebx
0x180075e2c  lea     rcx, a136141311217; "1.3.6.1.4.1.311.21.7"
0x180075e33  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180075e37  mov     [rbp+hMem], rbx
0x180075e3b  mov     [rbp+arg_10], ebx
0x180075e3e  mov     r8, [rdx+0C8h]; rgExtensions
0x180075e45  mov     edx, [rdx+0C0h]; cExtensions
0x180075e4b  call    cs:__imp_CertFindExtension
0x180075e51  test    rax, rax
0x180075e54  jz      short loc_180075EC4
0x180075e56  mov     r9d, [rax+10h]; cbEncoded
0x180075e5a  lea     rcx, [rbp+arg_0]
0x180075e5e  mov     r8, [rax+18h]; pbEncoded
0x180075e62  lea     edx, [rbx+40h]; lpszStructType
0x180075e65  mov     [rsp+60h+pcbStructInfo], rcx; pcbStructInfo
0x180075e6a  lea     rcx, [rbp+var_20]
0x180075e6e  mov     [rsp+60h+pvStructInfo], rcx; pvStructInfo
0x180075e73  lea     ecx, [rbx+1]; dwCertEncodingType
0x180075e76  mov     [rsp+60h+pDecodePara], rbx; pDecodePara
0x180075e7b  mov     [rsp+60h+dwFlags], 8000h; dwFlags
0x180075e83  call    cs:__imp_CryptDecodeObjectEx
0x180075e89  test    eax, eax
0x180075e8b  jnz     short loc_180075E97
0x180075e8d  mov     ebx, 0C0000017h
0x180075e92  jmp     loc_180075F4E
0x180075e97  mov     rdx, [rbp+var_20]
0x180075e9b  xor     r8d, r8d; dwGroupId
0x180075e9e  mov     rdx, [rdx]; pvKey
0x180075ea1  lea     ecx, [r8+1]; dwKeyType
0x180075ea5  call    cs:__imp_CryptFindOIDInfo
0x180075eab  test    rax, rax
0x180075eae  jz      loc_180075F4E
0x180075eb4  mov     rdx, [rax+10h]; SourceString
0x180075eb8  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075ebc  call    cs:__imp_RtlInitUnicodeString
0x180075ec2  jmp     short loc_180075F40
0x180075ec4  mov     rdx, [rsi+18h]
0x180075ec8  lea     rcx, a136141311202; "1.3.6.1.4.1.311.20.2"
0x180075ecf  mov     r8, [rdx+0C8h]; rgExtensions
0x180075ed6  mov     edx, [rdx+0C0h]; cExtensions
0x180075edc  call    cs:__imp_CertFindExtension
0x180075ee2  test    rax, rax
0x180075ee5  jz      short loc_180075F4E
0x180075ee7  mov     r9d, [rax+10h]; cbEncoded
0x180075eeb  lea     rcx, [rbp+arg_10]
0x180075eef  mov     r8, [rax+18h]; pbEncoded
0x180075ef3  mov     edx, 18h; lpszStructType
0x180075ef8  mov     [rsp+60h+pcbStructInfo], rcx; pcbStructInfo
0x180075efd  lea     rcx, [rbp+hMem]
0x180075f01  mov     [rsp+60h+pvStructInfo], rcx; pvStructInfo
0x180075f06  mov     [rsp+60h+pDecodePara], rbx; pDecodePara
0x180075f0b  lea     ecx, [rdx-17h]; dwCertEncodingType
0x180075f0e  mov     [rsp+60h+dwFlags], 8000h; dwFlags
0x180075f16  call    cs:__imp_CryptDecodeObjectEx
0x180075f1c  test    eax, eax
0x180075f1e  jz      loc_180075E8D
0x180075f24  mov     rcx, [rbp+hMem]
0x180075f28  movzx   eax, word ptr [rcx+8]
0x180075f2c  mov     [rbp+DestinationString.Length], ax
0x180075f30  movzx   eax, word ptr [rcx+8]
0x180075f34  mov     [rbp+DestinationString.MaximumLength], ax
0x180075f38  mov     rax, [rcx+10h]
0x180075f3c  mov     [rbp+DestinationString.Buffer], rax
0x180075f40  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180075f44  mov     rcx, rdi; struct _UNICODE_STRING *
0x180075f47  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180075f4c  mov     ebx, eax
0x180075f4e  mov     rcx, [rbp+hMem]; hMem
0x180075f52  test    rcx, rcx
0x180075f55  jz      short loc_180075F5D
0x180075f57  call    cs:__imp_LocalFree
0x180075f5d  mov     rcx, [rbp+var_20]; hMem
0x180075f61  test    rcx, rcx
0x180075f64  jz      short loc_180075F6C
0x180075f66  call    cs:__imp_LocalFree
0x180075f6c  mov     eax, ebx
0x180075f6e  mov     rbx, [rsp+60h+arg_8]
0x180075f76  add     rsp, 60h
0x180075f7a  pop     rdi
0x180075f7b  pop     rsi
0x180075f7c  pop     rbp
0x180075f7d  retn
```
