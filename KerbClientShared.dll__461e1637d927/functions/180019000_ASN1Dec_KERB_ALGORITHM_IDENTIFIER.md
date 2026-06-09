# ASN1Dec_KERB_ALGORITHM_IDENTIFIER

- ea: `0x180019000`
- end: `0x1800190b5`
- name: `ASN1Dec_KERB_ALGORITHM_IDENTIFIER`
- size: `181`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180019cc8`
- `0x18001ea18`
- `0x18001ee68`
- `0x18001fd80`
- `0x180020b20`

## callees

- `0x180019000`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x18001906a`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001906a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001903c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001903c`
- `MSASN1!ASN1BERDecOpenType2` at `0x180019080`
- `MSASN1!ASN1BERDecOpenType2` at `0x180019080`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x180019056`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x180019056`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180019097`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180019097`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_ALGORITHM_IDENTIFIER(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v8[0] = 0;
  v9 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v10, v8)
    && (v5 = v10, *a3 = 0, (unsigned int)ASN1BERDecObjectIdentifier(v5, 6, a3 + 8))
    && (!(unsigned int)ASN1BERDecPeekTag(v10, &v9)
     || (v6 = v10, *a3 |= 0x80u, (unsigned int)ASN1BERDecOpenType2(v6, a3 + 16))) )
  {
    return (unsigned int)ASN1BERDecEndOfContents(a1, v10, v8[0]) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180019000  mov     r11, rsp
0x180019003  mov     [r11+8], rbx
0x180019007  push    rdi
0x180019008  sub     rsp, 30h
0x18001900c  test    edx, edx
0x18001900e  mov     qword ptr [r11+20h], 0
0x180019016  mov     eax, 10h
0x18001901b  mov     qword ptr [r11-18h], 0
0x180019023  mov     rbx, r8
0x180019026  mov     [rsp+38h+arg_8], 0
0x18001902e  cmovz   edx, eax
0x180019031  lea     r9, [r11-18h]
0x180019035  lea     r8, [r11+20h]
0x180019039  mov     rdi, rcx
0x18001903c  call    cs:__imp_ASN1BERDecExplicitTag
0x180019042  test    eax, eax
0x180019044  jz      short loc_1800190A8
0x180019046  mov     rcx, [rsp+38h+arg_18]
0x18001904b  lea     r8, [rbx+8]
0x18001904f  xor     eax, eax
0x180019051  mov     [rbx], al
0x180019053  lea     edx, [rax+6]
0x180019056  call    cs:__imp_ASN1BERDecObjectIdentifier
0x18001905c  test    eax, eax
0x18001905e  jz      short loc_1800190A8
0x180019060  mov     rcx, [rsp+38h+arg_18]
0x180019065  lea     rdx, [rsp+38h+arg_8]
0x18001906a  call    cs:__imp_ASN1BERDecPeekTag
0x180019070  test    eax, eax
0x180019072  jz      short loc_18001908A
0x180019074  mov     rcx, [rsp+38h+arg_18]
0x180019079  lea     rdx, [rbx+10h]
0x18001907d  or      byte ptr [rbx], 80h
0x180019080  call    cs:__imp_ASN1BERDecOpenType2
0x180019086  test    eax, eax
0x180019088  jz      short loc_1800190A8
0x18001908a  mov     r8, [rsp+38h+var_18]
0x18001908f  mov     rcx, rdi
0x180019092  mov     rdx, [rsp+38h+arg_18]
0x180019097  call    cs:__imp_ASN1BERDecEndOfContents
0x18001909d  xor     ecx, ecx
0x18001909f  test    eax, eax
0x1800190a1  setnz   cl
0x1800190a4  mov     eax, ecx
0x1800190a6  jmp     short loc_1800190AA
0x1800190a8  xor     eax, eax
0x1800190aa  mov     rbx, [rsp+38h+arg_0]
0x1800190af  add     rsp, 30h
0x1800190b3  pop     rdi
0x1800190b4  retn
```
