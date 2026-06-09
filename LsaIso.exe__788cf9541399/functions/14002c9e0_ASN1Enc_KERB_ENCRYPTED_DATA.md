# ASN1Enc_KERB_ENCRYPTED_DATA

- ea: `0x14002c9e0`
- end: `0x14002cb15`
- name: `ASN1Enc_KERB_ENCRYPTED_DATA`
- size: `309`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14002a800`
- `0x14002aee0`
- `0x14002b050`
- `0x14002bb80`
- `0x14002d740`
- `0x14002e0b8`
- `0x14002e4b0`
- `0x14002f070`
- `0x14002fa30`
- `0x140030da0`
- `0x140031184`
- `0x140031220`

## callees

- `0x14002c9e0`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ca0f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ca2a`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ca79`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002cabb`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ca0f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ca2a`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ca79`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002cabb`
- `MSASN1!ASN1BEREncS32` at `0x14002ca44`
- `MSASN1!ASN1BEREncS32` at `0x14002ca93`
- `MSASN1!ASN1BEREncS32` at `0x14002ca44`
- `MSASN1!ASN1BEREncS32` at `0x14002ca93`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002ca59`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002caa4`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002cae6`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002caf7`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002ca59`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002caa4`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002cae6`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002caf7`
- `MSASN1!ASN1DEREncOctetString` at `0x14002cad5`
- `MSASN1!ASN1DEREncOctetString` at `0x14002cad5`

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
0x14002c9e0  mov     [rsp+arg_0], rbx
0x14002c9e5  push    rdi
0x14002c9e6  sub     rsp, 20h
0x14002c9ea  test    edx, edx
0x14002c9ec  mov     [rsp+28h+arg_18], 0
0x14002c9f4  mov     eax, 10h
0x14002c9f9  mov     [rsp+28h+arg_8], 0
0x14002ca01  mov     rdi, r8
0x14002ca04  cmovz   edx, eax
0x14002ca07  lea     r8, [rsp+28h+arg_18]
0x14002ca0c  mov     rbx, rcx
0x14002ca0f  call    cs:__imp_ASN1BEREncExplicitTag
0x14002ca15  test    eax, eax
0x14002ca17  jz      loc_14002CB08
0x14002ca1d  lea     r8, [rsp+28h+arg_8]
0x14002ca22  mov     edx, 80000000h
0x14002ca27  mov     rcx, rbx
0x14002ca2a  call    cs:__imp_ASN1BEREncExplicitTag
0x14002ca30  test    eax, eax
0x14002ca32  jz      loc_14002CB08
0x14002ca38  mov     r8d, [rdi+4]
0x14002ca3c  mov     edx, 2
0x14002ca41  mov     rcx, rbx
0x14002ca44  call    cs:__imp_ASN1BEREncS32
0x14002ca4a  test    eax, eax
0x14002ca4c  jz      loc_14002CB08
0x14002ca52  mov     edx, [rsp+28h+arg_8]
0x14002ca56  mov     rcx, rbx
0x14002ca59  call    cs:__imp_ASN1BEREncEndOfContents
0x14002ca5f  test    eax, eax
0x14002ca61  jz      loc_14002CB08
0x14002ca67  cmp     byte ptr [rdi], 0
0x14002ca6a  jge     short loc_14002CAAE
0x14002ca6c  lea     r8, [rsp+28h+arg_8]
0x14002ca71  mov     edx, 80000001h
0x14002ca76  mov     rcx, rbx
0x14002ca79  call    cs:__imp_ASN1BEREncExplicitTag
0x14002ca7f  test    eax, eax
0x14002ca81  jz      loc_14002CB08
0x14002ca87  mov     r8d, [rdi+8]
0x14002ca8b  mov     edx, 2
0x14002ca90  mov     rcx, rbx
0x14002ca93  call    cs:__imp_ASN1BEREncS32
0x14002ca99  test    eax, eax
0x14002ca9b  jz      short loc_14002CB08
0x14002ca9d  mov     edx, [rsp+28h+arg_8]
0x14002caa1  mov     rcx, rbx
0x14002caa4  call    cs:__imp_ASN1BEREncEndOfContents
0x14002caaa  test    eax, eax
0x14002caac  jz      short loc_14002CB08
0x14002caae  lea     r8, [rsp+28h+arg_8]
0x14002cab3  mov     edx, 80000002h
0x14002cab8  mov     rcx, rbx
0x14002cabb  call    cs:__imp_ASN1BEREncExplicitTag
0x14002cac1  test    eax, eax
0x14002cac3  jz      short loc_14002CB08
0x14002cac5  mov     r9, [rdi+18h]
0x14002cac9  mov     edx, 4
0x14002cace  mov     r8d, [rdi+10h]
0x14002cad2  mov     rcx, rbx
0x14002cad5  call    cs:__imp_ASN1DEREncOctetString
0x14002cadb  test    eax, eax
0x14002cadd  jz      short loc_14002CB08
0x14002cadf  mov     edx, [rsp+28h+arg_8]
0x14002cae3  mov     rcx, rbx
0x14002cae6  call    cs:__imp_ASN1BEREncEndOfContents
0x14002caec  test    eax, eax
0x14002caee  jz      short loc_14002CB08
0x14002caf0  mov     edx, [rsp+28h+arg_18]
0x14002caf4  mov     rcx, rbx
0x14002caf7  call    cs:__imp_ASN1BEREncEndOfContents
0x14002cafd  xor     ecx, ecx
0x14002caff  test    eax, eax
0x14002cb01  setnz   cl
0x14002cb04  mov     eax, ecx
0x14002cb06  jmp     short loc_14002CB0A
0x14002cb08  xor     eax, eax
0x14002cb0a  mov     rbx, [rsp+28h+arg_0]
0x14002cb0f  add     rsp, 20h
0x14002cb13  pop     rdi
0x14002cb14  retn
```
