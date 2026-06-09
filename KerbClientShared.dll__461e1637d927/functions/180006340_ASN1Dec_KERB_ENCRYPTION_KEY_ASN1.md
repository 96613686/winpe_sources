# ASN1Dec_KERB_ENCRYPTION_KEY_ASN1

- ea: `0x180006340`
- end: `0x18000645d`
- name: `ASN1Dec_KERB_ENCRYPTION_KEY_ASN1`
- size: `285`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180008240`
- `0x180019560`
- `0x18001a290`
- `0x18001abe0`
- `0x18001ad04`
- `0x18001c840`
- `0x18001df80`
- `0x18001e0c0`
- `0x18001e260`

## callees

- `0x180006340`

## import_xrefs

- `MSASN1!ASN1BERDecExplicitTag` at `0x18000637a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000639c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800063f2`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000637a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000639c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800063f2`
- `MSASN1!ASN1BERDecS32Val` at `0x1800063b7`
- `MSASN1!ASN1BERDecS32Val` at `0x1800063b7`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800063d4`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180006423`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000643a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800063d4`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180006423`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000643a`
- `MSASN1!ASN1BERDecOctetString` at `0x18000640a`
- `MSASN1!ASN1BERDecOctetString` at `0x18000640a`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_ENCRYPTION_KEY_ASN1(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  _QWORD v8[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  v6 = 0;
  v8[0] = 0;
  v9 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  v7 = 0;
  return (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v6, v8)
      && (unsigned int)ASN1BERDecExplicitTag(v6, 0x80000000LL, &v9, &v7)
      && (unsigned int)ASN1BERDecS32Val(v9, 2, a3)
      && (unsigned int)ASN1BERDecEndOfContents(v6, v9, v7)
      && (unsigned int)ASN1BERDecExplicitTag(v6, 2147483649LL, &v9, &v7)
      && (unsigned int)ASN1BERDecOctetString(v9, 4, a3 + 8)
      && (unsigned int)ASN1BERDecEndOfContents(v6, v9, v7)
      && (unsigned int)ASN1BERDecEndOfContents(a1, v6, v8[0]) != 0;
}

```

## disassembly

```asm
0x180006340  mov     r11, rsp
0x180006343  mov     [r11+8], rbx
0x180006347  mov     [r11+10h], rsi
0x18000634b  push    rdi
0x18000634c  sub     rsp, 40h
0x180006350  xor     esi, esi
0x180006352  lea     r9, [r11-18h]
0x180006356  test    edx, edx
0x180006358  mov     [r11-28h], rsi
0x18000635c  mov     eax, 10h
0x180006361  mov     [r11-18h], rsi
0x180006365  mov     rbx, r8
0x180006368  mov     [r11+20h], rsi
0x18000636c  cmovz   edx, eax
0x18000636f  mov     [r11-20h], rsi
0x180006373  lea     r8, [r11-28h]
0x180006377  mov     rdi, rcx
0x18000637a  call    cs:__imp_ASN1BERDecExplicitTag
0x180006380  test    eax, eax
0x180006382  jz      loc_180006459
0x180006388  mov     rcx, [rsp+48h+var_28]
0x18000638d  lea     r9, [rsp+48h+var_20]
0x180006392  lea     r8, [rsp+48h+arg_18]
0x180006397  mov     edx, 80000000h
0x18000639c  call    cs:__imp_ASN1BERDecExplicitTag
0x1800063a2  test    eax, eax
0x1800063a4  jz      loc_180006459
0x1800063aa  mov     rcx, [rsp+48h+arg_18]
0x1800063af  mov     r8, rbx
0x1800063b2  mov     edx, 2
0x1800063b7  call    cs:__imp_ASN1BERDecS32Val
0x1800063bd  test    eax, eax
0x1800063bf  jz      loc_180006459
0x1800063c5  mov     r8, [rsp+48h+var_20]
0x1800063ca  mov     rdx, [rsp+48h+arg_18]
0x1800063cf  mov     rcx, [rsp+48h+var_28]
0x1800063d4  call    cs:__imp_ASN1BERDecEndOfContents
0x1800063da  test    eax, eax
0x1800063dc  jz      short loc_180006459
0x1800063de  mov     rcx, [rsp+48h+var_28]
0x1800063e3  lea     r9, [rsp+48h+var_20]
0x1800063e8  lea     r8, [rsp+48h+arg_18]
0x1800063ed  mov     edx, 80000001h
0x1800063f2  call    cs:__imp_ASN1BERDecExplicitTag
0x1800063f8  test    eax, eax
0x1800063fa  jz      short loc_180006459
0x1800063fc  mov     rcx, [rsp+48h+arg_18]
0x180006401  lea     r8, [rbx+8]
0x180006405  mov     edx, 4
0x18000640a  call    cs:__imp_ASN1BERDecOctetString
0x180006410  test    eax, eax
0x180006412  jz      short loc_180006459
0x180006414  mov     r8, [rsp+48h+var_20]
0x180006419  mov     rdx, [rsp+48h+arg_18]
0x18000641e  mov     rcx, [rsp+48h+var_28]
0x180006423  call    cs:__imp_ASN1BERDecEndOfContents
0x180006429  test    eax, eax
0x18000642b  jz      short loc_180006459
0x18000642d  mov     r8, [rsp+48h+var_18]
0x180006432  mov     rcx, rdi
0x180006435  mov     rdx, [rsp+48h+var_28]
0x18000643a  call    cs:__imp_ASN1BERDecEndOfContents
0x180006440  test    eax, eax
0x180006442  mov     ecx, esi
0x180006444  setnz   cl
0x180006447  mov     eax, ecx
0x180006449  mov     rbx, [rsp+48h+arg_0]
0x18000644e  mov     rsi, [rsp+48h+arg_8]
0x180006453  add     rsp, 40h
0x180006457  pop     rdi
0x180006458  retn
0x180006459  xor     eax, eax
0x18000645b  jmp     short loc_180006449
```
