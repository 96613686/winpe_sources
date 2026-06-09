# ASN1Dec_GET_LENGTH

- ea: `0x14001fa80`
- end: `0x14001fa9b`
- name: `ASN1Dec_GET_LENGTH`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSASN1!ASN1BERDecOpenType2` at `0x14001fa87`
- `MSASN1!ASN1BERDecOpenType2` at `0x14001fa87`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_GET_LENGTH(__int64 a1, __int64 a2, __int64 a3)
{
  return (unsigned int)ASN1BERDecOpenType2(a1, a3) != 0;
}

```

## disassembly

```asm
0x14001fa80  sub     rsp, 28h
0x14001fa84  mov     rdx, r8
0x14001fa87  call    cs:__imp_ASN1BERDecOpenType2
0x14001fa8d  xor     ecx, ecx
0x14001fa8f  test    eax, eax
0x14001fa91  setnz   cl
0x14001fa94  mov     eax, ecx
0x14001fa96  add     rsp, 28h
0x14001fa9a  retn
```
