# ASN1Dec_KERB_REALM_CACHE

- ea: `0x18001dd80`
- end: `0x18001de51`
- name: `ASN1Dec_KERB_REALM_CACHE`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001dd80`
- `0x18001de58`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x18001dde5`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001dde5`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001ddc1`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001ddc1`
- `MSASN1!ASN1DecAlloc` at `0x18001ddf8`
- `MSASN1!ASN1DecAlloc` at `0x18001ddf8`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001de2e`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001de2e`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18001ddd3`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18001ddd3`

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
0x18001dd80  mov     [rsp-8+arg_0], rbx
0x18001dd85  mov     [rsp-8+arg_10], rdi
0x18001dd8a  push    rbp
0x18001dd8b  mov     rbp, rsp
0x18001dd8e  sub     rsp, 30h
0x18001dd92  test    edx, edx
0x18001dd94  mov     [rbp+arg_18], 0
0x18001dd9c  mov     eax, 10h
0x18001dda1  mov     [rbp+var_10], 0
0x18001dda9  mov     rbx, r8
0x18001ddac  mov     [rbp+arg_8], 0
0x18001ddb3  cmovz   edx, eax
0x18001ddb6  lea     r9, [rbp+var_10]
0x18001ddba  lea     r8, [rbp+arg_18]
0x18001ddbe  mov     rdi, rcx
0x18001ddc1  call    cs:__imp_ASN1BERDecExplicitTag
0x18001ddc7  test    eax, eax
0x18001ddc9  jz      short loc_18001DE3F
0x18001ddcb  mov     rdx, [rbp+var_10]
0x18001ddcf  mov     rcx, [rbp+arg_18]
0x18001ddd3  call    cs:__imp_ASN1BERDecNotEndOfContents
0x18001ddd9  test    eax, eax
0x18001dddb  jz      short loc_18001DE1C
0x18001dddd  mov     rcx, [rbp+arg_18]
0x18001dde1  lea     rdx, [rbp+arg_8]
0x18001dde5  call    cs:__imp_ASN1BERDecPeekTag
0x18001ddeb  test    eax, eax
0x18001dded  jz      short loc_18001DE3F
0x18001ddef  mov     rcx, [rbp+arg_18]
0x18001ddf3  mov     edx, 20h ; ' '
0x18001ddf8  call    cs:__imp_ASN1DecAlloc
0x18001ddfe  mov     [rbx], rax
0x18001de01  test    rax, rax
0x18001de04  jz      short loc_18001DE3F
0x18001de06  mov     rcx, [rbp+arg_18]
0x18001de0a  lea     r8, [rax+8]
0x18001de0e  call    ASN1Dec_KERB_REALM_CACHE_ENTRY
0x18001de13  test    eax, eax
0x18001de15  jz      short loc_18001DE3F
0x18001de17  mov     rbx, [rbx]
0x18001de1a  jmp     short loc_18001DDCB
0x18001de1c  mov     qword ptr [rbx], 0
0x18001de23  mov     rcx, rdi
0x18001de26  mov     r8, [rbp+var_10]
0x18001de2a  mov     rdx, [rbp+arg_18]
0x18001de2e  call    cs:__imp_ASN1BERDecEndOfContents
0x18001de34  xor     ecx, ecx
0x18001de36  test    eax, eax
0x18001de38  setnz   cl
0x18001de3b  mov     eax, ecx
0x18001de3d  jmp     short loc_18001DE41
0x18001de3f  xor     eax, eax
0x18001de41  mov     rbx, [rsp+30h+arg_0]
0x18001de46  mov     rdi, [rsp+30h+arg_10]
0x18001de4b  add     rsp, 30h
0x18001de4f  pop     rbp
0x18001de50  retn
```
