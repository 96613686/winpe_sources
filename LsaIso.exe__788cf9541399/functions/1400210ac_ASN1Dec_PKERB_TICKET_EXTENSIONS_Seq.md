# ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq

- ea: `0x1400210ac`
- end: `0x1400211c0`
- name: `ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq`
- size: `276`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400224e0`
- `0x1400230a0`
- `0x140023440`
- `0x140025e04`
- `0x140026318`
- `0x140027288`
- `0x1400299cc`
- `0x140029ba8`

## callees

- `0x1400210ac`

## import_xrefs

- `MSASN1!ASN1BERDecOctetString` at `0x140021172`
- `MSASN1!ASN1BERDecOctetString` at `0x140021172`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1400210f1`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140021110`
- `MSASN1!ASN1BERDecExplicitTag` at `0x14002115b`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1400210f1`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140021110`
- `MSASN1!ASN1BERDecExplicitTag` at `0x14002115b`
- `MSASN1!ASN1BERDecS32Val` at `0x14002112a`
- `MSASN1!ASN1BERDecS32Val` at `0x14002112a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021140`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021188`
- `MSASN1!ASN1BERDecEndOfContents` at `0x14002119d`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021140`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021188`
- `MSASN1!ASN1BERDecEndOfContents` at `0x14002119d`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // [rsp+20h] [rbp-20h] BYREF
  __int64 v7; // [rsp+28h] [rbp-18h] BYREF
  __int64 v8; // [rsp+30h] [rbp-10h] BYREF
  __int64 v9; // [rsp+68h] [rbp+28h] BYREF

  v6 = 0;
  v8 = 0;
  v9 = 0;
  v7 = 0;
  return (unsigned int)ASN1BERDecExplicitTag(a1, 16, &v6, &v8)
      && (unsigned int)ASN1BERDecExplicitTag(v6, 0x80000000LL, &v9, &v7)
      && (unsigned int)ASN1BERDecS32Val(v9, 2, a3)
      && (unsigned int)ASN1BERDecEndOfContents(v6, v9, v7)
      && (unsigned int)ASN1BERDecExplicitTag(v6, 2147483649LL, &v9, &v7)
      && (unsigned int)ASN1BERDecOctetString(v9, 4, a3 + 8)
      && (unsigned int)ASN1BERDecEndOfContents(v6, v9, v7)
      && (unsigned int)ASN1BERDecEndOfContents(a1, v6, v8) != 0;
}

```

## disassembly

```asm
0x1400210ac  mov     [rsp-8+arg_0], rbx
0x1400210b1  mov     [rsp-8+arg_8], rdi
0x1400210b6  push    rbp
0x1400210b7  mov     rbp, rsp
0x1400210ba  sub     rsp, 40h
0x1400210be  mov     rbx, r8
0x1400210c1  mov     [rbp+var_20], 0
0x1400210c9  lea     r8, [rbp+var_20]
0x1400210cd  mov     [rbp+var_10], 0
0x1400210d5  lea     r9, [rbp+var_10]
0x1400210d9  mov     [rbp+arg_18], 0
0x1400210e1  mov     edx, 10h
0x1400210e6  mov     [rbp+var_18], 0
0x1400210ee  mov     rdi, rcx
0x1400210f1  call    cs:__imp_ASN1BERDecExplicitTag
0x1400210f7  test    eax, eax
0x1400210f9  jz      loc_1400211AE
0x1400210ff  mov     rcx, [rbp+var_20]
0x140021103  lea     r9, [rbp+var_18]
0x140021107  lea     r8, [rbp+arg_18]
0x14002110b  mov     edx, 80000000h
0x140021110  call    cs:__imp_ASN1BERDecExplicitTag
0x140021116  test    eax, eax
0x140021118  jz      loc_1400211AE
0x14002111e  mov     rcx, [rbp+arg_18]
0x140021122  mov     r8, rbx
0x140021125  mov     edx, 2
0x14002112a  call    cs:__imp_ASN1BERDecS32Val
0x140021130  test    eax, eax
0x140021132  jz      short loc_1400211AE
0x140021134  mov     r8, [rbp+var_18]
0x140021138  mov     rdx, [rbp+arg_18]
0x14002113c  mov     rcx, [rbp+var_20]
0x140021140  call    cs:__imp_ASN1BERDecEndOfContents
0x140021146  test    eax, eax
0x140021148  jz      short loc_1400211AE
0x14002114a  mov     rcx, [rbp+var_20]
0x14002114e  lea     r9, [rbp+var_18]
0x140021152  lea     r8, [rbp+arg_18]
0x140021156  mov     edx, 80000001h
0x14002115b  call    cs:__imp_ASN1BERDecExplicitTag
0x140021161  test    eax, eax
0x140021163  jz      short loc_1400211AE
0x140021165  mov     rcx, [rbp+arg_18]
0x140021169  lea     r8, [rbx+8]
0x14002116d  mov     edx, 4
0x140021172  call    cs:__imp_ASN1BERDecOctetString
0x140021178  test    eax, eax
0x14002117a  jz      short loc_1400211AE
0x14002117c  mov     r8, [rbp+var_18]
0x140021180  mov     rdx, [rbp+arg_18]
0x140021184  mov     rcx, [rbp+var_20]
0x140021188  call    cs:__imp_ASN1BERDecEndOfContents
0x14002118e  test    eax, eax
0x140021190  jz      short loc_1400211AE
0x140021192  mov     r8, [rbp+var_10]
0x140021196  mov     rcx, rdi
0x140021199  mov     rdx, [rbp+var_20]
0x14002119d  call    cs:__imp_ASN1BERDecEndOfContents
0x1400211a3  xor     ecx, ecx
0x1400211a5  test    eax, eax
0x1400211a7  setnz   cl
0x1400211aa  mov     eax, ecx
0x1400211ac  jmp     short loc_1400211B0
0x1400211ae  xor     eax, eax
0x1400211b0  mov     rbx, [rsp+40h+arg_0]
0x1400211b5  mov     rdi, [rsp+40h+arg_8]
0x1400211ba  add     rsp, 40h
0x1400211be  pop     rbp
0x1400211bf  retn
```
