# ASN1Dec_PKERB_TICKET_EXTENSIONS

- ea: `0x140029ba8`
- end: `0x140029c78`
- name: `ASN1Dec_PKERB_TICKET_EXTENSIONS`
- size: `208`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140021670`
- `0x140022a88`
- `0x140023440`
- `0x140024c28`
- `0x1400283a0`

## callees

- `0x1400210ac`
- `0x140029ba8`

## import_xrefs

- `MSASN1!ASN1BERDecNotEndOfContents` at `0x140029bfa`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x140029bfa`
- `MSASN1!ASN1BERDecPeekTag` at `0x140029c0c`
- `MSASN1!ASN1BERDecPeekTag` at `0x140029c0c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140029be8`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140029be8`
- `MSASN1!ASN1DecAlloc` at `0x140029c1f`
- `MSASN1!ASN1DecAlloc` at `0x140029c1f`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140029c55`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140029c55`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_PKERB_TICKET_EXTENSIONS(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  int v9; // [rsp+48h] [rbp+18h] BYREF
  __int64 v10; // [rsp+58h] [rbp+28h] BYREF

  v10 = 0;
  v8 = 0;
  v9 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, 16, &v10, &v8) )
    return 0;
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v10, v8) )
  {
    if ( !(unsigned int)ASN1BERDecPeekTag(v10, &v9) )
      return 0;
    v5 = ASN1DecAlloc(v10, 32);
    *a3 = v5;
    if ( !v5 || !ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq(v10, v6, v5 + 8) )
      return 0;
    a3 = (__int64 *)*a3;
  }
  *a3 = 0;
  return (unsigned int)ASN1BERDecEndOfContents(a1, v10, v8) != 0;
}

```

## disassembly

```asm
0x140029ba8  mov     [rsp-8+arg_0], rbx
0x140029bad  mov     [rsp-8+arg_10], rdi
0x140029bb2  mov     [rsp-8+arg_8], edx
0x140029bb6  push    rbp
0x140029bb7  mov     rbp, rsp
0x140029bba  sub     rsp, 30h
0x140029bbe  mov     rbx, r8
0x140029bc1  mov     [rbp+arg_18], 0
0x140029bc9  lea     r8, [rbp+arg_18]
0x140029bcd  mov     [rbp+var_10], 0
0x140029bd5  lea     r9, [rbp+var_10]
0x140029bd9  mov     [rbp+arg_8], 0
0x140029be0  mov     edx, 10h
0x140029be5  mov     rdi, rcx
0x140029be8  call    cs:__imp_ASN1BERDecExplicitTag
0x140029bee  test    eax, eax
0x140029bf0  jz      short loc_140029C66
0x140029bf2  mov     rdx, [rbp+var_10]
0x140029bf6  mov     rcx, [rbp+arg_18]
0x140029bfa  call    cs:__imp_ASN1BERDecNotEndOfContents
0x140029c00  test    eax, eax
0x140029c02  jz      short loc_140029C43
0x140029c04  mov     rcx, [rbp+arg_18]
0x140029c08  lea     rdx, [rbp+arg_8]
0x140029c0c  call    cs:__imp_ASN1BERDecPeekTag
0x140029c12  test    eax, eax
0x140029c14  jz      short loc_140029C66
0x140029c16  mov     rcx, [rbp+arg_18]
0x140029c1a  mov     edx, 20h ; ' '
0x140029c1f  call    cs:__imp_ASN1DecAlloc
0x140029c25  mov     [rbx], rax
0x140029c28  test    rax, rax
0x140029c2b  jz      short loc_140029C66
0x140029c2d  mov     rcx, [rbp+arg_18]
0x140029c31  lea     r8, [rax+8]
0x140029c35  call    ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq
0x140029c3a  test    eax, eax
0x140029c3c  jz      short loc_140029C66
0x140029c3e  mov     rbx, [rbx]
0x140029c41  jmp     short loc_140029BF2
0x140029c43  mov     qword ptr [rbx], 0
0x140029c4a  mov     rcx, rdi
0x140029c4d  mov     r8, [rbp+var_10]
0x140029c51  mov     rdx, [rbp+arg_18]
0x140029c55  call    cs:__imp_ASN1BERDecEndOfContents
0x140029c5b  xor     ecx, ecx
0x140029c5d  test    eax, eax
0x140029c5f  setnz   cl
0x140029c62  mov     eax, ecx
0x140029c64  jmp     short loc_140029C68
0x140029c66  xor     eax, eax
0x140029c68  mov     rbx, [rsp+30h+arg_0]
0x140029c6d  mov     rdi, [rsp+30h+arg_10]
0x140029c72  add     rsp, 30h
0x140029c76  pop     rbp
0x140029c77  retn
```
