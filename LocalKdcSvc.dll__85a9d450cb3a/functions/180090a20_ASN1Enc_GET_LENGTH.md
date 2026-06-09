# ASN1Enc_GET_LENGTH

- ea: `0x180090a20`
- end: `0x180090a3b`
- name: `ASN1Enc_GET_LENGTH`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSASN1!ASN1BEREncOpenType` at `0x180090a27`
- `MSASN1!ASN1BEREncOpenType` at `0x180090a27`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_GET_LENGTH(__int64 a1, __int64 a2, __int64 a3)
{
  return (unsigned int)ASN1BEREncOpenType(a1, a3) != 0;
}

```

## disassembly

```asm
0x180090a20  sub     rsp, 28h
0x180090a24  mov     rdx, r8
0x180090a27  call    cs:__imp_ASN1BEREncOpenType
0x180090a2d  xor     ecx, ecx
0x180090a2f  test    eax, eax
0x180090a31  setnz   cl
0x180090a34  mov     eax, ecx
0x180090a36  add     rsp, 28h
0x180090a3a  retn
```
