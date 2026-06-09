# ASN1Dec_KERB_CHECKSUM

- ea: `0x180006ee0`
- end: `0x18000700b`
- name: `ASN1Dec_KERB_CHECKSUM`
- size: `299`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180018870`
- `0x180019560`
- `0x18001c940`
- `0x18001e260`
- `0x18001e670`
- `0x18001f858`
- `0x18001f9fc`
- `0x180020020`

## callees

- `0x180006ee0`

## import_xrefs

- `MSASN1!ASN1BERDecExplicitTag` at `0x180006f1a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180006f3c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180006f92`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180006f1a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180006f3c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180006f92`
- `MSASN1!ASN1BERDecS32Val` at `0x180006f57`
- `MSASN1!ASN1BERDecS32Val` at `0x180006f57`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180006f74`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180006fc3`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180006fda`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180006f74`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180006fc3`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180006fda`
- `MSASN1!ASN1BERDecOctetString` at `0x180006faa`
- `MSASN1!ASN1BERDecOctetString` at `0x180006faa`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_CHECKSUM(__int64 a1, __int64 a2, __int64 a3)
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
0x180006ee0  mov     r11, rsp
0x180006ee3  mov     [r11+8], rbx
0x180006ee7  mov     [r11+10h], rsi
0x180006eeb  push    rdi
0x180006eec  sub     rsp, 40h
0x180006ef0  xor     esi, esi
0x180006ef2  lea     r9, [r11-18h]
0x180006ef6  test    edx, edx
0x180006ef8  mov     [r11-28h], rsi
0x180006efc  mov     eax, 10h
0x180006f01  mov     [r11-18h], rsi
0x180006f05  mov     rbx, r8
0x180006f08  mov     [r11+20h], rsi
0x180006f0c  cmovz   edx, eax
0x180006f0f  mov     [r11-20h], rsi
0x180006f13  lea     r8, [r11-28h]
0x180006f17  mov     rdi, rcx
0x180006f1a  call    cs:__imp_ASN1BERDecExplicitTag
0x180006f20  test    eax, eax
0x180006f22  jz      loc_180006FF9
0x180006f28  mov     rcx, [rsp+48h+var_28]
0x180006f2d  lea     r9, [rsp+48h+var_20]
0x180006f32  lea     r8, [rsp+48h+arg_18]
0x180006f37  mov     edx, 80000000h
0x180006f3c  call    cs:__imp_ASN1BERDecExplicitTag
0x180006f42  test    eax, eax
0x180006f44  jz      loc_180006FF9
0x180006f4a  mov     rcx, [rsp+48h+arg_18]
0x180006f4f  mov     r8, rbx
0x180006f52  mov     edx, 2
0x180006f57  call    cs:__imp_ASN1BERDecS32Val
0x180006f5d  test    eax, eax
0x180006f5f  jz      loc_180006FF9
0x180006f65  mov     r8, [rsp+48h+var_20]
0x180006f6a  mov     rdx, [rsp+48h+arg_18]
0x180006f6f  mov     rcx, [rsp+48h+var_28]
0x180006f74  call    cs:__imp_ASN1BERDecEndOfContents
0x180006f7a  test    eax, eax
0x180006f7c  jz      short loc_180006FF9
0x180006f7e  mov     rcx, [rsp+48h+var_28]
0x180006f83  lea     r9, [rsp+48h+var_20]
0x180006f88  lea     r8, [rsp+48h+arg_18]
0x180006f8d  mov     edx, 80000001h
0x180006f92  call    cs:__imp_ASN1BERDecExplicitTag
0x180006f98  test    eax, eax
0x180006f9a  jz      short loc_180006FF9
0x180006f9c  mov     rcx, [rsp+48h+arg_18]
0x180006fa1  lea     r8, [rbx+8]
0x180006fa5  mov     edx, 4
0x180006faa  call    cs:__imp_ASN1BERDecOctetString
0x180006fb0  test    eax, eax
0x180006fb2  jz      short loc_180006FF9
0x180006fb4  mov     r8, [rsp+48h+var_20]
0x180006fb9  mov     rdx, [rsp+48h+arg_18]
0x180006fbe  mov     rcx, [rsp+48h+var_28]
0x180006fc3  call    cs:__imp_ASN1BERDecEndOfContents
0x180006fc9  test    eax, eax
0x180006fcb  jz      short loc_180006FF9
0x180006fcd  mov     r8, [rsp+48h+var_18]
0x180006fd2  mov     rcx, rdi
0x180006fd5  mov     rdx, [rsp+48h+var_28]
0x180006fda  call    cs:__imp_ASN1BERDecEndOfContents
0x180006fe0  test    eax, eax
0x180006fe2  mov     ecx, esi
0x180006fe4  setnz   cl
0x180006fe7  mov     eax, ecx
0x180006fe9  mov     rbx, [rsp+48h+arg_0]
0x180006fee  mov     rsi, [rsp+48h+arg_8]
0x180006ff3  add     rsp, 40h
0x180006ff7  pop     rdi
0x180006ff8  retn
0x180006ff9  mov     rbx, [rsp+48h+arg_0]
0x180006ffe  xor     eax, eax
0x180007000  mov     rsi, [rsp+48h+arg_8]
0x180007005  add     rsp, 40h
0x180007009  pop     rdi
0x18000700a  retn
```
