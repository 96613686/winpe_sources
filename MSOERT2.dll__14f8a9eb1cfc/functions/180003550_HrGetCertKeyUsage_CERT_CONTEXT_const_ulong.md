# HrGetCertKeyUsage(_CERT_CONTEXT const *,ulong *)

- ea: `0x180003550`
- end: `0x18000360d`
- name: `?HrGetCertKeyUsage@@YAJPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `189`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001c80`
- `0x180003530`
- `0x180003550`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x180003582`
- `CRYPT32!CertFindExtension` at `0x180003582`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800035cd`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800035cd`

## pseudocode

```c
__int64 __fastcall HrGetCertKeyUsage(const struct _CERT_CONTEXT *a1, unsigned int *a2)
{
  unsigned int LastError; // edi
  PCERT_INFO pCertInfo; // rdx
  PCERT_EXTENSION Extension; // rax
  void *v6; // rdx
  DWORD pcbStructInfo; // [rsp+50h] [rbp+8h] BYREF
  void *pvStructInfo; // [rsp+58h] [rbp+10h] BYREF

  LastError = 0;
  *a2 = 0;
  pCertInfo = a1->pCertInfo;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  Extension = CertFindExtension("2.5.29.15", pCertInfo->cExtension, pCertInfo->rgExtension);
  if ( Extension )
  {
    if ( CryptDecodeObjectEx(
           1u,
           (LPCSTR)0xE,
           Extension->Value.pbData,
           Extension->Value.cbData,
           0x8000u,
           &CryptDecodeAlloc,
           &pvStructInfo,
           &pcbStructInfo) )
    {
      v6 = pvStructInfo;
      *a2 = **((unsigned __int8 **)pvStructInfo + 1);
      goto LABEL_7;
    }
    LastError = HrGetLastError();
  }
  else
  {
    *a2 = 255;
  }
  v6 = pvStructInfo;
LABEL_7:
  if ( v6 )
    CryptFreeFunc(v6);
  return LastError;
}

```

## disassembly

```asm
0x180003550  mov     [rsp+arg_10], rbx
0x180003555  push    rdi
0x180003556  sub     rsp, 40h
0x18000355a  xor     edi, edi
0x18000355c  mov     rbx, rdx
0x18000355f  mov     [rdx], edi
0x180003561  mov     rdx, [rcx+18h]
0x180003565  lea     rcx, pszObjId; "2.5.29.15"
0x18000356c  mov     [rsp+48h+arg_8], rdi
0x180003571  mov     [rsp+48h+arg_0], edi
0x180003575  mov     r8, [rdx+0C8h]; rgExtensions
0x18000357c  mov     edx, [rdx+0C0h]; cExtensions
0x180003582  call    cs:__imp_CertFindExtension
0x180003588  test    rax, rax
0x18000358b  jnz     short loc_180003595
0x18000358d  mov     dword ptr [rbx], 0FFh
0x180003593  jmp     short loc_1800035EE
0x180003595  mov     r9d, [rax+10h]; cbEncoded
0x180003599  lea     rcx, [rsp+48h+arg_0]
0x18000359e  mov     r8, [rax+18h]; pbEncoded
0x1800035a2  mov     edx, 0Eh; lpszStructType
0x1800035a7  mov     [rsp+48h+pcbStructInfo], rcx; pcbStructInfo
0x1800035ac  lea     rcx, [rsp+48h+arg_8]
0x1800035b1  mov     [rsp+48h+pvStructInfo], rcx; pvStructInfo
0x1800035b6  lea     rcx, ?CryptDecodeAlloc@@3U_CRYPT_DECODE_PARA@@A; _CRYPT_DECODE_PARA CryptDecodeAlloc
0x1800035bd  mov     [rsp+48h+pDecodePara], rcx; pDecodePara
0x1800035c2  lea     ecx, [rdx-0Dh]; dwCertEncodingType
0x1800035c5  mov     [rsp+48h+dwFlags], 8000h; dwFlags
0x1800035cd  call    cs:__imp_CryptDecodeObjectEx
0x1800035d3  test    eax, eax
0x1800035d5  jz      short loc_1800035E7
0x1800035d7  mov     rdx, [rsp+48h+arg_8]
0x1800035dc  mov     rax, [rdx+8]
0x1800035e0  movzx   ecx, byte ptr [rax]
0x1800035e3  mov     [rbx], ecx
0x1800035e5  jmp     short loc_1800035F3
0x1800035e7  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800035ec  mov     edi, eax
0x1800035ee  mov     rdx, [rsp+48h+arg_8]
0x1800035f3  test    rdx, rdx
0x1800035f6  jz      short loc_180003600
0x1800035f8  mov     rcx, rdx; void *
0x1800035fb  call    ?CryptFreeFunc@@YAXPEAX@Z; CryptFreeFunc(void *)
0x180003600  mov     rbx, [rsp+48h+arg_10]
0x180003605  mov     eax, edi
0x180003607  add     rsp, 40h
0x18000360b  pop     rdi
0x18000360c  retn
```
