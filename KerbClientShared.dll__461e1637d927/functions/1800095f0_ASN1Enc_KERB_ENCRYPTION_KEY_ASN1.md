# ASN1Enc_KERB_ENCRYPTION_KEY_ASN1

- ea: `0x1800095f0`
- end: `0x1800096d5`
- name: `ASN1Enc_KERB_ENCRYPTION_KEY_ASN1`
- size: `229`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180006170`
- `0x180021830`
- `0x1800221f4`
- `0x1800228a4`
- `0x180022944`
- `0x180022d14`
- `0x1800234a0`
- `0x180023e60`
- `0x180024df0`
- `0x180024ed0`
- `0x180025010`
- `0x1800261a0`

## callees

- `0x1800095f0`

## import_xrefs

- `MSASN1!ASN1DEREncOctetString` at `0x180009695`
- `MSASN1!ASN1DEREncOctetString` at `0x180009695`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180009664`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800096a6`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800096b7`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180009664`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800096a6`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800096b7`
- `MSASN1!ASN1BEREncS32` at `0x180009653`
- `MSASN1!ASN1BEREncS32` at `0x180009653`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000961f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000963a`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000967b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000961f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000963a`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000967b`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_ENCRYPTION_KEY_ASN1(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  return (unsigned int)ASN1BEREncExplicitTag(a1, a2, &v7)
      && (unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v6)
      && (unsigned int)ASN1BEREncS32(a1, 2, *a3)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6)
      && (unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v6)
      && (unsigned int)ASN1DEREncOctetString(a1, 4, a3[2], *((_QWORD *)a3 + 2))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v7) != 0;
}

```

## disassembly

```asm
0x1800095f0  mov     [rsp+arg_0], rbx
0x1800095f5  push    rdi
0x1800095f6  sub     rsp, 20h
0x1800095fa  test    edx, edx
0x1800095fc  mov     [rsp+28h+arg_18], 0
0x180009604  mov     eax, 10h
0x180009609  mov     [rsp+28h+arg_8], 0
0x180009611  mov     rdi, r8
0x180009614  cmovz   edx, eax
0x180009617  lea     r8, [rsp+28h+arg_18]
0x18000961c  mov     rbx, rcx
0x18000961f  call    cs:__imp_ASN1BEREncExplicitTag
0x180009625  test    eax, eax
0x180009627  jz      loc_1800096C8
0x18000962d  lea     r8, [rsp+28h+arg_8]
0x180009632  mov     edx, 80000000h
0x180009637  mov     rcx, rbx
0x18000963a  call    cs:__imp_ASN1BEREncExplicitTag
0x180009640  test    eax, eax
0x180009642  jz      loc_1800096C8
0x180009648  mov     r8d, [rdi]
0x18000964b  mov     edx, 2
0x180009650  mov     rcx, rbx
0x180009653  call    cs:__imp_ASN1BEREncS32
0x180009659  test    eax, eax
0x18000965b  jz      short loc_1800096C8
0x18000965d  mov     edx, [rsp+28h+arg_8]
0x180009661  mov     rcx, rbx
0x180009664  call    cs:__imp_ASN1BEREncEndOfContents
0x18000966a  test    eax, eax
0x18000966c  jz      short loc_1800096C8
0x18000966e  lea     r8, [rsp+28h+arg_8]
0x180009673  mov     edx, 80000001h
0x180009678  mov     rcx, rbx
0x18000967b  call    cs:__imp_ASN1BEREncExplicitTag
0x180009681  test    eax, eax
0x180009683  jz      short loc_1800096C8
0x180009685  mov     r9, [rdi+10h]
0x180009689  mov     edx, 4
0x18000968e  mov     r8d, [rdi+8]
0x180009692  mov     rcx, rbx
0x180009695  call    cs:__imp_ASN1DEREncOctetString
0x18000969b  test    eax, eax
0x18000969d  jz      short loc_1800096C8
0x18000969f  mov     edx, [rsp+28h+arg_8]
0x1800096a3  mov     rcx, rbx
0x1800096a6  call    cs:__imp_ASN1BEREncEndOfContents
0x1800096ac  test    eax, eax
0x1800096ae  jz      short loc_1800096C8
0x1800096b0  mov     edx, [rsp+28h+arg_18]
0x1800096b4  mov     rcx, rbx
0x1800096b7  call    cs:__imp_ASN1BEREncEndOfContents
0x1800096bd  xor     ecx, ecx
0x1800096bf  test    eax, eax
0x1800096c1  setnz   cl
0x1800096c4  mov     eax, ecx
0x1800096c6  jmp     short loc_1800096CA
0x1800096c8  xor     eax, eax
0x1800096ca  mov     rbx, [rsp+28h+arg_0]
0x1800096cf  add     rsp, 20h
0x1800096d3  pop     rdi
0x1800096d4  retn
```
