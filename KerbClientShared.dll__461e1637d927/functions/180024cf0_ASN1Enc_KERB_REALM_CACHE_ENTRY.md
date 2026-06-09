# ASN1Enc_KERB_REALM_CACHE_ENTRY

- ea: `0x180024cf0`
- end: `0x180024de1`
- name: `ASN1Enc_KERB_REALM_CACHE_ENTRY`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180024c80`

## callees

- `0x180024cf0`

## import_xrefs

- `MSASN1!ASN1DEREncGeneralizedTime` at `0x180024d9c`
- `MSASN1!ASN1DEREncGeneralizedTime` at `0x180024d9c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180024d6f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180024dad`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180024dbe`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180024d6f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180024dad`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180024dbe`
- `MSASN1!ASN1DEREncCharString` at `0x180024d5e`
- `MSASN1!ASN1DEREncCharString` at `0x180024d5e`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180024d20`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180024d46`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180024d86`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180024d20`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180024d46`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180024d86`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180024d31`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180024d31`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_REALM_CACHE_ENTRY(__int64 a1, __int64 a2, LPCSTR *a3)
{
  unsigned int v5; // esi
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  v7 = 0;
  if ( (unsigned int)ASN1BEREncExplicitTag(a1, 16, &v8)
    && (v5 = lstrlenA(*a3), (unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v7))
    && (unsigned int)ASN1DEREncCharString(a1, 27, v5, *a3)
    && (unsigned int)ASN1BEREncEndOfContents(a1, v7)
    && (unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v7)
    && (unsigned int)ASN1DEREncGeneralizedTime(a1, 24, a3 + 1)
    && (unsigned int)ASN1BEREncEndOfContents(a1, v7) )
  {
    return (unsigned int)ASN1BEREncEndOfContents(a1, v8) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180024cf0  mov     rax, rsp
0x180024cf3  mov     [rax+8], rbx
0x180024cf7  mov     [rax+18h], rsi
0x180024cfb  mov     [rax+10h], edx
0x180024cfe  push    rdi
0x180024cff  sub     rsp, 20h
0x180024d03  mov     rdi, r8
0x180024d06  mov     dword ptr [rax+20h], 0
0x180024d0d  lea     r8, [rax+20h]
0x180024d11  mov     dword ptr [rax+10h], 0
0x180024d18  mov     edx, 10h
0x180024d1d  mov     rbx, rcx
0x180024d20  call    cs:__imp_ASN1BEREncExplicitTag
0x180024d26  test    eax, eax
0x180024d28  jz      loc_180024DCF
0x180024d2e  mov     rcx, [rdi]; lpString
0x180024d31  call    cs:__imp_lstrlenA
0x180024d37  lea     r8, [rsp+28h+arg_8]
0x180024d3c  mov     edx, 80000000h
0x180024d41  mov     rcx, rbx
0x180024d44  mov     esi, eax
0x180024d46  call    cs:__imp_ASN1BEREncExplicitTag
0x180024d4c  test    eax, eax
0x180024d4e  jz      short loc_180024DCF
0x180024d50  mov     r9, [rdi]
0x180024d53  mov     r8d, esi
0x180024d56  mov     edx, 1Bh
0x180024d5b  mov     rcx, rbx
0x180024d5e  call    cs:__imp_ASN1DEREncCharString
0x180024d64  test    eax, eax
0x180024d66  jz      short loc_180024DCF
0x180024d68  mov     edx, [rsp+28h+arg_8]
0x180024d6c  mov     rcx, rbx
0x180024d6f  call    cs:__imp_ASN1BEREncEndOfContents
0x180024d75  test    eax, eax
0x180024d77  jz      short loc_180024DCF
0x180024d79  lea     r8, [rsp+28h+arg_8]
0x180024d7e  mov     edx, 80000001h
0x180024d83  mov     rcx, rbx
0x180024d86  call    cs:__imp_ASN1BEREncExplicitTag
0x180024d8c  test    eax, eax
0x180024d8e  jz      short loc_180024DCF
0x180024d90  lea     r8, [rdi+8]
0x180024d94  mov     edx, 18h
0x180024d99  mov     rcx, rbx
0x180024d9c  call    cs:__imp_ASN1DEREncGeneralizedTime
0x180024da2  test    eax, eax
0x180024da4  jz      short loc_180024DCF
0x180024da6  mov     edx, [rsp+28h+arg_8]
0x180024daa  mov     rcx, rbx
0x180024dad  call    cs:__imp_ASN1BEREncEndOfContents
0x180024db3  test    eax, eax
0x180024db5  jz      short loc_180024DCF
0x180024db7  mov     edx, [rsp+28h+arg_18]
0x180024dbb  mov     rcx, rbx
0x180024dbe  call    cs:__imp_ASN1BEREncEndOfContents
0x180024dc4  xor     ecx, ecx
0x180024dc6  test    eax, eax
0x180024dc8  setnz   cl
0x180024dcb  mov     eax, ecx
0x180024dcd  jmp     short loc_180024DD1
0x180024dcf  xor     eax, eax
0x180024dd1  mov     rbx, [rsp+28h+arg_0]
0x180024dd6  mov     rsi, [rsp+28h+arg_10]
0x180024ddb  add     rsp, 20h
0x180024ddf  pop     rdi
0x180024de0  retn
```
