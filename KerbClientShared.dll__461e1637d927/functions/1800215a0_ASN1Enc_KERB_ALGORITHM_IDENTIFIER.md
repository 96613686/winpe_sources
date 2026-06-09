# ASN1Enc_KERB_ALGORITHM_IDENTIFIER

- ea: `0x1800215a0`
- end: `0x180021622`
- name: `ASN1Enc_KERB_ALGORITHM_IDENTIFIER`
- size: `130`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180021d98`
- `0x1800255dc`
- `0x18002594c`
- `0x180026380`
- `0x180026b10`

## callees

- `0x1800215a0`

## import_xrefs

- `MSASN1!ASN1BEREncObjectIdentifier` at `0x1800215dd`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x1800215dd`
- `MSASN1!ASN1BEREncOpenType` at `0x1800215f3`
- `MSASN1!ASN1BEREncOpenType` at `0x1800215f3`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180021604`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180021604`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800215c7`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800215c7`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_ALGORITHM_IDENTIFIER(__int64 a1, __int64 a2, char *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  return (unsigned int)ASN1BEREncExplicitTag(a1, a2, &v6)
      && (unsigned int)ASN1BEREncObjectIdentifier(a1, 6, a3 + 8)
      && (*a3 >= 0 || (unsigned int)ASN1BEREncOpenType(a1, a3 + 16))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6) != 0;
}

```

## disassembly

```asm
0x1800215a0  mov     [rsp+arg_0], rbx
0x1800215a5  push    rdi
0x1800215a6  sub     rsp, 20h
0x1800215aa  test    edx, edx
0x1800215ac  mov     [rsp+28h+arg_8], 0
0x1800215b4  mov     eax, 10h
0x1800215b9  mov     rbx, r8
0x1800215bc  cmovz   edx, eax
0x1800215bf  lea     r8, [rsp+28h+arg_8]
0x1800215c4  mov     rdi, rcx
0x1800215c7  call    cs:__imp_ASN1BEREncExplicitTag
0x1800215cd  test    eax, eax
0x1800215cf  jz      short loc_180021615
0x1800215d1  lea     r8, [rbx+8]
0x1800215d5  mov     edx, 6
0x1800215da  mov     rcx, rdi
0x1800215dd  call    cs:__imp_ASN1BEREncObjectIdentifier
0x1800215e3  test    eax, eax
0x1800215e5  jz      short loc_180021615
0x1800215e7  cmp     byte ptr [rbx], 0
0x1800215ea  jge     short loc_1800215FD
0x1800215ec  lea     rdx, [rbx+10h]
0x1800215f0  mov     rcx, rdi
0x1800215f3  call    cs:__imp_ASN1BEREncOpenType
0x1800215f9  test    eax, eax
0x1800215fb  jz      short loc_180021615
0x1800215fd  mov     edx, [rsp+28h+arg_8]
0x180021601  mov     rcx, rdi
0x180021604  call    cs:__imp_ASN1BEREncEndOfContents
0x18002160a  xor     ecx, ecx
0x18002160c  test    eax, eax
0x18002160e  setnz   cl
0x180021611  mov     eax, ecx
0x180021613  jmp     short loc_180021617
0x180021615  xor     eax, eax
0x180021617  mov     rbx, [rsp+28h+arg_0]
0x18002161c  add     rsp, 20h
0x180021620  pop     rdi
0x180021621  retn
```
