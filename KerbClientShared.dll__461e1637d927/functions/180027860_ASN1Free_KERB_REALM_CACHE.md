# ASN1Free_KERB_REALM_CACHE

- ea: `0x180027860`
- end: `0x1800278a8`
- name: `ASN1Free_KERB_REALM_CACHE`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180027860`

## import_xrefs

- `MSASN1!ASN1ztcharstring_free` at `0x180027883`
- `MSASN1!ASN1ztcharstring_free` at `0x180027883`
- `MSASN1!ASN1Free` at `0x18002788f`
- `MSASN1!ASN1Free` at `0x18002788f`

## pseudocode

```c
__int64 __fastcall ASN1Free_KERB_REALM_CACHE(_QWORD **a1)
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
          ASN1ztcharstring_free(v1[1]);
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
0x180027860  test    rcx, rcx
0x180027863  jz      short locret_1800278A7
0x180027865  mov     [rsp+arg_0], rbx
0x18002786a  push    rdi
0x18002786b  sub     rsp, 20h
0x18002786f  mov     rdi, [rcx]
0x180027872  test    rdi, rdi
0x180027875  jz      short loc_18002789D
0x180027877  lea     rcx, [rdi+8]
0x18002787b  test    rcx, rcx
0x18002787e  jz      short loc_180027889
0x180027880  mov     rcx, [rcx]
0x180027883  call    cs:__imp_ASN1ztcharstring_free
0x180027889  mov     rbx, [rdi]
0x18002788c  mov     rcx, rdi
0x18002788f  call    cs:__imp_ASN1Free
0x180027895  mov     rdi, rbx
0x180027898  test    rbx, rbx
0x18002789b  jnz     short loc_180027877
0x18002789d  mov     rbx, [rsp+28h+arg_0]
0x1800278a2  add     rsp, 20h
0x1800278a6  pop     rdi
0x1800278a7  retn
```
