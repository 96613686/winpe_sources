# ASN1Dec_KERB_ENCRYPTED_DATA

- ea: `0x1400228f0`
- end: `0x140022a7f`
- name: `ASN1Dec_KERB_ENCRYPTED_DATA`
- size: `399`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f980`
- `0x140020300`
- `0x1400204c0`
- `0x1400214a0`
- `0x140023a48`
- `0x1400246bc`
- `0x140024c28`
- `0x140025c30`
- `0x140026ab0`
- `0x1400283a0`
- `0x140028964`
- `0x140028a48`

## callees

- `0x1400228f0`

## import_xrefs

- `MSASN1!ASN1BERDecOctetString` at `0x140022a31`
- `MSASN1!ASN1BERDecOctetString` at `0x140022a31`
- `MSASN1!ASN1BERDecPeekTag` at `0x1400229af`
- `MSASN1!ASN1BERDecPeekTag` at `0x1400229af`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140022941`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140022964`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1400229ce`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140022a1a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140022941`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140022964`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1400229ce`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140022a1a`
- `MSASN1!ASN1BERDecS32Val` at `0x14002297f`
- `MSASN1!ASN1BERDecS32Val` at `0x1400229e9`
- `MSASN1!ASN1BERDecS32Val` at `0x14002297f`
- `MSASN1!ASN1BERDecS32Val` at `0x1400229e9`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140022999`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1400229ff`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140022a47`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140022a5c`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140022999`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1400229ff`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140022a47`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140022a5c`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_ENCRYPTED_DATA(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-20h] BYREF
  __int64 v9; // [rsp+28h] [rbp-18h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+58h] [rbp+18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+28h] BYREF

  v8 = 0;
  v10 = 0;
  v12 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  v9 = 0;
  v11 = 0;
  if ( (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v8, &v10)
    && (v5 = v8, *a3 = 0, (unsigned int)ASN1BERDecExplicitTag(v5, 0x80000000LL, &v12, &v9))
    && (unsigned int)ASN1BERDecS32Val(v12, 2, a3 + 4)
    && (unsigned int)ASN1BERDecEndOfContents(v8, v12, v9)
    && ((ASN1BERDecPeekTag(v8, &v11), v11 != -2147483647)
     || (v6 = v8, *a3 |= 0x80u, (unsigned int)ASN1BERDecExplicitTag(v6, 2147483649LL, &v12, &v9))
     && (unsigned int)ASN1BERDecS32Val(v12, 2, a3 + 8)
     && (unsigned int)ASN1BERDecEndOfContents(v8, v12, v9))
    && (unsigned int)ASN1BERDecExplicitTag(v8, 2147483650LL, &v12, &v9)
    && (unsigned int)ASN1BERDecOctetString(v12, 4, a3 + 16)
    && (unsigned int)ASN1BERDecEndOfContents(v8, v12, v9) )
  {
    return (unsigned int)ASN1BERDecEndOfContents(a1, v8, v10) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1400228f0  mov     [rsp-8+arg_0], rbx
0x1400228f5  mov     [rsp-8+arg_10], rdi
0x1400228fa  push    rbp
0x1400228fb  mov     rbp, rsp
0x1400228fe  sub     rsp, 40h
0x140022902  test    edx, edx
0x140022904  mov     [rbp+var_20], 0
0x14002290c  mov     eax, 10h
0x140022911  mov     [rbp+var_10], 0
0x140022919  mov     rbx, r8
0x14002291c  mov     [rbp+arg_18], 0
0x140022924  cmovz   edx, eax
0x140022927  mov     [rbp+var_18], 0
0x14002292f  lea     r9, [rbp+var_10]
0x140022933  mov     [rbp+arg_8], 0
0x14002293a  lea     r8, [rbp+var_20]
0x14002293e  mov     rdi, rcx
0x140022941  call    cs:__imp_ASN1BERDecExplicitTag
0x140022947  test    eax, eax
0x140022949  jz      loc_140022A6D
0x14002294f  mov     rcx, [rbp+var_20]
0x140022953  lea     r9, [rbp+var_18]
0x140022957  xor     eax, eax
0x140022959  lea     r8, [rbp+arg_18]
0x14002295d  mov     edx, 80000000h
0x140022962  mov     [rbx], al
0x140022964  call    cs:__imp_ASN1BERDecExplicitTag
0x14002296a  test    eax, eax
0x14002296c  jz      loc_140022A6D
0x140022972  mov     rcx, [rbp+arg_18]
0x140022976  lea     r8, [rbx+4]
0x14002297a  mov     edx, 2
0x14002297f  call    cs:__imp_ASN1BERDecS32Val
0x140022985  test    eax, eax
0x140022987  jz      loc_140022A6D
0x14002298d  mov     r8, [rbp+var_18]
0x140022991  mov     rdx, [rbp+arg_18]
0x140022995  mov     rcx, [rbp+var_20]
0x140022999  call    cs:__imp_ASN1BERDecEndOfContents
0x14002299f  test    eax, eax
0x1400229a1  jz      loc_140022A6D
0x1400229a7  mov     rcx, [rbp+var_20]
0x1400229ab  lea     rdx, [rbp+arg_8]
0x1400229af  call    cs:__imp_ASN1BERDecPeekTag
0x1400229b5  mov     edx, 80000001h
0x1400229ba  cmp     [rbp+arg_8], edx
0x1400229bd  jnz     short loc_140022A09
0x1400229bf  mov     rcx, [rbp+var_20]
0x1400229c3  lea     r9, [rbp+var_18]
0x1400229c7  or      byte ptr [rbx], 80h
0x1400229ca  lea     r8, [rbp+arg_18]
0x1400229ce  call    cs:__imp_ASN1BERDecExplicitTag
0x1400229d4  test    eax, eax
0x1400229d6  jz      loc_140022A6D
0x1400229dc  mov     rcx, [rbp+arg_18]
0x1400229e0  lea     r8, [rbx+8]
0x1400229e4  mov     edx, 2
0x1400229e9  call    cs:__imp_ASN1BERDecS32Val
0x1400229ef  test    eax, eax
0x1400229f1  jz      short loc_140022A6D
0x1400229f3  mov     r8, [rbp+var_18]
0x1400229f7  mov     rdx, [rbp+arg_18]
0x1400229fb  mov     rcx, [rbp+var_20]
0x1400229ff  call    cs:__imp_ASN1BERDecEndOfContents
0x140022a05  test    eax, eax
0x140022a07  jz      short loc_140022A6D
0x140022a09  mov     rcx, [rbp+var_20]
0x140022a0d  lea     r9, [rbp+var_18]
0x140022a11  lea     r8, [rbp+arg_18]
0x140022a15  mov     edx, 80000002h
0x140022a1a  call    cs:__imp_ASN1BERDecExplicitTag
0x140022a20  test    eax, eax
0x140022a22  jz      short loc_140022A6D
0x140022a24  mov     rcx, [rbp+arg_18]
0x140022a28  lea     r8, [rbx+10h]
0x140022a2c  mov     edx, 4
0x140022a31  call    cs:__imp_ASN1BERDecOctetString
0x140022a37  test    eax, eax
0x140022a39  jz      short loc_140022A6D
0x140022a3b  mov     r8, [rbp+var_18]
0x140022a3f  mov     rdx, [rbp+arg_18]
0x140022a43  mov     rcx, [rbp+var_20]
0x140022a47  call    cs:__imp_ASN1BERDecEndOfContents
0x140022a4d  test    eax, eax
0x140022a4f  jz      short loc_140022A6D
0x140022a51  mov     r8, [rbp+var_10]
0x140022a55  mov     rcx, rdi
0x140022a58  mov     rdx, [rbp+var_20]
0x140022a5c  call    cs:__imp_ASN1BERDecEndOfContents
0x140022a62  xor     ecx, ecx
0x140022a64  test    eax, eax
0x140022a66  setnz   cl
0x140022a69  mov     eax, ecx
0x140022a6b  jmp     short loc_140022A6F
0x140022a6d  xor     eax, eax
0x140022a6f  mov     rbx, [rsp+40h+arg_0]
0x140022a74  mov     rdi, [rsp+40h+arg_10]
0x140022a79  add     rsp, 40h
0x140022a7d  pop     rbp
0x140022a7e  retn
```
