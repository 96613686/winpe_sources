# ASN1Free_KERB_ENCRYPTED_DATA

- ea: `0x18000d640`
- end: `0x18000d658`
- name: `ASN1Free_KERB_ENCRYPTED_DATA`
- size: `24`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d564`
- `0x18000d5f0`
- `0x180026c90`
- `0x180026dd0`
- `0x180026df0`
- `0x180027040`
- `0x180027474`
- `0x180027620`
- `0x180027c20`
- `0x180027c50`

## callees

- `0x18000d640`

## import_xrefs

- `MSASN1!ASN1octetstring_free` at `0x18000d64d`
- `MSASN1!ASN1octetstring_free` at `0x18000d64d`

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
0x18000d640  sub     rsp, 28h
0x18000d644  test    rcx, rcx
0x18000d647  jz      short loc_18000D653
0x18000d649  add     rcx, 10h
0x18000d64d  call    cs:__imp_ASN1octetstring_free
0x18000d653  add     rsp, 28h
0x18000d657  retn
```
