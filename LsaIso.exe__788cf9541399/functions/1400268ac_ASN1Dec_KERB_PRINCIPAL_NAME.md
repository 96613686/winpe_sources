# ASN1Dec_KERB_PRINCIPAL_NAME

- ea: `0x1400268ac`
- end: `0x140026981`
- name: `ASN1Dec_KERB_PRINCIPAL_NAME`
- size: `213`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x140020820`
- `0x1400211d0`
- `0x140021670`
- `0x140022a88`
- `0x140023440`
- `0x140023b20`
- `0x1400246bc`
- `0x140024c28`
- `0x140025418`
- `0x140025750`
- `0x1400261f8`
- `0x140026560`
- `0x14002669c`
- `0x140027df0`
- `0x1400281a0`
- `0x1400283a0`
- `0x140028710`
- `0x140028bec`
- `0x14002a040`

## callees

- `0x1400268ac`
- `0x140026988`

## import_xrefs

- `MSASN1!ASN1BERDecExplicitTag` at `0x1400268f1`
- `MSASN1!ASN1BERDecExplicitTag` at `0x14002690c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1400268f1`
- `MSASN1!ASN1BERDecExplicitTag` at `0x14002690c`
- `MSASN1!ASN1BERDecS32Val` at `0x140026922`
- `MSASN1!ASN1BERDecS32Val` at `0x140026922`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026938`
- `MSASN1!ASN1BERDecEndOfContents` at `0x14002695e`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026938`
- `MSASN1!ASN1BERDecEndOfContents` at `0x14002695e`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_PRINCIPAL_NAME(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 v7; // [rsp+20h] [rbp-20h] BYREF
  __int64 v8; // [rsp+28h] [rbp-18h] BYREF
  __int64 v9; // [rsp+30h] [rbp-10h] BYREF
  __int64 v10; // [rsp+68h] [rbp+28h] BYREF

  v10 = 0;
  v9 = 0;
  v7 = 0;
  v8 = 0;
  return (unsigned int)ASN1BERDecExplicitTag(a1, 16, &v10, &v9)
      && (unsigned int)ASN1BERDecExplicitTag(v10, 0x80000000LL, &v7, &v8)
      && (unsigned int)ASN1BERDecS32Val(v7, 2, a3)
      && (unsigned int)ASN1BERDecEndOfContents(v10, v7, v8)
      && (unsigned int)ASN1Dec_KERB_PRINCIPAL_NAME_name_string(v10, v5, a3 + 8)
      && (unsigned int)ASN1BERDecEndOfContents(a1, v10, v9) != 0;
}

```

## disassembly

```asm
0x1400268ac  mov     [rsp-8+arg_0], rbx
0x1400268b1  mov     [rsp-8+arg_8], rdi
0x1400268b6  push    rbp
0x1400268b7  mov     rbp, rsp
0x1400268ba  sub     rsp, 40h
0x1400268be  mov     rbx, r8
0x1400268c1  mov     [rbp+arg_18], 0
0x1400268c9  lea     r8, [rbp+arg_18]
0x1400268cd  mov     [rbp+var_10], 0
0x1400268d5  lea     r9, [rbp+var_10]
0x1400268d9  mov     [rbp+var_20], 0
0x1400268e1  mov     edx, 10h
0x1400268e6  mov     [rbp+var_18], 0
0x1400268ee  mov     rdi, rcx
0x1400268f1  call    cs:__imp_ASN1BERDecExplicitTag
0x1400268f7  test    eax, eax
0x1400268f9  jz      short loc_14002696F
0x1400268fb  mov     rcx, [rbp+arg_18]
0x1400268ff  lea     r9, [rbp+var_18]
0x140026903  lea     r8, [rbp+var_20]
0x140026907  mov     edx, 80000000h
0x14002690c  call    cs:__imp_ASN1BERDecExplicitTag
0x140026912  test    eax, eax
0x140026914  jz      short loc_14002696F
0x140026916  mov     rcx, [rbp+var_20]
0x14002691a  mov     r8, rbx
0x14002691d  mov     edx, 2
0x140026922  call    cs:__imp_ASN1BERDecS32Val
0x140026928  test    eax, eax
0x14002692a  jz      short loc_14002696F
0x14002692c  mov     r8, [rbp+var_18]
0x140026930  mov     rdx, [rbp+var_20]
0x140026934  mov     rcx, [rbp+arg_18]
0x140026938  call    cs:__imp_ASN1BERDecEndOfContents
0x14002693e  test    eax, eax
0x140026940  jz      short loc_14002696F
0x140026942  mov     rcx, [rbp+arg_18]
0x140026946  lea     r8, [rbx+8]
0x14002694a  call    ASN1Dec_KERB_PRINCIPAL_NAME_name_string
0x14002694f  test    eax, eax
0x140026951  jz      short loc_14002696F
0x140026953  mov     r8, [rbp+var_10]
0x140026957  mov     rcx, rdi
0x14002695a  mov     rdx, [rbp+arg_18]
0x14002695e  call    cs:__imp_ASN1BERDecEndOfContents
0x140026964  xor     ecx, ecx
0x140026966  test    eax, eax
0x140026968  setnz   cl
0x14002696b  mov     eax, ecx
0x14002696d  jmp     short loc_140026971
0x14002696f  xor     eax, eax
0x140026971  mov     rbx, [rsp+40h+arg_0]
0x140026976  mov     rdi, [rsp+40h+arg_8]
0x14002697b  add     rsp, 40h
0x14002697f  pop     rbp
0x140026980  retn
```
