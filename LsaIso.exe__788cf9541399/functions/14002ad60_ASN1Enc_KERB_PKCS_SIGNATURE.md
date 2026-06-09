# ASN1Enc_KERB_PKCS_SIGNATURE

- ea: `0x14002ad60`
- end: `0x14002ae45`
- name: `ASN1Enc_KERB_PKCS_SIGNATURE`
- size: `229`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x14002a8d0`
- `0x14002b330`
- `0x14002bcf4`
- `0x14002c3a4`
- `0x14002c444`
- `0x14002c4f0`
- `0x14002cb1c`
- `0x14002d2a0`
- `0x14002eb00`
- `0x14002ec90`
- `0x14002fd10`
- `0x14002fdf0`
- `0x14002ff30`
- `0x140030220`
- `0x140031220`
- `0x140031344`
- `0x140031610`
- `0x1400319d0`

## callees

- `0x14002ad60`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ad8f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002adaa`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002adeb`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002ad8f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002adaa`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002adeb`
- `MSASN1!ASN1BEREncS32` at `0x14002adc3`
- `MSASN1!ASN1BEREncS32` at `0x14002adc3`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002add4`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002ae16`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002ae27`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002add4`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002ae16`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002ae27`
- `MSASN1!ASN1DEREncOctetString` at `0x14002ae05`
- `MSASN1!ASN1DEREncOctetString` at `0x14002ae05`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_PKCS_SIGNATURE(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  return (unsigned int)ASN1BEREncExplicitTag(a1, a2, &v7)
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
0x14002ad60  mov     [rsp+arg_0], rbx
0x14002ad65  push    rdi
0x14002ad66  sub     rsp, 20h
0x14002ad6a  test    edx, edx
0x14002ad6c  mov     [rsp+28h+arg_18], 0
0x14002ad74  mov     eax, 10h
0x14002ad79  mov     [rsp+28h+arg_8], 0
0x14002ad81  mov     rdi, r8
0x14002ad84  cmovz   edx, eax
0x14002ad87  lea     r8, [rsp+28h+arg_18]
0x14002ad8c  mov     rbx, rcx
0x14002ad8f  call    cs:__imp_ASN1BEREncExplicitTag
0x14002ad95  test    eax, eax
0x14002ad97  jz      loc_14002AE38
0x14002ad9d  lea     r8, [rsp+28h+arg_8]
0x14002ada2  mov     edx, 80000000h
0x14002ada7  mov     rcx, rbx
0x14002adaa  call    cs:__imp_ASN1BEREncExplicitTag
0x14002adb0  test    eax, eax
0x14002adb2  jz      loc_14002AE38
0x14002adb8  mov     r8d, [rdi]
0x14002adbb  mov     edx, 2
0x14002adc0  mov     rcx, rbx
0x14002adc3  call    cs:__imp_ASN1BEREncS32
0x14002adc9  test    eax, eax
0x14002adcb  jz      short loc_14002AE38
0x14002adcd  mov     edx, [rsp+28h+arg_8]
0x14002add1  mov     rcx, rbx
0x14002add4  call    cs:__imp_ASN1BEREncEndOfContents
0x14002adda  test    eax, eax
0x14002addc  jz      short loc_14002AE38
0x14002adde  lea     r8, [rsp+28h+arg_8]
0x14002ade3  mov     edx, 80000001h
0x14002ade8  mov     rcx, rbx
0x14002adeb  call    cs:__imp_ASN1BEREncExplicitTag
0x14002adf1  test    eax, eax
0x14002adf3  jz      short loc_14002AE38
0x14002adf5  mov     r9, [rdi+10h]
0x14002adf9  mov     edx, 4
0x14002adfe  mov     r8d, [rdi+8]
0x14002ae02  mov     rcx, rbx
0x14002ae05  call    cs:__imp_ASN1DEREncOctetString
0x14002ae0b  test    eax, eax
0x14002ae0d  jz      short loc_14002AE38
0x14002ae0f  mov     edx, [rsp+28h+arg_8]
0x14002ae13  mov     rcx, rbx
0x14002ae16  call    cs:__imp_ASN1BEREncEndOfContents
0x14002ae1c  test    eax, eax
0x14002ae1e  jz      short loc_14002AE38
0x14002ae20  mov     edx, [rsp+28h+arg_18]
0x14002ae24  mov     rcx, rbx
0x14002ae27  call    cs:__imp_ASN1BEREncEndOfContents
0x14002ae2d  xor     ecx, ecx
0x14002ae2f  test    eax, eax
0x14002ae31  setnz   cl
0x14002ae34  mov     eax, ecx
0x14002ae36  jmp     short loc_14002AE3A
0x14002ae38  xor     eax, eax
0x14002ae3a  mov     rbx, [rsp+28h+arg_0]
0x14002ae3f  add     rsp, 20h
0x14002ae43  pop     rdi
0x14002ae44  retn
```
