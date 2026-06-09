# ASN1Dec_KERB_ENCRYPTED_DATA

- ea: `0x180004fa0`
- end: `0x180005127`
- name: `ASN1Dec_KERB_ENCRYPTED_DATA`
- size: `391`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180004860`
- `0x180004c90`
- `0x180018740`
- `0x1800190c0`
- `0x180019280`
- `0x18001a0c0`
- `0x18001b6a8`
- `0x18001bf3c`
- `0x18001ce20`
- `0x18001dbc0`
- `0x18001f774`
- `0x18001f858`

## callees

- `0x180004fa0`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x18000504a`
- `MSASN1!ASN1BERDecPeekTag` at `0x18000504a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180004fdc`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180004fff`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000506a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800050eb`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180004fdc`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180004fff`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000506a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800050eb`
- `MSASN1!ASN1BERDecS32Val` at `0x18000501a`
- `MSASN1!ASN1BERDecS32Val` at `0x180005102`
- `MSASN1!ASN1BERDecS32Val` at `0x18000501a`
- `MSASN1!ASN1BERDecS32Val` at `0x180005102`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005034`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005097`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800050ac`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005118`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005034`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005097`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800050ac`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005118`
- `MSASN1!ASN1BERDecOctetString` at `0x180005081`
- `MSASN1!ASN1BERDecOctetString` at `0x180005081`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_ENCRYPTED_DATA(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v7; // rcx
  __int64 v8; // [rsp+20h] [rbp-20h] BYREF
  __int64 v9; // [rsp+28h] [rbp-18h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+68h] [rbp+28h] BYREF
  __int64 v12; // [rsp+78h] [rbp+38h] BYREF

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
     || (v7 = v8, *a3 |= 0x80u, (unsigned int)ASN1BERDecExplicitTag(v7, 2147483649LL, &v12, &v9))
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
0x180004fa0  mov     [rsp-18h+arg_0], rbx
0x180004fa5  push    rbp
0x180004fa6  push    rsi
0x180004fa7  push    rdi
0x180004fa8  mov     rbp, rsp
0x180004fab  sub     rsp, 40h
0x180004faf  xor     esi, esi
0x180004fb1  lea     r9, [rbp+var_10]
0x180004fb5  test    edx, edx
0x180004fb7  mov     [rbp+var_20], rsi
0x180004fbb  mov     eax, 10h
0x180004fc0  mov     [rbp+var_10], rsi
0x180004fc4  mov     rbx, r8
0x180004fc7  mov     [rbp+arg_18], rsi
0x180004fcb  cmovz   edx, eax
0x180004fce  mov     [rbp+var_18], rsi
0x180004fd2  lea     r8, [rbp+var_20]
0x180004fd6  mov     [rbp+arg_8], esi
0x180004fd9  mov     rdi, rcx
0x180004fdc  call    cs:__imp_ASN1BERDecExplicitTag
0x180004fe2  test    eax, eax
0x180004fe4  jz      loc_1800050C8
0x180004fea  mov     rcx, [rbp+var_20]
0x180004fee  lea     r9, [rbp+var_18]
0x180004ff2  xor     eax, eax
0x180004ff4  lea     r8, [rbp+arg_18]
0x180004ff8  mov     edx, 80000000h
0x180004ffd  mov     [rbx], al
0x180004fff  call    cs:__imp_ASN1BERDecExplicitTag
0x180005005  test    eax, eax
0x180005007  jz      loc_1800050C8
0x18000500d  mov     rcx, [rbp+arg_18]
0x180005011  lea     r8, [rbx+4]
0x180005015  mov     edx, 2
0x18000501a  call    cs:__imp_ASN1BERDecS32Val
0x180005020  test    eax, eax
0x180005022  jz      loc_1800050C8
0x180005028  mov     r8, [rbp+var_18]
0x18000502c  mov     rdx, [rbp+arg_18]
0x180005030  mov     rcx, [rbp+var_20]
0x180005034  call    cs:__imp_ASN1BERDecEndOfContents
0x18000503a  test    eax, eax
0x18000503c  jz      loc_1800050C8
0x180005042  mov     rcx, [rbp+var_20]
0x180005046  lea     rdx, [rbp+arg_8]
0x18000504a  call    cs:__imp_ASN1BERDecPeekTag
0x180005050  cmp     [rbp+arg_8], 80000001h
0x180005057  jz      short loc_1800050D7
0x180005059  mov     rcx, [rbp+var_20]
0x18000505d  lea     r9, [rbp+var_18]
0x180005061  lea     r8, [rbp+arg_18]
0x180005065  mov     edx, 80000002h
0x18000506a  call    cs:__imp_ASN1BERDecExplicitTag
0x180005070  test    eax, eax
0x180005072  jz      short loc_1800050C8
0x180005074  mov     rcx, [rbp+arg_18]
0x180005078  lea     r8, [rbx+10h]
0x18000507c  mov     edx, 4
0x180005081  call    cs:__imp_ASN1BERDecOctetString
0x180005087  test    eax, eax
0x180005089  jz      short loc_1800050C8
0x18000508b  mov     r8, [rbp+var_18]
0x18000508f  mov     rdx, [rbp+arg_18]
0x180005093  mov     rcx, [rbp+var_20]
0x180005097  call    cs:__imp_ASN1BERDecEndOfContents
0x18000509d  test    eax, eax
0x18000509f  jz      short loc_1800050C8
0x1800050a1  mov     r8, [rbp+var_10]
0x1800050a5  mov     rcx, rdi
0x1800050a8  mov     rdx, [rbp+var_20]
0x1800050ac  call    cs:__imp_ASN1BERDecEndOfContents
0x1800050b2  test    eax, eax
0x1800050b4  mov     ecx, esi
0x1800050b6  setnz   cl
0x1800050b9  mov     eax, ecx
0x1800050bb  mov     rbx, [rsp+40h+arg_0]
0x1800050c0  add     rsp, 40h
0x1800050c4  pop     rdi
0x1800050c5  pop     rsi
0x1800050c6  pop     rbp
0x1800050c7  retn
0x1800050c8  mov     rbx, [rsp+40h+arg_0]
0x1800050cd  xor     eax, eax
0x1800050cf  add     rsp, 40h
0x1800050d3  pop     rdi
0x1800050d4  pop     rsi
0x1800050d5  pop     rbp
0x1800050d6  retn
0x1800050d7  mov     rcx, [rbp+var_20]
0x1800050db  lea     r9, [rbp+var_18]
0x1800050df  or      byte ptr [rbx], 80h
0x1800050e2  lea     r8, [rbp+arg_18]
0x1800050e6  mov     edx, 80000001h
0x1800050eb  call    cs:__imp_ASN1BERDecExplicitTag
0x1800050f1  test    eax, eax
0x1800050f3  jz      short loc_1800050C8
0x1800050f5  mov     rcx, [rbp+arg_18]
0x1800050f9  lea     r8, [rbx+8]
0x1800050fd  mov     edx, 2
0x180005102  call    cs:__imp_ASN1BERDecS32Val
0x180005108  test    eax, eax
0x18000510a  jz      short loc_1800050C8
0x18000510c  mov     r8, [rbp+var_18]
0x180005110  mov     rdx, [rbp+arg_18]
0x180005114  mov     rcx, [rbp+var_20]
0x180005118  call    cs:__imp_ASN1BERDecEndOfContents
0x18000511e  test    eax, eax
0x180005120  jz      short loc_1800050C8
0x180005122  jmp     loc_180005059
```
