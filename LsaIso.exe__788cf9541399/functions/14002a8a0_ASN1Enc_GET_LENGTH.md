# ASN1Enc_GET_LENGTH

- ea: `0x14002a8a0`
- end: `0x14002a8bb`
- name: `ASN1Enc_GET_LENGTH`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSASN1!ASN1BEREncOpenType` at `0x14002a8a7`
- `MSASN1!ASN1BEREncOpenType` at `0x14002a8a7`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_GET_LENGTH(__int64 a1, __int64 a2, __int64 a3)
{
  return (unsigned int)ASN1BEREncOpenType(a1, a3) != 0;
}

```

## disassembly

```asm
0x14002a8a0  sub     rsp, 28h
0x14002a8a4  mov     rdx, r8
0x14002a8a7  call    cs:__imp_ASN1BEREncOpenType
0x14002a8ad  xor     ecx, ecx
0x14002a8af  test    eax, eax
0x14002a8b1  setnz   cl
0x14002a8b4  mov     eax, ecx
0x14002a8b6  add     rsp, 28h
0x14002a8ba  retn
```
