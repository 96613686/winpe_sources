# ASN1Enc_GET_LENGTH

- ea: `0x1800210e0`
- end: `0x1800210fb`
- name: `ASN1Enc_GET_LENGTH`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSASN1!ASN1BEREncOpenType` at `0x1800210e7`
- `MSASN1!ASN1BEREncOpenType` at `0x1800210e7`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_GET_LENGTH(__int64 a1, __int64 a2, __int64 a3)
{
  return (unsigned int)ASN1BEREncOpenType(a1, a3) != 0;
}

```

## disassembly

```asm
0x1800210e0  sub     rsp, 28h
0x1800210e4  mov     rdx, r8
0x1800210e7  call    cs:__imp_ASN1BEREncOpenType
0x1800210ed  xor     ecx, ecx
0x1800210ef  test    eax, eax
0x1800210f1  setnz   cl
0x1800210f4  mov     eax, ecx
0x1800210f6  add     rsp, 28h
0x1800210fa  retn
```
