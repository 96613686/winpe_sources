# ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq

- ea: `0x180019dec`
- end: `0x180019f00`
- name: `ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq`
- size: `276`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001ae30`
- `0x18001b240`
- `0x18001cff4`
- `0x18001d508`
- `0x18001e398`
- `0x1800206c8`

## callees

- `0x180019dec`

## import_xrefs

- `MSASN1!ASN1BERDecExplicitTag` at `0x180019e31`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180019e50`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180019e9b`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180019e31`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180019e50`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180019e9b`
- `MSASN1!ASN1BERDecS32Val` at `0x180019e6a`
- `MSASN1!ASN1BERDecS32Val` at `0x180019e6a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180019e80`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180019ec8`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180019edd`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180019e80`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180019ec8`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180019edd`
- `MSASN1!ASN1BERDecOctetString` at `0x180019eb2`
- `MSASN1!ASN1BERDecOctetString` at `0x180019eb2`

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
0x180019dec  mov     [rsp-8+arg_0], rbx
0x180019df1  mov     [rsp-8+arg_8], rdi
0x180019df6  push    rbp
0x180019df7  mov     rbp, rsp
0x180019dfa  sub     rsp, 40h
0x180019dfe  mov     rbx, r8
0x180019e01  mov     [rbp+var_20], 0
0x180019e09  lea     r8, [rbp+var_20]
0x180019e0d  mov     [rbp+var_10], 0
0x180019e15  lea     r9, [rbp+var_10]
0x180019e19  mov     [rbp+arg_18], 0
0x180019e21  mov     edx, 10h
0x180019e26  mov     [rbp+var_18], 0
0x180019e2e  mov     rdi, rcx
0x180019e31  call    cs:__imp_ASN1BERDecExplicitTag
0x180019e37  test    eax, eax
0x180019e39  jz      loc_180019EEE
0x180019e3f  mov     rcx, [rbp+var_20]
0x180019e43  lea     r9, [rbp+var_18]
0x180019e47  lea     r8, [rbp+arg_18]
0x180019e4b  mov     edx, 80000000h
0x180019e50  call    cs:__imp_ASN1BERDecExplicitTag
0x180019e56  test    eax, eax
0x180019e58  jz      loc_180019EEE
0x180019e5e  mov     rcx, [rbp+arg_18]
0x180019e62  mov     r8, rbx
0x180019e65  mov     edx, 2
0x180019e6a  call    cs:__imp_ASN1BERDecS32Val
0x180019e70  test    eax, eax
0x180019e72  jz      short loc_180019EEE
0x180019e74  mov     r8, [rbp+var_18]
0x180019e78  mov     rdx, [rbp+arg_18]
0x180019e7c  mov     rcx, [rbp+var_20]
0x180019e80  call    cs:__imp_ASN1BERDecEndOfContents
0x180019e86  test    eax, eax
0x180019e88  jz      short loc_180019EEE
0x180019e8a  mov     rcx, [rbp+var_20]
0x180019e8e  lea     r9, [rbp+var_18]
0x180019e92  lea     r8, [rbp+arg_18]
0x180019e96  mov     edx, 80000001h
0x180019e9b  call    cs:__imp_ASN1BERDecExplicitTag
0x180019ea1  test    eax, eax
0x180019ea3  jz      short loc_180019EEE
0x180019ea5  mov     rcx, [rbp+arg_18]
0x180019ea9  lea     r8, [rbx+8]
0x180019ead  mov     edx, 4
0x180019eb2  call    cs:__imp_ASN1BERDecOctetString
0x180019eb8  test    eax, eax
0x180019eba  jz      short loc_180019EEE
0x180019ebc  mov     r8, [rbp+var_18]
0x180019ec0  mov     rdx, [rbp+arg_18]
0x180019ec4  mov     rcx, [rbp+var_20]
0x180019ec8  call    cs:__imp_ASN1BERDecEndOfContents
0x180019ece  test    eax, eax
0x180019ed0  jz      short loc_180019EEE
0x180019ed2  mov     r8, [rbp+var_10]
0x180019ed6  mov     rcx, rdi
0x180019ed9  mov     rdx, [rbp+var_20]
0x180019edd  call    cs:__imp_ASN1BERDecEndOfContents
0x180019ee3  xor     ecx, ecx
0x180019ee5  test    eax, eax
0x180019ee7  setnz   cl
0x180019eea  mov     eax, ecx
0x180019eec  jmp     short loc_180019EF0
0x180019eee  xor     eax, eax
0x180019ef0  mov     rbx, [rsp+40h+arg_0]
0x180019ef5  mov     rdi, [rsp+40h+arg_8]
0x180019efa  add     rsp, 40h
0x180019efe  pop     rbp
0x180019eff  retn
```
