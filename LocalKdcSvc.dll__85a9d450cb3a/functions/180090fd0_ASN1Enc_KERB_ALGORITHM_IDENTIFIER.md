# ASN1Enc_KERB_ALGORITHM_IDENTIFIER

- ea: `0x180090fd0`
- end: `0x180091052`
- name: `ASN1Enc_KERB_ALGORITHM_IDENTIFIER`
- size: `130`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180091a18`
- `0x18009667c`
- `0x1800969ec`
- `0x180097970`
- `0x180098390`

## callees

- `0x180090fd0`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x180090ff7`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180090ff7`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180091034`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180091034`
- `MSASN1!ASN1BEREncOpenType` at `0x180091023`
- `MSASN1!ASN1BEREncOpenType` at `0x180091023`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x18009100d`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x18009100d`

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
0x180090fd0  mov     [rsp+arg_0], rbx
0x180090fd5  push    rdi
0x180090fd6  sub     rsp, 20h
0x180090fda  test    edx, edx
0x180090fdc  mov     [rsp+28h+arg_8], 0
0x180090fe4  mov     eax, 10h
0x180090fe9  mov     rbx, r8
0x180090fec  cmovz   edx, eax
0x180090fef  lea     r8, [rsp+28h+arg_8]
0x180090ff4  mov     rdi, rcx
0x180090ff7  call    cs:__imp_ASN1BEREncExplicitTag
0x180090ffd  test    eax, eax
0x180090fff  jz      short loc_180091045
0x180091001  lea     r8, [rbx+8]
0x180091005  mov     edx, 6
0x18009100a  mov     rcx, rdi
0x18009100d  call    cs:__imp_ASN1BEREncObjectIdentifier
0x180091013  test    eax, eax
0x180091015  jz      short loc_180091045
0x180091017  cmp     byte ptr [rbx], 0
0x18009101a  jge     short loc_18009102D
0x18009101c  lea     rdx, [rbx+10h]
0x180091020  mov     rcx, rdi
0x180091023  call    cs:__imp_ASN1BEREncOpenType
0x180091029  test    eax, eax
0x18009102b  jz      short loc_180091045
0x18009102d  mov     edx, [rsp+28h+arg_8]
0x180091031  mov     rcx, rdi
0x180091034  call    cs:__imp_ASN1BEREncEndOfContents
0x18009103a  xor     ecx, ecx
0x18009103c  test    eax, eax
0x18009103e  setnz   cl
0x180091041  mov     eax, ecx
0x180091043  jmp     short loc_180091047
0x180091045  xor     eax, eax
0x180091047  mov     rbx, [rsp+28h+arg_0]
0x18009104c  add     rsp, 20h
0x180091050  pop     rdi
0x180091051  retn
```
