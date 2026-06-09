# ASN1Dec_PKERB_TICKET_EXTENSIONS

- ea: `0x1800206c8`
- end: `0x180020798`
- name: `ASN1Dec_PKERB_TICKET_EXTENSIONS`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004c90`

## callees

- `0x180019dec`
- `0x1800206c8`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x18002072c`
- `MSASN1!ASN1BERDecPeekTag` at `0x18002072c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180020708`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180020708`
- `MSASN1!ASN1DecAlloc` at `0x18002073f`
- `MSASN1!ASN1DecAlloc` at `0x18002073f`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180020775`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180020775`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18002071a`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18002071a`

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
0x1800206c8  mov     [rsp-8+arg_0], rbx
0x1800206cd  mov     [rsp-8+arg_10], rdi
0x1800206d2  mov     [rsp-8+arg_8], edx
0x1800206d6  push    rbp
0x1800206d7  mov     rbp, rsp
0x1800206da  sub     rsp, 30h
0x1800206de  mov     rbx, r8
0x1800206e1  mov     [rbp+arg_18], 0
0x1800206e9  lea     r8, [rbp+arg_18]
0x1800206ed  mov     [rbp+var_10], 0
0x1800206f5  lea     r9, [rbp+var_10]
0x1800206f9  mov     [rbp+arg_8], 0
0x180020700  mov     edx, 10h
0x180020705  mov     rdi, rcx
0x180020708  call    cs:__imp_ASN1BERDecExplicitTag
0x18002070e  test    eax, eax
0x180020710  jz      short loc_180020786
0x180020712  mov     rdx, [rbp+var_10]
0x180020716  mov     rcx, [rbp+arg_18]
0x18002071a  call    cs:__imp_ASN1BERDecNotEndOfContents
0x180020720  test    eax, eax
0x180020722  jz      short loc_180020763
0x180020724  mov     rcx, [rbp+arg_18]
0x180020728  lea     rdx, [rbp+arg_8]
0x18002072c  call    cs:__imp_ASN1BERDecPeekTag
0x180020732  test    eax, eax
0x180020734  jz      short loc_180020786
0x180020736  mov     rcx, [rbp+arg_18]
0x18002073a  mov     edx, 20h ; ' '
0x18002073f  call    cs:__imp_ASN1DecAlloc
0x180020745  mov     [rbx], rax
0x180020748  test    rax, rax
0x18002074b  jz      short loc_180020786
0x18002074d  mov     rcx, [rbp+arg_18]
0x180020751  lea     r8, [rax+8]
0x180020755  call    ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq
0x18002075a  test    eax, eax
0x18002075c  jz      short loc_180020786
0x18002075e  mov     rbx, [rbx]
0x180020761  jmp     short loc_180020712
0x180020763  mov     qword ptr [rbx], 0
0x18002076a  mov     rcx, rdi
0x18002076d  mov     r8, [rbp+var_10]
0x180020771  mov     rdx, [rbp+arg_18]
0x180020775  call    cs:__imp_ASN1BERDecEndOfContents
0x18002077b  xor     ecx, ecx
0x18002077d  test    eax, eax
0x18002077f  setnz   cl
0x180020782  mov     eax, ecx
0x180020784  jmp     short loc_180020788
0x180020786  xor     eax, eax
0x180020788  mov     rbx, [rsp+30h+arg_0]
0x18002078d  mov     rdi, [rsp+30h+arg_10]
0x180020792  add     rsp, 30h
0x180020796  pop     rbp
0x180020797  retn
```
