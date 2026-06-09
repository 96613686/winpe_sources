# ASN1Dec_GET_LENGTH

- ea: `0x180085bf0`
- end: `0x180085c0b`
- name: `ASN1Dec_GET_LENGTH`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSASN1!ASN1BERDecOpenType2` at `0x180085bf7`
- `MSASN1!ASN1BERDecOpenType2` at `0x180085bf7`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_GET_LENGTH(__int64 a1, __int64 a2, __int64 a3)
{
  return (unsigned int)ASN1BERDecOpenType2(a1, a3) != 0;
}

```

## disassembly

```asm
0x180085bf0  sub     rsp, 28h
0x180085bf4  mov     rdx, r8
0x180085bf7  call    cs:__imp_ASN1BERDecOpenType2
0x180085bfd  xor     ecx, ecx
0x180085bff  test    eax, eax
0x180085c01  setnz   cl
0x180085c04  mov     eax, ecx
0x180085c06  add     rsp, 28h
0x180085c0a  retn
```
