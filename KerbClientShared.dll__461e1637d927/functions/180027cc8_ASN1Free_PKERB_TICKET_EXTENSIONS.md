# ASN1Free_PKERB_TICKET_EXTENSIONS

- ea: `0x180027cc8`
- end: `0x180027d11`
- name: `ASN1Free_PKERB_TICKET_EXTENSIONS`
- size: `73`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d5f0`
- `0x180026e70`
- `0x1800270a4`
- `0x1800271f8`
- `0x180027300`
- `0x180027474`
- `0x180027d20`

## callees

- `0x180027cc8`

## import_xrefs

- `MSASN1!ASN1octetstring_free` at `0x180027cec`
- `MSASN1!ASN1octetstring_free` at `0x180027cec`
- `MSASN1!ASN1Free` at `0x180027cf8`
- `MSASN1!ASN1Free` at `0x180027cf8`

## pseudocode

```c
__int64 __fastcall ASN1Free_PKERB_TICKET_EXTENSIONS(_QWORD **a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbx
  __int64 result; // rax

  if ( a1 )
  {
    v1 = *a1;
    if ( *a1 )
    {
      do
      {
        if ( v1 != (_QWORD *)-8LL )
          ASN1octetstring_free(v1 + 2);
        v2 = (_QWORD *)*v1;
        result = ASN1Free(v1);
        v1 = v2;
      }
      while ( v2 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027cc8  test    rcx, rcx
0x180027ccb  jz      short locret_180027D10
0x180027ccd  mov     [rsp+arg_0], rbx
0x180027cd2  push    rdi
0x180027cd3  sub     rsp, 20h
0x180027cd7  mov     rdi, [rcx]
0x180027cda  test    rdi, rdi
0x180027cdd  jz      short loc_180027D06
0x180027cdf  lea     rcx, [rdi+8]
0x180027ce3  test    rcx, rcx
0x180027ce6  jz      short loc_180027CF2
0x180027ce8  add     rcx, 8
0x180027cec  call    cs:__imp_ASN1octetstring_free
0x180027cf2  mov     rbx, [rdi]
0x180027cf5  mov     rcx, rdi
0x180027cf8  call    cs:__imp_ASN1Free
0x180027cfe  mov     rdi, rbx
0x180027d01  test    rbx, rbx
0x180027d04  jnz     short loc_180027CDF
0x180027d06  mov     rbx, [rsp+28h+arg_0]
0x180027d0b  add     rsp, 20h
0x180027d0f  pop     rdi
0x180027d10  retn
```
