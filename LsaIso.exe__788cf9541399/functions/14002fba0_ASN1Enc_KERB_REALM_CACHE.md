# ASN1Enc_KERB_REALM_CACHE

- ea: `0x14002fba0`
- end: `0x14002fc09`
- name: `ASN1Enc_KERB_REALM_CACHE`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002fba0`
- `0x14002fc10`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x14002fbc7`
- `MSASN1!ASN1BEREncExplicitTag` at `0x14002fbc7`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002fbeb`
- `MSASN1!ASN1BEREncEndOfContents` at `0x14002fbeb`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_REALM_CACHE(__int64 a1, __int64 a2, LPCSTR *a3)
{
  int i; // eax
  __int64 v6; // rdx
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  for ( i = ASN1BEREncExplicitTag(a1, a2, &v8); i; i = ASN1Enc_KERB_REALM_CACHE_ENTRY(a1, v6, a3 + 1) )
  {
    a3 = (LPCSTR *)*a3;
    if ( !a3 )
      return (unsigned int)ASN1BEREncEndOfContents(a1, v8) != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14002fba0  mov     [rsp+arg_0], rbx
0x14002fba5  push    rdi
0x14002fba6  sub     rsp, 20h
0x14002fbaa  test    edx, edx
0x14002fbac  mov     [rsp+28h+arg_8], 0
0x14002fbb4  mov     eax, 10h
0x14002fbb9  mov     rbx, r8
0x14002fbbc  cmovz   edx, eax
0x14002fbbf  lea     r8, [rsp+28h+arg_8]
0x14002fbc4  mov     rdi, rcx
0x14002fbc7  call    cs:__imp_ASN1BEREncExplicitTag
0x14002fbcd  test    eax, eax
0x14002fbcf  jz      short loc_14002FBFC
0x14002fbd1  mov     rbx, [rbx]
0x14002fbd4  mov     rcx, rdi
0x14002fbd7  test    rbx, rbx
0x14002fbda  jz      short loc_14002FBE7
0x14002fbdc  lea     r8, [rbx+8]
0x14002fbe0  call    ASN1Enc_KERB_REALM_CACHE_ENTRY
0x14002fbe5  jmp     short loc_14002FBCD
0x14002fbe7  mov     edx, [rsp+28h+arg_8]
0x14002fbeb  call    cs:__imp_ASN1BEREncEndOfContents
0x14002fbf1  xor     ecx, ecx
0x14002fbf3  test    eax, eax
0x14002fbf5  setnz   cl
0x14002fbf8  mov     eax, ecx
0x14002fbfa  jmp     short loc_14002FBFE
0x14002fbfc  xor     eax, eax
0x14002fbfe  mov     rbx, [rsp+28h+arg_0]
0x14002fc03  add     rsp, 20h
0x14002fc07  pop     rdi
0x14002fc08  retn
```
