# ASN1Dec_KERB_REALM_CACHE

- ea: `0x140026c70`
- end: `0x140026d41`
- name: `ASN1Dec_KERB_REALM_CACHE`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140026c70`
- `0x140026d48`

## import_xrefs

- `MSASN1!ASN1BERDecNotEndOfContents` at `0x140026cc3`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x140026cc3`
- `MSASN1!ASN1BERDecPeekTag` at `0x140026cd5`
- `MSASN1!ASN1BERDecPeekTag` at `0x140026cd5`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140026cb1`
- `MSASN1!ASN1BERDecExplicitTag` at `0x140026cb1`
- `MSASN1!ASN1DecAlloc` at `0x140026ce8`
- `MSASN1!ASN1DecAlloc` at `0x140026ce8`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026d1e`
- `MSASN1!ASN1BERDecEndOfContents` at `0x140026d1e`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_REALM_CACHE(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  int v9; // [rsp+48h] [rbp+18h] BYREF
  __int64 v10; // [rsp+58h] [rbp+28h] BYREF

  v10 = 0;
  v8 = 0;
  v9 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v10, &v8) )
    return 0;
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v10, v8) )
  {
    if ( !(unsigned int)ASN1BERDecPeekTag(v10, &v9) )
      return 0;
    v5 = ASN1DecAlloc(v10, 32);
    *a3 = v5;
    if ( !v5 || !ASN1Dec_KERB_REALM_CACHE_ENTRY(v10, v6, v5 + 8) )
      return 0;
    a3 = (__int64 *)*a3;
  }
  *a3 = 0;
  return (unsigned int)ASN1BERDecEndOfContents(a1, v10, v8) != 0;
}

```

## disassembly

```asm
0x140026c70  mov     [rsp-8+arg_0], rbx
0x140026c75  mov     [rsp-8+arg_10], rdi
0x140026c7a  push    rbp
0x140026c7b  mov     rbp, rsp
0x140026c7e  sub     rsp, 30h
0x140026c82  test    edx, edx
0x140026c84  mov     [rbp+arg_18], 0
0x140026c8c  mov     eax, 10h
0x140026c91  mov     [rbp+var_10], 0
0x140026c99  mov     rbx, r8
0x140026c9c  mov     [rbp+arg_8], 0
0x140026ca3  cmovz   edx, eax
0x140026ca6  lea     r9, [rbp+var_10]
0x140026caa  lea     r8, [rbp+arg_18]
0x140026cae  mov     rdi, rcx
0x140026cb1  call    cs:__imp_ASN1BERDecExplicitTag
0x140026cb7  test    eax, eax
0x140026cb9  jz      short loc_140026D2F
0x140026cbb  mov     rdx, [rbp+var_10]
0x140026cbf  mov     rcx, [rbp+arg_18]
0x140026cc3  call    cs:__imp_ASN1BERDecNotEndOfContents
0x140026cc9  test    eax, eax
0x140026ccb  jz      short loc_140026D0C
0x140026ccd  mov     rcx, [rbp+arg_18]
0x140026cd1  lea     rdx, [rbp+arg_8]
0x140026cd5  call    cs:__imp_ASN1BERDecPeekTag
0x140026cdb  test    eax, eax
0x140026cdd  jz      short loc_140026D2F
0x140026cdf  mov     rcx, [rbp+arg_18]
0x140026ce3  mov     edx, 20h ; ' '
0x140026ce8  call    cs:__imp_ASN1DecAlloc
0x140026cee  mov     [rbx], rax
0x140026cf1  test    rax, rax
0x140026cf4  jz      short loc_140026D2F
0x140026cf6  mov     rcx, [rbp+arg_18]
0x140026cfa  lea     r8, [rax+8]
0x140026cfe  call    ASN1Dec_KERB_REALM_CACHE_ENTRY
0x140026d03  test    eax, eax
0x140026d05  jz      short loc_140026D2F
0x140026d07  mov     rbx, [rbx]
0x140026d0a  jmp     short loc_140026CBB
0x140026d0c  mov     qword ptr [rbx], 0
0x140026d13  mov     rcx, rdi
0x140026d16  mov     r8, [rbp+var_10]
0x140026d1a  mov     rdx, [rbp+arg_18]
0x140026d1e  call    cs:__imp_ASN1BERDecEndOfContents
0x140026d24  xor     ecx, ecx
0x140026d26  test    eax, eax
0x140026d28  setnz   cl
0x140026d2b  mov     eax, ecx
0x140026d2d  jmp     short loc_140026D31
0x140026d2f  xor     eax, eax
0x140026d31  mov     rbx, [rsp+30h+arg_0]
0x140026d36  mov     rdi, [rsp+30h+arg_10]
0x140026d3b  add     rsp, 30h
0x140026d3f  pop     rbp
0x140026d40  retn
```
