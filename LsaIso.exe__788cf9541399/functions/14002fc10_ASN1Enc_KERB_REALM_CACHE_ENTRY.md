# ASN1Enc_KERB_REALM_CACHE_ENTRY

- ea: `0x14002fc10`
- end: `0x14002fd01`
- name: `ASN1Enc_KERB_REALM_CACHE_ENTRY`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002fba0`

## callees

- `0x14002fc10`

## import_xrefs

- `MSASN1!ASN1DEREncGeneralizedTime` at `0x14002fcbc`
- `MSASN1!ASN1DEREncGeneralizedTime` at `0x14002fcbc`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002fc40`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002fc66`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002fca6`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002fc40`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002fc66`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002fca6`
- `MSASN1!ASN1DEREncCharString` at `0x14002fc7e`
- `MSASN1!ASN1DEREncCharString` at `0x14002fc7e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002fc8f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002fccd`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002fcde`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002fc8f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002fccd`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002fcde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x14002fc51`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x14002fc51`

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
0x14002fc10  mov     rax, rsp
0x14002fc13  mov     [rax+8], rbx
0x14002fc17  mov     [rax+18h], rsi
0x14002fc1b  mov     [rax+10h], edx
0x14002fc1e  push    rdi
0x14002fc1f  sub     rsp, 20h
0x14002fc23  mov     rdi, r8
0x14002fc26  mov     dword ptr [rax+20h], 0
0x14002fc2d  lea     r8, [rax+20h]
0x14002fc31  mov     dword ptr [rax+10h], 0
0x14002fc38  mov     edx, 10h
0x14002fc3d  mov     rbx, rcx
0x14002fc40  call    cs:__imp_ASN1BEREncExplicitTag
0x14002fc46  test    eax, eax
0x14002fc48  jz      loc_14002FCEF
0x14002fc4e  mov     rcx, [rdi]; lpString
0x14002fc51  call    cs:__imp_lstrlenA
0x14002fc57  lea     r8, [rsp+28h+arg_8]
0x14002fc5c  mov     edx, 80000000h
0x14002fc61  mov     rcx, rbx
0x14002fc64  mov     esi, eax
0x14002fc66  call    cs:__imp_ASN1BEREncExplicitTag
0x14002fc6c  test    eax, eax
0x14002fc6e  jz      short loc_14002FCEF
0x14002fc70  mov     r9, [rdi]
0x14002fc73  mov     r8d, esi
0x14002fc76  mov     edx, 1Bh
0x14002fc7b  mov     rcx, rbx
0x14002fc7e  call    cs:__imp_ASN1DEREncCharString
0x14002fc84  test    eax, eax
0x14002fc86  jz      short loc_14002FCEF
0x14002fc88  mov     edx, [rsp+28h+arg_8]
0x14002fc8c  mov     rcx, rbx
0x14002fc8f  call    cs:__imp_ASN1BEREncEndOfContents
0x14002fc95  test    eax, eax
0x14002fc97  jz      short loc_14002FCEF
0x14002fc99  lea     r8, [rsp+28h+arg_8]
0x14002fc9e  mov     edx, 80000001h
0x14002fca3  mov     rcx, rbx
0x14002fca6  call    cs:__imp_ASN1BEREncExplicitTag
0x14002fcac  test    eax, eax
0x14002fcae  jz      short loc_14002FCEF
0x14002fcb0  lea     r8, [rdi+8]
0x14002fcb4  mov     edx, 18h
0x14002fcb9  mov     rcx, rbx
0x14002fcbc  call    cs:__imp_ASN1DEREncGeneralizedTime
0x14002fcc2  test    eax, eax
0x14002fcc4  jz      short loc_14002FCEF
0x14002fcc6  mov     edx, [rsp+28h+arg_8]
0x14002fcca  mov     rcx, rbx
0x14002fccd  call    cs:__imp_ASN1BEREncEndOfContents
0x14002fcd3  test    eax, eax
0x14002fcd5  jz      short loc_14002FCEF
0x14002fcd7  mov     edx, [rsp+28h+arg_18]
0x14002fcdb  mov     rcx, rbx
0x14002fcde  call    cs:__imp_ASN1BEREncEndOfContents
0x14002fce4  xor     ecx, ecx
0x14002fce6  test    eax, eax
0x14002fce8  setnz   cl
0x14002fceb  mov     eax, ecx
0x14002fced  jmp     short loc_14002FCF1
0x14002fcef  xor     eax, eax
0x14002fcf1  mov     rbx, [rsp+28h+arg_0]
0x14002fcf6  mov     rsi, [rsp+28h+arg_10]
0x14002fcfb  add     rsp, 20h
0x14002fcff  pop     rdi
0x14002fd00  retn
```
