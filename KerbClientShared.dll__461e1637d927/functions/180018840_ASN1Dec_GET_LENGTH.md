# ASN1Dec_GET_LENGTH

- ea: `0x180018840`
- end: `0x18001885b`
- name: `ASN1Dec_GET_LENGTH`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSASN1!ASN1BERDecOpenType2` at `0x180018847`
- `MSASN1!ASN1BERDecOpenType2` at `0x180018847`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_GET_LENGTH(__int64 a1, __int64 a2, __int64 a3)
{
  return (unsigned int)ASN1BERDecOpenType2(a1, a3) != 0;
}

```

## disassembly

```asm
0x180018840  sub     rsp, 28h
0x180018844  mov     rdx, r8
0x180018847  call    cs:__imp_ASN1BERDecOpenType2
0x18001884d  xor     ecx, ecx
0x18001884f  test    eax, eax
0x180018851  setnz   cl
0x180018854  mov     eax, ecx
0x180018856  add     rsp, 28h
0x18001885a  retn
```
