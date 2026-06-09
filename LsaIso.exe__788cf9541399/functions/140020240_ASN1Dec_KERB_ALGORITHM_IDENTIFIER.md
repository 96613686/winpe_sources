# ASN1Dec_KERB_ALGORITHM_IDENTIFIER

- ea: `0x140020240`
- end: `0x1400202f5`
- name: `ASN1Dec_KERB_ALGORITHM_IDENTIFIER`
- size: `181`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140020f88`
- `0x140027908`
- `0x140027d58`
- `0x140029264`
- `0x14002a2e0`

## callees

- `0x140020240`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x1400202aa`
- `MSASN1!ASN1BERDecPeekTag` at `0x1400202aa`
- `MSASN1!ASN1BERDecExplicitTag` at `0x14002027c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x14002027c`
- `MSASN1!ASN1BERDecOpenType2` at `0x1400202c0`
- `MSASN1!ASN1BERDecOpenType2` at `0x1400202c0`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x140020296`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x140020296`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1400202d7`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1400202d7`

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
0x140020240  mov     r11, rsp
0x140020243  mov     [r11+8], rbx
0x140020247  push    rdi
0x140020248  sub     rsp, 30h
0x14002024c  test    edx, edx
0x14002024e  mov     qword ptr [r11+20h], 0
0x140020256  mov     eax, 10h
0x14002025b  mov     qword ptr [r11-18h], 0
0x140020263  mov     rbx, r8
0x140020266  mov     [rsp+38h+arg_8], 0
0x14002026e  cmovz   edx, eax
0x140020271  lea     r9, [r11-18h]
0x140020275  lea     r8, [r11+20h]
0x140020279  mov     rdi, rcx
0x14002027c  call    cs:__imp_ASN1BERDecExplicitTag
0x140020282  test    eax, eax
0x140020284  jz      short loc_1400202E8
0x140020286  mov     rcx, [rsp+38h+arg_18]
0x14002028b  lea     r8, [rbx+8]
0x14002028f  xor     eax, eax
0x140020291  mov     [rbx], al
0x140020293  lea     edx, [rax+6]
0x140020296  call    cs:__imp_ASN1BERDecObjectIdentifier
0x14002029c  test    eax, eax
0x14002029e  jz      short loc_1400202E8
0x1400202a0  mov     rcx, [rsp+38h+arg_18]
0x1400202a5  lea     rdx, [rsp+38h+arg_8]
0x1400202aa  call    cs:__imp_ASN1BERDecPeekTag
0x1400202b0  test    eax, eax
0x1400202b2  jz      short loc_1400202CA
0x1400202b4  mov     rcx, [rsp+38h+arg_18]
0x1400202b9  lea     rdx, [rbx+10h]
0x1400202bd  or      byte ptr [rbx], 80h
0x1400202c0  call    cs:__imp_ASN1BERDecOpenType2
0x1400202c6  test    eax, eax
0x1400202c8  jz      short loc_1400202E8
0x1400202ca  mov     r8, [rsp+38h+var_18]
0x1400202cf  mov     rcx, rdi
0x1400202d2  mov     rdx, [rsp+38h+arg_18]
0x1400202d7  call    cs:__imp_ASN1BERDecEndOfContents
0x1400202dd  xor     ecx, ecx
0x1400202df  test    eax, eax
0x1400202e1  setnz   cl
0x1400202e4  mov     eax, ecx
0x1400202e6  jmp     short loc_1400202EA
0x1400202e8  xor     eax, eax
0x1400202ea  mov     rbx, [rsp+38h+arg_0]
0x1400202ef  add     rsp, 30h
0x1400202f3  pop     rdi
0x1400202f4  retn
```
