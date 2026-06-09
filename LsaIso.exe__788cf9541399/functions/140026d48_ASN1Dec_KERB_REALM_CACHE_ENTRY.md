# ASN1Dec_KERB_REALM_CACHE_ENTRY

- ea: `0x140026d48`
- end: `0x140026e5c`
- name: `ASN1Dec_KERB_REALM_CACHE_ENTRY`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140026c70`

## callees

- `0x140026d48`

## import_xrefs

- `MSASN1!ASN1BERDecGeneralizedTime` at `0x140026e0e`
- `MSASN1!ASN1BERDecGeneralizedTime` at `0x140026e0e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140026d8d`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140026dac`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140026df7`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140026d8d`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140026dac`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140026df7`
- `MSASN1!ASN1BERDecZeroCharString` at `0x140026dc6`
- `MSASN1!ASN1BERDecZeroCharString` at `0x140026dc6`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026ddc`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026e24`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026e39`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026ddc`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026e24`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026e39`

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
0x140026d48  mov     [rsp-8+arg_0], rbx
0x140026d4d  mov     [rsp-8+arg_8], rdi
0x140026d52  push    rbp
0x140026d53  mov     rbp, rsp
0x140026d56  sub     rsp, 40h
0x140026d5a  mov     rbx, r8
0x140026d5d  mov     [rbp+var_20], 0
0x140026d65  lea     r8, [rbp+var_20]
0x140026d69  mov     [rbp+var_10], 0
0x140026d71  lea     r9, [rbp+var_10]
0x140026d75  mov     [rbp+arg_18], 0
0x140026d7d  mov     edx, 10h
0x140026d82  mov     [rbp+var_18], 0
0x140026d8a  mov     rdi, rcx
0x140026d8d  call    cs:__imp_ASN1BERDecExplicitTag
0x140026d93  test    eax, eax
0x140026d95  jz      loc_140026E4A
0x140026d9b  mov     rcx, [rbp+var_20]
0x140026d9f  lea     r9, [rbp+var_18]
0x140026da3  lea     r8, [rbp+arg_18]
0x140026da7  mov     edx, 80000000h
0x140026dac  call    cs:__imp_ASN1BERDecExplicitTag
0x140026db2  test    eax, eax
0x140026db4  jz      loc_140026E4A
0x140026dba  mov     rcx, [rbp+arg_18]
0x140026dbe  mov     r8, rbx
0x140026dc1  mov     edx, 1Bh
0x140026dc6  call    cs:__imp_ASN1BERDecZeroCharString
0x140026dcc  test    eax, eax
0x140026dce  jz      short loc_140026E4A
0x140026dd0  mov     r8, [rbp+var_18]
0x140026dd4  mov     rdx, [rbp+arg_18]
0x140026dd8  mov     rcx, [rbp+var_20]
0x140026ddc  call    cs:__imp_ASN1BERDecEndOfContents
0x140026de2  test    eax, eax
0x140026de4  jz      short loc_140026E4A
0x140026de6  mov     rcx, [rbp+var_20]
0x140026dea  lea     r9, [rbp+var_18]
0x140026dee  lea     r8, [rbp+arg_18]
0x140026df2  mov     edx, 80000001h
0x140026df7  call    cs:__imp_ASN1BERDecExplicitTag
0x140026dfd  test    eax, eax
0x140026dff  jz      short loc_140026E4A
0x140026e01  mov     rcx, [rbp+arg_18]
0x140026e05  lea     r8, [rbx+8]
0x140026e09  mov     edx, 18h
0x140026e0e  call    cs:__imp_ASN1BERDecGeneralizedTime
0x140026e14  test    eax, eax
0x140026e16  jz      short loc_140026E4A
0x140026e18  mov     r8, [rbp+var_18]
0x140026e1c  mov     rdx, [rbp+arg_18]
0x140026e20  mov     rcx, [rbp+var_20]
0x140026e24  call    cs:__imp_ASN1BERDecEndOfContents
0x140026e2a  test    eax, eax
0x140026e2c  jz      short loc_140026E4A
0x140026e2e  mov     r8, [rbp+var_10]
0x140026e32  mov     rcx, rdi
0x140026e35  mov     rdx, [rbp+var_20]
0x140026e39  call    cs:__imp_ASN1BERDecEndOfContents
0x140026e3f  xor     ecx, ecx
0x140026e41  test    eax, eax
0x140026e43  setnz   cl
0x140026e46  mov     eax, ecx
0x140026e48  jmp     short loc_140026E4C
0x140026e4a  xor     eax, eax
0x140026e4c  mov     rbx, [rsp+40h+arg_0]
0x140026e51  mov     rdi, [rsp+40h+arg_8]
0x140026e56  add     rsp, 40h
0x140026e5a  pop     rbp
0x140026e5b  retn
```
