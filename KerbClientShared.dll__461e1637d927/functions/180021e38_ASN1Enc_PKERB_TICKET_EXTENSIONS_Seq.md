# ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq

- ea: `0x180021e38`
- end: `0x180021f1a`
- name: `ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq`
- size: `226`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009728`
- `0x180022a60`
- `0x1800231e0`
- `0x1800234a0`
- `0x180024404`
- `0x180024710`
- `0x1800250ec`
- `0x180026a20`

## callees

- `0x180021e38`

## import_xrefs

- `MSASN1!ASN1DEREncOctetString` at `0x180021eda`
- `MSASN1!ASN1DEREncOctetString` at `0x180021eda`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180021ea9`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180021eeb`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180021efc`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180021ea9`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180021eeb`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180021efc`
- `MSASN1!ASN1BEREncS32` at `0x180021e98`
- `MSASN1!ASN1BEREncS32` at `0x180021e98`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180021e64`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180021e7f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180021ec0`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180021e64`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180021e7f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180021ec0`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  return (unsigned int)ASN1BEREncExplicitTag(a1, 16, &v7)
      && (unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v6)
      && (unsigned int)ASN1BEREncS32(a1, 2, *a3)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6)
      && (unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v6)
      && (unsigned int)ASN1DEREncOctetString(a1, 4, a3[2], *((_QWORD *)a3 + 2))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v7) != 0;
}

```

## disassembly

```asm
0x180021e38  mov     rax, rsp
0x180021e3b  mov     [rax+8], rbx
0x180021e3f  mov     [rax+10h], edx
0x180021e42  push    rdi
0x180021e43  sub     rsp, 20h
0x180021e47  mov     rdi, r8
0x180021e4a  mov     dword ptr [rax+20h], 0
0x180021e51  lea     r8, [rax+20h]
0x180021e55  mov     dword ptr [rax+10h], 0
0x180021e5c  mov     edx, 10h
0x180021e61  mov     rbx, rcx
0x180021e64  call    cs:__imp_ASN1BEREncExplicitTag
0x180021e6a  test    eax, eax
0x180021e6c  jz      loc_180021F0D
0x180021e72  lea     r8, [rsp+28h+arg_8]
0x180021e77  mov     edx, 80000000h
0x180021e7c  mov     rcx, rbx
0x180021e7f  call    cs:__imp_ASN1BEREncExplicitTag
0x180021e85  test    eax, eax
0x180021e87  jz      loc_180021F0D
0x180021e8d  mov     r8d, [rdi]
0x180021e90  mov     edx, 2
0x180021e95  mov     rcx, rbx
0x180021e98  call    cs:__imp_ASN1BEREncS32
0x180021e9e  test    eax, eax
0x180021ea0  jz      short loc_180021F0D
0x180021ea2  mov     edx, [rsp+28h+arg_8]
0x180021ea6  mov     rcx, rbx
0x180021ea9  call    cs:__imp_ASN1BEREncEndOfContents
0x180021eaf  test    eax, eax
0x180021eb1  jz      short loc_180021F0D
0x180021eb3  lea     r8, [rsp+28h+arg_8]
0x180021eb8  mov     edx, 80000001h
0x180021ebd  mov     rcx, rbx
0x180021ec0  call    cs:__imp_ASN1BEREncExplicitTag
0x180021ec6  test    eax, eax
0x180021ec8  jz      short loc_180021F0D
0x180021eca  mov     r9, [rdi+10h]
0x180021ece  mov     edx, 4
0x180021ed3  mov     r8d, [rdi+8]
0x180021ed7  mov     rcx, rbx
0x180021eda  call    cs:__imp_ASN1DEREncOctetString
0x180021ee0  test    eax, eax
0x180021ee2  jz      short loc_180021F0D
0x180021ee4  mov     edx, [rsp+28h+arg_8]
0x180021ee8  mov     rcx, rbx
0x180021eeb  call    cs:__imp_ASN1BEREncEndOfContents
0x180021ef1  test    eax, eax
0x180021ef3  jz      short loc_180021F0D
0x180021ef5  mov     edx, [rsp+28h+arg_18]
0x180021ef9  mov     rcx, rbx
0x180021efc  call    cs:__imp_ASN1BEREncEndOfContents
0x180021f02  xor     ecx, ecx
0x180021f04  test    eax, eax
0x180021f06  setnz   cl
0x180021f09  mov     eax, ecx
0x180021f0b  jmp     short loc_180021F0F
0x180021f0d  xor     eax, eax
0x180021f0f  mov     rbx, [rsp+28h+arg_0]
0x180021f14  add     rsp, 20h
0x180021f18  pop     rdi
0x180021f19  retn
```
