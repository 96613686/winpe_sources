# ASN1Free_KERB_ENCRYPTED_DATA

- ea: `0x140032a20`
- end: `0x140032a38`
- name: `ASN1Free_KERB_ENCRYPTED_DATA`
- size: `24`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140032400`
- `0x140032560`
- `0x140032580`
- `0x1400327d0`
- `0x140032cb8`
- `0x140032dac`
- `0x140032fb0`
- `0x140033470`
- `0x140033680`
- `0x1400336b0`

## callees

- `0x140032a20`

## import_xrefs

- `MSASN1!ASN1octetstring_free` at `0x140032a2d`
- `MSASN1!ASN1octetstring_free` at `0x140032a2d`

## pseudocode

```c
__int64 __fastcall ASN1Free_KERB_ENCRYPTED_DATA(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return ASN1octetstring_free(a1 + 16);
  return result;
}

```

## disassembly

```asm
0x140032a20  sub     rsp, 28h
0x140032a24  test    rcx, rcx
0x140032a27  jz      short loc_140032A33
0x140032a29  add     rcx, 10h
0x140032a2d  call    cs:__imp_ASN1octetstring_free
0x140032a33  add     rsp, 28h
0x140032a37  retn
```
