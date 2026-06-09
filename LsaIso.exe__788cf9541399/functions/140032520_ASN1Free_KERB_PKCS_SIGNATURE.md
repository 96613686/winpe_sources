# ASN1Free_KERB_PKCS_SIGNATURE

- ea: `0x140032520`
- end: `0x140032538`
- name: `ASN1Free_KERB_PKCS_SIGNATURE`
- size: `24`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x140032450`
- `0x140032600`
- `0x140032834`
- `0x1400328c0`
- `0x140032950`
- `0x1400329a0`
- `0x140032a40`
- `0x140032b00`
- `0x140032b40`
- `0x140032c60`
- `0x140032cb8`
- `0x140032d40`
- `0x140032e80`
- `0x140032ef0`
- `0x140032fb0`
- `0x1400330f0`
- `0x140033290`
- `0x1400332d0`
- `0x140033300`
- `0x140033570`
- `0x1400335e0`
- `0x1400336b0`
- `0x140033700`

## callees

- `0x140032520`

## import_xrefs

- `MSASN1!ASN1octetstring_free` at `0x14003252d`
- `MSASN1!ASN1octetstring_free` at `0x14003252d`

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
0x140032520  sub     rsp, 28h
0x140032524  test    rcx, rcx
0x140032527  jz      short loc_140032533
0x140032529  add     rcx, 8
0x14003252d  call    cs:__imp_ASN1octetstring_free
0x140032533  add     rsp, 28h
0x140032537  retn
```
