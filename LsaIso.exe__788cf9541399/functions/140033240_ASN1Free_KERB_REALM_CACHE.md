# ASN1Free_KERB_REALM_CACHE

- ea: `0x140033240`
- end: `0x140033288`
- name: `ASN1Free_KERB_REALM_CACHE`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140033240`

## import_xrefs

- `MSASN1!ASN1Free` at `0x14003326f`
- `MSASN1!ASN1Free` at `0x14003326f`
- `MSASN1!ASN1ztcharstring_free` at `0x140033263`
- `MSASN1!ASN1ztcharstring_free` at `0x140033263`

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
0x140033240  test    rcx, rcx
0x140033243  jz      short locret_140033287
0x140033245  mov     [rsp+arg_0], rbx
0x14003324a  push    rdi
0x14003324b  sub     rsp, 20h
0x14003324f  mov     rdi, [rcx]
0x140033252  test    rdi, rdi
0x140033255  jz      short loc_14003327D
0x140033257  lea     rcx, [rdi+8]
0x14003325b  test    rcx, rcx
0x14003325e  jz      short loc_140033269
0x140033260  mov     rcx, [rcx]
0x140033263  call    cs:__imp_ASN1ztcharstring_free
0x140033269  mov     rbx, [rdi]
0x14003326c  mov     rcx, rdi
0x14003326f  call    cs:__imp_ASN1Free
0x140033275  mov     rdi, rbx
0x140033278  test    rbx, rbx
0x14003327b  jnz     short loc_140033257
0x14003327d  mov     rbx, [rsp+28h+arg_0]
0x140033282  add     rsp, 20h
0x140033286  pop     rdi
0x140033287  retn
```
