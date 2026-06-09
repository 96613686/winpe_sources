# ASN1Enc_KERB_ENCRYPTED_DATA

- ea: `0x180005bc0`
- end: `0x180005d0c`
- name: `ASN1Enc_KERB_ENCRYPTED_DATA`
- size: `332`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002540`
- `0x180009728`
- `0x180021040`
- `0x180021630`
- `0x180022080`
- `0x180023850`
- `0x1800242c0`
- `0x180024b10`
- `0x180025f44`

## callees

- `0x180005bc0`

## import_xrefs

- `MSASN1!ASN1DEREncOctetString` at `0x180005c74`
- `MSASN1!ASN1DEREncOctetString` at `0x180005c74`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180005c3e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180005c89`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180005c9e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180005cf9`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180005c3e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180005c89`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180005c9e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180005cf9`
- `MSASN1!ASN1BEREncS32` at `0x180005c2d`
- `MSASN1!ASN1BEREncS32` at `0x180005ce4`
- `MSASN1!ASN1BEREncS32` at `0x180005c2d`
- `MSASN1!ASN1BEREncS32` at `0x180005ce4`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180005bee`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180005c17`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180005c5a`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180005cca`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180005bee`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180005c17`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180005c5a`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180005cca`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_ENCRYPTED_DATA(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  return (unsigned int)ASN1BEREncExplicitTag(a1, a2, &v7)
      && (unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v6)
      && (unsigned int)ASN1BEREncS32(a1, 2, *(unsigned int *)(a3 + 4))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6)
      && (*(char *)a3 >= 0
       || (unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v6)
       && (unsigned int)ASN1BEREncS32(a1, 2, *(unsigned int *)(a3 + 8))
       && (unsigned int)ASN1BEREncEndOfContents(a1, v6))
      && (unsigned int)ASN1BEREncExplicitTag(a1, 2147483650LL, &v6)
      && (unsigned int)ASN1DEREncOctetString(a1, 4, *(unsigned int *)(a3 + 16), *(_QWORD *)(a3 + 24))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v7) != 0;
}

```

## disassembly

```asm
0x180005bc0  mov     [rsp+arg_0], rbx
0x180005bc5  mov     [rsp+arg_10], rsi
0x180005bca  push    rdi
0x180005bcb  sub     rsp, 20h
0x180005bcf  xor     esi, esi
0x180005bd1  mov     eax, 10h
0x180005bd6  test    edx, edx
0x180005bd8  mov     [rsp+28h+arg_18], esi
0x180005bdc  mov     rdi, r8
0x180005bdf  mov     [rsp+28h+arg_8], esi
0x180005be3  cmovz   edx, eax
0x180005be6  lea     r8, [rsp+28h+arg_18]
0x180005beb  mov     rbx, rcx
0x180005bee  call    cs:__imp_ASN1BEREncExplicitTag
0x180005bf4  test    eax, eax
0x180005bf6  jnz     short loc_180005C0A
0x180005bf8  xor     eax, eax
0x180005bfa  mov     rbx, [rsp+28h+arg_0]
0x180005bff  mov     rsi, [rsp+28h+arg_10]
0x180005c04  add     rsp, 20h
0x180005c08  pop     rdi
0x180005c09  retn
0x180005c0a  lea     r8, [rsp+28h+arg_8]
0x180005c0f  mov     edx, 80000000h
0x180005c14  mov     rcx, rbx
0x180005c17  call    cs:__imp_ASN1BEREncExplicitTag
0x180005c1d  test    eax, eax
0x180005c1f  jz      short loc_180005BF8
0x180005c21  mov     r8d, [rdi+4]
0x180005c25  mov     edx, 2
0x180005c2a  mov     rcx, rbx
0x180005c2d  call    cs:__imp_ASN1BEREncS32
0x180005c33  test    eax, eax
0x180005c35  jz      short loc_180005BF8
0x180005c37  mov     edx, [rsp+28h+arg_8]
0x180005c3b  mov     rcx, rbx
0x180005c3e  call    cs:__imp_ASN1BEREncEndOfContents
0x180005c44  test    eax, eax
0x180005c46  jz      short loc_180005BF8
0x180005c48  cmp     [rdi], sil
0x180005c4b  jl      short loc_180005CBD
0x180005c4d  lea     r8, [rsp+28h+arg_8]
0x180005c52  mov     edx, 80000002h
0x180005c57  mov     rcx, rbx
0x180005c5a  call    cs:__imp_ASN1BEREncExplicitTag
0x180005c60  test    eax, eax
0x180005c62  jz      short loc_180005BF8
0x180005c64  mov     r9, [rdi+18h]
0x180005c68  mov     edx, 4
0x180005c6d  mov     r8d, [rdi+10h]
0x180005c71  mov     rcx, rbx
0x180005c74  call    cs:__imp_ASN1DEREncOctetString
0x180005c7a  test    eax, eax
0x180005c7c  jz      loc_180005BF8
0x180005c82  mov     edx, [rsp+28h+arg_8]
0x180005c86  mov     rcx, rbx
0x180005c89  call    cs:__imp_ASN1BEREncEndOfContents
0x180005c8f  test    eax, eax
0x180005c91  jz      loc_180005BF8
0x180005c97  mov     edx, [rsp+28h+arg_18]
0x180005c9b  mov     rcx, rbx
0x180005c9e  call    cs:__imp_ASN1BEREncEndOfContents
0x180005ca4  mov     rbx, [rsp+28h+arg_0]
0x180005ca9  mov     ecx, esi
0x180005cab  mov     rsi, [rsp+28h+arg_10]
0x180005cb0  test    eax, eax
0x180005cb2  setnz   cl
0x180005cb5  mov     eax, ecx
0x180005cb7  add     rsp, 20h
0x180005cbb  pop     rdi
0x180005cbc  retn
0x180005cbd  lea     r8, [rsp+28h+arg_8]
0x180005cc2  mov     edx, 80000001h
0x180005cc7  mov     rcx, rbx
0x180005cca  call    cs:__imp_ASN1BEREncExplicitTag
0x180005cd0  test    eax, eax
0x180005cd2  jz      loc_180005BF8
0x180005cd8  mov     r8d, [rdi+8]
0x180005cdc  mov     edx, 2
0x180005ce1  mov     rcx, rbx
0x180005ce4  call    cs:__imp_ASN1BEREncS32
0x180005cea  test    eax, eax
0x180005cec  jz      loc_180005BF8
0x180005cf2  mov     edx, [rsp+28h+arg_8]
0x180005cf6  mov     rcx, rbx
0x180005cf9  call    cs:__imp_ASN1BEREncEndOfContents
0x180005cff  test    eax, eax
0x180005d01  jnz     loc_180005C4D
0x180005d07  jmp     loc_180005BF8
```
