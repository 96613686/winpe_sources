# utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>>::_Uninit(void)

- ea: `0x18000b638`
- end: `0x18000b693`
- name: `?_Uninit@?$vector@VBinXmlVariantHolder@@V?$allocator@VBinXmlVariantHolder@@@utl@@@utl@@AEAAXXZ`
- size: `91`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180007fb8`
- `0x18000a838`
- `0x18000c420`
- `0x18000c6c8`
- `0x18001b3d4`
- `0x18001bbcc`

## callees

- `0x18000a100`
- `0x18000b638`
- `0x18000b6a0`

## pseudocode

```c
void __fastcall utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>>::_Uninit(__int64 a1)
{
  void **v1; // rsi
  __int64 v3; // rbx
  __int64 i; // rbx

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 != -1 )
  {
    v3 = *(_QWORD *)(a1 + 8) - (_QWORD)v1;
    *(_QWORD *)(a1 + 8) = v1;
    for ( i = v3 >> 4; i; BinXmlVariantHolder::Clear(&v1[2 * i]) )
      --i;
    operator delete(*(void **)a1);
  }
}

```

## disassembly

```asm
0x18000b638  mov     [rsp+arg_0], rbx
0x18000b63d  mov     [rsp+arg_8], rsi
0x18000b642  push    rdi
0x18000b643  sub     rsp, 20h
0x18000b647  mov     rsi, [rcx]
0x18000b64a  mov     rdi, rcx
0x18000b64d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000b651  jz      short loc_18000B683
0x18000b653  mov     rbx, [rcx+8]
0x18000b657  sub     rbx, rsi
0x18000b65a  mov     [rcx+8], rsi
0x18000b65e  sar     rbx, 4
0x18000b662  jmp     short loc_18000B676
0x18000b664  dec     rbx
0x18000b667  mov     rcx, rbx
0x18000b66a  shl     rcx, 4
0x18000b66e  add     rcx, rsi; this
0x18000b671  call    ?Clear@BinXmlVariantHolder@@QEAAXXZ; BinXmlVariantHolder::Clear(void)
0x18000b676  test    rbx, rbx
0x18000b679  jnz     short loc_18000B664
0x18000b67b  mov     rcx, [rdi]; void *
0x18000b67e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b683  mov     rbx, [rsp+28h+arg_0]
0x18000b688  mov     rsi, [rsp+28h+arg_8]
0x18000b68d  add     rsp, 20h
0x18000b691  pop     rdi
0x18000b692  retn
```
