# ASN1Enc_PKERB_TICKET_EXTENSIONS

- ea: `0x180026a20`
- end: `0x180026a87`
- name: `ASN1Enc_PKERB_TICKET_EXTENSIONS`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800032e0`

## callees

- `0x180021e38`
- `0x180026a20`

## import_xrefs

- `MSASN1!ASN1BEREncEndOfContents` at `0x180026a69`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180026a69`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180026a45`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180026a45`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_PKERB_TICKET_EXTENSIONS(__int64 a1, __int64 a2, unsigned int *a3)
{
  int i; // eax
  __int64 v6; // rdx
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  for ( i = ASN1BEREncExplicitTag(a1, 16, &v8); i; i = ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq(a1, v6, a3 + 2) )
  {
    a3 = *(unsigned int **)a3;
    if ( !a3 )
      return (unsigned int)ASN1BEREncEndOfContents(a1, v8) != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180026a20  mov     rax, rsp
0x180026a23  mov     [rax+8], rbx
0x180026a27  mov     [rax+10h], edx
0x180026a2a  push    rdi
0x180026a2b  sub     rsp, 20h
0x180026a2f  mov     rbx, r8
0x180026a32  mov     dword ptr [rax+10h], 0
0x180026a39  lea     r8, [rax+10h]
0x180026a3d  mov     edx, 10h
0x180026a42  mov     rdi, rcx
0x180026a45  call    cs:__imp_ASN1BEREncExplicitTag
0x180026a4b  test    eax, eax
0x180026a4d  jz      short loc_180026A7A
0x180026a4f  mov     rbx, [rbx]
0x180026a52  mov     rcx, rdi
0x180026a55  test    rbx, rbx
0x180026a58  jz      short loc_180026A65
0x180026a5a  lea     r8, [rbx+8]
0x180026a5e  call    ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq
0x180026a63  jmp     short loc_180026A4B
0x180026a65  mov     edx, [rsp+28h+arg_8]
0x180026a69  call    cs:__imp_ASN1BEREncEndOfContents
0x180026a6f  xor     ecx, ecx
0x180026a71  test    eax, eax
0x180026a73  setnz   cl
0x180026a76  mov     eax, ecx
0x180026a78  jmp     short loc_180026A7C
0x180026a7a  xor     eax, eax
0x180026a7c  mov     rbx, [rsp+28h+arg_0]
0x180026a81  add     rsp, 20h
0x180026a85  pop     rdi
0x180026a86  retn
```
