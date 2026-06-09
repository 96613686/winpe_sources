# ASN1Enc_KERB_PA_DATA

- ea: `0x1800023d0`
- end: `0x1800024be`
- name: `ASN1Enc_KERB_PA_DATA`
- size: `238`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021d0`
- `0x1800090e8`
- `0x180023138`
- `0x180023ccc`
- `0x1800262e4`
- `0x1800269b0`

## callees

- `0x1800023d0`

## import_xrefs

- `MSASN1!ASN1DEREncOctetString` at `0x18000247d`
- `MSASN1!ASN1DEREncOctetString` at `0x18000247d`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000244c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000248e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000249f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000244c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000248e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000249f`
- `MSASN1!ASN1BEREncS32` at `0x180002429`
- `MSASN1!ASN1BEREncS32` at `0x180002429`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800023fd`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180002414`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180002463`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800023fd`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180002414`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180002463`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_PA_DATA(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  return (unsigned int)ASN1BEREncExplicitTag(a1, 16, &v7)
      && (unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v6)
      && (unsigned int)ASN1BEREncS32(a1, 2, *a3)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6)
      && (unsigned int)ASN1BEREncExplicitTag(a1, 2147483650LL, &v6)
      && (unsigned int)ASN1DEREncOctetString(a1, 4, a3[2], *((_QWORD *)a3 + 2))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v7) != 0;
}

```

## disassembly

```asm
0x1800023d0  mov     [rsp+arg_0], rbx
0x1800023d5  mov     [rsp+arg_10], rsi
0x1800023da  mov     [rsp+arg_8], edx
0x1800023de  push    rdi
0x1800023df  sub     rsp, 20h
0x1800023e3  mov     rdi, r8
0x1800023e6  xor     esi, esi
0x1800023e8  lea     r8, [rsp+28h+arg_18]
0x1800023ed  mov     [rsp+28h+arg_18], esi
0x1800023f1  mov     edx, 10h
0x1800023f6  mov     [rsp+28h+arg_8], esi
0x1800023fa  mov     rbx, rcx
0x1800023fd  call    cs:__imp_ASN1BEREncExplicitTag
0x180002403  test    eax, eax
0x180002405  jz      short loc_180002433
0x180002407  lea     r8, [rsp+28h+arg_8]
0x18000240c  mov     edx, 80000001h
0x180002411  mov     rcx, rbx
0x180002414  call    cs:__imp_ASN1BEREncExplicitTag
0x18000241a  test    eax, eax
0x18000241c  jz      short loc_180002433
0x18000241e  mov     r8d, [rdi]
0x180002421  mov     edx, 2
0x180002426  mov     rcx, rbx
0x180002429  call    cs:__imp_ASN1BEREncS32
0x18000242f  test    eax, eax
0x180002431  jnz     short loc_180002445
0x180002433  xor     eax, eax
0x180002435  mov     rbx, [rsp+28h+arg_0]
0x18000243a  mov     rsi, [rsp+28h+arg_10]
0x18000243f  add     rsp, 20h
0x180002443  pop     rdi
0x180002444  retn
0x180002445  mov     edx, [rsp+28h+arg_8]
0x180002449  mov     rcx, rbx
0x18000244c  call    cs:__imp_ASN1BEREncEndOfContents
0x180002452  test    eax, eax
0x180002454  jz      short loc_180002433
0x180002456  lea     r8, [rsp+28h+arg_8]
0x18000245b  mov     edx, 80000002h
0x180002460  mov     rcx, rbx
0x180002463  call    cs:__imp_ASN1BEREncExplicitTag
0x180002469  test    eax, eax
0x18000246b  jz      short loc_180002433
0x18000246d  mov     r9, [rdi+10h]
0x180002471  mov     edx, 4
0x180002476  mov     r8d, [rdi+8]
0x18000247a  mov     rcx, rbx
0x18000247d  call    cs:__imp_ASN1DEREncOctetString
0x180002483  test    eax, eax
0x180002485  jz      short loc_180002433
0x180002487  mov     edx, [rsp+28h+arg_8]
0x18000248b  mov     rcx, rbx
0x18000248e  call    cs:__imp_ASN1BEREncEndOfContents
0x180002494  test    eax, eax
0x180002496  jz      short loc_180002433
0x180002498  mov     edx, [rsp+28h+arg_18]
0x18000249c  mov     rcx, rbx
0x18000249f  call    cs:__imp_ASN1BEREncEndOfContents
0x1800024a5  mov     rbx, [rsp+28h+arg_0]
0x1800024aa  mov     ecx, esi
0x1800024ac  mov     rsi, [rsp+28h+arg_10]
0x1800024b1  test    eax, eax
0x1800024b3  setnz   cl
0x1800024b6  mov     eax, ecx
0x1800024b8  add     rsp, 20h
0x1800024bc  pop     rdi
0x1800024bd  retn
```
