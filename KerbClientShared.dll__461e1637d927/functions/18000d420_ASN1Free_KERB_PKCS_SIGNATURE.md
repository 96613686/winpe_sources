# ASN1Free_KERB_PKCS_SIGNATURE

- ea: `0x18000d420`
- end: `0x18000d438`
- name: `ASN1Free_KERB_PKCS_SIGNATURE`
- size: `24`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x1800096e0`
- `0x18000d390`
- `0x18000d564`
- `0x180026ce0`
- `0x180026e70`
- `0x1800270a4`
- `0x180027130`
- `0x180027180`
- `0x1800271f8`
- `0x1800272c0`
- `0x180027300`
- `0x1800273b0`
- `0x180027408`
- `0x180027560`
- `0x180027620`
- `0x180027760`
- `0x1800278b0`
- `0x1800278f0`
- `0x180027920`
- `0x180027b10`
- `0x180027b80`
- `0x180027c50`
- `0x180027ca0`

## callees

- `0x18000d420`

## import_xrefs

- `MSASN1!ASN1octetstring_free` at `0x18000d42d`
- `MSASN1!ASN1octetstring_free` at `0x18000d42d`

## pseudocode

```c
__int64 __fastcall ASN1Free_KERB_PKCS_SIGNATURE(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return ASN1octetstring_free(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x18000d420  sub     rsp, 28h
0x18000d424  test    rcx, rcx
0x18000d427  jz      short loc_18000D433
0x18000d429  add     rcx, 8
0x18000d42d  call    cs:__imp_ASN1octetstring_free
0x18000d433  add     rsp, 28h
0x18000d437  retn
```
