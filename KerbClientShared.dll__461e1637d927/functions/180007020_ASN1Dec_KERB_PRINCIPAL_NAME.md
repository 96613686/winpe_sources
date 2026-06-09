# ASN1Dec_KERB_PRINCIPAL_NAME

- ea: `0x180007020`
- end: `0x1800071d1`
- name: `ASN1Dec_KERB_PRINCIPAL_NAME`
- size: `433`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180005130`
- `0x180019560`
- `0x180019f10`
- `0x18001a290`
- `0x18001bf3c`
- `0x18001c72c`
- `0x18001c940`
- `0x18001d3e8`
- `0x18001d750`
- `0x18001d9b0`
- `0x18001ef00`
- `0x18001f230`
- `0x18001f520`
- `0x18001f9fc`
- `0x180020880`

## callees

- `0x180007020`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x180007132`
- `MSASN1!ASN1BERDecPeekTag` at `0x180007132`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000705f`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000707a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800070ef`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000710a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000705f`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000707a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800070ef`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000710a`
- `MSASN1!ASN1BERDecZeroCharString` at `0x180007168`
- `MSASN1!ASN1BERDecZeroCharString` at `0x180007168`
- `MSASN1!ASN1BERDecS32Val` at `0x180007090`
- `MSASN1!ASN1BERDecS32Val` at `0x180007090`
- `MSASN1!ASN1DecAlloc` at `0x180007149`
- `MSASN1!ASN1DecAlloc` at `0x180007149`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800070a6`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000718a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800071a3`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800071bc`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800070a6`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000718a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800071a3`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800071bc`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x180007120`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x180007120`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_PRINCIPAL_NAME(__int64 a1, int a2, __int64 a3)
{
  __int64 v6; // rsi
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // [rsp+20h] [rbp-40h] BYREF
  __int64 v10; // [rsp+28h] [rbp-38h] BYREF
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h] BYREF
  __int64 v14; // [rsp+48h] [rbp-18h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h] BYREF
  int v16; // [rsp+88h] [rbp+28h] BYREF
  __int64 v17; // [rsp+98h] [rbp+38h] BYREF

  v16 = a2;
  v9 = 0;
  v15 = 0;
  v11 = 0;
  v13 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, 16, &v9, &v15) )
    return 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v9, 0x80000000LL, &v11, &v13) )
    return 0;
  if ( !(unsigned int)ASN1BERDecS32Val(v11, 2, a3) )
    return 0;
  if ( !(unsigned int)ASN1BERDecEndOfContents(v9, v11, v13) )
    return 0;
  v6 = v9;
  v10 = 0;
  v14 = 0;
  v17 = 0;
  v12 = 0;
  v16 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v9, 2147483649LL, &v10, &v14)
    || !(unsigned int)ASN1BERDecExplicitTag(v10, 16, &v17, &v12) )
  {
    return 0;
  }
  v7 = (__int64 *)(a3 + 8);
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v17, v12) )
  {
    if ( !(unsigned int)ASN1BERDecPeekTag(v17, &v16) )
      return 0;
    v8 = ASN1DecAlloc(v17, 16);
    *v7 = v8;
    if ( !v8 || !(unsigned int)ASN1BERDecZeroCharString(v17, 27, v8 + 8) )
      return 0;
    v7 = (__int64 *)*v7;
  }
  *v7 = 0;
  return (unsigned int)ASN1BERDecEndOfContents(v10, v17, v12)
      && (unsigned int)ASN1BERDecEndOfContents(v6, v10, v14)
      && (unsigned int)ASN1BERDecEndOfContents(a1, v9, v15) != 0;
}

```

## disassembly

```asm
0x180007020  mov     [rsp-18h+arg_0], rbx
0x180007025  mov     [rsp-18h+arg_10], rsi
0x18000702a  mov     [rsp-18h+arg_8], edx
0x18000702e  push    rbp
0x18000702f  push    rdi
0x180007030  push    r14
0x180007032  mov     rbp, rsp
0x180007035  sub     rsp, 60h
0x180007039  xor     r14d, r14d
0x18000703c  lea     r9, [rbp+var_10]
0x180007040  mov     rbx, r8
0x180007043  mov     [rbp+var_40], r14
0x180007047  lea     r8, [rbp+var_40]
0x18000704b  mov     [rbp+var_10], r14
0x18000704f  mov     edx, 10h
0x180007054  mov     [rbp+var_30], r14
0x180007058  mov     [rbp+var_20], r14
0x18000705c  mov     rdi, rcx
0x18000705f  call    cs:__imp_ASN1BERDecExplicitTag
0x180007065  test    eax, eax
0x180007067  jz      short loc_1800070B0
0x180007069  mov     rcx, [rbp+var_40]
0x18000706d  lea     r9, [rbp+var_20]
0x180007071  lea     r8, [rbp+var_30]
0x180007075  mov     edx, 80000000h
0x18000707a  call    cs:__imp_ASN1BERDecExplicitTag
0x180007080  test    eax, eax
0x180007082  jz      short loc_1800070B0
0x180007084  mov     rcx, [rbp+var_30]
0x180007088  mov     r8, rbx
0x18000708b  mov     edx, 2
0x180007090  call    cs:__imp_ASN1BERDecS32Val
0x180007096  test    eax, eax
0x180007098  jz      short loc_1800070B0
0x18000709a  mov     r8, [rbp+var_20]
0x18000709e  mov     rdx, [rbp+var_30]
0x1800070a2  mov     rcx, [rbp+var_40]
0x1800070a6  call    cs:__imp_ASN1BERDecEndOfContents
0x1800070ac  test    eax, eax
0x1800070ae  jnz     short loc_1800070C7
0x1800070b0  xor     eax, eax
0x1800070b2  lea     r11, [rsp+60h+var_s0]
0x1800070b7  mov     rbx, [r11+20h]
0x1800070bb  mov     rsi, [r11+30h]
0x1800070bf  mov     rsp, r11
0x1800070c2  pop     r14
0x1800070c4  pop     rdi
0x1800070c5  pop     rbp
0x1800070c6  retn
0x1800070c7  mov     rsi, [rbp+var_40]
0x1800070cb  lea     r9, [rbp+var_18]
0x1800070cf  mov     rcx, rsi
0x1800070d2  mov     [rbp+var_38], r14
0x1800070d6  lea     r8, [rbp+var_38]
0x1800070da  mov     [rbp+var_18], r14
0x1800070de  mov     edx, 80000001h
0x1800070e3  mov     [rbp+arg_18], r14
0x1800070e7  mov     [rbp+var_28], r14
0x1800070eb  mov     [rbp+arg_8], r14d
0x1800070ef  call    cs:__imp_ASN1BERDecExplicitTag
0x1800070f5  test    eax, eax
0x1800070f7  jz      short loc_1800070B0
0x1800070f9  mov     rcx, [rbp+var_38]
0x1800070fd  lea     r9, [rbp+var_28]
0x180007101  lea     r8, [rbp+arg_18]
0x180007105  mov     edx, 10h
0x18000710a  call    cs:__imp_ASN1BERDecExplicitTag
0x180007110  test    eax, eax
0x180007112  jz      short loc_1800070B0
0x180007114  add     rbx, 8
0x180007118  mov     rdx, [rbp+var_28]
0x18000711c  mov     rcx, [rbp+arg_18]
0x180007120  call    cs:__imp_ASN1BERDecNotEndOfContents
0x180007126  test    eax, eax
0x180007128  jz      short loc_18000717B
0x18000712a  mov     rcx, [rbp+arg_18]
0x18000712e  lea     rdx, [rbp+arg_8]
0x180007132  call    cs:__imp_ASN1BERDecPeekTag
0x180007138  test    eax, eax
0x18000713a  jz      loc_1800070B0
0x180007140  mov     rcx, [rbp+arg_18]
0x180007144  mov     edx, 10h
0x180007149  call    cs:__imp_ASN1DecAlloc
0x18000714f  mov     [rbx], rax
0x180007152  test    rax, rax
0x180007155  jz      loc_1800070B0
0x18000715b  mov     rcx, [rbp+arg_18]
0x18000715f  lea     r8, [rax+8]
0x180007163  mov     edx, 1Bh
0x180007168  call    cs:__imp_ASN1BERDecZeroCharString
0x18000716e  test    eax, eax
0x180007170  jz      loc_1800070B0
0x180007176  mov     rbx, [rbx]
0x180007179  jmp     short loc_180007118
0x18000717b  mov     [rbx], r14
0x18000717e  mov     r8, [rbp+var_28]
0x180007182  mov     rdx, [rbp+arg_18]
0x180007186  mov     rcx, [rbp+var_38]
0x18000718a  call    cs:__imp_ASN1BERDecEndOfContents
0x180007190  test    eax, eax
0x180007192  jz      loc_1800070B0
0x180007198  mov     r8, [rbp+var_18]
0x18000719c  mov     rcx, rsi
0x18000719f  mov     rdx, [rbp+var_38]
0x1800071a3  call    cs:__imp_ASN1BERDecEndOfContents
0x1800071a9  test    eax, eax
0x1800071ab  jz      loc_1800070B0
0x1800071b1  mov     r8, [rbp+var_10]
0x1800071b5  mov     rcx, rdi
0x1800071b8  mov     rdx, [rbp+var_40]
0x1800071bc  call    cs:__imp_ASN1BERDecEndOfContents
0x1800071c2  test    eax, eax
0x1800071c4  mov     ecx, r14d
0x1800071c7  setnz   cl
0x1800071ca  mov     eax, ecx
0x1800071cc  jmp     loc_1800070B2
```
