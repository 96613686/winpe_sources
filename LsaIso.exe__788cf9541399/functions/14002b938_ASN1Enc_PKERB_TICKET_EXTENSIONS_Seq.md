# ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq

- ea: `0x14002b938`
- end: `0x14002ba1a`
- name: `ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq`
- size: `226`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14002c720`
- `0x14002cfe0`
- `0x14002d2a0`
- `0x14002f1b4`
- `0x14002f4c0`
- `0x14003000c`
- `0x140030da0`
- `0x140031220`
- `0x140031cc8`
- `0x140031dd0`

## callees

- `0x14002b938`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x14002b964`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002b97f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002b9c0`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002b964`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002b97f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002b9c0`
- `MSASN1!ASN1BEREncS32` at `0x14002b998`
- `MSASN1!ASN1BEREncS32` at `0x14002b998`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002b9a9`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002b9eb`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002b9fc`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002b9a9`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002b9eb`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002b9fc`
- `MSASN1!ASN1DEREncOctetString` at `0x14002b9da`
- `MSASN1!ASN1DEREncOctetString` at `0x14002b9da`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  return (unsigned int)ASN1BEREncExplicitTag(a1, 16, &v7)
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
0x14002b938  mov     rax, rsp
0x14002b93b  mov     [rax+8], rbx
0x14002b93f  mov     [rax+10h], edx
0x14002b942  push    rdi
0x14002b943  sub     rsp, 20h
0x14002b947  mov     rdi, r8
0x14002b94a  mov     dword ptr [rax+20h], 0
0x14002b951  lea     r8, [rax+20h]
0x14002b955  mov     dword ptr [rax+10h], 0
0x14002b95c  mov     edx, 10h
0x14002b961  mov     rbx, rcx
0x14002b964  call    cs:__imp_ASN1BEREncExplicitTag
0x14002b96a  test    eax, eax
0x14002b96c  jz      loc_14002BA0D
0x14002b972  lea     r8, [rsp+28h+arg_8]
0x14002b977  mov     edx, 80000000h
0x14002b97c  mov     rcx, rbx
0x14002b97f  call    cs:__imp_ASN1BEREncExplicitTag
0x14002b985  test    eax, eax
0x14002b987  jz      loc_14002BA0D
0x14002b98d  mov     r8d, [rdi]
0x14002b990  mov     edx, 2
0x14002b995  mov     rcx, rbx
0x14002b998  call    cs:__imp_ASN1BEREncS32
0x14002b99e  test    eax, eax
0x14002b9a0  jz      short loc_14002BA0D
0x14002b9a2  mov     edx, [rsp+28h+arg_8]
0x14002b9a6  mov     rcx, rbx
0x14002b9a9  call    cs:__imp_ASN1BEREncEndOfContents
0x14002b9af  test    eax, eax
0x14002b9b1  jz      short loc_14002BA0D
0x14002b9b3  lea     r8, [rsp+28h+arg_8]
0x14002b9b8  mov     edx, 80000001h
0x14002b9bd  mov     rcx, rbx
0x14002b9c0  call    cs:__imp_ASN1BEREncExplicitTag
0x14002b9c6  test    eax, eax
0x14002b9c8  jz      short loc_14002BA0D
0x14002b9ca  mov     r9, [rdi+10h]
0x14002b9ce  mov     edx, 4
0x14002b9d3  mov     r8d, [rdi+8]
0x14002b9d7  mov     rcx, rbx
0x14002b9da  call    cs:__imp_ASN1DEREncOctetString
0x14002b9e0  test    eax, eax
0x14002b9e2  jz      short loc_14002BA0D
0x14002b9e4  mov     edx, [rsp+28h+arg_8]
0x14002b9e8  mov     rcx, rbx
0x14002b9eb  call    cs:__imp_ASN1BEREncEndOfContents
0x14002b9f1  test    eax, eax
0x14002b9f3  jz      short loc_14002BA0D
0x14002b9f5  mov     edx, [rsp+28h+arg_18]
0x14002b9f9  mov     rcx, rbx
0x14002b9fc  call    cs:__imp_ASN1BEREncEndOfContents
0x14002ba02  xor     ecx, ecx
0x14002ba04  test    eax, eax
0x14002ba06  setnz   cl
0x14002ba09  mov     eax, ecx
0x14002ba0b  jmp     short loc_14002BA0F
0x14002ba0d  xor     eax, eax
0x14002ba0f  mov     rbx, [rsp+28h+arg_0]
0x14002ba14  add     rsp, 20h
0x14002ba18  pop     rdi
0x14002ba19  retn
```
