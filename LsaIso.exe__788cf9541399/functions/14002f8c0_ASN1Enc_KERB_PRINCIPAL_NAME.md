# ASN1Enc_KERB_PRINCIPAL_NAME

- ea: `0x14002f8c0`
- end: `0x14002f968`
- name: `ASN1Enc_KERB_PRINCIPAL_NAME`
- size: `168`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x14002b330`
- `0x14002ba20`
- `0x14002bcf4`
- `0x14002cb1c`
- `0x14002d2a0`
- `0x14002d7f0`
- `0x14002e0b8`
- `0x14002e4b0`
- `0x14002ea0c`
- `0x14002ec90`
- `0x14002f424`
- `0x14002f600`
- `0x14002f700`
- `0x140030900`
- `0x140030c10`
- `0x140030da0`
- `0x140031090`
- `0x140031344`
- `0x140032010`

## callees

- `0x14002f8c0`
- `0x14002f970`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x14002f8ec`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002f903`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002f8ec`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002f903`
- `MSASN1!ASN1BEREncS32` at `0x14002f918`
- `MSASN1!ASN1BEREncS32` at `0x14002f918`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002f929`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002f94a`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002f929`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002f94a`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_PRINCIPAL_NAME(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int64 v5; // rdx
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  v7 = 0;
  return (unsigned int)ASN1BEREncExplicitTag(a1, 16, &v8)
      && (unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v7)
      && (unsigned int)ASN1BEREncS32(a1, 2, *a3)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v7)
      && (unsigned int)ASN1Enc_KERB_PRINCIPAL_NAME_name_string(a1, v5, a3 + 2)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v8) != 0;
}

```

## disassembly

```asm
0x14002f8c0  mov     rax, rsp
0x14002f8c3  mov     [rax+8], rbx
0x14002f8c7  mov     [rax+10h], edx
0x14002f8ca  push    rdi
0x14002f8cb  sub     rsp, 20h
0x14002f8cf  mov     rdi, r8
0x14002f8d2  mov     dword ptr [rax+20h], 0
0x14002f8d9  lea     r8, [rax+20h]
0x14002f8dd  mov     dword ptr [rax+10h], 0
0x14002f8e4  mov     edx, 10h
0x14002f8e9  mov     rbx, rcx
0x14002f8ec  call    cs:__imp_ASN1BEREncExplicitTag
0x14002f8f2  test    eax, eax
0x14002f8f4  jz      short loc_14002F95B
0x14002f8f6  lea     r8, [rsp+28h+arg_8]
0x14002f8fb  mov     edx, 80000000h
0x14002f900  mov     rcx, rbx
0x14002f903  call    cs:__imp_ASN1BEREncExplicitTag
0x14002f909  test    eax, eax
0x14002f90b  jz      short loc_14002F95B
0x14002f90d  mov     r8d, [rdi]
0x14002f910  mov     edx, 2
0x14002f915  mov     rcx, rbx
0x14002f918  call    cs:__imp_ASN1BEREncS32
0x14002f91e  test    eax, eax
0x14002f920  jz      short loc_14002F95B
0x14002f922  mov     edx, [rsp+28h+arg_8]
0x14002f926  mov     rcx, rbx
0x14002f929  call    cs:__imp_ASN1BEREncEndOfContents
0x14002f92f  test    eax, eax
0x14002f931  jz      short loc_14002F95B
0x14002f933  lea     r8, [rdi+8]
0x14002f937  mov     rcx, rbx
0x14002f93a  call    ASN1Enc_KERB_PRINCIPAL_NAME_name_string
0x14002f93f  test    eax, eax
0x14002f941  jz      short loc_14002F95B
0x14002f943  mov     edx, [rsp+28h+arg_18]
0x14002f947  mov     rcx, rbx
0x14002f94a  call    cs:__imp_ASN1BEREncEndOfContents
0x14002f950  xor     ecx, ecx
0x14002f952  test    eax, eax
0x14002f954  setnz   cl
0x14002f957  mov     eax, ecx
0x14002f959  jmp     short loc_14002F95D
0x14002f95b  xor     eax, eax
0x14002f95d  mov     rbx, [rsp+28h+arg_0]
0x14002f962  add     rsp, 20h
0x14002f966  pop     rdi
0x14002f967  retn
```
