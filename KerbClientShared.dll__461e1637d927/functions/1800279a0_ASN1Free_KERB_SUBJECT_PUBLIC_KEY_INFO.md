# ASN1Free_KERB_SUBJECT_PUBLIC_KEY_INFO

- ea: `0x1800279a0`
- end: `0x1800279c2`
- name: `ASN1Free_KERB_SUBJECT_PUBLIC_KEY_INFO`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180026ee0`
- `0x180026f30`
- `0x1800273b0`
- `0x180027620`
- `0x180027760`
- `0x1800279d0`

## callees

- `0x180026db0`
- `0x1800279a0`

## import_xrefs

- `MSASN1!ASN1bitstring_free` at `0x1800279b6`
- `MSASN1!ASN1bitstring_free` at `0x1800279b6`

## pseudocode

```c
__int64 __fastcall ASN1Free_KERB_SUBJECT_PUBLIC_KEY_INFO(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
  {
    ASN1Free_KERB_ALGORITHM_IDENTIFIER();
    return ASN1bitstring_free(a1 + 32);
  }
  return result;
}

```

## disassembly

```asm
0x1800279a0  test    rcx, rcx
0x1800279a3  jz      short locret_1800279C1
0x1800279a5  push    rbx
0x1800279a6  sub     rsp, 20h
0x1800279aa  mov     rbx, rcx
0x1800279ad  call    ASN1Free_KERB_ALGORITHM_IDENTIFIER
0x1800279b2  lea     rcx, [rbx+20h]
0x1800279b6  call    cs:__imp_ASN1bitstring_free
0x1800279bc  add     rsp, 20h
0x1800279c0  pop     rbx
0x1800279c1  retn
```
