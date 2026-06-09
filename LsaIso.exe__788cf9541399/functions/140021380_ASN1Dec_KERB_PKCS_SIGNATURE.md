# ASN1Dec_KERB_PKCS_SIGNATURE

- ea: `0x140021380`
- end: `0x140021499`
- name: `ASN1Dec_KERB_PKCS_SIGNATURE`
- size: `281`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x14001fab0`
- `0x140020820`
- `0x140021670`
- `0x140021fc0`
- `0x1400220e4`
- `0x140022210`
- `0x140022a88`
- `0x140023440`
- `0x140025530`
- `0x140025750`
- `0x140026e70`
- `0x140026fb0`
- `0x140027150`
- `0x140027560`
- `0x140028a48`
- `0x140028bec`
- `0x140028f70`
- `0x140029500`

## callees

- `0x140021380`

## import_xrefs

- `MSASN1!ASN1BERDecOctetString` at `0x14002144b`
- `MSASN1!ASN1BERDecOctetString` at `0x14002144b`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1400213ca`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1400213e9`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140021434`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1400213ca`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1400213e9`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140021434`
- `MSASN1!ASN1BERDecS32Val` at `0x140021403`
- `MSASN1!ASN1BERDecS32Val` at `0x140021403`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021419`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021461`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021476`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021419`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021461`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140021476`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_PKCS_SIGNATURE(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // [rsp+20h] [rbp-20h] BYREF
  __int64 v7; // [rsp+28h] [rbp-18h] BYREF
  __int64 v8; // [rsp+30h] [rbp-10h] BYREF
  __int64 v9; // [rsp+68h] [rbp+28h] BYREF

  v6 = 0;
  v8 = 0;
  v9 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  v7 = 0;
  return (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v6, &v8)
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
0x140021380  mov     [rsp-8+arg_0], rbx
0x140021385  mov     [rsp-8+arg_8], rdi
0x14002138a  push    rbp
0x14002138b  mov     rbp, rsp
0x14002138e  sub     rsp, 40h
0x140021392  test    edx, edx
0x140021394  mov     [rbp+var_20], 0
0x14002139c  mov     eax, 10h
0x1400213a1  mov     [rbp+var_10], 0
0x1400213a9  mov     rbx, r8
0x1400213ac  mov     [rbp+arg_18], 0
0x1400213b4  cmovz   edx, eax
0x1400213b7  mov     [rbp+var_18], 0
0x1400213bf  lea     r9, [rbp+var_10]
0x1400213c3  mov     rdi, rcx
0x1400213c6  lea     r8, [rbp+var_20]
0x1400213ca  call    cs:__imp_ASN1BERDecExplicitTag
0x1400213d0  test    eax, eax
0x1400213d2  jz      loc_140021487
0x1400213d8  mov     rcx, [rbp+var_20]
0x1400213dc  lea     r9, [rbp+var_18]
0x1400213e0  lea     r8, [rbp+arg_18]
0x1400213e4  mov     edx, 80000000h
0x1400213e9  call    cs:__imp_ASN1BERDecExplicitTag
0x1400213ef  test    eax, eax
0x1400213f1  jz      loc_140021487
0x1400213f7  mov     rcx, [rbp+arg_18]
0x1400213fb  mov     r8, rbx
0x1400213fe  mov     edx, 2
0x140021403  call    cs:__imp_ASN1BERDecS32Val
0x140021409  test    eax, eax
0x14002140b  jz      short loc_140021487
0x14002140d  mov     r8, [rbp+var_18]
0x140021411  mov     rdx, [rbp+arg_18]
0x140021415  mov     rcx, [rbp+var_20]
0x140021419  call    cs:__imp_ASN1BERDecEndOfContents
0x14002141f  test    eax, eax
0x140021421  jz      short loc_140021487
0x140021423  mov     rcx, [rbp+var_20]
0x140021427  lea     r9, [rbp+var_18]
0x14002142b  lea     r8, [rbp+arg_18]
0x14002142f  mov     edx, 80000001h
0x140021434  call    cs:__imp_ASN1BERDecExplicitTag
0x14002143a  test    eax, eax
0x14002143c  jz      short loc_140021487
0x14002143e  mov     rcx, [rbp+arg_18]
0x140021442  lea     r8, [rbx+8]
0x140021446  mov     edx, 4
0x14002144b  call    cs:__imp_ASN1BERDecOctetString
0x140021451  test    eax, eax
0x140021453  jz      short loc_140021487
0x140021455  mov     r8, [rbp+var_18]
0x140021459  mov     rdx, [rbp+arg_18]
0x14002145d  mov     rcx, [rbp+var_20]
0x140021461  call    cs:__imp_ASN1BERDecEndOfContents
0x140021467  test    eax, eax
0x140021469  jz      short loc_140021487
0x14002146b  mov     r8, [rbp+var_10]
0x14002146f  mov     rcx, rdi
0x140021472  mov     rdx, [rbp+var_20]
0x140021476  call    cs:__imp_ASN1BERDecEndOfContents
0x14002147c  xor     ecx, ecx
0x14002147e  test    eax, eax
0x140021480  setnz   cl
0x140021483  mov     eax, ecx
0x140021485  jmp     short loc_140021489
0x140021487  xor     eax, eax
0x140021489  mov     rbx, [rsp+40h+arg_0]
0x14002148e  mov     rdi, [rsp+40h+arg_8]
0x140021493  add     rsp, 40h
0x140021497  pop     rbp
0x140021498  retn
```
