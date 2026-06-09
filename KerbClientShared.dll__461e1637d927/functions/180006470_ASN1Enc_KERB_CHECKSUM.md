# ASN1Enc_KERB_CHECKSUM

- ea: `0x180006470`
- end: `0x180006563`
- name: `ASN1Enc_KERB_CHECKSUM`
- size: `243`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180009728`
- `0x180021110`
- `0x180021830`
- `0x180023ee0`
- `0x180025010`
- `0x180025300`
- `0x180025fe0`
- `0x1800264e0`

## callees

- `0x180006470`

## import_xrefs

- `MSASN1!ASN1DEREncOctetString` at `0x18000651e`
- `MSASN1!ASN1DEREncOctetString` at `0x18000651e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800064ed`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000652f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180006544`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800064ed`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000652f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180006544`
- `MSASN1!ASN1BEREncS32` at `0x1800064dc`
- `MSASN1!ASN1BEREncS32` at `0x1800064dc`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000649e`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800064c7`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180006504`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000649e`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800064c7`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180006504`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_CHECKSUM(__int64 a1, __int64 a2, unsigned int *a3)
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
0x180006470  mov     [rsp+arg_0], rbx
0x180006475  mov     [rsp+arg_10], rsi
0x18000647a  push    rdi
0x18000647b  sub     rsp, 20h
0x18000647f  xor     esi, esi
0x180006481  mov     eax, 10h
0x180006486  test    edx, edx
0x180006488  mov     [rsp+28h+arg_18], esi
0x18000648c  mov     rdi, r8
0x18000648f  mov     [rsp+28h+arg_8], esi
0x180006493  cmovz   edx, eax
0x180006496  lea     r8, [rsp+28h+arg_18]
0x18000649b  mov     rbx, rcx
0x18000649e  call    cs:__imp_ASN1BEREncExplicitTag
0x1800064a4  test    eax, eax
0x1800064a6  jnz     short loc_1800064BA
0x1800064a8  xor     eax, eax
0x1800064aa  mov     rbx, [rsp+28h+arg_0]
0x1800064af  mov     rsi, [rsp+28h+arg_10]
0x1800064b4  add     rsp, 20h
0x1800064b8  pop     rdi
0x1800064b9  retn
0x1800064ba  lea     r8, [rsp+28h+arg_8]
0x1800064bf  mov     edx, 80000000h
0x1800064c4  mov     rcx, rbx
0x1800064c7  call    cs:__imp_ASN1BEREncExplicitTag
0x1800064cd  test    eax, eax
0x1800064cf  jz      short loc_1800064A8
0x1800064d1  mov     r8d, [rdi]
0x1800064d4  mov     edx, 2
0x1800064d9  mov     rcx, rbx
0x1800064dc  call    cs:__imp_ASN1BEREncS32
0x1800064e2  test    eax, eax
0x1800064e4  jz      short loc_1800064A8
0x1800064e6  mov     edx, [rsp+28h+arg_8]
0x1800064ea  mov     rcx, rbx
0x1800064ed  call    cs:__imp_ASN1BEREncEndOfContents
0x1800064f3  test    eax, eax
0x1800064f5  jz      short loc_1800064A8
0x1800064f7  lea     r8, [rsp+28h+arg_8]
0x1800064fc  mov     edx, 80000001h
0x180006501  mov     rcx, rbx
0x180006504  call    cs:__imp_ASN1BEREncExplicitTag
0x18000650a  test    eax, eax
0x18000650c  jz      short loc_1800064A8
0x18000650e  mov     r9, [rdi+10h]
0x180006512  mov     edx, 4
0x180006517  mov     r8d, [rdi+8]
0x18000651b  mov     rcx, rbx
0x18000651e  call    cs:__imp_ASN1DEREncOctetString
0x180006524  test    eax, eax
0x180006526  jz      short loc_1800064A8
0x180006528  mov     edx, [rsp+28h+arg_8]
0x18000652c  mov     rcx, rbx
0x18000652f  call    cs:__imp_ASN1BEREncEndOfContents
0x180006535  test    eax, eax
0x180006537  jz      loc_1800064A8
0x18000653d  mov     edx, [rsp+28h+arg_18]
0x180006541  mov     rcx, rbx
0x180006544  call    cs:__imp_ASN1BEREncEndOfContents
0x18000654a  mov     rbx, [rsp+28h+arg_0]
0x18000654f  mov     ecx, esi
0x180006551  mov     rsi, [rsp+28h+arg_10]
0x180006556  test    eax, eax
0x180006558  setnz   cl
0x18000655b  mov     eax, ecx
0x18000655d  add     rsp, 20h
0x180006561  pop     rdi
0x180006562  retn
```
