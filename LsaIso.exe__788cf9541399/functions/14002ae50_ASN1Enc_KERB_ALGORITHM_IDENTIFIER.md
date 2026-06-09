# ASN1Enc_KERB_ALGORITHM_IDENTIFIER

- ea: `0x14002ae50`
- end: `0x14002aed2`
- name: `ASN1Enc_KERB_ALGORITHM_IDENTIFIER`
- size: `130`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14002b898`
- `0x1400304fc`
- `0x14003086c`
- `0x1400317f0`
- `0x140032210`

## callees

- `0x14002ae50`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ae77`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ae77`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002aeb4`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002aeb4`
- `MSASN1!ASN1BEREncOpenType` at `0x14002aea3`
- `MSASN1!ASN1BEREncOpenType` at `0x14002aea3`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x14002ae8d`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x14002ae8d`

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
0x14002ae50  mov     [rsp+arg_0], rbx
0x14002ae55  push    rdi
0x14002ae56  sub     rsp, 20h
0x14002ae5a  test    edx, edx
0x14002ae5c  mov     [rsp+28h+arg_8], 0
0x14002ae64  mov     eax, 10h
0x14002ae69  mov     rbx, r8
0x14002ae6c  cmovz   edx, eax
0x14002ae6f  lea     r8, [rsp+28h+arg_8]
0x14002ae74  mov     rdi, rcx
0x14002ae77  call    cs:__imp_ASN1BEREncExplicitTag
0x14002ae7d  test    eax, eax
0x14002ae7f  jz      short loc_14002AEC5
0x14002ae81  lea     r8, [rbx+8]
0x14002ae85  mov     edx, 6
0x14002ae8a  mov     rcx, rdi
0x14002ae8d  call    cs:__imp_ASN1BEREncObjectIdentifier
0x14002ae93  test    eax, eax
0x14002ae95  jz      short loc_14002AEC5
0x14002ae97  cmp     byte ptr [rbx], 0
0x14002ae9a  jge     short loc_14002AEAD
0x14002ae9c  lea     rdx, [rbx+10h]
0x14002aea0  mov     rcx, rdi
0x14002aea3  call    cs:__imp_ASN1BEREncOpenType
0x14002aea9  test    eax, eax
0x14002aeab  jz      short loc_14002AEC5
0x14002aead  mov     edx, [rsp+28h+arg_8]
0x14002aeb1  mov     rcx, rdi
0x14002aeb4  call    cs:__imp_ASN1BEREncEndOfContents
0x14002aeba  xor     ecx, ecx
0x14002aebc  test    eax, eax
0x14002aebe  setnz   cl
0x14002aec1  mov     eax, ecx
0x14002aec3  jmp     short loc_14002AEC7
0x14002aec5  xor     eax, eax
0x14002aec7  mov     rbx, [rsp+28h+arg_0]
0x14002aecc  add     rsp, 20h
0x14002aed0  pop     rdi
0x14002aed1  retn
```
