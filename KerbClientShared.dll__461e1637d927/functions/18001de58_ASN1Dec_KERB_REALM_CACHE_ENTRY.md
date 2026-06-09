# ASN1Dec_KERB_REALM_CACHE_ENTRY

- ea: `0x18001de58`
- end: `0x18001df6c`
- name: `ASN1Dec_KERB_REALM_CACHE_ENTRY`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001dd80`

## callees

- `0x18001de58`

## import_xrefs

- `MSASN1!ASN1BERDecExplicitTag` at `0x18001de9d`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001debc`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001df07`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001de9d`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001debc`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001df07`
- `MSASN1!ASN1BERDecZeroCharString` at `0x18001ded6`
- `MSASN1!ASN1BERDecZeroCharString` at `0x18001ded6`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001deec`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001df34`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001df49`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001deec`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001df34`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001df49`
- `MSASN1!ASN1BERDecGeneralizedTime` at `0x18001df1e`
- `MSASN1!ASN1BERDecGeneralizedTime` at `0x18001df1e`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_REALM_CACHE_ENTRY(__int64 a1, __int64 a2, __int64 a3)
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
      && (unsigned int)ASN1BERDecZeroCharString(v9, 27, a3)
      && (unsigned int)ASN1BERDecEndOfContents(v6, v9, v7)
      && (unsigned int)ASN1BERDecExplicitTag(v6, 2147483649LL, &v9, &v7)
      && (unsigned int)ASN1BERDecGeneralizedTime(v9, 24, a3 + 8)
      && (unsigned int)ASN1BERDecEndOfContents(v6, v9, v7)
      && (unsigned int)ASN1BERDecEndOfContents(a1, v6, v8) != 0;
}

```

## disassembly

```asm
0x18001de58  mov     [rsp-8+arg_0], rbx
0x18001de5d  mov     [rsp-8+arg_8], rdi
0x18001de62  push    rbp
0x18001de63  mov     rbp, rsp
0x18001de66  sub     rsp, 40h
0x18001de6a  mov     rbx, r8
0x18001de6d  mov     [rbp+var_20], 0
0x18001de75  lea     r8, [rbp+var_20]
0x18001de79  mov     [rbp+var_10], 0
0x18001de81  lea     r9, [rbp+var_10]
0x18001de85  mov     [rbp+arg_18], 0
0x18001de8d  mov     edx, 10h
0x18001de92  mov     [rbp+var_18], 0
0x18001de9a  mov     rdi, rcx
0x18001de9d  call    cs:__imp_ASN1BERDecExplicitTag
0x18001dea3  test    eax, eax
0x18001dea5  jz      loc_18001DF5A
0x18001deab  mov     rcx, [rbp+var_20]
0x18001deaf  lea     r9, [rbp+var_18]
0x18001deb3  lea     r8, [rbp+arg_18]
0x18001deb7  mov     edx, 80000000h
0x18001debc  call    cs:__imp_ASN1BERDecExplicitTag
0x18001dec2  test    eax, eax
0x18001dec4  jz      loc_18001DF5A
0x18001deca  mov     rcx, [rbp+arg_18]
0x18001dece  mov     r8, rbx
0x18001ded1  mov     edx, 1Bh
0x18001ded6  call    cs:__imp_ASN1BERDecZeroCharString
0x18001dedc  test    eax, eax
0x18001dede  jz      short loc_18001DF5A
0x18001dee0  mov     r8, [rbp+var_18]
0x18001dee4  mov     rdx, [rbp+arg_18]
0x18001dee8  mov     rcx, [rbp+var_20]
0x18001deec  call    cs:__imp_ASN1BERDecEndOfContents
0x18001def2  test    eax, eax
0x18001def4  jz      short loc_18001DF5A
0x18001def6  mov     rcx, [rbp+var_20]
0x18001defa  lea     r9, [rbp+var_18]
0x18001defe  lea     r8, [rbp+arg_18]
0x18001df02  mov     edx, 80000001h
0x18001df07  call    cs:__imp_ASN1BERDecExplicitTag
0x18001df0d  test    eax, eax
0x18001df0f  jz      short loc_18001DF5A
0x18001df11  mov     rcx, [rbp+arg_18]
0x18001df15  lea     r8, [rbx+8]
0x18001df19  mov     edx, 18h
0x18001df1e  call    cs:__imp_ASN1BERDecGeneralizedTime
0x18001df24  test    eax, eax
0x18001df26  jz      short loc_18001DF5A
0x18001df28  mov     r8, [rbp+var_18]
0x18001df2c  mov     rdx, [rbp+arg_18]
0x18001df30  mov     rcx, [rbp+var_20]
0x18001df34  call    cs:__imp_ASN1BERDecEndOfContents
0x18001df3a  test    eax, eax
0x18001df3c  jz      short loc_18001DF5A
0x18001df3e  mov     r8, [rbp+var_10]
0x18001df42  mov     rcx, rdi
0x18001df45  mov     rdx, [rbp+var_20]
0x18001df49  call    cs:__imp_ASN1BERDecEndOfContents
0x18001df4f  xor     ecx, ecx
0x18001df51  test    eax, eax
0x18001df53  setnz   cl
0x18001df56  mov     eax, ecx
0x18001df58  jmp     short loc_18001DF5C
0x18001df5a  xor     eax, eax
0x18001df5c  mov     rbx, [rsp+40h+arg_0]
0x18001df61  mov     rdi, [rsp+40h+arg_8]
0x18001df66  add     rsp, 40h
0x18001df6a  pop     rbp
0x18001df6b  retn
```
