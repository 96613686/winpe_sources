# ASN1Enc_KERB_REALM_CACHE

- ea: `0x180024c80`
- end: `0x180024ce9`
- name: `ASN1Enc_KERB_REALM_CACHE`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180024c80`
- `0x180024cf0`

## import_xrefs

- `MSASN1!ASN1BEREncEndOfContents` at `0x180024ccb`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180024ccb`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180024ca7`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180024ca7`

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
0x180024c80  mov     [rsp+arg_0], rbx
0x180024c85  push    rdi
0x180024c86  sub     rsp, 20h
0x180024c8a  test    edx, edx
0x180024c8c  mov     [rsp+28h+arg_8], 0
0x180024c94  mov     eax, 10h
0x180024c99  mov     rbx, r8
0x180024c9c  cmovz   edx, eax
0x180024c9f  lea     r8, [rsp+28h+arg_8]
0x180024ca4  mov     rdi, rcx
0x180024ca7  call    cs:__imp_ASN1BEREncExplicitTag
0x180024cad  test    eax, eax
0x180024caf  jz      short loc_180024CDC
0x180024cb1  mov     rbx, [rbx]
0x180024cb4  mov     rcx, rdi
0x180024cb7  test    rbx, rbx
0x180024cba  jz      short loc_180024CC7
0x180024cbc  lea     r8, [rbx+8]
0x180024cc0  call    ASN1Enc_KERB_REALM_CACHE_ENTRY
0x180024cc5  jmp     short loc_180024CAD
0x180024cc7  mov     edx, [rsp+28h+arg_8]
0x180024ccb  call    cs:__imp_ASN1BEREncEndOfContents
0x180024cd1  xor     ecx, ecx
0x180024cd3  test    eax, eax
0x180024cd5  setnz   cl
0x180024cd8  mov     eax, ecx
0x180024cda  jmp     short loc_180024CDE
0x180024cdc  xor     eax, eax
0x180024cde  mov     rbx, [rsp+28h+arg_0]
0x180024ce3  add     rsp, 20h
0x180024ce7  pop     rdi
0x180024ce8  retn
```
