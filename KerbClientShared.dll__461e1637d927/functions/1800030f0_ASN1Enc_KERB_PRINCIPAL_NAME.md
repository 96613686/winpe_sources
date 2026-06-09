# ASN1Enc_KERB_PRINCIPAL_NAME

- ea: `0x1800030f0`
- end: `0x180003235`
- name: `ASN1Enc_KERB_PRINCIPAL_NAME`
- size: `325`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180002540`
- `0x180002aa0`
- `0x1800071e0`
- `0x1800093d0`
- `0x180021830`
- `0x180021f20`
- `0x1800221f4`
- `0x180022d14`
- `0x1800234a0`
- `0x180023d68`
- `0x180023ee0`
- `0x180024674`
- `0x180024850`
- `0x180024950`
- `0x1800259e0`
- `0x180025c10`
- `0x180025e50`
- `0x180025fe0`

## callees

- `0x1800030f0`

## import_xrefs

- `MSASN1!ASN1BEREncEndOfContents` at `0x18000316c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800031ec`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180003201`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180003216`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000316c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800031ec`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180003201`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180003216`
- `MSASN1!ASN1DEREncCharString` at `0x1800031d2`
- `MSASN1!ASN1DEREncCharString` at `0x1800031d2`
- `MSASN1!ASN1BEREncS32` at `0x18000315b`
- `MSASN1!ASN1BEREncS32` at `0x18000315b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000311d`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180003146`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000318b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800031a2`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000311d`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180003146`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000318b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800031a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800031bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800031bd`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_PRINCIPAL_NAME(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int64 **i; // rbx
  unsigned int v7; // eax
  unsigned int v8; // [rsp+20h] [rbp-18h] BYREF
  _DWORD v9[5]; // [rsp+24h] [rbp-14h] BYREF
  unsigned int v10; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v11; // [rsp+58h] [rbp+20h] BYREF

  v9[0] = 0;
  v10 = 0;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 16, v9) )
    return 0;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v10) )
    return 0;
  if ( !(unsigned int)ASN1BEREncS32(a1, 2, *a3) )
    return 0;
  if ( !(unsigned int)ASN1BEREncEndOfContents(a1, v10) )
    return 0;
  v8 = 0;
  v11 = 0;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v8) || !(unsigned int)ASN1BEREncExplicitTag(a1, 16, &v11) )
    return 0;
  for ( i = (__int64 **)*((_QWORD *)a3 + 1); i; i = (__int64 **)*i )
  {
    v7 = lstrlenA((LPCSTR)i[1]);
    if ( !(unsigned int)ASN1DEREncCharString(a1, 27, v7, i[1]) )
      return 0;
  }
  return (unsigned int)ASN1BEREncEndOfContents(a1, v11)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v8)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v9[0]) != 0;
}

```

## disassembly

```asm
0x1800030f0  mov     [rsp+arg_0], rbx
0x1800030f5  mov     [rsp+arg_10], rsi
0x1800030fa  mov     [rsp+arg_8], edx
0x1800030fe  push    rdi
0x1800030ff  sub     rsp, 30h
0x180003103  mov     rbx, r8
0x180003106  xor     esi, esi
0x180003108  lea     r8, [rsp+38h+var_14]
0x18000310d  mov     [rsp+38h+var_14], esi
0x180003111  mov     edx, 10h
0x180003116  mov     [rsp+38h+arg_8], esi
0x18000311a  mov     rdi, rcx
0x18000311d  call    cs:__imp_ASN1BEREncExplicitTag
0x180003123  test    eax, eax
0x180003125  jnz     short loc_180003139
0x180003127  xor     eax, eax
0x180003129  mov     rbx, [rsp+38h+arg_0]
0x18000312e  mov     rsi, [rsp+38h+arg_10]
0x180003133  add     rsp, 30h
0x180003137  pop     rdi
0x180003138  retn
0x180003139  lea     r8, [rsp+38h+arg_8]
0x18000313e  mov     edx, 80000000h
0x180003143  mov     rcx, rdi
0x180003146  call    cs:__imp_ASN1BEREncExplicitTag
0x18000314c  test    eax, eax
0x18000314e  jz      short loc_180003127
0x180003150  mov     r8d, [rbx]
0x180003153  mov     edx, 2
0x180003158  mov     rcx, rdi
0x18000315b  call    cs:__imp_ASN1BEREncS32
0x180003161  test    eax, eax
0x180003163  jz      short loc_180003127
0x180003165  mov     edx, [rsp+38h+arg_8]
0x180003169  mov     rcx, rdi
0x18000316c  call    cs:__imp_ASN1BEREncEndOfContents
0x180003172  test    eax, eax
0x180003174  jz      short loc_180003127
0x180003176  lea     r8, [rsp+38h+var_18]
0x18000317b  mov     [rsp+38h+var_18], esi
0x18000317f  mov     edx, 80000001h
0x180003184  mov     [rsp+38h+arg_18], esi
0x180003188  mov     rcx, rdi
0x18000318b  call    cs:__imp_ASN1BEREncExplicitTag
0x180003191  test    eax, eax
0x180003193  jz      short loc_180003127
0x180003195  lea     r8, [rsp+38h+arg_18]
0x18000319a  mov     edx, 10h
0x18000319f  mov     rcx, rdi
0x1800031a2  call    cs:__imp_ASN1BEREncExplicitTag
0x1800031a8  test    eax, eax
0x1800031aa  jz      loc_180003127
0x1800031b0  mov     rbx, [rbx+8]
0x1800031b4  test    rbx, rbx
0x1800031b7  jz      short loc_1800031E5
0x1800031b9  mov     rcx, [rbx+8]; lpString
0x1800031bd  call    cs:__imp_lstrlenA
0x1800031c3  mov     r9, [rbx+8]
0x1800031c7  mov     edx, 1Bh
0x1800031cc  mov     r8d, eax
0x1800031cf  mov     rcx, rdi
0x1800031d2  call    cs:__imp_ASN1DEREncCharString
0x1800031d8  test    eax, eax
0x1800031da  jz      loc_180003127
0x1800031e0  mov     rbx, [rbx]
0x1800031e3  jmp     short loc_1800031B4
0x1800031e5  mov     edx, [rsp+38h+arg_18]
0x1800031e9  mov     rcx, rdi
0x1800031ec  call    cs:__imp_ASN1BEREncEndOfContents
0x1800031f2  test    eax, eax
0x1800031f4  jz      loc_180003127
0x1800031fa  mov     edx, [rsp+38h+var_18]
0x1800031fe  mov     rcx, rdi
0x180003201  call    cs:__imp_ASN1BEREncEndOfContents
0x180003207  test    eax, eax
0x180003209  jz      loc_180003127
0x18000320f  mov     edx, [rsp+38h+var_14]
0x180003213  mov     rcx, rdi
0x180003216  call    cs:__imp_ASN1BEREncEndOfContents
0x18000321c  mov     rbx, [rsp+38h+arg_0]
0x180003221  mov     ecx, esi
0x180003223  mov     rsi, [rsp+38h+arg_10]
0x180003228  test    eax, eax
0x18000322a  setnz   cl
0x18000322d  mov     eax, ecx
0x18000322f  add     rsp, 30h
0x180003233  pop     rdi
0x180003234  retn
```
