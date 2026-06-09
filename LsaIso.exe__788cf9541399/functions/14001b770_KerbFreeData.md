# KerbFreeData

- ea: `0x14001b770`
- end: `0x14001b7c5`
- name: `KerbFreeData`
- size: `85`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x140014230`
- `0x140014250`
- `0x140014274`
- `0x140014298`
- `0x1400142c0`
- `0x140014f5c`
- `0x140015b90`
- `0x140016310`
- `0x140016ac0`
- `0x140017840`
- `0x140018340`
- `0x1400186e0`
- `0x140018ff0`
- `0x140019210`
- `0x140019f00`
- `0x14001bc24`

## callees

- `0x14001ae0c`
- `0x14001b1fc`
- `0x14001b770`

## import_xrefs

- `MSASN1!ASN1_FreeDecoded` at `0x14001b7a8`
- `MSASN1!ASN1_FreeDecoded` at `0x14001b7a8`

## pseudocode

```c
void __fastcall KerbFreeData(unsigned int a1, __int64 a2)
{
  struct ASN1decoding_s *v4; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    v4 = 0;
    if ( !(unsigned int)KerbInitAsn(0, &v4) )
    {
      ASN1_FreeDecoded(v4, a2, a1);
      KerbTermAsn(0, v4);
    }
  }
}

```

## disassembly

```asm
0x14001b770  test    rdx, rdx
0x14001b773  jz      short locret_14001B7C4
0x14001b775  mov     [rsp+arg_0], rbx
0x14001b77a  push    rdi
0x14001b77b  sub     rsp, 20h
0x14001b77f  mov     rbx, rdx
0x14001b782  mov     [rsp+28h+arg_8], 0
0x14001b78b  mov     edi, ecx
0x14001b78d  lea     rdx, [rsp+28h+arg_8]; struct ASN1decoding_s **
0x14001b792  xor     ecx, ecx; struct ASN1encoding_s **
0x14001b794  call    ?KerbInitAsn@@YAJPEAPEAUASN1encoding_s@@PEAPEAUASN1decoding_s@@@Z; KerbInitAsn(ASN1encoding_s * *,ASN1decoding_s * *)
0x14001b799  test    eax, eax
0x14001b79b  jnz     short loc_14001B7BA
0x14001b79d  mov     rcx, [rsp+28h+arg_8]
0x14001b7a2  mov     r8d, edi
0x14001b7a5  mov     rdx, rbx
0x14001b7a8  call    cs:__imp_ASN1_FreeDecoded
0x14001b7ae  mov     rdx, [rsp+28h+arg_8]; struct ASN1decoding_s *
0x14001b7b3  xor     ecx, ecx; struct ASN1encoding_s *
0x14001b7b5  call    ?KerbTermAsn@@YAXPEAUASN1encoding_s@@PEAUASN1decoding_s@@@Z; KerbTermAsn(ASN1encoding_s *,ASN1decoding_s *)
0x14001b7ba  mov     rbx, [rsp+28h+arg_0]
0x14001b7bf  add     rsp, 20h
0x14001b7c3  pop     rdi
0x14001b7c4  retn
```
